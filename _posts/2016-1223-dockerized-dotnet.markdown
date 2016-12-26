Folder structure

root
    src
        web.server
        bl

Start by creating a asp.net core inside of web.server: dotnet new -t web
Switch to bl layer and create a dotnet core library project: dotnet new -t lib
Add a reference to the library project from the web project:     "bl" : "1.0.0-*"
