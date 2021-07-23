# AutoSpace
This repo contains the code for the paper Rethinking Bottleneck Structure for Efficient Mobile Network Design ([ICCV 2021](https://arxiv.org/abs/2103.11833))

Current neural architecture search (NAS) algorithms still require expert knowledge and effort to design a search space for network construction. In this paper, we consider automating the search space design to minimize human interference, which however faces two challenges: the explosive complexity of the exploration space and the expensive computation cost to evaluate the quality of different search spaces. To solve them, we propose a novel differentiable evolutionary framework named AutoSpace, which evolves the search space to an optimal one with following novel techniques: a differentiable fitness scoring function to efficiently evaluate the performance of cells and a reference architecture to speedup the evolution procedure and avoid falling into sub-optimal solutions. The framework is generic and compatible with additional computational constraints, making it feasible to learn specialized search spaces that fit different computational budgets. With the learned search space, the performance of recent NAS algorithms can be improved significantly compared with using previously manually designed spaces. Remarkably, the models generated from the new search space achieve 77.8% top-1 accuracy on ImageNet under the mobile setting (MAdds < 500M), out-performing previous SOTA EfficientNet-B0 by 0.7%. All codes will be made public.

```
@article{zhou2021autospace,
  title={AutoSpace: Neural Architecture Search with Less Human Interference},
  author={Zhou, Daquan and Jin, Xiaojie and Lian, Xiaochen and Yang, Linjie and Xue, Yujing and Hou, Qibin and Feng, Jiashi},
  journal={arXiv preprint arXiv:2103.11833},
  year={2021}
}
```


<p align="center">
<img src="https://github.com/zhoudaquan/AutoSpace/blob/master/figures/pipeline.png" | width=500>
</p>

## Performance
Model performance at different computation budget with model searched with AutoSpace using ProxylessNAS:

<p align="center">
  
Model|Param.(M)|Madd(M)|Top-1 Acc.(%)
---|---|---|---
AutoSpace-PNAS|3.3|175|71.1
AutoSpace-PNAS|4.3|340|75.3
AutoSpace-PNAS|4.7|430|75.7
AutoSpace-PNAS|6.4|570|77.0
AutoSpace-PNAS - 1.4x|7.2|650|77.2

</p>
