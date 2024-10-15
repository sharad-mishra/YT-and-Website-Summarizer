# YouTube and Website Summarization App

This Streamlit app provides a convenient way to summarize text content from YouTube videos or websites using the LangChain and Groq APIs.

## Features

- **Summarize YouTube Videos**: Extract and summarize text content from YouTube videos.
- **Summarize Websites**: Extract and summarize text content from any website.
- **User-Friendly Interface**: Simple and intuitive interface built with Streamlit.

## Live Demo

Check out the live demo of the app [here](https://yt-and-website-summarizer.streamlit.app/).

## Requirements

- Python 3.7+
- `validators`
- `streamlit`
- `langchain`
- `langchain_groq`
- `langchain_community`

## Installation

1. **Clone the Repository**:

    ```sh
    git clone https://github.com/sharad-mishra/yt-video-summarization.git
    cd yt-video-summarization
    ```

2. **Install the Required Packages**:

    ```sh
    pip install -r requirements.txt
    ```

## Usage

1. **Set Your Groq API Key**:

    Open the `app.py` file and set your Groq API key:

    ```python
    GROQ_API_KEY = "your_groq_api_key_here"
    ```

2. **Run the Streamlit App**:

    ```sh
    streamlit run app.py
    ```

3. **Open the App in Your Browser**:

    Open your web browser and go to the URL provided by Streamlit (usually `http://localhost:8501`).

4. **Enter the URL to Summarize**:

    - Enter the URL of the YouTube video or website you want to summarize.
    - Click the "Summarize the Content from YT or Website" button.
    - The app will display the summarized content.

## Example

To summarize a YouTube video, enter the URL of the video (e.g., `https://youtube.com/watch?v=zQnBQ4tB3ZA`) and click the "Summarize the Content from YT or Website" button. The app will display the summarized content.

## Error Handling

If an error occurs while accessing the YouTube video or website, an error message will be displayed. Please ensure that the URL is valid and try again.

## Code Excerpt

Here is an excerpt from the `app.py` file showing the core functionality:

```python
else:
    loader = UnstructuredURLLoader(
        urls=[generic_url],
        ssl_verify=False,
        headers={"User-Agent": "Mozilla/5.0 (Macintosh; Intel Mac OS X 13_5_1) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/116.0.0.0 Safari/537.36"}
    )
    docs = loader.load()

# Chain For Summarization
chain = load_summarize_chain(llm, chain_type="stuff", prompt=prompt)
output_summary = chain.run(docs)

st.success(output_summary)
except Exception as e:
    st.exception(f"Exception: {e}")


## Contributing

Contributions are welcome! Please follow these steps to contribute:

1. **Fork the repository**.
2. **Create a new branch** (`git checkout -b feature-branch`).
3. **Make your changes**.
4. **Commit your changes** (`git commit -m 'Add some feature'`).
5. **Push to the branch** (`git push origin feature-branch`).
6. **Open a pull request**.

Please ensure your code adheres to the existing code style and includes appropriate tests.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
```
