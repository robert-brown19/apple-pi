cat /proc/cpuinfo | grep Model
sudo apt update && sudo apt full-upgrade -y
- sudo apt install opensc libpam-pkcs11 auditd ufw libpam-pwquality apparmor vlock aide chrony -y

- sudo apt install libopencv-dev libcamera-dev libcamera-v4l2 libcamera-tools libavdevice-dev libmicrohttpd-dev libmariadb-dev libfftw3-dev libfftw3-double3 libmariadb-dev libmariadb3 mariadb-client mariadb-client-core mariadb-common mariadb-server -y

- sudo apt install autoconf automake autopoint build-essential pkgconf libtool libzip-dev libjpeg-dev git libavformat-dev libavcodec-dev libavutil-dev libswscale-dev libavdevice-dev libopencv-dev libwebp-dev gettext libmicrohttpd-dev libmariadb-dev libcamera-dev libcamera-tools libcamera-v4l2 libasound2-dev libpulse-dev libfftw3-dev

- sudo apt install ffmpeg v4l-utils libavcodec-dev libavdevice-dev libavformat-dev libswresample-dev nginx-common nginx-core libnginx-mod-rtmp -y


64bit

wget https://github.com/Motion-Project/motionplus/releases/download/release-0.2.1/bookworm_motionplus_0.2.1-1_arm64.deb
wget https://github.com/Motion-Project/motionplus/releases/download/release-0.2.1/bookworm_motionplus_0.2.1-1_armhf.deb

wget https://github.com/Motion-Project/motionplus/releases/download/release-0.2.1/bookworm_motionplus_0.2.1-1_amd64.deb

sudo dpkg -i bookworm_motionplus_0.2.1-1_arm64.deb 
sudo dpkg -i bookworm_motionplus_0.2.1-1_armhf.deb

sudo dpkg -i bookworm_motionplus_0.2.1-1_amd64.deb

text_left CameraID
text_right ip_Address\n%Y-%m-%d\n%T-%q
text_scale 2

sudo mariadb
GRANT ALL ON *.* TO 'motiondb'@'localhost' IDENTIFIED BY 'password' WITH GRANT OPTION;
FLUSH PRIVILEGES;
exit

mariadb -u motiondb -p
password
create database motionplus;
use motionplus;
quit;

database_type mariadb
database_dbname motionplus
database_host localhost
database_port 3306
database_user motiondb
database_password password

sudo systemctl status MariaDB

sudo nano /etc/nginx/nginx.conf

rtmp {
server {
    listen 1935;
    timeout 60s;
    notify_method post;
    chunk_size 4096;

application pi {
live on;
record off;
        }
}
}


