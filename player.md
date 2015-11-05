## Twitch Player API

### Functions
<table>
    <thead>
        <tr>
            <th>Name</th>
            <th width="100%">Description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><code>isPaused</code></td>
            <td>Gets the playing status of the video. Returns boolean <code>true</code> or <code>false</code></td>
        </tr>
        <tr>
            <td><code>loadStream</code></td>
            <td>Loads a given stream. Parameter is a channel name (as a String).</td>
        </tr>
        <tr>
            <td><code>loadVideo</code></td>
            <td>Loads a given video. Parameter is the video ID (as a String).</td>
        </tr>
        <tr>
            <td><code>mute</code></td>
            <td>Mutes the player.</td>
        </tr>
        <tr>
            <td><code>onlineStatus</code></td>
            <td>Returns the online status of the loaded stream. Values returned are <code>online</code>, <code>offline</code>, or <code>unknown</code>.</td>
        </tr>
        <tr>
            <td><code>pauseVideo</code></td>
            <td>If stream is online, will pause the player.</td>
        </tr>
        <tr>
            <td><code>playVideo</code></td>
            <td>If stream is online, will play the player.</td>
        </tr>
        <tr>
            <td><code>videoSeek</code></td>
            <td>Seeks a video. Parameter is seconds (as a Number)</td>
        </tr>
        <tr>
            <td><code>unmute</code></td>
            <td>Unmutes the player.</td>
        </tr>
    </tbody>
</table>

### Events

Events are emitted through the eventsCallback Flash player parameter in the following form:

```json
[
  {
    "event": "",
    "data": {}
  },
  ...
]
```

<table>
    <thead>
        <tr>
            <th width="25%">Event</th>
            <th width="50%">Description</th>
            <th width="25%">Data</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><code>streamLoaded</code></td>
            <td>Emitted when a stream is loaded in the video player</td>
            <td>
<pre>{
  channel: "test_stream",
  channelSteamId: null,
  videoId: null,
  videoLengthInSecs: 0,
  viewerSteamId: null
}</pre>
            </td>
        </tr>
        <tr>
            <td><code>videoLoaded</code></td>
            <td>Emitted when a video is loaded in the video player</td>
            <td>
<pre>{
  channel: "test_stream",
  channelSteamId: null,
  videoId: "4345634",
  videoLengthInSecs: 15,
  viewerSteamId: null
}</pre>
            </td>
        </tr>
        <tr>
            <td><code>online</code></td>
            <td>Emitted when the stream is online (emitted on stream load too)</td>
            <td><pre>{}</pre></td>
        </tr>
        <tr>
            <td><code>offline</code></td>
            <td>Emitted when the stream goes offline</td>
            <td><pre>{}</pre></td>
        </tr>
        <tr>
            <td><code>viewerCount</code></td>
            <td>The viewer count is emitted periodically for streams</td>
            <td>
<pre>{
  channel: "test_stream",
  viewers: 12975
}</pre>
            </td>
        </tr>
        <tr>
            <td><code>videoLoading</code></td>
            <td>Emitted when a stream or video is loading</td>
            <td><pre>{}</pre></td>
        </tr>
        <tr>
            <td><code>playerInit</code></td>
            <td>Emitted when the player is loaded</td>
            <td><pre>{}</pre></td>
        </tr>
        <tr>
            <td><code>videoPlaying</code></td>
            <td>Emitted when a stream or video starts playing</td>
            <td><pre>{}</pre></td>
        </tr>
    </tbody>
</table>
