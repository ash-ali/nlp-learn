## one-hot representation shortcoming


### 1、不能表示语义相似度

例如：我们、爬山、运动、昨天
我们(0,1,0,0,0,0)
爬山(0,0,1,0,0,0)
运动(1,0,0,0,0,0)
昨天(0,0,0,1,0,0)

#### 利用欧式距离
d(我们,爬山) = 根号2
d(我们,运动) = 根号2
d(我们,昨天) = 根号2
...

>得出欧式距离（结合one-hot）表达，无法判断两个单词语义相似度


#### 利用余弦相似度
cos(我们,爬山) = 0
cos(我们,运动) = 0
cos(我们,昨天) = 0
...

>得出余弦相似度（结合one-hot）表达，无法判断两个单词语义相似度




### 2、Sparsity（稀疏性问题）
例如基于one-hot representation
我们 今天 很开心 = ( .... ) = 向量大小 = |词典|

但是，常见的中文词典大小在 10^5~10^6之间，这就会导致一个问题就是：该向量绝大多数都是0，少部分1，这就是稀疏性的问题。

解决办法就是利用分布式的表示方法即可！