# Vamonos
An app to help optimize your time and travel, by finding you the least occupied places in a variety of industries.

- IOS Application dedicated to helping students find empty spaces to work on campus
- Data is pushed to the cloud from the Telus IoT development board and then pulled from the ios application
- Data is stored in a NoSQL database by Azure (cosmosDB)
- Currently, map view is shown but due to issues, pulling from the database still doesnt work

## Inspiration

**Our inspiration was waiting in long lines and walking around aimlessly to find space.**

Remember the last time you waited in a line at a ServiceOntario location? Wouldn't it have been nice to get a decent estimate of how full the location is so you could either choose a different location or time?

Or what about walk-in clinics? Wouldn't it be nice to get recommendations on which walk-in clinic near you you should visit based on which is the least busy?

Or even finding a cafe thats not full to the brim?

Our app aims to reduce time waiting and let you "Vamonos" to the least busy place you need to go.

## What it does

This app finds places of interest in close proximity and allows you to view the current occupancy level to help you pick where to go. By detecting the number of wifi devices in the space, it can provide updated location occupancy level to users through the app.

_The Concept_

First, users are to sign up or log in.

Then they choose what category of location they are looking for, whether a place to eat (EAT), medical help (HEALTH), places to study (STUDY), places to shop (SHOP), or ServiceOntario services (ServiceOntario).

Then they choose the specific location type they are looking for, for example, if they choose STUDY they can look for cafes, meeting rooms, individual space, or group spaces.

Close proximity spaces are displayed in a map view and a list view. Users can scroll through the "List View" which is organized in a ranked list based on the percent occupancy of the building. Percent occupancy is found by identifying the number of wifi-connected devices in the space. Each item in the list would clearly display a percent occupancy of the building or space, and allow the user to click the item for further details. The "Map View" allows the user to view these options on a map, and click the pinned locations that are in the list.

Upon clicking a pinned location from the Map or List Views, the location would open in a new screen and display the details of the place. This screen could display the percent occupancy, address, hours, contact, reviews and other info about the place. After browsing, users can make decisions on where they want to go, by identifying places convenient to them with decent/low occupancy to avoid any waiting times.

_The Prototype_

The prototype is able to detect the number of wifi connected devices in the space. The ESP32 sniffs all the wifi packets in the space, builds a data structure that keeps track of the presence of individual MAC addresses. Once in a while, the aggregated data of the devices is sent to the IOT board. This updates the different devices that may have entered or left the space. The Telus IOT board connects to the Azure IoT backend, and sends the data to the cloud. This data is then transferred to an Azure Cosmos DB so it can be easily accessed with the IOS app.

The UX design was modelled in Marvel as well, to show the functionality from a user journey perspective.

## How we built it

We used a variety of tools in this hack, including, ESP32, the Telus IOT starter kit, Azure, and XCode.

The UX design was modelled in Marvel as well, to show the functionality from a user journey perspective.

## Challenges we ran into

Major challenges we faced were in configuring Azure and the Telus IoT kit. With no previous experience using these, it was really difficult to set these up before being able to actually develop the solution. We tested a number of different IOT boards before getting the Telus one to work.

## Accomplishments that we're proud of

We are proud of being able to get the Telus IOT board to work, and be able to implement the backend.

## What we learned

We learned a lot about implement IOT, using Azure and integrating hardware components.

## What's next for Vamonos

Next steps would be implementing more of the UI and UX components, and expanding the industries included. In the future, implementing more filter options and introducing more features like reviews would be a goal.
