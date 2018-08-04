# videojs-vast-vpaid-waterfall

Allows for VAST and VPAID preroll, midroll, and postroll ads with fallback

## Installation

```sh
npm install --save videojs-vast-vpaid-waterfall
```

## Usage

To include videojs-vast-vpaid-waterfall on your website or web application, use any of the following methods.

### `<script>` Tag

This is the simplest case. Get the script in whatever way you prefer and include the plugin _after_ you include [video.js][videojs], so that the `videojs` global is available.

```html
<script src="//path/to/video.min.js"></script>
<script src="//path/to/video-contrib-ads.min.js"></script>
<script src="//path/to/videojs-vast-vpaid-waterfall.min.js"></script>
<script>
	var player = videojs("my-video");

	player.vastWaterfall({
		preroll:
		[
			{
				ads: ["https://www.adserver.com/preroll/default/...",
				"https://www.adserver.com/preroll/backup1/...",
				"https://www.adserver.com/preroll/backup2/...",
				"https://www.adserver.com/prerolll/backup3/..."]
			}
		],
		midroll:
		[
			{
				time: 229,
				ads: ["https://www.adserver.com/midroll/default/...",
				"https://www.adserver.com/midroll/backup1/...",
				"https://www.adserver.com/midroll/backup2/...",
				"https://www.adserver.com/midroll/backup3/..."]
			},
			{
				time: 229,
				ads: ["https://www.adserver.com/midroll/default/...",
				"https://www.adserver.com/midroll/backup1/...",
				"https://www.adserver.com/midroll/backup2/...",
				"https://www.adserver.com/midroll/backup3/..."]
			}
		],
		postroll:
		[
			{
				ads: ["https://www.adserver.com/postroll/default/...",
				"https://www.adserver.com/postroll/backup1/...",
				"https://www.adserver.com/postroll/backup2/...",
				"https://www.adserver.com/postrolll/backup3/..."]
			}
		]
	});
</script>
```

### Browserify/CommonJS

When using with Browserify, install videojs-vast-vpaid-waterfall via npm and `require` the plugin as you would any other module.

```js
var videojs = require('video.js');

// The actual plugin function is exported by this module, but it is also
// attached to the `Player.prototype`; so, there is no need to assign it
// to a variable.
require('videojs-vast-vpaid-waterfall');

var player = videojs('my-video');

player.vastWaterfall({
	preroll:
	[
		{
			ads: ["https://www.adserver.com/preroll/default/...",
			"https://www.adserver.com/preroll/backup1/...",
			"https://www.adserver.com/preroll/backup2/...",
			"https://www.adserver.com/prerolll/backup3/..."]
		}
	],
	midroll:
	[
		{
			time: 229,
			ads: ["https://www.adserver.com/midroll/default/...",
			"https://www.adserver.com/midroll/backup1/...",
			"https://www.adserver.com/midroll/backup2/...",
			"https://www.adserver.com/midroll/backup3/..."]
		},
		{
			time: 229,
			ads: ["https://www.adserver.com/midroll/default/...",
			"https://www.adserver.com/midroll/backup1/...",
			"https://www.adserver.com/midroll/backup2/...",
			"https://www.adserver.com/midroll/backup3/..."]
		}
	],
	postroll:
	[
		{
			ads: ["https://www.adserver.com/postroll/default/...",
			"https://www.adserver.com/postroll/backup1/...",
			"https://www.adserver.com/postroll/backup2/...",
			"https://www.adserver.com/postrolll/backup3/..."]
		}
	]
});
```

### RequireJS/AMD

When using with RequireJS (or another AMD library), get the script in whatever way you prefer and `require` the plugin as you normally would:

```js
require(['video.js', 'videojs-vast-vpaid-waterfall'], function(videojs) {
	var player = videojs('my-video');

	player.vastWaterfall({
		preroll:
		[
			{
				ads: ["https://www.adserver.com/preroll/default/...",
				"https://www.adserver.com/preroll/backup1/...",
				"https://www.adserver.com/preroll/backup2/...",
				"https://www.adserver.com/prerolll/backup3/..."]
			}
		],
		midroll:
		[
			{
				time: 229,
				ads: ["https://www.adserver.com/midroll/default/...",
				"https://www.adserver.com/midroll/backup1/...",
				"https://www.adserver.com/midroll/backup2/...",
				"https://www.adserver.com/midroll/backup3/..."]
			},
			{
				time: 229,
				ads: ["https://www.adserver.com/midroll/default/...",
				"https://www.adserver.com/midroll/backup1/...",
				"https://www.adserver.com/midroll/backup2/...",
				"https://www.adserver.com/midroll/backup3/..."]
			}
		],
		postroll:
		[
			{
				ads: ["https://www.adserver.com/postroll/default/...",
				"https://www.adserver.com/postroll/backup1/...",
				"https://www.adserver.com/postroll/backup2/...",
				"https://www.adserver.com/postrolll/backup3/..."]
			}
		]
	});
});
```

## Other options
### markers
Adds markers to indicate when midroll markers will happen. Defaults to `true`. Markers will have the class `vjs-midroll-marker`, so their appearance can be customized with CSS.

### debug
Prints debug messages. Defaults to `false`

### skipDelay
Overrides any skip delay defined in the ad. Will cause a "skip" button to appear after `n` seconds

### flashWrapperPath
Points to the file that will serve as the wrapper for VPAID Flash ads. Defaults to `/VPAIDFlash.swf`

## License

MIT. Copyright (c) DoomTay


[videojs]: http://videojs.com/
