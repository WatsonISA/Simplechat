
# Implementing a chat bot using Watson Cognitive Services

Welcome! These instructions describe the pre-requisites to be completed before attending the lab session. Please follow these steps to ensure that you are fully prepared to participate on the day of the lab.

# Prepare your Bluemix account


<b>1. Ensure that you have an account on [IBM Bluemix](https://bluemix.net/). If you already have a Bluemix account, then sign in to your account and click on Deploy the Bluemix. </b>


## Deploy the App

NOTE: Perform steps 1-6 OR click the Deploy to Bluemix button to do it all at once!

[![Deploy to Bluemix](https://deployment-tracker.mybluemix.net/stats/49d75098a98a520d8944bbb1d3560dc5/button.svg)](https://bluemix.net/deploy?repository=https://github.com/WatsonISA/Simplechat)

1. Log in to your Bluemix account before deploying.
If already logged in, then ignore this step.
![](readme_images/Login-bluemix.png)

2. We can see that the app is ready to be deplyed, and we need to ensure that the App name, region, Organization, Space is valid before 'Deploy'.
![](readme_images/deploy-click.png)

3. In Toolchain, the app is deployed. There are also option to edit code via eclipseIDE, git changes if required.
Once deployed, the app can be viewed by clicking 'View app'.
![](readme_images/toolchain-pipeline.png)

4. Wait for the deployment to complete, the following actions will be performed:

  * Creates the application.
  * Creates a Conversation and Retrieve & Rank service instance.

5. It is required to configure the Conversation and Tone Analyzer service that is created. We can follow the next steps

6. Configure Watson Conversation

Launch the **Watson Conversation** tool. Use the **import** icon button on the right

<p align="center">
  <img width="400" height="55" src="readme_images/import_conversation_workspace.png">
</p>

Find the local version of [`data/Banking workspace.json`](data/Banking workspace.json) or [`data/Retail workspace.json`](data/Retail workspace.json) and select **Import**. Find the **Workspace ID** by clicking on the context menu of the new
workspace and select **View details**.
##### Save this ID for later.

<p align="center">
  <img width="400" height="250" src="readme_images/workspaceid.PNG">
</p>

*Optionally*, to view the conversation dialog select the workspace and choose the
**Dialog** tab, here's a snippet of the dialog:

![](readme_images/dialog.PNG)

7. Once the watson services are configured, Go to View App -> Runtime -> Environment Variables -> User Defined, add the IDs saved above and save it.

 ![](readme_images/runtime-settings.png)

8. The application and services have been successfully deployed, and you are now ready to use the application.


# Steps

1. [Clone the repo](#1-clone-the-repo)
2. [Create Watson services on IBM Bluemix](#2-create-watson-services-on-ibm-bluemix)
3. [Configure Watson Conversation](#3-configure-watson-conversation)
4. [Run the application](#4-run-the-application)

## 1. Clone the repo

Clone the `Simplechat` locally. In a terminal, run:

`$ git clone https://github.com/WatsonISA/Simplechat`

We can use the files [`data/Banking workspace.json`](data/Banking workspace.json) or [`data/Retail workspace.json`](data/Retail workspace.json) in the folder [`data/`](data/)

## 2. Create Watson services on IBM Bluemix

Create the following services:

* [**Watson Conversation**](https://console.ng.bluemix.net/catalog/services/conversation)
* [**Watson Tone Analyzer**](https://console.ng.bluemix.net/catalog/services/tone-analyzer)


> Note: Ensure that you have logged into Bluemix and are allowed to use these services.

## 3. Configure Watson Conversation

Launch the **Watson Conversation** tool. Use the **import** icon button on the right

<p align="center">
  <img width="400" height="55" src="readme_images/import_conversation_workspace.png">
</p>

Find the local version of [`data/Banking workspace.json`](data/Banking workspace.json) or 
and [`data/Retail workspace.json`](data/Retail workspace.json) 
select **Import**. Find the **Workspace ID** by clicking on the context menu of the new
workspace and select **View details**. Save this ID for later.

<p align="center">
  <img width="400" height="250" src="readme_images/workspaceid.PNG">
</p>

*Optionally*, to view the conversation dialog select the workspace and choose the
**Dialog** tab, here's a snippet of the dialog:

![](readme_images/dialog.PNG)

## 4. Run the application

### If you used the Deploy to Bluemix button...

If you used ``Deploy to Bluemix``, most of the setup is automatic to start using the App.

### If you want to run it locally...

Otherwise as explained above:
1. Clone the repo
2. Instantiate/ Configure the above watson services
2. Install NodeJS runtime or npm.
3. Start the app and it can be used at localhost:3000

> Note: server host can be changed as required in server.js

# Troubleshooting tips

If you are using the IBM Jazz DevOps to deploy the app, you may see the following steps as required to deploy:

1. *Optional:* If you are asked to choose an alias, enter a unique alias name and click create.
![](readme_images/alias.PNG)

2. *Optional:* If you are asked to choose an alias, verify your alias name and click continue.
![](readme_images/cont.PNG)

3. Name your app, and then select the Region, Organization and Space where the app will be deployed. Click 'DEPLOY'.
![](readme_images/deploy1.PNG)

# License

This sample code is licensed under Apache 2.0.
Full license text is available in [LICENSE](LICENSE).

# Links

* [Open Source @ IBM](http://ibm.github.io/): Find more open source projects on the IBM bluemix github

# Privacy Notice

If using the `Deploy to Bluemix` button some metrics are tracked, the following
information is sent to a [Deployment Tracker](https://github.com/IBM-Bluemix/cf-deployment-tracker-service) service
on each deployment:

* Node.js package version
* Node.js repository URL
* Application Name (`application_name`)
* Application GUID (`application_id`)
* Application instance index number (`instance_index`)
* Space ID (`space_id`)
* Application Version (`application_version`)
* Application URIs (`application_uris`)
* Labels of bound services
* Number of instances for each bound service and associated plan information

This data is collected from the `package.json` file in the sample application and the `VCAP_APPLICATION` and `VCAP_SERVICES` environment variables in IBM Bluemix and other Cloud Foundry platforms. This data is used by IBM to track metrics around deployments of sample applications to IBM Bluemix to measure the usefulness of our examples, so that we can continuously improve the content we offer to you. Only deployments of sample applications that include code to ping the Deployment Tracker service will be tracked.

## Disabling Deployment Tracking

To disable tracking, simply remove ``require("cf-deployment-tracker-client").track();`` from the ``app.js`` file in the top level directory.
