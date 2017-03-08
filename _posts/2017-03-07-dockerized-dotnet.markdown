This blog started with one simple idea: I wanted to be able to write .Net Core code locally in VSCode but build and run the code within Docker. Doing so frees me as a developer from having to maintain .Net Core SDK and tooling compatibility between my development computer and the applications themselves. This walkthrough will show just how to do that.

To start off, let's first look at how far the current state of tooling will get you when writing a .Net Core web application and using yeoman's .Net Core/Docker scaffolding. This part is totally optional and does require you to download the latest .Net Core SDK (I'm using 1.1.1) and tooling (I'm using 1.0). This is just to give you context around how the solution started.

Folder structure

dotnet-docker-example
    src
    docker

Start by creating a asp.net core inside of src: dotnet new mvc -n dde-web
Then create a dotnet core library project inside of src: dotnet new  classlib -n dde-bl
Add a reference to the library project from the web project:         <ProjectReference Include="..\dde-bl\dde-bl.csproj" />
Add a little bit of code to the BL project add call it from the web project in order to make our debugging a little more interesting. (Add a static field).


Copy the following files into the 'docker' directory:
dockerTask.ps1
Dockerfile
