## Linear-Regression-Till-Deployment

### Cloud Deployment (Google Cloud Platform)

Once the training is completed, we need to expose the trained model as an API for the user to consume it. For prediction, the saved model is loaded first and then the predictions are made using it. If the web app works fine, the same app is deployed to the cloud platform. The application flow for cloud deployment looks like:

<img src="testing_pipeline.PNG" width= "300">

### Pre-requisites:
* Basic knowledge of flask framework.
* Any Python IDE installed(we are using PyCharm).
* A Google Cloud Platform account.
* Basic understanding of HTML.


###### Flask App

As we’ll expose the created model as a web API to be consumed by the client/client APIs, we’d do it using the flask framework. 
The flow of our flask app will be:
<img src="flask_flow.PNG" width= "300">

Create the project structure, as shown below:
<img src="folder_structure.PNG" width= "300">


## Deployment to G-cloud:

* Go to https://cloud.google.com/ and create an account if already haven’t created one. Then go to the console of your account.
* Go to IAM and admin(highlighted) and click manage resources
<img src="iam.PNG" width= "300">

* Click CREATE PROJECT to create a new project for deployment.
* Once the project gets created, select App Engine and select Dashboard.
<img src="dashboard.PNG" width= "300">

* Go to https://dl.google.com/dl/cloudsdk/channels/rapid/GoogleCloudSDKInstaller.exe to download the google cloud SDK to your machine.
* Click Start Tutorial on the screen and select Python app and click start.
<img src="tutorial.PNG" width= "300">

* Check whether the correct project name is displayed and then click next.
<img src="setup.PNG" width= "300">

* Create a file ‘app.yaml’ and put  ‘runtime: python37’ in that file.
* Create a ‘requirements.txt’ file by opening the command prompt/anaconda prompt, navigate to the project folder and enter the command ‘pip freeze > requirements.txt’.
It is recommended to use separate environments for different projects.
* Your python application file should be called ‘main.py’. It is a GCP specific requirement.
* Open command prompt window, navigate to the project folder and enter the command gcloud init to initialise the gcloud context.
* It asks you to select from the list of available projects.
<img src="select_project.PNG" width= "300">

* Once the project name is selected, enter the command gcloud app deploy app.yaml 
--project <project name>
    
* After executing the above command, GCP will ask you to enter the region for your application. Choose the appropriate one.
<img src="region_select.PNG" width= "300">

* GCP will ask for the services to be deployed. Enter ‘y’ to deploy the services.
* And then it will give you the link for your app,and the deployed app looks like:

<img src="final_snap.PNG" width= "300">


