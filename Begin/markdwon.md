# Markdown笔记

### <font color=#69bad9>1.基本语法</font>
#### **<font color=red>a.标题</font>**

|markdown|解析效果|
|:---:|:---:|
| #(space)一级标题|<font size=6>一级标题</font>|
|##(space)二级标题|<font size=5>二级标题</font>|
|###(space)三级标题|<font size=4>三级标题</font>|

以此类推,共有六级标题,**注意标记与文字中间有一个空格**


#### **<font color=red>b.特殊标记</font>**

\*\* **这是粗体**\*\*　　　\__这是斜体__　　\~~ ~~这是删除线~~ \~~<br />
>这是引用
>>这是嵌套引用


>这是  
>一个  
>多行引用

`<br>`是换行　　
\`printf()\`解析效果:`printf()`<br />
>个人觉得可以理解为短引用

---

\`\`\`<br>
这是代码<br>
\`\`\`<br>
效果如下(以C语言为示例):
```c
#include <stdio.h>
int main(void)
{
  return 0;
}
```
<br>

---

支持的语言主要有:<br>
-   c/cpp，Java，Python
-   html，XML，YAML，CSS，Js/Ts，Json
-   Go，Rust，Kotlin，Gradle，Groovy
-   Markdown，Makefile，Dockerfile
-   Lua，Julia，Haskell，PHP，Ruby，Lisp，Perl
-   SQL，Objective-c，R，Clojure，Verilog

上面是无序列表,下面是有序列表:<br />
1.第一个<br />
2.第二个<br />
3.第三个<br />


这是链接：[`Markdown教程`](https://markdown.com.cn)
[Markdown教程](https://markdown.xyz)<br />
这也是链接：<https://baidu.com>　　<2839389290@qq.com><br />
脚注：mardown在线编辑器[^1]
a<sup>b</sup>
<!-- (https://markdown.com.cn/editor "参考") -->

---

-   [x] 这是一个多选框
-   [ ] 这也是多选框😊<br />

![图片](https://www.markdown.xyz/assets/images/tux.png)
[![带链接的图片](https://www.markdown.xyz/assets/images/shiprock.jpg)](https://baidu.com)

[^1]:https://markdown.com.cn/editor
