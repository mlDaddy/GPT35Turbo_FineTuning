## ChatGPT Fine Tuning using OpenAI's API
This is a simple bare minimum script needed for fine-tuning GPT35Turbo (ChatGPT) on your custom data. You can see all the instructions and example cases in the [FineTuning_GPT35Turbo.ipynb](FineTuning_GPT35Turbo.ipynb) file.

#### Setting up the Environment
```
conda create -n openai python=3.10
conda activate openai
pip install -r requirements.txt
```

#### Setting up the api key
1. Create a file named my_openai_api_key.txt in the working directory
2. Paste your api key provided by OpenAI in this file and save
3. You can delete this file once you are done

#### Setting up the Data Files
- Create Data Folder
```
!mkdir data
```
- Place Your JSONL data file in data folder
- Next, we specify the data path and open the JSONL file
```
data_path = "data/data.jsonl"
```
#### Performing the Fine-Tuning
- import utility functions from OpenAI
```
from utils import verify_data, upload_fintuning_data, start_finetuning_job
```
- Verify the data file
```
verify_data(data_path)
```
- Upload data to OpenAI's Server
```
file_id = upload_fintuning_data(data_path)
```
- Start the finetuning job on OpenAI's Server
```
job = start_finetuning_job(file_id=file_id, model="gpt-3.5-turbo")
```
#### Testing your fine-tuned ChatGPT
- You will receive an email from OpenAI after the process gets completed.
- You can start using the new fine-tuned model inside OpenAI Playground