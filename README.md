Wi-Find Design Project - README 
===

# Wi-Find

## Table of Contents
1. [Overview](#Overview)
1. [Product Spec](#Product-Spec)
1. [Wireframes](#Wireframes)

## Overview
### Description
This is a Wifi finder app, which allows user to find wifi signals that are joinable. The app will take into account an users current location and will display all wifi signals within 10 mile radius of the user. 

### App Evaluation
[Evaluation of your app across the following attributes]
- **Category:** Utility
- **Mobile:** This app would be primarily built for mobile but can be just as viable on a computer.
- **Story:** Analyzes the location of the user to find valid wifi signals withing 10 mile radius of the user's current location. The wifi signals will vary depending on user's location.
- **Market:** This app could be used often or unoften depending on user's need to connect to wifi.
- **Habit:** The user would use this anytime they are out of their house and looking for a wifi spot to connect to. 
- **Scope:** This app would use the location of an user to find valid wifi access points.  

## Product Spec

### 1. User Stories (Required and Optional)

**Required Must-have Stories**

- [ ] User can find wifi locations within a 10 mile radius via map
- [x] User sees a styled launch screen when they open the app.
- [ ] User can find wifi locations via table view and search
- [x] Search bar is visible to user



**Optional Nice-to-have Stories**

- [ ] User can save wifi spots they've conncected to and rate their experience.
- [ ] User can see the strength of the nearby wifi signals
- [ ] User will be given a message saying they have connected to this wifi before if they connect to it again for the second time or so forth. This way they will know if they still want to connect to it based on their previous experience. 

### 2. Screen Archetypes


* Map Screen
   * Google Geolocation API

### 3. Navigation

**Tab Navigation** (Tab to Screen)

* Map View Finder
* Table View Finder

**Flow Navigation** (Screen to Screen)
* Table View Finder
  - Goes to specific Wifi point if an user taps on one from the list.



## Wireframes
![](https://i.imgur.com/0bJFl65.jpg)


### [BONUS] Digital Wireframes & Mockups
![](https://i.imgur.com/PXZTeYh.png)


### [BONUS] Interactive Prototype
![](https://media0.giphy.com/media/FC9e5yXXAuJ3SXwJE6/giphy.gif?cid=790b76118bc289eee9177be604f809bea360cc2e7fe73be1&rid=giphy.gif&ct=g)


**Schema**

---
**Models**

Post


| Property | Type     | Description |
| -------- | -------- | ----------- |
| location    | String   | location of the wifi point       |
| Wifi signal strength  | Number   | the strength of the wifi in integer form         |
    

**Networking**

List of network requests by screen

* Display Screen
  (Read/Get) Query all wifi points
```
let query = PFQuery(className:"Post")
# query.whereKey("user", equalTo: currentUser)
query.order(byDescending: "location")
query.findObjectsInBackground { 
(posts: [PFObject]?, error: Error?) in
   if let error = error { 
      print(error.localizedDescription)
   } 
   else if let wifiPoint = wifiPoint {
      print("Successfully retrieved \(wifiPoint.count)wifiPoint.")
      // TODO: Do something with wifi points...
    }
}
```

* Map Screen
  (Read/Get) Query all wifi points


* Build Progress 11/14/2021


![](https://i.imgur.com/QHIFYEA.gif)
