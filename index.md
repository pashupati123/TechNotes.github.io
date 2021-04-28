### Github
Github handy commands

```markdown
#1. Adding ssh key to Github Account
    https://help.github.com/en/enterprise/2.17/user/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent

#2. Recover 2FA for Github Account
    https://docs.github.com/en/github/authenticating-to-github/recovering-your-account-if-you-lose-your-2fa-credentials

#3. Github Commands
- To create new branch:
     git branch branch_name
    
- To Delete any branch:
     git branch -d branch_name

- To Delete Remote Branch
     git push -d origin <branch_name>

- To checkout branch:
     git checkout branch_name 
 
- To check all branch:
     git branch --all 

- To push the changes:
     git status
     git add .
     git commit -m “msg”
     git push origin branch_name 

#4. How to Raise PR
- Step1: fork the repo
- Step2: git clone the forked repo from your account
- Step3: create new branch
            Git checkout -b “branch_name”
- Step4: make your changes
- Step5: 
        git add .
        git commit -m “msg”
        git push origin “branch_name”

- Step6: Go to Github repo click “compare and pull request”
- Step7: click on create pull request

#5. Git Stash
    https://www.atlassian.com/git/tutorials/saving-changes/git-stash#:~:text=git%20stash%20temporarily%20shelves%20(or,re%2Dapply%20them%20later%20on

```
### Docker

Write docker file => Build the Images By Running the docker file => Run the image to bring up the container

```markdown
Basic Commands for Docker (run the commands where dockerfile present)

- To check running images
      docker ps 
- To list the docker images
      docker images or docker images -a 
- To forcely delete the image
      docker rmi -f image_name 
- To pull the image
      docker pull image_name 
- To build the image from the dockerfile
      docker build -t tag_file -f docker_file
- To run the Docker image, port1:local machine port, port2: container port
      docker run  -it -p port1:port2 image_name 
- To Run the container in background 
      docker run -d -p port1:port2 image_name        
- To stopt the conatiner
      docker stop image_name
           
```


### Python

Steps for Python Intsalltaion and Creating virtual Env using pipenv

```markdown
#1. Install Home-brew
      ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

#2. Using brew To install python
      brew install python3
      brew install python
      
#3. Using brew To upgrade python
      brew upgrade python3
      brew upgrade python
      
#3. Using brew To swith python version
      brew switch python 3.x.x

#4. Using brew To link python
      brew link python 3.x.x
      
#5. Install pip
      python3 -m pip install --upgrade pip
      python -m pip install --upgrade pip

#6. Install pipenv (To create Virtual Env)
      pipenv —version
      pip3 install pipenv
      pip install pipenv
      
 #7. To Check the pipenv commands
      pipenv
 
 #8. Pipenv Commands
     https://pashupati123.github.io/Pipenv-Packaging-Tool/
 
```

### ReactJS

ReactJS Notes

```markdown
Syntax highlighted code block

# Python
## ReactJS
### PostgresSql

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

### PostgreSql

PostgreSql Notes

```markdown
Syntax highlighted code block

# Python
## ReactJS
### PostgresSql

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```



