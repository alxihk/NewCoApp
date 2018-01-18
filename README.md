# NewCo App (for iOS)
## Version
 1.0

## About NewCo App

 NewCo App for iOS enables authorized users to visualize, buy and review our productsand Conekta, receive notifications about offers and promo codes.

## Build Requirements
+ Xcode 8.0
+ iOS 10.0 SDK
+ Swift 3.0
+ A developer apple account to build on device

## Runtime Requirements
+ iOS 9.3 and further

## Frameworks

The frameworks imported with pods are:

+ **Alamofire** (4.4 Performm network requests)
+ **SwiftyJSON** (3.1.4 Parse json results)
+ **Fabric** (Report app crash events)
+ **Crashlytics** (Report app crash events)

The frameworks imported directly on the project are:

+ **FBSDKCoreKit** (4.22 Facebook Analytics)
+ **FBSDKLoginKit** (4.22 Facebook Analytics)
+ **FBSDKShareKit** (4.22 Facebook Analytics)
+ **Bolts** (4.22 Facebook Analytics)
+ **Stripe** (Process card payments)


## Project Structure

 NewCo App project is programed with an adaptation of clean architecture, the use cases are abstracted as scenes
 and each scene is composed of the following files:

+ **ViewController**: manages the ui interaction and displays ui elements, receives the events from the user and passes the required info the the interactor.

+ **Interactor**: it is in charge to perform the business logic to the provided information and get the requested information by the ViewController, when there is a response ready it tells the ViewController to update the UI with the corresponding information.

+ **Worker**: When a connection to a datasource is requiered the *Interactor* uses a Worker to retrieve or send data to the corresponding data source.

+ **APIManager**: it is in charge to perform a connection to the API endpoints to get and send information.


 The source is included on NewCoApp directory and it is subdivided this way:

 * **Resources**: includes the design assets used for the app.
 * **Common**: it includes classes that are of common use on all the project like utils, constants, local data, and entity objects.
 * **Scenes**: includes the files for all the use cases and it include all the directories listed down:
  * **Login**: includes the login features.
  * **RecoverPassword**: includes the recover password features.
  * **Dashboard**: includes files for the app dashboard (menu).
  * **Profile**: includes files for the user profile features.
  * **Products**: includes files to list our products.
  * **ProductDetail**: includes files to show a product detail and perform a purchase.
  * **Orders**: includes files to show current orders.
  * **OrderDetail**: includes files to show the purchase order detail.
  * **Purchase**: includes files to show the purchase detail and add a promotional code.
  * **PaymentMethods**: includes files to list and select a payment method.
  * **Card**: includes files to register a card.
  * **Success**: includes files to show a successful purchase, print tickets and send email.
  * **Cancel**: includes files to cancel a purchase order and register the reason on the backend.
  * **Cancelled**: includes files to show a cancelled purchase.

> On each source code file there is included a description with the purpose
> of the class, navigate to each one of them to get more information for what
> it does and which screen does it serve.

## Project configuration values

The key values to configure the project are contained on the Info.plist file and the values that should be defined at code level are included as constants on the Constants.swift file under PosBoletia>Common>Utils.

## License
NewCo App iOS is released under the MIT license.