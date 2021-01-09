## Add multilingual support to Xamarin
In this article I will show you how to add multilingual support to a Xamarin forms project. We will use standard Resources files to handle the different languages and in part 2 I will show you how to use the [Multilingual Extension](https://github.com/JoacimWall/Visual-studio-multilingual-extension) for simplify the synchronization from the master file to different language files. 

### Lets get started
Screenshots in this article is from Visual Studio For Mac but the process is the same for the Windows version of Visual Studio.  Create a Xamarin project by select the template "Blank Forms App"
I will name this app MLDemo and press Next and then create in the next dialog.
![Screenshot](img/multilingual_support/create_project.png)

Now lets create a new folder named Resources then right click and add a new Resources file to that folder named AppResources and press new.
![Screenshot](img/multilingual_support/add_appresoruce_file.png)

Now you should have project structure and a AppResources.resx file looking like this. This resx file is you master language file and it's from this file we will synchronize the translations to the other languages files files. If you created the resx file on Windows computer you will also se the xsd part of the file this is the rolls for the resx file like that you are not allowed to att to data filed with the same name. On mac you will not get this validations. 

![Screenshot](img/multilingual_support/project_structure_1.png)

Set the natural language of you app by right click the shared project and select options. then under MetaData/details select English or other preferred language that reflect you master file. In this demo I select English (United States).   
![Screenshot](img/multilingual_support/select_natural_language.png)

To support two more language lets add two more resx files. In this sample we are going to support French and Spanish. When we add this files we will use a naming convention that include both the country code and language this is needed if you should support both French in France(Resources.fr-FR.resx) and French in Canada (Resources.fr-CA.resx).  

Now we are going to add two files to the folder Resources
AppResources.fr-FR.resx for French
AppResources.es-ES.resx for Spanish

Important is that we keep the same name as the master resx file in this case AppResources.resx.

For a list of culture codes see [language codes](https://github.com/JoacimWall/Visual-studio-multilingual-extension).

For the intellisense to work the master file needs a AppResources.Designer.cs file. Under property's change Custom Tool to PublicResxFileCodeGenerator. I like to remove the Designer.cs file for the other language files to keep it cleaner as you se in the MLDemo.csproj file.  

![Screenshot](img/multilingual_support/project_file_no_design_files.png)


## Now lets add some translations
In the master file (AppResources.resx) we add the data block. Where the "name" attribute is what we are going to use when i reference it in code.
In the value tag we write the sentence.
We do the same for the French and Spanish file But we replace the text in the value filed with translated text in French and Spanish.      
![Screenshot](img/multilingual_support/add_translation_to_resfiles.png)

To use the translation in c# files or from you xaml files you just build one time and the AppResources.Designer.cs will be created.  

To get the translation in C# you just use this statement.  

var translation = MLDemo.Resources.AppResources.C_Sharp_Is_Love; 
    
And from xaml 

You add the namespace and then bind the text in the label.  
![Screenshot](img/multilingual_support/xaml_code.png)

In the next Article i will show how to simplify management of synchronize and auto translation with Google or Microsoft services using [Multilingual Extension](https://github.com/JoacimWall/Visual-studio-multilingual-extension).

           
