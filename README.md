# n8n Workshop Prep

This repository contains a test workflow to verify your n8n credentials before the workshop. Follow the steps below to ensure all required integrations are properly configured.

## Prerequisites

- An n8n instance (cloud or self-hosted)
- Google account with access to Gmail, Google Drive, and Google Sheets
- OpenAI API account

## Setup Instructions

### 1. Download the Workflow

Download the `workflow.json` file from this repository:
- Click on `workflow.json` in the repository
- Click the "Download" or "Raw" button to save the file locally

### 2. Import the Workflow into n8n

1. Open your n8n instance
2. Click on "Workflows" in the main menu
3. Click the "Import from File" button (or use the menu: ⋮ → Import from File)
4. Select the downloaded `workflow.json` file
5. The workflow "Workshop Credentials Test Workflow" will be imported

### 3. Set Up Credentials

You'll need to configure credentials for the following services in n8n:

#### Google Drive
1. Go to the "Google Drive - Create File" node
2. Click on "Credential to connect with"
3. Create or select your Google Drive OAuth2 credentials
4. Authorize n8n to access your Google Drive

#### Google Sheets
1. Go to the "Google Sheets - Read" node
2. Click on "Credential to connect with"
3. Create or select your Google Sheets OAuth2 credentials
4. Authorize n8n to access your Google Sheets

#### Gmail
1. Go to the "Gmail - Create Draft" node
2. Click on "Credential to connect with"
3. Create or select your Gmail OAuth2 credentials
4. Authorize n8n to access your Gmail

#### OpenAI
1. Go to the "OpenAI Chat Model" node
2. Click on "Credential to connect with"
3. Create new OpenAI API credentials
4. Enter your OpenAI API key

### 4. Create Test Data in Google Sheets

#### Create a Test Spreadsheet
1. Open Google Sheets (https://sheets.google.com)
2. Create a new Google Sheet (e.g., "Workshop Test Data")
3. Add a column header in cell A1: "Name"
4. Add your name in cell A2 (e.g., "Gilad")
5. Copy the spreadsheet ID from the URL (the long string between `/d/` and `/edit`)
   - Example: `https://docs.google.com/spreadsheets/d/1DEF...ABC/edit` → sheet ID is `1DEF...ABC`

### 5. Update Node Parameters

#### Update the Google Sheets Node
1. Open the "Google Sheets - Read" node
2. Replace `YOUR_SHEET_ID_HERE` with your actual spreadsheet ID
3. Ensure the sheet name matches (default is "Sheet1")

### 6. Test the Workflow

#### Test Part 1: Google Integration Flow
1. Click the "Execute Workflow" button at the top
2. Click on the "Manual Trigger" node
3. Click "Execute node" to run the workflow
4. Monitor the execution:
   - The workflow should create a file called "n8n-workshop-test.txt" in your Google Drive
   - It should read your name from the Google Sheet
   - It should create a draft email in your Gmail with subject "n8n workshop draft"
5. Verify the results:
   - Check your Google Drive for the new text file
   - Verify the Google Sheets node output shows your name
   - Check Gmail drafts for the draft email

#### Test Part 2: Chat with AI Agent
1. In the n8n workflow, locate the "Chat Trigger" node
2. Click on the "Chat Trigger" node to open it
3. Click "Test Chat" or open the chat interface
4. Type "hello" in the chat
5. Verify that the OpenAI agent returns a response

### 7. Troubleshooting

If any node fails:
- Check that the credentials are properly configured and authorized
- Verify that the spreadsheet ID is correct
- Ensure your API keys are valid and have sufficient quota/credits
- Check the error messages in n8n for specific issues
- Make sure your Google account has necessary permissions

## Success Criteria

Your setup is complete when:
- ✅ All nodes in the manual trigger flow execute successfully (green status)
- ✅ A text file "n8n-workshop-test.txt" is created in your Google Drive
- ✅ The Google Sheets node successfully reads your name from the spreadsheet
- ✅ A draft email with subject "n8n workshop draft" appears in your Gmail drafts
- ✅ The chat trigger responds to your "hello" message with an AI-generated response
- ✅ No error messages appear in the workflow execution

## Support

If you encounter issues during setup, please reach out before the workshop so we can help you resolve them.
