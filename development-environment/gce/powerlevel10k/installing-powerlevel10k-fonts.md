---
description: >-
  Installing Powerlevel10k fonts, in Linux involves downloading the font files
  and placing them in the appropriate system directory, then configuring your
  terminal to use them.
---

# 😄 Installing Powerlevel10k fonts

.1. Download the MesloLGS NF Fonts:Download the four recommended MesloLGS NF font files from the official Powerlevel10k GitHub repository. These include: MesloLGS NF Regular.ttf, MesloLGS NF Bold.ttf, MesloLGS NF Italic.ttf, and MesloLGS NF Bold Italic.ttf.You can typically find these files in the `romkatv/dotfiles-public` repository under `.local/share/fonts/NerdFonts/`.2. Install the Fonts:There are two primary methods to install fonts in Linux:

* **Graphical Installation (Double-click):** In most desktop environments, you can simply double-click each `.ttf` file. This will open a font viewer application, where you can click an "Install" button to add the font to your system.
* **Manual Installation (Copying files):**
  * Create a directory for user-specific fonts if it doesn't exist:

Code

```
        mkdir -p ~/.local/share/fonts
```

* Copy the downloaded `.ttf` files into this directory:

Code

```
        cp ~/Downloads/MesloLGS\ NF*.ttf ~/.local/share/fonts/
```

(Adjust `~/Downloads/` if you saved them elsewhere.) Update the font cache.Code

```
        fc-cache -fv ~/.local/share/fonts/
```

3\. Configure Your Terminal:After installing the fonts, you need to configure your terminal emulator to use MesloLGS NF as its font. The exact steps vary depending on your terminal:&#x20;

* **GNOME Terminal:** Open Terminal -> Preferences -> Profiles. Select your profile, check "Custom font" under Text Appearance, and choose "MesloLGS NF Regular".
* **Microsoft Terminal (WSL):** Open Settings (Ctrl+,), search for `fontFace`, and set the value to `MesloLGS NF` for each profile you want to use it with.
* **Other Terminals:** Consult your specific terminal's documentation or preferences for changing the font. Look for settings related to "Font," "Text," or "Appearance."

4\. Verify Installation (Optional):You can verify that the fonts are correctly installed and recognized by your system by running:Code

```
fc-list | grep MesloLGS
```

This should display entries for the MesloLGS NF fonts you installed.Once these steps are completed, restart your terminal, and the Powerlevel10k configuration wizard should automatically start, allowing you to customize your prompt's appearance using the newly installed fonts. If the wizard doesn't start automatically, you can manually run it with `p10k configure`
