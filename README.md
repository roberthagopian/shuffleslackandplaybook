The final steps in this lab were to create a workflow using shuffle, and then integrate a webhook that would carry out the logical diagram. Referenced below is the shuffle workflow, and I'm going to touch on some of the key components that I added to make sure it functioned as planned.
![alt text](https://i.imgur.com/1Lu452n.png)

Steps:
1. created a webhook within splunk and added integration through the shuffle webhook.
2. created an alerts channel in slack and then linked integration with shuffle, creating a parse filter so the slack notification comes off informed and neat in appearance.
3. Added a user action which in this case was an automatic email to alert Security Analyst of the successful unauthorized login and the option to allow it or disable the user. Ref: See the email below
   ![alt text](https://i.imgur.com/YyB9cxE.png)
5. Linked my Active Directory Admin Account as well as user my user library to shuffle, with the prompt to disable a user. Remember these alerts are based off splunk notifications so the user in question is always going to be based off that alert.
6. I added a user attribute check here to ensure that if I choose disabled, it double checks that the user is disabled. I included a condition here if=accountdisabled -->
7. With the step 5. failsafe in place, I created a User has been disabled alert update for slack.

   ![alt text](https://i.imgur.com/7SV7DnF.png)
   ![alt text](https://i.imgur.com/wlTLFI1.png)



Things I learned with this lab:
  When creating and executing a workflow, there is going to be lots of back and forth on the most effecient way to execute. In doing so there is going to be hiccups along the way but following the diagram and rerunning, refreshing, and rerunning again often will get things sorted out. The logs are important to read and understand as well because if something isn't working, the log will lead you to the fix 9/10 times.
  
  Shuffle has a great library of extensions that you can include and the workflow possibilities are probably endless. I will use this for most workflows moving forward.

  Splunk really is the base that opens all the doors. Effecient splunk monitoring can create a treasure trove of data that can be monitored, parsed, and analyzed ad nauseum.
