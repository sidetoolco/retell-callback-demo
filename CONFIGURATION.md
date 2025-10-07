# Configuration Guide

This guide will help you configure the Retell callback widget demo with your credentials.

## Required Information

You'll need the following from your Retell account:

1. **Public Key**: `key_9b7349002a90326c7c553addd6ce` (already configured)
2. **Agent ID**: `agent_d1e33aa42cae40033f4ce5e641` (already configured)
3. **Phone Number**: The Retell phone number that will make outbound calls (needs to be configured)
4. **Conversation Flow ID**: `conversation_flow_b65b55fd6a02` (optional, for advanced configuration)

## Step-by-Step Setup

### 1. Get Your Retell Phone Number

Before the widget can work, you need to configure it with a phone number from your Retell account:

1. Log in to your [Retell Dashboard](https://dashboard.retellai.com)
2. Navigate to **Phone Numbers** section
3. Copy your phone number (should be in E.164 format, e.g., `+1234567890`)

### 2. Update the Widget Configuration

Open `index.html` and find this line:

```html
data-phone-number="YOUR_RETELL_PHONE_NUMBER"
```

Replace `YOUR_RETELL_PHONE_NUMBER` with your actual phone number:

```html
data-phone-number="+1234567890"
```

### 3. Optional: Enable reCAPTCHA Protection

To prevent bot abuse, you can enable Google reCAPTCHA v3:

1. Get a reCAPTCHA v3 site key from [Google reCAPTCHA](https://www.google.com/recaptcha/admin)
2. Update the reCAPTCHA script tag:
   ```html
   <script src="https://www.google.com/recaptcha/api.js?render=YOUR_RECAPTCHA_SITE_KEY"></script>
   ```
3. Add the `data-recaptcha-key` attribute:
   ```html
   data-recaptcha-key="YOUR_RECAPTCHA_SITE_KEY"
   ```
4. Enable reCAPTCHA in your [Retell Public Keys settings](https://dashboard.retellai.com/settings/public-keys)

### 4. Optional: Customize the Widget

You can customize various aspects of the widget:

#### Change Theme Color
```html
data-color="#6366f1"  <!-- Change to any hex color -->
```

#### Modify Supported Countries
```html
data-countries="US,CA,GB,AU,MX"  <!-- Add/remove country codes -->
```

#### Custom Title
```html
data-title="Talk to Our AI Agent"
```

#### Add Terms & Conditions
```html
data-tc="https://yoursite.com/terms"
```

## Testing the Demo

1. Open `index.html` in a web browser
2. Click the phone icon in the bottom right corner
3. Fill out the form with test information
4. Submit the form
5. You should receive a phone call from your configured number

## Troubleshooting

### Widget Not Appearing
- Check browser console for errors
- Verify the script tag is in the `<head>` section
- Ensure `data-widget="callback"` is set

### No Phone Call Received
- Verify your phone number is in E.164 format
- Check that the agent ID is correct and active
- Ensure you have phone number credits in your Retell account
- Check the Retell dashboard for call logs

### Form Submission Errors
- Verify the public key is correct
- Check that reCAPTCHA is properly configured (if enabled)
- Ensure the phone number field accepts your country format

## Advanced Configuration

### Using Dynamic Variables

You can pass dynamic variables to your agent using the conversation flow:

```html
data-conversation-flow="conversation_flow_b65b55fd6a02"
```

### Webhook Integration

To track callback requests, configure webhooks in your Retell dashboard to receive events when:
- A callback is requested
- A call is initiated
- A call completes

## Resources

- [Retell Documentation](https://docs.retellai.com)
- [Widget Configuration Reference](https://docs.retellai.com/build/retell-website-widget)
- [Voice Agent Setup](https://docs.retellai.com/build/create-voice-agent)
- [Public Keys Management](https://docs.retellai.com/accounts/public-keys)

## Support

If you encounter issues:
1. Check the [Retell Documentation](https://docs.retellai.com)
2. Review the browser console for error messages
3. Verify your Retell account has active credits
4. Contact Retell support for API-specific issues
