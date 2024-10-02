# [TPAC] Web Standards Beyond The Browser

Sep 25, 2024

Link: [bit.ly/standards-beyond-the-browser](https://bit.ly/standards-beyond-the-browser)

## Attendees

* Niklas Merz (Apache Cordova)
* Ben Wiser (Google Android WebView)
* Hadrien Gardeur (EDRLab, Readium Foundation)
* Derek Schuff (Google, Chrome/WebAssembly)
* Christoph Guttandin (Freelance)
* Abhijeet Kandalkar (Igalia)
* Sebastian Käbisch (Siemens)
* Kunihiko Toumura (Hitachi)
* Nigel Megitt (BBC)
* Oliver Dunk (Google, Extensions)
* Ali Spivak (Google, Chrome)
* Mihai Cîrlănaru (Google Android WebView)
* Andreu Botella (Igalia, WinterCG)
* Florian Scholz (Open Web Docs)
* Will Bamberg (Open Web Docs)

## Scribes

* Ben Wiser (Google Android WebView)

## Notes

* Introduction & Admin (5 min)
* Roll call: Who is here and what environments are we looking at? (15 min)
  * Niklas: Interested in WebViews - problems around compat and documentation
    * Found overlap talking to others in other spaces
    * Wanted to get a better sense of the bigger picture of environments outside of browser
  * Ben: Beyond the browser discussion is interesting: Webviews are special cases. They are part of the operating system in many cases. How do things like identity look when you can chat to the OS.
  * Sebastian: Working in the web of things area. This working group is mainly focusing not on the browser but rather on the thing talking to the web. Focus more on capabilities and ways to interact with those things.
    * Niklas: Also interested in this space.
  * Christoph: In the Audio WG - also working in the audio space in the web. Interested in if these APIs work outside of the web. Eg: node
  * Hadrien: Working at EDRLab on the Readium toolkits - work on epubs. Used by a few hundred readers. Relies on WebViews.
  * Derek: Work at Google on WebAssembly - this technology has a lot of embedders outside of the web. May in the future develop standards that apply outside of the web but not inside it.
  * Abhijeet: Working on the Chromium team - receive a lot of customization requests for things that are not quite a browser and not quite a WebView. Would be great to have some kind of standardization for something like this. Example: things like WebView2 on Windows.
  * Oliver (Chrome extensions): A lot of interesting overlap with extensions because we sometimes want to use web standards but we don’t always want to add back to this.
  * ?? (Oricle): Here to listen and understand
  * Ali (Google Chrome DevRel): Work with teams that do wasm and webrtc
  * Tetsuhiko Hirata (Hitachi): Work on web of things working group
  * Kunihiko Toumura (Hitachi): Working on the web of things working group
  * Nigel Megitt (BBC): Work in the accessibility space. A huge amount of the implementation of subtitle and caption and audio description web standards are through non-browser devices and pages on browsers via javascript, but these things are not implemented natively in browsers even if they’re web specs (e.g. IMSC, TTML etc).
  * Andreu Botella (Igalia / WinterCG): Think about which WebAPIs should apply to server side environments like NodeJS. Also focus on things where they would be more of a priority for the server side but still want to land them into the broader specs.
* Open discussion on discussion points (30 min)
  * Ben addressed Abhijeet about custom WebViews mentioning the WebView discussion yesterday. There are a bunch of mini app vendors that want to strip out a lot of web features.
    * Abhijeet: The use case I had in mind was vendors who want to display web content via a web view but want to customize the browser.
  * Hadrien: Challenges with epub. A lot of expectations that things should behave like a book. Eg: pagination, continue scrolling. Need to find ways of cheating this on platforms but it means orchestrating multiple webviews. The EU accessibility act means we need more TTS support; We need to ultimately serve this html content into something that can be read via a TTS engine. Expect other accessibility acts to drive more.
  * Nigel Megitt (BBC): Wanted to call out - I see a perception issue with promoting these environments. We often call it the user agent, not the browser. But the browser has become the big focus of user agents.
    * Niklas: I also find this space the most interesting question in this space. WebView feels often like an afterthought.
    * Ben: the Privacy and security model for browsers is totally different in environments as WebViews
  * Andreu Botella: Find it interesting that the html spec  not developed in W3C but in WHATWG) initially supported conformance checkers as user agents but overtime this has shifted away. The question is how do we work with the W3C to fit our needs. In the WinterCG, we’ve had more luck with things that overlap with browser interests - not explicitly out of scope. Use service workers to often justify our work. This of course would not work for things like WebViews. There is a non standardization for server side environments that is hard to describe in W3C specs. The question is how we make them pay attention to the use cases we care about.
  * Elika Etemad (CSS WG): Wanted to talk about collaboration with epub WG. This happened because we had dialogue with the epub WG. This helped us understand why this work was important. The non traditional environments have to engage with the WGs that they have needs from. If the WGs are not aware of the challenges, the work won’t get taken into account. We had joint members and joint meetings which helped a lot. I was working on reading mode at the time and also joined the epub group to take away from their needs.
  * Elika Etemad (CSS WG): TTML WG came to us with a number of requests and questions but there was no follow up with the implementation. There are two aspects of the work, part one is standardizing but part two is the actual implementation. The browsers are open source at this point, the community can contribute if they are interested in getting these features landed.
    * Nigel Megitt (BBC): Was thinking about that same example. It feels like a high barrier to entry to get these changes implemented because these are big code bases. We talked to Igalia and it was difficult to get this onto their workstreams too. Some of the features are simple within the browser, but very difficult to implement in Javascript. Also not clear how open the code is with the open source code versus code being distributed for browsers being embedded. Deployment cycles are also a challenge here because things take a long time to ripple through.
    * Niklas: What I always find to do. The standards come out but they don’t always apply to all environments because there are additional privacy security considerations outside of the standard.
    * Nigel: Related, things like testing and certification. At the BBC, we run certification tests to check the capabilities of the devices. Running interoperability tests on embedded devices is much harder. In the embedded world, running tests often have to be done differently.
  * Luke Wagner: There is also an emerging category of web assembly based environments that are not web but want the ease of use. IOT examples. A lot of work has gone into providing language agnostic bindings to support these environments. This is ongoing in the web assembly CG.
    * Andreu Botella: It doesn’t seem easy to adopt the javascript bindings to other languages environments.
    * Luke: The ongoing web IDL bindings work is really a distilled language agnostic IDL to more effectively create bindings in different languages.
  * Andreu Botella: WinterCG is also interested in testing challenges. Looking into a subset of WPTs that can be run in server side environments. This is of course much easier than BBCs problems. We will need to create a new test runner for these environments. WPT has been written primarily for browsers - not sure if there would be any changes necessarily that would benefit the BBC case.
  * Nigel Megitt (BBC): Some of the things that are not covered in browsers, don’t have WPTs.
  * Ben: Make identity sharing in Webviews better. Challenge is that the specs will often treat talking to the platform as a black box so it is hard to also write tests for this.
    * Andreu Botella: WPTs use web driver. Not sure if something is available to use for places like WebViews.
    * Ben: Challenging is lack of conformance for debugging protocols.
  * Nigel Megitt (BBC): Another browser / non browser difference in behavior. Differences in refresh cycles is a massive challenge. Embedded systems often only get a few shots to do updates. Would be great to find a way to be patient in the community.
* Close up with minutes, follow up items, results etc. (10 min)
