 Задание1.Как грузится моя машина
Режим загрузки
 наличие каталога `/sys/firmware/efi`:
```bash
ls /sys/firmware/efi
Вывод
ls: невозможно получить доступ к '/sys/firmware/efi': Нет такого файла или каталога
Вывод: Каталог отсутствует, значит, система загружается в режиме BIOS (Legacy), а не UEFI. В режиме UEFI этот каталог существует и содержит файлы прошивки.
2. Структура диска
Выполнил команду:lsblk -f
Вывод
 NAME   FSTYPE   FSVER  LABEL                           UUID                                 FSAVAIL FSUSE% MOUNTPOINTS
sda                                                                                                    
├─sda1                                                                                                 
├─sda2   vfat     FAT32                                  5620-34FB                             505,8M     1% /boot/efi
─sda3   ext4     1.0                                    7e954d2c-666c-4405-8426-c4ede4dab4bd   27,1G    25% /
sr0    iso966   Joliet Linux Mint 22.3 Cinnamon 64-bit  2026-04-17-15-33-05-00                    0   100% /media/riki/Linux Mint 22.3 Cinnamon 64-bit
Таблица разделов:
Раздел   Файловая система           Точка монтирования          Назначение
sda1      (нет)                        -                         Служебный раздел (возможно, BIOS boot partition)

sda2      vfat (FAT32)               /boot/efi                   ESP-раздел (хранилище загрузчика)

sda3      ext4                       /                           Корневой раздел (сама система)

sr0      	 	iso9660                  /media/riki/...             Виртуальный CD-привод с установочным образом (не используется)
3. Версии ядра
 текущее ядро:6.17.0-20-generic
 все установленные ядра: -rw-r--r-- 1 root root 16734280 мар 19  2026 /boot/vmlinuz-6.17.0-20-generic
