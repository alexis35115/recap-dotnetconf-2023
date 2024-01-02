# Récapitulatif de la conférence .NET Conf 2023

## .NET Aspire

.NET Aspire is an opinionated, cloud ready stack for building observable, production ready, distributed applications. .NET Aspire is delivered through a collection of NuGet packages that handle specific cloud-native concerns. Cloud-native apps often consist of small, interconnected pieces or microservices rather than a single, monolithic code base. Cloud-native apps generally consume a large number of services, such as databases, messaging, and caching.

Session : <https://devblogs.microsoft.com/dotnet/introducing-dotnet-aspire-simplifying-cloud-native-development-with-dotnet-8/>
Démonstration de Nick Chapsas : <https://www.youtube.com/watch?v=HYe6y1kBuGI>
La différence avec Dapr : <https://www.youtube.com/live/xEFO1sQ2bUc?si=at6qBm8-Zm49nJKE&t=32511>
Fin du projet Tye : <https://github.com/dotnet/tye/issues/1622>

## Visual Studio 22 version 17.8

Session : <https://www.youtube.com/live/vU-iZcxbDUk?si=pYS5GzYZjh_d5-1G&t=16251>

- Scaffolding - <https://www.youtube.com/live/vU-iZcxbDUk?si=4xna7j0ATBVxTcvo&t=16917>
- Utilisation des secrets dans les fichiers `.http` - <https://www.youtube.com/live/vU-iZcxbDUk?si=9dM3iPbeRjoaX9HM&t=17679>

Blog : <https://devblogs.microsoft.com/visualstudio/visual-studio-17-8-now-available/>

Ui fresh pour la version 17.9 à venir : <https://devblogs.microsoft.com/visualstudio/the-visual-studio-ui-refresh-preview-is-here/>

## .NET 8 et C# 12

Blog : <https://devblogs.microsoft.com/dotnet/announcing-dotnet-8/>, <https://devblogs.microsoft.com/dotnet/announcing-csharp-12/> et <https://learn.microsoft.com/fr-fr/dotnet/core/whats-new/dotnet-8>

Notons que cette version est la nouvelle LTS et aura un support de 3 ans

Nouvelles fonctionnalités :

- Présentation des différentes nouvelles fonctionnalités C# 12 - <https://www.youtube.com/watch?v=Gv2uBJzBAms>
  - [Primary constructor](https://www.c-sharpcorner.com/blogs/primary-constructors-in-c-sharp-12#:~:text=A%20Primary%20Constructor%20is%20a%20new%20feature%20in,and%20makes%20your%20code%20more%20concise%20and%20readable.) - C'est le même principe pour les `record`, il faut faire attention, pour le moment, la notion de "readonly" n'existe pas et plusieurs recommandent d'utiliser seulement cette fonctionnalité dans les classe où __on n'utilise pas l'injection de dépendance__.
- Mise à jour des data annotation - <https://www.youtube.com/watch?v=SCDiuvK-GI8>
- Meilleur manière de rechercher une valeur - <https://www.youtube.com/watch?v=IzDMg916t98>
- Introduction des keyed services - <https://www.youtube.com/watch?v=mTRvRZmlHT4> et <https://www.youtube.com/watch?v=vU-iZcxbDUk&t=8114s>
  - Ça règle cette problématique <https://stackoverflow.com/questions/60937827/net-core-keyed-dependency-injection>
- Adds Shuffle to Random for Arrays and Spans - <https://www.youtube.com/watch?v=hsrfLtu_cVk>
- Ajout d'un [TimeProvider](https://learn.microsoft.com/en-us/dotnet/api/system.timeprovider?view=net-8.0) et d'une classe pour abstraire la date dans les tests [FakeTimeProvider](https://learn.microsoft.com/en-us/dotnet/api/microsoft.extensions.time.testing.faketimeprovider?view=dotnet-plat-ext-8.0), voici un exemple d'utilisation <https://www.roundthecode.com/dotnet-tutorials/timeprovider-easier-mock-time-dotnet-8>.
  - Plus besoin de faire une abstraction maison, on peut probablement s'attendre qu'à l'interne de Microsoft ils fond pareil, on a vu avec le temps plusieurs initiatives dans plusieurs secteurs.

La liste est exhaustive, idéalement, il faut lire les "blogs".

Les breaking changes <https://learn.microsoft.com/en-ca/dotnet/core/compatibility/8.0?toc=%2Fdotnet%2Ffundamentals%2Ftoc.json&bc=%2Fdotnet%2Fbreadcrumb%2Ftoc.json>.

### Blazor et ASP.NET Core

Blog : <https://devblogs.microsoft.com/dotnet/announcing-asp-net-core-in-dotnet-8/>

Nouvelles fonctionnalités :

- SignalR reconnect - <https://www.youtube.com/live/vU-iZcxbDUk?si=YNQJVV0QqzMDQ-mz&t=7352>
- Building resilient cloud services with .NET 8 (wrapper par dessus Polly) - <https://devblogs.microsoft.com/dotnet/building-resilient-cloud-services-with-dotnet-8/>
- Blazor - SSR, Stream Rendering, Auto, and more - <https://www.youtube.com/watch?v=walv3nLTJ5g>
- Open Telemetry - <https://www.youtube.com/live/vU-iZcxbDUk?si=HKo6UXyps5TUOkrL&t=2211>
- Antiforgery partout et non seulement MVC - <https://www.youtube.com/live/vU-iZcxbDUk?si=dHFlrgOIUXk9mAXF&t=7801>
- Request timeout policy - <https://www.youtube.com/live/vU-iZcxbDUk?si=EL7MCioUeSq8SbaD&t=7892>
- Ajouter du nouveau IExceptionHandler - <https://www.youtube.com/live/vU-iZcxbDUk?si=ixSGmKjtZ5sggL5a&t=8670> et <https://www.youtube.com/watch?v=uOEDM0c9BNI>
- System.Text.Json string as enum value - <https://www.youtube.com/live/vU-iZcxbDUk?si=n-oaDGwiTq-0Us2H&t=9333>
- Bonification de System.Text.Json dans un contexte AoT - <https://www.youtube.com/live/vU-iZcxbDUk?si=4hu0Or7kjM8f5FYz&t=9440>, <https://www.youtube.com/live/vU-iZcxbDUk?si=n-oaDGwiTq-0Us2H&t=9333> et <https://www.youtube.com/watch?v=vU-iZcxbDUk&t=9773s>
- Astuce, avoir une seule instance readonly static pour le JsonSerializerOptions au lieu de faire un new c'est couteux et encourager l'utilisation d'un wrapper - <https://www.youtube.com/live/vU-iZcxbDUk?si=4hu0Or7kjM8f5FYz&t=9440> et <https://www.youtube.com/live/vU-iZcxbDUk?si=KSUtj2cht_pZUldn&t=10372>
- Native Aot - <https://www.youtube.com/live/vU-iZcxbDUk?si=Re4uG2aa8DVJJkr3&t=10829> et <https://www.youtube.com/live/vU-iZcxbDUk?si=NuH0T-nNIieTRu8A&t=11330>

### Entity Framework Core 8

Blog : <https://devblogs.microsoft.com/dotnet/announcing-ef8/>

Cas d'utilisation des `Interceptor` : <https://twitter.com/mjovanovictech/status/1725423885737181312>

### MAUI

Blog : <https://devblogs.microsoft.com/dotnet/announcing-dotnet-maui-in-dotnet-8/>
Hybrid app : <https://www.youtube.com/watch?v=vU-iZcxbDUk&t=25310s>

## WinForms

Whats new in WinForms : <https://www.youtube.com/live/vU-iZcxbDUk?si=nvbE3y9F6Pe3CF5b&t=28910>

## Azure developer CLI

Annonce du release : <https://devblogs.microsoft.com/azure-sdk/azure-developer-cli-azd-november-2023-release/>

## WSL

Nouveau contrôle pour WSL : <https://devblogs.microsoft.com/commandline/new-enterprise-grade-security-controls-for-the-windows-subsystem-for-linux/>

## Azure SQL Database

Vector Search : <https://devblogs.microsoft.com/azure-sql/vector-search-with-azure-sql-database/> et <https://devblogs.microsoft.com/cosmosdb/mongodb-vcore-vector-search/>

## Windows Terminal

Ajout du chat dans la version canary : <https://devblogs.microsoft.com/commandline/terminal-chat-in-windows-terminal-canary/>

## Nuget 6.8

Séance : <https://www.youtube.com/live/vU-iZcxbDUk?si=6rpnI3nB3okJaVVE&t=27049>
Nouveaux features : <https://www.youtube.com/live/vU-iZcxbDUk?si=X2l74BNgMq6t2Z3G&t=27135>
Plusieurs ajouts pour la sécurité : <https://devblogs.microsoft.com/nuget/announcing-nuget-6-8-maintaining-security-with-ease/>

## Web job

Coming web job in app service linux and windows container : <https://www.youtube.com/live/vU-iZcxbDUk?si=uhrz65vYI3OstLOO&t=5965>

## Conteneur

Séance : <https://www.youtube.com/live/vU-iZcxbDUk?si=efi_xRpo_Am_AMic&t=23509>
Nouveau conteneur : <https://devblogs.microsoft.com/dotnet/announcing-dotnet-chiseled-containers/>

## Autres

### why migration .net app to cloud

Séance : <https://www.youtube.com/live/vU-iZcxbDUk?si=hQ1cL1LPCOikybf3&t=21696>
Ajout d'une extension pour Visual Studio pour : <https://www.youtube.com/live/vU-iZcxbDUk?si=oHUdsJ6SWdNvtnem&t=22202>
À venir intégration dans copilot chat : <https://www.youtube.com/live/vU-iZcxbDUk?si=oymsq4zQOjxIWIRH&t=23113>

### Two ways of migrating old aspnet web app to .net 7/8

Séance : <https://www.youtube.com/watch?v=Rd73zT7gpD8>

### Utilisation des simulations

Blog : <https://devblogs.microsoft.com/dotnet/fake-it-til-you-make-it-to-production/>
