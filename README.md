# 🏡Build an Automated Home of the Future using Home Assistant hub 🐋
We recently went to Disney World and rode on the Carousel of Progress. In that ride we see the great advancements the world has made, but also a vision of the future (in 1964). There’s a connected home with a voice assistant that uses devices around the house to do things for the family. With the IoT devices available on the market today we can have that home of the future.
The problem with setting up that futuristic home is you likely have a variety of different devices that you’re trying to control with a number of different platforms. It’s too disconnected and using an assistant like Google or Alexa can limit what you could potentially do with these cool technologies. However with Home Assistant we can collect data from a variety of different sources, run it through a workflow, and output it to any device we want on our network. The number of cool scenarios you can create is limitless. In this session we’ll talk about how to set it up and run through basic functionality so you can hit the ground running when you get back home.

## Introduction
Jesse Dahir-Kanehl

- Developer
- Tinkerer
- Gardener
- Climber
- Cyclist
- IoT Automater

## Home Assistant
- “Open source home automation that puts local control and privacy first.”
- Alternative to Google Home, Amazon Alexa, Apple Siri, and different hubs
- Local control - works without internet, you have control over your data
- Better security from big data leaks - smaller target for hackers
- Support for many devices, triggers, and ways to make your ideas come to life
- Customization of the dashboard - different themes

## Deciding on Which Installation Method to Use
[Installation Guide](https://www.home-assistant.io/installation/)

- [Home Assistant Yellow](https://www.crowdsupply.com/nabu-casa/home-assistant-yellow#products)
    - Built in Raspberry Pi 4 module
    - Zigbee module
    - M.2 SSD slot
    - Ethernet with Power over Ethernet
    - Fully open source and supports Nabu Casa, founders of Home Assistant and EspHome
    - Expensive but fully featured
- [Raspberry Pi 4](https://smile.amazon.com/Raspberry-Model-2019-Quad-Bluetooth/dp/B07TC2BK1X)
    - Next easiest, but a bit pricey
    - Write to SD card and install - follow the prompts
- Docker Container
    - Next easiest, but less features
- VM
    - Not too hard, fully featured
    - Could use more resources depending on install process
- Home Assistant OS install
    - Create bootable usb and install
- Core on Linux, macOS, WSL
    - Doesn't make sense to just do this, use Docker instead
    - Stepping stone for Supervised
- Supervised on Linux
    - Tricky to install but fully featured, uses less resources

## Onboarding
- Simple setup using [docs](https://www.home-assistant.io/getting-started/onboarding/)
- Wait to zoom in on the map until after initial setup

### Integrations
Support for so many [devices!](https://www.home-assistant.io/integrations/)

- Auto Discovery
- UI Integration through Settings menu, no restart needed
- Platform Integration
    - Example: [Tuya](https://www.home-assistant.io/integrations/tuya/)
- Manual Integration
    - Custom configuration that needs to go into configuration file

Once the devices are added, rename any that you want to now. It'll be harder to rename later.

Phone app - download from app store, allows for device tracking for presence detection and geofencing

### Backups
Remember to take them, download them, and store them in an organized way or use a blueprint to create automatic backups...

## Automations

### [Blueprints](https://www.home-assistant.io/docs/automation/using_blueprints/)
Automation recipes that are easy to use and share with others, like
 - [Automatic backups](https://community.home-assistant.io/t/create-automated-backups-every-day/254039)
 - Need to edit file to use *backup_full* instead of *snapshot_full*

### [Scenes](https://www.home-assistant.io/docs/scene/editor/)
Simple way to turn on or off many devices at once to "set a scene"
- Turn off all the lights before going to bed but turn on the bedroom fan
- Set the family room lights to dim and turn on the tv for movie night

Using the GUI editor it will set the state of those devices to what they currently are. If that isn't possible then edit the entity/device states of the scene in the scenes.yaml file.

### [Scripts](https://www.home-assistant.io/integrations/script/)

Allows us to manually trigger a variety of actions

### [Automations](https://www.home-assistant.io/getting-started/automation/)

Allows us to automatically trigger a variety of actions including calling a script or a scene based on the state of a device or a wide variety of other triggers (sunset, time, home assistant turning off)

## More [Advanced Configurations](https://www.home-assistant.io/getting-started/configuration/)

### Our First Add-On -> File Editor
Download from Add-Ons. Very useful for editing configuration files. Once you install an add-on hit the refresh button to see it

#### Google Drive Backup Add-on
This is an Add-On from an [external repository](https://github.com/sabeechen/hassio-google-drive-backup). Allows for backups to automatically be stored in a google drive instead of having to manually download them

### Editing Dashboard
- Remove any data points or cards you're not intested in. You can always add them back later
- Add, rename, move around entities or cards
- Add, delete, move dashboards
- All of this is saved to a configuration file which is editable directly if you wish

### Home Assistant Cloud and Nabu Casa
Easy way to setup remote connection to your Home Assistant instance and allows integration with cloud hubs like Google Assistant and Amazon Alexa