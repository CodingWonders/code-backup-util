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

6. **IMPORTANT**: replace all values of `SourceFolder` from `C:\dev` (a sample development folder) with the folder you store the projects on. Also replace all references of `I:\` with the target directory of your choosing
7. Save the new flow and click the Play button in the flow list

## Scheduling the task
Power Automate doesn't support scheduling desktop flows, so we have to improvise a little bit with Task Scheduler:

1. Open Task Scheduler or press `Win + R` and type `taskschd.msc`
<p align="center">
  <img src="https://user-images.githubusercontent.com/101426328/234676547-dbc69ed9-b04c-4136-bf3b-79f2d83d3f26.png">
</p>

2. Right-click an empty area of the task list, and click "New basic task..."
<p align="center">
  <img src="https://user-images.githubusercontent.com/101426328/234677123-8ff24a6d-6b58-4c32-bdb5-8de77579db4b.png">
</p>

3. Provide a name and a description (the latter is optional)
<p align="center">
  <img src="https://user-images.githubusercontent.com/101426328/234677533-da8fb7b0-c5f8-4412-89b2-d66e622982b1.png">
</p>

4. Specify when should the task be triggered. It is recommended to keep the default value, and to trigger the task at 9 PM
<p align="center">
  <img src="https://user-images.githubusercontent.com/101426328/234678141-c32b2378-39bc-4da3-aed5-a8ea361f7bb1.png">
</p>
<p align="center">
  <img src="https://user-images.githubusercontent.com/101426328/234678523-877ae36d-3af3-46b2-b7bd-3ff8a2b29724.png">
</p>

  > If your time zone is affected by daylight savings, tick the "Sync time zones" check box
  
5. Tell the wizard to start a program (it is the default value), and specify the following settings in the next page:

    - Program or script: `ping`
    - Arguments: `localhost`
    - Start in: (nothing)
    
  > The flow waits for the `ping` process. The combination doesn't ping external servers, but only your host system (`localhost`, `127.0.0.1`)
  
6. In the Summary screen, click "Finish"

The disadvantage of this is that, when the task is triggered, a CMD window will show. This is the `ping` command running. If you know of a better way of running the task without showing anything, please let me know.

## How do I contribute?
You'll need to follow the steps in the "How do I begin?" section first. Then, make your fixes, select ALL blocks and copy it to a text editor. Save the contents to `code-backup-util.robin` and replace the contents of the old file in the repository. That's it!
