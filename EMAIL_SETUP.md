# Email Setup Guide - Contact Form

## Current Status
✅ EmailJS integration has been added to the contact form
⚠️ **You need to configure EmailJS to actually send emails**

## Quick Setup (EmailJS - Free)

### Step 1: Create EmailJS Account
1. Go to https://www.emailjs.com/
2. Sign up for a free account
3. Verify your email address

### Step 2: Create Email Service
1. Go to "Email Services" in dashboard
2. Click "Add New Service"
3. Choose your email provider (Gmail, Outlook, etc.)
4. Connect your email account
5. Copy the **Service ID** (e.g., `service_xxxxx`)

### Step 3: Create Email Template
1. Go to "Email Templates"
2. Click "Create New Template"
3. Use this template:

```
Subject: New Contact Form Submission from {{from_name}}

Hello Dileep Tiwari,

You have received a new message from your website contact form:

Name: {{from_name}}
Email: {{from_email}}
Phone: {{phone}}
Subject: {{subject}}

Message:
{{message}}

---
This email was sent from your website contact form.
Reply to: {{reply_to}}
```

4. Copy the **Template ID** (e.g., `template_xxxxx`)

### Step 4: Get Public Key
1. Go to "Account" → "General"
2. Copy your **Public Key** (e.g., `xxxxxxxxxxxxx`)

### Step 5: Update script.js
Open `script.js` and replace these values:

```javascript
// Line ~195: Replace with your Public Key
emailjs.init('YOUR_PUBLIC_KEY'); // Replace YOUR_PUBLIC_KEY

// Line ~220: Replace with your Service ID
const serviceID = 'YOUR_SERVICE_ID'; // Replace YOUR_SERVICE_ID

// Line ~221: Replace with your Template ID
const templateID = 'YOUR_TEMPLATE_ID'; // Replace YOUR_TEMPLATE_ID

// Line ~222: Replace with your Public Key again
const publicKey = 'YOUR_PUBLIC_KEY'; // Replace YOUR_PUBLIC_KEY
```

## Alternative: Formspree (Even Easier)

If you prefer a simpler solution:

1. Go to https://formspree.io/
2. Sign up for free
3. Create a new form
4. Copy the form endpoint URL
5. Update the form action in `index.html`:

```html
<form class="contact-form" id="contactForm" 
      action="https://formspree.io/f/YOUR_FORM_ID" 
      method="POST">
```

## Testing
After setup:
1. Fill out the contact form
2. Click "Send Message"
3. Check your email inbox
4. You should receive the form submission

## Free Tier Limits
- EmailJS: 200 emails/month (free)
- Formspree: 50 submissions/month (free)

Both services offer paid plans for more submissions.

## Support
If you need help setting up, refer to:
- EmailJS Docs: https://www.emailjs.com/docs/
- Formspree Docs: https://help.formspree.io/

