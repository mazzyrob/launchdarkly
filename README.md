Welcome to the easiest way to see how LaunchDarkly can transform your business by implementing a simple yet powerful feature flagging SDK in this Python-based example

This example is a simple pricing application, where different users will get different pricing, depending on the rules you set for your users.

Prerequisites:

To use this example, you will need the following:

I. An LaunchDarkly Account:

If you don't have a LaunchDarkly account, create one!

You must set up a LaunchDarkly project and environment where your flags will live. Create a new project or use an existing one in your account.

To create a new project:

a. Navigate to the Account settings page.

b. Click the Projects tab in the top navigation.

c. Click the Create project button in blue. The "Create a project" panel appears.

d. Give your project a human-readable Name, so you can find it easily later.

e. Click Create project. The new project's Environments tab appears.

f. Click the "Production" environment SDK key to copy it to your clipboard: VERY IMPORTANT - you will need this number later!

II. A GitHub account  - you probably have one if you are reading this right now, but if you don't, sign up at github.com and follow the instructions

III. Ability to run a Python application locally or using this example on Glitch - https://glitch.com/edit/#!/rp-starlight-travel2



++++++++++++++

Getting Started:

1. Clone the repository locally - https://github.com/mazzyrob/launchdarkly.git
OPTIONAL: This repository was tested in Glitch, you can also Remix it here https://glitch.com/edit/#!/rp-starlight-travel2 NOTE: you will need a Glitch Account

2. First, create a new project in Python - skip this step if you are using Glitch

mkdir <NAME-YOUR-PROJECT>

3. Then, go into your new directory and create a .env file with this entry:

LD_SDK_KEY=<PASTE-YOUR-SDK-KEY-HERE>

Alternatively, if you are using Glitch, navigate to it and create/insert your key
  
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



