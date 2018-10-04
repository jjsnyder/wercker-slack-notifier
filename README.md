# wercker-slack-notifier

Introduction
This project shows an example of how to use "after-steps" to send a notification to a Slack channel after a Wercker pipeline is executed.

Slack Notification
- Must create a slack application and add an incoming web hook on that application.
See https://api.slack.com/incoming-webhooks
  - The application will specify the channel to which the notifications will be sent.
  - Copy the Webhook URL
- The Wercker slack notifier requires that curl be installed on the box defined in the wercker.yml file.
  
Steps
- Steps are self-contained bash scripts or compiled binaries for accomplishing 
specific tasks defined in the wercker.yml file of your application. 

- Steps can be written manually or borrowed from the community via the Steps Registry.

Example wercker.yml :
build:
  steps:
    - script:
        name: step 1
        code: ls

For more information on steps see http://devcenter-staging.wercker.com/learn/steps/introduction.html

After Step
- "after-steps" are used to perform a function after a pipeline has run.  This is ideally suited for notifications.
Example wercker.yml of sending a notification to Slack :
  after-steps:
    - slack-notifier:
      url:  $SLACK_URL
      
  Note that the channel to which the message is sent is specified when the web hook is created.
  The url is the Slack application's Webhook URL copied above.

See wercker.yml for putting it all together.


resources:
Learn more about steps and after-step: 
- http://devcenter-staging.wercker.com/learn/steps/introduction.html
- http://devcenter-staging.wercker.com/learn/steps/after-steps.html
