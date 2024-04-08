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

## Installation

This document is for the latest Aimeos TYPO3 **2.0 release and later**.

- LTS release: 2.0 (Rice Rescue LTS)
- Old LTS release: 1.0 (Rice Rescue 1.0 LTS)

**Note:** Flutter 3.0.0+ is required!

The latest Flutter version can be installed via command line. This is required useful, if you want to run the installations automatically or play with the latest code.
To update the Flutter SDK use the flutter upgrade command:

```bash
$ flutter upgrade
```
This command gets the most recent version of the Flutter SDK.

If you are using the stable channel and want an even more recent version of the Flutter SDK, switch to the beta channel using flutter channel beta, and then run flutter upgrade.

### Adding a package dependency to your local clone

To add the package, for example flutter_svg, to your repositories:

1. #### Depend on it

Open the `pubspec.yaml` file located inside the app folder, and add css_colors: under dependencies.
Install it

From the terminal: 

```bash
# Visual Studio Code
$ flutter pub get

# Android Studio/IntelliJ
$ flutter pub get
```

#### OR

# Visual Studio Code

Click the Get Packages button located in the right-side action ribbon at the top of your pubspec.yaml file, indicated by the Download icon.



### TER Extension

If you want to install Aimeos into a traditionally installed TYPO3 ("legacy installation"), the [Aimeos extension from the TER](https://typo3.org/extensions/repository/view/aimeos) is recommended. You can download and install it directly from the Extension Manager of your TYPO3 instance.

* Log into the TYPO3 backend
* Click on "Admin Tools::Extensions" in the left navigation
* Click the icon with the little plus sign left from the Aimeos list entry

![Install Aimeos TYPO3 extension](https://user-images.githubusercontent.com/213803/211545083-d0820b63-26f2-453e-877f-ecd5ec128713.jpg)

Afterwards, you have to execute the update script of the extension to create the required database structure:

* Click on "Admin Tools::Upgrade"
* Click "Run Upgrade Wizard" in the "Upgrade Wizard" tile
* Click "Execute"

![Execute update script](https://user-images.githubusercontent.com/213803/211545122-8fd94abd-78b2-47ad-ad3c-1ef1b9c052b4.jpg)

#### Aimeos Distribution

For new TYPO3 installations, there is a 1-click [Aimeos distribution](https://typo3.org/extensions/repository/view/aimeos_dist) available, too. Choose the Aimeos distribution from the list of available distributions in the Extension Manager and you will get a completely set up shop system including demo data for a quick start.

## TYPO3 Setup

Setup TYPO3 by creating a `FIRST_INSTALL` file in the `./public` directory:

```bash
touch public/FIRST_INSTALL
```

Open the URL of your installation in the browser and follow the steps in the TYPO3 setup scripts.

### Database Setup

If you use MySQL < 5.7.8, you have to use `utf8` and `utf8_unicode_ci` instead because those MySQL versions can't handle the long indexes created by `utf8mb4` (up to four bytes per character) and you will get errors like

```
1071 Specified key was too long; max key length is 767 bytes
```

To avoid that, change your database settings in your `./typo3conf/LocalConfiguration.php` to:

```php
    'DB' => [
        'Connections' => [
            'Default' => [
                'tableoptions' => [
                    'charset' => 'utf8',
                    'collate' => 'utf8_unicode_ci',
                ],
                // ...
            ],
        ],
    ],
```

### Security

Since **TYPO3 9.5.14+** implements **SameSite cookie handling** and restricts when browsers send cookies to your site. This is a problem when customers are redirected from external payment provider domain. Then, there's no session available on the confirmation page. To circumvent that problem, you need to set the configuration option `cookieSameSite` to `none` in your `./typo3conf/LocalConfiguration.php`:

```php
    'FE' => [
        'cookieSameSite' => 'none'
    ]
```

## Site Setup

TYPO3 10+ requires a site configuration which you have to add in "Site Management" > "Sites" available in the left navigation. When creating a root page (a page with a globe icon), a basic site configuration is automatically created (see below at [Go to the Import View](#go-to-the-import-view)).

## Page Setup

### Download the Aimeos Page Tree t3d file

The page setup for an Aimeos web shop is easy, if you import the example page tree for TYPO3 10/11. You can download the version you need from here:

* [23.4+ page tree](https://aimeos.org/fileadmin/download/Aimeos-pages_2023.04.t3d) and later
* [22.10 page tree](https://aimeos.org/fileadmin/download/Aimeos-pages_2022.10.t3d)
* [21.10 page tree](https://aimeos.org/fileadmin/download/Aimeos-pages_21.10.t3d)

**Note:** The Aimeos layout expects [Bootstrap](https://getbootstrap.com) providing the grid layout!

In order to upload and install the file, follow the following steps:

### Go to the Import View

**Note:** It is recommended to import the Aimeos page tree to a page that is defined as "root page". To create a root page, simply create a new page and, in the "Edit page properties", activate the "Use as Root Page" option under "Behaviour". The icon of the root page will change to a globe. This will also create a basic site configuration. Don't forget to also create a typoscript root template and include the bootstrap templates with it!

![Create a root page](https://user-images.githubusercontent.com/213803/211549273-1d3883dd-710c-4e27-8dbb-3de6e45680d7.jpg)

* In "Web::Page", right-click on the root page (the one with the globe)
* Click on "More options..."
* Click on "Import"

![Go to the import view](https://user-images.githubusercontent.com/213803/211550212-df6daa73-74cd-459e-8d25-a56c413c175d.jpg)

### Upload the page tree file

* In the page import dialog
* Select the "Upload" tab (2nd one)
* Click on the "Select" dialog
* Choose the T3D file you've downloaded
* Press the "Upload files" button

![Upload the page tree file](https://user-images.githubusercontent.com/8647429/212347778-17238e05-7494-4413-adb3-a54b2b524e05.png)

### Import the page tree

* In Import / Export view
* Select the uploaded file from the drop-down menu
* Click on the "Preview" button
* The pages that will be imported are shown below
* Click on the "Import" button that has appeared
* Confirm to import the pages

![Import the uploaded page tree file](https://user-images.githubusercontent.com/8647429/212348040-c3e10b60-5579-4d1b-becc-72548826c6db.png)

Now you have a new page "Shop" in your page tree including all required sub-pages.

### SEO-friendly URLs

TYPO3 9.5 and later can create SEO friendly URLs if you add the rules to the site config:
[https://aimeos.org/docs/latest/typo3/setup/#seo-urls](https://aimeos.org/docs/latest/typo3/setup/#seo-urls)

## License

The Aimeos TYPO3 extension is licensed under the terms of the GPL Open Source
license and is available for free.

## Links

* [Web site](https://aimeos.org/integrations/typo3-shop-extension/)
* [Documentation](https://aimeos.org/docs/TYPO3)
* [Forum](https://aimeos.org/help/typo3-extension-f16/)
* [Issue tracker](https://github.com/aimeos/aimeos-typo3/issues)
* [Source code](https://github.com/aimeos/aimeos-typo3)
