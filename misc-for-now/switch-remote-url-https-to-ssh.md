# Switch Your Git Repo's Remote URL to Use SSH Instead of HTTPS

If you try to push changes to your repository and you're prompted for your username/password, it means your project's
remote url is using https. To verify that type:

```bash
$ git remote -v
> origin  https://github.com/USERNAME/REPOSITORY.git (fetch)
> origin  https://github.com/USERNAME/REPOSITORY.git (push)
```

To switch to SSH, type:
```bash
$ git remote set-url origin git@github.com:USERNAME/REPOSITORY.git
```

Then type the first command again to verify the changes are correct.


NOTE: This assumes you already have a ssh key generated and saved to your account.
