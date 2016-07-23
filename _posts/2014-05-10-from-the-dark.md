---
layout:     post
title:      From The Dark
date:       2014-05-10
img:	images/from-the-dark/WiFiPeople.png
summary:    Understanding the social nature of the Wi-Fi Protocol.
permalink: /from-the-dark/
categories: all research
---


Anonymous data is a myth. From the Dark offers insight into the hidden mechanisms and power struggles within our current communications infrastructure. It brings to light the data we generate with our smart devices and what it reveals about us.
<div class="mxn1 embed-container">
<iframe class="px4" src="//player.vimeo.com/video/110800707" width="670" height="376" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>
</div>
Over the last year or so there has been a surge in companies that are providing location based tracking services to brick and mortar stores. Some of the more well known companies include Euclid Analytics and Density. These companies use the Wi-Fi signal from smartphones to track people in space. With the insights gained from the Snowden leaks, it has become clear that the government also uses this technique to identify and track people. 

Companies are using this data for metric accumulation and targeted advertising, the government is using this data for surveillance - the only people who aren't directly benefitting from this data were the ones who created it. Taking all this into consideration I was motivated to create an open source tool that uses Wi-Fi to track people in space with the intention of providing rich interactive experiences for the people that actually create this data i.e the people being tracked.


Our devices have memories. They store lists of places (via Wi-Fi networks) where they've previously been. If you have Wi-Fi activated on your device (smartphone/laptop) then that device will send packets that are know as Probe Request Frames looking for known networks. Once it's found one to connect to, it ceases to send these Probe Request Frames.

A Probe Request Frame is basically a packet that a Wi-Fi device sends looking for networks that it has stored in its Preferred Networks list. An important thing to note is that a Wi-Fi device has no concept of where it is located geographically. So when it's searching for known networks it's just screaming out past locations you have visited.

So let's take the example of Bob. Bob is our friend who goes to NYU. Nearby the NYU campus he goes to Starbucks to study and use the free internet. So Bob has connected to Wi-Fi both at NYU and Starbucks and both these networks have been stored on his smartphone. 

Now when Bob goes anywhere and uses his phone, it by default tries to connect to known networks. So wherever Bob goes his phone is shouting out "NYU Wi-Fi are you here?", "Starbucks Free Wi-Fi are you here?" If either of those networks are available Bob's phone will automatically connect to that network.

Now all this data is going across the air unencrypted, so any router in the vicinity listening to the network activity can hear these messages.

This is the underlying technology used to track people in space using Wi-Fi. Companies set up multiple routers to listen to all the network activity in the space they are tracking. Then using those routers they listen to the "volume" (RSSI) of the Probe Request Frames picked up by each router to triangulate people in space. As each smart device has a unique MAC address it's also possible to uniquely identify an individual in that space.

