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
![Screenshot 2024-11-18 231341](https://github.com/user-attachments/assets/0010ecf1-7ff5-4423-a54f-258dcefdaf50)

sudo curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64 

ll
![Screenshot 2024-11-18 232555](https://github.com/user-attachments/assets/84296b20-a230-45a8-9c55-7c0e4da2d89f)

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
![Screenshot 2024-11-19 003114](https://github.com/user-attachments/assets/b4244b07-e040-4f6b-a94e-d56b016f2ba0)

sudo minikube start --driver=docker --force

minikube status

kubectl get nodes
![Screenshot 2024-11-19 004053](https://github.com/user-attachments/assets/495bedc3-f380-47b1-a810-b79ae5d21502)

creation of pod

kubectl run pod1 --image=nginx

kubectl get pods![Screenshot 2024-11-19 005211](https://github.com/user-attachments/assets/c649fee1-91da-478b-b776-caf1b9634a9d)

vi srinu.yml

apiVersion: v1

kind: Pod

metadata:

  name: nginx
  
spec:

  containers:
  
  - name: nginx
  - 
    image: nginx:1.14.2
    
    ports:
    
    - containerPort: 80
:wq!
![Screenshot 2024-11-19 014257](https://github.com/user-attachments/assets/ef11792e-7181-423b-b40f-e6c9c31cd539)
kubectl api-resources

