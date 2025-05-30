
生成一个快速的 anaconda env，在一台未安装的mac下配置开发环境。

这个过程也适用于从一个已成熟的环境下，迁移到一个新的未配置过的环境。

```bash
### 在原主机
conda activate scanpy
conda env export > scanpy.yaml

### 转移到新主机

conda env create -f scanpy.yaml
```