# Donkey Family Lab

Shared repo for local sim driving + remote GPU training.

## Quick links
- Local (kids): install DonkeyCar, run simulator, `python manage.py drive --js`
- Remote (GPU): `docker compose -f docker-compose.gpu.yml run --rm train bash` → train
- Sync data up/down: see `scripts/` (rsync for mac/linux, scp for Windows PowerShell)

## Structure
```
.devcontainer/      # Optional devcontainer for Codespaces/VS Code (CPU-only)
docker/             # GPU Dockerfile for remote VM
scripts/            # sync scripts (up/down) mac/linux and Windows
projects/           # car projects live here (on VM)
data/               # tubs live here on VM
```

## First steps on the GPU VM
```bash
docker compose -f docker-compose.gpu.yml build
docker compose -f docker-compose.gpu.yml run --rm train bash -lc "donkey createcar --path /workspace/projects/mycar"
```
