# dmoney-api-testing-newman

#Automated dmoney API testing with Postman and generated report by Newman

This is the Postman Documentation link: https://documenter.getpostman.com/view/14844920/UzBsGPRz 

**Prerequisite**

1. Install VS Code
2. Install Node js

**Steps**

1. Download repository from github 

2. Open downloaded folder through VS Code 

3. Click open terminal and run a command to install newman package 

**npm i newman**

![image](https://user-images.githubusercontent.com/45478777/175780343-50ec18be-bd7b-418f-b9ed-56c234606440.png)

Note that, package.json will modify automatically once newman is installed

![image](https://user-images.githubusercontent.com/45478777/175779966-66fa8e34-0b75-463d-bd14-9018034cb942.png)

4. Next, run this command in the terminal same as above command:

**npx newman run .\collection\dmoneyCollection.json**

![image](https://user-images.githubusercontent.com/45478777/175780050-a3d3b2a8-5431-4cd0-8401-f38c7a5a65b6.png)

**HTML report generate using Newman**

1. Install following package by this command:

**npm i newman-reporter-htmlextra**

2. Now hit this command:

**npm test**

3. Next, you will see a html report named report.html will be generate in Reports folder, since the Reports folder will be there. 

![image](https://user-images.githubusercontent.com/45478777/175780118-6ea9983e-80b5-4886-aef5-bb13c293cb0f.png)

4. Now reveal the folder and open the html file and you will see the result in a html report

![image](https://user-images.githubusercontent.com/45478777/175780188-ef624854-89ae-4e8f-93fc-4dd1083d72d8.png)

