# n8n Workshop Prep

This repository contains a test workflow to verify your n8n credentials before the workshop. Follow the steps below to ensure all required integrations are properly configured.

## Prerequisites

- An n8n instance (cloud or self-hosted)
- Google account with access to Gmail, Google Drive, and Google Sheets
- OpenAI API account
- Supabase account with vector store configured

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
1. Go to the "Google Drive - List Files" node
2. Click on "Credential to connect with"
3. Create or select your Google Drive OAuth2 credentials
4. Authorize n8n to access your Google Drive

#### Google Sheets
1. Go to the "Google Sheets - Read" node
2. Click on "Credential to connect with"
3. Create or select your Google Sheets OAuth2 credentials
4. Authorize n8n to access your Google Sheets

#### Gmail
1. Go to the "Gmail - Send Email" node
2. Click on "Credential to connect with"
3. Create or select your Gmail OAuth2 credentials
4. Authorize n8n to access your Gmail
5. Update the "To" email address to your own email for testing

#### OpenAI
1. Go to the "OpenAI" node
2. Click on "Credential to connect with"
3. Create new OpenAI API credentials
4. Enter your OpenAI API key

#### Supabase Vector Store
1. Go to the "Supabase Vector Store" node
2. Click on "Credential to connect with"
3. Create new Supabase credentials
4. Enter your Supabase project URL and API key

### 4. Create Test Data in Google Drive and Sheets

#### Create a Test Folder in Google Drive
1. Open Google Drive (https://drive.google.com)
2. Create a new folder (e.g., "n8n Workshop Test")
3. Copy the folder ID from the URL (the long string after `/folders/`)
   - Example: `https://drive.google.com/drive/folders/1ABC...XYZ` → folder ID is `1ABC...XYZ`

#### Create a Test Spreadsheet
1. Inside your test folder, create a new Google Sheet (e.g., "Workshop Test Data")
2. Add some mock data to the spreadsheet:
   - Header row: Name, Email, Status
   - Add 2-3 sample rows with test data
3. Copy the spreadsheet ID from the URL (the long string between `/d/` and `/edit`)
   - Example: `https://docs.google.com/spreadsheets/d/1DEF...ABC/edit` → sheet ID is `1DEF...ABC`

### 5. Update Node Parameters

#### Update the Google Drive Node
1. Open the "Google Drive - List Files" node
2. Replace `YOUR_FOLDER_ID_HERE` with your actual folder ID

#### Update the Google Sheets Node
1. Open the "Google Sheets - Read" node
2. Replace `YOUR_SHEET_ID_HERE` with your actual spreadsheet ID
3. Ensure the sheet name matches (default is "Sheet1")

### 6. Run the Workflow

1. Click the "Execute Workflow" button in n8n
2. Monitor the execution:
   - Each node should turn green upon successful execution
   - Check for any error messages (red nodes)
3. Verify the results:
   - The workflow should list files from your Google Drive folder
   - It should read data from your Google Sheet
   - You should receive a test email in Gmail
   - The OpenAI node should generate a response
   - The Supabase Vector Store should complete its operation

### 7. Troubleshooting

If any node fails:
- Check that the credentials are properly configured and authorized
- Verify that the folder ID and sheet ID are correct
- Ensure your API keys are valid and have sufficient quota/credits
- Check the error messages in n8n for specific issues
- Make sure your Google account has necessary permissions

## Success Criteria

Your setup is complete when:
- ✅ All nodes execute successfully (green status)
- ✅ You receive the test email in your Gmail inbox
- ✅ No error messages appear in the workflow execution
- ✅ All API credentials are properly authenticated

## Support

If you encounter issues during setup, please reach out before the workshop so we can help you resolve them.
