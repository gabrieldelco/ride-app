## Ride App

### Introduction

Mobile first application developed with bootstrap, and vanilla javascript. This project aims to develop a data tracking application for general rides. The application includes features such as GPS tracking, map route, real time speedometer, and general data tracking for any sort of ride (on foot, vehicle, etc.). It also provides a user-friendly UI, allowing users to check history and detailed information, delete and start new rides easily.

### Tech Stack

- **Framework**: Bootstrap
- **Language**: JavaScript

### Application Structure (JS)

  - `index.js` : the app has its ride history as homepage, as well as the button that starts a new ride. In this script, all the elements are created using ride's data storage from the `storage.js` and manipulated by `dataManager.js`. The minimap preview is also configured.
  - `speedometer.js` : manages start and stop ride events, and uses the geolocation objetc in order to track the data and also change velocity in real time.
  - `detail.js`: shows each individual ride detailed information, accordingly to its rideID. The elements are created using storage data, and a bigger map with the route feature is configured.
  - `dataManager.js` : manipulates all the data tracked and storaged of a ride. It calculates the max speed, the ride duration, the starting time and date, and the total distance, wich uses the "harversine" formula. For getting location data, such as region, city, it was used the reverse geocode API from bigdatacloud. 
  - `storage.js` : saves ride's tracked data in local storage.

### Getting Started (ngrok)

Since its an applicaiton for rides, you will not be able to test all of its features on your regular computer, unless you are running in a macOS. If you are running a macOS, you will be well served using the OS mobile simulators. Otherwise, I recommend hosting the local application in **ngrok**. The geolocation object methods require a HTTPS connection, and ngrok can easily it. In this way, you will be able to run the application in your mobile device. Follow the instructions:

1. Sign up for free at [ngrok](https://ngrok.com/).
2. Get your authtoken, or generate one.
3. Install ngrok software.
4. Run the following command to add your authtoken.
  ```bash
  $ ngrok config add-authtoken <token>
  ```
5. Start a tunnel at your localhost port.
  ```bash
  $ ngrok http 5500
  ```
6. If everything went fine, you will get the screen below, or similar.
  ```bash
  Session Status                online
  Account                       Gabriel Delconti (Plan: Free)
  Version                       3.5.0
  Region                        South America (sa)
  Latency                       19ms
  Web Interface                 http://127.0.0.1:4040
  Forwarding                    https://c8db-2804-d55-5e35-6e00-a0e4-302-249a-7c39.ngrok-free.app -> http://localhost:5500
  
  Connections                   ttl     opn     rt1     rt5     p50     p90
                                0       0       0.00    0.00    0.00    0.00
  ```
7. Your HTTPS connection was established. Use the `Forwarding` link in your mobile device to test all features of the Ride App project.
