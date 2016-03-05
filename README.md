# angular-slug

[Inspired by paulsmith's angular-slugify](https://github.com/paulsmith/angular-slugify) angular-slugs converts converts text into slugs or slugs into text with desired capitalization through a service and filter.


## Installation

You can install the filter using [Bower](http://bower.io/):

```bash
$ bower install angular-slugs
```

Or [npm](https://www.npmjs.com/):

```bash
$ npm install angular-slugs
```

Then you have to include it in your HTML:

```html
<script src="bower_components/angular-slugs/angular-slug.js"></script>
<script src="bower_components/angular-slugs/angular-unslug.js"></script>
<script src="bower_components/angular-slugs/angular-capitalize.js"></script>
```

And inject the desired modules into your application:

```js
angular.module('webApp', ['capitalizer','slugifier','unslugifier']);
```


## Service

The `Slug` service provides a single function `slug` that takes a string
input as argument and returns the slugified string.

```js
function MyCtrl($scope, Slug) {
    $scope.slug = function(input) {
        $scope.mySlug = Slug.slug(input);
    };
}
```
or

```js
function MyCtrl($scope, Unslug) {
    $scope.unslug = function(input) {
        $scope.myUnslug = Unslug.slug(input);
    };
}
```

### Filter

To use add a `slug` or `unslug` pipe filter in your AngularJS curly-brace
expression.

Filters `hello world` to `hello-world`

```html
<p>Slug: {{msg | slug}}</p>
```
Filters `hello-world` to `hello world`

```html
<p>Unslug: {{msg | unslug}}</p>
```

Filters `hello world` to `Hello world`

```html
<p>Unslug: {{msg | unslug| capitalize}}</p>
```

Filters `hello world` to `Hello World`

```html
<p>Unslug: {{msg | unslug| capitalize:true}}</p>
```



## Capitalize

You can use it like any other AngularJS filter:

First word only:

```html
<p>{{msg | capitalize}}</p>
```

First Letter In All Words:

```html
<p>{{msg | capitalize:true}}</p>
```

## License

Copyright © 2016 Garrett M. <team@cera.io>

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the “Software”), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED “AS IS”, WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
# angular-slugs
