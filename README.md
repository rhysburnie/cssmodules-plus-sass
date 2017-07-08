# My Simple Starter 2017

## CSS Modules + Sass

> This test case is to enable to usage of Sass with css modules.

[Using as starter](#starter)

**Why?**

While I mostly want to simply use CSS Modules and PostCSS there are times where being able to drop in a Sass utility is helpful.

I have tried many starter kits that claim to have both working together only to find it stops working in certain scenarios - simply because they had not setup a robust test case and at first glance it appears to work.

> That being said there are some caveats:

**My Requirements / What is tested**

* CSS / Sass files work as expected

  For each the following is consistent:

  * Runs through PostCSS
  * Results are extracted to css file

* @import vendor Sass file from node_modules into Sass file

  _caveat_: **MUST use tilde ~ prefix**  `@import '~vendor-path';`

* @import a CSS file into a Sass file

* @import a Sass file into a CSS file
  _caveat_: **MUST use loader prefix** `@import 'sass-loader!path-to-file.scss';`

* Compose a class from a CSS file into a Sass file

* Compose a class from a Sass file into a CSS file
  _caveat_: **MUST use loader prefix** `composes: name from 'sass-loader!path-to-file.scss';`

**Caveats**

* Obviously Sass variables not available to css (however you could generate css vars from them to be used by css files)
  Typically best approach would be to create classes for composition.
* Only a build tested - not tested with dev or hot reload (don't imagine a problem with setup)

<a name="starter"></a>
## Using as starter

```
git clone --depth 1 -b master https://github.com/rhysburnie/cssmodules-plus-sass.git PROJECTNAME

cd PROJECTNAME

// option 1 - remove .git (bye bye history) and start new
rm -rf .git && git init

// option 2 - set new remote origin

// (optional) ref to this repo
git remote add starter https://github.com/rhysburnie/cssmodules-plus-sass.git

// set new origin
git remote set-url origin https://WHATEVER.git

// when ready
// git push -u origin master
```
