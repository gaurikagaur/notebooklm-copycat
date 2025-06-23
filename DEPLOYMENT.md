# Deploying to Streamlit Cloud

This guide will walk you through the steps to deploy your Streamlit application to Streamlit Cloud.

## Prerequisites

1.  **A Streamlit app:** You should have a working Streamlit application.
2.  **A GitHub account:** Streamlit Cloud deploys apps directly from GitHub repositories.
3.  **Your app code on GitHub:** Your Streamlit app's code, including all necessary files (`main.py`, `requirements.txt`, etc.), must be pushed to a GitHub repository.

## Steps to Deploy

### 1. Create a `requirements.txt` file
If you haven't already, create a `requirements.txt` file in the root of your repository. This file lists all the Python packages your app needs to run. You can generate this file using:
```bash
pip freeze > requirements.txt
```
Ensure this file is committed and pushed to your GitHub repository. For this specific application, your `requirements.txt` should include at least:
```
streamlit
google-generativeai
gTTS
python-dotenv
python-magic
pypdf2
python-docx
```
**Note on `python-magic`:** The `python-magic` library is a wrapper around the `libmagic` file type identification library. You might need to install `libmagic` on your system if it's not already present.
  - For Debian/Ubuntu: `sudo apt-get install libmagic1`
  - For macOS (using Homebrew): `brew install libmagic`
  - For other systems, please refer to your system's package manager or the `python-magic` documentation.
  Streamlit Cloud typically handles common dependencies, but it's good to be aware of this.

### 2. Sign up or Log in to Streamlit Cloud
- Go to [share.streamlit.io](https://share.streamlit.io/).
- You can sign up using your Google account, GitHub account, or email. If you already have an account, log in.

### 3. Connect Your GitHub Account
- If this is your first time, Streamlit Cloud will prompt you to connect your GitHub account.
- Authorize Streamlit to access your repositories. You can choose to give access to all repositories or only select ones.

### 4. Deploy Your App
- Once logged in and your GitHub account is connected, click the "**New app**" button (usually found on the top right of your workspace).
- **Repository:** Select the GitHub repository where your Streamlit app code is located.
- **Branch:** Choose the branch you want to deploy (e.g., `main`, `master`).
- **Main file path:** Specify the path to your main Streamlit script (e.g., `main.py` if it's in the root, or `src/app.py` if it's in a subdirectory). For this project, it should be `main.py`.
- **App URL (Optional):** You can customize the URL for your app.

### 5. Advanced Settings (Optional but Recommended)
- Click on "**Advanced settings...**".
- **Python version:** Select the Python version that your application is compatible with. It's good practice to specify this.
- **Secrets (if any):** If your app uses environment variables (like API keys), you need to add them here. For this project, you will need to add your `GEMINI_API_KEY`.
    - In the "Secrets" section, add your `GEMINI_API_KEY` like this:
      ```
      GEMINI_API_KEY = "YOUR_ACTUAL_API_KEY_HERE"
      ```
      Replace `"YOUR_ACTUAL_API_KEY_HERE"` with your actual Gemini API key.

### 6. Deploy
- Click the "**Deploy!**" button.
- Streamlit Cloud will start building and deploying your app. You can see the logs in real-time.
- This process might take a few minutes. Your app will install dependencies from `requirements.txt` and then run your script.

### 7. Access Your App
- Once deployment is complete, you'll be redirected to your live app.
- You can share the URL with others.

## Updating Your App
- To update your app, simply push your changes (new code, updated `requirements.txt`, etc.) to the connected GitHub repository and branch.
- Streamlit Cloud will automatically detect the changes and redeploy your app. You might need to manually reboot the app from the Streamlit Cloud dashboard in some cases if it doesn't update automatically.

## Troubleshooting
- **Check Logs:** The Streamlit Cloud dashboard provides logs for your app. If deployment fails or your app crashes, these logs are the first place to look for errors.
- **`requirements.txt`:** Ensure all necessary dependencies are listed and correctly versioned (if needed).
- **File Paths:** Double-check that the "Main file path" in your app settings is correct.
- **Secrets:** Verify that all required secrets (API keys, etc.) are correctly entered in the advanced settings.

That's it! Your Document to Podcast Converter should now be live on Streamlit Cloud.Tool output for `create_file_with_block`:
