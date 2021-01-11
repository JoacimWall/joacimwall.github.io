## Simplify translation management by using the Multilingual Extension
In this previous article [Add multilingual support to Xamarin](https://joacimwall.github.io/#multilingual_support/) I show you how to add multilingual support to a Xamarin forms project. In this article I will show you how to use the [Multilingual Extension](https://github.com/JoacimWall/Visual-studio-multilingual-extension) for simplify the synchronization from the master file to different language files. 

We are going to use this extension to simplify ans solve four main problem.  
 * Synchronization of Resx files  
 * Translation of texts by Google translate or Microsoft translate  
 * Export of translations into csv or xlsx file for final translation by external stakeholder  
 * Import of final translations from external stakholder  

We will continue whit the same project as we started with in the previous article [Add multilingual support to Xamarin](https://joacimwall.github.io/#multilingual_support/)

[Source code of Demo](https://github.com/JoacimWall/Blog_Samples/tree/main/Add%20multilingual%20support%20to%20Xamarin)

### Install the extension
First we need to install the extension. below you will find the instructions for the different platforms. Remember to restart you visual studio after install for the extension to load.  

#### Install for Mac
The Visual studio for Mac team has closed the signup for new developers to publish extensions. So you need to download the latest release from this page then go to visual studio mac and click "install from file" in the Exstension Mananger.  
[Latest release](https://github.com/JoacimWall/Visual-studio-multilingual-extension/releases)

#### Install for Windows 
Go to Extension Manager and search for Multilingual Extension or Walltec and you will find it or use the link below.   
[Multilingual extension](https://marketplace.visualstudio.com/items?itemName=Walltec.MultilingualExtension)

### Setting the preferred property's for the extension. 
Select tools/multilingual settings in visual studio   
By default, this extension use Google's free translation. This is limited to only 100 translations per hour. To use the Microsoft translation service, select tools/multilangual settings in the visual studio and fill in the information from Microsoft. In this dialog you can also change the master language that is 'en' by default.
Here should you also select your preferd export format, csv or xslt.
If you also want to handle the status for the texts in the master resx file, check the 'Add Comment node to master Resx file on sync' in settings dialog.

<img width=“150” height="300" src="https://github.com/JoacimWall/Visual-studio-multilingual-extension/blob/main/Images/MultilingualSettingsDialog.png">

### Adding a new translation and synchronize
 There are two ways to sync the resx files. 
 Right-click the master file and select "Sync all .xx-x.resx files with this". Then all files that are in the same folder and follow the naming standard .xx-xx.resx  will be synchronized with the master file or,  
Right-click one of the language files (AppResources.fr-FR.resx) and select "Sync this .xx-x.resx file". This file will then be synchronized with the master file. 

<img width=“100” height="400" src="https://joacimwall.github.io/img/multilingual_extension/SyncAllFilePopUpDialog.png">
<img width=“100” height="400" src="https://joacimwall.github.io/img/multilingual_extension/SyncFilePopUpDialog.png">

the synchronization will not only add translations to the language files it will also remove translation that are not present in the master file.

So lets add a new translation "HTML is funny" into the master file this is easy done by just copy/past the last datanode from master file and change the name attribute and the value in the value filed.    



           
