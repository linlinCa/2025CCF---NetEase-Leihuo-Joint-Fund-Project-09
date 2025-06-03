# 2025CCF-网易雷火联合基金课题——基于MonoFaceCompute的表情重定向系统
日期：2025年5月26日

【项目背景】
本系统基于MonoFaceCompute开源框架(https://github.com/KelianB/MonoFaceCompute)完成，选取低维模型为FLAME（general）。

【核心配置】
1. 运行环境：
   - CUDA 12.1
   - PyTorch 2.1.0
   - Blender 4.4（含自定义FLAME插件）
   - 是在Ubuntu22.04，NVIDIA A40的GPU上完成测试

2. 模型架构：
   - 基础模型：FLAME低维参数化人脸模型
   - 控制方式：通过改造的Blender插件实现可视化编辑

【使用说明】
1. 环境部署：
   运行命令：conda env create -f environment.yaml

2. 快速启动：
   - 将输入视频新建文件夹，放入/datasets
   - 修改、config文件夹中的config.yaml的文件路径和参数
   - 回到项目目录下，运行python process.py -dataset config/config.yaml

3. 表情编辑：
   - 安装blender插件
   - 将输出的flame.json文件通过插件【auto animate from JSON】导入，自动将flame参数转换为blender动画
   - 用户可以通过GUI界面更改某一帧的表情（Exp1,Exp2...）和姿势pose，点击【SaveFrame】保存修改，然后点击【smooth shape keys】可以让修改后的动画更平滑
   - 编辑完成后可以直接导出fbx

4. 测试数据
包含30组完整测试案例：
- 输出结果：/videos
- 重定向后的人脸动画可在百度网盘下载：https://pan.baidu.com/s/1bDwRHMejO7RJCX8C113ooA?pwd=xk4h 提取码: xk4h 

* 声明
本系统为比赛用途开发，核心算法基于MonoFaceCompute实现，特此说明。
