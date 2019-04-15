---
title: Server-side Blazor
page_title: First Steps with Server-side UI for Blazor
description: First Steps with UI for Blazor Server-side
slug: getting-started/server-side
tags: get,started,first,steps,server
published: true
position: 1
---

# First Steps with Server-side UI for Blazor

This article explains how to get the Telerik UI for Blazor components in your **Server-side** Blazor project and start using them quickly. The process consists of the following steps:

1. [Set Up a Blazor Project](#set-up-a-blazor-project)
1. [Add the Telerik NuGet Feed to Visual Studio](#add-the-telerik-nuget-feed-to-visual-studio)
1. [Add the Telerik Components to Your Project](#add-the-telerik-components-to-your-project)
1. [Add a Telerik Component to a View](#add-a-telerik-component-to-a-view)

@[template](/_contentTemplates/common/get-started.md#add-latest-ms-bits-server-side-link)


@[template](/_contentTemplates/common/get-started.md#add-nuget-feed)


## Add the Telerik Components to Your Project

To use Blazor server-side, you need to use the `Razor Components` type of project.
@[template](/_contentTemplates/common/get-started.md#project-creation-part-1)

1. Choose the `Razor Components` project type and click `Create`.

    ![Select Blazor Project Type](images/choose-project-template-server-blazor.png)


### Add to Existing Project

@[template](/_contentTemplates/common/get-started.md#get-access)

    1. Right-click on the project in the solution and select `Manage NuGet Packages`:
    
       ![](images/manage-nuget-packages-for-server-app.png)
    
    1. Choose the `telerik.com` feed, find the `Telerik.UI.for.Blazor` package and click `Install`:
    
         ![Add Telerik Blazor Package to the project](images/add-telerik-nuget-to-server-app.png)

1. Open the `~/Components/_ViewImports.cshtml` file and add the following line to register the Telerik components for all component files:

    **CSHTML**
    
        @addTagHelper *,Telerik.Blazor
        
1. Open the `~/Pages/Index.cshtml` and register the [Theme stylesheet]({%slug general-information/themes%}) (note the escaping for the `@` symbol):

    **HTML**
    
        <link id="kendoCss" rel="stylesheet" href="https://unpkg.com/@@progress/kendo-theme-default@@latest/dist/all.css" />

    
Now your project can use the Telerik UI for Blazor components in all its component files.

## Add a Telerik Component to a View

The final step is to actually use a component on a view and run it in the browser. For example:

1. **Add** a **Button** component to the `~/Components/Pages/Index.cshtml` view:
@[template](/_contentTemplates/common/get-started.md#add-component-sample)

## See Also

* [Get Started with Client-side Blazor]({%slug getting-started/client-side%})
* [Telerik Private NuGet Feed]({%slug installation/nuget%})