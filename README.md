## Linear-Regression-Till-Deployment https://mllearningdeployment.appspot.com/

### Cloud Deployment (Google Cloud Platform)

Once the training is completed, we need to expose the trained model as an API for the user to consume it. For prediction, the saved model is loaded first and then the predictions are made using it. If the web app works fine, the same app is deployed to the cloud platform. The application flow for cloud deployment looks like:

![image](https://user-images.githubusercontent.com/54983568/74457276-ffc5da80-4ec2-11ea-81c5-56ba8d322147.png)


### Pre-requisites:
* Basic knowledge of flask framework.
* Any Python IDE installed(we are using PyCharm).
* A Google Cloud Platform account.
* Basic understanding of HTML.


###### Flask App

As we’ll expose the created model as a web API to be consumed by the client/client APIs, we’d do it using the flask framework. 
The flow of our flask app will be:

![image](https://user-images.githubusercontent.com/54983568/74457370-1e2bd600-4ec3-11ea-81fc-cfd5ddfcf1aa.png)


Create the project structure, as shown below:

![image](https://user-images.githubusercontent.com/54983568/74457421-300d7900-4ec3-11ea-98dc-53c42e9ab424.png)


## Deployment to G-cloud:

* Go to https://cloud.google.com/ and create an account if already haven’t created one. Then go to the console of your account.
* Go to IAM and admin(highlighted) and click manage resources

![image](https://user-images.githubusercontent.com/54983568/74457479-43204900-4ec3-11ea-9ce0-59a14f8dfa85.png)

* Click CREATE PROJECT to create a new project for deployment.
* Once the project gets created, select App Engine and select Dashboard.

![image](https://user-images.githubusercontent.com/54983568/74457549-5c28fa00-4ec3-11ea-997b-5c070a7948ee.png)

* Go to https://dl.google.com/dl/cloudsdk/channels/rapid/GoogleCloudSDKInstaller.exe to download the google cloud SDK to your machine.
* Click Start Tutorial on the screen and select Python app and click start.

![image](https://user-images.githubusercontent.com/54983568/74457585-6ea33380-4ec3-11ea-82a6-f33d1fe3efd9.png)

* Check whether the correct project name is displayed and then click next.

![image](https://user-images.githubusercontent.com/54983568/74457633-8084d680-4ec3-11ea-94b5-db8f7fdc0d6b.png)

* Create a file ‘app.yaml’ and put  ‘runtime: python37’ in that file.
* Create a ‘requirements.txt’ file by opening the command prompt/anaconda prompt, navigate to the project folder and enter the command ‘pip freeze > requirements.txt’.
It is recommended to use separate environments for different projects.
* Your python application file should be called ‘main.py’. It is a GCP specific requirement.
* Open command prompt window, navigate to the project folder and enter the command gcloud init to initialise the gcloud context.
* It asks you to select from the list of available projects.

![image](https://user-images.githubusercontent.com/54983568/74457674-90041f80-4ec3-11ea-9fe7-47ebee817537.png)

* Once the project name is selected, enter the command gcloud app deploy app.yaml 
--project <project name>
    
* After executing the above command, GCP will ask you to enter the region for your application. Choose the appropriate one.

![image](https://user-images.githubusercontent.com/54983568/74457756-ac07c100-4ec3-11ea-8705-2c63d642ab52.png)

* GCP will ask for the services to be deployed. Enter ‘y’ to deploy the services.
* And then it will give you the link for your app,and the deployed app looks like:

![Screenshot 2020-02-14 at 12 28 25 AM](https://user-images.githubusercontent.com/54983568/74457866-ce99da00-4ec3-11ea-93e2-dadf2a31af1c.png)

![Screenshot 2020-01-19 at 11 57 37 PM](https://user-images.githubusercontent.com/54983568/74457887-d6597e80-4ec3-11ea-908f-3d6aa0235ce9.png)


