# aichatbot
Create your own AI Chat bot with this python code.
import openai

# Set the OpenAI API key
openai.api_key = "YOUR_API_KEY"

def chatbot():
  # Start the conversation
  print("Chatbot: Hello! How can I help you today?")
  
  # Get user input
  user_input = input("User: ")
  
  # Set a flag to indicate if the conversation is over
  finished = False
  
  # Start a loop to have the chatbot respond to the user
  while not finished:
    # Use the OpenAI API to generate a response
    response = openai.Completion.create(
      engine="text-davinci-002",
      prompt=user_input,
      max_tokens=1024,
      n=1,
      stop=None,
      temperature=0.5
    )
    
    # Print the chatbot's response
    print(f"Chatbot: {response.choices[0].text}")
    
    # Get the next user input
    user_input = input("User: ")

# Run the chatbot
chatbot()
