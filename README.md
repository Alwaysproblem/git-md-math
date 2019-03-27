<!---title:Markdown中插入数学公式的方法-->
<!---keywords:工具-->
<!---date:old-->

## 方法一：使用Google Chart的服务器

```
<img src="http://chart.googleapis.com/chart?cht=tx&chl= 在此插入Latex公式" style="border:none;">
```

一个例子，

```
<img src="http://chart.googleapis.com/chart?cht=tx&chl=\Large x=\frac{-b\pm\sqrt{b^2-4ac}}{2a}" style="border:none;">
```

公式显示结果为：

<img src="http://chart.googleapis.com/chart?cht=tx&chl=\Large x=\frac{-b\pm\sqrt{b^2-4ac}}{2a}" style="border:none;">

适用了下，Google Chart服务器的响应速度还可以，但据说可能复杂一些的Latex公式可能无法解析（参考[2]）。


## 方法二：使用MathJax引擎

大家都看过[Stackoverflow](http://stackoverflow.com/)上的公式吧，漂亮，其生成的不是图片。这就要用到MathJax引擎，在Markdown中添加MathJax引擎也很简单，

```
<script type="text/javascript" src="http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=default"></script>
```

<script type="text/x-mathjax-config"> 
    MathJax.Hub.Config({ TeX: { equationNumbers: { autoNumber: "all" } } }); 
</script>

<script type="text/x-mathjax-config">
    MathJax.Hub.Config({tex2jax: {
            inlineMath: [ ['$','$'], ["\\(","\\)"] ],
            processEscapes: true
        }
        });
</script>

<script type="text/javascript" src="http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=default"></script>

然后，再使用Tex写公式。`$$公式$$`表示行间公式，本来Tex中使用`\(公式\)`表示行内公式，但因为Markdown中`\`是转义字符，所以在Markdown中输入行内公式使用`\\(公式\\)`，如下代码：

```
$$x=\frac{-b\pm\sqrt{b^2-4ac}}{2a}$$
\\(x=\frac{-b\pm\sqrt{b^2-4ac}}{2a}\\)
```

分别显示结果（行间公式）：

$$x=\frac{-b\pm\sqrt{b^2-4ac}}{2a}$$

行内公式：
\(x=\frac{-b\pm\sqrt{b^2-4ac}}{2a}\)

不信，你可以试一下，在公式上还可以使用鼠标右键操作。

## 参考

[1] <http://www.forkosh.com/mathtextutorial.html>

[2] <http://www.ruanyifeng.com/blog/2011/07/formula_online_generator.html>

[3] <http://www.forkosh.com/mathtex.html>
