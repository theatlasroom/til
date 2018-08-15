
# Loading static assets in storybook
Storybook is a fantastic tool for prototyping and rapid development of ui's particularily in the react ecosystem. It also functions as a working styleguide for an application. A simple problem I had was loading external assets, the project in question was using some custom fonts and was based on bootstrap for the UI framework. 

The burden of migrating from bootstrap was going to be too much for the few features to implement so i thought the best solution in the interim to preserve the look of the components was just to ensure the storybook includes the same set of assets used in the application. Luckily storybook provides 2 useful hooks for this:

## Custom head tags
Add a `preview-head.html` file into the `.storybook` config directory, this file should contain tags that you would like included in the head of the iframe where your stories are loaded into. This can include tags like `<link />`, `<script />` to import scripts and stylesheets.

```html
<script src="link-to-external-some-js-file"></script>
<link rel="stylesheet" href="link-to-some-external-stylesheet" />
```

## Asset directory config
The `start-storybook` command accepts a series of flags, one of which is `-s` or `--static-dir` which can be used to specify a location to search for assets (images, js, css files). This is useful for assets that are local to your project not downloaded from a cdn.
```javascript
package.json

{
	...
	"scripts": {
		"storybook":"start-storybook -p 9001 -s ./some/asset/dir" 
	}
	...
}
```

## Links
[Storybook - serving static files](https://storybook.js.org/configurations/serving-static-files/)
[Storybook - custom head tags](https://storybook.js.org/configurations/add-custom-head-tags/)
