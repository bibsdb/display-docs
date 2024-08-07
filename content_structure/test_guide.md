---
layout: default
title: Testing Guide
parent: Content Structure
nav_order: 5
---

# Testing Guide

## Overview

This guide explains how to test the different parts of the system. This can be used to confirm that the system works
following upgrades, new features, etc.

The following test scenarios are explained:

* [T1 Basic use](#t1-basic-use)
* [T2 Templates](#t2-templates)
* [T3 Publishing and planning](#t3-publishing-and-planning)
* [T4 Themes](#t4-themes)
* [T5 Screen layouts](#t5-screen-layouts)
* [T6 External users](#t6-external-users)
* [T7 Campaigns](#t7-campaigns)
* [T8 Shared playlists](#t8-shared-playlists)

---

## T1 Basic use

### Description

This guide tests that the user can log in, create content and show the content on a screen.
The user will create a slide, a playlist and a screen and then make the slide be displayed
on the screen.

This guide requires a user that has the `ROLE_ADMIN` role.

### Steps

* Open the admin at `/admin`.
* Log in.
* If more than one tenant has been set up, choose one.
* You should now be on the page `/admin/slide/list` (slide list).
* Create a slide
  * Click "Opret nyt slide".
  * You should now be on `/admin/slide/create`.
  * Fill "Slidets navn" with a name you can recognize.
  * Select "Billede og tekst" in "Vælg en skabelon til dit slide".
  * Fill "Overskrift på slide".
  * Fill "Tekst på slide".
  * Select "l" in "Tekststørrelse".
  * Upload an image under "Billeder".
  * Scroll to the bottom and click "Gem slide".
  * You should be redirected to the slide list at `/admin/slide/list`.
  * You should be able to find the new slide in the list.
* Create a playlist
  * Navigate to `/admin/playlist/list` by clicking `Spillelister` in the navigation.
  * Click "Opret ny spilleliste"
  * You should now be on `/admin/playlist/create`.
  * Fill "Spillelistens navn" with a name you can recognize.
  * Select the slide created above in "Vælg en eller flere slides".
  * Scroll to the bottom and click "Gem".
  * You should be redirected to the playlist list at `/admin/playlist/list`.
  * You should be able to find the new playlist in the list.
* Create a screen
  * Navigate to `/admin/screen/list` by clicking `Skærme` in the navigation.
  * Click "Opret ny skærm"
  * Fill "Skærmens navn" with a name you can recognize.
  * Select "Fuld skærm" in "Skærmens layout".
  * Select the playlist created above in "Vælg en eller flere spillelister"
  * Scroll to the bottom and click "Gem skærm".
  * You should be redirected to the screen list at `/admin/screen/list`.
  * You should be able to find the new screen in the list.
* Set up the screen
  * Open the screen client at `/screen` in another tab in the browser.
  * You should see an empty screen with an activation code in the bottom right corner.
  * If already logged in from earlier you can log out the screen with `shift+ctrl+i`.
  * Copy the activation code.
* Activate the screen
  * Open the the screen in the admin by clicking "Rediger".
  * You should be at a route like `/admin/screen/edit/[ID]`.
  * Input the activation code in "Tilkoblingskode".
  * Click "Tilkobl skærm".
* Check the content is displayed in the screen
  * Open the screen tab again at `/screen`.
  * See that the slide is displayed.

---

## T2 Templates

### Description

This guide tests that the different supported templates can be created.

### Steps

---

## T3 Publishing and planning

### Description

This guide tests the different publishing and planning options available.

### Steps

---

## T4 Themes

### Description

This guide tests setting up a theme and applying it to a slide.

### Steps

---

## T5 Screen layouts

### Description

This guide tests setting up screens with different layouts.

### Steps

---

## T6 External users

### Description

This guide tests inviting external users to the system using the OIDC external setup.

### Steps

---

## T7 Campaigns

### Description

This guide tests applying campaigns to screens and screen groups.

### Steps

---

## T8 Shared playlists

### Description

This guide tests sharing playlists across tenants.

### Steps

---
