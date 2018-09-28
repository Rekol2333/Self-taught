# 忽略语法
1. 所有空行或者以注释符号 ＃ 开头的行都会被 Git 忽略。

可以使用标准的 glob 模式匹配。
匹配模式最后跟反斜杠（/）说明要忽略的是目录。
要忽略指定模式以外的文件或目录，可以在模式前加上惊叹号（!）取反。
所谓的 glob 模式是指 shell 所使用的简化了的正则表达式。
星号（*）匹配零个或多个任意字符；
[abc] 匹配任何一个列在方括号中的字符（这个例子要么匹配一个 a，要么匹配一个 b，要么匹配一个 c）；
问号（?）只匹配一个任意字符；
如果在方括号中使用短划线分隔两个字符，表示所有在这两个字符范围内的都可以匹配（比如 [0-9] 表示匹配所有 0 到 9 的数字）。

>  cat.gitignore
> *.[oa]
> *~

第一行告诉 Git 忽略所有以 .o 或 .a 结尾的文件。一般这类对象文件和存档文件都是编译过程中出现的，我们用不着跟踪它们的版本。
第二行告诉 Git 忽略所有以波浪符（~）结尾的文件，许多文本编辑软件（比如 Emacs）都用这样的文件名保存副本。此外，你可能还需要忽略 log，tmp 或者 pid 目录，以及自动生成的文档等等。要养成一开始就设置好 .gitignore 文件的习惯，以免将来误提交这类无用的文件。

>  忽略所有 .a 结尾的文件
> *.a# 但 lib.a 除外
> !lib.a
> 
>  仅仅忽略项目根目录下的 TODO 文件，不包括 subdir
> /TODO/TODO
>
>  忽略 build/ 目录下的所有文件build/# 会忽略 doc/notes.txt 但不包括 doc/server/notes.txt
> doc/notes.txt

作者：songsongchen
链接：https://www.jianshu.com/p/29a03c466441
來源：简书
简书著作权归作者所有，任何形式的转载都请联系作者获得授权并注明出处。

# .ignore配置
Git 代码管理中，我们在没有添加 .gitignore 文件的前提下提交了代码之后再提交 .gitignore 文件，或者是中途添加某一文件类型到 .gitignore 文件中，需要通过以下命令行的方式，让 .gitignore 文件生效：
1 `git rm -r --cached .`
2 `git add .`
3 `git commit -m "Refresh adding .gitignore file."`
如果是中途从 .gitignore 文件中移除某一文件类型，想要这个文件类型重新被 track，需要通过以下命令行的方式，让 .gitignore 文件生效：
查看源代码打印帮助
1 `git add -f *.class`
2 `git commit -m "Refresh removing .class from .gitignore file."`
备注：注意你所处的分支，如果你在当前分支修改，切换到其他分支是不生效的，如果多人开发，注意合并修改！
[](http://www.ifeegoo.com/git-code-management-dot-gitignore-file-has-no-effect-solution.html#comment-5991)