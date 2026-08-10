## TechUp CoCo Setup

We recommend using Github Codespaces to get a clean cloud-hosted VSCode environment to run CoCo in for this lab. This helps avoid conflicts with existing local coco skills, preferences etc and is easier to setup. 

First go to https://github.com/codespaces - and locate the Blank template, click Use this Template.

<img width="1710" height="887" alt="image" src="https://github.com/user-attachments/assets/2b518bca-3972-492d-a577-ab567a4238ac" />


This will launch your new Codespace. Now - open a terminal and run the following command to install the coco CLI

```curl -LsS https://ai.snowflake.com/static/cc-scripts/install.sh | sh```


Once CoCo CLI is installed, run the following command to create a new config file to store Snowflake Connections in.

```vi ~/.snowflake/connections.toml```

Update the below config to use your account identifier and your account password. Your account identifier can be found by clicking the User menu in the bottom left-hand corner of Snowsight, then selecting 'Connect a tool to Snowflake'. 
Your password is the login password you used to authenticate to your snowflake instance from DataOps Live. 

```
[TECHUP_2026_TEST_VXFSSL]
account = "<YOUR_ACCOUNT_IDENTIFIER>"
user = "USER"
password = "<YOUR_PASSWORD>"
role = "AGENT_EVAL_ROLE"
```
(Note - you can edit in the vim editor by pressing the ```i``` key - but editing in a notepad or somewhere else is sometimes easier)

Once you have pasted your updated config into the editor, click escape then type in ```:wq``` then enter to write the file and quit the editor.

Now launch CoCo CLI by running the command ```cortex``` in your terminal.

Select your settings and test your newly created connection. When prompted, specify YES that you want to use the same SQL connection as Agent connection and that you trust the directory you're working in. 

You should now be all set to run the prompts laid out in coco_prompts.txt
