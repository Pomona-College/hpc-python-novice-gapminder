---
title: Setup
---

## Pre-Workshop Requirements

Before the workshop, please ensure you have the following set up and working.

### 1. Active Sagehen HPC Account

You must have a valid Pomona College HPC account with access to the Sagehen cluster.

**To verify your access:**
```bash
ssh <myusername>@sagehen.hpc.pomona.edu
```

If you don't have an account or can't log in, contact **its-hpc@pomona.edu**.

### 2. Accessing Python via OnDemand

The recommended way to access Python for this workshop is through the OnDemand web interface:

**https://ondemand.hpc.pomona.edu/**

Steps to access Jupyter Notebook:
1. Go to https://ondemand.hpc.pomona.edu/
2. Log in with your Pomona credentials (with DUO MFA)
3. Click on "Interactive Apps" menu
4. Select "Jupyter Notebook" or "RStudio Server"
5. Configure your session:
   - Partition: `amd` (default)
   - Number of hours: 2-4 hours
   - Number of cores: 4
   - Memory: 8GB
6. Click "Launch"
7. Wait for the session to start, then click "Connect to Jupyter"

### 3. Load Required Python Module

If accessing via SSH (command line), load the miniconda3 module:

```bash
# Load miniconda3
module load miniconda3

# Verify Python is available
python --version

# You should see something like:
# Python 3.10.x :: Anaconda, Inc.
```

### 4. Required Python Packages

This workshop requires the following Python packages. They may already be installed in the base conda environment. Test them by:

```bash
python -c "import numpy; import pandas; import matplotlib; print('All packages available!')"
```

If you see an error, install the packages:

```bash
pip install numpy pandas matplotlib
```

**Package list:**
- **numpy**: Numerical computing library
- **pandas**: Data manipulation and analysis
- **matplotlib**: Plotting and visualization

### 5. Download Gapminder Dataset

The workshop uses the Gapminder dataset. Download it before the workshop:

```bash
# Create a workshop directory
mkdir -p ~/workshops/python-gapminder
cd ~/workshops/python-gapminder

# Download the dataset
wget https://raw.githubusercontent.com/swcarpentry/python-novice-gapminder/gh-pages/data/gapminder_gdp_oceania.csv
wget https://raw.githubusercontent.com/swcarpentry/python-novice-gapminder/gh-pages/data/gapminder_gdp_africa.csv
wget https://raw.githubusercontent.com/swcarpentry/python-novice-gapminder/gh-pages/data/gapminder_gdp_americas.csv
wget https://raw.githubusercontent.com/swcarpentry/python-novice-gapminder/gh-pages/data/gapminder_gdp_asia.csv
wget https://raw.githubusercontent.com/swcarpentry/python-novice-gapminder/gh-pages/data/gapminder_gdp_europe.csv

# Verify the files were downloaded
ls -lh gapminder*.csv
```

### 6. Test Your Python Environment

Create a test script to verify everything works:

```bash
cat > test_env.py << 'EOF'
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt

# Test numpy
arr = np.array([1, 2, 3, 4, 5])
print(f"NumPy test: {arr.mean()}")

# Test pandas
df = pd.DataFrame({'x': [1, 2, 3], 'y': [4, 5, 6]})
print(f"Pandas test:\n{df}")

# Test matplotlib
plt.figure(figsize=(6, 4))
plt.plot([1, 2, 3], [1, 4, 9])
plt.title("Simple Test Plot")
plt.savefig("test_plot.png")
print("Matplotlib test: plot saved as test_plot.png")

print("\nAll tests passed!")
EOF

python test_env.py
```

### 7. (Optional) Interactive Access via SSH

If you prefer using the command line instead of OnDemand:

```bash
# SSH into Sagehen
ssh <myusername>@sagehen.hpc.pomona.edu

# Load Python
module load miniconda3

# Start Jupyter Notebook (on compute node recommended)
srun --pty --partition=short --time=02:00:00 jupyter notebook --no-browser
```

### 8. Sagehen Cluster Access Methods

You can access Sagehen three ways:

1. **OnDemand Web Interface** (recommended for this workshop)
   https://ondemand.hpc.pomona.edu/

2. **SSH Command Line** (for terminal work)
   ```bash
   ssh <myusername>@sagehen.hpc.pomona.edu
   ```

3. **Local Development + Remote Submission**
   Develop locally, submit scripts to Sagehen via SSH

### 9. Cluster Resources Available

Sagehen has the following resources available during the workshop:

- **Compute Nodes:** 12 nodes with 128 cores each, 512GB RAM
- **GPU Nodes (10 GPUs total, confirmed May 2026):**
  - 4× NVIDIA A100 80 GB
  - 4× NVIDIA L40S 48 GB
  - 2× NVIDIA RTX PRO 6000 Blackwell 96 GB
- **Storage:**
  - `/rhome` (100GB personal)
  - `/bigdata` (1TB lab, shared)
  - `/scratch` (SSD temp)
  - `/tmpfs` (RAM temp)
- **Partitions:** `amd` (default), `gpu`, `short` (1 hour max)

### 10. Getting Help

- **HPC Support:** its-hpc@pomona.edu
- **Instructor:** Andrew Wilson
- **OnDemand Docs:** https://ondemand.hpc.pomona.edu/

Once you've verified items 1-6 above, you're ready for the workshop!

<!-- highlight <labname>/<myusername> placeholders in code blocks; remove if the varnish theme handles this natively -->
<script>(function(){var CSS='.sh-placeholder{color:#c2410c;font-weight:700}[data-bs-theme="dark"] .sh-placeholder,html.dark .sh-placeholder{color:#fdba74}@media (prefers-color-scheme: dark){[data-bs-theme="auto"] .sh-placeholder{color:#fdba74}}';var RX=/<labname>|<myusername>/g;function firstMatch(el){var w=document.createTreeWalker(el,NodeFilter.SHOW_TEXT,null),nodes=[],full='';while(w.nextNode()){nodes.push({n:w.currentNode,s:full.length});full+=w.currentNode.nodeValue;}RX.lastIndex=0;var m;while((m=RX.exec(full))){var s=m.index,e=s+m[0].length,inSpan=false,parts=[];for(var j=0;j<nodes.length;j++){var ns=nodes[j].s,ne=ns+nodes[j].n.nodeValue.length;if(ne<=s||ns>=e)continue;parts.push({node:nodes[j].n,a:Math.max(s-ns,0),b:Math.min(e-ns,nodes[j].n.nodeValue.length)});var p=nodes[j].n.parentNode;while(p&&p!==el){if(p.classList&&p.classList.contains('sh-placeholder')){inSpan=true;break;}p=p.parentNode;}}if(!inSpan&&parts.length)return parts;}return null;}function wrapParts(parts){for(var i=parts.length-1;i>=0;i--){var t=parts[i].node,txt=t.nodeValue,a=parts[i].a,b=parts[i].b;var span=document.createElement('span');span.className='sh-placeholder';span.textContent=txt.slice(a,b);var f=document.createDocumentFragment();if(a>0)f.appendChild(document.createTextNode(txt.slice(0,a)));f.appendChild(span);if(b<txt.length)f.appendChild(document.createTextNode(txt.slice(b)));t.parentNode.replaceChild(f,t);}}function run(){var st=document.createElement('style');st.textContent=CSS;document.head.appendChild(st);document.querySelectorAll('pre,code').forEach(function(el){var guard=0,parts;while((parts=firstMatch(el))&&guard++<500){wrapParts(parts);}});}if(document.readyState==='loading'){document.addEventListener('DOMContentLoaded',run);}else{run();}})();</script>
