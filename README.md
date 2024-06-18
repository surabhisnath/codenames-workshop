# codenames-workshop

## Requirements for provided AI client, LLM

* Install requirements: `pip install -r requirements.txt`
* Setup OpenAI API Key

# Changes Implemented in Fork

* `Word2Vec` embeddings replaced by `sentence-transformer` embeddings
* Subset of words to relate with a hint chosen based on mean similarity of the words in a subset of positive words:
  * If high mean similarity, the subset is selected,
  * as long as none of entries of the subset are very similar to any of the negative words (neutral, opposite team or assassin). Else, the subset is rejected
* A hint for the words in the selected subset is produced by an LLM: in this case GPT4.

# Deploying changes to production server

After you have pushed changes to the repository on Github, you can deploy that code to the production server following these instructions.

## Connect to production server

On Linux:

`ssh -i path/to/production.pem ubuntu@codenames.click`

## Pull code from Github repository

`git pull`

## Restart codenames service

```
sudo systemctl restart codenames
```

*That's it!*
