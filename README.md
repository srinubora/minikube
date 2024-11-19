# minikube
creating ec2 and connecting the ec2 instance
![Screenshot 2024-11-18 230610](https://github.com/user-attachments/assets/48722769-0d11-4658-b91a-25464ba20bf9)
sudo su -

apt update -y

sudo curl -fsSL https://get.docker.com -o get-docker.sh

ll	
![Screenshot 2024-11-18 230900](https://github.com/user-attachments/assets/1472abc5-2528-4c80-bac6-d452a60141bc)

chmod +x get-docker.sh

./get-docker.sh

docker version

systemctl status docker

sudo curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64 

ll

sudo mv minikube-linux-amd64 /usr/local/bin/minikube

sudo chmod +x /usr/local/bin/minikube

sudo minikube version

sudo apt install curl wget apt-transport-https -y

sudo curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"

sudo kubectl version --client

sudo curl -LO "https://dl.k8s.io/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl.sha256"

sudo echo "$(cat kubectl.sha256) kubectl" | sha256sum --check

sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl

sudo kubectl version --client

sudo kubectl version --client --output=yaml

sudo minikube start --driver=docker --force

creation of pod

kubectl run pod1 --image=nginx

kubectl get pods

