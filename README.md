# CSS Modules + Sass

> This test case is to enable to usage of Sass with css modules.

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