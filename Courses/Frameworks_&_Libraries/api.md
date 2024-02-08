# API with ASP .NET

A few tips that could be useful when **making a REST API with ASP .NET.** <br>
I made mine **with a React application** for the client side. I added a few commands about how to create that.

## API startup commands 
*(That section will be deleted on later versions).*

Here are a few commands that helped me to start the project. 

After the creation of a folder. **Add a solution** (sln is the name of a template):
```bash
dotnet new sln --name <SolutionName>
```

**Add a project** (webapi is the name of a template):
```bash
dotnet new webapi --name <ProjectName>
```

Add the project to the solution (link both):
```bash
dotnet sln add <./ProjectName/ProjectName.csproj>
```

Add a special gitignore for dotnet/visual studio files:
```bash
dotnet new gitignore
```

**Add a react project** (inside the api project):
```bash
npx create-react-app client-app
```