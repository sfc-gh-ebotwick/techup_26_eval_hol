## TechUp CoCo Setup

As Snowflake SE's you should be comfortable setting up new Snowflake Environments in your CoCo CLI. For this lab the easiest way to use CoCo will be to set up a new connection in CoCo desktop. Click on the Snowflake connection icon in the top left corner. Click add connection. 


Fill out as below. **Ensure you set the role to AGENT_EVAL_ROLE** for this connection to not encounter permissions errors in the lab.

<img width="484" height="860" alt="image" src="https://github.com/user-attachments/assets/4e042aad-a322-4b63-b8bc-46bd76209b32" /> <br>

Your account identifier can be found by clicking the User menu in the bottom left-hand corner of Snowsight, then selecting 'Connect a tool to Snowflake'. 

<img width="664" height="474" alt="image" src="https://github.com/user-attachments/assets/c3b8c83b-390a-44a9-8d23-ec5dbc1e749e" /> <br>

Local OAuth should open a new browser for you to authenticate with the credentials provided on the dataops registration page. Once you've signed in you should be all set. Run ```cortex -c your_connection_name``` to start CoCo with your new instance.

# ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

# ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

### Clean CoCo env setup (as necessary)

If you would like a fresh environment to run your CoCo CLI in - we recommend using Github Codespaces to get a clean cloud-hosted VSCode environment for this lab. This helps avoid conflicts with existing local coco skills, preferences etc and is easier to setup. 

First go to https://github.com/codespaces - and locate the Blank template, click Use this Template.

<img width="1710" height="887" alt="image" src="https://github.com/user-attachments/assets/2b518bca-3972-492d-a577-ab567a4238ac" />


This will launch your new Codespace. Now - open a terminal and run the following command to install the coco CLI

```curl -LsS https://ai.snowflake.com/static/cc-scripts/install.sh | sh```

Once CoCo CLI is installed, run the  ```cortex``` command to enter the setup flow. 

Choose 'Enter Connection Details Manually'


<img width="449" height="280" alt="image" src="https://github.com/user-attachments/assets/632646bf-2a34-42fc-8a82-aaca0f6d5f92" />


Paste in your account identifier. Your account identifier can be found by clicking the User menu in the bottom left-hand corner of Snowsight, then selecting 'Connect a tool to Snowflake'. 


<img width="493" height="387" alt="image" src="https://github.com/user-attachments/assets/6bb638c7-9edf-486e-ba7e-4ca076ecfbd0" />



We will authenticate via Programmatic Access Token (PAT).

<img width="468" height="312" alt="image" src="https://github.com/user-attachments/assets/46d9e04b-7f9d-4ee3-8a56-140fb645cdd5" />


We will first have to generate a PAT. To do so first click on the 'U' icon in the bottom left corner, then select Authentication and click Generate Token.

<img width="1710" height="886" alt="image" src="https://github.com/user-attachments/assets/1596b9b8-09a3-46ac-b340-e410e26a9d6b" />

IMPORTANT - select the newly created AGENT_EVAL_ROLE as the role associated with the PAT. If you have not run throguht the EVAL_HOL_SETUP.sql you will need to do so before proceeding. 

<img width="569" height="513" alt="image" src="https://github.com/user-attachments/assets/dfcc2ab8-f66a-43bf-b54f-50d6183324fb" />

Finally - you will need to create a temporary network rule exception for your token. Click the ellipses next to your newly created token. 

<img width="704" height="278" alt="image" src="https://github.com/user-attachments/assets/4b71758e-aa0c-450b-b93d-d979a7e3983b" />

Back in CoCo - paste in your newly created PAT.


Next fill out the connection details. 


Specify USER for user and AGENT_EVAL_ROLE for role.

<img width="467" height="274" alt="image" src="https://github.com/user-attachments/assets/197f78d6-2228-467c-b8ec-00c37ec18aa9" />

Once completed you should be able to successfully test your newly created agent. Note if your test fails you may have not forgotten to create the required network policy exception.

<img width="542" height="426" alt="image" src="https://github.com/user-attachments/assets/a5951b98-8357-4c66-8364-cb87c49ac846" />


After successfully testing your connection you will be - specify YES that you want to use the same SQL connection as Agent connection and that you trust the directory you're working in. 

You should now be all set to run the prompts laid out in coco_prompts.txt!
