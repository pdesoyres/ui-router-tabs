# UI Router Tabs

Leverages [UI Bootstrap](http://angular-ui.github.io/bootstrap/) and [UI Router](https://github.com/angular-ui/ui-router) to give you full-strength route-driven tabs in Angular.js.

[![Build Status](https://secure.travis-ci.org/rpocklin/ui-router-tabs.svg)](http:/travis-ci.org/rpocklin/ui-router-tabs)
[![Coverage Status](https://coveralls.io/repos/rpocklin/ui-router-tabs/badge.png)](https://coveralls.io/r/rpocklin/ui-router-tabs)

## Example / Demo
[Link](http://rpocklin.github.io/ui-router-tabs/example/index.html)

## How to Install / Usage

1. Install the plugin into your Angular.js project, manually or via `bower install angular-ui-router-tabs`
1. Add `ui.router.tabs` as a new module dependency in your angular app.

1. Define your routes in a hierarchy that makes sense for a tabbed layout, Eg:
```javascript
    $stateProvider.state('user', {
      url:         '',
      controller: 'UserCtrl',
      templateUrl: 'example.html'
    }).state('user.settings', {
      url:         '/user/settings',
      templateUrl: 'user/settings.html'
    }).state('user.accounts', {
      url:         '/user/accounts',
      templateUrl: 'user/accounts.html'
    });
```

1. Define your `tabData` (or similiar variable) in the root view controller of your tabs (ie. `UserCtrl` in the case above) Eg:
```javascript
    $scope.tabData   = [
      {
        heading: 'Settings',
        route:   'user.settings'
      },
      {
        heading: 'Accounts',
        route:   'user.accounts'
      }
    ];
```

NOTE: You can also specify `params` and `options` to pass special parameters or options for the target route to UI Router, Eg:
```javascript
    {
      heading: 'Accounts',
      route:   'user.accounts',
      params: {
                accountId: account.id
              },
      options: {}
    }
```

1. Declare the following in your the parent HTML view template `<tabs data="tabData" type="tabs" />`.

Optional attributes for the `<tabs>` (which are passed on to the UI Bootstrap component) are:

- `type: [ 'tabs' | 'pills' ]`
- `vertical: boolean`
- `justified: boolean`



## Tips

* You can override the default directive template by specifying `template-url="my_template.html" on the `<tabs>` element.
* You can use `<tab-heading>` in a custom directive template to add any HTML into the tab title.
* You can move the `<tabs>` tag around to wherever you want the tab listing to appear.
* Left-positioned seems the best spot for responsive design.
* You can update the `tabData` variable dynamically, if you want to.

## Running Locally

1. Checkout git repository locally: `git clone git@github.com:rpocklin/ui-router-tabs.git`
1. `npm install`
1. `bower install`
1. `grunt serve`
1. View `http://localhost:9000/example/`in your browser to see the example.


## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Added some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request

## License

Released under the MIT License. See the [LICENSE][license] file for further details.

[license]: https://github.com/rpocklin/ui-router-tabs/blob/master/LICENSE
