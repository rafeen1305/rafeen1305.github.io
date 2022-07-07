# rafeen1305.github.io
## Link : [Main Article](https://medium.com/@viviennediegoencarnacion/manage-github-and-gitlab-accounts-on-single-machine-with-ssh-keys-on-mac-43fda49b7c8d)

## **step 1 : Generate new ssh key**
- [ ] ssh-keygen -t rsa -C "gitlab@mail.com" -f ~/.ssh/id_rsa_gitlab
- [ ] ssh-keygen -t rsa -C "github@mail.com" -f ~/.ssh/id_rsa_github

which will generate 4 files
 - ~/.ssh/id_rsa_github
 - ~/.ssh/id_rsa_github.pub
 - ~/.ssh/id_rsa_gitlab
 - ~/.ssh/id_rsa_gitlab.pub
  
## **Step 2. Add SSH keys to Github, and Gitlab**
- [ ] Git Hub :
  Settings > SSH and GPG Keys > New SSH key
- [ ] Git Lab :
  Settings > SSH Keys
  
## **Step 3: Register SSH Keys with the ssh-agent**
  - [ ] ssh-add ~/.ssh/id_rsa_github
  - [ ] ssh-add ~/.ssh/id_rsa_gitlab
  
## **Step 4: Editing Config File**
```
  Host github.com
   HostName ssh.github.com
   User git
   IdentityFile ~/.ssh/id_rsa_github
   PreferredAuthentications publickey
   Port 443
 ```
 ```
  Host gitlab.com
     HostName altssh.gitlab.com
     User git
     IdentityFile ~/.ssh/id_rsa_gitlab
     Port 443
     PreferredAuthentications publickey
 ```
