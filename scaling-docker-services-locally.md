# How to Locally Scale Docker Containers With Docker Compose and Load Balancing

## TL;DR
```
docker-compose scale <service-name>=<# of instances>
```

## Initial Problem
We were having issues with the video quality of our MVP Google Meet integration.
Our recorder would set recorded video data to a specified endpoint as the data
became available. The issue though was that each request was being routed to a
different instance of our backend. In other words, I forgot that our load
balancer was doing it's job. 

Though I could see it plainly in our logs, I decided to see if I could replicate
this in my local environment. The only issue is I need to have multiple
instances of our app running. Thank goodness for docker-compose.

After adding a simple nginx container that routed all localhost requests, I
could see each request being routed to the different containers.

The fix for the overarching issue requires a separate entry.

Here's the nginx config and compose definition:

```
user nginx;

events
{
  worker_connections 1000;
}
http
{
  client_max_body_size 300M;

  server
  {
    listen 4000;


    gzip on;
    gzip_vary on;
    gzip_proxied any;
    gzip_types text/plain text/css text/js text/xml text/javascript application/javascript application/x-javascript application/json application/xml application/rss+xml image/svg+xml;
    add_header X-Frame-Options SAMEORIGIN always;
    location /
    {
      proxy_pass http://app:3000;
    }
  }
}
```

```
version: "3"
services:
  app:
    build:
      dockerfile: Dockerfile
...
...
  nginx:
    image: nginx:latest
    volumes:
      - ./app/nginx.conf:/etc/nginx/nginx.conf
    depends_on:
      - app
    ports:
      - 4000:4000
```

