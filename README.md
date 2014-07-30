# Bricks Framework Package Manager
This is a cli for compiling Bricks Framework and installing Bricks Framework addons. The default option is to install and compile everything, without compression. The addons are downloaded directly from Bricks Framework servers.

Getting started:
----------------
Bricks Framework Package Manager is available on npm and the usage is simple, let's see how this cli can help to make easy the things for you. 

## Install

	npm install -g bfpm

## Usage

	bfpm [options] <folder>

Both `options` and `folder` are optional. `folder` is the path you want to dump the bootstrap files in and defaults to `./bootstrap`. If the directory already exists and isn't empty, bootstrap-package-manager will warn you. Here are available options:

* `-h, --help` : output usage information
* `-V, --version` : output the version number
* `-j, --javascript` : Add Javascript
* `-c, --css` : Add CSS
* `-l, --less` : Add Less
* `-i, --img` : Add Images
* `-a, --font-awesome` : Add Font Awesome
* `-t, --theme <name>` : Mixin in a Bootswatch theme. See <http://bootswatch.com/> for full list. Compatible with custom variables.less file.
* `-v, --variables <path>` : Path to a custom `variables.less` file to replace the included version.
* `-f, --font-path <path>` : Set a custom value for the less variable `@FontAwesomePath` for a custom css font path when using Font Awesome.
* `-s, --script <paths>` : Include javascript files (seperated by commas) with custom runtime instructions. See `src/font-awesome.coffee` or `src/variables.coffee` for examples.
* `-x, --compress` : Compress JS and CSS and include as an extra `*.min.*` file.
* `--compress-js` : Compress JS with UglifyJs and include as  an extra `bootstrap.min.js` file.
* `--compress-css` : Compress CSS with lessc (YUI) and include as an extra `*.min.css` file.
* `--no-concat` : Don't concat Javascript files together.
* `--bricks-version <version>` : Specific Bootstrap version to use. See <http://github.com/BricksFramework/Bricks/tags> for full list. Default: `master`; Example: `2.1.0` or `v2.1.0`

The default is to include all javascript, css, images and less unless you include at least one of the options `-j`, `-c`, `-l`, or `-i`, in which case only those specified are included.

Sometimes, bfpm fails and it's usually caused by a problem with http requests or file streams (ie. a package url is offline). If this happens, attempt a few reruns and then if the problem still occurs, submit an issue report.

Examples
--------

	$ bfpm

Creates a new folder in the current working directory named "bootstrap" and dumps js, css, less and images into it.

	$ bfpm -ax

Creates a new folder in the current working directory named "bootstrap" and dumps js, css, less, images and font awesome into it. Then it compresses all of the css and js.

	$ bfpm -jcix booten_gurt

Creates a new folder in the current working directory named "booten_gurt" and dumps only js, css, and images into it. Then it compresses all of the css and js.

	$ bfpm -x -v ./variables.less

Creates a new folder in the current working directory named "bootstrap" and dumps js, css, images and less files into it. Then it replaces the existing variables.less file with the custom one and compresses all of the css and js.

	$ bfpm --bootstrap-version 2.1.0

Creates a new folder in the current working directory named "bootstrap", gets version 2.1.0 of bootstrap and dumps only js, css, less, and images into it.

	$ bfpm -t Cosmo

Creates a new folder in the current working directory named "bootstrap", finds and includes the Bootswatch theme `Cosmo` and then exports the js, css, less, and images.

FAQ
---
## BFPM failed
Sometimes, bfpm fails and it's usually caused by a problem with http requests or file streams (ie. a package url is offline). If this happens, attempt a few reruns and then if the problem still occurs, submit an issue report.

Contribute
----------
BFPM is open source and open to any change you think is necessary. If you have changes or submissions that could improve it, we will really appreciate. So, fork this project, makes changes and create a pull request.

Changelod
---------
### 1.0.0
 * First public release on Github

Thanks
------
### Spread it to the world
We will really appreciate if you tweet, blog, use, share, post, or whatever about Bricks Framework. We are really interested in know your experiences with Bricks and continue making it awesome. Tell to the entire people why they should give a try to Bricks Framework.

### Support Bricks Framework
Do you like Bricks and you are interested on support it? Those are the ways you can support Bricks Framework:

 * [Gittip](https://www.gittip.com/BricksFramework/)

### Credits
Bricks is starting at this momment but there are people in back. We would like to thank:

 * [Giovanny Gongora](https://github.com/Gioyik) - Creator and founder
 * You for being about to stargaze or fork this project on GitHub
 * Everyone who has kindly reported issues or made pull requests

### License
BFPM is licensed under MIT. See [LICENSE](https://github.com/BricksFramework/bricks-package-manager/blob/master/LICENSE.md) for more information.
