### Github
Github handy commands

```markdown
#1. Adding ssh key to Github Account
    https://help.github.com/en/enterprise/2.17/user/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent

#2. Recover 2FA for Github Account
    https://docs.github.com/en/github/authenticating-to-github/recovering-your-account-if-you-lose-your-2fa-credentials

#3. Github Commands
 3.1 To create new branch:
        git branch branch_name
    
 3.2 To Delete any branch:
        git branch -d branch_name

 3.3 To Delete Remote Branch
        git push -d origin <branch_name>

 3.4 To checkout branch:
        git checkout branch_name 
 
 3.5 To check all branch:
        git branch --all 

 3.6 To push the changes:
        git status
        git add .
        git commit -m “msg”
        git push origin branch_name 

#4. How to Raise PR
  Step1: fork the repo
  Step2: git clone the forked repo from your account
  Step3: create new branch
            Git checkout -b “branch_name” 
  Step4: make your changes
  Step5: 
        git add .
        git commit -m “msg”
        git push origin “branch_name”

 Step6: Go to Github repo click “compare and pull request”
 Step7: click on create pull request

#5. Git Stash
    https://www.atlassian.com/git/tutorials/saving-changes/git-stash#:~:text=git%20stash%20temporarily%20shelves%20(or,re%2Dapply%20them%20later%20on

```
### Docker

Write docker file => Build the Images By Running the docker file => Run the image to bring up the container

```markdown
Basic Commands for Docker (run the commands where dockerfile present)

#1. To check running images
       docker ps 
#2. To list the docker images
       docker images or docker images -a 
#3. To forcely delete the image
       docker rmi -f image_name 
#4. To pull the image
       docker pull image_name 
#5. To build the image from the dockerfile
       docker build -t tag_file -f docker_file
#6. To run the Docker image, port1:local machine port, port2: container port
       docker run  -it -p port1:port2 image_name 
#7. To Run the container in background 
       docker run -d -p port1:port2 image_name        
#8. To stopt the conatiner
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
### Flask

Flask is a light wieght web framework,this means flask provides tools,libraries and technologies that allow to build a web application.

```markdown
#1. Install Flask
  pip install flask
  pipenv install flask (using venv with help of pipenv tool)
  
#2. Sample Code

    from flask import Flask, jsonify, request 
    from flask_cors import CORS

    # Create the application.
    app = Flask(__name__)
    CORS(app)

    @app.route('/health')
    def helloIndex():
          return 'Hello World from Python Flask!'

    if __name__ == '__main__':
          app.debug=True
          app.run(host='0.0.0.0', port=8050)
          
          
#3. Sample code : To connect with PostgreSql Server
  
     from flask import Flask
     import pandas as pd
     import psycopg2  #pipenv install psycopg2-binary
     import yaml

     app = Flask(__name__)

     #For local development
     with open("/secret.yml", "r") as f:
          pg_secrets = yaml.safe_load(f)

     #For Hosting Server 
     # with open("/host_path/secret.yml", "r") as f:
     #     pg_secrets = yaml.safe_load(f)

     dbname = pg_secrets["database"]["pg_db"]
     host = pg_secrets["database"]["pg_host"]
     port = pg_secrets["database"]["pg_port"]
     user = pg_secrets["database"]["pg_username"]
     password = pg_secrets["database"]["pg_password"]

     connection = psycopg2.connect(user=user, password=password, host=host, port=port, database=dbname)
    
     sql = """ Select * from praxisdays.udf_get_all_pot_user_feedbacks(); """
     df = pd.read_sql_query(sql, connection)

     @app.route('/getrecord')
     def getrecord():
          recordJSON = df.to_json(orient='records')
          return(recordJSON)

     @app.route('/health')
     def helloIndex():
         return 'Hello World from Python Flask!'
    
     if __name__ == '__main__':
          app.debug=True
          app.run(host='0.0.0.0', port=8050)

#4. Format of Secret.yml

      database:
      pg_host:
        pg_server_name
      pg_port:
        5432
      pg_username:
        your_username
      pg_password:
        xxxxxxxxx
      pg_db:
        db_name
    
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
### NodeJs

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

### Redis

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

