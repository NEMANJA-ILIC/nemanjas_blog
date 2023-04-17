---
layout: post
title: "How to install Jekyll on Windows"
date: 2023-04-17
categories: jekyll
---

Jekyll is a static website generator that is based on Ruby. Having that in mind, the first thing that should be done is to install Ruby i.e. Ruby programming language.
Besides the Ruby programming language, Ruby Gems Package Manager is shall be installed as well.

The Ruby Gems Package Manager allows users to download, install and maintain Ruby programs.

After these two pieces of software have been installed, Jekyll can finally be installed using Ruby Gems Package Manager

## Installing Ruby and Ruby package manager via winget
The easiest way to install and maintain software on the modern Windows operating system is using the windows package manager CLI tool called winget. The package manager is a free and open source project maintained by Microsoft that can be found on the following Github page:

[https://github.com/microsoft/winget-cli](https://github.com/microsoft/winget-cli)

Note that in the installation instructions of the project, installation using the Microsoft Store is recommended. This, however requires the user to have a Microsoft account and to actually use the Microsoft store. To this end, it is possible to install winget without having a Microsoft account and without using the Microsoft store. Just navigate to the releases on the winget github page and download and run the latest .msixbundle package. After this, the winget package is installed with which the rest of the installation of Ruby shall be performed.

To install Ruby, first a PowerShell (PS) terminal must be run as an Admin.

After a PS has started, type winget search ruby to check the available packages.

The package with the ID `RubyInstallerTeam.RubyWithDevKit.X.X` shall be installed with the `X.X` representing the latest version.

The command to install Ruby is 
```ps
winget install RubyInstallerTeam.RubyWithDevKit.X.X -h
```
Be sure to change the `X.X` in the command to what is given as the ID.

After the installation has completed, run a Ruby CMD instance as Admin and type: 
```bat
ridk install
```
Once the command has been run, go through all the steps (1-3) sequentially.

Verify that everything installed correctly with the following commands in CMD:
```bat
ruby -v
```
This shall print the version of Ruby installed.

After Ruby is verified to be installed, run the following command:
```bat
gem -v
```
This shall print the version of Ruby Gems Package Manager installed.

## Installing Jekyll via Ruby package manager
Now that everything has successfully been installed, Jekyll can simply be installed via the Ruby package using the following command in the CMD:
```bat
gem install jekyll bundler
```
Verify that jekyll has been successfully installed with the following command:
```bat
jekyll -v
```
This prints out the version of Jekyll installed on the system.
