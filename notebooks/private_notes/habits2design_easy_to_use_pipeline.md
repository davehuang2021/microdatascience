## 基本操作
- 使用 conda env
	- conda env 使用jupyterlab，通过配置~/.jupyter/jupyter_lab_config.py文件来修改端口，避免和vpn软件产生冲突[[anaconda jupyterlab quick setting]]
	- 一个快速的anaconda env操作见这里：[[quick mac os anaconda env]]
	- 
- 尽可能简化原则
- jupyter notebook and html来保存版本快照
	- [ ] 以下代码需要测试 
```bash
### 以下代码需要测试
jupyter nbconvert --output-dir archive --to html --no-input report.ipynb  # 纯净输出
git tag v1.0.0 $(git hash-object report.ipynb)     # 精确版本标记
```

## 基于模版构建pipeline文件，规则内置其中

提醒用户阅读后再开始撰写代码

## 基本的命名规则
- 变量名的命名规则：下滑线命名
- pipeline运行顺序按照0，1，2，...，也便于对文件夹中的文件排序


## 清晰的包版本声明与高可重复的运行环境
- 封装进特定的conda env中
- 每个文件结尾打印软件包的版本，并声称存档文件

```python
# scanpy
sc.logging.print_versions()
```

```R
### R语言的代码实现

```


## 检查可重复性的快速方法

通常使用实例文件的md5值来快速检查，也就是说存档时，保存测试文件结果的md5；
后续再重复/测试时候，不用检查结果的数据，直接看md5是否一致即可，迅速可靠。

这种方法更简单暴力，也无需对数据有深入的理解，适合让工程师或者实习生来做。

## jupyter nb的精简文件（ipynb精简）做到单个文件可从头到尾执行

即中间保存的参数都经过了调试，从头完整运行即可获得可用的结果。这要求：
- 中间无需要定制或调试的参数
- 中间没有需要手动编辑的输入文件
- 输入输出文件无需手动改动，不会导致报错

## jupyter nb的完整文件（ipynb-full）包含note、技术细节解释和实例
- 完整文件（ipynb-full），其主干功能与ipynb精简保持一致
- 尽量写详细的代码解释，便于复查或者解释
- 可关联更多case，通过链接到更多文件

## jupyter nb按照功能模块编写
> 比如scanpy的切割/模块化模式[见这个教程的切块模式]()
> 比如数据下载与标准化 >> 数据初步分析与打包 >> 特定参数高级分析 >> 故事线文件1/2/3/...
