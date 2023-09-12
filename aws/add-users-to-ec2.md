# How to add users to an EC2 instance

See the [Official AWS Walkthrough](https://aws.amazon.com/premiumsupport/knowledge-center/new-user-accounts-linux-instance/)

## Steps
1. Create user
```
$ sudo adduser new_user
```
2. Change security context to become user
```
$ sudo su - new_user
```
3. Create .ssh dir
```
$ mkdir ~/.ssh
```
4. Give .ssh dir correct permissions
```
$ chmod ~/.ssh 700
```
5. Create authorized_keys file
```
$ touch ~/.ssh/authorized_keys
```
6. Give file correct permissions
```
$ chmod ~/.ssh/authorized_keys 600
```
7. Add public key from key pair to authorized_keys file
```
$ ssh-keygen -y -f /path_to_key_pair/my-key-pair.pem
...
# make sure the pem file has the correct permissions (chmod 400 file.pem)
```
8. Log out and verify login works with username and key file

