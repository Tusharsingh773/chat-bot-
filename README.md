pip install google-generativeai
from google.colab import userdata
userdata.get('GOOGLE_API_KEY_1')
import google.generativeai as genai

genai.configure(api_key="AIzaSyAFAQJg7_xZV6sN-DDIIqE7B-x7BfKb0Bw")

# Use flash model instead of pro
model = genai.GenerativeModel('models/gemini-1.5-flash')

chat = model.start_chat(history=[])

print("Welcome to the Gemini Chatbot! Type 'exit' to end the conversation.")

while True:
    user_input = input("You: ")
    if user_input.lower() == 'exit':
        break
    try:
        response = chat.send_message(user_input)
        print(f"Gemini: {response.text}")
