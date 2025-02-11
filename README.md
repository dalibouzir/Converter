Flask App API Setup Guide

This repository provides a simple Flask API that can be used to upload files through Postman or interact with it using a Python script. Follow the instructions below to set up the Flask app, install dependencies, and start the server on 127.0.0.1:5000.

Prerequisites

- Python 3.11 or above
- pip (Python package installer)

Installation Instructions

1. Clone the repository

First, clone the repository to your local machine:

git clone https://github.com/yourusername/your-repo-name.git
cd your-repo-name

2. Create a virtual environment

It is recommended to use a virtual environment to manage the project's dependencies. Create one using Python 3.11:

python3.11 -m venv venv

3. Activate the virtual environment

- For Windows:

venv\Scripts\activate

- For macOS/Linux:

source venv/bin/activate

4. Install project dependencies

Once the virtual environment is activated, install the necessary dependencies by running:

pip install -r requirements.txt

This will install all the required Python libraries, including Flask, necessary for running the application.

5. Running the Flask App

To start the Flask server, simply run the following command:

python app.py

By default, the Flask app will run on 127.0.0.1:5000.

6. Testing the API with Postman

1. Open Postman.
2. Set the request type to POST.
3. Enter the URL: http://127.0.0.1:5000/upload.
4. In the request body, choose form-data.
5. Select the file you want to upload by clicking on the "Choose Files" button.
6. Send the request.

You should receive a response from the API indicating whether the upload was successful.

7. Using the API in a Python Script

You can also interact with the API directly through Python using the requests library. Here's an example Python script to upload a file:

import requests

url = "http://127.0.0.1:5000/upload"
file_path = "path_to_your_file"

# Open the file to send in the request
with open(file_path, 'rb') as file:
    files = {'file': file}
    response = requests.post(url, files=files)

if response.status_code == 200:
    print("File uploaded successfully!")
else:
    print("Failed to upload the file.")
