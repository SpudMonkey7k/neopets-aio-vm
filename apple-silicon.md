## Mac OS Apple Silicon Guide

>[!Important]
>The VM uses 2GB ram and 10GB storage.
>
>This VM already has Flash, Shockwave, 3dvia, and Fiddler already setup.
>There are 2 browsers installed, Safari and Seamonkey.
>Use Safari for Flash and Shockwave games.
>Use Seamonkey for Flash and 3dvia games.
>
>**Make sure Fiddler is running at all times when playing games**

>[!Note]
> Head to https://neopets.com/vsilogin.phtml (classic login page) to login. 
>> Note that you will need to disable your 2fa to login via classic login page. 

>[!Note]
>**NeoPass**
>
>In your default browser, like chrome:
>1. Open developer console (ctrl + shift + i).
>2. Write `document.cookie.split(';').find(c => c.includes('neologin')).trim()` in console, hit enter and you will see something like neologin=youruserxxxxx (don't show anyone this value!!!). 
>3. Then in Safari/SM visit neopets.com
>4. Open developer console (f12) and write `document.cookie = "yyy"` where yyy is what you got from chrome (neologin=youruserxxxxx). 
>5. Then refresh and you should be logged in.

### Download
1. [UTM 4.6.5](https://github.com/utmapp/UTM/releases/latest/download/UTM.dmg)
2. [Neopets VM](https://www.mediafire.com/file/wslhbasvmx1a3mz/Neo.ova/file)

>[!Note]
>This guide has two parts:
>1. Convert .ova vm file to .qcow2 vm file
>2. Setting up VM using the .qcow2 file

**Conversion** 
1. Open Terminal
2. Install Homebrew with the following command:
   
`/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"`

3. Install qemu with the following command:

`brew install qemu`

4. In Terminal, browse to where the `Neo.ova` is using the following command:

`cd Downloads`

5. Extract the disk image included in the ova with the following command: 

`tar -xvf Neo.ova`
> Once completed, there should be 3 files generated, .vmdk, .ovf, and .mf files.

6. Converting to .qcow2 using the following command:

`qemu-img convert -O qcow2 Neo-disk001.vmdk Neo.qcow2`
> This will generate the VM file needed to run in UTM

**UTM VM Guide**
1. Run UTM and click on `Create a New Virtual Machine`.

![new](https://github.com/user-attachments/assets/d33a5ca6-414e-4ca0-ad7a-9c5877b4fdf3)

2. Select `Emulate`.

![s1](https://github.com/user-attachments/assets/0a43ca5b-834a-420d-a50f-a97b827acdef)

3. Select `Other`.

![s2](https://github.com/user-attachments/assets/7cfcb429-ea22-4eeb-945f-dd25a13b53b4)

4. Under Boot Device select `None` and click `Continue`.

![s3](https://github.com/user-attachments/assets/e48c6176-9f19-42c9-ba1e-33502eb864b4)

5. Default hardware should be fine, adjust if you'd like but `2048MB` minimmum of memory is required.

![s4](https://github.com/user-attachments/assets/75fadcf2-087a-4a74-b2a1-2584ce897d50)

6. Set Storage Size to be `11GB`.

![s6](https://github.com/user-attachments/assets/33259fbf-13e2-4d40-9a52-3fd78667abcc)

7. There is no need to create a Shared Directory, simply click `Next` to move to the next step.

![s7](https://github.com/user-attachments/assets/f0d3d0e4-b95e-45d8-b2ba-2c334adbae56)

8. On the summary page, give the VM a name, check `Open VM Settings`, and click `Save`.

![s8](https://github.com/user-attachments/assets/f1465c5e-00e7-4596-9251-e8d7735fba6c)

9. Select `QEMU` from the sidebar and uncheck `UEFI Boot`.

![s9](https://github.com/user-attachments/assets/1461a2e1-e724-46a7-a454-862a188d6dc9)

10. Under `Drives` in the sidebar, select `IDE Drive` then click `Delete`.

![s10](https://github.com/user-attachments/assets/c9b5118a-965d-49f4-b5fa-4f798afa72c8)

11.  Under `Drives` in the sidebar, select `New Drive`. In the window that pops up, set Interface to `IDE` and size to `10GB` then click `Import`.

![s11](https://github.com/user-attachments/assets/73877f10-3789-47fb-a3c0-e5da9e8b67bf)

12. In the window that pops up, select the .qcow2 file that you created and press `Open`. 

![s12](https://github.com/user-attachments/assets/8a02cefa-bdc7-43c2-8639-bc476761bbac)

13. When it finishes loading, click `Save`.

![s13](https://github.com/user-attachments/assets/01bf1ecc-5506-40c2-91f1-05a86972ac89)

14. Start the VM. 
