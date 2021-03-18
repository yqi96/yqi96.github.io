---
title: Softmax和Cross-entropy的数值稳定问题
categories: Note
tags:
  - loss
abbrlink: 6deaeeb1
date: 2020-10-21 00:00:00
---
<script type="text/javascript" src="http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=default"></script>
<script type="text/x-mathjax-config">
MathJax.Hub.Config({
  TeX: { equationNumbers: { autoNumber: "AMS" } },
  "HTML-CSS": { linebreaks: { automatic: true } },
         SVG: { linebreaks: { automatic: true } }
});
</script>
<!-- more -->

### 理论

Softmax公式:
$$
\begin{equation}
p_i=\frac{e^{l_i}}{\sum_\limits{j}e^{l_j}}
\end{equation}
$$

当logits太大时，指数求和部分会出现上溢，解决方案：

$$
\begin{equation}
p_i=\frac{e^{l_i-l_{max}}}{\sum_\limits{j}e^{l_j-l_{max}}}
\end{equation}
$$

\\(l_j-l_{max}\le0\\)且必有至少一项为0，因此指数和不会出现上溢，分母不会出现下溢。

Cross-entropy公式：
$$
\begin{equation}
xent=-\sum_\limits{i}y_i\ln p_i
\end{equation}
$$
若\\(p_i\\)接近0，则\\(\ln p_i\\)会发生下溢，解决方案：

将(2)代入(3),有

$$
\begin{equation}
\begin{aligned}
xent&=-\sum_\limits{i}y_i\ln {(\frac{e^{l_i-l_{max}}}{\sum_\limits{j}e^{l_j-l_{max}}})} \\\\
&=-\sum_\limits{i}y_i(l_i-l_{max}-\ln{\sum_\limits{j}e^{l_j-l_{max}}})\\\\
&=\sum_\limits{i}y_i(\ln{\sum_\limits{j}e^{l_j-l_{max}}}+l_{max}-l_i)
\end{aligned}
\end{equation}
$$

### Pytorch简单实现

```Python
class SoftmaxCrossEntropyLoss(nn.Module):
    def __init__(self, dim=1, mean=True):
        super(SoftmaxCrossEntropyLoss, self).__init__()
        self.dim = dim
        self.mean = mean

    def forward(self, logits, targets):
        if len(targets.shape) == 1:
            # one-hot
            ones = torch.eye(logits.shape[self.dim]).to(targets.device)
            targets = ones.index_select(0, targets)
        
        max_logit = logits.max()
        exp_sum = (logits - max_logit).exp().sum(dim=self.dim, keepdim=True)
        log_softmax = logits - max_logit - exp_sum.log()

        xent = - (targets * log_softmax).sum()
        
        if self.mean:
            xent /= logits.shape[0]
        
        return xent
```
---
