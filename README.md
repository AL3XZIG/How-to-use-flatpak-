

```markdown
# Flatpak Guide for Linux

📦 **A complete guide to installing, managing, and using Flatpak applications on Linux.**

---

## 🔧 **Installation**

### **1. Install Flatpak**
Most modern Linux distributions come with Flatpak pre-installed. If not, install it:

#### **Debian/Ubuntu & Derivatives**
```bash
sudo apt install flatpak
```

#### **Arch Linux & Derivatives**
```bash
sudo pacman -S flatpak
```

#### **Fedora**
```bash
sudo dnf install flatpak
```

#### **OpenSUSE**
```bash
sudo zypper install flatpak
```

### **2. Enable Flathub (Main Flatpak Repository)**
```bash
flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
```
*(If the command fails, try with `sudo`)*

---

## 🚀 **Basic Commands**

| Command | Description |
|---------|-------------|
| `flatpak search <app>` | Search for an app |
| `flatpak install <app>` | Install an app |
| `flatpak run <app>` | Run an installed app |
| `flatpak list` | List installed apps |
| `flatpak update` | Update all Flatpak apps |
| `flatpak uninstall <app>` | Remove an app |
| `flatpak remote-list` | List configured repositories |
| `flatpak info <app>` | Show app details |

---

## 📥 **Install Applications**

### **Example: Install Firefox**
```bash
flatpak install flathub org.mozilla.firefox
```
- `flathub` = Repository name  
- `org.mozilla.firefox` = App ID  

### **Example: Install LibreOffice**
```bash
flatpak install flathub org.libreoffice.LibreOffice
```

### **Example: Install Discord**
```bash
flatpak install flathub com.discordapp.Discord
```

---

## ▶ **Run Flatpak Applications**
After installation, run apps via:
```bash
flatpak run <app-id>
```
Example:
```bash
flatpak run org.mozilla.firefox
```
Or launch from the **application menu** (GNOME/KDE/etc.).

---

## 🔄 **Update Flatpak Apps**
```bash
flatpak update
```
*(Updates all installed Flatpak apps)*

---

## 🗑 **Remove Flatpak Apps**
```bash
flatpak uninstall <app-id>
```
Example:
```bash
flatpak uninstall org.mozilla.firefox
```

To remove unused runtimes (free up space):
```bash
flatpak uninstall --unused
```

---

## ⚠ **Troubleshooting**

### **App Not Showing in Menu?**
- Restart the session (log out & in).
- Rebuild the menu cache:
  ```bash
  sudo update-desktop-database
  ```

### **Permission Issues?**
Flatpak apps run in a sandbox. To grant more permissions (e.g., file access):
```bash
flatpak override --filesystem=home <app-id>
```
Example:
```bash
flatpak override --filesystem=home org.mozilla.firefox
```

### **Where Are Flatpak Apps Installed?**
Flatpak apps are stored in:
- **User installation:** `~/.var/app/`
- **System-wide installation:** `/var/lib/flatpak/`

---

## 🖥 **GUI Tools for Flatpak**
- **GNOME Software** / **KDE Discover** → Supports Flatpak.
- **Flatseal** (Manage permissions graphically):
  ```bash
  flatpak install flathub com.github.tchx84.Flatseal
  ```

---

## ✅ **Advantages of Flatpak**
✔ **Sandboxed** (More secure)  
✔ **Cross-distro** (Works on Ubuntu, Arch, Fedora, etc.)  
✔ **Stable & Latest Apps** (No dependency conflicts)  
✔ **Easy to manage**  

---

## 📝 **Notes**
- Flatpak apps may use more disk space (due to bundled dependencies).
- Some apps (like Steam) may need extra permissions (`flatpak override`).

---

📌 **Enjoy thousands of apps from [Flathub](https://flathub.org/)!** 🚀  

```
