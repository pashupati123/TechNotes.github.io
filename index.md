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

#9. Range vs Xrange
      xrange returns an iterator and only keeps one number in memory at a time. range keeps the entire list of numbers in memory.

#10. Immutable vs Mutable data type
      Whenever an object is instantiated, it is assigned a unique object id. The type of the object is defined at the runtime and it can’t be changed afterwards.         However, it’s state can be changed if it is a mutable object.
      mmutable: int, float, bool, string, unicode, tuple.
      Mutable: array, dict, set, list
      
#11. Exception Handling
      https://www.w3schools.com/python/python_try_except.asp
      Syntax Error: As the name suggest this error is caused by wrong syntax in the code. It leads to the termination of the program.
      Exceptions: Exceptions are raised when the program is syntactically correct but the code resulted in an error. This error does not stop the execution of the       program, however, it changes the normal flow of the program.
      
      Sample Code
      
          try:
            # Some Code.... 
          except:
            # optional block
            # Handling of exception (if required)
          else:
            # execute if no exception
          finally:
            # Some code .....(always executed)
          
          AND 
          
          try:  
            raise NameError("Hi there")  # Raise Error 
          except NameError: 
            print "An exception"
          raise  # To determine whether the exception was raised or not 

#12. Python Class
      Class: https://www.w3schools.com/python/python_classes.asp
      Class Parent:
         def __init__(self, name, age):
                  self.name=name
                  self.age=age
        
         def getDate(self):
                  return(self.name+self.age)

      Class Child(Parent):
          def __init__(self,name,age):
             super().__init__(name, age)

      p1=Child(x,6)
      print(p1.getData())

#13. Implement Graph in python 

      graph={“v1”:[],”v2”:[]……}
      Using dict where key value will be list

      Queue:
           List = []
           list.add(item) -> similar to queue
           Pop element from front:
           element = List[0]
           List.remove(element)

      Stack:
          Pop element from last
          element = List[len(List)-1]
          List.remove(element)
          
#14. Rsyslog
     Rsyslog is an Open Source logging program, which is the most popular logging mechanism in a huge number of Linux distributions.
     Rsyslog daemon in CentOS can be configured to run as a server in order collect log messages from multiple network devices.
     https://www.tecmint.com/install-rsyslog-centralized-logging-in-centos-ubuntu/

#15. IPC mechanism
     Inter Process Communication (IPC) refers to a mechanism, where the operating systems allow various processes to communicate with each other. This involves          synchronizing their actions and managing shared data.
     https://www.geeksforgeeks.org/inter-process-communication-ipc/#:~:text=Inter%20process%20communication%20(IPC)%20is,of%20co%2Doperation%20between%20them
     
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
    
    #pipenv install psycopg2-binary
    from flask import Flask
    import pandas as pd
    import psycopg2  
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
#1. React Tutorial important Links

    1.Introduction: https://www.geeksforgeeks.org/react-js-introduction-working/
    2.Create Components: https://www.tutorialspoint.com/reactjs/reactjs_components.htm
    3.Hooks:
         1. https://www.andreasreiterer.at/react-useeffect-hook-loop/
         2. https://overreacted.io/a-complete-guide-to-useeffect/
         3. https://egghead.io/lessons/react-use-react-useeffect-hook-to-see-how-many-times-component-mounts-and-unmounts?pl=learn-react-lazy-memo-usestate-and-               useeffect-in-10-minutes-3bd981f6
         4. Context API: https://www.youtube.com/watch?v=6RhOzQciVwI&list=PL4cUxeGkcC9hNokByJilPg5g9m2APUePI&index=1
         
     4.React SearchBar: https://www.npmjs.com/package/material-ui-search-bar
     5.React Charts:
         1.3d pie chart: https://react-d3-library.github.io/
         2.https://www.npmjs.com/package/react-charts
         3.https://react-charts.js.org/examples/axis-options
     
     6.How to call two function on click button: https://stackoverflow.com/questions/26069238/call-multiple-functions-onclick-reactjs
     7.Onclick error: https://stackoverflow.com/questions/41429020/reactjs-button-onclick-gets-called-during-render
     8.Component Life Cycle: https://www.geeksforgeeks.org/reactjs-lifecycle-components/
     9.Material UI: https://material-ui.com/
     
#2. Steps To create the React App
    
       1. Install NodeJs pacakage: 
          https://nodejs.org/en/
          
       Commands: 
       1. Install nvm using curl 
          curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.3/install.sh | bash
       2. load nvm
           export NVM_DIR="$([ -z "${XDG_CONFIG_HOME-}" ] && printf %s "${HOME}/.nvm" || printf %s "${XDG_CONFIG_HOME}/nvm")"
           [-s "$NVM_DIR/nvm.sh"] && \. "$NVM_DIR/nvm.sh"
       3. Verify Installation
           command -v nvm 
       4. Install Node
           nvm install 12.14.0
       5. Check all version of Node installed
           nvm ls
       6. Switch Node
           nvm use 12.14.0
       7. To make the code Linted
           To check run:   npm run lint
           To fix the lint:  npm run lint — —fix
           
         Troubleshoot
        1. Source command update bash_profile
            source ~/.nvm/nvm.sh
        3. Upgrade npm version
            npm install -g npm@6.13.4
        3. npx cannot be found
            npm install -g npx
        4. Clear the cache
            npm cache clean --force
        5. Most of time Delete the node_module and again do npm install works

#3. ReactJs Api Call

       Axios : https://www.npmjs.com/package/axios
       Axios install : npm install axios
       Sample code for Class Component:
       
               export class Apicall extends Component {
                        constructor(props) {
                        super(props)
                        this.state = {
                              data: [],
                              }
                        }

                       apicall = () => {
                            axios.get('https://jsonplaceholder.typicode.com/users').then(response => {
                            this.setState({ data: response.data })
                            console.log(this.state.data)
                           })
                       }
                       render() {
                          return(
                          <div>
                          <button onClick={this.apicall}>Api Call</button>
                          <table>
                          <tr>
                         <td>id</td>
                         <td>name</td>
                         </tr>
                         {this.state.data.map(index => {
                                   return (
                                            <tr>
                                            <td>{index.id}</td>
                                            <td>{index.address.street}</td>
                                            </tr>
                                          )
                          })}
                        </table>
                        </div>
                          )
                       }
                 }
                 
                 
         Sample code for Functional Component:
             
                 import React,{useState,useEffect} from 'react'
                 import axios from 'axios'

                 export default function Axiosfun() {
                      const [myData,setMydata] = useState([])
                      
                      const apicall = () => {
                                axios.get('https://jsonplaceholder.typicode.com/users').then(
                                           res=>{
                                                   setMydata(res.data)
                                                   console.log(res.data)
                                                 }
                                         )
                        }

                       useEffect(()=>{
                                 apicall()
                                },[])
                                
                        return (
                               <div>
                                     <h1>I m from Axios Function Component!!</h1>
                                </div>
                                )
                   }
         
                 
#4. ReactJs Testing Framework
       
       JEST:Jest is the javascript test runner tool library used for testing react application .it can be installed using npm.
       Other testing tool: enzyme,mocha

       JEST Installation:
           npm install —save jest@22.3.0
       
       Jest File structure
            Create a test file in a __tests__/*.js directory(Any files inside a folder named __tests__ are considered tests)
            Create a test file with *.spec.js or *.test.js as part of the filename
            Use describe and it block
            Verify that Jest automatically recognizes these test files
            
       JEST Link:
            https://rossbulat.medium.com/testing-in-react-with-jest-and-enzyme-an-introduction-99ce047dfcf8
            https://pusher.com/tutorials/react-jest-enzyme
            https://app.pluralsight.com/library/courses/testing-react-applications-jest/table-of-contents
            https://blog.logrocket.com/testing-state-changes-in-react-functional-components/
      
       Jest & enzyme: 1) https://www.npmjs.com/package/jest-enzyme
                      2)https://medium.com/@rossbulat/testing-in-react-with-jest-and-enzyme-an-introduction-99ce047dfcf8
     
       Sample Code for JEST & Enzyme
            
            //import { mount, shallow, render } from ‘enzyme';
           //Mount: Full DOM rendering including child components
           //Shallow: Renders only the single component, not including its children. 
          //Render: Renders to static HTML, including children
          //simulator allows to execute the application under test as if it was the actual device.

           import React from 'react'
           import ReactDOM from 'react-dom'
           import Button from './Button'
           import { render } from '@testing-library/react'
           import { shallow } from 'enzyme'
           import '@testing-library/jest-dom/extend-expect'

           describe('Testing Demo Jest ', () => {
                it('button render without crashing', () => {
               const div = document.createElement('div')
               ReactDOM.render(<Button label={'Click Me'} />, div)
               })

          it('renders button correctly', () => {
               const { getByTestId } = render(<Button label="Click Me"></Button>)
               expect(getByTestId('button')).toHaveTextContent('Click Me')
               })
          })

          describe('Testing Demo using Enzyme', () => {
                  it('knows that 2 and 2 make 4', () => {
                        expect(2 + 2).toBe(4);
                });
                 it('snapshot component test', () => {
                       const wrapper = shallow(<Button label={'Click M'} />)
                       expect(wrapper).toMatchSnapshot()
                })
                it('testing button onClick handle', () => {
                      const wrapper = shallow(<Button label={'Click Me'} />)
                      const incrementBtn = wrapper.find('button');
                      incrementBtn.simulate('click');
                      const text = wrapper.find('p').text();
                      expect(text).toEqual('count:1');
                 })
           })
            
           
    
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

