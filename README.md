PhoneGap Plugin for OpenTok iOS
===

Weave video chat into your web (and now mobile!) application.

## Step 1. Install and create a PhoneGap app
**Make sure You have PhoneGap 2.0 Installed** If you haven't, check out PhoneGap's [Getting Started](http://docs.phonegap.com/en/2.0.0/guide_getting-started_ios_index.md.html#Getting%20Started%20with%20iOS) Page.

1. Create a PhoneGap app by going to your PhoneGap's Bin folder, and type into Terminal:  
`./create <project_folder_path> <bundle_id> <project_name>`  
*Example:*  
`./create ~/Development/OpenTokApp me.songz.OpenTokApp OpenTokApp`

2. Go to ~/Development/OpenTokApp directory that you just created, and launch `*.xcodeproj` file in the folder  


## Step 2. Add the OpenTok iOS SDK to your project
The easiest way is to do this: take a working OpenTok app and copy the OpenTok Framework and all the dependencies to your project.  Here's how to do that.

1. Clone from <https://github.com/opentok/OpenTok-iOS-Hello-World.git> and open the Hello-World xcode project.  
Be sure to git clone with --recursive to grab the required OpenTok iOS SDK submodule!  
`git clone --recursive https://github.com/opentok/OpenTok-iOS-Hello-World.git`

2. In XCode, drag the OpenTok.framework from Hello-World project into your project's *Frameworks* folder.
Select *Copy Items into destination group's folder* so you don't depend on the Hello-World project.

3. In XCode, drag the frameworks that OpenTok needs to run that are not currently in your project.
Since these are iOS frameworks, you already have the in your system. Make sure *Copy items into destination group's folder* is **not** selected  
![framework](http://songz.github.com/phonegap-plugin-opentok/images/frameworks.png)

4. Click on your project in the XCode project manager and select **Build Settings**. 
Make sure **Standard (armv7)** is selected for **Architectures**.  
Make sure **armv7** is the *only* option selected for **Valid Architectures**.  

![architecture](http://songz.github.com/phonegap-plugin-opentok/images/arch.png)  

**Note** When testing, please run your app in your device, and **NOT** the simulator. The OpenTok iOS SDK requires access to the camera, which
is not available in the simulator. 

## Step 3. Install the OpenTok PhoneGap Plugin
1. Clone from <https://github.com/opentok/PhoneGap-Plugin>.
`git clone https://github.com/opentok/PhoneGap-Plugin`

2. Copy `OpenTokPlugin.h` and `OpenTokPlugin.m` into your **Classes** folder  
> Make sure **Copy items into destination group's folder** *is selected*.
>
![ios](http://songz.github.com/phonegap-plugin-opentok/images/iosplugin.png)

3. Copy `OpenTok.js` into your `www/js` folder.  
![js](http://songz.github.com/phonegap-plugin-opentok/images/jsplugin.png)

4. In the XCode project manager, under `Supporting Files` folder, select `Cordova.plist`.
> Under `Plugins`, add a new entry: `TokBox`, `OpenTokPlugin`  

> Under `ExternalHosts`, add a new entry with the value *.  
![plist](http://songz.github.com/phonegap-plugin-opentok/images/cplist.png) 


---

## Getting Started on your Project:
All your editing will be done in your www folder.

To use the opentok library, make sure you include **OpenTok.js** file in your HTML document.  
` <script type="text/javascript" charset="utf-8" src="OpenTok.js"></script>`

All code should be written in `onDeviceReady` function because it is executed after all the devices/libraries DOM has loaded.

	function onDeviceReady()
	{
		// do your thing!
	}

---

## Tutorial and sample code
Go through the 15-minute [Getting started tutorial](http://www.tokbox.com/opentok/api/documentation/gettingstarted) to learn the Basics!  

Next, look at the included in the Samples folder and follow the instructions in the README. It will show you how to get something start right away based on the [OpenTok HelloWorld sample application](http://www.tokbox.com/opentok/api/tools/js/tutorials/helloworld.html).  

Have Fun!

----

## [Documentation for PhoneGap Plugin](docs/README.md)

----

License
===

Copyright (c) 2012 TokBox, Inc.

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:


The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

The software complies with Terms of Service for the OpenTok platform described in <http://www.tokbox.com/termsofservice>.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
