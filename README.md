# CoffeeKup Template Engine wrapper for SocketStream 0.3

http://coffeekup.org

Use pre-compiled CoffeeKup client-side templates in your app.


### Installation

Add `ss-coffeekup` to your application's `package.json` file and then add this line to app.js:

```javascript
ss.client.templateEngine.use(require('ss-coffeekup'));
```

Restart the server. From now on all templates will be pre-compiled and accessibale via the `ss.tmpl` object.


### Usage

A template placed in

    /client/templates/offers/latest.coffee

Can be rendered in your browser with

```javascript
// assumes var ss = require('socketstream')
var html = ss.tmpl['offers-latest']({name: 'Special Offers'})
```

### Note

CoffeeKup templates do not require a VM or any other client-side library as each template is turned into pure JS code. This is great for convenience and performance, but can result in a lot of code being sent to the client vs other template solutions if your app has many templates.

Improvements and forks welcome.


### Options

When experimenting with CoffeeKup, or converting an app from one template type to another, you may find it advantageous to use multiple template engines and confine use of CoffeeKup to a sub-directory of `/client/templates`.

Directory names can be passed to the second argument as so:

```javascript
ss.client.templateEngine.use(require('ss-coffeekup'), '/ck-templates');
```

