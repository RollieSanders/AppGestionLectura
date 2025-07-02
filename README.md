# AppGestionLectura
Inicializa la Solución (.sln):
===============================

dotnet new sln

Crea el Proyecto de Dominio
===============================
dotnet new classlib --name AppGestionLectura.Domain --output src/AppGestionLectura.Domain

Agrega este proyecto a la solución:
dotnet sln add src/AppGestionLectura.Domain/AppGestionLectura.Domain.csproj

Crea el Proyecto de Aplicación
==============================
dotnet new classlib --name AppGestionLectura.Application --output src/AppGestionLectura.Application

Agrega este proyecto a la solución:
dotnet sln add src/AppGestionLectura.Application/AppGestionLectura.Application.csproj

Crea el Proyecto de Infraestructura
====================================
dotnet new classlib --name AppGestionLectura.Infrastructure --output src/AppGestionLectura.Infrastructure

Agrega este proyecto a la solución:
dotnet sln add src/AppGestionLectura.Infrastructure/AppGestionLectura.Infrastructure.csproj


Crea el Proyecto Blazor Web App (Capa de Presentación):
dotnet new blazor --interactivity Auto --name AppGestionLectura.Presentation --output src/AppGestionLectura.Presentation

Agrega el Proyecto Blazor a la Solución:
dotnet sln add src/AppGestionLectura.Presentation/AppGestionLectura.Presentation/AppGestionLectura.Presentation.csproj

Establecer Referencias entre Proyectos
Presentation depende de Application:

dotnet add src/AppGestionLectura.Presentation/AppGestionLectura.Presentation/AppGestionLectura.Presentation.csproj reference src/AppGestionLectura.Application/AppGestionLectura.Application.csproj

Application depende de Domain:
dotnet add src/AppGestionLectura.Application/AppGestionLectura.Application.csproj reference src/AppGestionLectura.Domain/AppGestionLectura.Domain.csproj

Infrastructure depende de Domain (y posiblemente de Application si implementa interfaces de Application, aunque es más común que solo implemente interfaces de Domain):
dotnet add src/AppGestionLectura.Infrastructure/AppGestionLectura.Infrastructure.csproj reference src/AppGestionLectura.Domain/AppGestionLectura.Domain.csproj
