# Set up Replit
Replit will be used to build and host project. 
1. Create Replit account
2. Fork started code: https://replit.com/@postman/AI-Text-Summarizer-App-Starter-Template
    - package.json contains metadata about app and packages
    - Server: 
        - index.js is express server
        - summarize.js will make requests to Hugging Face Inference API
    - Client:
        - public folder contains code for front end
            - index.html for structure
            - stylesheet.css for style
            - script.js for user interactions
# Make Hugging Face account
- https://huggingface.co/
- Hugging face is an AI community that hosts open source AI models, datasets and more. Think of it as github of AI
- Hugging face allows to try models free with Hugging Face Inference API. 
- Will use API to access Facebook's _bart-large-cnn_ model, a Large Language Model (LLM) trained for text summarization
- There are many other models available: https://huggingface.co/models
# Create a new workspace on Postman named "AI Text Summarizer App"
- https://www.postman.com/postman-student-programs/workspace/ai-text-summarizer-with-node-js-and-hugging-face-api/overview 
- Fork above into the newly created workspace
