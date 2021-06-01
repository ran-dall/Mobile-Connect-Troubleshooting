# Dell / Alienware Mobile Connect 📲 Troubleshooting

⛔ ***Disclaimer: I'm not affiliates with Dell or Alienware in any way. Everything provided here is openly available on a wide-array of websites.***

## 📜 Background Story

Recently, I was helping a friend hook up set up an old Alienware Laptop to sync from his phone, however we were having trouble downloading the app from the Microsoft Store. After doing some digging, I found a lot of really helpful information that was able to fix it. However, before getting rid of everything, I decided to complied that information here in a more usable form, for the easy use of anyone that is having problem downloading either Dell Mobile Connect or Alienware Mobile Connect.

## 🗃 Files

📝 NOTE: The values provided in these files are simply there for demonstration purposes, but they do work if you specifically want to install **Alienware Mobile Connect**.

`Install_Registry_Requirements.reg` - This file will merge all the required Registry Requirements needed to install Mobile Connect. You will want to update your `Manufacturer` to either `DELL` or ``ALIENWARE`; and `Model` to whatever your model is. 

`Delete_Nonrequired_Registry_Requirements.reg` - This file will delete any previously merged Registry Requirements that are not needed for the continued operation of Mobile Connect. You will want to update these file with the same values you used for `Manufacturer` and `Model` in `Install_Registry_Requirements.reg`.

`Clean_Registry.reg` - This file will clean out all the Registry Requirements that have been merged into your Computer's Registry. You will want to update these file with the same values you used for `Manufacturer` and `Model` in `Install_Registry_Requirements.reg`.

`Add_SCMID_RegEdit_for_DMC.bat` - This Batch File contains [a script suggested by Alienware Forum Moderator `Alienware-Eimy` in Dell's Community Forum](https://www.dell.com/community/Alienware/15-R4-mobile-connect-Microsoft-store-download/m-p/7331091/highlight/true#M22653). 

## 🔌 Use

### ⚙ Batch Script
If you're trying to fix a legitimate Dell, Alienware, Dell XPS, or Dell Vostro model machine, then this might be your best bet. Personally, I have not tested it.  However, I don't see anything wrong with using it. Many users have reported success with it.

### 📃 Registry Merging
Start with modifying `Install_Registry_Requirements.reg`, `Delete_Nonrequired_Registry_Requirements.reg`, and `Clean_Registry.reg`. You will want to update your `Manufacturer` to either `DELL` or ``ALIENWARE`; and `Model` to whatever your model is. You can find your model using the following command in PowerShell or Command Prompt: `> wmic computersystem get model /format:list`.

Once you modified the Registry files, merge `Install_Registry_Requirements.reg` into the Computer's Registry, and restart your computer. Once it has restarted, you should be able to download the version of Mobile Connect that's apt for your computer model.

If you want to remove your model information after installing Mobile Connect, you can do so merging `Delete_Nonrequired_Registry_Requirements.reg`. Remove this will no prevent you from using Mobile Connect.

If you uninstalled Mobile Connect and will no longer use it, or simple just want to get rid of all orphaned Registry Entries created this workaround needed by Mobile Connect then you can do so merging  `Clean_Registry.reg`. Removing this will prevent you from using Mobile Connect and disable it again in the store. You can re-enable it in the store merging `Install_Registry_Requirements.reg` again.

## 📚 Resources
- https://www.dell.com/community/Alienware/15-R4-mobile-connect-Microsoft-store-download/m-p/7331091/highlight/true#M22653
- https://www.dell.com/community/Productivity-Software/Alienware-mobile-connect/m-p/6135831/highlight/true#M37570