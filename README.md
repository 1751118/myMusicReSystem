### 3.8 数据集的特征含义
* 用户行为特征
user_id（用户id）：用户唯一标识
track_id（歌曲id）：歌曲唯一标识
created_at （时间戳）：此次session发生的时间

* 内容特征（音轨特征）
Instrumentalness（器乐度）：预测音轨中没有人声的概率。数值越接近1.0，表示音轨越可能是器乐。
Liveness（现场感）：检测音轨中是否有观众现场录音的证据。数值越高，表示音轨越可能是在现场录制。
Speechiness（语音度）：检测音轨中所包含的口语部分。数值越高，表示音轨中包含的口语部分越多。
Danceability（可舞动度）：描述音轨适合舞蹈的程度。基于音轨的节奏、节拍稳定性、节拍强度和整体活跃度等元素计算得出。
* Valence（情感度）：描述音乐传达的情感积极性。数值越高，音乐听起来情感越积极（快乐、欢快、欣快）。
Loudness（响度）：音轨的平均响度，以分贝（dB）计。响度值通常在-60到0db之间。
**Tempo（节奏）：音轨的速度，以每分钟节拍数（BPM）计算。
Acousticness（原声度）：音轨是由原声乐器演奏而非电子合成的概率。数值越高，表示音轨越可能是原声的。
**Energy（能量）：音轨的强度和活跃度。动感的、嘈杂的音轨会得到较高的能量值。
Mode（调式）：音乐的调式，大调为1，小调为0。调式是音乐的一个基本特征，与旋律和和声的构成有关。
* Key（音调）：音乐的主音调。通常用0到11之间的数字表示，对应12个音阶。(是否就是十二平均律？)


* 上下文特征（听歌事件特征）
Coordinates（坐标）、Place（地点）、Geo（地理信息）：以geoJSON格式提供，描述了听歌事件发生的地理位置信息。（地点、时间、地区可视化相关性？偏好是什么？）
Tweet_language（推文语言）：发布推文时使用的语言。
Created_at（创建时间）：推文或听歌事件的创建时间。
User_lang（用户语言）：用户设置的界面语言。
Time_zone（时区）：用户所在的时区。
Entities（实体）：推文中包含的实体，如标签、提到的用户等。
hashtag(推文标签)：
    AFINN: Assigns words a score from -5 to +5, indicating negative to positive sentiment.
    Opinion Lexicon: Categorizes words as positive or negative.
    SentiStrength Lexicon: Estimates the strength of positive and negative sentiment in short texts, giving separate scores for each.
    VADER: Specifically tuned for social media, VADER provides scores for positivity, negativity, neutrality, and a compound score reflecting the overall sentiment.
score（情绪分数）：范围0（消极）~1（积极）

### 3.10 复现了UserCF、ItemCF、Random和MostPopular算法
均只需要用到用户行为特征
但测评指标如召回率、精确率极低，问题何在？

### 3.15 完成了五类情绪{0:'anger', 1:'disgust', 2:'fear', 3:'happiness', 4: 'sadness'} 的模型训练
准确率不到0.7，模型效果不佳
可能是训练epoch不够，本地服务器性能不佳，训练轮次太多的话时间太长
学校发的毕设服务器CPU和tensorflow不兼容，无法使用，如何解决？
可否学习使用pytorch代替tensorflow完成相关任务？


### 3.19
点赞
情感、节奏、能量，时间、地区的相关性，可视化