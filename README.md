## Easy Input Shaper UI

It provide a web-ui for running `SHAPER_CALIBRATE` and generate charts.

![image-20230426104629163](https://img.mpx.wiki/i/2023/04/26/6448908838c9c.webp)

![image-20230426105049366](https://img.mpx.wiki/i/2023/04/26/6448918c644f5.webp)



## Usage 

### Install 

> The current executable only works on ARM. If you use it on x86, you need to compile it yourself.

```shell
cd ~
git clone https://github.com/lraithel15133/EIS-port8081
cd EIS
chmod +x ./eis
chmod +x install.sh
sudo ./install.sh  
nohup ./eis &
```

Open http://\<your-ip\>:8081

Set Socket Config and Path Config

> Only need to set them once, and it will be saved automatically.

You can see socket address here

![image-20230426111842338](https://img.mpx.wiki/i/2023/04/26/64489814881e9.webp) 

![image-20230426111854094](https://img.mpx.wiki/i/2023/04/26/6448981fb07cf.webp)

![image-20230426112046247](https://img.mpx.wiki/i/2023/04/26/64489890f037c.webp)

Path is your klipper path, usually it's `/home/pi/klipper`, for CB1 it's `/home/biqu/klipper`

![image-20230426112136416](https://img.mpx.wiki/i/2023/04/26/644898c2c4d69.webp)

That's all, now you can click ` +New Test` , when it shows 100% Command completed, just refresh the webpage.

** Must home and qgl before test 



### Compile

If the stock binary file does not work, you can try compiling it

```shell
cd ~
git clone https://github.com/lraithel15133/EIS-port8081
cd EIS
wget -qO- https://raw.githubusercontent.com/voidint/g/master/install.sh | bash
source /home/pi/.g/env
g install 1.18
go mod tidy 
rm eis
go build -o eis main.go 
chmod +x eis

```

Then follow `Install` above 

## PR

Welcome any PR. 
