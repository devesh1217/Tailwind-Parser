# Tailwind CSS Live Editor

## Overview

The **Tailwind CSS Live Editor** is an interactive tool designed to help developers experiment with Tailwind CSS in real-time. It features a code editor and a live preview pane, allowing users to see the results of their changes instantly. The project is built with **CodeMirror** for the editor and includes a documentation popup for quick reference.

## Features

- **Real-Time Preview**: See your Tailwind CSS changes instantly in the preview pane.
- **CodeMirror Integration**: A powerful code editor with syntax highlighting, auto-completion, and keyboard shortcuts.
- **Documentation Popup**: Access Tailwind CSS documentation directly within the app.
- **Save and Reset**: Save your work as an HTML file or reset the editor to its initial state.
- **Keyboard Shortcuts**: Includes VS Code-like shortcuts for faster editing.

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/your-repo/tailwind-parser.git
   cd tailwind-parser
   ```

2. Open the project in your favorite code editor.

3. Serve the project using a local server (e.g., VS Code Live Server or Python's HTTP server):
   ```bash
   python -m http.server
   ```

4. Open `index.html` in your browser.

## Usage

1. Start typing your Tailwind CSS code in the editor on the left.
2. View the live preview on the right.
3. Use the **Save File** button to download your code as an HTML file.
4. Use the **Reset** button to restore the editor to its initial state.
5. Click the **Docs** button to open the Tailwind CSS documentation popup.

## Keyboard Shortcuts

| Shortcut       | Action                     |
|----------------|----------------------------|
| `Ctrl + /`     | Toggle comment             |
| `Ctrl + Space` | Auto-complete              |
| `Ctrl + S`     | Save file                  |
| `Ctrl + D`     | Multi-select               |
| `Alt + ↑/↓`    | Move line up/down          |
| `Ctrl + [`     | Outdent                    |
| `Ctrl + ]`     | Indent                     |
| `Tab`          | Indent or insert soft tab  |
| `Shift + Tab`  | Outdent                    |

## File Structure

```
e:\Project\Tailwind Parser\
├── assets/                # Images and other assets
├── libs/                  # CodeMirror and Tailwind dependencies
├── index.html             # Main HTML file
├── tailwind-css-documentation.md # Tailwind CSS documentation
└── readme.md              # Project README
```

## Contributing

Contributions are welcome! Feel free to submit a pull request or open an issue for any bugs or feature requests.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgments

- [Tailwind CSS](https://tailwindcss.com/)
- [CodeMirror](https://codemirror.net/)
- Developed by **Team Nexus**.
