# 总体思路

形式化之后，我们可以进行迁移学习的研究。迁移学习的总体思路可以概括为

> 开发算法来最大限度地利用有标注的领域的知识，来辅助目标领域的知识获取和学习。

迁移学习的核心是，找到源领域和目标领域之间的**相似性**，并加以合理利用。这种相似性非常普遍。比如，不同人的身体构造是相似的；自行车和摩托车的骑行方式是相似的；国际象棋和中国象棋是相似的；羽毛球和网球的打球方式是相似的。这种相似性也可以理解为**不变量**。以不变应万变，才能立于不败之地。

举一个杨强教授经常举的例子来说明：我们都知道在中国大陆开车时，驾驶员坐在左边，靠马路右侧行驶。这是基本的规则。然而，如果在英国、香港等地区开车，驾驶员是坐在右边，需要靠马路左侧行驶。那么，如果我们从中国大陆到了香港，应该如何快速地适应他们的开车方式呢？诀窍就是找到这里的不变量：**不论在哪个地区，驾驶员都是紧靠马路中间。**这就是我们这个开车问题中的不变量。

找到相似性(不变量)，是进行迁移学习的核心。

有了这种相似性后，下一步工作就是，**如何度量和利用这种相似性**。度量工作的目标有两点：一是很好地度量两个领域的相似性，不仅定性地告诉我们它们是否相似，更**定量**地给出相似程度。二是以度量为准则，通过我们所要采用的学习手段，增大两个领域之间的相似性，从而完成迁移学习。

一句话总结：

> 相似性是核心，度量准则是重要手段。