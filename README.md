**Note: These changes are currently in development and may not be merged into Rookie's production version. You'll find a download below, which is simply a compiled version with all of my changes and improvements of the source [here](https://github.com/VRPirates/rookie/compare/beta/RSL-2.35...jp64k:rookie:beta/RSL-2.35-yt) and [there](https://github.com/VRPirates/rookie/compare/beta/RSL-3.0...jp64k:rookie:RSL-3.0).**

# JP's RSL 3.0 BETA (Fixed V6)
A complete UI redesign, substantial performance improvements and enhanced functionality. Highlights include comprehensive startup optimizations, much faster game list initialization, instant list filtering, a new gallery view, modernized UI components, integrated uninstall buttons, improved wireless ADB workflows and numerous quality-of-life improvements throughout.

**Details & Download: [https://github.com/jp64k/rookie/releases/tag/release-3.0-fixed6](https://github.com/jp64k/rookie/releases/tag/release-3.0-fixed6)**

![ezgif-5636440132a5fd37](https://github.com/user-attachments/assets/7580c01e-8499-4eb5-abad-87ac04e0a7b4)

## Game Gallery
- Added a custom high-performance Gallery View with smooth animations and dynamic scaling  
- Toggle seamlessly between List and Gallery views, with your preference automatically saved for future launches  
- Switching from List to Gallery or Gallery to List scrolls directly to the previously selected game to maintain context  
- Features include smooth scrolling, hover animations, status badges, favorite borders and integrated uninstall buttons for installed apps  
- Supports search, filters, sorting and context menu actions (“Add to Favorites”, “Remove from Favorites”)   
- Optimized LRU image caching ensures smooth performance even on low-end hardware  

## Performance Improvements
- Improved startup performance through overhaul of initialization logic, removal of splash screen, parallelized asynchronous operations, batched version retrieval, optimized metadata extraction, faster directory deletion and much faster game list initialization
- Instant list filtering via caching and streamlined filter logic (INSTALLED / UPDATE AVAILABLE / NEWER THAN LIST)  
- Improved search responsiveness with indexed lookups and reduced debounce timers  
- Reduced application size by removing unused assets and optimizing existing assets

## UI & UX Redesign
- Complete visual overhaul with new color scheme and refined layout for improved consistency and modernity  
- Redesigned left-side navigation bar with smooth animations and clearer device information, status and option presentation  
- Relocated and refined numerous options (mount device, select device, share app, uninstall app, pull-to-desktop, filters, etc.) for a more logical workflow  
- Fine-tuned styling, sizing, positioning and color consistency across all UI components with enhanced visual polish
- Implemented modern ToggleSwitch component with animations and updated Quest and Rookie option menus to use the new toggles  
- Redesigned Rookie option menu layout to reduce vertical height and improve readability  
- Added status indicators in the bottom-left corner showing Rookie status, device ID, mirror status and sideloading status at a glance  
- Corrected grammatical and logical issues across text, tooltips and titles throughout the application  
- Added uninstall buttons directly in List and Gallery views for quicker app management  
- Updated the app icon based on the VRP server icon and enabled it in the window title bar  

Together with the refined sorting/installation status filters and uninstall functions, these changes allow Rookie to function not only as a sideloader, but also as an efficient device app browser and manager.

## Wireless ADB Enhancements
- Fully reworked Wireless ADB options to simplify setup and day-to-day use  
- **Manual mode:** 
  - The IP address field now automatically prefills the first three octets by using the system's local IPv4, reducing typing and input errors  
- **Automatic mode:**  
  - No longer requires a USB connection to establish a connection  
  - Instead now performs a network scan to automatically find the device and connects to it
  - Includes multi-device selection support (behavior designed for multiple devices, though only tested with a single device)  
- Updated the ADB button label and messages to better reflect the new logic and to provide clearer guidance during connection attempts
- Increased speed of disabling Wireless ADB, reducing the time it takes to turn the feature off 
- Note: Wireless ADB still requires a one-time USB setup to run the `adb tcpip 5555` command. In testing, connections could not be established from Rookie (both in this build and in earlier 2.34) without enabling TCP/IP mode on the device

## Sideloading & Install Flow
- Added a modern progress bar with improved visuals and clearer status information during installs
- Now shows real-time progress for app installs and OBB file transfers while sideloading, powered by integrated AdvancedSharpAdbClient progress reporting  
- Improved messages and prompts during and after sideloading to make actions, errors and results easier to understand  
- Added a dialog asking whether to delete game files after installation when enabling sideloading from the left navigation toggle  

## Device Handling & Connectivity
- Fixed several startup issues that could cause false connection error messages  
- Resolved zombie ADB instances preventing proper startup and reliable connections
- Fixed initialization behavior when no device is connected so the app continues in a predictable "download-only mode" state without a headset attached
- Refined "download-only mode" logic to preserve downloaded files until installation has completed successfully
- Added automatic device detection to trigger a full UI/data refresh once a device is connected

## Local Blacklist
- Added local blacklist support allowing users to permanently suppress donation prompts for specific apps  
- Blacklisted apps are stored in a local `blacklist.json` and merged locally with the server blacklist  
- This eliminates unwanted prompts immediately without waiting for server-side blacklist updates  

## Stability & Bug Fixes
- Fixed active filter resetting after uninstalling a game so filters remain intact while you manage your library 
- Fixed several issues around initialization when no device is connected, reducing edge-case crashes and inconsistent states  
- Fixed YouTube trailer playback issues by using a local `player.html` with the YouTube IFrame API and a WebView2 message bridge, plus per-game video ID caching and WebView2 optimizations for faster and more reliable trailer loading  
- Added `WebView2.dll` validation to ensure required runtime dependencies are present
- Added a retry mechanism for RCLONE initialization to improve robustness of cloud-related operations
- Synced sideloading button text to correctly match the current sideloading status to avoid confusion  
- Fixed update prompt when the local version exceeds the server version to avoid misleading downgrade suggestions
  
**Details & Download: [https://github.com/jp64k/rookie/releases/tag/release-3.0-fixed6](https://github.com/jp64k/rookie/releases/tag/release-3.0-fixed6)**

---


# Forked Info: AndroidSideloader

## Forked Info: Disclaimer
This application might get flagged as malware by some antivirus software; however, both the Sideloader and the Sideloader Launcher are open source.

To run properly, Rookie must be extracted to a non-Protected folder on your drive. We recommend running Rookie from C:\RSL\Rookie
Do Not use folders such as- C:\Users; C:\Users\Desktop; C:\Program Files; OneDrive; Google Drive; etc...
Rookie will cleanup its own folder. We are not responsible if you run Rookie from a folder containing other files as Rookie may delete them.


## Forked Info: Support
For any assistance or questions, please utilize our support channels available at [Live Chats](https://vrpirates.wiki/en/general_information/live-chats).

## Forked Info: Build Instructions
This project is developed using C# with WinForms targeting the .NET Framework 4.5.2. To build the project successfully in Visual Studio 2022, follow these steps:

1. Clone this repository to your local machine.
2. Ensure you have the .NET Framework 4.5.2 installed on your machine.
3. Open the solution file (`*.sln`) in Visual Studio 2022.
4. Sometimes the building process can fail due to the packages.config, you should migrate it to PackageReference, do this by right clicking on References in the Solution Explorer, and pressing "Migrate packages.config to PackageReference"
5. Build the solution by selecting "Build" > "Build Solution" from the Visual Studio menu or pressing `Ctrl + Shift + B`. (or right click the solution in the solution explorer, then press Build)
6. Run the application.

## Forked Info: Contributing
We welcome contributions from the community. If you would like to contribute, please fork the repository, branch from the newest beta branch from this repository, make your changes, and submit a pull request.

## Forked Info: License
AndroidSideloader is distributed under the GPL license, meaning any forks of it must have their source code made public on the internet. See the [LICENSE](LICENSE) file for details.
