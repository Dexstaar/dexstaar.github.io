---
layout: post
title:  "Hello Xamarin"
date:   2016-11-20 19:55:16 +0800
categories: Programming
---


It is quite surprising almost every time Microsoft announces their products these Things that surprises people in the latest "Connect();" was launching visual studio for Mac. Since mobile app market became the mainstream of software development, it seems Microsoft focus on expanding mobile development platform despite of their failure of mobile platform. Xamarin is a representative one of this movement and started being on the tongues of developers rapidly these days. Visual studio for Mac is based on Xamarin studio and added some more functions for developing Windows apps and web development.

<br/>
<img src="/assets/screen-shot-2016-11-20-at-8-47-48-pm.png" width="500px">
<br/>
 Visual Studio for Mac and Xamarin Studio
<br/><br/>




What is Xamarin ?

Xamarin is a hybrid mobile developement platform to develop iOS, Android and Windows mobile apps using C#. A traditional approach to develop mobile apps is using their native SDKs. Thus, develpers use different languages and platforms for each. There are some approaches to prevent this kind of overlapped investement. A widespread way is putting mobile web into Webview and make it be covered by mobile platforms. but this kind of WebView methodology has poor usability due to late response time.

Another methodology of buliding hybird apps is writing single source code and converting it to native binary files. Recently this way of approach is becoming more popular due to there are usable platforms are released. First one is react Native developed by Facebook, and the other is Xamarin, that became free of charge platform since it's acquired by Microsoft.



How does Xamarin Work ?

Xamarin offers two commercial products: Xamarin.iOS and Xamarin.Android. They’re both built on top of Mono, an open-source version of the .NET Framework based on the published .NET ECMA standards. Mono has been around almost as long as the .NET framework itself, and runs on nearly every imaginable platform including Linux, Unix, FreeBSD, and Mac OS X.

On iOS, Xamarin’s Ahead-of-Time ( AOT) Compiler compiles Xamarin.iOS applications directly to native ARM assembly code. On Android, Xamarin’s compiler compiles down to Intermediate Language ( IL), which is then Just-in-Time ( JIT) compiled to native assembly when the application launches.

In both cases, Xamarin applications utilize a runtime that automatically handles things such as memory allocation, garbage collection, underlying platform interop, etc.

<br/>
<img src="/assets/screen-shot-2016-11-20-at-9-25-06-pm.png" width="500px">
<br/>
 Xamarin & Xamarin Forms Architecture
<br/><br/>




My first Xamarin App

I recently attended Microsoft's Xamarin Dev Day conference and had a chance to glance the platform. In order to prepare for attending the event, I had short studies of Xamarin and also had little hands on experience before and after the event. This is the app that I firstly developed following the live coding session during the conference. This app receives the information of the dev day speakers using RESTful API and display their information.

<br/>
<img src="/assets/screen-shot-2016-11-20-at-10-01-25-pm.png" width="500px">
<br/>
 Screenshot of runtime using iOS and Android emulator
<br/><br/>


Xamarin.Forms is based on  MVVM(Model-View-ViewModel) pattern.

"Model–view–view-model (MVVM) is a software architectural pattern. MVVM facilitates a separation of development of the graphical user interface – be it via a markup language or GUI code – from development of the business logic or back-end logic (the data model)." <Source: Wikipedia>

<br/>
<img src="/assets/screen-shot-2016-11-20-at-10-29-50-pm.png" width="500px">
<br/>
 Application Folder Structure
<br/><br/>



 In Model folder, there is "Speaker.cs" that implements data models of the application.

 <br/>
 <img src="/assets/screen-shot-2016-11-20-at-10-59-48-pm.png" width="500px">
 <br/>
  Speakers.cs
 <br/><br/>




User Interface files exist in View folder. There are two types of files. ".xaml " is a xml to implement display page and ".xaml.cs" is a place that the UI relate logics are implemented such as event handlers.

<br/>
<img src="/assets/screen-shot-2016-11-20-at-11-02-09-pm.png" width="500px">
<br/>
 SpeakersPage.xaml
<br/><br/>


<br/>
<img src="/assets/screen-shot-2016-11-20-at-10-57-10-pm.png" width="500px">
<br/>
 SpeakersPage.xaml.cs
<br/><br/>


In SpeakersPage.xaml.cs, it creates the ViewModel object and set as binding context.

<br/>
<img src="/assets/screen-shot-2016-11-20-at-11-06-57-pm.png" width="500px">
<br/>
 Constructor of the ViewModel
<br/><br/>




Let's see the constructor of SpeakersViewModel. It calls GetSpeakers() method.

<br/>
<img src="/assets/screen-shot-2016-11-20-at-11-21-45-pm.png" width="500px">
<br/>
 The method that calls RESTful API to receive the speakers's information
<br/><br/>



In GetSpeakers() method, it calls a RESTful API and puts the received data into Speaking model. So the xaml file can display the bound Speakers objects into list format.



# Xamarin Dev Day

This is a sample application that was presented in Xamarin Dev Day in Singapore and there was a session that every participants had a hands on experience while following live coding. Also other sessions were followed to introduce related technologies such as Azure, Xamarin test cloud. This event was the fruit of Microsoft's developer friendly movement and internationalized Singapore IT industry culture.

<br/>
<img src="/assets/IMG_0977.JPG" width="500px">
<br/>
<br/>
<img src="/assets/IMG_0974.JPG" width="500px">
<br/>
Xamarin Dev Days with 3 times served high quality food. This is free event !
<br/><br/>
