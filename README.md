# we will install Gemini Sdk Software Develipment kit that will help us to create a applications using these tools
!pip install --upgrade --quiet google-generativeai

# Import the `userdata` module from `google.colab` to access user-specific data.
from google.colab import userdata
# and then get the api key and pass it and set the type str for ambiguity for type errors
GEMINI_API_KEY: str = userdata.get('GOOGLE_API_KEY')
# and we check now our api is connected or not
if GEMINI_API_KEY:
  print('Key Connected Successfully')
else:
  print('Key Connection fail ')

# Import the genai module for API interaction
import google.generativeai as genai

# configure the key

# Select the model
after that we wil select the model
# import generateContent response for give the command and get the output
from google.generativeai.types.generation_types import GenerateContentResponse

# import IPython for display the output
from IPython.display import display
# import Markdown from Ipython to get response on MarkDown
from IPython.display import Markdown

# for image generation we will use the following model
# import the model PIL
from PIL import Image

# and pass our question and image as a parameter to the model
response: GenerateContentResponse = model.generate_content([prompt, img])
display(Markdown(response.text))

# For previous chat save we will following these steps
from google.generativeai import ChatSession
# and then we will create a new chat session save in list
chat: ChatSession = model.start_chat(history=[])
# display the chat 
response = chat.send_message("Hye, I am Hassan")
display(Markdown(response.text))