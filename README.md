## What is the Universal Windows Platform

> An Universal Windows Platform (UWP) app is a Windows experience that is built upon the UWP, which was first introduced in Windows 8 as the **Windows Runtime**. At the core of UWP apps is the idea that users want their _experiences_ to be mobile across ALL their devices, and they want to use whatever device is most convenient or productive for the task at hand.
> 
> [More on the official MSDN documentation](https://msdn.microsoft.com/en-us/windows/uwp/get-started/whats-a-uwp)

## Introduction to Universal Apps development

In order to pass on the legacy, the first example you learn to code when you are introduced to a new programming language or concept is the [Hello World](https://en.wikipedia.org/wiki/%22Hello,_World!%22_program). To set your development enviorment, you will need to download [Visual Studio Community edition](https://www.visualstudio.com/) and install the Universal Platform SDK, as described [here](https://msdn.microsoft.com/en-us/windows/uwp/get-started/get-set-up).

We will start by creating a basic universal app project. To do this we go to **File > New > Project...**, we select **Blank App (Universal Windows)**. We can change the .NET Framework target, include Application Insights into our project and create a new Git repository from the project. We then specify the project and solution names and also the location to which we want to store it.

![01](https://laurentiu.microsoft.pub.ro/wp-content/uploads/sites/3/2016/04/01.png)

## The project explained

<table>
<tr valign="top">
<td><img src="https://laurentiu.microsoft.pub.ro/wp-content/uploads/sites/3/2016/04/01-1.png" alt="01" width="445" height="428" /></td>
<td>
<strong>Properties</strong>: Information about the project (version, copyright etc.)
<br>
<strong>References</strong>: A list of all your dependencies in form of NuGet packages
<br>
<strong>Assets</strong>: Default folder (can be changed) for storing visual assets of your app (splash screen, app icon, store logo icon etc.)
<br>
<strong>App.xaml</strong>/<strong>App.xaml.cs</strong>: The main entry point where you configure which page to load when the app is opened
<br>
<strong>App_TemporaryKey.pfx</strong>: Used for publishing to the Windows store (not covered in this post)
<br>
<strong>MainPage.xaml</strong>: User interface implementation of a page (in this case, the main page)
<br>
<strong>MainPage.xaml.cs</strong>: Backend implementation of a page (in this case, the main page)
<br>
<strong>Package.appxmanifest</strong>: A file which describes your app (app name, capabilities etc.)
<br>
<strong>project.json</strong>: The file which stores a list of all the NuGet packages your application needs to have in order to function.
</td>
<tr>
</table>

## What is XAML?

> Extensible Application Markup Language (XAML) is a declarative language that can initialize objects and set properties of objects, using a language structure that shows hierarchical relationships between multiple objects, and using a backing type convention that supports extension of types. XAML has a basic syntax that builds on XML. By definition, valid XAML must also be valid XML.
> 
> [More on the official MSDN documentation](https://msdn.microsoft.com/en-us/windows/uwp/xaml-platform/xaml-overview)
If you are familiar with XML or have ever modified (or viewed) a HTML page, be it for a project or assignment, you will learn XAML very quickly.

## The code - MainPage.xaml

The [Page](https://msdn.microsoft.com/en-us/library/windows/apps/windows.ui.xaml.controls.page.aspx) element is **mandatory** in order for the file to be recognized as the content of the window [Frame](https://msdn.microsoft.com/en-us/library/windows/apps/windows.ui.xaml.controls.frame).

The [Grid](https://msdn.microsoft.com/en-us/library/windows/apps/windows.ui.xaml.controls.grid.aspx) element serves as the **root element** in the page. The root element is not required by default, nor it has to be a Grid (it can be anything, as long as it derives from the [Panel](https://msdn.microsoft.com/en-us/library/windows/apps/windows.ui.xaml.controls.panel) class) but only one root element can exist in a page.

The [TextBlock](https://msdn.microsoft.com/en-us/library/windows/apps/windows.ui.xaml.controls.textblock.aspx) element serves as a text container (:information_source:  unlike HTML, text cannot be randomly written inside the document, it has to be contained inside a tag). We can make use of the powerfull [Visual C# IntelliSense](https://msdn.microsoft.com/en-us/library/43f44291.aspx) and style our "Hello Universe" text however we want to.

## The code - Main.xaml.cs

**Namespaces** can be described as the playground of your application. Namespaces are a way to group related classes and help you organize them. Now that we have a way to group related classes, we need a way to include them, hence the **using** keyword (it has the same function as **import** in Java or **#include** in C/C++).

As you now observed, every XAML UI element is a class implemented in the **.NET Framework**. The MainPage inherits the properties of a base page in order to know how to interact with the main window. Without the power of C#, the Universal Windows Platform can't exist. In the constructor of the MainPage class, we initialize the components used by the user interface.

## Running the application

We are now ready to build, deploy and run our app. We go to **Debug > Start debugging** or press **F5** on our keyboard. After it builds and deploys successfully, you should see the following window pop-up

![01](https://laurentiu.microsoft.pub.ro/wp-content/uploads/sites/3/2016/04/01-2.png)

Eureka, it works. The two black boxes are enabled by default if you build with in the "Debug" environment and are used for profiling and quick live editing when the application is running (:information_source: the quick live editing box is added in the new Visual Studio Community Update 2) .

## In conclusion

As you may have observed, no C# coding knowledge is required create a basic "Hello World" app in the Universal Windows Platform, it's as simple as File > New > Project. For a better understanding of how powerful the C# language really is, you can check out [this repository](https://github.com/microsoft-dx/csharp-fundamentals/) full with basic C# projects.

So there you have it, these are your first steps in UWP app development. Stay tuned on [this blog](https://laurentiu.microsoft.pub.ro/) (and star the [microsoft-dx organization](https://github.com/microsoft-dx/)) to emerge in the beautiful world of "there's an app for that".
