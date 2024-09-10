ASP .NET Core Project Template
ASP .NET Core Project Template for GSA FM IT team. Every one should be able to use this templae to build a ASP .NET Core web app with PostgreSQL database and beautifully looking U.S. Web Deisgn Standard UI.

Key Functions
Landing page design with U.S. Web Deisgn System 2.
Cross-platform.
Sing-in pgae exmaple.
Getting Started
These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. See deployment for notes on how to deploy the project on a live system.

Prerequisites
Visual Studio 2022 or higher
.NET 6.x SDK
Npgsql.EntityFrameworkCore.PostgreSQL 2.1.1.1 (https://www.nuget.org/packages/Npgsql.EntityFrameworkCore.PostgreSQL/)
Installing
Download and copy to \My Documents\Visual Studio 2017\Templates\ProjectTemplates folder.
Using the Template for a New Project
Launch Visual Studio 2019 and create a new project. Use the "ASP.NET Core Web Application" template (C#). Use a unique name for the new project.
In the "Create a new ASP.NET Core web application" window, select ".NET Core" and "ASP.NET Core 3.1" in the dropdown menus. Choose the "Empty" project type and Check the "Configure for HTTPS" box. Click "Create".
Once the project has been created, close Visual Studio.
Clone this repository to a new folder.
Remove all of the files and folders from within your project's web root. This includes the following:
bin/
obj/
Properties/
appsettings.Development.json
appsettings.json
Program.cs
Startup.cs
Copy all files and folders from this repository's 2nd ASP Core MVC Template subdirectory and paste them into the same location within your own project. You're replacing all of the files you removed in the previous step.
Rename the ASP Core MVC Template.csproj file to your own project's name. Edit it with an app like Notepad and make the following changes:
Replace the <RootNamespace> value with your project's namespace.
Rename the ASP Core MVC Template.csproj.user file to your own project's name.
Rename the ASP_CORE_MVC_Template_appsettings_Example.json file to <YOURPROJECT>_appsettings.json.
Copy <YOURPROJECT>_appsettings.json to the folder you assigned to the APPSETTINGS_DIRECTORY environment variable (as described earlier in this readme).
Edit AssemblyInfo.cs as follows:
Replace the RootNamespace value with your project's namespace.
Edit Program.cs as follows:
Change namespace ASP_Core_MVC_Template to namespace <YOURPROJECTNAMESPACE>
Change config.AddJsonFile("ASP_Core_MVC_Template_appsettings.json") to config.AddJsonFile("<YOURPROJECT>_appsettings.json")
Edit Startup.cs as follows:
Change namespace ASP_Core_MVC_Template to namespace <YOURPROJECTNAMESPACE>
Change options.Cookie.Name = ".Core-Web-Template.Session"; to options.Cookie.Name = ".<YOURPROJECT>.Session";
Change loggerFactory.AddFile(logDirectory + "/Core-Web-Template-{Date}.log"); to loggerFactory.AddFile(logDirectory + "/<YOURPROJECT>-{Date}.log");
Change app.UsePathBase("/core-web"); to app.UsePathBase("/<yourproject>"); (make sure you preserve all lowercase for this change!)
Remove all bin\Debug\netcoreapp3.1\ASP Core MVC Template.* files.
Edit Controllers\HomeControler.cs as follows:
Change using ASP_Core_MVC_Template.Models; to using <YOURPROJECT>.Models;
Change namespace ASP_Core_MVC_Template.Controllers to namespace <YOURPROJECTNAMESPACE>.Controllers
If using AppStatus functionality from CAAM, change _configService.GetAppClosed("CORE_TEMPLATE"); to _configService.GetAppClosed("<YOURPROJECT>");
If using AppStatus functionality from CAAM, change _configService.GetAppWarning("CORE_TEMPLATE"); to _configService.GetAppWarning("<YOURPROJECT>");
If using roles from CAAM, edit the [Authorize(Roles = "COREADMIN,COREUSER")] line to use roles that are applicable to your project.
Edit Controllers\LoginControler.cs as follows:
Change namespace ASP_Core_MVC_Template.Controllers to namespace <YOURPROJECTNAMESPACE>.Controllers
If using roles from CAAM, edit _dataAPIService.GetCAAMRoles("Core Template" to _dataAPIService.GetCAAMRoles("<YOURPROJECT>"
Edit Models\ErrorViewModel.cs as follows:
Change namespace ASP_Core_MVC_Template.Models to namespace <YOURPROJECTNAMESPACE>.Models
If using roles from CAAM, edit Views\Home\LoggedIn.cshtml as follows:
Change Context.User.IsInRole("COREADMIN") to use a role applicable to your project.
Edit Views\Home\Warning.cshtml as follows:
Change <title>Warning - CAAM Web Template</title> to <title>Warning - <YOURPROJECT></title>
Edit Views\Shared\_Layout.cshtml as follows:
Change @ViewData["Title"] - Core Web Template to @ViewData["Title"] - <YOURPROJECT>
Change aria-label="Home">Core Web Template to aria-label="Home"><YOURPROJECT>
Edit Views\_ViewImports.cshtml as follows:
Change both instances of @using ASP_Core_MVC_Template to @using <YOURPROJECT>
