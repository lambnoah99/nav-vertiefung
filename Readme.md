# Navigation

## Wildcard Routes
We now the Application to handle routes which don't exist. Currently when the user tries to navigate to a page that isn't defined in our routing-module, the application will not respond to the request. To catch these requests we'll be using a wildcard route. A Wildcard Route is defined by two asterisks like this:
```ts
{ path: '**', component: ExampleComonent }
```
This way every unknown request would be directed to ExampleComponent. Add the code sample to your Tour-of-Heroes Application, and change the component to the `DashboardComponent`.
## 404-Page