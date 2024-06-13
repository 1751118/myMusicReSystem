### 说明

该项目是本科毕业设计的一次个人探索和尝试，使用了#nowplaying-RS音乐数据集，基于音乐内容特征进行聚类得到音乐类别标签后，再使用上下文特征对用户收听事件流进行分类完成基于情绪需要的推荐，使用PyWebIO实现了一个简单的交互界面展示自己的系统。

系统展示视频：https://www.bilibili.com/video/BV1NT421i7Js/?vd_source=f0ace1255f5d873c3a5c27615e80a439

### 开发环境

* python 3.10.12

* Ubuntu 22.04.2 LTS



### 几个关键的文件

EDA.ipynb：可视化数据分析，衍生特征后拆分数据集为音乐内容特征和上下文特征，分别做聚类分析和分类分析。

cluster_analyse.ipynb：聚类分析，得到音乐类别标签。

class_analyse.ipynb：分类分析，得到分类模型。

data_merge.ipynb：将原数据集的track_id按照等频出现的规则替换为Spotify音乐数据集的id（因为这里实在没找到原数据集track_id对应的音频资源）。

Rec_music.ipynb：音乐推荐系统搭建。

model_gen_pytorch.ipynb：使用fer2013数据集训练了一个深度卷积神经网络，用于通过人脸获取用户情绪输入。



### 注意

由于学校在答辩完成后限制了服务器的使用，最终没有完全整理好代码。cluster_analyse和class_analyse需要根据需要运行特定单元格，其他文件可直接Run All。另外由于服务器磁盘限制，最终用于推荐系统推荐的模型也没有更新（保存不了），所以代码也就没改，还有一些小bug，TabTransformer没有训练成功，最后使用随机森林模型进行推荐。