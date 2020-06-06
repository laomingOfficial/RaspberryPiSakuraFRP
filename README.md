# SakuraFRP 架设树莓派外网
进入terminal，然后输入以下
1) sudo mkdir -p /opt/sakurafrp
2) sudo wget -O /opt/sakurafrp/frpc_linux_arm https://qianqu.me/frp/frpc_linux_arm
3) sudo chmod +x /opt/sakurafrp/frpc_linux_arm
4) sudo wget -O /etc/systemd/system/sakurafrp.service https://raw.githubusercontent.com/laomingOfficial/SakuraFRP/master/sakurafrp.service
5) sudo nano /etc/systemd/system/sakurafrp.service
6) 替换以下的"访问密钥"和"服务器ID"
ExecStart=/opt/sakurafrp/frpc_linux_arm -t 访问密钥 -s 服务器ID
---
重载所有修改过的配置文件  
sudo systemctl daemon-reload  

启动服务  
sudo systemctl start sakurafrp  

将服务设置为开机启动  
sudo systemctl enable sakurafrp  

停止运行服务  
sudo systemctl stop sakurafrp  

将服务设置为禁止开机启动  
sudo systemctl disable sakurafrp  

检测服务状态  
sudo systemctl status sakurafrp  