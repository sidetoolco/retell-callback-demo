# Retell Callback Widget Demo

A simple demonstration of the Retell AI callback widget that allows users to request a phone call from an AI agent.

## 🌐 Live Demo

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/sidetoolco/retell-callback-demo)

Try the live demo: Coming soon after deployment!

## Features

- 🔥 Simple single HTML file demo
- 📞 Retell callback widget integration
- 🎨 Modern, responsive design
- 🚀 No build process required
- 🌍 Multi-country phone number support

## Quick Start

1. **Clone this repository**
   ```bash
   git clone https://github.com/sidetoolco/retell-callback-demo.git
   cd retell-callback-demo
   ```

2. **Open the demo**

   Simply open `index.html` in your browser or use a local server:

   ```bash
   # Using Python 3
   python -m http.server 8000

   # Using Node.js (with http-server)
   npx http-server
   ```

3. **Test the callback widget**

   Click the phone icon in the bottom right corner of the page to trigger the callback widget.

## Configuration

The widget is configured using data attributes in the script tag. You can customize:

- `data-public-key`: Your Retell public key
- `data-agent-id`: Your Retell agent ID
- `data-phone-number`: The phone number that will make outbound calls
- `data-title`: Custom widget title
- `data-countries`: Comma-separated country codes (e.g., "US,CA,GB")
- `data-color`: Hex color code for widget theme
- `data-tc`: URL to your terms and conditions (optional)
- `data-recaptcha-key`: Google reCAPTCHA v3 site key (optional)

### Example Configuration

```html
<script
  id="retell-widget"
  src="https://dashboard.retellai.com/retell-widget.js"
  type="module"
  data-public-key="key_9b7349002a90326c7c553addd6ce"
  data-agent-id="agent_d1e33aa42cae40033f4ce5e641"
  data-widget="callback"
  data-phone-number="+1234567890"
  data-title="Request a Call"
  data-countries="US,CA,GB"
  data-color="#6366f1"
></script>
```

## How It Works

1. User clicks the floating phone button
2. A form appears collecting:
   - First name
   - Last name
   - Phone number
   - Privacy policy agreement
3. User submits the form
4. The Retell API creates a phone call
5. User receives a call from the configured phone number
6. The conversation is handled by the configured AI agent

## Widget Modes

This demo uses the **callback widget** mode. Retell also offers a **chat widget** mode for text-based conversations. See the [Retell documentation](https://docs.retellai.com) for more information.

## Deployment

Deploy this demo to Vercel in minutes:

### Quick Deploy

```bash
# Install Vercel CLI
npm install -g vercel

# Deploy
vercel
```

See [DEPLOYMENT.md](./DEPLOYMENT.md) for detailed deployment instructions including custom domains and configuration.

## Resources

- [Retell AI Documentation](https://docs.retellai.com)
- [Retell Website Widget Guide](https://docs.retellai.com/build/retell-website-widget)
- [Create Voice Agent Guide](https://docs.retellai.com/build/create-voice-agent)
- [Retell Public Keys](https://docs.retellai.com/accounts/public-keys)

## Security

- The widget uses Retell's public key system, allowing direct API calls from the frontend
- Optional reCAPTCHA v3 protection available for bot prevention
- No backend proxy required for basic functionality

## Support

For issues or questions:
- [Retell Documentation](https://docs.retellai.com)
- [GitHub Issues](https://github.com/sidetoolco/retell-callback-demo/issues)

## License

MIT License - feel free to use this demo as a starting point for your own projects.
