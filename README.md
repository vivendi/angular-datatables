angular-datatables [![Build Status](https://travis-ci.org/l-lin/angular-datatables.png?branch=master)](https://travis-ci.org/l-lin/angular-datatables) [![Built with Grunt](https://cdn.gruntjs.com/builtwith.png)](http://gruntjs.com/)
================
> Angular module that provides a `datatable` directive along with datatable options helpers.

Notes
-----

The required dependencies are:

* [AngularJS](http://angular.org) (tested with version 1.2.6)
* [jQuery](http://jquery.com) (tested with version 1.11.0)
* [Datatables](https://datatables.net) (tested with version 1.9.4)

This module has been tested with the following datatables modules:

* [ColReorder](https://datatables.net/extras/colreorder/) with version 1.1.0
* [ColVis](https://datatables.net/extras/colvis/) with version 1.1.0
* [TableTools](https://datatables.net/extras/tabletools/) with version 2.2.0

This module also has a [Twitter Bootstrap](http://getbootstrap.com/) support (tested with version 3.1.1).

Getting started
---------------

### Download

**Manually**

The files can be downloaded from:

* Minified [JS](https://raw.githubusercontent.com/l-lin/angular-datatables/master/dist/angular-datatables.min.js) and [CSS](https://raw.githubusercontent.com/l-lin/angular-datatables/master/dist/datatables.bootstrap.min.css) for production usage
* Un-minified [JS](https://raw.githubusercontent.com/l-lin/angular-datatables/master/dist/angular-datatables.js) and [CSS](https://raw.githubusercontent.com/l-lin/angular-datatables/master/dist/datatables.bootstrap.css) for development

> The CSS file only contains `Twitter Bootstrap` styles to support datatables.

**With Bower**

```
bower install angular-datatables
```

### Installation

Include the JS file in your `index.html` file:

```html
<script src="angular-datatables.min.js"></script>
```

**IMPORTANT**: You must include the JS **AFTER** `jQuery` and `DataTables`!

If you want the `Twitter Bootstrap` support, then add the CSS file:

```html
<link rel="datatables.bootstrap.min.css" rel="stylesheet">
```

Declare dependencies on your module app like this:

```html
angular.module('myModule', ['datatables']);
```

Usage
-----

See [github page](https://l-lin.github.io/angular-datatables).

Additional notes
----------------

* This module does not support multiple datatables in the same page (YET)! You can do it, but expect some side effects!
* Each time a datatable is rendered, a message is sent to the parent scopes with the id of the table.

For instance, for the given dataTable:

```html
<table id="foobar" datatable dt-options="dtOptions" dt-columns="dtColumns"></table>
```

You can catch the event like this in your parent directive or controller:

```js
$scope.$on('event:dataTableLoaded', function(event, loadedDT) {
    // loadedDT === {"id": "foobar"}
});
```

License
================
[MIT License](http://en.wikipedia.org/wiki/MIT_License)
