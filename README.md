This task is from the GitHub link provided in the document.

At first I follow the link to open a new Dockerfile, and type in the following:

FROM debian:9.5-slim

ADD entrypoint.sh /entrypoint.sh

RUN chmod +x /entrypoint.sh

ENTRYPOINT ["/entrypoint.sh"]


Then I commit the file and move onto step 2.

Step 2 I create the entrypoint script. I use the following link to quickly create a new file called entrypoint.sh. This creates the file in the same repository.
In the file I type in the following:

#!/bin/sh -1


sh -c "echo Hello world my name is $INPUT_MY_NAME"


I commit changes and push it into GitHub. In this instance I have split the browser into two so I can read on the left and do on the right.

Step 3, after the creation of this I follow the new link called: action-a/action.yml , which creates the link automatically action.yml file and I input the following:

name: "Hello Actions"

description: "Greet someone"

author: "octocat@github.com"

inputs:
  
  MY_NAME:
    
    description: "Who to greet"
    
    required: true
    
    default: "World"

runs:
  
  using: "docker"
  
  image: "Dockerfile"

branding:
  
  icon: "mic"
  
  color: "purple"
  
  
There is a tab space from input to MY_NAME to description, runs to using, and branding to icon. I save changes and commit then push into GitHub. Please input MY_NAME in the editing process and then I await instructions onto step 4.


Step 4 I follow again for the new link called main.yml and type in the following:

name: A workflow for my Hello World file.

on: push

I commit and push. Step 5 is to edit main.yml. Open that file and edit it. Without deleting the previous input and directly under on no space breaks write the following:

jobs:

  build:
  
    name: Hello world action
    
    runs-on: ubuntu-latest
    
    steps:
    
      - uses: actions/checkout@v1
      
      - uses: ./action-a
      
        with:
        
          MY_NAME: "Mona"
          
Please input build in your editing process. Now commit changes and it will automatically push and will move onto Step 6. Step 6 is looking for the action on the bar below your username/repository name like this:

![image](https://user-images.githubusercontent.com/87336176/129272121-e82d3c6f-f5e7-45cc-bdd3-4b766805b1dd.png)

Once it has given the green check you can move on. If it has given you a red X then there is something wrong and needs revision. It is mainly in the main.yml file as I had to redo-it a few times to get it right. Step 7 would be merging into the main branch. For this you need to go to the bot conversation and merge it there. To get there you need to click on the Pull Requests

![image](https://user-images.githubusercontent.com/87336176/129272566-3f09a5c2-cb7c-45da-9473-0cea11656638.png)


As it opens the page: it would be in open and you have to click the Create Dockerfile

![image](https://user-images.githubusercontent.com/87336176/129272822-1761bda1-d422-4576-923f-01beb6e20d81.png)


After that at the bottom there would be a Pull Request Merge in green above the witing comment section and click on merge. Once merged it would give you this:

![image](https://user-images.githubusercontent.com/87336176/129273023-9fecc3db-8974-42cb-95ee-18f52cd8450f.png)

And now you are done. 
