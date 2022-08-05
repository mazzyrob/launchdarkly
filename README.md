Welcome to the easiest way to see how LaunchDarkly can transform your business by implementing a simple yet powerful feature flagging SDK in this Python-based example

This example is a simple pricing application, where different users will get different pricing, depending on the rules you set for your users.

Prerequisites:

To use this example, you will need the following:

I. An LaunchDarkly Account:

If you don't have a LaunchDarkly account, create one here https://launchdarkly.com/ !

You must set up a LaunchDarkly project and environment where your flags will live. Create a new project or use an existing one in your account.

To create a new project:

a. Navigate to the Account settings page.

b. Click the Projects tab in the top navigation.

c. Click the Create project button in blue. The "Create a project" panel appears.

d. Give your project a name, so you can find it easily later.

e. Click Create project. The new project's Environments tab appears.

f. Click the "Production" environment SDK key to copy it to your clipboard: VERY IMPORTANT - you will need this number later!

II. A GitHub account  - you probably have one if you are reading this right now, but if you don't, sign up at github.com and follow the instructions

III. Ability to run a Python application locally or using this example on Glitch - https://glitch.com/edit/#!/rp-starlight-travel2



++++++++++++++

Getting Started:

1. Clone the repository locally - https://github.com/mazzyrob/launchdarkly.git
OPTIONAL: This repository was tested in Glitch, you can also Remix it here https://glitch.com/edit/#!/rp-starlight-travel2 NOTE: you will need a Glitch Account

2. First, create a new project in Python - skip this step if you are using Glitch


3. Then, go into your new directory and create a .env file with this entry and your SDK Key:

LD_SDK_KEY=ENTER-YOUR-KEY-HERE

Alternatively, if you are using Glitch, navigate to .env and create/insert your key
  
Run your project in Python and navigate/preview it.
  

++++++++++++++

Creating your first feature flag
  
In LaunchDarkly, navigate to the Feature flags list (make sure you are in your Production project).

1. Click "Create flag" in blue

2. Enter "Pricing tier 3" in the Name field, set the flag variation to "Boolean"
  
3. Click Save flag.

4. Turn on the flag - the code is already inserted in this example.  You can see the code in the views/tier_3.html and the handling in the server.py file
  
5. You should see a new pricing option.  
  
6. Try logging in a few times, and then you can create additional targeting options by going back into LaunchDarkly and targeting specific email hash values or percentages

  
Congratulations, you have set up an application, where you can play with LaunchDarkly's feature targeting rules!

++++++++++++++

Advanced/Extra Credit - Percentage Roll-out

1. In LaunchDarkly, navigate to the Feature flags list (make sure you are in your Production project).

2. In the "Feature flags" list, click Pricing Tier 3. The flag's Targeting tab appears.

Find the "Default rule", which is the flag variation or rollout that appears when targeting is enabled. 

Click the Serve menu.

Choose "a percentage rollout":

Set the true variation to 40%.
Confirm that the flag's targeting toggle is set to On.
Click Review and save.

Log in to the app as a few different users. Keep track of which email addresses you use as you log in and log out.
When the third pricing tier appears, you know the user you logged in as is part of the 40% of users targeted by the "Pricing Tier 3" flag.
Log out and log back in again as that same user. The third pricing tier appears every time that user logs in, because LaunchDarkly can identify individual users. 
That user will always receive the third tier until the flag's targeting changes.
When you find a user who doesn't receive the third tier, save their email address.

Now you've experienced flag targeting in action!


++++++++++++++

Advanced/Extra Credit  - Targeting individual Users

You can override the percentage rollout for any particular user, forcing them to receive or not receive a flag regardless of other targeting rules. 

You can do this by targeting them with rules individually.

To target an individual user through the Users list:

1. Log into the pricing app with the email address of the user who did not receive the "Pricing Tier 3" flag.
2. Click on the avatar icon in the top-right of the page. The 10-character hashed user key is displayed. Copy this key and save it.
3. Navigate to the LaunchDarkly Users list. Find the user key you saved in the list of users and click their name. The user's menu appears.
4. Change the Variation setting for the "Pricing Tier 3" flag from false to true (blue diamond).
5. Click "Review and Save"
6. Log back into the app as that user and refresh the page. The third pricing tier should now be visible.
