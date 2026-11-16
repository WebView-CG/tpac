# Thinking outside the browser - More coordination for better web standards for embedding TPAC 2026

Nov. 11, 2025 08:30 GMT+9

Link: https://bit.ly/webview-cg-2510

Notes on GitHub: https://github.com/WebView-CG/tpac/blob/main/TPAC-2026/Breakout/ThinkingOutsideTheBrowser.md

## Session goals

A plan on how to do more and regular coordination between browsers, embedded contexts and more

Bring together:

* MiniApps
* WebViews
* Embedded Web Engines & Native Web Runtimes
* Embeeded Browsers like WPE WebKit
* Sub Apps API
* TAG
* more

### Attendees

* [Niklas Merz](mailto:niklasmerz@apache.org) (Apache Cordova) @niklasmerz  
* [Brian Kardell](mailto:bkardell@gmail.com) (Igalia) @bkardell  
* Martin Alvarez (Huawei) @espinr   
* Seokho Song (Igalia)  
* [Patryk Chodur](mailto:pchodur@google.com) (Google) @pchodur  
* Euclid Ye (Huawei) @yezhizhen  
* Xiaoqian Wu (W3C)  
* Wei Ding (Huawei)  
* Jing Shen (Huawei)  
* Jingshi Shangguan（Huawei）  
* Hyojin Song (LG Electronics)  
* Greg Whitworth (Microsoft)  
* Guangzhen Li (Huawei)  
* Zgroza Klimek (Google)  
* Jan Jaap de Groot (Abra / Mobile Accessibility Task Force)  
* Tanya van Workum (Abra / Mobile Accessibility Task Force)  
* Omprakash Selvaraj (Portable web content format community group)  
* Chunming Hu (W3C)


### Scribes

Martin Alvarez

### Agenda

- **Introductions**  
  - Admin  
  - Intros  
    - The Web Platform at 128MB: an embedder's view ([slides](https://docs.google.com/presentation/d/1nM5DVImx2pig6a6Xc34JA1j8NxQUjQBFvP8GqiNsQdM/))  
    - The MiniApps perspective  
    - The embedders perspective (Servo)  
    - **Your introduction..**

### Minutes

- **Introductions & Administriva**  
  - Objectives: we have discussing about topics like MiniApps, WebViews,... in previous TPACs. We need to keep the conversation.  
  - We have the same targets, let’s solve together.  
- MiniApps:  
  - Perspective from MiniApps WG  
  - Running in webviews, extending engines, using subsets of standards  
  - Needed new security model to be aligned with W3C standards.  
- IWA (Isolated Web Apps):  
  - Google’s team focused on this new installable and distributable web apps.  
  - Something in between Electron and PWAs  
  - Incubating within WICG, including Web Bundles  
- Igalia:  
  - Working on browser engines (WPE, stewards of Servo, embedded systems with Chrome)  
  - Interested in this activity. What is this? Not the Web exactly, but at some point it is.  
  - Not reinventing things and learn from each other.  
- LG’s:  
  - Developing embedded platform.  
  - Facing challenges that will be shared in the session.  
  - Hyojin’s Song showing slides (The Web platform at 128MB)  
    - Difference between PC/Mobile and embedded devices in terms of capabilities  
    - NevaOSS is a fork of Chromium optimized for embedded devices [https\://github.com/nevaoss](https://github.com/nevaoss)   
    - Challenges:  
      - Reduce the footprint of web apps  
      - Cross-platform frameworks are strong alternatives (e.g., Flutter)  
      - Considering lightweight solutions (e.g., Servo) but they are limited  
    - How to build a lightweight Web solution  
      - Web to native bindings (20 MB footprint)  
      - Use other lightweight browsers (50\~100 MB) \- like AI browsers  
    - Fragmentation of standards is a problem  
  - Discussion points:  
    - WebViews CG could support developing test suites for lightweight runtimes?  
    - Definition of a light runtime for low-end devices  
    - Alignment with with IWA, MiniApps, Web embedders?  
  - Xiaoqian: Why do we need a new test suite for lightweight runtimes?  
    - Showing [https\://blitz.is/wpt](https://blitz.is/wpt)   
      - A guideline from W3C could serve as reference for the vendors.  
    - Several to compare: [https\://wpt.fyi/results/?product=chrome%5Bexperimental%5D\&product=edge%5Bexperimental%5D\&product=firefox%5Bexperimental%5D\&product=safari%5Bexperimental%5D\&product=servo\&product=wpewebkit](https://wpt.fyi/results/?product=chrome%5Bexperimental%5D&product=edge%5Bexperimental%5D&product=firefox%5Bexperimental%5D&product=safari%5Bexperimental%5D&product=servo&product=wpewebkit)   
  - Jet: If you do customizations, do you contribute Chromium upstream?  
  - Hyojin: We have 100+ new features pushed to upstream.   
    - We try to provide our spec to W3C and push them also to upstream  
    - But most of the downstream features are dedicated to our platform  
  - Jet: On the web we have limitations like fingerprint authentication.   
    - We can extend the functionality of the native app, but we don’t have the standard of the content (app) itself, neither the baseline of the runtime.  
    - Packaging is also heterogeneous across platforms  
    - MiniApp vendors (e.g., Bilibili) are creating their own runtime and they distribute them.  
    -   
  - Greg: You mentioned several examples. I would like to have the same UX in all my devices. How we can prioritize it?    
    - It will be interesting to understand the real use cases and their requirements in terms of features.  
  - Hyojin: The use cases depend on the product.   
  -   
  - Euclid: For your use cases, you should create a tailor–made engine instead of forking Chromium.    
  -   
  - Shubham: Blitz provides a set of features. Do you have a similar set of features you require?  
  - Hyojin: Some features already in WPT, but also our own customized features.  
    - I’m aware of other vendors with the same issues.  
  -   
  - Brian: WPE is another engine for embeddings with very good scores (on par with Firefox) too.  
    - We can support too.   
    - We need to find small things to start the activities (discussed for long time)  
  - Niklas: Right. We need to clarify the scope and next actions  
    - Several ideas on the screen (slide 6\)  
  - JJ: Accessibility: Interesting to understand existing issues in webviews across the different platforms & native. Accessibility is an interesting topic for us.  
    - How to pass the accessibility info between native and webview content.  
  - Chumming: Embedding means constraints in terms of resources.   
    - Area to explore in new devices like watches and home appliances.  
    - Reuse what W3C has.   
    - Suggestion of using “embedding”.   
- Servo:  
  - Using the same WPT benchmarks than other browsers  
  - Presentation (add slides here)   
    - Embedable web browser.  
    - Demo comparison between ArkWeb (Chromium) and Servo engines.  
  - Good to see the evolution of Servo.  
- Next steps:  
  - Could we focus on some concrete activity?  
  - Let’s start by a questionnaire to understand the priorities of the stakeholders here.  
  - Later we can see if we create a new group.

### Action items

- To share survey with participants and community for next steps.

