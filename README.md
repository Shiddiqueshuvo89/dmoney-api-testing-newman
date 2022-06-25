# dmoney-api-testing-newman

#Automated dmoney API testing with Postman and generated report by Newman

**Steps**

**1.** Import DmoneyUserB4 Collection in Postman 

![image](https://user-images.githubusercontent.com/45478777/175765962-a2c39801-a98b-4eb3-be90-cd76e8a90d59.png)

**2.** Add Test Cases and do API Testing 

**3.** Apply Run Collection

![image](https://user-images.githubusercontent.com/45478777/175766079-8aa8ba12-a2af-462f-8784-97efb310b352.png)

**4.** Check Run Collection Results 

![image](https://user-images.githubusercontent.com/45478777/175766827-fecb8dc6-c03d-4e36-b086-f96e6a6d685a.png)

**5.** Create a new folder in Desktop as Newman-Postman-Test

**6.** After creating the folder, open the blank folder with VS code. Therefore, VS Code needs to be installed in the machine. 

Next, open the terminal and hit a command to install package.json:

**npm init -y**

**7.** Install newman by run this command in the terminal:

**npm i newman**

**8.** Next, you will see that newman has been installed and showing the package name at package.json file under dependencies tag

![image](https://user-images.githubusercontent.com/45478777/175767017-6844f30e-d577-4412-a2d0-c698d0409627.png)

**9.** Now create a folder named collection and export "**dmoneyCollection.json**" and saved it to the **“collection”** folder.

![image](https://user-images.githubusercontent.com/45478777/175767063-7105980f-3db6-4933-8820-7fc107a9fe7a.png)

**N.B:** when saving the collection and environment files, there should not contain any space within the file name. You can fillup the space (if any) with underscore_

**10.** Now run this command:

**npx newman run .\collection\dmoneyCollection.json**

![image](https://user-images.githubusercontent.com/45478777/175767428-48b5b404-d80a-4476-9991-b002aecab590.png)

**HTML report generate using Newman**

**1.** Install following package by this command:

**npm i newman-reporter-htmlextra**

**2.** Now create another file as **report.js** and copy paste following code under **report.js file**:

const newman = require('newman');

newman.run({
    collection: require('./collection/customer_api_collection.json'), // pointing to local JSON file.
    environment: require('./collection/customer_api_env.json'), // pointing to local env file
    iterationCount: 1,
    reporters: 'htmlextra',
    reporter: {
        htmlextra: {
            export: './Reports/report.html', // If not specified, the file will be written to `newman/` in the current working directory.
        }
    }
    
}, function (err) {
    if (err) { throw err; }
    console.log('collection run complete!');
});

![image](https://user-images.githubusercontent.com/45478777/175768279-95bc62d3-7ca0-4acb-8e57-ff8ae951eef2.png)


**3.** Next, create another folder named Reports. If you do not create this folder, the report will be generate to a new folder named ‘newman’ in current working directory.

**4.** Then go to the package file and update “test” value under scripts as:

**“node report.js”**

![image](https://user-images.githubusercontent.com/45478777/175767547-24b0303d-30f2-4ca1-b919-4807350ce2fb.png)

**5.** Now hit this command:

**npm test**

**6.** You will see a html report named report.html will be generate in Reports folder

![image](https://user-images.githubusercontent.com/45478777/175767563-e7450fa5-9490-4ca5-9937-ae241cda0cd0.png)

**7.** Now reveal the folder and open the html file and you will see the result in a html report

![image](https://user-images.githubusercontent.com/45478777/175767619-0a5367e4-6d71-4f22-ad33-cbf427cb2d4d.png)
