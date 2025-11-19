# GitHub Actions Workflows

## Build iOS App Installer

This workflow builds an iOS installer (IPA file) for the Sample iOS App that can be installed on your iPhone.

### How it works

The workflow:
1. Runs on macOS with Xcode
2. Installs Carthage dependencies
3. Builds the Sample iOS App for iOS devices
4. Creates an IPA file (iOS App Package)
5. Uploads the IPA as a downloadable artifact

### Triggering the workflow

The workflow runs automatically on:
- Push to `main` or `master` branch
- Pull requests to `main` or `master` branch
- Manual trigger via "Actions" tab (workflow_dispatch)

To manually trigger:
1. Go to the "Actions" tab in GitHub
2. Select "Build iOS App Installer" workflow
3. Click "Run workflow" button

### Downloading the IPA

After the workflow completes:
1. Go to the workflow run in the "Actions" tab
2. Scroll down to the "Artifacts" section
3. Download the `SampleiOSApp-IPA` artifact
4. Unzip the downloaded file to get the IPA

### Installing on iPhone

To install the IPA on your iPhone, you have several options:

#### Option 1: Apple Configurator (Recommended)
1. Download [Apple Configurator](https://apps.apple.com/app/apple-configurator/id1037126344) from the Mac App Store
2. Connect your iPhone via USB
3. Drag and drop the IPA file onto your device in Apple Configurator

#### Option 2: Xcode
1. Open Xcode on your Mac
2. Go to Window → Devices and Simulators
3. Select your connected iPhone
4. Drag and drop the IPA file onto the "Installed Apps" section

#### Option 3: Sign with Developer Certificate
If you have an Apple Developer account, you can re-sign the IPA with your certificate and install via TestFlight or direct installation.

### Notes

- The IPA is built without code signing for simplicity
- You may need to trust the developer certificate on your iPhone after installation
- Go to Settings → General → Device Management on your iPhone to trust the app
- The artifact is kept for 30 days before automatic deletion
