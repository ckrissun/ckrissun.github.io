---
layout: post
title: "Unity3D: 预定义宏定义"
date: 2013-07-02 18:53
category: "Unity3D"
tags: [游戏 Unity3D]
---

{% include JB/setup %}


Unity3D的一些预定义宏定义，仅仅作为备案，以备查阅。

来自Unity3D官方[Platform Dependent Compilation](http://docs.unity3d.com/Documentation/Manual/PlatformDependentCompilation.html)


Platform Defines
The platform defines that Unity supports for your scripts are:

UNITY_EDITOR	         | Define for calling Unity Editor scripts from your game code.
---------------------- | ----------------------------------------------------------------------------------------------------------------------------
UNITY_STANDALONE_OSX   | Platform define for compiling/executing code specifically for Mac OS (This includes Universal, PPC and Intel architectures).
UNITY_DASHBOARD_WIDGET | Platform define when creating code for Mac OS dashboard widgets.
UNITY_STANDALONE_WIN	 | Use this when you want to compile/execute code for Windows stand alone applications.
UNITY_STANDALONE_LINUX | Use this when you want to compile/execute code for Linux stand alone applications.
UNITY_STANDALONE	     | Use this to compile/execute code for any standalone platform (Mac, Windows or Linux).
UNITY_WEBPLAYER        | Platform define for web player content (this includes Windows and Mac Web player executables).
UNITY_WII	             | Platform define for compiling/executing code for the Wii console.
UNITY_IPHONE	         | Platform define for compiling/executing code for the iPhone platform.
UNITY_ANDROID	         | Platform define for the Android platform.
UNITY_PS3	             | Platform define for running PlayStation 3 code.
UNITY_XBOX360	         | Platform define for executing Xbox 360 code.
UNITY_NACL	           | Platform define when compiling code for Google native client (this will be set additionally to UNITY_WEBPLAYER).
UNITY_FLASH	           | Platform define when compiling code for Adobe Flash.

Also you can compile code selectively depending on the version of the engine you are working on. Currently the supported ones are:

UNITY_2_6	| Platform define for the major version of Unity 2.6.
----------  | ------------------------------------------------------------------
UNITY_2_6_1	| Platform define for specific version 1 from the major release 2.6.
UNITY_3_0	| Platform define for the major version of Unity 3.0.
UNITY_3_0_0	| Platform define for the specific version 0 of Unity 3.0.
UNITY_3_1	| Platform define for major version of Unity 3.1.
UNITY_3_2	| Platform define for major version of Unity 3.2.
UNITY_3_3	| Platform define for major version of Unity 3.3.
UNITY_3_4	| Platform define for major version of Unity 3.4.
UNITY_3_5	| Platform define for major version of Unity 3.5.
UNITY_4_0	| Platform define for major version of Unity 4.0.
UNITY_4_0_1	| Platform define for major version of Unity 4.0.1.
UNITY_4_1	| Platform define for major version of Unity 4.1.

Note: For versions before 2.6.0 there are no platform defines as this feature was first introduced in that version.

