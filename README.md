# TranslatePad - Notepad with Translator

A beautiful, dual-pane notepad application with built-in translation capabilities. Write notes in one language and instantly translate them to another!

![TranslatePad Screenshot](https://via.placeholder.com/800x400.png?text=TranslatePad+Screenshot)

## Features

- **Dual-Pane Interface** - Write in the left panel, see translations in the right panel
- **Multi-Language Support** - Translate between 12 different languages
- **Smart Translation** - Real-time translation simulation (easily replaceable with real API)
- **Note Management** - Save, load, and delete notes with timestamps
- **Auto-Save** - Automatically saves your work every 30 seconds
- **Word & Character Counter** - Real-time statistics for both panes
- **Copy Functionality** - Copy both original and translated text with one click
- **Responsive Design** - Works seamlessly on mobile, tablet, and desktop
- **Local Storage** - All notes are saved in your browser
- **No Account Required** - Start using immediately

##  Live Demo

[View Live Demo](#) (Add your deployment link here)

##  Technologies Used

- HTML5
- CSS3 (with Flexbox & Grid)
- Vanilla JavaScript
- Local Storage API

##  Supported Languages

| Language | Code |
|----------|------|
| Spanish | es |
| French | fr |
| German | de |
| Italian | it |
| Portuguese | pt |
| Russian | ru |
| Japanese | ja |
| Korean | ko |
| Chinese | zh |
| Arabic | ar |
| Hindi | hi |
| Dutch | nl |

##  Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/translatepad.git
```

2. Navigate to the project directory:
```bash
cd translatepad
```

3. Open `index.html` in your browser:
```bash
# On macOS
open index.html

# On Windows
start index.html

# On Linux
xdg-open index.html
```

That's it! No build process or dependencies required.

## 🔧 Usage

1. **Write your note** in the left text area
2. **Select a target language** from the dropdown menu
3. **Click "Translate"** to see the translation (simulated in demo)
4. **Save your note** with a custom title using the "Save" button
5. **Access saved notes** from the bottom panel
6. **Clear or copy** content using the toolbar buttons

##  Key Features Explained

### Note Management
- **Save Notes** - Store notes with custom titles and timestamps
- **Load Notes** - Click on any saved note to open it
- **Delete Notes** - Remove unwanted notes with one click
- **Auto-Save** - Never lose your work with automatic backup

### Translation System
The current version uses a mock translation function for demonstration. To implement real translations:

1. **Google Cloud Translation API**
```javascript
async function translateWithGoogle(text, targetLang) {
    const response = await fetch(
        `https://translation.googleapis.com/language/translate/v2?key=YOUR_API_KEY&q=${encodeURIComponent(text)}&target=${targetLang}`
    );
    const data = await response.json();
    return data.data.translations[0].translatedText;
}
```

2. **Microsoft Translator API**
```javascript
async function translateWithMicrosoft(text, targetLang) {
    // Implementation for Microsoft Translator
}
```

3. **LibreTranslate** (Open Source)
```javascript
async function translateWithLibre(text, targetLang) {
    // Implementation for LibreTranslate
}
```

##  Project Structure

```
translatepad/
│
├── index.html          # Main application file
├── README.md           # Project documentation
├── LICENSE             # MIT License
└── screenshot.png      # Application screenshot
```

##  Customization

### Adding More Languages
Edit the `targetLanguage` select element in the HTML:

```html
<select id="targetLanguage" class="language-select">
    <option value="es">Spanish</option>
    <option value="fr">French</option>
    <!-- Add your languages here -->
</select>
```

Then update the `mockTranslate` function:

```javascript
function mockTranslate(text, targetLang) {
    const translations = {
        // Add your translations here
        'newlang': 'Your translation here'
    };
}
```

### Styling
Modify the CSS variables in the `<style>` section to change the color scheme:

```css
body {
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    /* Change these colors */
}
```

##  API Integration Guide

To replace the mock translation with a real API:

1. **Get an API key** from your preferred translation service
2. **Replace the `mockTranslate` function** with actual API calls
3. **Add error handling** for API failures
4. **Implement rate limiting** if needed

Example with Google Translate API:
```javascript
async function translateNote() {
    const text = document.getElementById('originalNote').value;
    const targetLang = document.getElementById('targetLanguage').value;
    
    try {
        const response = await fetch(
            `https://translation.googleapis.com/language/translate/v2?key=YOUR_API_KEY&q=${encodeURIComponent(text)}&target=${targetLang}`
        );
        const data = await response.json();
        document.getElementById('translatedNote').value = 
            data.data.translations[0].translatedText;
    } catch (error) {
        alert('Translation failed: ' + error.message);
    }
}
```

##  Browser Support

- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)
- Opera (latest)
- Mobile browsers (iOS Safari, Chrome for Android)

##  Contributing

Contributions are welcome! Here's how you can help:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

### Contribution Ideas
- Add real translation API integration
- Implement speech-to-text for note-taking
- Add dark mode
- Create export options (PDF, TXT, DOC)
- Add note categories/tags
- Implement search functionality
- Add keyboard shortcuts
- Create a backend for cloud storage

## License

Distributed under the MIT License. See `LICENSE` for more information.

## Acknowledgments

- Icons and emojis for UI elements
- Gradient background inspired by [uiGradients](https://uigradients.com/)
- Local storage concept for data persistence

## Contact

Om Gedam

GitHub: @itsomg134

Email: omgedam123098@gmail.com

Twitter (X): @omgedam

LinkedIn: Om Gedam

Portfolio: https://ogworks.lovable.app

## Future Enhancements

- [ ] Real API integration
- [ ] Dark mode
- [ ] PDF export
- [ ] Cloud sync
- [ ] Mobile app version
- [ ] Voice input
- [ ] Text-to-speech for translations
- [ ] Note categories and tags
- [ ] Search functionality
- [ ] Keyboard shortcuts
- [ ] Multiple note templates
- [ ] Share notes via link
