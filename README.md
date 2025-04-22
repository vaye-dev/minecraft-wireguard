server:
setup firewall to accept: 22/tcp 51820/udp 25565/udp/tcp 
echo 'net.ipv4.ip_forward=1' | sudo tee -a /etc/sysctl.conf
sudo sysctl -p
move server/wg0.conf to /etc/wireguard/wg0.conf
sudo wg-quick up wg0

client:
move client/wg0.conf to /etc/wireguard/wg0.conf
sudo wg-quick up wg0
