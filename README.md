# techup_26_eval_hol
Hands on Lab materials for eval driven agent optimization coco for Techup 2026



# Instructions

## 1. Setup 

Run the [EVAL_HOL_SETUP.sql](https://github.com/sfc-gh-ebotwick/techup_26_eval_hol/edit/main/EVAL_HOL_SETUP.sql) file to provision a new database with data, a semantic view, a cortex search service and a custom tool before wrapping these services into a baseline agent and running your first evaluation.

## 2. Eval Investigation

In snowsight, navigate to your newly created Agent and click on the Evaluations tab. Check out your global metric scores and get a sense of where your baseline agent is. Look into individual records to understand how the agent performed across a variety of metrics for given queries. 

## 3. Agent Optimization

Now - on your local machine or in Github Codespaces - start a new CoCo CLI session. Run the two prompts in [coco_prompts.txt](https://github.com/sfc-gh-ebotwick/techup_26_eval_hol/edit/main/coco_prompts.txt). The first prompt will help analyze the evaluation executed in step 1 and improve your agent based on observed failure patterns. The second prompt will kick off a new evaluation run to measure how well your agent improved from your baseline to your optimized version. 

## 4. Challenge!

You should have seen a decent improvement in your evaluation metrics going from your baseline to your optimized agent. Now lets take things a bit further and see how far you can take your agent!
