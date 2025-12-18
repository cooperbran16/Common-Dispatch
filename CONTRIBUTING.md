# Contributing to Common Dispatch Console

Thank you for your interest in contributing to Common Dispatch Console! This project is open source under the GPL-3.0 license, and contributions are welcome from everyone.

## Ways to Contribute

### 🐛 Reporting Bugs

If you find a bug, please open an issue with:

- A clear, descriptive title
- Steps to reproduce the problem
- Expected behavior vs. actual behavior
- Browser and version (e.g., Chrome 120)
- Operating system
- Any relevant console errors (press F12 to open developer tools)

### 💡 Suggesting Features

Have an idea for a new feature? Open an issue with:

- A clear description of the feature
- Why it would be useful for dispatch operations
- Any implementation ideas you have (optional)

### 🔧 Submitting Code Changes

1. **Fork** the repository
2. **Create a branch** for your feature or fix (`git checkout -b feature/my-new-feature`)
3. **Make your changes** to the HTML file
4. **Test thoroughly** with actual KV4P-HT hardware if possible
5. **Commit** with clear, descriptive messages
6. **Push** to your fork
7. **Open a Pull Request** with a description of your changes

## Development Guidelines

### Code Style

Since this is a single-file application, keeping the code organized is important:

- **Sections are marked** with comment headers like `// ============ SECTION NAME ============`
- **Keep related functions together** within their section
- **Use descriptive variable and function names**
- **Add comments** for complex logic or non-obvious behavior
- **Maintain consistent indentation** (4 spaces)

### Testing

Before submitting changes:

- Test in both Chrome and Edge
- Test with actual KV4P-HT hardware if available
- Test both VHF and UHF modules if possible
- Verify existing features still work (regression testing)
- Check the browser console for errors

### Areas Where Help is Especially Welcome

- **Bug fixes** - Especially edge cases in audio handling or serial communication
- **Browser compatibility** - Improvements for different browsers/platforms
- **Accessibility** - Screen reader support, keyboard navigation
- **Documentation** - README improvements, screenshots, usage guides
- **Testing** - Finding and reporting bugs
- **Translations** - Internationalization support

## Architecture Overview

For those new to the codebase, here's how the single HTML file is organized:

```
Common_Dispatch_Console.html
├── GPL-3.0 License Header
├── <head>
│   ├── Tailwind CSS (CDN)
│   ├── Font Awesome (CDN)
│   ├── Custom CSS styles
│   └── Tailwind configuration
├── <body>
│   ├── Header (title, clock, toolbar buttons)
│   ├── Resource Grid (radio cards)
│   ├── Control Bar (PTT, mute, VU meter)
│   ├── Activity Log
│   └── Modals (settings, aliases, pages, help, etc.)
└── <script>
    ├── Serial Protocol Constants
    ├── State Variables
    ├── Audio Context & Opus Codec
    ├── DTMF Decoder Class
    ├── Tone Generation Functions
    ├── UI Rendering Functions
    ├── Resource Control Functions
    ├── Serial Communication Functions
    ├── Settings & Storage Functions
    └── Initialization
```

### Key Technologies

- **Web Serial API** - Communication with KV4P-HT hardware
- **WebCodecs API** - Opus audio encoding/decoding
- **Goertzel Algorithm** - DTMF tone detection
- **Web Audio API** - Audio routing, mixing, and VU metering
- **Tailwind CSS** - Styling (via CDN)
- **localStorage** - Persistent settings storage

## Pull Request Process

1. Ensure your code follows the style guidelines
2. Update the README.md if you've added features that need documentation
3. Update the version number in:
   - The `<script>` section initialization log
   - The About section in the help modal
4. Your PR will be reviewed and may receive feedback or change requests
5. Once approved, your PR will be merged

## Code of Conduct

- Be respectful and inclusive
- Focus on constructive feedback
- Remember that this is a hobby project maintained by volunteers
- Help others learn - we all started somewhere

## Questions?

If you have questions about contributing:

- Open a GitHub issue with the "question" label
- Ask in the KV4P-HT Discord server

## License

By contributing to this project, you agree that your contributions will be licensed under the GPL-3.0 license. This means:

- Your contributions must also be open source
- Anyone can use, modify, and distribute your contributions
- Derivative works must also be GPL-3.0 licensed

Thank you for helping make Common Dispatch Console better for the amateur radio community!
