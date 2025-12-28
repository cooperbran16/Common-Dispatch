# Common Dispatch Console

A web-based multi-resource dispatch console for KV4P-HT amateur radio hardware. Built entirely with HTML, CSS, and JavaScript - no installation required.

![License](https://img.shields.io/badge/license-GPL--3.0-blue.svg)
![Platform](https://img.shields.io/badge/platform-Web%20Browser-brightgreen.svg)
![Hardware](https://img.shields.io/badge/hardware-KV4P--HT-orange.svg)

## Features

### Multi-Resource Management
- Connect and control multiple KV4P-HT radios simultaneously
- Independent VHF (134-174 MHz) and UHF (400-480 MHz) support
- Real-time RSSI signal strength monitoring
- Per-resource volume control with stereo panning (selected left, unselected right)

### Audio & Communication
- Full-duplex audio with Opus codec encoding/decoding via WebCodecs API
- DTMF caller ID detection with Goertzel algorithm
- Customizable radio aliases (map DTMF codes to names)
- Console ID transmission (send DTMF identifier with each transmission)
- VU meter for transmit audio monitoring

### Paging & Alerting
- Two-tone sequential paging (fire/EMS style)
- DTMF paging support
- Emergency alert detection with configurable trigger codes
- Visual and audio emergency notifications
- Priority tone transmission

### Advanced Features
- Channel patching (link two resources for cross-band repeat/rebroadcast)
- Activity logging with transmission recording (WAV format)
- CTCSS tone support for encode/decode
- Configurable squelch levels
- Mute unselected resources option
- Light/Dark theme support
- Stack Light Support - Connect an AndonStack for physical RGB status indication

### User Experience
- Clean, responsive interface
- Real-time clock display (12/24 hour format)
- Configuration import/export (JSON)
- All settings saved to browser localStorage
- Keyboard PTT support (configurable key)

## Requirements

### Hardware
- One or more [KV4P-HT](https://github.com/VanceVagell/kv4p-ht) radio modules
  - VHF version (SA818-V) for 134-174 MHz
  - UHF version (SA818-U) for 400-480 MHz
- USB connection to computer
- ## Optional Hardware: AndonStack

AndonStack is a physical RGB stack light that provides visual status indication for your dispatch console:

- 🟢 **Green** - Receiving audio on selected resource
- 🟡 **Yellow** - Transmitting (voice, alert tones, pages)
- 🔴 **Red** - Emergency alert or priority tone

Build instructions, firmware, and BOM: [AndonStack Repository](https://github.com/cooperbran16/AndonStack)

**To connect:**
1. Enable "Stack Light" in Settings
2. Click the Stack Light Settings button
3. Click "Connect to Stack Light" and select the ESP32-C3 serial port

### Software
- Modern web browser with Web Serial API support:
  - Google Chrome (recommended)
  - Microsoft Edge
  - Opera
- No installation or server required - just open the HTML file

### Licensing
- Valid amateur radio license required for transmission
- Ensure compliance with local regulations for frequencies used

## Quick Start

1. **Download** `Common_Dispatch.html`
2. **Open** the file in Chrome or Edge
3. **Click** add resource
4. **Configure** frequency, CTCSS, other settings, and press save resource
5. **Click** the edit resource button on the resource card
6. **Select** Connect to KV4P-HT and select the desired serial port when prompted
7. **Click** the resource card to select it (purple highlight)
8. **Hold** the PTT button or press your configured PTT key to transmit

## Usage Tips

### Selecting Resources
- Click a resource card to select it (purple highlight, audio pans left)
- Selected resources play at full volume; unselected play at reduced volume (configurable)
- Multiple resources can be selected simultaneously

### Channel Patching
- Click the link icon on two resources to patch them together
- Audio received on one resource automatically rebroadcasts on the other
- Click the link icon again to remove the patch

### Recording Transmissions
- Click the download button next to the desired RX/TX to save audio
- Recordings saved as WAV files with timestamps

### Emergency Alerts
- Configure emergency trigger DTMF code in settings (e.g., "911")
- When detected, resource flashes red and alert tone plays
- Click the emergency icon in header to view/acknowledge alerts

## Screenshots

*Screenshots coming soon - contributions welcome!*

## Configuration

### Settings (Gear Icon in Header)
- **Console Name**: Customize the header title
- **Theme**: Light, Dark, or System default
- **Clock**: Show/hide, 12/24 hour format
- **Selected/Unselected Volume**: Default volume levels
- **Console ID**: DTMF string sent with transmissions

### Resource Settings (Gear Icon on Resource Card)
- **Name**: Display name for the resource
- **Frequency**: TX/RX frequency in MHz
- **Tone Mode**: None (CSQ), CTCSS encode/decode
- **Squelch**: 0-8 (0 = open, 8 = tight)
- **Power**: High/Low
- **Bandwidth**: Narrow (12.5 kHz) or Wide (25 kHz)

### Import/Export
- Export your complete configuration (resources, aliases, pages, settings) as JSON
- Import configuration on another browser/computer
- Great for backup or sharing setups with others

## Known Limitations

- Web Serial API requires Chrome, Edge, or Opera (Firefox/Safari not supported)
- USB serial connection required (no network/remote operation)

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
- [KV4P-HT Discord](https://discord.gg/kv4p-ht)
- [GNU GPL-3.0 License](https://www.gnu.org/licenses/gpl-3.0.html)

---

