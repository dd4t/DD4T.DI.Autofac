# DD4T.DI.Autofac

Autofac dependency injection container

## Release 2.6

- Upgraded reference to DD4T.Core to 2.6.1
- Upgraded reference to Autofac to 8.2.0

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
