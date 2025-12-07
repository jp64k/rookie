**Note: These changes are currently in development and may not be merged into Rookie's production version. You'll find a download below, which is simply a compiled version with [all of my changes and improvements of the source](https://github.com/jp64k/rookie/tree/beta/RSL-2.35-yt).**

# RSL 3.0 BETA ⸺ JP's (extended) version
A complete UI redesign, substantial performance improvements and enhanced functionality. Highlights include comprehensive startup optimizations with 95% faster game list initialization, instant filtering, a new gallery view, modernized UI components, integrated uninstall buttons, and numerous quality-of-life improvements throughout.

**Details & Download: [https://github.com/jp64k/rookie/releases/tag/release-3.0](https://github.com/jp64k/rookie/releases/tag/release-3.0)**

<img width="1256" height="753" alt="AndroidSideloader_iOoxoeh5sx" src="https://github.com/user-attachments/assets/5be83c7b-3f16-484f-8501-a8bce9d2fc3d" />

# AndroidSideloader

## Disclaimer
This application might get flagged as malware by some antivirus software; however, both the Sideloader and the Sideloader Launcher are open source.

To run properly, Rookie must be extracted to a non-Protected folder on your drive. We recommend running Rookie from C:\RSL\Rookie
Do Not use folders such as- C:\Users; C:\Users\Desktop; C:\Program Files; OneDrive; Google Drive; etc...
Rookie will cleanup its own folder. We are not responsible if you run Rookie from a folder containing other files as Rookie may delete them.


## Support
For any assistance or questions, please utilize our support channels available at [Live Chats](https://vrpirates.wiki/en/general_information/live-chats).

## Build Instructions
This project is developed using C# with WinForms targeting the .NET Framework 4.5.2. To build the project successfully in Visual Studio 2022, follow these steps:

1. Clone this repository to your local machine.
2. Ensure you have the .NET Framework 4.5.2 installed on your machine.
3. Open the solution file (`*.sln`) in Visual Studio 2022.
4. Sometimes the building process can fail due to the packages.config, you should migrate it to PackageReference, do this by right clicking on References in the Solution Explorer, and pressing "Migrate packages.config to PackageReference"
5. Build the solution by selecting "Build" > "Build Solution" from the Visual Studio menu or pressing `Ctrl + Shift + B`. (or right click the solution in the solution explorer, then press Build)
6. Run the application.

## Contributing
We welcome contributions from the community. If you would like to contribute, please fork the repository, branch from the newest beta branch from this repository, make your changes, and submit a pull request.

## License
AndroidSideloader is distributed under the GPL license, meaning any forks of it must have their source code made public on the internet. See the [LICENSE](LICENSE) file for details.
