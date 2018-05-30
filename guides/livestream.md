---
layout: page
title: How to run the Cyber@UC livestream
permalink: /guides/livestream
---
This guide will teach you how to run the Cyber@UC livestream. It is a work in progress, so please ask [Hayden Schiff](mailto:schiffha@mail.uc.edu) if you have any questions or issues.

**Table of Contents:**
* [Hardware setup](#hardware-setup)
  * [Equipment list](#equipment-list)
  * [Webcam](#webcam)
  * [Capture card](#capture-card)
  * [Projectors](#projectors)
* [Software setup](#software-setup)
  * [Starting OBS](#starting-obs)
  * [Intro to OBS](#intro-to-obs)
  * [Video capture devices](#video-capture-devices)
* [Running the stream](#running-the-stream)
  * [Ending the stream](#ending-the-stream)

## Hardware setup
Here's how to setup all the hardware components. **If you're not sure what piece of equipment I'm talking about, you can find photos of everything by clicking the links in the equipment list.**

### Equipment list
The equipment we use for the livestream is:

* the PC in Rhodes 850D (for running OBS, and for presenting slides)
* [Logitech C922 Pro Stream Webcam](https://www.logitech.com/en-us/product/c922-pro-stream-webcam) (for the primary webcam)
* [Elgato Cam Link capture card](https://www.elgato.com/en/gaming/cam-link) (for capturing laptop footage)
* [VGA-to-HDMI Converter](https://www.amazon.com/gp/product/B00V3RJKLO/) (in case we need to use AJ's stupid old laptop that doesn't have an HDMI port)
* [1x2 HDMI Splitter](https://www.amazon.com/HDS-102-Powered-Certified-Splitter-Resolutions/dp/B00F5R9TNM) (so that the laptop video feed can be sent to both the projector and the capture card for the stream)
* [2x1 HDMI Pigtail Switch](https://www.monoprice.com/product?c_id=101&cp_id=10110&cs_id=1011001&p_id=8147&seq=1&format=2) (to simplify switching between HDMI and VGA laptops)
* a standard camera tripod (for the primary webcam)
* USB extension cables
* HDMI cables

Most of this equipment can be found in a Hak5-branded drawstring bag that should be either in Rhodes 1000 or ERC 516 (if you don't have a key for those rooms, you'll have to ask someone who does).

The tripod, however, will need to be checked out from the library. Go to the desk at Langsam and ask them for a tripod. They'll ask you to show your Bearcat card and fill out a form (on the form, you can put "Cyber@UC" for the class and "livestreaming meetings" as the purpose). When you return the tripod, they'll ask again for your Bearcat card, so the person who checked it out has to be the one to return it.

### Webcam
Mount the Logitech C922 Webcam on the tripod using the screw threading on the bottom of the camera. Set up the tripod as close as possible to the presenter's desk. Try to point the camera to a reasonable spot where anyone will probably remain mostly in frame even if they move around a lot.

The USB cable on the webcam is really short, so I recommend you don't even remove the cable tie or unwind it. Instead, connect a USB extension cable to it, and plug that into one of the 4 USB ports on the PC (inside the cabinet of the presenter's desk -- you may have to reach around the door if it's locked).

### Capture card
The Elgato Cam Link capture card should already have a dinky little ~6-inch USB 3.0 extension cable attached to it. Plug that cable directly into one of the USB 3.0 ports on the PC (you **must** use a USB 3.0 port or it won't work). We have a couple HDMI cables, most of them are short but there's one long one; connect the long one to the Elgato Cam Link. Connect the other end of that HDMI cable to one of the outputs on the 1x2 HDMI Splitter.

The other output on the 1x2 HDMI Splitter needs to go to the projector. There are two HDMI cables coming out of a hole in the top of the presenter's desk (just behind the computer monitors)—unfortunately, it's a game of trial and error to figure out which one is the HDMI input (once you've finished connecting everything you should test it—see the last paragraph of the Projectors section below).

Now both of the outputs on the 1x2 HDMI Splitter should be connected, but we still need an input. Connect the 2x1 HDMI Pigtail Switch to the 1x2 HDMI Splitter's input.

Now we need to connect the 2x1 HDMI Pigtail Switch's input. For one of the inputs, just connect a short HDMI cable and leave it on the desk. If anyone needs to present their HDMI laptop, they can plug the other end of that cable into their laptop.

For the 2x1 HDMI Pigtail Switch's other input, connect it to the VGA-to-HDMI Converter with another short HDMI cable. The VGA-to-HDMI Converter should already have a VGA cable attached to it -- if anyone needs to present from a VGA laptop, they can connect that VGA cable to their laptop.

### Projectors
You now need to correctly setup the projector using the little touch screen attached to the presenter's desk. Tap "Start Class" to turn on the projectors.

To have the projectors show what's on the right monitor of the desktop PC, set the touch screen to "Project PC". To have the projectors show a laptop, select "Project HDMI" (note: even if it's a VGA laptop, you should select HDMI due to the quirks of our setup).

At this point, you should probably connect a laptop to the short HDMI cable we mentioned earlier and test that it shows up on the projectors when the touchscreen is set to "Project HDMI". If it does not show up, you might have used the wrong one of the two HDMI cables coming out of the desk.

## Software setup
Now that all the hardware is connected, it's time to get OBS working.

### Starting OBS
Log in to the desktop PC with your UC account. You should have a copy of OBS downloaded with our configs; if not, you can download OBS with our configs [here](https://drive.google.com/file/d/1iD4PfSkKcArQNPUHNlQ6dESHrxipdMOQ/view?usp=sharing).

Once you've extracted the zip file to some folder on the PC, you can start OBS by double-clicking the "Launch OBS" batch file. (FYI: All the batch file does is run obs64.exe with the `--portable` flag for portable mode, which is needed since UC doesn't allow us to install applications.)

### Intro to OBS
You should have OBS in studio mode, which means you will see two different scenes side by side, with a few buttons in between them and a bunch of options and stuff at the bottom of the screen (if you only see one scene, turn on Studio Mode). The scene on the right is what's "live" -- when the stream is turned on, that is what is being sent to YouTube. The scene on the left is what's "on deck" -- it's whatever scene you have ready to go live at the click of a button. OBS sort of thinks of this as your current scene for editing/configuration -- the Scenes and Sources menus at the bottom of the window are for making changes to the "on deck" scene.

You can select which scene is "on deck" via the Scenes list at the bottom of the window on the far left. To swap the "on deck" scene with the "live" scene, click the Transition button in the middle of the screen (i.e. between the two scenes).

### Video capture devices
Once you have OBS opened, you should make sure that both the webcam and the Cam Link are working properly (which they often aren't). Theoretically, OBS should automatically find these devices as long as they were plugged in when you started OBS. In practice, they're finicky as hell and you have to futz about with it to get them working.

In the Scenes list, there are separate "RAW" scenes for both the webcam and the capture card -- go to these scenes to troubleshoot each device. The webcam raw scene should be showing the picture from the Logitech C922 Pro Webcam, and the Cam Link raw scene should be showing the display of the laptop (if you don't have a laptop connected, obviously this will show nothing, so you'll need to plug in a laptop to test this).

If either/both of these are not properly displaying, here are some possible troubleshooting steps:

* While in the "RAW" scene for a device, go to the Sources list at the bottom of OBS. The raw scenes should only have one source, which is the video capture device. Right-click this and select Properties. There's a few things you can check in the Properties pop-up:
  * The dropdown menu at the top of the options should be set to the appropriate device. Click the dropdown menu and re-select the appropriate device.
  * If there are no devices in the dropdown menu, or if the device you're looking for is missing from the dropdown, try reconnecting its USB connection, then closing and reopening the Properties pop-up. If that doesn't work, you might need to reboot the entire PC.
  * Often times, you might simply need to deactivate and reactivate the source, using the Deactivate button (this is particularly effective for the Cam Link).
  * The resolution for both devices should be 1920x1080 and the FPS should be "Same as Output FPS".
* If you're really having trouble getting the source to display, you might try closing the Properties pop-up, then right-clicking the source in the Sources list and deleting it. Then add a new source, select Video Capture Device, and try adding the appropriate device again.
* If the source is displaying, but there's black space around it in the scene or it's mispositioned, go to the Properties pop-up again and make sure the video resolution is correct. If it is indeed 1920x1080, then you can fix the scene by simply clicking on the picture in the scene, and dragging the corners of the source to adjust its position/size.

## Running the stream
Now that everything is (hopefully) working, you need to actually run the stream during the meeting. Essentially, this just consists of switching between scenes. In the scenes list, there are two types of scenes that you can use during the stream: SPLASH and PRESENT.

* The SPLASH scenes show a pretty photo of the university and show a simple message. There are "starting soon" and "see you next week" versions of the SPLASH screen pre-made, and there's also one with no preset message that you can edit. To change the text on that scene, go to that scene, then right click the text source in the Sources list and select Properties. Change the text to whatever you like.
* The PRESENT scenes are the primary scenes you'll use while the meeting is actually ongoing. There's three main PRESENT scenes: desktop, laptop, and webcam.
  * The desktop scene shows whatever is the right monitor of the PC. When you show this scene, you should also have the classroom projectors set to "Project PC" (via the touchscreen on the desk).
  * The laptop scenes show any laptop that is connected, whether it be HDMI or VGA. Most of the time, the first laptop scene on the list should be fine, but there are alternate versions of the scene you can use if you have a laptop putting out a weird resolution. When you use the laptop scenes, you should have the classroom projectors set to "Project HDMI".
  * The webcam scene is shows the webcam video fullscreen with the name of the club tucked in the corner. We don't use this one much.

A few minutes before the meeting is going to start, make sure the "live" scene is set to the "SPLASH: starting soon" scene. Then click the "Start Streaming" button in OBS (it's at the bottom on the far right).

### Ending the stream
If you can, it's nice to have the "SPLASH: see you next week" scene up for a minute or so at the end of the meeting. When you're ready to kill it, click "Stop Streaming", close OBS, and log out of the computer. Tap "End Class" on the touchscreen to turn off the projectors. Pack up all the equipment into the Hak5 bag and store it in either Rhodes 1000 or ERC 516. Put the tripod in its bag and return it to Langsam (the Langsam desk is open pretty late, so I recommend returning it immediately after the meeting ends).
