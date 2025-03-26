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
1. [UTM](https://github.com/utmapp/UTM/releases/latest/download/UTM.dmg)
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

4. Check `Skip ISO boot` and click `Next`.

![s3](https://github.com/user-attachments/assets/eef7bdcf-e8b9-48a7-8c8b-a2070204d8be)

5. Set Memory to be at least `2048 MB`.

![s4](https://github.com/user-attachments/assets/aa6b33bc-8761-4b53-8c82-4c4f9dc19375)

6. Set Storage Size to be at least `11GB`.

![s6](https://github.com/user-attachments/assets/ec34646d-5f24-45ed-8e89-adcf45d0cad3)

7. There is no need to create a Shared Directory, simply click `Next` to move to the next step.

![s7](https://github.com/user-attachments/assets/f0d3d0e4-b95e-45d8-b2ba-2c334adbae56)

8. On the summary page, give the VM a name and click `Save`.

![s8](https://github.com/user-attachments/assets/7e5b1b14-ad7c-41ee-8104-0191427aae20)

9. Right click on the machine that you created and click `Edit`.

![s9](https://github.com/user-attachments/assets/414e8cea-b12d-485d-bd19-588900a99df9)

10. Uncheck `UEFI Boot`.

![s10](https://github.com/user-attachments/assets/703fdda1-4270-4aad-856e-8be33081eeaa)

11. Then select `New Drive` from the sidebar. In the window that pops up, set Interface to `IDE` and size to `10GB` then click `Import`.

![s11](https://github.com/user-attachments/assets/6eacc945-51e3-4417-b56d-242287ff0a86)

12. In the window that pops up, select the .qcow2 file that you created and press `Open`. 

![s12](https://github.com/user-attachments/assets/a6099a6f-1dc9-4855-b60b-e8fc42368011)

13. When it finishes loading, drag the IDE Drive to the top of the Drives list and click `Save`.

![s13](https://github.com/user-attachments/assets/5ac4afa8-3419-470b-8a96-739f330f2ff7)
> Note that the IDE Drive must be at the top of the list or you won't be able to boot!

14. Start the VM. 
