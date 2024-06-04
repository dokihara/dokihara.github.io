---
layout: post
title: Custom AppleTV Screensavers!
---
### Custom AppleTV Screensavers!
One day, one of my coworkers asked if it would be possible to change the screensaver that is on the AppleTVs across our campus. I thought that would be a great idea, and started searching the web to see what options were available. I came across a few app-based solutions but they seemed limited and I would have to force the AppleTV into single-app mode for it to work all the time. 

Then, I stumbled across something called retail Demo mode. Instructions on how to enter retail Demo mode found here: https://www.idownloadblog.com/2016/01/18/apple-tv-store-demo-mode/

However, once you turn on Demo mode, a lot of settings are grayed out. So we need to first set those up. 

Step 1: Set screensaver timer to 2 minutes in screensaver settings
Step 2: Set sleep to never
Step 3: Turn on Conference mode
Step 4: Apply these changes. 

Here's the secret sauce. You can set the screensaver to a custom file if you mimic Apple's JSON structure. 

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

Step 1: Open Settings.
Step 2: Click General and highlight About.
Step 3: Press the Play/Pause button 4 times.
Step 4: Click the Demo Mode panel and select Apple Store or Channel to set the retail demo mode type.

![]({{ site.url }}/assets/imgs/retail-mode.jpg)
Step 5: On the circled field, enter the URL of your `entries.json` file. 
Step 6: Click Apply Changes to enable Demo mode.
Step 7: Reboot your AppleTV. 

Now, after 2 minutes, your AppleTV should start showing your custom video as it's screensaver! Did this work for you? Let us know in the comments. 


{% include utterances.html %}