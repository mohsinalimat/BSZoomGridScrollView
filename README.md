# BSZoomGridScrollView

[![CI Status](https://img.shields.io/travis/boraseoksoon/BSZoomGridScrollView.svg?style=flat)](https://travis-ci.org/boraseoksoon/BSZoomGridScrollView)
[![Version](https://img.shields.io/cocoapods/v/BSZoomGridScrollView.svg?style=flat)](https://cocoapods.org/pods/BSZoomGridScrollView)
[![License](https://img.shields.io/cocoapods/l/BSZoomGridScrollView.svg?style=flat)](https://cocoapods.org/pods/BSZoomGridScrollView)
[![Platform](https://img.shields.io/cocoapods/p/BSZoomGridScrollView.svg?style=flat)](https://cocoapods.org/pods/BSZoomGridScrollView)

BSZoomGridScrollView is a powerful, pure swift iOS UI framework that provides the awesome grid scrollview containing your image array that are able to zoom, tracking your touch area.<br>

Screenshots
-----------

![Alt Text](https://media.giphy.com/media/jS7ZYuYXRtPk6lHp5F/giphy.gif)

![BSZoomGridScrollView Screenshot](https://firebasestorage.googleapis.com/v0/b/boraseoksoon-ff7d3.appspot.com/o/BSZoomGridScrollView%2Fs4.png?alt=media&token=111d96f0-317c-49f0-b115-fb1592ab6299)

Youtube video URL Link for how it works: <br>
[link0](https://youtu.be/QTB7GqZL-L8)

At a Glance
-----------

```swift

/// 🥳 # Step1: let's import!
import BSZoomGridScrollView

struct ContentView: View {
    var itemsToZoom: [Any] = {
        return (0...1500).compactMap { _ in UIImage(systemName: "smiley") }
    }()

    var body: some View {
        /// 😊 # Step2. That's it. completed!
        BSZoomGridScrollView(itemsToZoom: itemsToZoom,
                             powerOfZoomBounce: .regular,
                             isBeingDraggingOnItem:{ selectedImage in
                                ///
                             },
                             didLongPressItem: { selectedImage in
                                ///
                             },
                             didFinishDraggingOnItem: { selectedImage in
                                ///
        })
        .edgesIgnoringSafeArea(.all)
    }
}

```

## Features

- [x] Designed for SwiftUI, SwiftUI 100% is supported.
- [x] Complex grid ScrollView UI is provided out of box.
- [x] Tracking user touch area on the grid scrollview, Zooming items is done out of box.
- [x] BSZoomGridScrollView will return an image selected by a user, detected by the internal long press and pan gesture inside out of box. 
- [x] Grid UI can be styled for number of columns, rows, zoom effect and images you would like to input to show in the grid.

<br>

## Example

To run the example project, clone the repo, and run `pod install` from the Example directory first.
It includes examples for UIKit as well as SwiftUI.

## Requirements

- iOS 13.0 or later
- Swift 5.0 or later
- Xcode 11.0 or later


Getting Started
--------------- 

* SwiftUI

```Swift

import SwiftUI

/// 🥳 # Step1: let's import!
import BSZoomGridScrollView

struct ContentView: View {
    var itemsToZoom: [Any] = {
        return (0...1500).compactMap { _ in UIImage(systemName: "smiley") }
    }()

    var body: some View {
        /// 😊 # Step2. That's it. completed!
        BSZoomGridScrollView(itemsToZoom: itemsToZoom,
                             powerOfZoomBounce: .regular,
                             isBeingDraggingOnItem:{ selectedImage in
                                ///
                             },
                             didLongPressItem: { selectedImage in
                                ///
                             },
                             didFinishDraggingOnItem: { selectedImage in
                                ///
        })
        .edgesIgnoringSafeArea(.all)
    }
}

```

* UIKit
```Swift

///
/// To use BSZoomGridScrollView,
/// Please, Follow steps written in the comments with icon like 😀.
///

import SwiftUI
import UIKit

///
// 😚 #Step1: import BSZoomGridScrollView!
///
import BSZoomGridScrollView

class ViewController: UIViewController {
    ///
    // prepare any item array to feed to BSZoomGridScrollViewController.
    ///
    private var itemsToZoom: [Any] = {
        return (0...1500).compactMap { _ in UIImage(systemName: "smiley") }
    }()
    
    
    ///
    // 😋 #Step2: declare BSZoomGridScrollView
    ///
    private lazy var zoomGridScrollViewController: BSZoomGridScrollViewController = { [unowned self] in
        ///
        /// It can be used on both SwiftUI and UIKit.
        /// To see how it works on SwiftUI,
        /// please refer to comments in SwiftUI directory -> ContentView.swift
        ///
        return BSZoomGridScrollViewController(itemsToZoom: self.itemsToZoom,
                                              powerOfZoomBounce: .regular,
                                              scrollEnableButtonTintColor: .black,
                                              scrollEnableButtonBackgroundColor: .white,
                                              isBeingDraggingOnItem:{ [unowned self] selectedImage in
                                                 ///
                                              },
                                              didLongPressItem: { [unowned self] selectedImage in
                                                ///
                                              },
                                              didFinishDraggingOnItem: { [unowned self] selectedImage in
                                                ///
                                              })
    }()
    
    ///
    // 😁 #Step3: Present it!
    ///
    @IBAction func goToBSZoomGridScrollView(_ sender: Any) {
        ///
        // 😎 That's all. well done.
        ///
        self.present(zoomGridScrollViewController,
                     animated: true,
                     completion: nil)
    }
    
    ///
    // MARK: - ViewController LifeCycle Methods
    ///
    override func viewDidLoad() {
        super.viewDidLoad()
    }

    override func didReceiveMemoryWarning() {
        super.didReceiveMemoryWarning()
    }
}

```

## Installation

There are four ways to use BSZoomGridScrollView in your project:
- using CocoaPods
- using Swift Package Manager
- manual install (build frameworks or embed Xcode Project)

### Installation with CocoaPods

[CocoaPods](http://cocoapods.org/) is a dependency manager for Objective-C, which automates and simplifies the process of using 3rd-party libraries in your projects. See the [Get Started](http://cocoapods.org/#get_started) section for more details.

#### Podfile

First, 
```ruby
pod 'BSZoomGridScrollView'
```
then in your root project,
```ruby
pod install
```

### Installation with Swift Package Manager (Xcode 11+)

[Swift Package Manager](https://swift.org/package-manager/) (SwiftPM) is a tool for managing the distribution of Swift code as well as C-family dependency. From Xcode 11, SwiftPM got natively integrated with Xcode.

BSZoomGridScrollView support SwiftPM from version 5.1.0. To use SwiftPM, you should use Xcode 11 to open your project. Click `File` -> `Swift Packages` -> `Add Package Dependency`, enter [BSZoomGridScrollView repo's URL](https://github.com/boraseoksoon/BSZoomGridScrollView). Or you can login Xcode with your GitHub account and just type `BSZoomGridScrollView` to search.

After select the package, you can choose the dependency type (tagged version, branch or commit). Then Xcode will setup all the stuff for you.

If you're a framework author and use BSZoomGridScrollView as a dependency, update your `Package.swift` file:

```swift
let package = Package(
    dependencies: [
        .package(url: "https://github.com/boraseoksoon/BSZoomGridScrollView", from: "0.1.1")
    ],
    // ...
)
```

## Author

boraseoksoon@gmail.com

## License

BSZoomGridScrollView is available under the MIT license. See the LICENSE file for more info.


## More screenshots..

![BSZoomGridScrollView Screenshot](https://firebasestorage.googleapis.com/v0/b/boraseoksoon-ff7d3.appspot.com/o/BSZoomGridScrollView%2FBSZoomGridScrollView.png?alt=media&token=062257fc-2aeb-498f-aa33-b179f5e1656b)

![BSZoomGridScrollView Screenshot](https://firebasestorage.googleapis.com/v0/b/boraseoksoon-ff7d3.appspot.com/o/BSZoomGridScrollView%2Fs5.png?alt=media&token=396b4703-17cf-4411-a137-10ff516b9aac)

![BSZoomGridScrollView Screenshot](https://firebasestorage.googleapis.com/v0/b/boraseoksoon-ff7d3.appspot.com/o/BSZoomGridScrollView%2FBSZoomGridScrollView02.png?alt=media&token=2af6a309-dd1b-4aa5-a63e-10900011681f)

