## ReProvision
[![FOSSA Status](https://app.fossa.com/api/projects/git%2Bgithub.com%2FDaddycal69%2FReProvision.svg?type=shield)](https://app.fossa.com/projects/git%2Bgithub.com%2FDaddycal69%2FReProvision?ref=badge_shield)


This project provides automatic re-provisioning of iOS and tvOS applications to avoid the 7-day expiration associated with free certificates, along with a macOS application to manually provision a given `.ipa` file.

### WARNING

This project is currently functional, but I won't be providing further updates. However, I am more than happy to review/accept pull requests, and then publish those as updates.

Users: if you want automatic re-signing, it is strongly recommended to look at AltServer/AltStore.

### Features

Provisioning is undertaken via the user's Apple ID credentials, and supports both paid and free development accounts. These credentials are stored in the user's Keychain for subsequent re-use, and are only sent to Apple's iTunes Connect API for authentication.

#### iOS

- Automatic re-signing of locally provisioned applications.
- Basic settings to configure alerts shown by the automatic re-signing.
- Ability to install any `.ipa` file downloaded through Safari from the device.
- Support for re-signing Apple Watch applications.
- 3D Touch menu for starting a new re-signing routine directly from the Homescreen.

Battery optimisations are also in place through the usage of a background daemon to handle automatic signing.

Please note that only jailbroken devices are supported at this time. Follow [issues/44](https://github.com/Matchstic/ReProvision/issues/44) for progress regarding stock devices.

#### tvOS [TODO]

- Automatic re-signing of locally provisioned applications.
- Basic settings to configure alerts shown by the automatic re-signing.
- Ability to install any `.ipa` file downloaded to the device.

#### macOS [N/A]

- Not viable with this codebase. See AltDeploy instead: https://github.com/pixelomer/AltDeploy

### Pre-Requisites

~~For compiling the iOS project into a Debian archive, `ldid2` and (currently) `iOSOpenDev`. I plan to integrate these two dependencies into this repository.~~ These are now integrated into this repository under `/bin`.

CocoaPods is also utilised.

### Building

To build this project, make sure to have the above pre-requisites installed.

1. Clone the project; `git clone https://github.com/Matchstic/ReProvision.git`
2. Update CocoaPods, by running `pod install` in the project's root directory.
3. Open `ReProvision.xcworkspace`, and roll from there.

### Third-Party Libraries

**iOS**

A third-party library notice can be found [here](https://raw.githubusercontent.com/Matchstic/ReProvision/master/iOS/HTML/openSourceLicenses.html).

### License

Licensed under the AGPLv3 License.

If you re-distribute this package on a Cydia repository, be aware that I will not provide any support whatsoever for users of it on said repository.

Furthermore, ReProvision (and by extension, libProvision as found in `/Shared/`) IS NOT FOR PIRACY. It is intended to allow users to ensure applications signed with a free development certificate remain signed past the usual 7-day window.

Absolutely no warranty or guarantee is provided; the software is provided AS-IS.


[![FOSSA Status](https://app.fossa.com/api/projects/git%2Bgithub.com%2FDaddycal69%2FReProvision.svg?type=large)](https://app.fossa.com/projects/git%2Bgithub.com%2FDaddycal69%2FReProvision?ref=badge_large)