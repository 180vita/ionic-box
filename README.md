Ionic Box
=============================

Ionic Box is a ready-to-go hybrid deveopment environment for building mobile apps with Ionic, Cordova, and Android. Ionic Box was built to make it easier for developers to build Android versions of their app, and especially for Windows users to get a complete dev environment set up without all the headaches.

For iOS developers, Ionic Box won't do much for you right now unless you are having trouble installing the Android SDK, and Ionic Box cannot be used for iOS development for a variety of legal reasons (however, the `ionic package` command in beta will soon fix that).

### Installation


To install, download and install [Vagrant](https://www.vagrantup.com/downloads.html) for your platform, then download and install [VirtualBox](http://virtualbox.org/).

Once Vagrant and VirtualBox are installed, you can download the latest release of this GitHub repo, and unzip it. `cd` into the unzipped folder and run:

```bash
$ mkdir Apps
$ vagrant up
$ vagrant ssh
```

The username for vagrant is `vagrant` and the password is `vagrant`. 

This will download and install the image, and then go through the dependencies and install them one by one. `vagrant ssh` will connect you to the image and give you a bash prompt. Once everything completes, you'll have a working box to build your apps on Android.

You can then go into the /Apps directory within the box (or the Apps folder you just created in the root folder of the Ionic Box installation) and start a new Ionic app or checkout one from an existing repository.

### Connected Android Devices

The image also has support for connected USB Android devices. To test whether devices are connected, you can run (from the box):

```bash
$ sudo /home/vagrant/android-sdk-linux/platform-tools/adb devices
```

If that does not work, or shows `????? permissions`, then run:

```bash
sudo /home/vagrant/android-sdk-linux/platform-tools/adb kill-server
sudo /home/vagrant/android-sdk-linux/platform-tools/adb start-server
```

### Differences from original repository

This repository is a fork from https://github.com/driftyco/ionic-box. The main differences are:

* PhoneGap CLI is installed for phonegap development and builds.
* Gulp npm package is globally installed for task execution.
* Bower npm package is globally installed for js dependency management.
* A folder with the name Apps is expected to be created in the root folder. The applications should be living within this folder and it is synced in the /Apps folder inside the Vagrant box.
