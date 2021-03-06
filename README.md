## Why this fork?

We are working in a project that uses REST services that return huge geojson objects. When AngularJs have to deals with those responses, it take so long to $digets them because the function angular.copy make a copy considering specials cases and another stuff internals to AngularJs.

The problem matters only in one case of use and, replacing the way making the object copy for something more native in Javascript ( JSON.parse(JSON.stringify(value)) ), we can reduce the time of the $digets from 6 seconds to 300ms.

The improvement is amazing, and that is the reason of this repo :)

## How update this repo?

Be sure you add the original repo into the git configuration:

```shell
git remote add -f --tags angular-origin git@github.com:angular/bower-angular.git

```

Then, follow the next commands:
```shell
git checkout develop
git merge angular-origin/master
```

If everything is ok, you must have two conflicts:
```shell
# Unmerged paths:
#   (use "git add <file>..." to mark resolution)
#
#	both modified:   bower.json
#	both modified:   package.json
```

Fix the version in those files and then:
```shell
git commit
git flow release start <version>
git flow release finish <version>
git push origin develop
git push origin master
git push origin master --tags
```

==========

# packaged angular

This repo is for distribution on `npm` and `bower`. The source for this module is in the
[main AngularJS repo](https://github.com/angular/angular.js).
Please file issues and pull requests against that repo.

## Install

You can install this package either with `npm` or with `bower`.

### npm

```shell
npm install angular
```

Then add a `<script>` to your `index.html`:

```html
<script src="/node_modules/angular/angular.js"></script>
```

Or `require('angular')` from your code.

### bower

```shell
bower install angular
```

Then add a `<script>` to your `index.html`:

```html
<script src="/bower_components/angular/angular.js"></script>
```

## Documentation

Documentation is available on the
[AngularJS docs site](http://docs.angularjs.org/).

## License

The MIT License

Copyright (c) 2010-2015 Google, Inc. http://angularjs.org

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
