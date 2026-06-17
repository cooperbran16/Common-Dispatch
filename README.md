# Common Dispatch Console

A web-based multi-resource dispatch console for KV4P-HT amateur radio hardware. Built entirely with HTML, CSS, and JavaScript — no installation, no server, and no internet connection required.

![License](https://img.shields.io/badge/license-GPL--3.0-blue.svg)
![Platform](https://img.shields.io/badge/platform-Web%20Browser-brightgreen.svg)
![Hardware](https://img.shields.io/badge/hardware-KV4P--HT-orange.svg)

## Features

### Multi-Resource Management
- Connect and control multiple KV4P-HT radios simultaneously
- VHF (134-174 MHz) and UHF (400-480 MHz) support, with automatic module detection and frequency-mismatch warnings
- Real-time RSSI signal strength monitoring
- Per-resource volume control with stereo panning (selected left, unselected right)

### Channels
- Each resource holds multiple channels (up to 16), each with its own name, frequency, mode, tone, power, and bandwidth
- Switch the active channel from a dropdown on the resource card
- Add, edit, reorder, and delete channels in a dedicated channel manager
- Simplex and half-duplex (split TX/RX) operation
- Switching is blocked while transmitting and warns if a channel doesn't match the connected radio's band

### Audio & Communication
- Real-time Opus audio encode/decode via the WebCodecs API
- DTMF caller ID detection with the Goertzel algorithm
- Customizable radio aliases (map DTMF codes to names)
- Console ID transmission (send a DTMF identifier with each transmission)
- VU meter for transmit audio monitoring

### Paging & Alerting
- Two-tone sequential paging (fire/EMS style)
- DTMF paging support
- Emergency alert detection with configurable trigger codes
- Visual and audible emergency notifications (alerts show the channel the call came in on)
- Priority tone transmission

### Activity Recording & Logging
- Automatic recording of received and transmitted traffic — including alert tones and two-tone/DTMF pages
- Back-to-back traffic merges into a single recording (a short cooldown window keeps related transmissions together)
- Recordings persist between sessions, stored in the browser (up to 50 per resource)
- Per-recording playback (play/stop, one at a time) and WAV download
- Each entry is labeled by channel name, decoded alias, date, time, and duration
- Export all recordings as a single `.zip`, organized into a folder per channel
- Storage-usage indicator and one-click "delete all" in Settings

### Advanced Features
- Channel patching (link two resources for cross-band repeat/rebroadcast)
- CTCSS tone support for encode/decode
- Configurable squelch levels
- Mute unselected resources option
- Light/Dark theme support

### User Experience
- Clean, responsive interface
- Real-time clock display (12/24 hour format)
- Configuration import/export (JSON)
- Runs fully offline — all assets are bundled into the single HTML file
- All settings and configuration saved to the browser

## Requirements

### Hardware
- One or more [KV4P-HT](https://github.com/VanceVagell/kv4p-ht) radio modules
  - VHF version (SA818-V) for 134-174 MHz
  - UHF version (SA818-U) for 400-480 MHz
- USB connection to computer

### Software
- Modern web browser with Web Serial API support:
  - Google Chrome (recommended)
  - Microsoft Edge
  - Opera
- No installation or server required — just open the HTML file (works offline)

### Licensing
- Valid amateur radio license required for transmission
- Ensure compliance with local regulations for the frequencies used

## Quick Start

1. **Download** `Common_Dispatch.html`
2. **Open** the file in Chrome or Edge
3. **Click** Add Resource
4. **Name** the resource, then **add one or more channels** (frequency, tone, mode, etc.) and save
5. **Click** the Edit button on the resource card
6. **Select** Connect to KV4P-HT and choose the desired serial port when prompted
7. **Click** the resource card to select it (purple highlight)
8. If the resource has more than one channel, **pick the active channel** from the dropdown
9. **Hold** the PTT button or press your configured PTT key to transmit

## Usage Tips

### Selecting Resources
- Click a resource card to select it (purple highlight, audio pans left)
- Selected resources play at full volume; unselected play at reduced volume (configurable)
- Multiple resources can be selected simultaneously

### Channels
- The active channel's name is shown on the resource card
- Click the channel dropdown to switch; you can open a resource's Activity Log while the dropdown is open to check which channel traffic arrived on
- Manage channels (add, edit, reorder, delete) from the resource's channel manager

### Channel Patching
- Click the link icon on two resources to patch them together
- Audio received on one resource automatically rebroadcasts on the other
- Click the link icon again to remove the patch

### Activity Recording
- Received and transmitted traffic is recorded automatically, and consecutive traffic is merged into a single recording
- Expand a resource's Activity Log to play, download (WAV), or delete individual recordings
- Recordings persist across sessions; from Settings you can download all recordings as a zip or clear them all

### Emergency Alerts
- Configure the emergency trigger DTMF code in settings (e.g., "911")
- When detected, the resource flashes red and an alert tone plays; the alert shows the channel it came in on
- Click the emergency icon in the header to view/acknowledge alerts

## Screenshots

*Screenshots coming soon - contributions welcome!*

## Configuration

### Settings (Gear Icon in Header)
- **Console Name**: Customize the header title
- **Theme**: Light, Dark, or System default
- **Clock**: Show/hide, 12/24 hour format
- **Selected/Unselected Volume**: Default volume levels
- **Console ID**: DTMF string sent with transmissions
- **Activity Logs**: Download all recordings (zip), delete all, and view storage usage

### Resource & Channel Settings (Edit Icon on Resource Card)
- **Resource Name**: Display name for the radio
- **Channels** (per channel):
  - **Name**: Channel display name (shown on the card)
  - **Frequency**: Receive frequency in MHz
  - **Transmit Frequency**: Separate TX frequency for half-duplex/split channels
  - **Mode**: Simplex or half-duplex
  - **Tone Mode**: None (CSQ), CTCSS encode/decode
  - **Squelch**: 0-8 (0 = open, 8 = tight)
  - **Power**: High/Low
  - **Bandwidth**: Narrow (12.5 kHz) or Wide (25 kHz)

### Import/Export
- Export your complete configuration (resources, channels, aliases, pages, settings) as JSON
- Import configuration on another browser/computer
- Great for backup or sharing setups with others

## Known Limitations

- Web Serial API requires Chrome, Edge, or Opera (Firefox/Safari not supported)
- USB serial connection required (no network/remote operation)
- Activity-log recordings are stored per browser; use the JSON export and the activity-log zip download to move data between machines

## Troubleshooting

### "No port selected" Error
- Ensure KV4P-HT is connected via USB
- Try a different USB port or cable
- Check that no other application is using the serial port

### No Audio Output
- Check browser volume and system audio settings
- Click anywhere on the page first (browsers require user interaction for audio)
- Verify the resource is connected (green indicator)

### Choppy or Distorted Audio
- Close other browser tabs using significant resources
- Check USB connection stability
- Try a USB cable with ferrite chokes for noise reduction

## Contributing

Contributions are welcome! Please see [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

## License

This project is licensed under the GNU General Public License v3.0 - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- **[Vance Vagell](https://github.com/VanceVagell)** - Creator of the KV4P-HT project
- **SmittyHalibut** - KV4P-HT electronics design
- **Claude** (Anthropic) - AI development assistance
- **Gemini** (Google) - Additional AI assistance
- **Poe** - Additional AI assistance

## Links

- [KV4P-HT Project](https://github.com/VanceVagell/kv4p-ht)
- [KV4P-HT Discord](https://discord.gg/WKTEhuEZhp)
- [GNU GPL-3.0 License](https://www.gnu.org/licenses/gpl-3.0.html)

---
