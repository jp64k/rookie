**Note: These changes are currently in development and may not be merged into Rookie's production version. You'll find a download below, which is simply a compiled version with [all of my changes and improvements of the source](https://github.com/VRPirates/rookie/compare/beta/RSL-2.35...jp64k:rookie:beta/RSL-2.35-yt).**

# RSL 3.0 BETA ⸺ JP's version (Fixed)
A complete UI redesign, substantial performance improvements and enhanced functionality. Highlights include comprehensive startup optimizations, much faster game list initialization, instant list filtering, a new gallery view, modernized UI components, integrated uninstall buttons and numerous quality-of-life improvements throughout.

**Details & Download: [https://github.com/jp64k/rookie/releases/tag/release-3.0-fixed](https://github.com/jp64k/rookie/releases/tag/release-3.0-fixed)**

<img width="1256" height="753" alt="AndroidSideloader_iOoxoeh5sx" src="https://github.com/user-attachments/assets/5be83c7b-3f16-484f-8501-a8bce9d2fc3d" />

## Game Gallery
- Added a custom high-performance Gallery View with smooth animations and dynamic scaling  
- Toggle seamlessly between List and Gallery views, with your preference automatically saved for future launches  
- Features include smooth scrolling, hover animations, status badges, favorite borders and integrated uninstall buttons for installed apps  
- Supports search, filters, sorting and context menu actions (“Add to Favorites”, “Remove from Favorites”)  
- Optimized LRU image caching ensures smooth performance even on low-end hardware  

## Performance Improvements
- Improved startup performance through overhaul of initialization logic, removal of splash screen, parallelized asynchronous loading, batched version retrieval, optimized metadata extraction and much faster game list initialization  
- Instant list filtering via caching and streamlined filter logic (INSTALLED / UPDATE AVAILABLE / NEWER THAN LIST)  
- Improved search responsiveness with indexed lookups and reduced debounce timers
- Improved metadata extraction using faster directory deletion, parallel operations and atomic game list updates  
- Reduced application size by removing now unused assets 

## UI & UX Redesign
- Complete visual overhaul with custom theme, new color scheme and refined architecture for improved consistency and modernity  
- Redesigned left-side navigation bar with smooth animations and improved device information and option presentation  
- Relocated and refined numerous options (mount device, select device, share app, uninstall app, pull-to-desktop, filters, etc.)  
- Fine-tuned sizing, positioning and color consistency across all UI components  
- All message boxes now use custom themed styling with enhanced visual polish  
- Implemented a modern ToggleSwitch component (iOS-like) with animations and updated Quest and Rookie option menus to use the new toggles  
- Redesigned Rookie option menu layout for reduced vertical height
- Corrected grammatical and logical issues across text, tooltips and titles throughout the application  
- Added uninstall buttons directly in List and Gallery views for quicker app management  
- The refined sorting/installation status filters and uninstall functions now also let Rookie function as an efficient quest-app browser and manager

## Local Blacklist
- Added local blacklist support allowing users to permanently suppress donation prompts for specific apps  
- Blacklisted apps are stored in a local `blacklist.json` and merged locally with the server blacklist, eliminating prompts without waiting for server-side blacklist updates  

## Stability & Bug Fixes
- Fixed several startup issues causing false connection error messages
- Resolved zombie ADB instances preventing proper startup  
- Fixed YouTube trailer playback issues by using a local `player.html` with the YouTube IFrame API and a WebView2 message bridge, also added per-game video ID caching and WebView2 optimizations for faster and more reliable trailer loading
- Added WebView2.dll validation to ensure required runtime dependencies are present  
- Added a retry mechanism for RCLONE initialization  
- Fixed update prompt when the local version exceeds the server version

**Details & Download: [https://github.com/jp64k/rookie/releases/tag/release-3.0-fixed](https://github.com/jp64k/rookie/releases/tag/release-3.0-fixed)**


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
