# Demo guide

Record one 12 to 18 second GIF or MP4 at 1280×720 or smaller. Use a private test server with throwaway media and hide usernames, server names, channel names, and notifications.

## Main demo

1. Start on a message containing a test image.
2. Right-click it and choose **Hide this image**.
3. Pause on the placeholder for one second.
4. Drag the placeholder down for one second to show the peek interaction.
5. Open a second channel containing the same test image and show the placeholder.
6. Right-click and choose **Unhide this image**.

Keep the pointer movement deliberate. Crop out the member list and server list. Do not add an intro card; the GitHub heading already explains the feature.

Save the finished file as `docs/assets/demo.gif` and replace the Demo note in the README with:

```md
![HideMediaEverywhere demo](docs/assets/demo.gif)
```

## Optional clips

- **Video matching:** Post the same short test video in two channels, hide it in one, then show the match in the other.
- **Hide all:** Use a message with two harmless test images and show **Hide all media** followed by **Unhide all media**.
- **Customization:** Change the placeholder image in settings, then return to the test message.

## Export checklist

- Crop out private messages, usernames, avatars, server names, and notifications.
- The context-menu label is readable at normal GitHub width.
- Keep the file under 10 MB to reduce the README load time.
- The first frame shows visible media and the final frame shows the feature's result.
- The clip works without audio.
