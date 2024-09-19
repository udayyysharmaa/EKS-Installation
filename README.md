# EKS-Installation

## Need to Install First Unzip 

   ```bash
sudo apt-get install unzip -y
   ```
## Need to Install AWS CLI
   ```bash
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install
   ```


## Need to Config AWS
   ```bash
aws configure
   ```


## Need to Install eksctl
   ```bash
curl --silent --location "https://github.com/weaveworks/eksctl/releases/latest/download/eksctl_$(uname -s)_amd64.tar.gz" | tar xz -C /tmp
sudo mv /tmp/eksctl /usr/local/bin
eksctl version
   ```


## Install kubectl binary with curl on Linux
```bash
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
```
Note:
To download a specific version, replace the $(curl -L -s https://dl.k8s.io/release/stable.txt) portion of the command with the specific version.


### Download the kubectl checksum file:

```bash
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl.sha256"
```

### Validate the kubectl binary against the checksum file:
```bash
echo "$(cat kubectl.sha256)  kubectl" | sha256sum --check
```
If valid, the output is:

kubectl: OK

## Install kubectl

```bash
sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
```

### If you do not have root access on the target system, you can still install kubectl to the ~/.local/bin directory:

```bash
chmod +x kubectl
mkdir -p ~/.local/bin
mv ./kubectl ~/.local/bin/kubectl
```
