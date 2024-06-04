---
layout: post
title: Custom AppleTV Screensavers!
---
### Custom AppleTV Screensavers!
<i>Disclaimer: This methodologies used in this tutorial are not "officially" supported by Apple. Use at your own risk. Also, many menu items get disabled such as software update and restart. </i>

One day, one of my coworkers asked if it would be possible to change the screensaver that is on the AppleTVs across our campus. I thought that would be a great idea, and started searching the web to see what options were available. I came across a few app-based solutions but they seemed limited and I would have to force the AppleTV into single-app mode for it to work all the time. 

Then, I stumbled across something called retail Demo mode. Instructions on how to enter retail Demo mode found <a href="https://www.idownloadblog.com/2016/01/18/apple-tv-store-demo-mode/" target="_blank">here</a>. 

However, once you turn on Demo mode, a lot of settings are grayed out. So we need to first set those up. 

Step 1: Set screensaver timer to 2 minutes in screensaver settings.<br />
Step 2: Set sleep to never if you want it always on.<br />
Step 3: Turn on Conference mode.<br />
Step 4: Apply these changes.<br />

Here's the <b>secret sauce</b>. You can set the screensaver to a custom file if you mimic Apple's JSON structure. 

```
[
   {
      "id" : "73F3F654-9EC5-4876-8BF6-474E22029A49",
      "assets" : [
         {
            "url" : "your mp4 video file here",
            "accessibilityLabel" : "your label here",
            "type" : "video",
            "id" : "1E85E5A0-22E9-41C7-A04F-A3BCFD77D43F",
            "timeOfDay" : "day"
         }         
      ]
   }
]
```
Save this file as `entries.json` and put it on a network accessible web server. 

Now, we can enable Demo Mode: 

Step 1: Open Settings.<br />
Step 2: Click General and highlight About.<br />
Step 3: Press the Play/Pause button 4 times.<br />
Step 4: Click the Demo Mode panel and select Apple Store or Channel to set the retail demo mode type.<br />

![]({{ site.url }}/assets/imgs/retail-mode.jpg)<br /><br />
Step 5: On the circled field, enter the URL of your `entries.json` file. <br />
Step 6: Click Apply Changes to enable Demo mode.<br />
Step 7: Reboot your AppleTV. <br />

Now, after 2 minutes, your AppleTV should start showing your custom video as it's screensaver! Did this work for you? Let us know in the comments. 


{% include utterances.html %}