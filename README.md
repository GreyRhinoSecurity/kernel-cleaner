# Kernel Cleaner 🧹

`kernel-cleaner` is a lightweight utility that safely removes old kernel files from `/boot`, helping systems with limited space (like Kali Linux) stay clean and updatable.

## 📦 Features

- Keeps only the **currently running kernel** in `/boot`
- Skips non-regular files and directories
- Logs cleanup to `/var/log/kernel-cleaner.log`
- CLI flags:
  - `--help` — show usage info
  - `--info` — preview files that will be removed
- Weekly auto-clean via `systemd`
- Includes a proper `man` page (`man kernel-cleaner`)

## 🛠 Installation

```bash
sudo dpkg -i kernel-cleaner_2.0_systemd_help_man.deb
sudo systemctl enable --now kernel-cleaner.timer
```

## 🚀 Usage

```bash
kernel-cleaner --help     # show help
kernel-cleaner --info     # preview what will be removed
sudo kernel-cleaner       # perform cleanup
```

## 🧼 Log

Check cleanup history:

```bash
cat /var/log/kernel-cleaner.log
```

## 📅 Schedule

A `systemd` timer runs `kernel-cleaner` automatically every week:

```bash
systemctl status kernel-cleaner.timer
```

## 📚 Man Page

```bash
man kernel-cleaner
```

## ✨ Author

Github @greyrhinosec
