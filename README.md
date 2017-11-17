[![Chat on Gitter](https://img.shields.io/gitter/room/fody/fody.svg?style=flat)](https://gitter.im/Fody/Fody)
[![NuGet Status](http://img.shields.io/nuget/v/ModuleInit.Fody.svg?style=flat)](https://www.nuget.org/packages/ModuleInit.Fody/)


## This is an add-in for [Fody](https://github.com/Fody/Fody/) 

![Icon](https://raw.github.com/Fody/ModuleInit/master/package_icon.png)

Adds a module initializer to an assembly.

[Introduction to Fody](http://github.com/Fody/Fody/wiki/SampleUsage)


## The nuget package

https://nuget.org/packages/ModuleInit.Fody/

    PM> Install-Package ModuleInit.Fody


## What it does 

Based on Einar Egilsson's suggestion using cecil to create module initializers [http://tech.einaregilsson.com/2009/12/16/module-initializers-in-csharp/]


### Finds a class, in the target assembly, named 'ModuleInitializer' with the following form.

```
public static class ModuleInitializer
{
    public static void Initialize()
    {
        //Init code
    }
}
```


### Injects the following code into the module initializer of the target assembly. This code will be called when the assembly is loaded into memory

```
static <Module>()
{
    ModuleInitializer.Initialize();
}
```


## Icon

Icon courtesy of [The Noun Project](http://thenounproject.com)