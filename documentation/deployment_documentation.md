## Deployment Documentation

### Overview
This Chrome extension consists of a frontend extension and a backend API server. The backend is deployed on Render.com with automatic deployments triggered by changes to the main branch of the GitHub repository.

**Important Note**: This extension is **not published to the Chrome Web Store**. To use the application, you must manually load it into Chrome's extension manager using Developer Mode.

### Backend Deployment (Render.com)

#### Current Production Setup
- **Platform**: Render.com (Free Tier)
- **Deployment Method**: Automatic deployment from GitHub main branch
- **Important Limitation**: The free tier spins down with inactivity, which can delay requests by 50 seconds or more on the first request after idle period.

#### Deploying Backend Updates
1. Push changes to the main branch of your GitHub repository
2. [Github Action](https://github.com/dcsil/achievo-app/actions/workflows/backend-deployment.yml) will automatically detect the changes and trigger a deployment
3. Monitor the deployment status in the Render.com dashboard
4. Verify the deployment is successful before testing the extension

### Frontend (Chrome Extension) Setup

#### Prerequisites
- Google Account signed in to Chrome
- Chrome browser (Windows, Mac, or Linux)
- Node.js and npm installed (for building)
- Access to the project repository

#### Configuration Setup

**For Production (using deployed backend):**
1. Navigate to `frontend/src/config/api.ts`
2. Set `const ENVIRONMENT = 'production'`

**For Local Development (using local backend):**
1. Navigate to `frontend/src/config/api.ts`
2. Set `const ENVIRONMENT = 'local'`
3. Ensure your local backend server is running

#### Building the Extension

Run the build command:
```bash
npm run build
```

This will create a `build` folder containing the compiled extension.

### Running the Application

**Since this extension is not published on the Chrome Web Store, you MUST load it manually through Chrome's extension manager to run the application.**

#### Step-by-Step Installation Instructions

1. **Sign in to Chrome**
   - Ensure you are signed in to your Google Account on Chrome

2. **Navigate to Extension Manager**
   - Open Chrome browser
   - Navigate to `chrome://extensions/`

3. **Enable Developer Mode**
   - Toggle "Developer mode" on (top right corner)
   - This allows you to load unpacked extensions

4. **Load the Extension**
   - Click the "Load unpacked" button
   - Navigate to your project directory
   - Select the `build` folder
   - Click "Select Folder" or "Open"

5. **Verify Installation**
   - The extension should now appear in your extensions list
   - You should see the extension icon in your Chrome toolbar
   - If the icon is not visible, click the puzzle piece icon (Extensions) in the toolbar and pin your extension

6. **Launch the Application**
   - Click on the extension icon in your Chrome toolbar
   - The application should open and be ready to use

7. **Updating the Extension**
   - After making code changes, rebuild with `npm run build`
   - Go back to `chrome://extensions/`
   - Click the refresh/reload icon on your extension's card
   - The updated version will now be loaded

### Distribution to Teammates

#### Sharing for Production Use:
1. **Build the extension** with `ENVIRONMENT = 'production'` in `frontend/src/config/api.ts`
2. Run `npm run build`
3. **Share the `build` folder** with your teammate (via zip file, shared drive, or repository)
4. **Provide these instructions** so they can load the extension:
   - Open Chrome and go to `chrome://extensions/`
   - Enable Developer mode (toggle in top right)
   - Click "Load unpacked"
   - Select the `build` folder
   - Start using the extension

#### Sharing for Development/Testing:
1. Share the entire project repository
2. Have teammates configure `ENVIRONMENT` in `frontend/src/config/api.ts` as needed
3. Teammates should build and load the extension following the steps above

### Important Reminders

⚠️ **This extension is NOT available in the Chrome Web Store**
- You cannot install it by searching the Chrome Web Store
- You must manually load it through `chrome://extensions/` with Developer Mode enabled
- Every user needs to perform the manual loading process

⚠️ **Developer Mode Required**
- Chrome's Developer Mode must remain enabled for the extension to continue working
- If Developer Mode is disabled, the extension will stop functioning

⚠️ **No Automatic Updates**
- Unlike published extensions, this will not auto-update
- To get updates, users must obtain the new `build` folder and reload the extension

### Troubleshooting

**Extension not appearing:**
- Verify Developer Mode is enabled in `chrome://extensions/`
- Ensure you selected the `build` folder, not the project root or `frontend` folder
- Check for error messages in the extension card on `chrome://extensions/`

**Backend not responding:**
- The free Render.com instance may be spinning up. Wait up to 60 seconds for the first request.
- Check Render.com dashboard for deployment status and logs.

**Extension not loading:**
- Check Chrome console (right-click extension icon → Inspect popup) for error messages
- Verify the `ENVIRONMENT` setting matches your deployment target
- Ensure the backend is running (local or Render.com)

**"Load unpacked" button not visible:**
- Developer Mode must be enabled first (toggle in top right of `chrome://extensions/`)

### Reference
- Chrome Extension Testing Guide: https://support.google.com/chrome/a/answer/2714278?hl=en
