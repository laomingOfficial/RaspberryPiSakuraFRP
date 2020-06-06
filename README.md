# SakuraFRP 架设树莓派外网
进入terminal，然后输入以下
1) sudo mkdir -p /opt/sakurafrp && cd /opt/sakurafrp
2) sudo wget https://qianqu.me/frp/frpc_linux_arm
3) sudo chmod +x frpc_linux_arm
4) sudo wget -O /etc/systemd/system/sakurafrp.service https://raw.githubusercontent.com/laomingOfficial/SakuraFRP/master/sakurafrp.service
5) sudo nano /etc/systemd/system/sakurafrp.service

6) 替换以下的"访问密钥"和"服务器ID"
ExecStart=/opt/sakurafrp/frpc_linux_arm -t 访问密钥 -s 服务器ID
---
systemctl daemon-reload
启动服务
systemctl start sakurafrp
将服务设置为开机启动
systemctl enable sakurafrp
停止运行服务
systemctl stop sakurafrp
将服务设置为禁止开机启动
systemctl disable sakurafrp