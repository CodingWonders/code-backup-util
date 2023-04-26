# Code Backup Utility
<p align="center">
  <img src="https://user-images.githubusercontent.com/101426328/234370352-b37597aa-8e7c-4926-85f4-b625c9baf866.png">  
</p>

**Code Backup Utility** is a simple Power Automate script designed to back up your projects to your favorite location.

## Who is this script designed for?
Code Backup Utility is designed for people who would like to create "snapshots" of the projects they're working on. Code Backup Utility is also very useful in cases where, if the source files are corrupted, you can restore from a backup location and be back to a working state.

## Features of Code Backup Utility
Code Backup Utility includes the following features:
- Copy the files to a backup location
- Delete temporary Git and Visual Studio directories in the target directory

## What will be added?
These features will be added to Code Backup Utility:
- Support for deleting more temporary directories

## How do I begin?
> NOTE: this procedure is a bit complex and lengthy, as Power Automate doesn't support exporting scripts

0. Begin by downloading and installing [Power Automate Desktop](https://aka.ms/powerautomate-desktop)

    > If you have Windows 11, this tool is already included

1. Launch Power Automate. Sign in if the program asks to do so
2. Create a new flow by clicking "New flow" on the menu
<p align="center">
  <img src="https://user-images.githubusercontent.com/101426328/234374580-2c58fc4b-fcd2-4515-bd62-44bba9a285e5.png">
</p>
3. Give it a new name, or continue without naming it
<p align="center">
  <img src="https://user-images.githubusercontent.com/101426328/234374896-9bc1addd-39a1-49d4-b25c-503e72a08f7a.png">
</p>
4. You'll enter the Power Automate editor
<p align="center">
  <img src="https://user-images.githubusercontent.com/101426328/234375339-b8149ab6-7e8e-4463-9ce3-fa5384fdef55.png">
</p>

5. Open the `code-backup-util.robin` script file and copy all its contents to the editor. Power Automate will interpret everything and put it in a nice view
<p align="center">
  <img src="https://user-images.githubusercontent.com/101426328/234381124-0bd9eb5f-eff3-4857-b593-45665ef0097f.gif">
</p>
6. Save the new flow and click the Play button in the flow list
