## Embedding Streams, Videos, and Chat

There are two ways to include the player, either using an iframe or our embed script. Both support the same parameters but the script method has some extra functionality. 

#### Parameters
**Required**
- `channel`   : Channel name for live streams. (ex. `twitch`)
- `video`     : Video ID for past broadcasts. Has no effect if `channel` is specified. (ex. `v123456`)

**Optional**
- `volume`    : Sets the initial playback volume. Must be a number between `0.0` and `1.0` inclusive.
- `muted`     : Sets the initial muted state. `true` or `false`.
- `time`      : Start playback at the given timestamp for videos ONLY. Must be in the format `1h2m3s` specifying hours, minutes, and seconds respectively.
- `autoplay`  : Automatically starts playing without the user clicking play. `true` or `false`.
- `quality`   : Sets the initial quality if available. Valid options are `chunked`, `high`, `medium`, `low`, or `mobile`.
- `controls`  : Toggles the visibility of player controls. `true` or `false`.



## Embed iframe
    <iframe src="http://player.twitch.tv/?channel={CHANNEL}" frameborder="0" scrolling="no" height="720" width="1280" allowfullscreen></iframe>

## Embed script
    <script src="http://player.twitch.tv/js/embed-v0.js"></script>
    <div id="twitch-embed"></div>

    <script type="text/javascript">
      var params = {
        channel: "{CHANNEL}",
        width: 1280,
        height: 720,
      };

      // Instanciate a player and attach it to our div.
      var player = new Twitch.embed.Player("twitch-embed", params);
    </script>

This script embed has a full Javascript interface, allowing you to dynamically control the player. Read the [Twitch Player API][] for documentation.


### Chat

#### Parameters
- `channel` : Channel the chat belongs to.
- `height`  : Chat window height.
- `width`   : Chat window width.

#### Code

```html
<iframe frameborder="0" 
        scrolling="no" 
        id="chat_embed" 
        src="http://www.twitch.tv/{CHANNEL}/chat" 
        height="{HEIGHT}" 
        width="{WIDTH}">
</iframe>
```

#### Example

```html
<iframe frameborder="0" scrolling="no" id="chat_embed" src="http://www.twitch.tv/hebo/chat" height="500" width="350"></iframe>
```

[Twitch Player API]: player.md
