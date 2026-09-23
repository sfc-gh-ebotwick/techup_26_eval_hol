# ❄️ Snowflake TechUp 2026 ❄️
# Eval Based Agentic Optimization HOL  
Hands on Lab materials for eval driven agent optimization session for Techup 2026

🙋‍♀️ If at any point in the lab you need help please post a message in https://snowflake.enterprise.slack.com/archives/C0BQDQZUZMX and tag any of @elliott.botwick, @sharon.li, @haley.massa, @andrew.samant, and justin.marciszewski 🙋‍♀️


# Instructions

## 1. Account Access
Please plan to use your SE demo Snowflake account for this lab! If you have any issues with environment access please ping in the above linked slack channel.  

## 2. Setup 

Run the [EVAL_HOL_SETUP.sql](EVAL_HOL_SETUP.sql) file to provision a new database with data, a semantic view, a cortex search service and a custom tool before wrapping these services into a baseline agent and running your first evaluation.

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

Time to improve your agent using Cortex Code (CoCo)! You have two options depending on your environment. Both options use the same prompts from [coco_prompts.txt](./coco_prompts.txt) to analyze the evaluation results and drive improvements.

---

### Which option should I choose?

| | Option 1: CoCo Snowsight | Option 2: CoCo CLI |
|---|---|---|
| **Where it runs** | In your browser via Snowsight | Locally on your machine (or in GitHub Codespaces) |
| **Setup friction** | Low — already available in Snowsight | Moderate — requires CLI install and connection config |
| **Control** | Uses a Snowflake workspace for file context; same CoCo capabilities via the Snowsight chat panel | Full local filesystem, can read/write agent YAML files directly, supports all `cortex agent-studio` subcommands |
| **Best for** | Attendees whose org restricts local tooling or who want the quickest path | Attendees whose org has approved the CoCo CLI / Codespaces |

Both options produce the same result: improved agent instructions saved as a new committed version, and a re-evaluation run to measure the improvement.

> [!WARNING]
> **Choose one option and stick with it.** Do not switch between CLI and Snowsight mid-lab.

---

### Option 1 (recommended): CoCo Snowsight (browser-based)

No local install required. Follow the full setup guide: [coco_snowsight_setup.md](./coco_snowsight_setup.md)

### Option 2: CoCo CLI (via GitHub Codespaces or local)

Follow the full setup guide: [coco_cli_setup.md](./coco_cli_setup.md)

---

## 5. Challenge!

You should have seen a decent improvement in your evaluation metrics going from your baseline to your optimized agent. Now lets take things a bit further and see how far you can take your agent! This is your turn to use your AI and Snowflake knowledge to apply new methods to the agent to see how high we can push our agent quality.

A few ideas of things to try
- An updated Semantic Model
- A new orchestration model
- Enriched tool descriptions

The world is your oyster - get creative and see if you can impress the judges - LLM and Human!

To submit, post a short summary of what you did to improve your agent and how high you were able to get your scores. 

Post your summaries in appropriate threads (use the threads!!!) on https://snowflake.enterprise.slack.com/archives/C0BQDQZUZMX

# TODO
1. Update the DataOps link to Major TechUp event link
2. Update slack channel link
3. Ask for more support members

