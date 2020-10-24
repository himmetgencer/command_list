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
cat ~/.ssh/id_rsa.pub  #add to github
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

```sh
git branch branch_name
git checkout branch_name
git diff branch1 branch2
```

```sh
git merge branch_name
```

```sh
git revert hash_code
git reset --keep hash_code //local commitleri saklı tutar.
git reset --soft hash_code //staged file haline getirir.
git reset --mixed hash_code //untracked hale getirir.
git reset --hard hash_code //herseyi siler geriye dondurur
git check-ignore "folder_name"
```

| Description | Link |
| ------ | ------ |
| - | -|
