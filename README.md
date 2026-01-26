# Lonnskart Legal Documents - GitHub Pages Setup

This repository hosts the legal documents for the Lonnskart app, including the Privacy Policy.

## Quick Setup Instructions

### 1. Create a New GitHub Repository

```bash
# Create a new repository on GitHub named "lonnskart-legal" (or similar)
# Then clone it locally:
git clone https://github.com/yourusername/lonnskart-legal.git
cd lonnskart-legal
```

### 2. Add the Privacy Policy

```bash
# Copy the privacy-policy.html file to the repository
cp privacy-policy.html /path/to/lonnskart-legal/

# Commit and push
git add privacy-policy.html
git commit -m "Add privacy policy"
git push origin main
```

### 3. Enable GitHub Pages

1. Go to your repository on GitHub
2. Click **Settings** → **Pages** (in the left sidebar)
3. Under **Source**, select `main` branch
4. Click **Save**
5. Wait a few minutes for deployment

Your privacy policy will be available at:
```
https://yourusername.github.io/lonnskart-legal/privacy-policy.html
```

### 4. Optional: Add a Custom Domain

If you want to use `legal.lonnskart.com` or similar:

1. In your DNS settings, add a CNAME record pointing to `yourusername.github.io`
2. In GitHub Pages settings, add your custom domain
3. Enable "Enforce HTTPS"

## Updating the Privacy Policy

Whenever you need to update the privacy policy:

1. Edit `privacy-policy.html`
2. Update the "Last Updated" date in the HTML
3. Commit and push:
   ```bash
   git add privacy-policy.html
   git commit -m "Update privacy policy"
   git push origin main
   ```
4. Changes will be live within a few minutes

## Using in Your React Native App

### Option 1: Open in External Browser

```typescript
import { Linking } from 'react-native';

const PRIVACY_POLICY_URL = 'https://yourusername.github.io/lonnskart-legal/privacy-policy.html';

const openPrivacyPolicy = () => {
  Linking.openURL(PRIVACY_POLICY_URL);
};

// In your component:
<TouchableOpacity onPress={openPrivacyPolicy}>
  <Text>Privacy Policy</Text>
</TouchableOpacity>
```

### Option 2: In-App WebView

```typescript
import { WebView } from 'react-native-webview';

const PRIVACY_POLICY_URL = 'https://yourusername.github.io/lonnskart-legal/privacy-policy.html';

// In your component:
<WebView 
  source={{ uri: PRIVACY_POLICY_URL }}
  style={{ flex: 1 }}
/>
```

### Option 3: Modal with WebView

```typescript
import { Modal, SafeAreaView, TouchableOpacity } from 'react-native';
import { WebView } from 'react-native-webview';

const [showPolicy, setShowPolicy] = useState(false);

<Modal visible={showPolicy} animationType="slide">
  <SafeAreaView style={{ flex: 1 }}>
    <TouchableOpacity onPress={() => setShowPolicy(false)}>
      <Text>Close</Text>
    </TouchableOpacity>
    <WebView source={{ uri: PRIVACY_POLICY_URL }} />
  </SafeAreaView>
</Modal>
```

## Before Publishing

Make sure to replace these placeholders in `privacy-policy.html`:

- `[Your Company Address]`
- `[Your Email Address]`
- `[Your Phone Number]`
- `[your support email]`
- `[your company address]`
- `[if applicable]` (for Data Protection Officer)

## File Structure

```
lonnskart-legal/
├── README.md
├── privacy-policy.html
└── terms-of-service.html (to be added later)
```

## License

© 2026 Lonnskart. All rights reserved.
