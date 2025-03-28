# VM Guide for Neopets' Classic Games

<table>
<tr>
<td colspan="3" align="center"> <b>Operating System</b> </td>
</tr>
<tr>
  <td><a href="https://github.com/SpudMonkey7k/neopets-aio-vm/blob/main/README.md#windows">Windows</a></td><td><a href="https://github.com/SpudMonkey7k/neopets-aio-vm/blob/main/README.md#mac-os-intel">Mac OS Intel</a></td><td><a href="https://github.com/SpudMonkey7k/neopets-aio-vm/blob/main/apple-silicon.md">Mac OS Apple</a></td>
</tr>
</table>

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
>head to https://neopets.com/vsilogin.phtml (classic login page) to login. 
>> Note that you will need to disable your 2fa to login using classic login page. 

>[!Note]
>**NeoPass**
>
>In your default browser, like chrome:
>1. Open developer console.
>2. Write `document.cookie.split(';').find(c => c.includes('neologin')).trim()` in console, hit enter and you will see something like neologin=youruserxxxxx (don't show anyone this value!!!). 
>3. Then in Safari/SM visit neopets.com
>4. Open developer console and write `document.cookie = "yyy"` where yyy is what you got from chrome (neologin=youruserxxxxx).
>> in SM, you will need to press `ctrl + shift + i` or go to Tools > Web Development and select `Toggle Tools` to open developer console.
>>
>> in Safari, you will need to open `Preferences` then go to `Advanced` and check `Show Develop menu in menu bar` then press `ctrl + alt + c` to open developer console.
>5. Then refresh and you should be logged in.

## Windows

>[!IMPORTANT]
>Make sure to enable virtualization in bios before beginning.
>For Intel enable VT-x and for AMD enable AMD-V/SVM.
>Search guide for your computer/motherboard as it's different from computer to computer.

### Download
1. [VMware Workstation](https://www.vmware.com/products/workstation-player.html) or [VirtualBox](https://www.virtualbox.org/wiki/Downloads)
2. [Neopets VM](https://www.mediafire.com/file/wslhbasvmx1a3mz/Neo.ova/file)

**VMware Workstation**
1. Install and open VMware Workstation.
2. Select `Open a Virtual Machine`.
3. Browse to the `Neo.ova` file that you downloaded.
4. In the `Import Virtual Machine` window that opens, give the VM a name and indicate where you'd like to save it.
> default folder given after naming works fine.
5. After import is complete, you can select it from your VM list and click on `Play Virtual machine`.
>[!NOTE]
> 1. To close out the VM, in the VM, open start menu and click shutdown.
> 2. Whenever you want to start up the VM again, simply open VMware Workstation and repeat step 5 above.

**VirtualBox**
1. Install and open VirtualBox.
2. Click `Import` or from the menu bar select `File > Import Appliance`.
3. In the window that pop's up, click the folder button next to the file field.
4. Browse to the `Neo.ova` file that you downloaded.
5. Click `Finish`.
6. After import is complete, you can select it from your VM list and click `Start`.
>[!NOTE]
> 1. To close out the VM, in the VM, open start menu and click shutdown.
> 2. Whenever you want to start up the VM again, simply open VMware Workstation and repeat step 6 above.

## Mac OS Intel

### Download
1. [VMware Fusion](https://support.broadcom.com/group/ecx/productdownloads?subfamily=VMware+Fusion) or [VirtualBox](https://www.virtualbox.org/wiki/Downloads)
2. [Neopets VM](https://www.mediafire.com/file/wslhbasvmx1a3mz/Neo.ova/file)

**VMware Fusion** 
1. Install and open VMware Fusion.
2. From the menu bar select `File > Import`.
3. In the window that opens, click `Choose File` and browse to the `Neo.ova` file that you downloaded.
4. Click `Continue` then give the VM a name and indicate where you'd like to save it.
5. Click `Save`.
6. After import is complete, click `Finish to close the window and run the VM.
>[!NOTE]
> 1. To close out the VM, in the VM, open start menu and click shutdown.
> 2. Whenever you want to start up the VM again, simply open VMware Fusion, select the VM and click `Start Up`.

**VirtualBox** 
1. Install and open VirtualBox.
2. Click `Import` or from the menu bar select `File > Import Appliance`.
3. In the window that pop's up, click the folder button next to the file field.
4. Browse to the `Neo.ova` file that you downloaded.
5. Click `Finish`.
6. After import is complete, you can select it from your VM list and click `Start`.
>[!NOTE]
> 1. To close out the VM, in the VM, open start menu and click shutdown.
> 2. Whenever you want to start up the VM again, simply open VMware Workstation and repeat step 6 above.
