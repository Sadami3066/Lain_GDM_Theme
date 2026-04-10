# GDM Theme

A lain theme.

![preview](lain.jpg)

## Installation

### Method 1: Direct Replace (Pre-compiled)

1. Download `gnome-shell-theme.gresource` from this project

2. Locate the theme directory currently in use (Ubuntu 25.10 Yaru theme example):

   ```bash
   sudo cp gnome-shell-theme.gresource /usr/share/gnome-shell/theme/Yaru/
   ```

3. Reboot to apply changes

> **⚠️ Warning**: This will overwrite the original system theme. It's recommended to backup the original file or test in a safe environment.
>
> ```bash
> # Backup original file (requires root)
> sudo cp /usr/share/gnome-shell/theme/Yaru/gnome-shell-theme.gresource /usr/share/gnome-shell/theme/Yaru/gnome-shell-theme.gresource.backup
> ```

### Method 2: Clone and Replace

```bash
# Clone the project
git clone https://github.com/your-repo/gdmtheme.git
cd gdmtheme

# Replace system theme file
sudo cp gnome-shell-theme.gresource /usr/share/gnome-shell/theme/Yaru/
```

## Development

If you want to customize the background image, colors, or other styles, you can modify the CSS and recompile the theme.

### Step 1: Modify Styles

Edit `gdm.css` to customize:

- Background image: `background-image: url('lain.jpg');`
- Colors: `color: #ffffff;`
- Border radius: `border-radius: 16px;`

> You can send your modification requirements to an AI assistant to help with CSS changes.

### Step 2: Compile Theme

After modifying the CSS, compile all resource files into a `.gresource` file:

```bash
# Go to project directory
cd gdmtheme

# Compile theme using gresource
glib-compile-resources --target=gnome-shell-theme.gresource --sourcedir=. gnome-shell-theme.gresource.xml
```

### Step 3: Replace File

Once compiled, replace the system theme file following the steps in the "Installation" section.

### Backup and Restore

To restore the original theme:

```bash
sudo cp /usr/share/gnome-shell/theme/Yaru/gnome-shell-theme.gresource.backup /usr/share/gnome-shell/theme/Yaru/gnome-shell-theme.gresource
```

## File Description

| File | Description |
|------|------------|
| `gnome-shell-theme.gresource` | Compiled theme resource file |
| `gnome-shell-theme.gresource.xml` | Resource manifest (used for compilation) |
| `gdm.css` | GDM login interface styles |
| `gnome-shell-dark.css` | Dark theme styles |
| `gnome-shell-light.css` | Light theme styles |
| `lain.jpg` | Background image |