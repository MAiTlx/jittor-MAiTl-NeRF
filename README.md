<!-- # JNeRF -->
<div align="center">

</div>

## 简介
基于JNeRF的降噪优化


## 环境安装
JNeRF environment requirements:

* System: **Linux**(e.g. Ubuntu/CentOS/Arch), **macOS**, or **Windows Subsystem of Linux (WSL)**
* Python version >= 3.7
* CPU compiler (require at least one of the following)
    * g++ (>=5.4.0)
    * clang (>=8.0)
* GPU compiler (optional)
    * nvcc (>=10.0 for g++ or >=10.2 for clang)
* GPU library: cudnn-dev (recommend tar file installation, [reference link](https://docs.nvidia.com/deeplearning/cudnn/install-guide/index.html#installlinux-tar))
* GPU supporting:
  * sm arch >= sm_61 (GTX 10x0 / TITAN Xp and above)
  * to use fp16: sm arch >= sm_70 (TITAN V / V100 and above). JNeRF will automatically use original fp32 if the requirements are not meet.
  * to use FullyFusedMLP: sm arch >= sm_75 (RTX 20x0 and above). JNeRF will automatically use original MLPs if the requirements are not meet.

**Step 1: Install the requirements**
```shell
sudo apt-get install tcl-dev tk-dev python3-tk
git clone https://github.com/Jittor/JNeRF
cd JNeRF
python -m pip install -r requirements.txt
```
If you have any installation problems for Jittor, please refer to [Jittor](https://github.com/Jittor/jittor)

**Step 2: Install JNeRF**

JNeRF is a benchmark toolkit and can be updated frequently, so installing in editable mode is recommended.
Thus any modifications made to JNeRF will take effect without reinstallation.

```shell
cd python
python -m pip install -e .
```

After installation, you can ```import jnerf``` in python interpreter to check if it is successful or not.




### 数据集
数据集下载请参考Jrender仓库的download_competition_data.sh文件，或直接从链接下载（https://cloud.tsinghua.edu.cn/f/63016014a4ad410997f5/?dl=1



### 训练

```shell
python tools/run_net.py --config-file ./projects/ngp/configs/ngp_comp.py
```

### 通过模型参数生成渲染图片

执行 test.py

## 引用


```
@article{hu2020jittor,
  title={Jittor: a novel deep learning framework with meta-operators and unified graph execution},
  author={Hu, Shi-Min and Liang, Dun and Yang, Guo-Ye and Yang, Guo-Wei and Zhou, Wen-Yang},
  journal={Science China Information Sciences},
  volume={63},
  number={222103},
  pages={1--21},
  year={2020}
}
@article{mueller2022instant,
    author = {Thomas M\"uller and Alex Evans and Christoph Schied and Alexander Keller},
    title = {Instant Neural Graphics Primitives with a Multiresolution Hash Encoding},
    journal = {ACM Trans. Graph.},
    issue_date = {July 2022},
    volume = {41},
    number = {4},
    month = jul,
    year = {2022},
    pages = {102:1--102:15},
    articleno = {102},
    numpages = {15},
    url = {https://doi.org/10.1145/3528223.3530127},
    doi = {10.1145/3528223.3530127},
    publisher = {ACM},
    address = {New York, NY, USA},
}
@inproceedings{mildenhall2020nerf,
  title={NeRF: Representing Scenes as Neural Radiance Fields for View Synthesis},
  author={Ben Mildenhall and Pratul P. Srinivasan and Matthew Tancik and Jonathan T. Barron and Ravi Ramamoorthi and Ren Ng},
  year={2020},
  booktitle={ECCV},
}
```
