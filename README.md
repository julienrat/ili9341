# ili9341


Installation of aliexpress/alibaba/ebay 2.2 lcd screen on Raspbian Jessie.

http://fr.aliexpress.com/item/Wholesale-1PC-2-2-Inch-240-320-Dots-SPI-TFT-LCD-Serial-Port-Module-Display-ILI9341/1776409033.html?spm=2114.06020208.3.1.OtCkDr&ws_ab_test=searchweb201556_6,searchweb201644_2_505_506_503_504_502_10001_10002_10016_10017_10010_10005_10011_10006_10003_10004_401_10009_10008,searchweb201560_1,searchweb1451318400_-1,searchweb1451318411_6449&btsid=52cc5f70-bf3f-4e78-88e5-b22bf170a76a


##modprobe 

###Test it !
```
sudo modprobe fbtft_device custom name=fb_ili9341 gpios=reset:25,dc:24,led:18 speed=16000000 rotate=90 bgr=1
```

If it is correct, your screen will refresh.

```
con2fbmap 1 1
```
With this command you will be able to see startup messages.

###Make it permanent on jessie
Create and edit this file :
```
sudo nano /etc/modules-load.d/fbtft.conf
```
Put it this lines, and save (CTRL-X ; Y)
```
spi-bcm2835
fbtft_device
```
Create and edit this file to set fbtft_devices options :
```
sudo nano /etc/modprobe.d/fbtft.conf
```
Put it this line, and save (CTRL-X ; Y)
```
options fbtft_device custom name=fb_ili9341 gpios=reset:25,dc:24,led:18 speed=16000000 rotate=90 bgr=1

```


