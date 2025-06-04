# PromptGPT

*PromptGPT* is a Python library that makes prompting LLMs easy.

Specifically, *PromptGPT* is an instance of [*PromptPy*](https://github.com/Mieschendahl/PromptPy)
with inherent support for *ChatGPT*.

```python
from promptgpt import gpt_4o, Prompter

def translate(message: str) -> str:
    return Prompter(gpt_4o)\
        .add_message("You are a translator", role="developer")\
        .add_message("Return the user message in german and do nothing else", role="developer")\
        .add_message(message)\
        .get_response()

print(f"'Hello' in german is '{translate("Hello")}'")  # prints "Hallo" (generated)
print(f"'Hello' in german is '{translate("Hello")}'")  # prints "Hallo" (cached)
```

All documentation and examples can be found on https://github.com/Mieschendahl/PromptPy.

## Setup

1. Install *PromptGPT*.

    ```bash
    pip install --upgrade git+https://github.com/Mieschendahl/PromptGPT.git
    ```

2. Set your [OpenAI API Key](https://platform.openai.com/api-keys).

    ```bash
    export OPENAI_API_KEY=<your_api_key>
    ```