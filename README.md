# ChatGPT Selenium API

A lightweight Python wrapper that automates ChatGPT through Selenium, allowing you to send prompts and receive responses programmatically without using the official API.

This project launches a Chrome browser with your own ChatGPT session, submits prompts, waits for the response to finish generating, and returns the complete reply as plain text.

> **Disclaimer:** This project is an unofficial automation tool and is not affiliated with or endorsed by OpenAI.

---

## Features

* 🤖 Send prompts programmatically
* 💬 Interactive console chat mode
* ⚡ Simple `make_request()` API
* 🔐 Uses your existing ChatGPT account
* 🌐 Dedicated Chrome profile for persistent login
* 🚀 Automatically installs the correct ChromeDriver
* 🛡️ Uses Undetected ChromeDriver for improved browser compatibility

---

## How It Works

1. Launches Chrome using a dedicated profile.
2. Opens ChatGPT.
3. Sends your prompt.
4. Waits until the response finishes generating.
5. Copies the latest response.
6. Returns it as a Python string.

---

## Installation

```bash
git clone https://github.com/yourusername/chatgpt-selenium-api.git

cd chatgpt-selenium-api

pip install -r requirements.txt
```

---

## Setup

Generate the configuration file:

```bash
python models/utils.py
```

This creates a dedicated Chrome profile that keeps your ChatGPT login separate from your personal browser.

Then sign in to ChatGPT the first time.

---

## Usage

### Interactive Chat

```python
from models.backend import ChatGPTAPI

api = ChatGPTAPI()
api.chat()
```

Example:

```
Prompt:
> Explain recursion.

Response:
Recursion is...
```

---

### Single Request

```python
from models.backend import ChatGPTAPI

api = ChatGPTAPI()

response = api.make_request(
    "Translate 'Automation makes life easier.' into Urdu."
)

print(response)
```

---

## Project Structure

```
.
├── app.py
├── config.yaml
├── models/
│   ├── backend.py
│   ├── browser.py
│   └── utils.py
```

---

## Requirements

* Python 3.10+
* Google Chrome
* ChatGPT account

Python packages:

* selenium
* undetected-chromedriver
* webdriver-manager
* pyperclip
* pyyaml
* requests

---

## Limitations

* Requires a ChatGPT account.
* Browser automation may break if ChatGPT's website changes.
* Only one browser session is supported at a time.
* Intended for personal automation and experimentation.

---

## Future Improvements

* Conversation history support
* Streaming responses
* File upload support
* Image generation support
* Session management
* Better error handling
* Async API
* Packaging for PyPI

---

## License

This project is released under the MIT License.

---

## Contributing

Contributions, issues, and pull requests are welcome.

If you find a bug or have an idea for an improvement, feel free to open an issue.

---

## Disclaimer

This repository automates the ChatGPT web interface. It does **not** use the official OpenAI API and may stop working if the website changes. Use responsibly and in accordance with OpenAI's Terms of Service.
