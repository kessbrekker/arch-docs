# 🧠 Arch Linux Terminal Komut Rehberi

Bu belge, **Arch Linux** kullanıcıları için sistem yönetimi, ağ, disk, kullanıcı ve bakım komutlarını hızlıca erişilebilir hale getirir.

---

## 📦 `yay` Komutları (AUR Yardımcısı)

| Komut | Açıklama |
|-------|-----------|
| `yay -S <paket>` | Yeni paket kurar (resmi repo veya AUR). |
| `yay -R <paket>` | Paketi kaldırır. |
| `yay -Rns <paket>` | Paketi ve artık bağımlılıkları kaldırır. |
| `yay -Ss <arama>` | Paket arar (AUR dahil). |
| `yay -Si <paket>` | Paket hakkında bilgi verir. |
| `yay -Syu` | Sistemdeki tüm paketleri günceller (AUR dahil). |
| `yay -Yc` | Kullanılmayan bağımlılıkları siler. |
| `yay -Ps` | Sistem bilgisi ve AUR istatistiklerini gösterir. |
| `yay -Qi <paket>` | Kurulu paket hakkında bilgi verir. |
| `yay -Ql <paket>` | Paketin kurduğu dosyaları listeler. |
| `yay -G <paket>` | AUR paketini (PKGBUILD) klonlar. |

---

## 🧰 `pacman` Komutları (Resmi Depo Yöneticisi)

| Komut | Açıklama |
|-------|-----------|
| `sudo pacman -S <paket>` | Yeni paket kurar. |
| `sudo pacman -R <paket>` | Paketi kaldırır. |
| `sudo pacman -Rns <paket>` | Paketi ve artık bağımlılıkları kaldırır. |
| `sudo pacman -Ss <arama>` | Paket arar. |
| `sudo pacman -Si <paket>` | Paket hakkında bilgi verir. |
| `sudo pacman -Sy` | Paket veritabanını senkronize eder. |
| `sudo pacman -Syu` | Tüm sistemi günceller. |
| `sudo pacman -Syyu` | Zorunlu senkronizasyon + sistem güncellemesi. |
| `sudo pacman -Qi <paket>` | Kurulu paket hakkında bilgi verir. |
| `sudo pacman -Ql <paket>` | Kurulu paketin dosyalarını listeler. |
| `sudo pacman -Qdt` | Artık kullanılmayan bağımlılıkları listeler. |
| `sudo pacman -Qdtq` | Artık bağımlılıkların sadece isimlerini listeler. |
| `sudo pacman -Rns $(pacman -Qdtq)` | Tüm artık bağımlılıkları kaldırır. |
| `sudo pacman -Sc` | Eski paket önbelleğini temizler. |
| `sudo pacman -Scc` | Tüm paket önbelleğini temizler (dikkatli kullan). |


---
## ⚙️ Servis Yönetimi (systemd)

| Komut | Açıklama |
|:------|:----------|
| `systemctl status <servis>` | Servisin durumunu gösterir. |
| `sudo systemctl start <servis>` | Servisi başlatır. |
| `sudo systemctl stop <servis>` | Servisi durdurur. |
| `sudo systemctl restart <servis>` | Servisi yeniden başlatır. |
| `sudo systemctl enable <servis>` | Servisi açılışta başlatır. |
| `sudo systemctl disable <servis>` | Servisi açılışta devre dışı bırakır. |
| `systemctl list-units --type=service` | Aktif servisleri listeler. |
| `journalctl -xe` | Servis hatalarını ve logları gösterir. |

---

## 🌐 Ağ ve İnternet

| Komut | Açıklama |
|:------|:----------|
| `ip a` | Ağ arayüzlerini ve IP adreslerini gösterir. |
| `ping -c 4 google.com` | İnternet bağlantısını test eder. |
| `iwctl` | Wi‑Fi bağlantı yöneticisini açar (iwd için). |
| `nmcli device wifi list` | Wi‑Fi ağlarını listeler (NetworkManager). |
| `nmcli device wifi connect <SSID> password <şifre>` | Kablosuz ağa bağlanır. |
| `curl ifconfig.me` | Dış IP adresini gösterir. |
| `sudo systemctl restart NetworkManager` | Ağ servisini yeniden başlatır. |

---

## 💾 Disk ve Dosya Yönetimi

| Komut | Açıklama |
|:------|:----------|
| `lsblk` | Disk bölümlerini listeler. |
| `df -h` | Disk kullanımını gösterir. |
| `du -sh *` | Klasörlerin boyutlarını özetler. |
| `sudo fdisk -l` | Tüm diskleri listeler. |
| `sudo mount /dev/sdXY /mnt` | Bir bölümü bağlar. |
| `sudo umount /mnt` | Bağlı diski ayırır. |
| `sudo mkfs.ext4 /dev/sdXY` | Disk bölümünü ext4 olarak biçimlendirir. |
| `sudo fsck /dev/sdXY` | Disk hatalarını denetler. |

---

## 👤 Kullanıcı ve İzin Yönetimi

| Komut | Açıklama |
|:------|:----------|
| `sudo useradd -m <kullanıcı>` | Yeni kullanıcı oluşturur. |
| `sudo passwd <kullanıcı>` | Kullanıcıya parola atar. |
| `sudo userdel -r <kullanıcı>` | Kullanıcıyı ve home dizinini siler. |
| `sudo usermod -aG wheel <kullanıcı>` | Kullanıcıyı sudo grubuna ekler. |
| `groups <kullanıcı>` | Kullanıcının bulunduğu grupları gösterir. |
| `sudo visudo` | Sudo yetkilerini düzenler. |

---

## 🧠 Sistem Bilgisi ve Donanım

| Komut | Açıklama |
|:------|:----------|
| `neofetch` veya `fastfetch` | Sistem özet bilgisi gösterir. |
| `uname -a` | Kernel ve sistem mimarisi bilgisi. |
| `lscpu` | CPU bilgilerini listeler. |
| `lsusb` | USB aygıtlarını gösterir. |
| `lspci` | PCI aygıtlarını gösterir. |
| `free -h` | Bellek kullanımını gösterir. |
| `top` veya `htop` | Gerçek zamanlı işlem listesi. |
| `ps aux \| grep <program>` | Belirli bir işlemi arar. |
| `df -Th` | Disk türü ve boyutlarını gösterir. |

---

## 🧹 Sistem Temizliği ve Optimizasyon

| Komut | Açıklama |
|:------|:----------|
| `sudo journalctl --vacuum-time=7d` | Log dosyalarını 7 günden eskileriyle birlikte temizler. |
| `sudo pacman -Rns $(pacman -Qdtq)` | Artık bağımlılıkları temizler. |
| `sudo paccache -r` | Paket önbelleğini azaltır (sadece son 3 sürüm kalır). |
| `sudo du -sh /var/cache/pacman/pkg/` | Pacman önbellek boyutunu gösterir. |

---

## 🧰 Gelişmiş ve Yardımcı Komutlar

| Komut | Açıklama |
|:------|:----------|
| `sudo timedatectl set-ntp true` | Sistem saatini otomatik senkronize eder. |
| `sudo hwclock --systohc` | Donanım saatini sistem saatine eşitler. |
| `sudo pacman -S reflector rsync` | Mirror yönetimi araçlarını kurar. |
| `sudo pacman -S base-devel git` | AUR derleme için gerekli temel araçları kurar. |
| `yay -Ps` | AUR ve sistem istatistiklerini gösterir. |

---

## 💡 İpuçları
- Her zaman sistem güncellemeden önce `sudo pacman -Syyu` veya `yay -Syu` kullan.  
- AUR derlemelerinde hata alırsan, `~/.cache/yay/` klasörünü temizle.  
- Sistem yüklerini izlemek için `htop`, `glances` veya `bpytop` kullan.  

---

**Hazırlayan:** Said  
**Sürüm:** 2.0  
**Format:** Markdown (`.md`)
