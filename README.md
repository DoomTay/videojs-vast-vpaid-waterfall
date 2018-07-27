# videojs-vast-vpaid-waterfall

Allows for VAST and VPAID preroll, midroll, and postroll ads with waterfall. This means that if one ad in an array can't be run for any reason, it will attempt to run the next one.

## Installation

Drop the JS and CSS files in the src folder somewhere in your project

## Usage

You will need video.js, as well as

* [videojs-contrib-ads](https://github.com/videojs/videojs-contrib-ads)
* [vast-client-js](https://github.com/dailymotion/vast-client-js)
* [VPAIDHTML5Client](https://github.com/MailOnline/VPAIDHTML5Client)
* [SWFObject](https://github.com/swfobject/swfobject)
* [VPAIDFLASHClient](https://github.com/MailOnline/VPAIDFLASHClient) *

\* Version must be no later than 0.1.9, as later versions will [inexplicably fail](https://github.com/MailOnline/VPAIDFLASHClient/issues/23)

```html
<script src="//path/to/video.min.js"></script>
<script src="//path/to/vast-client.js"></script>
<script src="//path/to/swfobject.js"></script>
<script src="//path/to/VPAIDHTML5Client.js"></script>
<script src="//path/to/VPAIDFLASHClient.js"></script>
<script src="//path/to/videojs-contrib-ads.js"></script>
<script src="//path/to/videojs-vast-vpaid-waterfall.js"></script>
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
