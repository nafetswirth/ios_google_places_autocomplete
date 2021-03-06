# GooglePlacesAutocomplete

[![Build Status](http://img.shields.io/travis/watsonbox/ios_google_places_autocomplete.svg?style=flat)](https://travis-ci.org/watsonbox/ios_google_places_autocomplete)
[![CocoaPod](https://img.shields.io/cocoapods/v/GooglePlacesAutocomplete.svg)](http://cocoadocs.org/docsets/GooglePlacesAutocomplete/)

A simple [Google Places API](https://developers.google.com/places/documentation/autocomplete) autocompleting address entry view for iOS devices.

There are already a couple of solutions out there for this. GooglePlacesAutocomplete is different because it is 100% Swift, and aims to provide the simplest possible method of entering validated, autocompleted addresses.

No attempt has been made to integrate MapKit since displaying Google Places on a non-Google map is against their terms of service.

<table width="100%">
  <tr>
    <td align="left"><img src="Screenshots/view.png"/></td>
    <td align="right"><img src="Screenshots/search.png"/></td>
  </td>
</table>

----------


## Requirements

- iOS 7.0+
- XCode 6.1


## Installation

> **Embedded frameworks require a minimum deployment target of iOS 8.**
>
> To use GooglePlacesAutocomplete with a project targeting iOS 7, you must include the source files directly in your project. See the ['manual installation'](#manual) section for instructions.

### CocoaPods

[CocoaPods](http://cocoapods.org) is a dependency manager for Cocoa projects.

CocoaPods 0.36 beta adds supports for Swift and embedded frameworks. You can install it with the following command:

```bash
$ gem install cocoapods --pre
```

To integrate GooglePlacesAutocomplete into your Xcode project using CocoaPods, specify it in your `Podfile`:

```ruby
source 'https://github.com/CocoaPods/Specs.git'
platform :ios, '8.0'

pod 'GooglePlacesAutocomplete'
```

Then, run the following command:

```bash
$ pod install
```

### Manual

Simply copy `GooglePlacesAutocomplete.swift` and `GooglePlacesAutocomplete.xib` to your project.

Note: Don't forget to add the PoweredByGoogle image to your xcassets.


## Usage

```swift
import GooglePlacesAutocomplete // Not required when including source files directly in project

let gpaViewController = GooglePlacesAutocomplete(
  apiKey: "[YOUR GOOGLE PLACES API KEY]",
  placeType: .Address
)

gpaViewController.placeDelegate = self // Conforms to GooglePlacesAutocompleteDelegate

presentViewController(gpaViewController, animated: true, completion: nil)
```

`GooglePlacesAutocompleteDelegate` supports three methods:

- `placesFound(places: [Place])`: Invoked whenever the Google Places API is called
- `placeSelected(place: Place)`: Invoked when a new place is selected
- `placeViewClosed()`: Invoked when the view is closed

Here's a [complete example](https://github.com/watsonbox/ios_google_places_autocomplete/blob/master/GooglePlacesAutocompleteExample/GooglePlacesAutocompleteExample/ViewController.swift).


## Contributing

1. Fork it ( https://github.com/watsonbox/ios-google-places-autocomplete/fork )
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create a new Pull Request
