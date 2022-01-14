````shell
vagrant ssh k8s-node1
su root  vagrant

vi /etc/ssh/sshd_config
PasswordAuthentication yes

service sshd restart 
exit;
exit;
````



网络环境  设置好网络

ip route show

ip addr



关闭防火墙

systemctl stop firewalld

systemctl disable firewalld



关闭slinux

sed -i 's/enforcing/disabled/'  /etc/selinux/config

setenforce 0

关闭swap  临时的

swapoff -a



永久的   `sed -ri 's/.*swap.*/#&/' /etc/fstab`

free -g 验证



主机名和ip地址对应关系

hostname

vi /etc/hosts

10.0.2.15 k8s-node1

10.0.2.4 k8s-node2

10.0.2.5 k8s-node3



将桥接的ipv4流量传递到iptables的链



cat > /etc/sysctl.d/k8s.conf << EOF

net.bridge.bridge-nf-call-ip6tables = 1

net.bridge.bridge-nf-call-iptables = 1

EOF

sysctl --system



安装docker kubeadm kubelet kubectl

kubeadm-1.23.1

kubelet-1.23.1

kubectl-1.23.1



yum install -y kubeadm-1.23.1 kubelet-1.23.1 kubectl-1.23.1

systemctl enable kubelet 

systemctl start kubelet



kubeadm init --apiserver-advertise-address=10.0.2.15 --image-repository registry.cn-hangzhou.aliyuncs.com/google_containers --kubernetes-version v1.23.1 --service-cidr=10.96.0.0/16 --pod-network-cidr=10.244.0.0/16



10.0.2.15





kubeadm join 10.0.2.15:6443 --token 3ed4vq.jogdl7o2a67r2e9n \
        --discovery-token-ca-cert-hash sha256:53f499394872d3f4ecb94356e528086a6c39e17b99d0f1fbbabd60df2901c8d7