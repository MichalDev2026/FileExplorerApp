========================================================================
                      MODERN .NET 8 FILE EXPLORER
========================================================================

A fast, crash-resistant, modern Windows file manager built with C# (.NET 8)
and WPF. Designed using strict MVVM architecture, this application combines
standard local file management with advanced system utilities, including
built-in SMB/FTP networking and a right-click drive formatting utility.

------------------------------------------------------------------------
1. KEY FEATURES
------------------------------------------------------------------------
* High-Performance Browsing:
  - Leverages .NET 8 asynchronous enumeration and UI virtualization.
  - Smoothly navigates folders containing 50,000+ files without UI freezes.

* Crash-Resistant Architecture:
  - Gracefully bypasses system-locked or protected folders (such as 
    "System Volume Information") without throwing unauthorized access 
    exceptions.

* Integrated Network Explorer:
  - SMB Shares: Connect to Windows UNC paths (e.g., \\192.168.1.50\Share) 
    with custom credential support.
  - FTP Client: Full asynchronous FTP browsing powered by FluentFTP.

* Built-in Drive Formatter & File System Selector:
  - Right-click any USB drive, external HDD, or SSD from the sidebar.
  - Format to NTFS, exFAT, or FAT32 with customizable volume labels and 
    quick format toggles.
  - Built-in OS protection safeguard prevents formatting the Windows root drive.
  - Requires UAC (Administrator) elevation before execution.

------------------------------------------------------------------------
2. TECH STACK & PREREQUISITES
------------------------------------------------------------------------
* Target Framework: .NET 8.0 (Windows Desktop)
* Language: C# 12
* Architecture: MVVM (Model-View-ViewModel)
* Primary Dependencies:
  - CommunityToolkit.Mvvm (Source generators for observable properties/commands)
  - FluentFTP (Async FTP connectivity)

Prerequisites:
* .NET 8.0 SDK (or later)
* Visual Studio 2022 (with ".NET Desktop Development" workload) or VS Code

------------------------------------------------------------------------
3. SETUP & INSTALLATION
------------------------------------------------------------------------
1. Clone or download the repository:
   git clone https://github.com/YourUsername/Modern-WPF-File-Explorer.git
   cd Modern-WPF-File-Explorer

2. Restore required NuGet packages:
   dotnet restore

   Or install dependencies manually via CLI:
   dotnet add package CommunityToolkit.Mvvm
   dotnet add package FluentFTP

3. Build and launch:
   dotnet run

------------------------------------------------------------------------
4. HOW TO USE
------------------------------------------------------------------------
* Local Browsing:
  - Double-click any folder or drive to open it.
  - Use the top navigation buttons (Back, Forward, Up) or type a path 
    directly into the address bar.
  - Type into the top-right search box for instant real-time filtering.

* Connecting to SMB / FTP:
  - SMB: Enter a UNC path like \\192.168.1.100\Shared in the Network bar. 
    Provide username and password if required, then click Connect.
  - FTP: Enter an address like ftp://ftp.example.com. Leave credentials 
    blank for anonymous access or specify them for authenticated servers.

* Formatting a Drive:
  1. Locate the target drive in the left-hand sidebar.
  2. Right-click the drive.
  3. Choose "Format Drive..." to open the modal dialogue, where you can select 
     the file system (NTFS, exFAT, FAT32), set a volume label, and toggle 
     Quick Format.
  4. Or select "Quick Format As" to instantly execute a quick format with a 
     pre-selected file system.
  5. Accept the Windows UAC Administrator prompt to proceed.

------------------------------------------------------------------------
5. DISCLAIMER
------------------------------------------------------------------------
The drive format utility invokes the native Windows format command with 
elevated privileges. While safe defaults and OS drive protection locks are 
enforced in code, users are responsible for selecting the correct drive. 
Always verify your drive letter before confirming a format operation.

------------------------------------------------------------------------
6. LICENSE
------------------------------------------------------------------------
Licensed under the MIT License.
