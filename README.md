# 📏 Pixel Ruler + Alignment Checker

A Chrome extension that displays pixel-perfect rulers and alignment guides on any webpage to help developers and designers ensure precise element positioning.

![Extension Demo](https://via.placeholder.com/800x400/007acc/ffffff?text=Pixel+Ruler+Demo)
*Replace with actual screenshot*

## ✨ Features

### 🎯 Core Functionality
- **Pixel-Perfect Rulers** - Horizontal and vertical rulers showing exact pixel measurements
- **Draggable Alignment Guides** - Create and position guides for perfect element alignment  
- **Element Inspector** - Hover over elements to see dimensions and positioning details
- **Measurement Tool** - Click and drag to measure distances between any elements
- **Background Grid** - Optional pixel grid overlay for precise positioning
- **Responsive Design** - Works on any screen size and zoom level

### ⌨️ Keyboard Shortcuts
- `Ctrl+Shift+R` - Toggle rulers on/off
- `Ctrl+Shift+G` - Toggle alignment guides  
- `Ctrl+Shift+C` - Clear all guides
- `Ctrl+M` - Enable/disable measurement mode
- `Escape` - Exit measurement mode
- `Double-click` - Create new alignment guide

### 🎨 Customization
- Adjustable ruler colors
- Customizable guide colors  
- Variable grid sizes (5px, 10px, 20px, 25px)
- Dark mode support
- High contrast accessibility mode

## 🚀 Installation

### For Development
1. Clone this repository:
   ```bash
   git clone https://github.com/yourusername/pixel-ruler-extension.git
   cd pixel-ruler-extension
   ```

2. **Generate Extension Icons** (Required):
   - Navigate to the `icons/` folder
   - Open `icon-generator.html` in your browser
   - Click "Generate" buttons to create icon16.png, icon48.png, icon128.png
   - Or use online converter with the provided `icon.svg`

3. Load in Chrome:
   - Open Chrome and go to `chrome://extensions/`
   - Enable "Developer mode" (top right toggle)
   - Click "Load unpacked" button
   - Select the extension folder

### From Chrome Web Store
*Coming soon - extension will be published after testing*

## 📖 Usage Guide

### Getting Started
1. Click the extension icon in your toolbar to activate
2. The popup panel provides easy access to all features
3. Use keyboard shortcuts for quick toggles

### Creating Alignment Guides
- **Double-click** anywhere on a webpage to create a guide
- **Drag guides** to reposition them
- **Right-click** on any guide to delete it
- Guides automatically snap to nearby elements

### Using the Measurement Tool
1. Enable "Measure Mode" from popup or press `Ctrl+M`
2. Click and drag between any two points
3. View distance in pixels (horizontal × vertical distance)
4. Press `Escape` to exit measurement mode

### Element Inspection
- Simply hover over any element to see:
  - Current mouse position (X, Y coordinates)
  - Element dimensions (width × height)
  - Element position on page

## 🏗️ Project Structure

```
pixel-ruler-extension/
├── manifest.json              # Extension configuration
├── background.js             # Service worker - handles shortcuts & lifecycle
├── content-script/           # Scripts injected into web pages
│   ├── content-script.js     # Main ruler functionality
│   └── content-script.css    # Ruler and guide styling
├── popup/                    # Extension popup interface
│   ├── popup.html           # Popup UI structure
│   ├── popup.css            # Popup styling
│   └── popup.js             # Popup functionality
├── icons/                    # Extension icons
│   ├── icon16.png           # Toolbar icon (16×16)
│   ├── icon48.png           # Management page icon (48×48)  
│   ├── icon128.png          # Store icon (128×128)
│   ├── icon.svg             # Source SVG template
│   ├── icon-generator.html  # Icon generation tool
│   └── README.md            # Icon setup instructions
└── README.md                # This file
```

## 🛠️ Development

### Prerequisites
- Google Chrome or Chromium-based browser
- Basic knowledge of JavaScript, HTML, CSS
- Text editor (VS Code recommended)

### Local Development
1. Make changes to any file
2. Go to `chrome://extensions/`
3. Click the "Reload" icon next to your extension
4. Test changes on any webpage

### Code Architecture

#### Content Script (`content-script.js`)
- Injected into every webpage
- Handles ruler rendering and user interactions
- Manages guides, measurement, and element inspection
- Communicates with popup and background script

#### Background Script (`background.js`)  
- Handles keyboard shortcuts globally
- Manages extension lifecycle events
- Enables cross-tab functionality
- Handles context menus

#### Popup (`popup.js`)
- Provides user interface for settings
- Communicates with content script
- Manages user preferences and storage

### Testing
- Test on various websites (simple and complex layouts)
- Verify keyboard shortcuts work correctly  
- Check responsiveness at different zoom levels
- Test dark mode and high contrast scenarios

## 🤝 Contributing

We welcome contributions! Here's how to get started:

### Ways to Contribute
- 🐛 **Bug Reports** - Found an issue? Please report it!
- 💡 **Feature Requests** - Have an idea? We'd love to hear it!
- 🔧 **Code Contributions** - Submit PRs for bug fixes or new features
- 📖 **Documentation** - Help improve our guides and README
- 🎨 **Design** - UI/UX improvements and icon refinements

### Development Process
1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Make your changes
4. Test thoroughly
5. Commit changes (`git commit -m 'Add amazing feature'`)
6. Push to branch (`git push origin feature/amazing-feature`)
7. Create a Pull Request

### Code Style Guidelines
- Use clear, descriptive variable names
- Add comments for complex logic
- Follow existing code formatting
- Test on multiple websites before submitting

## 🐛 Known Issues & Limitations

- Cannot run on `chrome://` or browser internal pages
- May not work on some websites with strict Content Security Policies
- Rulers reset when navigating to new pages (by design)
- Performance may be impacted on very large/complex pages

## 🗺️ Roadmap

### v1.1 Planned Features
- [ ] Snap-to-element functionality
- [ ] Export guides as image overlay
- [ ] Color picker for custom ruler colors
- [ ] Ruler units (rem, em, %)
- [ ] Save/load guide presets

### v1.2 Planned Features  
- [ ] Cross-browser support (Firefox, Safari)
- [ ] Advanced measurement tools (angles, curves)
- [ ] Element highlighting improvements
- [ ] Performance optimizations

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- Inspired by design tools like Figma and Adobe XD
- Icons designed with accessibility and clarity in mind
- Built with modern web standards and Chrome Extension Manifest V3

## 📞 Support

- **Issues**: [GitHub Issues](https://github.com/yourusername/pixel-ruler-extension/issues)
- **Discussions**: [GitHub Discussions](https://github.com/yourusername/pixel-ruler-extension/discussions)
- **Email**: your-email@example.com

---

**Made with ❤️ for developers and designers who care about pixel-perfect precision.**

### 📈 Stats
![GitHub stars](https://img.shields.io/github/stars/yourusername/pixel-ruler-extension?style=social)
![GitHub downloads](https://img.shields.io/github/downloads/yourusername/pixel-ruler-extension/total)
![Chrome Web Store users](https://img.shields.io/chrome-web-store/users/your-extension-id)
![GitHub issues](https://img.shields.io/github/issues/yourusername/pixel-ruler-extension)
![GitHub license](https://img.shields.io/github/license/yourusername/pixel-ruler-extension)

*Replace GitHub URLs and stats with your actual repository information*