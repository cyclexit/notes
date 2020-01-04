Git note
========
### Index
* [Config multiple git accounts(based on SSH key)](#config-multiple-git-accounts)

# 1. Config multiple git accounts(based on SSH keys)

## (1) Generate multiple SSH keys
```
ssh-keygen -t rsa -C "your_email_1" -f ~/.ssh/id_rsa_1
ssh-keygen -t rsa -C "your_email_2" -f ~/.ssh/id_rsa_2
```

## (2) Add `config` file to `.ssh` folder
Content of `config` file
```
# first                                                                       
Host github.com
HostName github.com
User git
IdentityFile ~/.ssh/id_rsa_1

# second                                                               
Host ieit.github.com
HostName github.com
User git
IdentityFile ~/.ssh/id_rsa_2
```
For the second host, the prefix `ieit` can be replaced by whatever you want.

## (3) [Add SSH keys to the corresponding repository](https://help.github.com/en/enterprise/2.15/user/articles/adding-a-new-ssh-key-to-your-github-account)

## (4) Test SSH connection
```
ssh -T git@github.com
ssh -T git@ieit.github.com
```

## (5) Unset the global git user setting
```
git config –global -–unset user.name
git config –global -–unset user.email
```

## (6) Set the user in each local folder
```
git config user.name “name”
git config user.email “email”
```

## (7) Redirect `origin` in each local folder
```
git remote rm origin
git remote add origin git@host:repository
```
Here `host` is the value of Host in the config file, and `repository` is the name of your repository.
