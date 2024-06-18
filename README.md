<h1 align="center">Apotheosis</h1>

<p align="center">  
Apotheosis is a fitness and lifestyle mobile app built with jetpack compose and spring
</p>

## Download
When Apotheosis is released you will be able to get it on the [Google Play Store](https://github.com/EthanNGit/Apotheosis)

## Tech stack | Frontend
- Minimum Android SDK 24
- Jetpack compose with Kotlin
  - Kotlin coroutines 
  - Hilt dependency injection
  - Navigation compose
  - Room DB
  - Retrofit
- Architecture
  - Model View View Model (MVVM): Reccomended by Google due to it's separation of concerns 
- Firebase Authentication
  - Google sign in
  - Facebook sign in
  - Email sign in
- API
  - Apotheosis Nutritional API (see backend tech stack below)
  - Fatsecret API
  - USDA API
  
## Tech stack | Backend
- Docker Compose
  - Spring boot w/ Kotlin
    - Spring security
    - JPA
  - Reverse Proxy
    - Nginx
  - Managing API
    - Prometheus
    - Alert manager
    - Grafana
  - API caching
    - Redis DB
  - Database
    - MariaDB
- Cloudflare
  - Cloudflare SSL
  - Cloudflare tunnels

## Technical details
TBC...

## Architecutre details
Apotheosis uses the MVVM (Model - View - View Model) architecture pattern, this separates the frontend into a couple layers. 
</br></br></br>- Insert graph here </br></br></br>
As seen in the graph above, there is two primary layers that are used.
- First the UI layer, this layer is primarily for collecting input and showing data.
  - The UI layer takes data from a view model and displays it to the views, in Jetpack compose, this could be a Composable.
  - The UI layer also should send inputs to the view model for the view model to decide what to do with the input.
- Second is the data layer, this is where you store Models, or collecting backend data.
  - The data layer collects data through multiple sources, such as the Apotheosis API, or the local Room DB.
  - The data layer also uses the concept of Repositories, which are a way to further enhance separation of concerns.
The view model comes into play as it can bridge the two layers together nicely, as it is the preferred method to holding business logic.

## Apotheosis API
The Apotheosis API gives you a way to access our nutritional database and get your user data to use in any of your projects. When the Apotheosis API goes public you can check [here](https://github.com/EthanNGit/Apotheosis) on how to use it.
