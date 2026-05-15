# Conda and environments

## Miniconda

```bash
brew install --cask miniconda
conda init zsh
source ~/.zshrc
```
### uv
```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

### Create conda environment

```bash
conda create -n ml python=3.11 -y
conda activate ml
```

### Now use uv for all Python packages — much faster
```bash
uv pip install torch torchvision torchaudio
uv pip install fastai polars wandb
uv pip install jupyter notebook matplotlib scikit-learn
```

### Export Python packages (uv/pip managed)
```bash
uv pip freeze > requirements.txt
```
### Export full conda env (includes Python version + conda packages)
```bash
conda env export > environment.yml
```
### Export only what you explicitly installed (cleaner)
```bash
conda env export --from-history > environment_clean.yml
```

### Recreate conda env
```bash
conda env create -f environment.yml
conda activate ml
```
### Reinstall Python packages fast with uv
```bash
uv pip install -r requirements.txt
```

## Daily Workflow

```bash
# Start working
conda activate ml

# Install new package — always use uv, not pip or conda install
uv pip install some-package

# Check what's installed
uv pip list

# Update a package
uv pip install -U some-package

# Remove a package
uv pip uninstall some-package

# Deactivate when done
conda deactivate
```

### When to Use conda install vs uv pip install
```bash
# Use conda install ONLY for non-Python system dependencies
conda install -c conda-forge gdal          # geospatial lib
conda install -c conda-forge opencv        # computer vision C++ bindings

# Use uv pip install for everything Python
uv pip install torch fastai polars wandb
```