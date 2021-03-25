# 流体模拟

## 项目简介

&#8194;&#8194;本项目为不可压缩流体仿真，可通过鼠标点击实现干扰。为保障顺利运行需安装TaiChi（[详情](https://github.com/taichi-dev/taichi))。

&#8194;&#8194;该仿真工作流程大体可分为Advection与Projection两部分，其中Advection部分可采用Semi-Lagrangian advection与BFECC两种方法中任意一种（均已实现），Projection部分通过jacobi迭代完成对速度场的更新。

## 理论推导
由不可压缩流体的N-S方程有：

![1](https://dm2305files.storage.live.com/y4m8gmMYmJW97WQDGFWs-8bUU4uo4mC2b44ex7LHnEcIIa7MdcmEa2dAorZdSvlreftboz3QFsB0mqp43CmMARRIlmyKZR341Nc_SPrIa2mm7-yR4gCKFaLV0u9xnggnh6NMI6DIjgN4PAHGnbk4QUUbimA9tMYz2pewmwYp_2WYbvoC3eIDAF2rfBxzoO9HNZ3?width=478&height=96&cropmode=none)

舍弃粘滞项，并且速度场无散：

![2](https://dm2305files.storage.live.com/y4mEdjgGeaqr_3Iv5dsjOL7g8Hx2ESkRVNdqDfxWUvmHD0PUje33iZN_3UApdbGLONxMMGzvSfwjIEbSPR-PTQw4xSHx4MUP1k86YCynWhTZXA-PajdPllCKI2QsfJ6pSwm2YETHVCSV7gw-kA9lbm6D3TUKNfzSc8s6avqCbRasc-5UsBbmKIxlgOm7HBWbwpv?width=438&height=90&cropmode=none)


对其使用Operator splitting有

![3](https://dm2305files.storage.live.com/y4mnTiSHWrjogYV8OBHxVHOWGfY1r5h0RDM8QUeoYlDgVZ8Nk6x7ss4hzAmahLiBZ4Fv6D8aSzCd08bVElQ-Y_On-lpHVCflW9SPUEwWa2PkXzZC35R917aQ6jTOfOBsNq99WcqL8j5LFEgRD7wrFpozLBNoQbkMStZkgpFqCBrQptF5wxaSmLSaugUzVvjOpsV?width=480&height=356&cropmode=none)

展开得到：

![6](https://dm2305files.storage.live.com/y4m7mT50m45LG0K8ltBLQxtxa-9Ut2uOy4WLqyCrSAYHbjYI7qpnRYMn2_Pj3tSCCEMnyo3lRnroHtlZ2k7lNazpRc2Iys5MeqgYtmsXh__6--GGgOdGEO3Jh-aiDAAkXHplS5N7ZUVo2tg-Gcd-xE4a-oR2BZ-1fEVuctTJb6cMGElfMyz0kOX1-uT98p1QlpY?width=667&height=542&cropmode=none)

![7](https://dm2305files.storage.live.com/y4mkz8caLwyXuIz2ik0TG2YlyaN8hHal8wZRZ8JkYxryw7AcNHHaU0xH8D1AjTGGIu0y1_amjTKDC9y3eva3pBIPzlULKR31GBPlvJdCBYl-pYzLRh-BeEIZ6A9ml3V3xNeMlsUn0QrVEmfJ6KfYx53OiwtXEQn6rTWWu3SiGSnfS4TEZwFqE_gpu_Lhah8msOy?width=1058&height=315&cropmode=none)

## 效果
![eg](https://dm2305files.storage.live.com/y4mkpCPA32QKBUxDh_jJk5fszGo6bAKMxK26SmYssXwXAl27AUlE_F7vFYNOa9pwx1RmxQJzujYTWTSA7tghTKavLxcwWTcPwTEUmAi8IhbwzJ63dVzS9qiwUgyFVceNlYmgmU3dC5UCAbDx4npzlCNr8KbB8alrPrWIkiil-Fzdq_crM7VLbYEBsKa4Xk7tfV_?width=513&height=519&cropmode=none)
