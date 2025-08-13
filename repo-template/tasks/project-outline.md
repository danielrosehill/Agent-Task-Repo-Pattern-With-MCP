# Task Outline

Your task is to install a basic NVR system on Ubuntu VM, a machine on Daniel's LAN.

There are 4 IP cams providing RTSP feeds to integrate into this sytem. Those are provided in the details document. 

Here is what you should design:

## NVR Outline

Page 1: Grid view. All cameras laid out in a grid. Note: from time to time one or more of the cams will be offline. Therefore, the NVR should be fault-tolerant. If a camera is offline rather than showing with an error message it can be simply hidden. 

## Navigation

A persistent top bar displaying across the screen with navigation buttons for toggling between the grid view and the individual cams.

## Mute/Unmute

On each single cam view a mute/unmute button.

## Tally Light

In order to help the user visually identify when cams are live/inactive, show a tally light indicator in the top right of every feed. This can be added as a frontend overlay and should show in both the grid view and the single cam pages.

Use this logic:

- If a cam has provided frames in the last 15 seconds, consider it live. Overlay a green tally.

- If a cam has provided its last frame between 15 and 45 seconds ago, consider it potentially offline. Show an orange indicator.

- If a cam has not provided a frame for more 45 seconds, consider it offline. It should show a pulsating red light. 