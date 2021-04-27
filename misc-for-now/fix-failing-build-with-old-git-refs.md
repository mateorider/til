# Fixing a Failing Build Due to Old Git Refs

When I was trying to build `phone-sms-inbound` it blew up saying
```
$ go build
go: weavelab.xyz/phone-sms-data@v1.0.0 requires
        weavelab.xyz/monorail@v0.1.160: reading weavelab.xyz/monorail/go.mod at revision v0.1.160: git fetch -f origin refs/heads/*:refs/heads/* refs/tags/*:refs/tags/* in /Users/matt.rider@getweave.com/workspace/go/pkg/mod/cache/vcs/73917a0759d28fd0528c6842d8ce94ac2bb0740e4954ad44c65771a7827a3591: exit status 1:
        error: refs/heads/accept-quote-resp does not point to a valid object!
        error: refs/heads/add-validate-e911 does not point to a valid object!
        error: refs/heads/agreement-list does not point to a valid object!
        ...
        ...
        fatal: bad object 3a04a9d596ea3fc179660d2f49d929960e27fd4f
        error: ssh://github.com/weave-lab/monorail did not send all necessary objects
```

After deleting and re `go get -u`ing all the repos I thought were affected I still got the same error.

I also tried clearing my cache and modcache `go clean -cache -modcache -r -i` to no avail.

Ultimately the fix just required me to delete the cached hash/ref/branch/whatever that the error was complaining about.

```
$ rm -rf ~/workspace/go/pkg/mod/cache/vcs/73917a0759d28fd0528c6842d8ce94ac2bb0740e4954ad44c65771a7827a3591
```

