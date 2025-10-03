# Chocolatey .zip Installer Instructions

## Step 1: Download and Install Dependencies
Open an **Admin PowerShell** window and run:

```Set-ExecutionPolicy Bypass -Scope Process -Force; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/api/v2//ChocolateyInstall.ps1'))```
```choco install git```
The first installs chocolatey and the second installs git.

# Step 2: Clone the repo
Open a admin powershell window and use cd to move to the folder where you want to put everything.
Run ```git clone https://github.com/FootGod-bot/choco-example``` to get all the files needed.

# Step 3: Cofiguration
Edit config.json (located in the tools folder) and edit these pramaters.
app name → Name of the folder and shorcuts.

zip name → ZIP to extract (found in the tools folder).

Main Path → Path to the main file from extract. say you have a scripts folder with script.py, you would put scripts/script.py, or if it is in the root of the zip, just put the name

startup → Set to true to make the file run every launch. Set to false to disable

start menu → When you press window key, will the app sow up. If so set to true, otherwise false.

# Step 4: creating the zip
Select all the files you want to extract and right click → compress → compress to .zip
Move the file to the tools folder and rename it to zip name in config.

# Step 5: Testing:
Run ```choco pack``` in a admin powershell or command prompt.
Run ```choco install MyApp -s .``` Replace MyApp with the app name in your .nuspec
If startup is true, press win + r and type ```shell:startup```. Check that your shortcut was made and opens the correct thing.
If start menu is true, press win + r and type ```C:\ProgramData\Microsoft\Windows\Start Menu\Programs``` Check that the shortcut is made and opens the correct thing.

## Step 6: Push to Chocolatey Community Repo

1. **Get an API Key**
   - Go to [https://community.chocolatey.org](https://community.chocolatey.org) and log in.
   - Click your username → **API Keys** → **Generate New Key**.
   - Copy the key.

2. **Add the API Key to Chocolatey**
   Open an **Admin PowerShell** and run:

   ```choco apikey --key YOUR_API_KEY_HERE -source https://push.chocolatey.org/

# Thats it
Its that easy. Congrats!!
