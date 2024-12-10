
# Basic API for a chatbot using Google Gemini

Created a custom api using Gemini on Google collab




## Deployment

To deploy this project run

```bash
!pip install -U -q "google-generativeai>=0.7.2"
import google.generativeai as genai
```

```bash
frfrom google.colab import userdata
GOOGLE_API_KEY=userdata.get('API')
genai.configure(api_key=GOOGLE_API_KEY)

```
## we have saved the secret key in the Collab Key locker

```bash
model = genai.GenerativeModel('gemini-1.5-flash')
response = model.generate_content("Pakistan")
print(response.text)
```

## Image ingestion

```bash
!curl -o image.jpg "https://storage.googleapis.com/generativeai-downloads/images/jetpack.jpg"
```

## importing library for image 

```bash

import PIL.Image
img = PIL.Image.open('image.jpg')
img
```

```bash
model = genai.GenerativeModel('gemini-1.5-flash')
response = model.generate_content([prompt, img])
print(response.text)
```
