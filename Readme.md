AngularJS Emoji Picker
======================

AngularJS Emoji Picker is a simple AngularJs module which allows you to add emoji images to your model value.

### Emoji Picker Directive
Add the `emoji-picker` attribute to an element to drop in to your template. The element will insert a list of available emoji for a user to select.

#### Basic Example:
```
<input type="text" ng-model="keyword"/>
<span emoji-picker="keyword"></span>
```

#### Full Example
```
<textarea ng-model="message" ng-change="messageUpdated()">{{message}}</textarea>
<span emoji-picker="message"
      recent-limit="10"
      output-format="unicode"
      on-change-func="messageUpdated"></span>
```

#### Options:
* **emoji-picker** - the bound property to which selected emoji should be added

* **recent-limit** (optional) - the number of recently-selected emoji to show in the popover window

* **output-format** (optional) - the format to add selected emoji
  
  `alias (default), unicode`

* **on-change-func** (optional) - a function to be called when the user selects or removes an emoji


### Angular Strap
```html
<link rel="stylesheet" href="/path/to/bootstrap/dist/css/bootstrap.min.css">
<script src="/path/to/angular-strap/dist/angular-strap.min.js"></script>
<script src="/path/to/angular-strap/dist/angular-strap.tpl.min.js"></script>
```

```javascript
angular.module('myModule', ['vkEmojiPicker', 'mgcrea.ngStrap']);
```

### Angular-UI Bootstrap
**Versions 0.12.x and lower are not supported.** You need to use angular-ui-bootstrap's current `master` branch. See "Known issues" section below for more information.

```bash
$ bower install angular-ui-bootstrap#master --save
```

```html
<link rel="stylesheet" href="bower_components/bootstrap/dist/css/bootstrap.min.css">
<script src="bower_components/angular-ui-bootstrap/src/bindHtml/bindHtml.js"></script>
<script src="bower_components/angular-ui-bootstrap/src/position/position.js"></script>
<script src="bower_components/angular-ui-bootstrap/src/tooltip/tooltip.js"></script>
<script src="bower_components/angular-ui-bootstrap/src/popover/popover.js"></script>
```

```javascript
angular.module('myModule', ['vkEmojiPicker', 'ui.bootstrap.popover']);
```

Also Emoji Picker provides a couple handy directives:

* `emojify` - converts an emoji string into image

`<div ng-bind-html="message | emojify"></div>`

* `hexify` - converts an emoji string into UTF-8 characters

`<div ng-bind-html="message | hexify"></div>`


## Known issues and limitations

1. The picker requires AngularJS 1.3 as a minimal dependency and up to latest 1.x.


### Building
The files in the `dist/` folder, plus dependencies, are all you need to use Emoji Picker. But if
you'd like to build it yourself, you have to use [grunt](http://gruntjs.com/).

First off, you need to have nodejs installed. Then install all dependencies of the
project with npm and bower, then install grunt and run the default task.

```bash
$ npm install
$ sudo npm install -g grunt-cli
$ bower install
$ grunt
```

The task compiles all source files.

You can also run `grunt watch:dev` to have it rebuild on change.
