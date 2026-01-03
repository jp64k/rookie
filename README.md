**Note: These changes are currently in development and may or may not be merged into Rookie's production version. Linked below is a compiled version with [all of my changes and improvements of the source](https://github.com/VRPirates/rookie/compare/beta/RSL-2.35...jp64k:rookie:RSL-3.0-2).**

# RSL 3.0 BETA
**Good news! The changes have been merged and RSL 3.0 BETA has been pre-released.**
**Download available here: https://github.com/VRPirates/rookie/releases**

A complete UI redesign, substantial performance improvements and enhanced functionality. Highlights include comprehensive startup optimizations, faster game list initialization, instant list filtering, a new gallery view, modernized UI components, integrated uninstall buttons, real-time installation progress updates and numerous quality-of-life improvements throughout.

<img width="1256" height="753" alt="cc5e7a818c" src="https://github.com/user-attachments/assets/ebe37ebe-5c04-4d79-a85d-d6d7e53082e8" />
<img width="1256" height="753" alt="aedf13543b" src="https://github.com/user-attachments/assets/53b8eb9a-2327-4d8e-b4c2-0f78535db077" />

## Game Gallery
- Added a custom high-performance Gallery View with smooth animations and dynamic scaling
- Toggle seamlessly between List and Gallery views, with your preference automatically saved for future launches
- Switching views scrolls directly to the previously selected game to maintain context
- Features smooth scrolling, hover animations, status badges, favorite borders and integrated uninstall buttons for installed apps
- Supports search, filters, sorting and context menu actions ("Add to Favorites", "Remove from Favorites")
- Optimized LRU image caching ensures smooth performance even on low-end hardware
- Sorting state is synchronized between List and Gallery views, maintaining consistent sort order when switching between view modes

## List View Modernization
- Added custom ModernListView component with modern dark theme and refined behavior
- Enhanced size and popularity sorting with cleaner size parsing and popularity ranking display
- Implemented modern scrollbars in both List and Gallery views for visual consistency
- Added logic to skip 0 MB entries when an MR-Fix version of the same game exists

## Performance Improvements
- Improved startup performance through overhaul of initialization logic, removal of splash screen, parallelized asynchronous operations, batched version retrieval, optimized metadata extraction and faster directory deletion
- Instant list filtering via caching and streamlined filter logic (FAVORITES / INSTALLED / UPDATE AVAILABLE / NEWER THAN LIST)
- Improved search responsiveness with indexed lookups and reduced debounce timers
- Reduced application size by removing unused assets and optimizing existing assets
- Implemented automatic Cloudflare DNS fallback to resolve connectivity issues
- Enhanced ADB connect command timeout handling to prevent startup delays

## UI & UX Redesign
- Complete visual overhaul with new color scheme and refined layout for improved consistency and modernity
- Redesigned left-side navigation bar with smooth animations and clearer device information and option presentation
- Relocated and refined numerous options (mount device, select device, share app, uninstall app, pull-to-desktop, filters, etc.) for a more logical workflow
- Fine-tuned styling, sizing, positioning and color consistency across all UI components
- Implemented modern ToggleSwitch component with animations
- Redesigned Rookie option menu layout to reduce vertical height and improve readability
- Added status indicators in the bottom-left corner showing Rookie status, device ID, mirror status and sideloading status at a glance
- Corrected grammatical and logical issues across text, tooltips and titles throughout the application
- Added uninstall buttons directly in List and Gallery views for quicker app management
- Updated the app icon based on the VRP server icon and enabled it in the window title bar
- Added automatic saving and restoration of window size, position, maximized state and sort order between sessions 

The combination of refined filters and integrated uninstall buttons allows Rookie to function not only as a Sideloader, but also as an efficient device app browser and manager

## Wireless ADB Enhancements
- Reworked Wireless ADB options to simplify setup and day-to-day use
- **Manual mode:** The IP address field now automatically prefills the first three octets using the system's local IPv4, reducing typing and input errors
- New **Automatic mode:** No longer requires a USB connection. Performs a network scan to automatically find the device and connects to it. Includes multi-device selection support
- Old **Automatic (USB) mode:** Retained the previous automatic USB-based setup as a third connection method
- Updated the ADB button label and messages to provide clearer guidance during connection attempts
- Increased speed of 'Disable Wireless ADB' feature
- **Note:** Wireless ADB still requires a one-time USB setup to run the adb tcpip 5555 command

## Sideloading & Install Flow
- Added a modern progress bar with improved visuals and clearer status information during installs
- Real-time progress for app installs, OBB file transfers, and ZIP extraction with floating-point percentages for smooth updates
- Added ETA estimation for APK installation, OBB copy and file extraction with smoothed calculations for accurate display
- Improved messages and prompts during and after sideloading to make actions, errors and results easier to understand
- Added a dialog asking whether to delete game files after installation when enabling sideloading from the sidebar

## Download Queue Enhancements
- Replaced the dated download queue ListBox with a custom ModernQueuePanel featuring drag-and-drop reordering, auto-scroll, and cancel buttons for individual entries
- Implemented persistent download queue with resume support. The queue is automatically saved and restored on startup, with a prompt to resume unfinished downloads if desired
- Implemented automatic disk and device space validation when adding games to the queue. Space checks account for already-installed packages by calculating the effective size difference needed, and users are prompted when space issues are detected
- The UI now displays total queue download size and automatically updates available device space after each installation 

## Local Blacklist
- Added local blacklist support allowing users to permanently suppress donation prompts for specific apps
- Blacklisted apps are stored in a local blacklist.json and merged locally with the server blacklist
- This eliminates unwanted prompts immediately without waiting for server-side blacklist updates

## Stability & Bug Fixes
- Fixed several startup issues that could cause false connection error messages
- Resolved zombie ADB instances preventing proper startup and reliable connections
- Fixed initialization behavior when no device is connected so the app continues in a predictable "download-only" state
- Added automatic device detection to trigger a full UI/data refresh once a device is connected
- Refactored filter and selection logic to preserve active filters and selected games when refreshing the game list
- Fixed active filter resetting after uninstalling a game
- Fixed YouTube trailer playback issues with improved player initialization, WebView2 optimizations and better search accuracy 
- Added WebView2.dll validation to ensure required runtime dependencies are present
- Added a retry mechanism for RCLONE initialization to improve robustness
- Synced sideloading button text to correctly match the current sideloading status
- Removed update prompt when the local version exceeds the server version
- Fixed cases where pop-up dialogs would open behind the main window
- Fixed corrupted user.config files preventing startup

## Preview
TODO

## Release
**Head over to **https://github.com/VRPirates/rookie/releases** for release.**
