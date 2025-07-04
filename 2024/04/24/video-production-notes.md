# Video production notes

[20240424](./) came with a video, in which I read the piece and you get to both watch me _and_ follow along onscreen with the same text I'm reading.

## Video recording

### Phone video

I used my phone, lol. I AirDrop'd it to my Macbook.

### Content video

The onscreen video was done on my Macbook, very simply, using cmd+shift+5 and choosing "Record Selected Portion". I used Chrome's dev tools to display the in-browser content in a scale and ratio appropriate for mobile.

<figure><img src="../../../.gitbook/assets/2024-04-24 13.10.45.gif" alt=""><figcaption></figcaption></figure>

## Audio recording

I didn't record audio separately. After getting the phone video file on my laptop, I used Quicktime to export as audio-only, and then I cleaned up the audio with [Auphonic](https://auphonic.com/).

<figure><img src="../../../.gitbook/assets/2024-04-24 13.14.44.gif" alt=""><figcaption></figcaption></figure>

Here's my Auphonic configuration:

<figure><img src="../../../.gitbook/assets/Screenshot 2024-04-24 at 1.05.36 PM.png" alt=""><figcaption></figcaption></figure>

Before/after samples, if you're curious:

{% file src="../../../.gitbook/assets/before.m4a" %}

{% file src="../../../.gitbook/assets/after.m4a" %}

## Video editing

Done with [Davinci Resolve](https://www.blackmagicdesign.com/products/davinciresolve). (I pay for it, but you wouldn't need to for this kind of thing.)

I used a timeline resolution of 1080x1350, which is the max for Instagram feed videos. (This was too long for a conventional reel, which is why I didn't use 1080x1920.)

<figure><img src="../../../.gitbook/assets/2024-04-24 13.21.01.gif" alt=""><figcaption></figcaption></figure>

I added three files to the timeline: both videos and the audio file from Auphonic (see above).

I used the waveforms shown on the audio tracks to align all three clips.

The audio tracks for the two videos are both muted.

There's a control curve for the screen recording video, which manages Opacity (found under Video / Composite in the Inspector). This is how the video fades in at the beginning and fades out at the end. I don't have a recording to show you of setting that one up; I really fumbled through it and I'm intimidated by figuring out a clean way to show it, haha. [Here's someone else showing you how on YouTube.](https://www.youtube.com/watch?v=tMjeH-is0z8)

<figure><img src="../../../.gitbook/assets/Screenshot 2024-04-24 at 1.08.25 PM.png" alt=""><figcaption></figcaption></figure>

The screen recording video is positioned as an overlay using the Transform settings found in the Inspector pane.

<figure><img src="../../../.gitbook/assets/2024-04-24 13.17.40.gif" alt=""><figcaption></figcaption></figure>
