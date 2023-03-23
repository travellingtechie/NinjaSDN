To Run scripts on Ubuntu Minimal:

For Ansible
```bash
sudo apt install python3-dev python3-venv inetutils-ping python3-wheel gcc libpq-dev vim nano git python3-pip
git clone https://github.com/travellingtechie/NinjaSDN
cd NinjaSDN
python3 -m venv venv --prompt="Ansible"
source venv/bin/activate
pip install --upgrade pip wheel
pip install --upgrade git+https://github.com/vmware/vsphere-automation-sdk-python.git
pip install -r requirements.txt
ansible-galaxy collection install git+https://github.com/vmware/ansible-for-nsxt
ansible-galaxy collection install community.vmware
```

For Terraform (from https://developer.hashicorp.com/terraform/downloads)
```bash
wget -O- https://apt.releases.hashicorp.com/gpg | gpg --dearmor | sudo tee /usr/share/keyrings/hashicorp-archive-keyring.gpg
echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] https://apt.releases.hashicorp.com $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/hashicorp.list
sudo apt update && sudo apt install terraform
```
