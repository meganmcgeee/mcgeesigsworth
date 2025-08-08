# Google Sheet RSVP Setup Guide

## Step 1: Create Google Sheet
1. Go to [Google Sheets](https://sheets.google.com)
2. Create a new spreadsheet
3. Name it "Wedding RSVPs" or similar
4. Copy the Sheet ID from the URL (the long string between `/d/` and `/edit`)
   - Example: `https://docs.google.com/spreadsheets/d/1BxiMVs0XRA5nFMdKvBdBZjgmUUqptlbs74OgvE2upms/edit`
   - Sheet ID: `1BxiMVs0XRA5nFMdKvBdBZjgmUUqptlbs74OgvE2upms`

## Step 2: Set Up Google Apps Script
1. Go to [Google Apps Script](https://script.google.com)
2. Click "New Project"
3. Replace the default code with the contents of `google-apps-script.js`
4. Update the `SHEET_ID` variable with your Google Sheet ID
5. Save the project (give it a name like "Wedding RSVP Handler")

## Step 3: Deploy the Web App
1. In Apps Script, click "Deploy" → "New deployment"
2. Choose type: "Web app"
3. Description: "Wedding RSVP Form Handler"
4. Execute as: "Me"
5. Who has access: "Anyone"
6. Click "Deploy"
7. Copy the Web App URL

## Step 4: Update Your Website
1. Open `index.html`
2. Find the line: `const scriptURL = 'https://script.google.com/macros/s/YOUR_SCRIPT_ID_HERE/exec';`
3. Replace `YOUR_SCRIPT_ID_HERE` with your Web App URL

## Step 5: Test the Form
1. Submit a test RSVP through your website
2. Check your Google Sheet - you should see the response appear
3. Check the browser console for any errors

## Data Structure
Your Google Sheet will automatically create these columns:
- **Timestamp**: When the RSVP was submitted
- **Name**: Guest name
- **Email**: Guest email
- **Attending**: Yes/No/Maybe
- **Guest Count**: Number of guests
- **Message**: Special requests/dietary restrictions
- **IP Address**: For basic tracking

## Getting RSVP Summary
You can run the `getRSVPSummary()` function in Apps Script to get statistics:
- Total attending
- Total not attending  
- Total guest count
- Total responses

## Security Notes
- The Web App is set to "Anyone" access but only accepts POST requests from your form
- No sensitive data is exposed
- Google automatically handles SSL/HTTPS
- Consider adding domain restrictions if needed

## Troubleshooting
- If form submissions fail, check the Apps Script execution log
- Make sure the Google Sheet exists and has the correct ID
- Verify the Web App deployment URL is correct
- Check browser console for JavaScript errors

## Optional Enhancements
- Set up email notifications when new RSVPs arrive
- Create a dashboard view of RSVP data
- Add form validation in Apps Script
- Export data to other formats