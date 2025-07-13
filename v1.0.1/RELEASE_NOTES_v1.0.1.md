# PitWatch v1.0.1 Release Notes

## 🚀 New Features

### Over-The-Air (OTA) Updates
- **Automatic GitHub-based updates**: Check for and install firmware updates directly from GitHub releases
- **Seamless version management**: Uses semantic versioning (v1.0.1) with automatic version comparison
- **WiFi auto-connect**: Automatically connects to configured network for updates
- **User-friendly OTA interface**: Simple buttons for checking and installing updates

### Enhanced User Interface
- **New OTA Settings Page**: Dedicated page for firmware updates and system information
- **Version display**: Shows current firmware version and build date
- **Update status**: Real-time progress bars and status messages during updates

### System Improvements
- **Optimized build process**: Removed unnecessary libraries for faster compilation
- **Better error handling**: Improved stability and error reporting
- **Enhanced logging**: Detailed startup and version information

## 🔧 Technical Changes

### Core Updates
- Added comprehensive OTA update system (`A08_otaSettingsPage.cpp/h`)
- Implemented version management system (`version.cpp/h`)
- Automatic firmware version detection and comparison
- GitHub API integration for release checking

### Build Optimizations
- Removed unused audio libraries (ESP8266Audio, arduinoFFT)
- Streamlined dependency management
- Faster build times and smaller firmware size

### File Structure
- Converted main file from `.ino` to `.cpp` for better compatibility
- Added comprehensive documentation and guides
- Structured version management system

## 📋 Installation

### For End Users
1. Navigate to OTA Settings on your PitWatch
2. Ensure WiFi connection
3. Click "CHECK UPDATES"
4. If update available, click "INSTALL UPDATE"
5. Device will restart with new firmware

### For Developers
1. Download `firmware.bin` from this release
2. Flash via USB using your preferred method
3. Or use the OTA system for wireless updates

## 🔄 Upgrade Path

- **From v1.0.0**: Use OTA update system (recommended)
- **First installation**: Flash firmware.bin via USB

## 📚 Documentation

- See `OTA_UPDATE_GUIDE.md` for user instructions
- See `VERSION_MANAGEMENT_GUIDE.md` for developer guidelines

## ⚙️ System Requirements

- LilyGo T-Watch S3 hardware
- WiFi network access for OTA updates
- Compatible with existing PitWatch installations

## 🐛 Bug Fixes

- Fixed compilation issues with library dependencies
- Improved memory management and stability
- Enhanced error handling during updates

---

**Build Date**: July 13, 2025  
**Firmware Size**: 1.6MB  
**Recommended Update Method**: OTA via device interface
