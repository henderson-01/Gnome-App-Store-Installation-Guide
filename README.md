# 🚀 Universal App Store for Ubuntu

Manage **Snap**, **Flatpak**, and **.deb** packages in one powerful, unified interface.

By default, Ubuntu’s "App Center" focuses heavily on Snaps. This guide helps you set up the official **GNOME Software** center to provide a truly universal experience including Flathub and traditional Debian packages.

---

## 📋 Prerequisites

Before starting, ensure you have:

* A computer running **Ubuntu** (20.04, 22.04, 24.04, or newer).
* An active **internet connection**.
* **Sudo** (administrative) privileges.

---

## 🛠️ Installation Steps

### Step 1: Update Your System

Ensure your package database is current to avoid installation conflicts:

```bash
sudo apt update && sudo apt upgrade -y
```

### Step 2: Install GNOME Software & Multi-Format Support

This command installs the store interface and the plugins required to handle both Flatpaks and Snaps:

```bash
sudo apt install gnome-software gnome-software-plugin-flatpak gnome-software-plugin-snap flatpak -y
```

* **gnome-software**: The graphical store interface.
* **gnome-software-plugin-flatpak**: Integration for Flathub.
* **gnome-software-plugin-snap**: Integration for the Snap Store.

### Step 3: Add the Flathub Repository

Enable the world's largest Flatpak repository:

```bash
flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
```

### Step 4: Restart Your System (Crucial!)

For the store to properly index the new repositories and integrate the "Source" toggle, you must reboot.

```bash
reboot
```

---

## 🛍️ How to Use Your New Store

* Search your applications for **Software**.

>[!NOTE]
> You will now see two stores. Use the **white shopping bag** icon for the universal experience.

* **Switching Between Formats:**

* Search for an app (e.g., *Discord* or *VLC*).
* Click on the application to open its details page.
* In the top-right corner (or under the "Install" button), use the **Source dropdown menu** to choose between **Flatpak (Flathub)**, **Snap Store**, or **Ubuntu (deb)**.

> [!TIP]
> **Flatpaks** are often updated faster than Snaps or .debs, making them ideal for the latest versions of apps like GIMP, OBS Studio, or Inkscape.

---

## 💡 Troubleshooting

**If the store is empty!**
Sometimes the store appears empty or search results aren't appearing after the first reboot, give it a few minutes to download metadata in the background. You can force a refresh by running:

```bash
flatpak update
```

---

## 🧹 (Optional) Uninstall the Ubuntu App Center

If you prefer to use GNOME Store exclusively and want to remove the default Ubuntu App center to avoid confusion:

```Bash
sudo snap remove snap-store
```

> [!TIP]
> This only removes the storefront app. Any apps you previously installed via Snap will remain installed and will now be manageable through your new universal store the **GNOME Store**.

## ⚠️ Disclaimer

This is provided "as is" without warranty of any kind. I am not responsible for any damage, data loss, or issues caused by the use of this information. **Use it at your own risk.**
