# WebView Quirks and Testing Breakout TPAC 2025

Nov. 11, 2025 08:30 GMT+9

Link: [https://bit.ly/webview-cg-2510](https://bit.ly/webview-cg-2510)

Notes on GitHub:[https://github.com/WebView-CG/tpac/blob/main/TPAC-2025/Breakout/WebViewQuirksAndTestingNotes.md](https://github.com/WebView-CG/tpac/blob/main/TPAC-2025/Breakout/WebViewQuirksAndTestingNotes.md)

## Session goals

* Showcase testing tools
* In progress testing resources
* Open exchange about WebView issues

### Attendees

* [Niklas Merz](mailto:niklasmerz@apache.org) (Apache Cordova)
* Bryan Ellis (Apache Cordova)
* Dan Pelegero (RPGC Group)
* Karl Dubost (Apple - WebKit Webcompat)
* SANG UI PARK
* Euclid (Huawei)
* Mingyu Lei (Google Chrome)
* Ben Kelly (Meta)

### Scribes

* Bryan Ellis

## Agenda

* Introduction round
* Present CanIWebview apps and ideas (Niklas)
* Test automations are being built
* Let's share our stories, issues and use cases with WebView
* Cookies and localhost (Niklas)
* ....more
* 

## Notes

* Niklas:
  * Going over the CanIWebView.com website that was built to collect and display data.
    * Cover major browsers. Data collected from BCD
  * Built basic apps to allow developers to test webviews.
    * Testing WebViews should be accessible for every web developer
    * The apps are built and published for Android and iOS
    * Can download and build locally for WebView 2 (Windows)
    * Working on an experimental build for Taui + Servo
    * The apps are open source and ad-free +  offer all WebView configurations
  * Next big step is to create automation for testing (App driver & Web driver)
  * Shows screenshots & demoing the CanIWebview App
    * Showing that from within the app can run the mdn bcd collector to test what the webview is capable of.
    * Shows that the app can configure the webview settings. For example, enable or disable JavaScript.
    * Looking to have discussion around what type of additional configurations should be added.
  * Looking for anyone that has recent knowledge around App driver & Web driver
  * Niklas: Personal number one issue is how local contents are served differently between Android and iOS.
    * File protocol is not used as much anymore because of how major frameworks handle routing.
    * Android supports hosting content though HTTP/HTTPS registered domains. Can intercept GET & path
    * iOS must use a customer app URL scheme.
    * iOS has more flexibility and capability
    * Different origins need different HTTP allow origin headers and therefore the backend needs to support dynamically setting that
  * WebViews implement their own Cookies managers but there are quirks in how it works in WebViews.
* Karl: Would like to know what is missing from in terms of documentation of what webviews are.
* Niklas: One example is what information vendors release, for example when a new feature is released from WebKit is it in Safari only or also in WebView.
* Niklas: WebDX is trying to collect and create a baseline of what features exist and support in browsers and we are trying to create a similar baseline for WebViews.
  * Showing a demo of the CanIWebView’s baseline map…
* Karl: BCD data is not always up-to-date
* Karl: Apple is contributing back to BCD for data they find is wrong in their testing
* Niklas: Which platforms?
* Karl: Safari desktop & mobile
* Niklas: Would be good if Apple could also contribute back to BCD for WKWebView
* Ben:
  * Android, it seems easier to monitor events like onPageLoad which can be abused
  * Browsers for a long time store cookies on disk and would be loaded into memory but for some reason the document.cookie is slower.
  * A lot of things that can be done in Chrome are not mapped the same in the WebView, or is disabled.
* Euclid: Has experience with web drivers and will reach out to talk further about it.
* Dan: SPC Payments APIs - Browser handles the payment calls, what is the role that should exist.
