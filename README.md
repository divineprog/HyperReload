# HyperReload

HyperReload is a lightweight tool for rapid development of mobile apps in JavaScript.

## What it does

Edit your HTML/CSS/JS on your desktop machine, save the edited file, and the changes are automatically reloaded on connected clients. This saves you from rebuild, deploy and restart your mobile application every time a code change is made. The result is a much faster workflow when coding HTML/CSS/JS.

Any number of clients can connect. You can connect from any browser (desktop or mobile), or you can connect from a mobile WebView widget of a native app (this should work on all mobile platforms that supports a Web widget, Android, iOS, Windows Phone, Firefox OS, Tizen, etc).

## Get started quickly

The easiest way to get started is to download the [HyperReload](http://hyperreload.com), product package (available for Linux, OS X, and Windows). The download includes documentation and tutorials, and the full source code (which you can modify as needed).

## Running from source

HyperReload uses [node-webkit](https://github.com/rogerwang/node-webkit) as its runtime (an amazing piece of software).

There is no need to do an actual build, you can clone the source, then run using node-webkit. Just place the node-webkit [executable files](https://github.com/rogerwang/node-webkit) in the same folder as package.json and launch node-webkit.

## Documentation and issue tracker

Documentation and downloads for HyperReload are on [hyperreload.com](http://hyperreload.com).

Developer documentation and design documents are on the [HyperReload GitHub wiki] (https://github.com/divineprog/HyperReload/wiki/_pages).

Use the [Github issue tracker](https://github.com/divineprog/HyperReload/issues) to report bugs, ask questions, and make suggestions (there are labels for different issue types you can use).

## How to use HyperReload

### 1. Launch the HyperReload desktop application

Download [HyperReload](http://hyperreload.com), unzip the download file and launch the  application.

When you run HyperReload on your desktop machine, it will start a local web server and listen for file updates, notifying connected clients to reload when files are saved.

### 2. Connect from the browser/device

Connect from a web browser on a mobile device or laptop/desktop machine by entering the URL displayed in the HyperReload window. For example:

    http://192.168.0.101:4042

You can also connect from a WebView widget in a mobile app. For example, on Android you use code like this:

	WebView mWebView = new WebView(this);
	mWebView.getSettings().setJavaScriptEnabled(true);
	setWebViewClient(new WebViewClient());
    mWebView.loadUrl("http://192.168.0.101:4042");

Make sure the WebView has JavaScript enabled, and that it has a WebViewClient (otherwise, URLs opened from within the WebView will be opened in en external browser, rather than in the WebView itself).

### 3. Click "Run"

When connected, click the **Run** button of the project you wish to launch, and the app will be loaded onto the connected device(s).

When editing and saving files in the project, the app will be automatically reloaded on the connected client(s). (Note that directory traversal is limited to three levels, this can be configured in the file settings.js, if you need deeper traversal.)

### 4. Create new projects using drag and drop

To create a new project entry, drag the main HTML file of our project into the HyperReload window. (This step assumes you have created a folder with an HTML file that has some basic content.)

### 5. Structure of the main HTML file

For HyperReload to work, you need to have a main HTML file. This is the file you want to be reloaded when a file in the project is updated. (Saving any file in the same directory or subdirectory will reload this file.)

For the reload mechanism to work, the server inserts a script tag in the main HTML file that installs the reloader script. This script will be inserted after the ending title tag, before the ending head tag, after the opening body tag, and before the ending body tag, in that order (first found tag will be used).

For example, for this file, the script tag would be inserted after the ending title tag:

	<!DOCTYPE html>
	<html>
	<head>
	  <meta charset="utf-8">
	  <title>Hello World</title><!-- script tag will be inserted here -->
	</head>
	<body>
        <h1>Hello World</h1>
	</body>
	</html>

## Roadmap

HyperReload is under development, with ongoing changes/updates.

New releases are made continously. Downloads are available at [hyperreload.com](http://hyperreload.com).

## Credits

HyperReload is based on several truly wonderful open-source projects, including:

* [node-webkit](https://github.com/rogerwang/node-webkit)
* [Node.js](http://nodejs.org/)
* [CodeMirror](http://codemirror.net/)
* [jQuery](http://jquery.com/)
* [Apache Cordova](http://cordova.apache.org/)

For a full listing of software used by HyperReload, see folder "license".

## License information

HyperReload is Copyright (c) 2013 Mikael Kindborg

The HyperReload source code is licensed under the Apache license. You are welcome to contribute to the project and use the HyperReload source code for your own projects.

See the folder "license" for full licensing information, including licenses for software used by HyperReload.

The [HyperReload software product](http://hyperreload.com) contains tutorials and other material that are not open source. You are free to use HyperReload at work and at home, and modify it for your own needs and share with friends, but you may not sell, publish, or distribute the HyperReload software product.

Commercial licenses of HyperReload and support and development services are available upon request.

## Contact

Email: mikael@kindborg.com

<!--
, mikael.kindborg@evothings.com

[EvoThings](http://evothings.com) are a seasoned bunch of developers who enjoy connecting phones to other things. We love to improve, refurbish, evolve and augment buildings, vehicles and gadgets, and make them smarter.
-->

<!--
## Components

HyperApp consists of two applications:

* The HyperApp UI desktop application
* The HyperApp mobile client application (optional, under development, not finished)

### 3. Enter the path of the mobile app main HTML file

When connected, enter the path to the main HTML file of your project in the HyperApp UI.

Then press the **Run** button, and the app will be loaded onto the connected device(s).

When editing and saving files in the project, the app will be automatically reloaded on the connected client(s). (Note that directory traversal is currently limited to two levels, this will be configurable in the UI, for now, update this manually in UI/index.html if you need deeper traversal.)
-->

<!--
With the HyperApp mobile application (under development) you get additional functionlity:

* Quick-connect to the running HyperApp UI
* Get console error messages displayed in the HyperApp UI (Android)
* No need to build the application, just install from the app store (forthcoming)
-->

<!--
## License

HyperReload is both and open-source project and a product. You are welcome to contribute to the project and use HyperReload source code for your own projects, but you may not copy or distribute the HyperReload software product.

Licensing information:

	Copyright (c) 2013 Mikael Kindborg

	You are free to use HyperReload at work and at home. You are free to
	modify the program to fit your own needs, and share with friends.

	You are NOT allowed to sell or distribute the HyperReload product package.

	The HyperReload source code files are licensed under the MIT license.

	The HyperReload software product, including the user interface design
	and user documentation, is NOT subject to the MIT license, and may NOT
	be sold, published, distributed, or sublicensed.

See the folder "license" for full licensing information, including licenses for software used by HyperReload.

-->
