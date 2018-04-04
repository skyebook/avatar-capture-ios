# avatar-capture-ios

## What is AvatarCapture?
Writing a ground-up solution for taking profile pictures in iOS can be a pain and time consuming. AvatarCapture is a Swift based library inspired by [ZCSAvatarCapture](https://github.com/zshannon/ZCSAvatarCapture) whose purpose is to make it as easy as possible to start your camera(front facing or rear), allow you to snap a photo or choose a photo from your Photos library.

## Installation
Edit your PodFile:        
`pod 'AvatarCapture', '1.0.0'`

Then run `pod install`

## Features
- Display an existing `UIImage`
- Start the iPhone camera for capture
- Swap cameras from front facing to rear and vice versa
- Choose a photo from the iPhone library

## Plans
- allow more flexibility in where buttons are positioned
- add custom elements/subviews
- Change/choose shape of avatar profile

## Getting Started
Getting started with AvatarCapture is super easy!

First, initialize the view controller(anywhere but `viewDidLoad` is common):
```
 let avatarCaptureController = AvatarCaptureController()
 avatarCaptureController.delegate = self
 avatarCaptureController.image = UIImage.init(named: "an_existing_image.png")
 avatarView.addSubview((avatarCaptureController?.view)!)
```

`AvatarCaptureController` subscribes to `AvatarCaptureControllerDelegate` and is required for retrieving the UIImage after selecting a photo

In this example, `avatarView` is a UIView defined in a storyboard. Whatever the `width` and `height` of this UIView is will determine the dimensions of the avatar.

## How do I get my image?
Once you've subscribed to the `AvatarCaptureControllerDelegate` protocol, you can be notified when an image was selected and when the image selection was cancelled:

```
extension MyViewController: AvatarCaptureControllerDelegate {
    func imageSelected(image: UIImage) {
        print("image Selected")
    }
    
    func imageSelectionCancelled() {
        print("image selection cancelled")
    }
}
```

## AvatarCapture In Action
Don't I look excited...?    
![Capture](https://github.com/gatewayapps/avatar-capture-ios/blob/master/AvatarCapture/AvatarCapture/capture_me.gif)

## Feedback
Please feel free to create issues if bugs are found or if enhancements or new features are desired
