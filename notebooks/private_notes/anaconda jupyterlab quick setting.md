

```bash

### 激活 env
conda activate scanpy
### 检查 juypter
which jupyter
# /opt/anaconda3/envs/scanpy/bin/jupyter

### 生成config文件
jupyter lab --generate-config
# Writing default config to: /Users/**/.jupyter/jupyter_lab_config.py

### 修改：实际这里是根据另一台已经配置的机器上的配置修改的
vi /Users/**/.jupyter/jupyter_lab_config.py
# 只用修改一处：c.ServerApp.port = 8890
```