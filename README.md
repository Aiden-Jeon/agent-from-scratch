# agent-from-scratch

## How to start

### Google Colaboratory

| Order | Name             | URL                                                                                                                                                                                                |
| ----- | ---------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1     | Stop             | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Aiden-Jeon/agent-from-scratch/blob/main/notebooks/01_Stop.ipynb)             |
| 2     | StructuredOutput | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Aiden-Jeon/agent-from-scratch/blob/main/notebooks/02_StructuredOutput.ipynb) |
| 3     | BindTools        | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Aiden-Jeon/agent-from-scratch/blob/main/notebooks/03_BindTools.ipynb)        |
| 4     | Agents           | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Aiden-Jeon/agent-from-scratch/blob/main/notebooks/04_Agents.ipynb)           |

### Local Setup

1. Copy the environment template file to your own.
    ```bash
    cp env.template notebooks/.env
    ```
2. Give your api key to the env file
    ```bash
    OPENAI_API_KEY=<YOUR-OPENAI-API-KEY>
    HF_TOKEN=<YOUR-HUGGINGFACE-API-KEY>
    ```
3. Install packages
    ```bash
    pip install -r requirements.txt
    ```

## Customization

For the huggingface model, I have test with [huggingface/meta-llama/Llama-3.3-70B-Instruct](https://huggingface.co/meta-llama/Llama-3.3-70B-Instruct), but this model require to pay.
So i have changed it to smaller model [huggingface/microsoft/Phi-3.5-mini-instruct](https://huggingface.co/microsoft/Phi-3.5-mini-instruct) which is free to use.

If you want to test other models you can easily use like this:

```python
hug_llm = ChatLiteLLM(
    model="huggingface/<REPO-NAME>/<MODEL-NAME>",
    temperature=0.2,
)
messages = [HumanMessage(content="what model are you")]
hug_llm.invoke(messages).pretty_print()
```
