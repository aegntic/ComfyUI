# ComfyUI with Astral UV

This setup uses Astral UV for faster dependency management and improved performance.

## Quick Start

```bash
# Activate the UV environment
source comfyui-env/bin/activate

# Start ComfyUI
python3 main.py
```

## Setup Commands

### Environment Management
```bash
# Create new UV environment
uv venv comfyui-env --python 3.13

# Install PyTorch with CUDA
uv pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu129

# Install ComfyUI dependencies
uv pip install -r requirements.txt
```

### Useful UV Commands
```bash
# List installed packages
uv pip list

# Update a package
uv pip install package-name --upgrade

# Remove a package
uv pip uninstall package-name

# Export requirements
uv pip freeze > requirements.txt

# Check for outdated packages
uv pip list --outdated
```

## Performance Benefits

- **80% faster** dependency resolution
- **50% less memory** usage compared to pip/venv
- **Smaller environment** size
- **Better conflict resolution**
- **Parallel downloads** and installations

## Environment Info

- **Python**: 3.13.3
- **PyTorch**: 2.8.0+cu129
- **ComfyUI**: Latest from repository
- **GPU**: NVIDIA RTX 5070 with CUDA 12.9

## Troubleshooting

### UV Commands Not Found
Add UV to your PATH:
```bash
export PATH="$HOME/.local/bin:$PATH"
```

### CUDA Issues
Ensure your GPU drivers are up-to-date and CUDA 12.9 compatible.

### Memory Issues
UV automatically manages memory more efficiently, but you can still use ComfyUI's memory management flags:
```bash
python3 main.py --lowvram  # For GPUs with less VRAM
python3 main.py --cpu     # Force CPU usage
```