# EmailJS Setup Instructions

## Complete Step-by-Step Guide to Enable Contact Form

### Step 1: Create EmailJS Account

1. Go to [https://www.emailjs.com/](https://www.emailjs.com/)
2. Click "Sign Up" and create a free account
3. Verify your email address

---

### Step 2: Add Email Service

1. After logging in, click on **"Email Services"** in the left sidebar
2. Click **"Add New Service"**
3. Choose your email provider:
   - **Gmail** (recommended for most users)
   - Outlook
   - Yahoo
   - Or other providers

4. Follow the connection steps:
   - For Gmail: You may need to allow less secure apps or use App Password
   - Click "Connect Account"
   - Sign in with your email

5. After successful connection, **COPY YOUR SERVICE ID**
   - Example: `service_abc123xyz`
   - Save this somewhere safe!

---

### Step 3: Create Email Template

1. Click on **"Email Templates"** in the left sidebar
2. Click **"Create New Template"**
3. Set up your template:

**Template Settings:**
- **Template Name**: Contact Form Submission (or any name you want)

**Email Template Content:**

**Subject:**
```
New Message from {{from_name}} - Glam by Suvii
```

**Content (Body):**
```
You have received a new message from your portfolio website!

Name: {{from_name}}
Email: {{from_email}}

Message:
{{message}}

---
This message was sent from your portfolio contact form.
```

4. Click **"Save"**
5. **COPY YOUR TEMPLATE ID**
   - Example: `template_xyz789abc`
   - Save this somewhere safe!

---

### Step 4: Get Your Public Key

1. Click on **"Account"** in the left sidebar
2. Go to **"General"** tab
3. Find **"Public Key"** section
4. **COPY YOUR PUBLIC KEY**
   - Example: `AbC123dEf456GhI789`
   - Save this somewhere safe!

---

### Step 5: Update Your Code

Open the file: `assets/js/main.js`

Find this section at the bottom:
```javascript
emailjs.sendForm('YOUR_SERVICE_ID', 'YOUR_TEMPLATE_ID', '#contact-form', 'YOUR_PUBLIC_KEY')
```

Replace the placeholders with your actual values:
```javascript
emailjs.sendForm('service_abc123xyz', 'template_xyz789abc', '#contact-form', 'AbC123dEf456GhI789')
```

**Example with real values:**
```javascript
emailjs.sendForm('service_8h3k2j1', 'template_portfolio', '#contact-form', 'user_K9mL2nP4qR5sT')
```

---

### Step 6: Test Your Contact Form

1. Make sure your website is running (refresh the browser)
2. Go to the Contact section
3. Fill out the form:
   - Name: Test User
   - Email: your-email@example.com
   - Message: This is a test message

4. Click "Send Message"
5. You should see: **"Message sent successfully ✅"**
6. Check your email inbox for the message!

---

### Troubleshooting

**Problem: "Message not sent (service error) ❌"**
- Check that all three IDs are correct in main.js
- Make sure your EmailJS account is verified
- Check your email service connection in EmailJS dashboard

**Problem: Email not received**
- Check your spam folder
- Verify the "To Email" in your EmailJS template settings
- Make sure the email service is properly connected

**Problem: Form doesn't submit**
- Open browser console (F12) and check for errors
- Make sure EmailJS script is loaded (check Network tab)
- Verify the form has id="contact-form"

---

### Important Notes

1. **Free Account Limits:**
   - EmailJS free plan allows 200 emails per month
   - Rate limit: 2 emails per second

2. **Security:**
   - Public Key is safe to use in frontend code
   - Never share your Private Key
   - Service ID and Template ID are also safe to expose

3. **Email Template Variables:**
   - `{{from_name}}` - Gets value from input with name="user_name"
   - `{{from_email}}` - Gets value from input with name="user_email"
   - `{{message}}` - Gets value from textarea with name="message"

---

### Your Configuration Checklist

- [ ] EmailJS account created and verified
- [ ] Email service connected
- [ ] Email template created
- [ ] Service ID copied
- [ ] Template ID copied
- [ ] Public Key copied
- [ ] main.js file updated with IDs
- [ ] Website tested
- [ ] Test email received

---

### Support

If you need help:
- EmailJS Documentation: https://www.emailjs.com/docs/
- Check the browser console for error messages
- Verify all IDs are correct and properly quoted

---

**Your website is ready! The contact form will now send emails to your inbox when visitors submit the form.**
