## Loading the Extension into Chrome

1. Open the Chrome browser and navigate to `chrome://extensions`.
2. Enable Developer Mode by clicking the toggle switch next to 'Developer mode'.
3. Click the 'Load unpacked' button and select the extension directory.

```markdown
# Note

This will load your extension directly into your Chrome browser for testing. The extension will remain installed until you manually remove it. It's a great way to test your extension during development.
```

Remember to reload the extension from `chrome://extensions` page every time you make changes to the `manifest.json` or `background.js` files.

I hope this helps! Let me know if you have any further questions.

```markdown
# Notification Creator Chrome Extension

This Chrome extension uses the Chrome API to generate notifications in the Chrome browser. It listens for a specific message and then creates a notification based on that message.

## Installation

1. Copy the `background.js` file into your Chrome extension's background directory.
2. Add the "notifications" permission to the `manifest.json` file in your Chrome extension:

```json
{
  "manifest_version": 2,
  "name": "Notification Creator",
  "version": "1.0",
  "background": {
    "scripts": ["background.js"]
  },
  "permissions": ["notifications"]
}
```

## Usage

To create a notification, send a message to the background script with an `action` property of "people_joined" and a `txt` property containing the message you want to display:

```javascript
chrome.runtime.sendMessage({
  action: "people_joined",
  txt: "John Doe joined the call",
});
```

The script will listen for this message and create a notification with the provided message.

## Example

Here's a step-by-step guide on how to use this extension:

1. Copy the `background.js` file into your Chrome extension's background directory.
2. Add the "notifications" permission to the `manifest.json` file in your Chrome extension.
3. In your Chrome extension, send a message to the background script:

```javascript
chrome.runtime.sendMessage({
  action: "people_joined",
  txt: "John Doe joined the call",
});
```

The script will listen for this message and create a notification with the provided message.

## Note

The `sender.tab.id` is converted to a string before being passed to the `sendNotification` function. This ensures that the `notificationId` parameter is a string, as required by the `chrome.notifications.create` method.

## Dependencies

This extension relies on the following Chrome APIs:

- `chrome.runtime.onMessage`
- `chrome.notifications.create`

## License

This project is licensed under the MIT License.
```

I hope this revised README file is easier to understand. Let me know if you have any further questions!
