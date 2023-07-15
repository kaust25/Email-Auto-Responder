
# Vacation Auto Responder

## Summary
The Vacation Auto Responder is a Python program that automatically replies to unread emails received between a specified start date and end date. The reply can be either prewritten or generated using the OpenAI API, based on the email snippet or body as required.

## Technology Used
- Python
- Google API (Gmail API)
- OpenAI API

## How to Run the Program
1. Install required libraries:
   
   pip install google-auth google-auth-oauthlib google-auth-httplib2 google-api-python-client openai
   

2. Create and obtain Google API credentials:
   - Go to the [Google API Console](https://console.developers.google.com/).
   - Create a new project or select an existing project.
   - Enable the Gmail API for the project.
   - Create credentials (OAuth 2.0 Client ID) for a desktop application.
   - Download the credentials JSON file and save it as `credentials.json` in the project directory.

3. Obtain OpenAI API secret key:
   - Sign up for an account on the [OpenAI website](https://openai.com/).
   - Obtain your secret API key from your account dashboard.

4. Modify the code:
   - Set the vacation start and end dates in the `start_date` and `end_date` variables.
   - Customize the `reply_body` variable with your vacation reply message.

5. Run the program:
   
   python vacation_auto_responder.py
   

## Credits
This project is developed by Kausthub Balaji. It utilizes the Google API (Gmail API) for email operations and the OpenAI API for generating auto-reply messages.

## Notes
- The program waits for a set amount of time before checking for new emails and then activates randomly between 45 to 120 seconds to scan the inbox.
- Since Gmail uses the MIME protocol for emails, the program checks for relevant headers and obtains information such as sender, receiver, dates, labels, thread ID (conversation ID), and email snippet.
- The program drafts a multipart message with a prewritten/generated reply along with the quoted message snippet to ensure that the reply remains in the same conversation thread as the initial message.
- The program alters labels to move the replied emails out of the inbox and adds a custom "Vacation Auto-reply" label.

Feel free to contribute to the project or provide any feedback!
