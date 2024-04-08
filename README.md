<a href="https://github.com/irfanghapar/rice-rescue">
    <img src="https://aimeos.org/fileadmin/template/icons/logo.png" alt="Aimeos logo" title="Aimeos" align="right" height="60" />
</a>

# Rice Rescue Mobile Application

[![Total Downloads](https://poser.pugx.org/aimeos/aimeos-typo3/d/total.svg)](https://packagist.org/packages/aimeos/aimeos-typo3)
[![Scrutinizer Code Quality](https://scrutinizer-ci.com/g/aimeos/aimeos-typo3/badges/quality-score.png?b=master)](https://scrutinizer-ci.com/g/aimeos/aimeos-typo3/?branch=master)
[![License](https://poser.pugx.org/aimeos/aimeos-typo3/license.svg)](https://packagist.org/packages/aimeos/aimeos-typo3)

:star: Star us on GitHub — it motivates us a lot!

[Rice Rescue](https://youtu.be/aIy220RJAAI) is a professional, Smart Farming App, with Precision Data
& AI Driven Technology for paddy care from seed to harvest 🌱. This app is still in development
and we are open for any issues or feature request.

![aimeos-frontend](https://github.com/irfanghapar/rice-rescue/blob/main/Rice%20Rescue%20V2.0.png)

## Table Of Content

- [Installation](#installation)
- [TYPO3 setup](#typo3-setup)
    - [Database setup](#database-setup)
    - [Security](#security)
- [Page setup](#page-setup)
    - [Download the Aimeos Page Tree t3d file](#download-the-aimeos-page-tree-t3d-file)
    - [Go to the Import View](#go-to-the-import-view)
    - [Upload the page tree file](#upload-the-page-tree-file)
    - [Go to the import view](#go-to-the-import-view)
    - [Import the page tree](#import-the-page-tree)
    - [SEO-friendly URLs](#seo-friendly-urls)
- [License](#license)
- [Links](#links)

### Built With

This section should list any major frameworks/libraries used to bootstrap your project. Leave any add-ons/plugins for the acknowledgements section. Here are a few examples.

* [![Flutter][Flutter]][Flutter-url]
* [![TensorFlow][TensorFlow]][TensorFlow-url]
* [![Google Maps][Google Maps]][Google-Maps-url]
* [![OpenAI][OpenAI]][OpenAI-url]
* [![Weather][Weather]][Weather-url]
* [![Kaggle][Kaggle]][Kaggle-url]
* [![MongoDB][MongoDB]][MongoDB-url]
* [![RaspberryPI][RaspberryPI]][RaspberryPI-url]

### System Design

This section should despict any major frameworks/libraries used to bootstrap the project. It also shows how it connects between each other

* [![software-architecture][software-architecture]][software-architecture]

<p align="right">(<a href="#readme-top">back to top</a>)</p>


## Installation

This document is for the latest Rice Rescue 2.0 release and later.

- LTS release: 2.0 (Rice Rescue LTS)
- Old LTS release: 1.0 (Rice Rescue 1.0 LTS)

**Note:** Flutter 3.0.0+ is required!

The latest Flutter version can be installed via the command line. This is useful if you want to run the installations automatically or play with the latest code.
To update the Flutter SDK use the `flutter upgrade` command:

```bash
$ flutter upgrade
```
This command gets the most recent version of the Flutter SDK.

If you are using the stable channel and want an even more recent version of the Flutter SDK, switch to the beta channel using flutter channel beta, and then run flutter upgrade.

#### 1. Adding a package dependency to your local clone

To add the package for example, flutter_svg, to your repositories:

Open the `pubspec.yaml` file inside the app folder, and add css_colors: under dependencies.

Install it

##### 1.1 From the terminal: 

```bash
# Visual Studio Code
$ flutter pub get

# Android Studio/IntelliJ
$ flutter pub get
```

### OR

#### Visual Studio Code

Click the Get Packages button located in the right-side action ribbon at the top of your pubspec.yaml file, indicated by the Download icon.

#### 2. Run

 Open the Command Palette.

```bash
Go to View > Command Palette or press + Shift + P.
```

#### 3. Type `flutter`

#### 4. Select the Flutter: Select Device.

If no devices are running, this command prompts you to enable a device.

Select a target device from Select Device prompt.

#### 5. After you select a target, start the app. 

```bash
Go to Run > Start Debugging or press F5.
```

You can watch the launch progress in the Debug Console view. After the app build completes, your device displays your app.

## License

The Aimeos TYPO3 extension is licensed under the terms of the GPL Open Source
license and is available for free.

## Links

* [Web site](https://aimeos.org/integrations/typo3-shop-extension/)
* [Documentation](https://aimeos.org/docs/TYPO3)
* [Forum](https://aimeos.org/help/typo3-extension-f16/)
* [Issue tracker](https://github.com/aimeos/aimeos-typo3/issues)
* [Source code](https://github.com/aimeos/aimeos-typo3)

<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[Flutter]: https://github.com/irfanghapar/rice-rescue/blob/main/assets-readme/1.png
[Flutter-url]: https://flutter.dev/
[TensorFlow]: https://github.com/irfanghapar/rice-rescue/blob/main/assets-readme/2.png
[TensorFlow-url]: https://www.tensorflow.org/
[Google Maps]: https://github.com/irfanghapar/rice-rescue/blob/main/assets-readme/3.png
[Google-Maps-url]: https://developers.google.com/maps
[OpenAI]: https://github.com/irfanghapar/rice-rescue/blob/main/assets-readme/4.png
[OpenAI-url]: https://platform.openai.com/
[Weather]: https://github.com/irfanghapar/rice-rescue/blob/main/assets-readme/5.png
[Weather-url]: https://openweathermap.org/api
[Kaggle]: https://github.com/irfanghapar/rice-rescue/blob/main/assets-readme/6.png
[Kaggle-url]: https://www.kaggle.com/docs/api
[MongoDB]: https://github.com/irfanghapar/rice-rescue/blob/main/assets-readme/7.png
[MongoDB-url]: https://www.mongodb.com/
[RaspberryPI]: https://github.com/irfanghapar/rice-rescue/blob/main/assets-readme/8.png
[RaspberryPI-url]: https://www.raspberrypi.com/
[Firebase]: https://github.com/irfanghapar/rice-rescue/blob/main/assets-readme/9.png
[Firebase-url]: https://console.firebase.google.com/
[Nodejs]: https://github.com/irfanghapar/rice-rescue/blob/main/assets-readme/10.png
[Nodejs-url]: https://nodejs.org/en
[software-architecture]: https://github.com/irfanghapar/rice-rescue/blob/main/assets-readme/software-architecture

