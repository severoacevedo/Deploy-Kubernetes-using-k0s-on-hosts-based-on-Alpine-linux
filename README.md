- 🌱 Build a cluster usin k0s with many hosts as you want
- 
Install Kubernetes using Alpine VMs
1. Deploy alpine VMS
   Uncomment http://dl-cdn.alpinelinux.org/alpine/latest-stable/community on /etc/apk/repositories file
   apk add docker
   addgroup username docker
   rc-update add docker boot
   service docker start

   Copy key from PC to each VM
   ssh-copy-id root@ip
   Difine hostnames for each VM
   /etc/hostname
   Define IP address for each VM
   /etc/network/interfaces


2. Install k0sctl on your client PC
go install github.com/k0sproject/k0sctl@latest

3. Deploy the Cluster on the VM's
./k0sctl init > init.yaml
./k0sctl init --k0s > conf.yaml
./k0sctl apply --config init.yaml
./k0sctl kubeconfig --config init.yaml > k0s.config
./k0sctl kubeconfig --config init.yaml > kub
4. get status and deploy your apps
kubectl get node --kubeconfig kub




https://wiki.alpinelinux.org/wiki/Docker
