# Understanding .NET Assemblies: Class Libraries vs. Executable Assemblies

## Class Library Assemblies
- **Purpose**: Contain reusable code (e.g., classes, methods) without an entry point.
- **Entry Point**: No `Main` method.
- **Execution**: Not directly executable; must be referenced by another application.
- **Use Case**: Shared functionality (e.g., utility libraries, algorithms).
- **Reference**: [Class Libraries Documentation](https://learn.microsoft.com/en-us/dotnet/standard/class-libraries)

## Executable Assemblies
- **Purpose**: Contain complete application logic with an entry point.
- **Entry Point**: Contains a `Main` method.
- **Execution**: 
  - On Windows, usually built as an **.exe**.
  - In cross-platform .NET (e.g., .NET Core, .NET 5+), may be built as a **.dll** and run using the `dotnet` CLI (e.g., `dotnet app.dll`).
- **Use Case**: Represents the entire application code—covering any type of .NET application (console, GUI, web, etc.).
- **Reference**: [Create a .NET App](https://learn.microsoft.com/en-us/dotnet/core/tutorials/)

## Summary
- **Class Library Assemblies**: Reusable code without an entry point; not directly executable.
- **Executable Assemblies**: Application assemblies with an entry point, capable of running as standalone applications regardless of type.

---

## Sources
- **Class Libraries**: [Class Libraries Documentation](https://learn.microsoft.com/en-us/dotnet/standard/class-libraries) – Official Microsoft documentation on class libraries.
- **Executable Assemblies**: [Create a .NET App](https://learn.microsoft.com/en-us/dotnet/core/tutorials/) – Guides on building various types of .NET applications.
- **Cross-platform Executable Assemblies**: [Framework-dependent deployment in .NET Core](https://learn.microsoft.com/en-us/dotnet/core/deploying/#framework-dependent-deployment) – Explains how applications are deployed as DLLs and executed using the `dotnet` CLI.
- **Introduction of Cross-platform DLLs**: [Announcing .NET Core 1.0](https://devblogs.microsoft.com/dotnet/announcing-net-core-1-0/) – Official announcement detailing the cross-platform model introduced in .NET Core.
- https://learn.microsoft.com/en-us/troubleshoot/windows-client/setup-upgrade-and-drivers/dynamic-link-library
- https://www.illumio.com/blog/exe-vs-dll-assemblies
- https://learn.microsoft.com/en-us/dotnet/standard/assembly/
- https://stackoverflow.com/questions/72071033/difference-between-console-application-dll-and-class-library-dll
- https://medium.com/the-crazy-coder/c-assembly-exe-and-dll-d871b9e77829
- https://clarionhub.com/t/difference-and-use-of-lib-vs-dll/4350
- https://www.vbforums.com/showthread.php?198180-Difference-between-a-DLL-and-EXE-file=
---

## How to Download This Markdown File
1. **Copy the content** above.
2. **Paste into a text editor** (e.g., Notepad, VS Code).
3. **Save the file** with a `.md` extension (e.g., `README.md`).

Alternatively, if your browser supports it, right-click on the text, choose "Save As," and save the file as markdown.
