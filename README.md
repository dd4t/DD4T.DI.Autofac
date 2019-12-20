
[![AppVeyor](https://ci.appveyor.com/api/projects/status/github/dd4t/DD4T.DI.Autofac?branch=master&svg=true&passingText=master)](https://ci.appveyor.com/project/DD4T/dd4t-di-autofac)

[![AppVeyor](https://ci.appveyor.com/api/projects/status/github/dd4t/DD4T.DI.Autofac?branch=develop&svg=true&passingText=develop)](https://ci.appveyor.com/project/DD4T/dd4t-di-autofac)

# dd4t-di-autofac

Autofac dependency injection container

## Release 2.5

- Upgraded reference to DD4T.Core
- Suppress warnings about obsolete methods in IComponentProvider


## How to 

1. Install Nuget package: `Install-Package DD4T.DI.Autofac` [http://www.nuget.org/packages/DD4T.DI.Autofac](http://www.nuget.org/packages/DD4T.DI.Autofac "DD4T.DI.Autofac")
2. Add `DD4T.DI.Autofac` namespace to your usings;
3. Call the `UseDD4T` method on your Autofac `Autofac.ContainerBuilder` class.

>     var builder = new ContainerBuilder();
>     //set all your custom apllication binding here.
>     builder.UseDD4T();
>     builder.Build();


UseDD4T will Register all default class provided by the DD4T framework.

If you need to override the default classes: (i.e. the DefaultPublicationResovler) Register your class before the method call `UseDD4T`

>     var builder = new ContainerBuilder();
>     //set all your custom apllication binding here.
>     builder.RegisterType<MyCustomPublicationResovler>().As<IPublicationResolver>().SingleInstance();
>     builder.UseDD4T();
>     builder.Build();
