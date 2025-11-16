<p align="center">
  <img src="https://github.com/K3rhos/Microsoft-Store-Apps-Direct-Downloader/assets/30273537/bea6a888-2214-4f56-8abe-a8c29ad81be4" width="600" />
</p>

# ⚙️ Microsoft Store Apps EXE Downloader

This tool allows you to download app executable files from the [Microsoft Official Web Store](https://apps.microsoft.com/) without needing to have the Microsoft Store on your computer.

It's really useful when you have a custom version of Windows (LTSC, tiny11, etc.) or if you just don't want to use the store to install your apps.

<img src="https://github.com/K3rhos/Microsoft-Store-Apps-EXE-Downloader/assets/30273537/6fd4eb07-15c3-4537-9a2b-d1c847ccf537" width="400" />

## 🔒 Security & Safety

> [!WARNING]
> **Always verify downloaded executables before running them:**
> - Only download apps from official Microsoft Store URLs
> - Check the publisher and app authenticity after download
> - Scan downloaded files with antivirus software
> - This tool validates input to prevent malicious URL injection

**Safety Features:**
- Input validation ensures only valid Microsoft Store URLs are processed
- App ID format validation (alphanumeric, hyphens, and underscores only)
- Length limits prevent potential buffer overflow issues
- Direct connection to Microsoft's official download service (`get.microsoft.com`)

## 📋 Prerequisites

- **Operating System:** Windows 7 or later
- **Compiler:** Visual Studio 2022 or later (for building from source)
- **.NET Framework:** Not required - this is a native C++ application
- **Internet Connection:** Required to fetch app download links

## 📑 How to Use

1. Download the [latest release](https://github.com/shuntia/Microsoft-Store-Apps-EXE-Downloader/releases)
2. Execute the app
3. Grab the URL from the store app you want to download (see example below)

<img src="https://github.com/K3rhos/Microsoft-Store-Apps-Direct-Downloader/assets/30273537/d308b5e1-c1c8-4a16-9f2e-fa52304a7eab" width="600" />

4. Copy & paste the URL inside the tool

<img src="https://github.com/K3rhos/Microsoft-Store-Apps-Direct-Downloader/assets/30273537/f0aded28-bb5e-43ea-9999-7e9c65e32126" width="600" />

5. Press enter - this will open a new link in your web browser and download the EXE file of the app

> [!NOTE]
> In some rare cases, you can't download app executables using this tool. As an example, it doesn't work with **Discord** & **Adobe Acrobat Reader**. This is because some apps use different distribution methods or require Microsoft Store authentication.

## 🔧 How It Works

1. The tool extracts the app ID from the Microsoft Store URL (the last part after `/detail/`)
2. It validates the URL format and app ID to ensure safety
3. It constructs a download URL using Microsoft's official installer service: `https://get.microsoft.com/installer/download/<app-id>`
4. Your default browser opens this URL, which redirects to the actual download

## 🛠️ Building from Source

### Requirements
- Visual Studio 2022 or later with C++ development tools
- Windows SDK

### Steps
1. Clone the repository:
   ```bash
   git clone https://github.com/shuntia/Microsoft-Store-Apps-EXE-Downloader.git
   cd Microsoft-Store-Apps-EXE-Downloader
   ```

2. Open the solution file in Visual Studio:
   ```
   Microsoft Store Apps EXE Downloader.sln
   ```

3. Build the project:
   - Select your configuration (Debug/Release)
   - Build > Build Solution (or press F7)

4. The executable will be in the output directory (usually `Debug/` or `Release/`)

## ❓ Troubleshooting

### "Failed: Invalid url"
- Ensure you're using a URL from `apps.microsoft.com/detail/`
- The URL should look like: `https://apps.microsoft.com/detail/9XXXXX/...`

### "Failed: Invalid app id format"
- The app ID contains invalid characters
- Try copying the URL again directly from the Microsoft Store

### Download doesn't start
- Check your internet connection
- Verify your default browser is set correctly
- Some apps may not be available for direct download

### Antivirus blocks the tool
- This is a false positive - the tool uses `ShellExecuteA` to open URLs, which some antivirus programs flag
- You can build from source to verify the code is safe
- Add an exception in your antivirus software

## 📜 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## ⚠️ Disclaimer

This tool is provided for convenience and educational purposes. Users are responsible for:
- Complying with Microsoft's Terms of Service
- Ensuring they have the right to download and use the apps
- Verifying the authenticity and safety of downloaded files

The author is not responsible for any misuse of this tool or any damages that may occur from using downloaded applications.
