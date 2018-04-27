# oneStep

```
2018/03/20
* 用引擎掃 ifonly.apk，掃了將近一個小時，且發現很多預期之外會被掃出來的 api。
  這表示很可能該 apk 被包了很多根本不會用到的 api。或許這就是 apk 瘦身的切入點？
  
2018/03/21
  https://github.com/18z/apk-re-forfun/blob/master/02/01.md

2018/03/22
  https://github.com/18z/apk-re-forfun/blob/master/02/02.md

2018/03/23
  https://github.com/18z/apk-re-forfun/blob/master/02/02.md

2018/03/26
  https://github.com/18z/apk-re-forfun/blob/master/02/02.md

2018/03/27
  https://github.com/18z/apk-re-forfun/blob/master/02/genymotion.md
  https://github.com/18z/apk-re-forfun/blob/master/02/frida.md
  https://blog.csdn.net/zuiwuyuan/article/details/48552701
  
2018/03/28
  https://github.com/18z/apk-re-forfun/blob/master/02/proguard.md
  
2018/03/29
  https://github.com/18z/apk-re-forfun/blob/master/02/proguard.md
  afn 改 function name
  http://sushant94.me/2015/05/31/Introduction_to_radare2/
  
2018/03/30
  https://monosource.gitbooks.io/radare2-explorations/content/intro/projects.html
  https://github.com/18z/apk-re-forfun/blob/master/02/rename-function.md
  
2018/04/02
  https://github.com/18z/apk-re-forfun/blob/master/02/r2project.md
  https://radare.gitbooks.io/radare2book/content/basic_commands/write.html
  https://www.u235.io/single-post/2017/07/23/Simplistic-Binary-Patching-With-Radare2
  https://androidrepublic.org/threads/using-radare2-for-binary-patch.21436/
  
2018/04/03
  https://github.com/18z/apk-re-forfun/blob/master/02/patch.md
  
2018/04/09
  apktool
    (2013)    http://akashkhaitan.soulastral.com/android/unpackingandrepackingapk
    (2015) ** https://blog.bramp.net/post/2015/08/01/decompile-and-recompile-android-apk/
    (2015) *  http://www.cis.syr.edu/~wedu/seed/Labs_Android5.1/Android_Repackaging/Android_Repackaging.pdf
    (2016)    https://yifeng.studio/2016/12/05/android-apk-decompile-and-repackaging/
    (2016) ** http://huli.logdown.com/posts/661513-android-apk-decompile
    (2018) *  https://nyllep.wordpress.com/2018/02/25/decompiling-and-reading-17media-sourcecode/
  radare2
    (2016)    https://androidrepublic.org/threads/using-radare2-for-binary-patch.21436/
    
2018/04/10
  https://github.com/18z/apk-re-forfun/blob/master/02/apktool.md
  
2018/04/11
  https://github.com/18z/apk-re-forfun/blob/master/02/apktool.md
  
2018/04/12
  https://github.com/18z/apk-re-forfun/blob/master/02/apktool.md

2018/04/13
  https://github.com/18z/apk-re-forfun/blob/master/02/apktool.md
  
2018/04/23
  https://github.com/18z/apk-re-forfun/blob/master/02/apktool.md
  https://github.com/18z/apk-re-forfun/blob/master/02/api-engine.md
  apk 加殼 ：https://chaman.gitbooks.io/techblog/Android/apk-enchance/apk-enchance.html
  tmr: run patched apk in genymotion to see if it really works.

2018/04/24
  https://github.com/18z/apk-re-forfun/blob/master/02/apktool.md
  tmr: write repackaging scripts

2018/04/25
  .so reference
  1. https://yangbo.tech/2015/11/27/so-files-guide/
  2. * https://www.niwoxuexi.com/blog/android/article/246.html
  3. http://allenfeng.com/2016/11/06/what-you-should-know-about-android-abi-and-so/
  
  write repackaging script
  https://github.com/18z/apk-re-forfun/blob/master/apktool-testenv/repackage.sh
  
  tmr: 驗證腳本 gen 出來的 apk 是否在虛擬機器中正常執行。
  
2018/04/26
  確認腳本 gen 出來的 apk 可在虛擬機器中正常執行。
  針對 https://www.niwoxuexi.com/blog/android/article/246.html step by step 實作
  tmr: https://www.niwoxuexi.com/blog/android/article/246.html 掌握流程
  
2018/04/27
  https://github.com/18z/apk-re-forfun/blob/master/02/frida.md
```
