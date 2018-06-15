# Swift 4 and Xcode 9 Walkthrough

After struggling to find the right tutorials for **Swift 4 & Xcode 9** environment and to find good tutorials to fit my level (with some development experience but no mobile programming), I thought to share steps I took on my *Macbook Pro*. 

I truly hope these steps I took can save you lots of time to get your hands on iOS. If you have any suggestions, please feel free to share with [me](mailto:melarisong@hotmail.com). I'll try to update if I find any more useful resources. 

---
> <small>Big credit goes to *[Make School](http://makeschool.com)*. By having no affiliation with Make School, if Make School wants me to remove this walkthrough, please let [me](mailto:melarisong@hotmail.com) know.</small>

---

Below are the ordered steps I took to learn and practice **Swift 4 on Xcode 9**.


#### 1. [Food Tracker](https://developer.apple.com/library/content/referencelibrary/GettingStarted/DevelopiOSAppsSwift/) by Apple

"Start developing iOS Apps (Swift)" says Apple. We're going program in a programmingn language developed **by Apple** on an integrated developement environment developed **by Apple**. Hence, why don't we try the creator's tutorial? 

Being said, this tutorial is quite thorough from building a basic UI to persisting data, but few areas are not updated to the latest. Encountering these outdated ones is definitely not pleasing, but trust me. Finding and solving these mismatched ones will bring you to the next level to move onto the next tutorial.


#### 2. [Tip Calculator](https://www.makeschool.com/online-courses/tutorials/build-a-tip-calculator-in-swift-4/implementing-subviews) by [Make School](https://www.makeschool.com)

"Auto-layout", "relative-positioning", etc all confused me from [Food Tracker](https://developer.apple.com/library/content/referencelibrary/GettingStarted/DevelopiOSAppsSwift/). Yes, I do understand these are important since we have multiple screen sizes. This [Tip Calculator](https://www.makeschool.com/online-courses/tutorials/build-a-tip-calculator-in-swift-4) tutorial from Make School helped me understand the concept and get used to Xcode GUI.  


#### 3. [JSON & APIs](https://www.makeschool.com/online-courses/tutorials/json-apis-in-swift-4/parsing-json) by [Make School](https://www.makeschool.com)

You might be wondering like I was: How do I do HTTP network? This [JSON & APIs](https://www.makeschool.com/online-courses/tutorials/json-apis-in-swift-4) tutorial from Make School introduces you a popular library [SwiftyJSON](https://github.com/SwiftyJSON/SwiftyJSON) for parsing JSON and [Alamofire](https://github.com/Alamofire/Alamofire) to call APIs.

The downloadable workspace will let you utilize these libraries without worrying about integrating them.

---
## Integrating Libraries

Ok, then how do we integrate libraries? There are multiple ways, but [CocoaPods](https://cocoapods.org) will be explained here for now. 

Integrating libraries to Xcode seemed to be quite complicated due to complex depencies here and there. CocoaPod is a dependency manager for Swift, and most libraries I've tried are on CocoaPods so far. 

In order to get used to this CocoaPods, I tried to integrate [Google Firebase](https://firebase.google.com) and Apple's iOS Swift 4. However, none of the tutorials nor guides were synced/up-to-date! <small>The reason to choose Firebase is that my team relies on Ember.js and Firebase.</small>

### Firebase + iOS Swift 4

These are the steps I took to integrate *successfully*: 

* Create Xcode project
> * remember your **Bundle Identifier**
> * ex: com.company.example)
* Close the project

* Go to your Xcode project path/ on Terminal
```
pod init
vim Podfile
```
Once Podfile is opened, you'll see "```#pods for <project name>```"
```
#Pods for MapoTofu
pod 'Firebase/Core'
pod 'Firebase/Auth'
pod 'FirebaseUI/Auth'
pod 'Firebase/Database'
pod 'Firebase/Storage'
```

My project name is ```MapoTofu``` in the example above. <small>I love mapo tofu!</small>

To intergrate [SwiftyJSON](https://github.com/SwiftyJSON/SwiftyJSON#integration) and [Alamofire](https://github.com/Alamofire/Alamofire#installatio://github.com/Alamofire/Alamofire#installation), 

```
pod 'SwiftyJSON', '~> 4.0'
pod 'Alamofire', '~> 4.7'
```
* Save & close vim. 
* Install with ```pod install``` command. 
> * Did it succeed?

* Create a Firebase project 
> * Add Firebase to your iOS app
> > * with the same bundle identifier from above.
> * follow Firebase's iOS instruction **until**
> > * "Run your app to verify installation"
> * Let Firebase continue looking for your iOS project.
* Go to your Xcode project on Finder and open **.xcworkspace** instead of **.xcodproj**.
* Once loaded, build the project.
* Check on Firebase.
> * Did Firebase successfully communicate with your iOS project? 

---

#### 4. [Build Notes](https://www.makeschool.com/online-courses/tutorials/learn-how-to-build-make-school-notes-in-swift-4/) by [Make School](https://www.makeschool.com/) 

This tutorial might seem like a duplicate of Apple's Food Tracker tutorial. I found this tutorial helpful as a reviewing tool. While reviewing, *navigation between view controllers* made more sense from this tutorial, and this seems to introduce a different way to manage core data. 

[Core Data](https://medium.com/xcblog/core-data-with-swift-4-for-beginners-1fc067cca707) is a framework provided by Apple to manage the model layer object in iOS application. Core Data uses SQLite but not a database. For me, since I prefer to keep my notes local (not in the cloud), this tutorial app is installed on my iPhone for my own use. 


#### 5. [Build a Photo Sharing App](https://www.makeschool.com/online-courses/tutorials/build-a-photo-sharing-app-9f153781-8df0-4909-8162-bb3b3a2f7a81/) by [Make School](https://www.makeschool.com/)

This tutorial walks you to build an **Instagram-like app** with Google Firebase! This could be considered a long one, but I'd say it's the most complete tutorial I've found so far: from user authentication to handling Firebase database. 

I believe I'm 90% completion to this tutoria, so please stay tuned for the summary.

---
## Others
<small>The below are the tools I used to create this README.</small>

#### Marked
[Marked2](http://marked2app.com) is a previewer app for Markdown files. *Marked* is used with Terminal to review everytime this README is saved. 

#### Markdown Cheatsheet
Special thanks to [Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet). This website is treated as my bible. 

