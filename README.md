# doc-pipeline-java
This is a simple java application that is deployed onto AWS Elasticbeanstalk, using AWS Code pipeline.

### Team Members
* Devon 
* Matt
* Doug

[Deployed Site](http://deploymentappjava.us-east-2.elasticbeanstalk.com/)


### How to deploy using AWS Code Pipeline

#### Basic Setup:

  * Ensure your java application is running locally.
  * Within AWS Console, navigate to [code pipeline](https://us-east-2.console.aws.amazon.com/codesuite/codepipeline/start?region=us-east-2)
  * Create a new pipeline
    * ![create](./assets/create.png)
  * Configure pipeline with proper settings
    * ![settings](./assets/settings.png)
  * Configure deployment stage
    * ![deploy](assets/deploy.png)
  *  Review configuration and submit
     * ![review](assets/review.png)  

#### Adding additional Stages:
  * Navigate to your pipeline
  * Click the edit button to bring up the edit stage view
     * ![edit](assets/edit.png) 
  * Click the add Stage button and select a name for it
     * ![add-stage](assets/addstage.png)
  * Click the add action group button within the new stage, and fill out form and choose AWS Codebuild as action provider
      * ![add-action](assets/addaction.png) 
  * In the project field choose Create Project
      * ![create-project](assets/createproject.png) 
  * Fill out the form, most can be left to the default. In the buildspec field, if your application needs to run any specific commands, this is where you'd add them
      * ![build-spec](assets/buildspec.png)  
      * Click continue to Code pipeline
      * ![new-stage](assets/newstage.png)
  *  Your pipeline should now be configured correctly 

  
  

#### Roadblocks
  * Transitioning artifacts thru the different stages
  * Not having a proper "Procfile" or "application.jar" file within the deployed stage
  * Codepipeline not being able to find the s3 bucket where the artifacts are
 
* ![err-deploy](assets/error-deploy.png)
* ![err-bucket](assets/err-no-bucket.png)  


