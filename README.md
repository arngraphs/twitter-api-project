 Twitter API Interaction Project

## Introduction
This project focuses on interacting with the Twitter API to accomplish two key tasks: posting a new tweet and deleting an existing tweet. The assignment helps me understand how to work with RESTful APIs and OAuth authentication. Through this project, I gained practical experience in using external APIs, managing API requests, and handling authentication securely.

## Setup Instructions

### 1. Set Up a Twitter Developer Account
To begin using the Twitter API, I first created a Twitter Developer account by following these steps:
- **Visit the Twitter Developer Platform:** I navigated to the [Twitter Developer Platform](https://developer.twitter.com/en).
- **Sign Up:** If I did not already have a Twitter account, I created one.
- **Apply for Developer Access:** I completed the application for a developer account by providing information on how I intended to use the Twitter API.
- **Account Approval:** I awaited confirmation of my developer account approval from Twitter.

### 2. Generate API Keys
After obtaining my developer account, I generated the necessary API credentials:
- **Navigate to Projects & Apps:** I accessed the **Projects & Apps** section on the Twitter Developer dashboard.
- **Create a New Project and App:** I followed the prompts to create a new project and associated app.
- **Generate API Keys and Tokens:**
  - Under the **Keys and Tokens** tab, I generated and retrieved the following credentials:
    - **API Key**
    - **API Secret Key**
    - **Bearer Token**
    - **Access Token**
    - **Access Token Secret**

# Twitter API Interaction

## Introduction
In this assignment, I learned how to interact with the Twitter API to perform actions like posting and deleting tweets. This exercise enhanced my understanding of REST APIs, OAuth authentication, and the practical application of handling external services programmatically. The main objectives were to authenticate with the Twitter API using OAuth, make POST requests to create a new tweet, and make DELETE requests to remove an existing tweet.

## Setup Instructions

### Setting Up a Twitter Developer Account
1. **Create a Twitter Account:** If I don’t have a Twitter account, I created a new one for testing purposes.
2. **Sign Up for a Developer Account:**
   - I visited the [Twitter Developer Platform](https://developer.twitter.com/).
   - I applied for a developer account and awaited approval.
3. **Create a New Project and App:**
   - Once my account was approved, I created a new project and an associated app.

### Generating API Keys
1. **Navigate to Projects & Apps:**
   - I went to `Projects & Apps` → `Your App` → `Keys and Tokens`.
2. **Generate the Following Keys and Tokens:**
   - API Key
   - API Secret Key
   - Bearer Token
   - Access Token
   - Access Token Secret
3. **Configure OAuth:**
   - I set the Callback URL to `http://localhost:3000` for local testing.

### Running the Program
1. **Clone the Repository:**
   - I cloned the repository containing the code to my local machine.
2. **Install Dependencies:**
   - I navigated to the project directory and ran `npm install` to install the necessary packages.
3. **Create a `.env` File:**
   - I created a `.env` file in the project directory and added my API keys and tokens.
4. **Run the Application:**
   - Finally, I executed `node app.js` in the terminal to run the program.

## Program Details

### Posting a New Tweet
The program uses the Twitter API's `POST` endpoint to create a new tweet. The function `postTweet(content)` is responsible for making this API call.

#### How the Program Posts a New Tweet:
1. **Function Invocation:** When I call the `postTweet` function and pass a string as the tweet's content, it triggers the process to post the tweet.
2. **API Call:** Inside the function, it utilizes the Twitter API client (`rwClient.v2.tweet(content)`) to send a `POST` request to the Twitter API with the content of the tweet.
3. **Response Handling:** The program awaits the response from the API. If the tweet is posted successfully, it logs the success message along with the response data. In case of an error, it logs an error message that provides details about the failure.

#### Implementation:
```javascript
async function postTweet(content) {
    try {
        const response = await rwClient.v2.tweet(content); // Send POST request
        console.log('Tweet posted successfully:', response); // Log success response
    } catch (error) {
        console.error('Error posting tweet:', error.response ? error.response.data : error); // Log error response
    }
}



