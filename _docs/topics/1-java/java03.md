---
title: Exercises
permalink: /docs/java03/
---

There are assorted pages in the **Reference** section of this website. These deal with using assorted applications and websites that we will be using in this module.  

These exercises will get you set up with Visual Studio Code and GitLab.
# Setting Up Visual Studio Code

We will be using Visual Studio Code (VSC or VSCode) to write, edit, debug and run our Java code. VSC is, at its heart, a text editor that can be extended in many different ways. It can be set up to work with many different programming languages by use of *Extensions*. We will be installing Extensions to allow VSCode to work with Java. These extensions will allow you to compile, debug and execute Java code. They will also help you manage Java projects and make it possible to work with GitLab from withing VSCode.  

## 1. Open VSCode

Where is it?

## 2. The VS Code Interface

The VSCode window will look something like this :-

![VSCode Interface](https://ysjprog02.netlify.app/assets/img/vscwindow-col.png)  

I've added coloured boxes to identify different areas of the interface.  

### <span style="color:red;">Menu Bar</span>

The menu bar is highlighted with a red box at the top of the window, it has menus.  

### <span style="color:yellow;">Editor Window(s)</span>

The majority of the window is taken up by the editor window(s). You can have multiple windows simultaneously. By defaul they appear in tabs, you can drag and drop tabs to tile windows.  

### <span style="color:cyan;">Icon Bar</span>/<span style="color:magenta;">Context Window</span>

The strip down the left hand side of the window (highlighted cyan above) is the Icon Toolbar. It can be used to switch between different modes in the Context Window (highlighted magenta) to the right of the Icon Bar. We will be mostly using three different modes.  

#### <span style="color:cyan;">Explorer</span>

The Explorer icon ![VSCode Explorer Icon](https://ysjprog02.netlify.app/assets/img/vscexplorer.png) is used to open the Explorer window in the context window. This is shown in the main image above. The Explorer Window allows you to navigate the folders and files of the current project.  

#### <span style="color:cyan;">GitLens</span>

The GitLens icon ![VSCode GitLens Icon](https://ysjprog02.netlify.app/assets/img/vscgitlens.png) is used to open the Git window in the context window. This is shown in below. The Git Window allows you to clone (download) git repositorys and upload your own code to your git repositories.  

![VSCode GitLens Window](https://ysjprog02.netlify.app/assets/img/vscgit.png)

#### <span style="color:cyan;">Extensions</span>

The Extensions icon ![VSCode GiExtensionstLens Icon](https://ysjprog02.netlify.app/assets/img/vscexticon.png) is used to open the Extensions window in the context window. This is shown in below. This window allows us to add and remove extensions, and to change their settings.    

![VSCode Extensions Window](https://ysjprog02.netlify.app/assets/img/vscextensions.png)  

This window is divided in to three sections. At the top of the window is a search bar that you can use to search for extensions. When you search for an extension the two sections below are replaced by the search results. If you wish to install an extension simply click on the blue **Install** button under the extension. You may need to reload after installing an extension.  

Below this is the **Installed** section that shows extensions which have been installed. You can access the settings for these extensions by clicking on the little cog icon next to them.  

The lower section shows recommended extensions. These are extensions that VSCode thinks you might find useful. Don't install them all, you don't need them.  

### <span style="color:blue;">Problems/Output/Terminal Window</span>

The window at the bottom of VSCode, below the editor windows, is used for output, debugging and the terminal. If any of these windows is not open/showing in the tabs, you can add them from the *View* menu.  

## 3. Install Extensions

1. Click on the Extension icon in the Icon toolbar. 
2. Install the following extensions
   * Extension Pack For Java
   * Test Runner for Java
   * Code Runner
   * PlantUML

**Extension Pack For Java** is a collection of extensions that will allow us to work with Java. **Test Runner for Java** will simplify running unit tests. **Code Runner** will make compiling and executing the code easier. **PlantUML** will allow us to make UML diagrams. We will be doing this later in the module.  

You may install any extensions you wish, just don't install too many or VSCode performance will suffer.  

## 4. Clone JavaHelloWorld Repository

Now we should be able to get some Java running. I've created a Java Hello World application and uploaded it to our GitLab server. You can use VSCode to download a copy of this programme to your machine and run it.  

1. Ensure you have no windows open in VSCode
2. Click the GitLens icon to open the Git/Source Control Window (shown below)

![VSCode Source Control Window](https://ysjprog02.netlify.app/assets/img/vsc-sc.png)  

3. Click the **Clone Repository** button
4. In the popup window enter the repository link [https://git.ysjcs.net:8888/a.guest/javahelloworld.git](https://git.ysjcs.net:8888/a.guest/javahelloworld.git) - you can type it in or copy and paste it, and press return.
![VSCode Source Control Window](https://ysjprog02.netlify.app/assets/img/vsc-cl-pop.png)  
5. Select a folder to clone the repository to. Note the process will create a folder called javahelloworld in the folder you select, so select the folder you want to keep all your code for this module in.  
6. Once the repository has been successfully cloned you should see a popup window appear. Click the **Open** button.
![VSCode Cloned](https://ysjprog02.netlify.app/assets/img/vsc-cloned.png)  
7. You should now see the window below. 
![VSCode Just Cloned](https://ysjprog02.netlify.app/assets/img/vsc-justcl.png)  
8. In the Explorer window click on **> src** to expand the src folder. Now click on **App.java** to view the code
![VSCode Hello World](https://ysjprog02.netlify.app/assets/img/vsc-hw.png)  
9. Press the play button to run the code (highlighted in the image above). You should see the **Output** window appear, looking something like the image below.
![VSCode Output](https://ysjprog02.netlify.app/assets/img/vsc-output.png)  


# Setting Up GitLab