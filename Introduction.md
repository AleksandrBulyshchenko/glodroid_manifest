## What is Glodroid

Glodroid is a project that adapts Android Open-Source Project to support Orange Pi platform in a way that is:
* Open and free as much as it's possible;
* Up-to-date version of Android;
* Close to mainline Android as much as it's possible;
* Provided with necessary libraries and software so user/customer could have up and running latest Android OS with no efforts

## Motivation

Before starting this project we've spent some time looking for a platform that would satisfy our own needs:
* **Cheap**
* Has Android support
* Android is of up-to-date version
* It is open as much as it's possible

After a search we were disappointed, since there were several choises but all of them was far from our desires. Hikey has relatively modern Android, but it has a lot of closed components and is a relatively expensive platform, at least not something that student or enthusiast could afford. Orange Pi had long forgotten Android version and closed graphic drivers that weren't updated since 2018 and made some suspicios socket and sha256 encrypting calls inside. On the other hand it was one of the cheapest platforms available and had some potential for Android. Also, we were lucky, since it's community has reverse-engineered it's graphics stack and made open-source implementation of graphic drivers that is currently supported and actively developing. Therefore we've decided that we could start this project in order to satisfy our own needs and to help Android community in general by making cheap, easy-to-start platform. 

## Goals

The goals of this project is:
* Provide a cheap platform with up-to-date Android for easier prototyping, learning and researching.
* Make it easy to start, reduce steps to build and deploy Android on your board as much as it's possible. No need to build kernel separately, download external binaries and fiddle with putting them in a correct place, etc.
* Upstream everything we could upstream in order to help community.