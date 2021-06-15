# Museum_Robot
Final project in Computer Engineering degree 

Link to the project's YouTube channel: https://www.youtube.com/channel/UCEsl3fHv6tYhknyyNeigeJA/videos

website link: https://adirbashari.github.io/Museum_Robot/museum%20website/museum_robot_website 
user name and password to the website: admin, admin

About the project:

This project is about a robot, whose role is to take a tour of the museum's visitors.
The robot manager selects through a web interface created for him, the stations where
the robot will stop for his current tour.
When the robot begins a tour, it travels while scanning barcodes belonging to museum stations.
When he scans a station barcode, which was included for the current tour,
he stops and performs a reading of the station content for visitors.
In this way, the robot takes a tour of all the selected stations, until the end of the tour.


Project components:

1. museum website folder
  This folder contins the code of the web interface. 
  The web interface provides the robot manager a way to perform ongoing management
  of the museum stations and the current tour for visitors.
  Written in JavaScript, HTML and interfaces with the database backend restdb.io, that stores all the site data.
  website link: https://adirbashari.github.io/Museum_Robot/museum%20website/museum_robot_website
  user name and password to the website: admin, admin
  
  website home page:
  This page contains a search engine, through which the robot manager can view all the existing stations in the museum.
  each station in the museum contains: its name, content for reading for an adult, content for reading for a child.
  In addition whether to include the station in the current tour and what content the robot will read, adult, child or both.
  The robot manager can add and delete stations and edit all station data. 

  website current tour page:
  This page provides for the robot manager, a way to quickly edit the current robot tour.
  He can view all the stations that currently exist on the tour, delete and add stations and in addition
  choose what content the robot will read, adult child or both.


2. rp robot code folder

  This folder contains the code, which runs on the raspberry pi smart controller. 
  Written in Python.

  The code consists of four main components, when each of them is thread, i.e., the robot performs four main operations simultaneously:

  1. Black stripe travel algorithm- the robot receives information from infrared sensors
  and therefore makes a change in travel, in order not to deviate from the route set for him.

  2. Collision prevention algorithm- the robot receives information about its distance from objects in front of it. 
  When the robot detects that there is an object close to it, it makes a stop, and only when the object becomes
  clear of its path, does it continue its tour from the point where it stopped.

  3. Barcode scanning algorithm- the robot scans the barcodes that are on the wall while traveling, 
  when it detects that the content of the barcode matches the name of the station included in the tour, 
  it stops and reads the contents of the station for the visitors. In case the content of the barcode, 
  does not include the name of the station belonging to the current tour, the robot continues to travel without stopping at the station.

  4. Algorithm for tracking battery life- the robot maintains a file that lists the time left for the battery to work until it runs out. 
  The robot measures the time it is on and updates the file accordingly, with the new time it has left to work.


  In addition to these main operations the robot performs other important operations such as:

  1. Download the current tour data from the database

  2. Convert text to speech- once the robot has detected a station where it needs to stop, it converts the text belonging to the station to speech

  3. Connect to a wireless Internet using a network name and password provided
