# Rothko

We all know the .NET Framework APIs for dealing with the file system are not 
designed with testability in mind. Also, I wasn't happy with the existing 
libraries for providing an abstraction for such things. I wanted one that was:

* Modern - Included the `Enumerate*` methods for example.
* Interface based - Using Abstract base classes as the abstraction is blech.
* Easy to port to - So it had to follow the existing APIs closely.

Rothko is this library. It provides abstractions for:

* File system.
* Registry
* Environment.

The starting point for Rothko is the `ISystem` interface. From there 
you can get to the other abstractions.

* `IFileSystem`
* `IEnvironment`
* `IRegistry`

# Goals

The goal is to use this in GitHub for Windows as well as any other libraries 
in which testability is important.

A secondary goal is to make it very easy to port code using the core .NET 
Framework APIs to port over to Rothko. The interfaces are very close to the 
Framework's, except in a few plases where I wouldn't be able to live with 
myself if I didn't modernize the library. For example, I updated methods 
that return arrays to return `IEnumerable` (or derived interface) instead.