# git Commands

```sh
git config --global user.name "user_name"
```

```sh
git config --global user.email "email"
```

```sh
ssh-keygen -t rsa -b 4096 -C "email"
eval ssh-agent -s
exec ssh-agent bash
ssh-add ~/.ssh/id_rsa
cat ~./ssh/id_rsa.pub  #add to github
ssh -T git@github.com
```

```sh
git init
git add .
git commit -m "first commit"
git remote add origin git@github.com:user_account/user_repository.git
git push -u origin master
```

```sh
git remote -v
git remote rm origin
```

```sh
git status
git log
```

```sh
git pull
git push origin master
```

| Description | Link |
| ------ | ------ |
| - | -|