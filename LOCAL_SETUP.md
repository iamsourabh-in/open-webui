```sh
# Setup Ollama

# Pull the required model
ollama pull llama3

# Clone the repository
git clone https://github.com/open-webui/open-webui.git

# Setup Conda
mkdir -p ~/miniconda3
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh -O ~/miniconda3/miniconda.sh
bash ~/miniconda3/miniconda.sh -b -u -p ~/miniconda3
rm ~/miniconda3/miniconda.sh

# Activate Conda base environment
source ~/miniconda3/bin/activate

# Create an environment to manage Python version
conda create --name openwebui python=3.11 -y
conda activate openwebui

# Download and install nvm:
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.1/install.sh | bash

# Download and install Node.js:
nvm install 22

# Verify the Node.js version:
node -v # Should print "v22.13.1".
nvm current # Should print "v22.13.1".

# Verify npm version:
npm -v # Should print "10.9.2".


# Install frontend dependencies at the root folder of repo
cd open-webui-main
npm install
npm run build

# Install Dependencies
cd ./backend
pip install -r requirements.txt -U

# Start Server
cd ./backend
bash start.sh

```