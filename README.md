# 🧬 ColabFold Local Installation Guide (macOS / Unix)

This guide walks you through installing and running [ColabFold](https://github.com/sokrypton/ColabFold) locally, including setting up the environment, dependencies, and a one-click launch script.

---

## 📦 Requirements

- macOS or Unix-like OS
- Anaconda or Miniconda
- Python 3.10
- Basic terminal usage

---

## 🧪 Step-by-Step Setup

### 🔹 1. Open your terminal and initialize Conda:

```bash
source ~/opt/anaconda3/etc/profile.d/conda.sh
```

### 🔹 2. Create a new Conda environment for ColabFold:

```bash
conda create -n colabfold python=3.10 -y
conda activate colabfold
```

### 🔹 3. Install ColabFold from GitHub:

```bash
pip install --upgrade pip
pip install git+https://github.com/sokrypton/ColabFold.git
```

### 🔹 4. Install MMseqs2 (used for MSA generation):

```bash
pip install mmseqs2
```

### 🔹 5. Install JAX for macOS CPU:

```bash
pip install jax jaxlib
```

### 🔹 6. Install Jupyter Lab (for interactive work):

```bash
conda install -c conda-forge jupyterlab
```

---

## 📁 Project Folder Setup

Create your working folders:

```bash
mkdir -p ~/ColabFoldProjects/input
mkdir -p ~/ColabFoldProjects/output
cd ~/ColabFoldProjects
```

---

## 🚀 One-Click Launch Script

Create a script to launch JupyterLab with ColabFold:

```bash
nano run_colabfold.sh
```

Paste the following content:

```bash
#!/bin/bash
source ~/opt/anaconda3/etc/profile.d/conda.sh
conda activate colabfold
cd ~/ColabFoldProjects
~/opt/anaconda3/envs/colabfold/bin/jupyter-lab
```

Then make it executable:

```bash
chmod +x run_colabfold.sh
```

---

## 🔄 Next Time You Run It

Just launch your workspace with:

```bash
cd ~/ColabFoldProjects
./run_colabfold.sh
```

This will activate the environment and open JupyterLab in your browser.

---

