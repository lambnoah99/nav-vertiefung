# Navigation
## Route-Order
The order of routes is important because the Router uses a first-match wins strategy when matching routes, so more specific routes should be placed above less specific routes. List routes with a static path first, followed by an empty path route, which matches the default route. The wildcard route comes last because it matches every URL and the Router selects it only if no other routes match first.
## Wildcard Routes
We now the Application to handle routes which don't exist. Currently when the user tries to navigate to a page that isn't defined in our routing-module, the application will not respond to the request. To catch these requests we'll be using a wildcard route. A Wildcard Route is defined by two asterisks like this:
```ts
{ path: '**', component: ExampleComonent }
```
This way every unknown request would be directed to ExampleComponent. Add the code sample to your Tour-of-Heroes Application, and change the component to the `DashboardComponent`.
## 404 Page
Next we want to create a '404 Page not found' page. Create a new component named PageNotFoundComponent
`ng generate component PageNotFound`
Change the template file to a that tells the user that the page doesn't exist. Additionally add a button which lets the user navigate to the Dashboard.
`pagenotfound.component.html`
```html
<h1>404 Page Not Found</h1>
<p>The requested page doesn't exist</p>
<a routerLink="/dashboard">Go to the dashboard</a>
``` 