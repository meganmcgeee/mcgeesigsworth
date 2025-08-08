# Google Apps Script OAuth Error Troubleshooting

## Error: "Error 401: deleted_client"

This OAuth authorization error is common when setting up Google Apps Script. Here are several solutions:

### Solution 1: Clear Browser Data
1. **Clear Cache & Cookies**:
   - Chrome: Settings → Privacy → Clear browsing data → Cookies and cached images
   - Firefox: Settings → Privacy → Clear Data
   - Safari: Develop → Empty Caches, then Safari → Clear History

2. **Try Incognito/Private Mode**:
   - This bypasses cached authentication data
   - Complete the setup in a private browsing window

3. **Use Different Browser**:
   - If Chrome fails, try Firefox or Safari
   - Sometimes browser-specific OAuth issues occur

### Solution 2: Alternative Setup Method
1. **Create from Google Drive**:
   - Go to [Google Drive](https://drive.google.com)
   - New → More → Google Apps Script
   - This creates the project with different OAuth settings

2. **Step-by-step Deployment**:
   - Save the script first before deploying
   - Test the script manually before web deployment
   - Deploy incrementally with different permission levels

### Solution 3: Formspree Alternative (Easier)
If Google Apps Script continues to cause issues, use Formspree instead:

1. **Sign up at [Formspree](https://formspree.io)**
2. **Create a new form**
3. **Update your form action**:
   ```html
   <form action="https://formspree.io/f/YOUR_FORM_ID" method="POST">
   ```
4. **No server setup required**

### Solution 4: Netlify Forms (If using Netlify)
If hosting on Netlify, you can use their built-in form handling:
1. Add `data-netlify="true"` to your form
2. No additional setup needed
3. Responses appear in Netlify dashboard

### Solution 5: Manual Google Sheet Setup
1. **Create Google Form instead**:
   - Use Google Forms to create an RSVP form
   - Responses automatically go to Google Sheets
   - Embed the form or link to it from your website

2. **Simple Email Fallback**:
   - Update form to use `mailto:` action
   - Add JavaScript to format email with form data
   - Less automated but always works

## Recommended Quick Fix

For immediate deployment, I recommend using **Formspree**:

1. Sign up at formspree.io (free tier allows 50 submissions/month)
2. Create a form and get your endpoint URL
3. Update the `scriptURL` in your website to the Formspree URL
4. Test immediately - no OAuth issues

Would you like me to update your form to use Formspree instead?