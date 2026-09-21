

main. py

import requests
from urllib.parse import quote

def translate_text(text, source, target):
    url = (
        "https://api.mymemory.translated.net/get?q="
        + quote(text)
        + "&langpair="
        + source
        + "|"
        + target
    )

    response = requests.get(url)

    if response.status_code == 200:
        data = response.json()
        return data["responseData"]["translatedText"]
    else:
        return "Translation failed."


print("================================")
print("   LANGUAGE TRANSLATION TOOL")
print("================================")

text = input("Enter text: ")
source = input("Source language (en/hi/fr): ")
target = input("Target language (en/hi/fr): ")

result = translate_text(text, source, target)

print("\nTranslated Text:")
print(result)

# Language Translation Tool

A simple Python-based Language Translation Tool developed as part of the CodeAlpha Internship.

## Features

- Accepts text from the user
- Supports source and target language selection
- Uses an online translation API
- Displays the translated text

## Technologies Used

- Python
- Requests
- MyMemory Translation API

## How to Run

Install the required library:

pip install -r requirements.txt

Then run:

python main.py

## Example

Input:
Hello, how are you?

Source Language:
en

Target Language:
hi

Output:
नमस्ते, आप कैसे हैं?
