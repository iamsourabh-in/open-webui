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