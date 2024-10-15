YouTube and Website Summarization App
=====================================

This Streamlit application allows users to generate text summaries from YouTube videos and websites using the LangChain framework and Groq's LLMs (Gemma-7b-It). The app provides a seamless, user-friendly interface that simplifies summarization tasks, making it ideal for researchers, content creators, and those who want a quick gist of video or web content.

🌟 Features
-----------

-   **Summarize YouTube Videos**: Automatically extracts transcript and summarizes key points from any YouTube video. Perfect for getting quick insights into long videos.
-   **Summarize Websites**: Fetches and summarizes text from web pages. Useful for summarizing articles, blogs, and news sites.
-   **AI-Powered Summarization**: Utilizes LangChain and Groq's advanced language models to generate concise and accurate summaries.
-   **User-Friendly Interface**: Built using Streamlit for an intuitive and interactive user experience.
-   **Error Handling**: Displays meaningful error messages if the summarization fails due to incorrect URLs or unsupported content types.

🖥️ Live Demo
-------------

Check out the **[Live Demo](#)** of the app. (Link placeholder)

🚀 How It Works
---------------

### 1\. **Summarizing YouTube Videos**

-   Enter the YouTube video URL, and the app extracts the video transcript using a dedicated API.
-   The extracted content is summarized using Groq's LLM (Gemma-7b-It), producing a brief, readable overview of the video's content.

### 2\. **Summarizing Websites**

-   Paste the URL of any article, blog, or web page.
-   The app fetches the textual content and generates a summary based on the page's core text.

🛠️ Requirements
----------------

Before running the app, ensure you have the following installed:

-   **Python 3.7+**
-   `validators` (for validating URL inputs)
-   `streamlit` (for building the web interface)
-   `langchain`, `langchain_groq`, `langchain_community` (for AI summarization capabilities)

📦 Installation
---------------

1.  **Clone the Repository**:

    bash

    Copy code

    `git clone https://github.com/sharad-mishra/yt-video-summarization.git
    cd yt-video-summarization`

2.  **Install Dependencies**:

    bash

    Copy code

    `pip install -r requirements.txt`

⚙️ Usage
--------

### Setting up the Groq API Key

To get started, you need a Groq API key:

1.  Open the `app.py` file.

2.  Set your Groq API key in the variable:

    python

    Copy code

    `groq_api_key = "your_groq_api_key_here"`

### Running the Streamlit App

Once the API key is set, you can start the app by running:

bash

Copy code

`streamlit run app.py`

This will launch the Streamlit app locally on your machine, and you'll be provided with a local URL (typically <http://localhost:8501>) to access the app.

### Summarizing Content

1.  **Enter a URL**: Input the URL of the YouTube video or website you wish to summarize.
2.  **Click the Summarize Button**: Once you enter the URL, click the "Summarize the Content from YT or Website" button.
3.  **View the Summary**: The app will fetch the content, process it, and display a neatly formatted summary.

### Example

To summarize a YouTube video, enter the video URL like this:

arduino

Copy code

`https://youtube.com/watch?v=zQnBQ4tB3ZA`

Once you click the button, a summary will be displayed based on the video transcript.

💡 Code Overview
----------------

Here's a key part of the code showing how content is loaded from websites:

python

Copy code

`loader = UnstructuredURLLoader(
    urls=[generic_url],
    ssl_verify=False,
    headers={"User-Agent": "Mozilla/5.0 (Macintosh; Intel Mac OS X 13_5_1) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/116.0.0.0 Safari/537.36"}
)
docs = loader.load()

# Chain For Summarization
chain = load_summarize_chain(llm, chain_type="stuff", prompt=prompt)
output_summary = chain.run(docs)

st.success(output_summary)`

### Error Handling

The app includes error handling to manage issues like invalid URLs or content retrieval errors. For example, if a video lacks a transcript, the user will be notified with an appropriate message.

🤝 Contributing
---------------

We welcome contributions to this project! Here's how you can get involved:

1.  **Fork the repository**.
2.  **Create a new branch** (`git checkout -b feature-branch`).
3.  **Make your changes**.
4.  **Commit your changes** (`git commit -m 'Add some feature'`).
5.  **Push to the branch** (`git push origin feature-branch`).
6.  **Open a pull request**.

Make sure your code adheres to the existing style and includes appropriate tests where needed.

📜 License
----------

This project is licensed under the MIT License. See the <LICENSE> file for details.

* * * * *

### 🔍 About the Project

This project aims to leverage the power of **Generative AI** to simplify content summarization for users. Whether you're browsing the web or watching long YouTube videos, this tool extracts the essential points so you can save time.

It showcases the capabilities of LangChain and Groq's LLM, demonstrating how complex tasks like video and article summarization can be handled through a straightforward, efficient interface. This app could be expanded into a more comprehensive tool, offering features like keyword extraction, sentiment analysis, or even multi-document summarization in the future.
