# langchain_stuff

Just playing around with langchain.

Please follow the following:

You will need an OpenAI Api Key for certain modules. You can obtain one from https://platform.openai.com/api-keys.

You will need a Weaviate Api Key for certain modules. You can obtain one from your cluster details page after creating a
cluster at https://console.weaviate.cloud/create-cluster. You will also obtain a cluster-specific REST Api Url.

You will need a Huggingface Api Key for certain modules. You can obtain one from https://huggingface.co/settings/tokens.

Create a copy of `.env.template` as instructed in the file.

I'm not entirely sure of this but it seems from my research that certain packages and drivers need to be installed for
the pip package `faiss-gpu`. In which case, you need to follow the instructions at https://developer.nvidia.com/cuda-downloads
for your operating system. I followed these steps for Ubuntu 22.04 and amdx64.

```commandline
wget https://developer.download.nvidia.com/compute/cuda/repos/ubuntu2204/x86_64/cuda-ubuntu2204.pin
sudo mv cuda-ubuntu2204.pin /etc/apt/preferences.d/cuda-repository-pin-600
wget https://developer.download.nvidia.com/compute/cuda/12.6.0/local_installers/cuda-repo-ubuntu2204-12-6-local_12.6.0-560.28.03-1_amd64.deb
sudo dpkg -i cuda-repo-ubuntu2204-12-6-local_12.6.0-560.28.03-1_amd64.deb
sudo cp /var/cuda-repo-ubuntu2204-12-6-local/cuda-3DBA81E7-keyring.gpg /usr/share/keyrings/
sudo apt-get -y install cuda-toolkit-12-6
sudo apt-get install -y nvidia-open
```

Then run:

```commandline
python3 -m venv venv .
source venv/bin/activate
pip install -r requirements.txt
jupyter lab --browser "/mnt/c/Program\ Files/Google/Chrome/Application/chrome.exe"
```
