# My Fit Tracker

My Fit Tracker is a full stack web application that I have created as a way to track your Fitbit data with D3.js data visualization. It will require the client to login with their Fitbit account info, and then uses the Fitbit API to get the stats from the client's account. 

Quick links:

* [Front-End Code](#frontend) 
*
*
*

## Front-End
  * HTML/CSS
  * AngularJS
  * Material Design
  * D3.js
  * ui-router
  * $q
  * $http

## Back-End
  * Node
  * Express
    * Body-Parser
    * CORS
    * Passport & Passport-Fitbit
  * MongoDB
    * Mongoose
    
## <a name="frontend"></a> Front-End tidbits

### The app

Setting up the app, I have injected 'ngMaterial' for the Material Design, and 'ui.router' for ui-router.

```bash
# angular.module:
var app = angular.module('myFitBit', ['ngMaterial', 'ui.router'])

# .config function - inject mdThemingProvider, stateProvider, urlRouterProvider:
.config(function($mdThemingProvider, $stateProvider, $urlRouterProvider) {

# configure Material Design theme:
  	$mdThemingProvider.theme('default')
      .primaryPalette('cyan')
      .accentPalette('blue')
    
# configure ui-router urlRouterProvider with default 'state':
  	$urlRouterProvider.otherwise('/');

# now configure all of the ui-router 'states':
      $stateProvider
  		.state('login', {
  			url: '/login',
  			templateUrl: 'templates/loginTmpl.html',
  			controller: 'AuthCtrl'
  		})
  		.state('dashboard', {
  			url: '/dashboard',
  			templateUrl: 'templates/dashboardTmpl.html',
  			// controller: 'AuthCtrl'
  		})
  		.state('welcome', {
  			url: '/',
  			templateUrl: 'templates/welcomeTmpl.html',
  		});
  })
```

