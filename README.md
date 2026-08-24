# ❄️ Snowflake TechUp 2026 - Eval Based Agentic Optimization HOL ❄️ 
Hands on Lab materials for eval driven agent optimization session for Techup 2026

🙋‍♀️ If at any point in the lab you need help please post a message in https://snowflake.enterprise.slack.com/archives/C0BQDQZUZMX and tag @elliott.botwick, @parker.erickson, or @fady.heiba 🙋‍♀️


# Instructions

## 1. Account Access
Go to [https://go.dataops.live/ams-expansion-techup/register](https://go.dataops.live/ams-expansion-techup/register) and sign in with your Snowflake email to access a temporary snowflake environment for this lab. Click the generated snowflake account link and use provided credentials to login.

## 2. Setup 

Run the [EVAL_HOL_SETUP.sql](https://github.com/sfc-gh-ebotwick/techup_26_eval_hol/edit/main/EVAL_HOL_SETUP.sql) file to provision a new database with data, a semantic view, a cortex search service and a custom tool before wrapping these services into a baseline agent and running your first evaluation.

## 3. Eval Investigation

In Snowsight, navigate to your newly created Agent and click on the Evaluations tab. Check out your global metric scores and get a sense of where your baseline agent is. Look into individual records to understand how the agent performed across a variety of metrics for given queries. 

Start with the link generated at the end of your setup SQL - or navigate to Agents -> Marketing_Agent -> Evaluations


<img width="1710" height="355" alt="image" src="https://github.com/user-attachments/assets/9fc1ab7f-f8ca-4ded-b062-858f6438375e" /> <br><br>
You should see your baseline evaluation run completed here (note your scores may vary!)

<img width="1710" height="879" alt="image" src="https://github.com/user-attachments/assets/01051989-7a79-4bd4-9839-05bd1395a337" />  <br><br>

Clicking into the eval run - we can see individual and aggregate scores for all records in our evalset. You can also click View Details on the top right corner this page to see run status, LLM judge model versions, custom metric prompts etc.

<img width="1710" height="879" alt="image" src="https://github.com/user-attachments/assets/1317c41a-e612-4f01-a439-1b7d0ee726a0" /> <br><br>

Clicking into a single record shows us the trace for that request and the metric scores. We can drill into each metric to see not only the score but the **criteria** the metric used to generate the score and the **reason** that score was given. This qualitative info combined with the quantitative scores gives agent developers, and importantly CoCo, very good feedback to understand the root cause of low eval scores.


## 4. Agent Optimization

Now - follow instructions in [coco_setup_instructions.md](https://github.com/sfc-gh-ebotwick/techup_26_eval_hol/blob/main/coco_setup_instructions.md) to get setup with CoCo in Github Codespaces. 

Once CoCo is installed and configured - start a new CoCo CLI session by running ```cortex```. Click shift+tab to go into Bypass Mode. Run the two prompts in [coco_prompts.txt](https://github.com/sfc-gh-ebotwick/techup_26_eval_hol/edit/main/coco_prompts.txt). The first prompt will help analyze the evaluation executed in step 1 and improve your agent based on observed failure patterns. The second prompt will kick off a new evaluation run to measure how well your agent improved from your baseline to your optimized version. 

## 5. Challenge!

You should have seen a decent improvement in your evaluation metrics going from your baseline to your optimized agent. Now lets take things a bit further and see how far you can take your agent! This is your turn to use your AI and Snowflake knowledge to apply new methods to the agent to see how high we can push our agent quality.

A few ideas of things to try
- An updated Semantic Model
- A new orchestration model
- Enriched tool descriptions

The world is your oyster - get creative and see if you can impress the judges - LLM and Human!

To submit, post a short summary of what you did to improve your agent and how high you were able to get your scores. 

Post your summaries to https://snowflake.enterprise.slack.com/archives/C0BQDQZUZMX
