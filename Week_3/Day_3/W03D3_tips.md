# Roy's Note

## tips
// git branch <branch> && git checkout <branch>
git checkout -b feature/user-registration  
** Git在dev分支获取master分支最新代码 **
简单方法：  
git pull origin master  
或者：  
1、git checkout master      切换到主分支  
2、git pull                           拉取主分支最新代码  
3、git checkout  dev1         切换到dev1分支
4、git pull                            拉取最新代码  
5、git merge master           合并主分支最新代码到dev1分支    
6、有冲突解决冲突  
7、git push                          推送本地dev1分支最新代码到远程dev1分支

**JavaScript四舍五入并保留两位小数**
自带的Math.Round()函数，能够对一个浮点数进行四舍五入，但是返回的结果是个整数，无法精确到小数点后.  
Number.toFixed()方法，能保留小数点后面的指定位数，但如果执行2.1.toFixed(2)的话，会返回2.10，而不是我们期待的2.1.  
```javascript
Math.round(number * 100) / 100;
```