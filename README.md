# wercker-slack-notifier

This project shows an example of how to use "after-steps" to send a notification to a Slack channel after a Wercker pipeline has executed.

Note that you must have curl installed on the docker image

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

See wercker.yml for an example of how steps are used.

For more information on steps see http://devcenter-staging.wercker.com/learn/steps/introduction.html

After Step
- "after-steps" are used to perform a function after a pipeline has run.  This is ideally suited for notifications.

See wercker.yml for an example of how "after-steps" are used.


Resources

Learn more about steps and after-step: 
- http://devcenter-staging.wercker.com/learn/steps/introduction.html
- http://devcenter-staging.wercker.com/learn/steps/after-steps.html

The "after-steps" git project for slack notifications:
- https://github.com/wercker/step-slack