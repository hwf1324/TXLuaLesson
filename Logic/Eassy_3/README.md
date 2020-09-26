# 论证

就像会说话的人不一定会陈述。会陈述的人也不一定会论证。在学会如何陈述之后，我们接下来才能讨论论证。

论证是从已知推测未知，并且试图从真实导出真实的过程。

> **补充：**传统的逻辑学中把论证分为演绎论证和归纳论证两个部分。演绎论证得出必然的推断，而归纳论证得出或然的推断。但是，其实可以完全取消掉归纳论证，而通过演绎论证加概率理论来取代归纳论证的地位。例如“他明天可能回来”，“他明天回来”这个事件是或然的，但是他明天回来的可能性是必然的。
>
> 后续我们只介绍演绎论证，而不介绍归纳论证。

古希腊的亚里士多德曾经建立过一套关于论证的体系。但是这套体系中概念繁多，需要记忆的内容也特别多，我认为太过于繁琐。因此我们跳过这个体系，直接从近似于符号逻辑的逻辑讲起。为了方便理解，一般教材会把这个系统中的一部分先拿出来讲解，这个被拿出来单独讲解的部分一般被称为“命题逻辑”。等命题逻辑介绍完之后，再介绍整个完整的体系。这个完整的体系则称为“谓词逻辑”。

而不论命题逻辑还是谓词逻辑，都是由两组规则构成——命题生成规则和演绎论证规则。所以其实我们一共要介绍四个部分——命题逻辑中的生成规则，命题逻辑中的演绎规则，谓词逻辑中的生成规则，谓词逻辑中的演绎规则。（其中命题逻辑实际上是谓词逻辑的一部分。）

这一次我们先不直接介绍命题逻辑或者谓词逻辑。为了防止你被突如其来的一堆术语冲昏头脑。我们先来探讨一下，这些“逻辑”，这些“规则”和论证究竟有什么关系。

## 命题是论证的基础

仅仅会作好的陈述，对于论证来说还是不够的。虽然论证都是陈述，但是陈述必须提炼为命题才能用于论证。具体来说，一个命题应当满足怎样的规则是生成规则里的内容。我们以后再介绍。现在我可以先举一些例子。例如“苏格拉底是人”这是一个命题。“所有人都会死”这也是一个命题。

有了命题才能论证。论证的前提是命题，结论也是命题。整个论证过程就是一系列命题的序列。那么我们究竟把这一堆命题排列起来要干什么呢？其实我们默认论证前提都是为“真”的命题，而论证过程是把这些命题根据一些规则变换为另一些命题。我们相信根据这些规则变换出来的命题也是“真”的命题。因此只要使用正确的前提，经过正确的步骤，总能得到正确的结论。在论证之前，我们也可以写出作为结论的命题。但是只有经过论证之后，作为结论的命题的“真”才能得以保证。

## 两种规则确定了什么

命题生成规则确定了从单词组成命题的方式。而演绎规则确定了从命题组成论证（论证是命题的序列）的方式。

对于命题来说，我们可以按照命题生成规则检验一个给定的句子是不是命题，也可以基于已有的词汇像造句那样造命题。但是命题本身的真假是不能从命题生成规则中得知的。一个命题为真要么是由演绎以外的方法确定的（例如这个命题是公理由共识或者实践保证，或者这个命题是定义由人规定），要么就是作为一个有效论证的结论由论证前提和论证过程保证它的正确性。

对于论证过程来说。我们也可以用演绎规则来检验论证过程是否合乎演绎规范。注意，有效的论证一定符合演绎规则，但是符合演绎规则的论证不一定就是有效的。一个论证要符合演绎规则，同时所使用的所有前提都为“真”才能保证论证有效。

还有一个值得探讨的话题，如果我们已知一些为真的命题，和一个需要论证的命题。有没有什么通用的方法正帮我们找到合适的论证过程呢？直觉上看，我们按照命题生成规则和演绎规则，遍历所有可能情况，总能找到想要的论证过程（哪怕费时费力）。但是，实际上并不是这么简单的（数理逻辑中会详细讨论这是为什么）。因此我们可以把检验论证是否合理的过程完全机械化处理，但是无法完全机械地创造新知识。
