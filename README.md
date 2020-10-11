# ALProgressRing



<img align="left" src="https://github.com/alxrguz/ALProgressRing/blob/main/Assets/PreviewBanner.gif" width="450"/>

### About



<br/>

If you liked this library, please do not forget to put a `★ star`, it will help me in its development.
<br/>

<br/>

## Navigation

- [Requirements](#requirements)
- [Installation](#installation)
  - [Swift Package Manager](#Swift-Package-Manager)
  - [CocoaPods](#CocoaPods)
  - [Manually](#Manually)
- [Usage](#usage)
  - [Quick Start](#Quick-Start)
  - [Customization](#Customization)
    - [Colors](#colors)
    - [Fonts](#Fonts)
    - [Layout](#Layout)
- [License](https://github.com/SnapKit/SnapKit#license)

## 

## Requirements

- iOS 10.0 + 
- Swift 4.2 +



## Installation

#### Swift Package Manager

The [Swift Package Manager](https://swift.org/package-manager/) is a tool for managing the distribution of Swift code. It’s integrated with the Swift build system to automate the process of downloading, compiling, and linking dependencies.

To integrate **ALProgressRing** click `File -> Swift Package -> Add Package Dependency` and insert:

```ogdl
https://github.com/alxrguz/ALProgressRing
```

#### CocoaPods

**ALProgressRing** is available through [CocoaPods](http://cocoapods.org/). To install it, simply add the following line to your Podfile:

```ruby
pod 'ALRadioButtons'
```

#### Manually

If you prefer not to use either of the aforementioned dependency managers, you can integrate SnapKit into your project manually. Put `Source/ALProgressRing` folder in your Xcode project. 



## Usage

#### Quick Start

```swift
import ALProgressRing

class MyViewController: UIViewController {

    private lazy var progressRing = ALProgressRing()

    override func viewDidLoad() {
        super.viewDidLoad()

        view.addSubview(progressRing)
        // ... Setup layout
        progressRing.translatesAutoresizingMaskIntoConstraints = false
        progressRing.centerXAnchor.constraint(equalTo: view.centerXAnchor).isActive = true
        progressRing.centerYAnchor.constraint(equalTo: view.centerYAnchor).isActive = true
      // Make sure to set the view size
        progressRing.widthAnchor.constraint(equalToConstant: 180).isActive = true
        progressRing.heightAnchor.constraint(equalToConstant: 180).isActive = true
        
        progressRing.setProgress(0.8, animated: true)
    }
}
```



#### Customization

#### Colors

You can customize the buttons, headers and indicators colors depending on their state.

```swift
/// Set track color
/// If you don't need a gradient, just set the same values for `startColor` and `endColor`
progressRing.startColor = .systemPink 
progressRing.endColor = .systemRed 

/// Set groove color
progressRing.endColor = .systemRed 
```



#### Layout

```swift
progressRing.startAngle = -.pi / 2 // The start angle of the ring to begin drawing.
progressRing.endAngle = 1.5 * .pi // The end angle of the ring to end drawing. 
progressRing.startGradientPoint = .init(x: 0.5, y: 0) // The starting poin of the gradient
progressRing.endGradientPoint = .init(x: 0.5, y: 1) // The ending position of the gradient.
```



#### Animation

```swift
progressRing.duration = 2 // Duration of the ring's fill animation.
progressRing.timingFunction = .easeOutExpo // Timing function of the ring's fill animation.

// The following use of setProgress (_ value: Int, animated: Bool) will take into account the new parameters 
progressRing.setProgress(0.8, animated: true)
```

Let's take a look at the `timingFunction` parameter, it is of type `ALTimingFunction`, which contains the following types of animations:

<img src="https://github.com/alxrguz/ALProgressRing/blob/main/Assets/timingFunctions.png"/>

There is a good cheat sheet available [here](http://easings.net/).

## License

**ALRadioButtons** is under MIT license. See the [LICENSE](https://github.com/alxrguz/ALRadioButtons/blob/master/LICENSE) file for more info.