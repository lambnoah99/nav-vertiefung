# Navigation
## Route-Order
The order of routes is important because the Router uses a first-match wins strategy when matching routes, so more specific routes should be placed above less specific routes. List routes with a static path first, followed by an empty path route, which matches the default route. The wildcard route comes last because it matches every URL and the Router selects it only if no other routes match first.
## Wildcard Routes
We now want the Application to handle routes which don't exist. Currently when the user tries to navigate to a page that isn't defined in our routing-module, the application will not respond to the request. To catch these requests we'll be using a wildcard route. A Wildcard Route is defined by two asterisks like this: 
```ts
{ path: '**', component: ExampleComonent }
```
This way every unknown request would be directed to ExampleComponent. Add the code sample to your Tour-of-Heroes Application, and change the component to the `DashboardComponent`.
## 404 Page
Next we want to create a '404 Page not found' page. Create a new component named PageNotFoundComponent
`ng generate component PageNotFound`
Change the template file to one that tells the user that the page doesn't exist. Additionally add a button which lets the user navigate to the Dashboard.
`pagenotfound.component.html`
```html
<h1>404 Page Not Found</h1>
<p>The requested page doesn't exist</p>
<a routerLink="/dashboard">Go to the dashboard</a>
```
## Redirects
To set up a redirect, configure a route with the `path` you want to redirect from, the `component` you want to redirect to, and a `pathMatch` value that tells the router how to match the URL.
```ts
{ path: '', redirectTo: '/someOtherPath', pathMatch: 'full' }
```
Note: `pathMatch` could as have the value `prefix`, this way, every route that has the `path` as a prefix gets redirected. So if the prefix is `lorem`, then `lorem/somePage` would be redirected. `ipsum/somePage` wouldn't be redirected.

We're going to create a path `the-ultimate-hero`. This path should redirect the User to the detail page of a hero. The route entry looks like this.
```ts
{ path: 'the-ultimate-hero', redirectTo: '/detail/12', pathMatch: 'full' }
```
And now if we type open the route `localhost:8082/the-ultimate-hero` we will land on the detail page of hero 12.

## Relative Paths
### In the Template
Relative paths allow you to define paths that are relative to the current URL segment. The following example shows a relative route to another component, `second-component`. `FirstComponent` and `SecondComponent` are at the same level in the tree, however, the link to `SecondComponent` is situated within the `FirstComponent`, meaning that the router has to go up a level and then into the second directory to find the `SecondComponent`. Rather than writing out the whole path to get to SecondComponent, you can use the `../` notation to go up a level.
```html
<a routerLink="../second-component">Relative Route to second component</a>
```
In addition to `../`, you can use `./` or no leading slash to specify the current level.
