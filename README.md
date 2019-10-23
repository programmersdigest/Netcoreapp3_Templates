# Netcoreapp3_Templates
Templates for *dotnet new* using netcoreapp3.0, C# 8.0, nullable reference types,
PublishTrimmed, etc.

For more information on the new features, see https://docs.microsoft.com/en-us/dotnet/core/whats-new/dotnet-core-3-0.

## Included templates

### .NET Core 3.0 Console Application

Usage

```console
dotnet new net3_console
```

A console application using .NET Core 3.0, C# 8.0, nullable reference types
(with warnings treated as errors), single file publishing and trimming.

Since single file publishing requires specifiing a single runtime identifier,
building and publishing the application requires the use of the *-r* flag:

```console
dotnet build -r linux-x64
dotnet publish -r linux-x64
```

PublishReadyToRun is included in the project file, but commented out. This is
because PublishReadyToRun does *not* support cross compilation and as such
requires building on the correct target platform (see
https://docs.microsoft.com/en-us/dotnet/core/whats-new/dotnet-core-3-0#readytorun-images).

### .NET Core 3.0 Class Library

Usage

```console
dotnet new net3_classlib
```

A class library using .NET Core 3.0, C# 8.0 and nullable reference types
(with warnings treated as errors).

Note: A class library generated in this way requires consuming applications to
be .NET Core 3.0 apps as well. There is *no compatibility* to older .NET Core
versions or .NET Framework. If you require compatibility, you should target .NET
standard 2.0 (by using the default *classlib* template).

## Building and installing

### Build

```console
git clone https://github.com/programmersdigest/Netcoreapp3_Templates.git
cd Netcoreapp3_Templates
dotnet pack
```

### Install

```console
dotnet new -i bin/Debug/programmersdigest.Netcoreapp3_Templates.1.0.0.nupkg
```

You can now find the templates in the template listing (output shortened):

```console
dotnet new

Templates                           Short Name
--------------------------------------------------
Console Application                 console
.NET Core 3.0 Console Application   net3_console
Class library                       classlib
.NET Core 3.0 Class Library         net3_classlib
```

### Uninstall

```console
dotnet new -u programmersdigest.Netcoreapp3_Templates
```