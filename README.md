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
  
2018/04/29
  https://github.com/18z/apk-re-forfun/blob/master/02/frida.md
  
2018/05/01
  1. 同步 android emulator 中 frida-server-android-x86 版本，以及 macos frida 版本為 10.8.0。
  2. 啟動 frida-server in android emulator
  3. frida-ps -U|less (In another terminal, 
     in a regular OS shell, check if Frida is running and lists processes on Android:)
  4. 鎖定 com.android.browser
  5. frida-trace -i "open" -U com.android.browser
  
2018/05/02
  透過 frida-trace -U -f com.android.calendar 將 com.android.calendar 啟動。
  https://github.com/18z/apk-re-forfun/blob/master/02/frida.md
  frida-trace -i -I 參數差異是？
  
2018/05/03
  1. frida-trace -i open 在 re_simple 上有 output。但還是無法解讀結果。
  2. frida-discover 無法用。
  3. 修改 open.js 成功
  4. 對 open function 問題的定義描述更清楚一點。
  
2018/05/04
  先前 frida hook 結果中出現 base.apk。
  經了解，是 apk 安裝過程中，會出現的東西。
  
  參考與整理
  https://www.jianshu.com/p/ae45af3c3098
  
  細節
  https://github.com/18z/apk-re-forfun/blob/master/02/frida.md
  
  Android：JNI 与 NDK到底是什么？
  https://blog.csdn.net/carson_ho/article/details/73250163

2018/05/07
  1. 原本想看 https://blog.csdn.net/carson_ho/article/details/73250163
  2. 後來看到 https://developer.android.com/ndk/guides/
     就決定看官方文件了，不要捨近求遠。
  3. base.apk 與原本 apk 差別在哪？(parkmftsai 大大 05/07 問題二有解答！)
     https://github.com/parkmftsai/Reverse-apk-research/blob/master/learning_reverse_apk_record.md
     
2018/05/08
  https://github.com/18z/apk-re-forfun/blob/master/02/ndk.md
  1. NDK 主要目的：build C and C++ source code 到 shared libary 中，使得 App 可以使用。
  2. Android.mk:       which defines properties specific to individual modules, or libraries. 
                       (特定的，module, library)
  3. Application.mk:   which defines properties for all the modules that you use in your app.
                       (all, modules use in the app)
                       
2018/05/09
  寫出 ndk-simple.apk，並成功在模擬器上運行。
  https://github.com/18z/apk-re-forfun/blob/master/02/ndk.md

2018/05/10

  實驗：patch .so 檔
  結果：失敗

  實驗步驟：
  1. 以 apktool d NDK-simple.apk 將 apk 解開
  2. 以 r2 -w 修改 lib/arm64-v8a, armeabi-v7a, x86, x86_64 中的 libnative-lib.so 
     將內部字串 Hello from C++ 改成 HELLO FROM CPP
  3. 以 apk-re-forfun 中的 repackage.sh 將改過的 .so 檔重新包裝
  4. 將 apk 送進 genymotion 中運行，字串還是 Hello from C++，實驗失敗。
  5. 試圖以 grep -r "Hello" . 在  NDK-simple 目錄下找尋，發現
     Binary file ./lib/x86_64/libnative-lib.so matches
     Binary file ./build/apk/res/layout/activity_main.xml matches
     Binary file ./build/apk/lib/x86_64/libnative-lib.so matches
     因此懷疑，可能有其他地方沒改到。

2018/05/14

  用了 radiff2 兩個參數 -x, -D 來看 .so 檔
  -D 發現，x86, x86_64 都有 invalid。
  
2018/05/16
  實驗：patch .so 檔
  結果：失敗

  實驗步驟：
  1. 撰寫 1 ndk apk。直接刪除 proguard-rules.pro。
  2. generate signed apk。
  3. 跑在 genymotion 中，成功！
  4. vim 直接改 proguard-rules.pro excluded apk。
  5. 將改過的 apk 試跑在 genymotion 中，閃退。
  
2018/05/17
  實驗：patch .so 檔
  結果：失敗

  實驗步驟：

  1. 以 r2 修改 signed apk (with no proguard-rules.pro)。
  2. 跑在 genymotion 中。
  3. app 沒閃退，但字串不變。@@
  
2018/05/21
  列出所有 android 內檔案，並解釋用途。
  猜測之所以 patch .so 失敗，可能跟驗證機制有關係。
  或許 config 檔中會有關閉驗證機制的設定？

2018/05/22
  鎖定下一步，用 r2pipe 找出特定字串相對記憶體位置。
  
2018/05/23
  auto patch r2script complete
  https://github.com/18z/re-env/blob/master/r2scripts/patch.py
  
2018/05/24

延續 2018/05/21 的東西。

manifests
  AndroidManifest.xml
Gradle Scripts
  build.gradle (Project: NDK_SIMPLE2)
  build.gradle (Module: app)
  gradle-wrapper.propertes (Gradle Version)
  proguard-rules.pro (ProGuard Rules for app)
  gradle.properties (Project Properties)
  settings.gradle (Project Settings)
  local.properties (SDK Location)
External Build Files
  CMakeLists.txt
  
  
請教 ChenJS 摘要 ：
1. 要先確定 模擬器的版本  是 x86 , x64, arm 32 , arm 64 ， 修改完so後 重新簽章  安裝時 會出現 INSTALL_FAILED_TEST_ONLY .......
2. 要使用 pm install -t -r xx.apk去安裝
3. 如果模擬器裡面, 之前app沒有移除  會出現INSTALL_PARSE_FAILED_INCONSISTENT_CERTIFICATES，就要移除app 再重新安裝
4. 再編譯ndk時  就要將proguard-rules.pro刪除了

cky
1. 模擬器版本我有確認！
2. 我是用 genymotion 付費版本，所以我安裝都是直接將 apk 拖拉進去模擬器就會自動安裝了。
3. 裝 apk 前，我都有確保模擬器裡面的舊 apk 已刪除！
4. 編譯 ndk 前，我就將 proguard-rules.pro 刪掉了。

cky
1. 修改 binary 你用的是什麼編輯器？
2. 模擬器是用哪一個？

ChenJS 
1. MadEdit 直接改 16禁制的字串
2. 模擬器使用Android Studio內建的   sdk 4.4 5.0 都可以執行
模逆器配置sdk  選 armeabi-v7a  就是arm 32   只要改 armeabi-v7a 檔案夾底下的so 就可以

確認刪除的 proguard-rules.pro 是正確的

2018/05/25
  針對 ChenJS 建議，未來實驗調整。
  1. 安裝方式使用 pm install，而非直接拖拉進 Genymotion。
  2. 改用 MadEdit 編輯器修改。直接改 16 進制。
  3. 直接用 android studio 的模擬器。而非 Genymotion。
  
2018/05/28

  實驗：1 規畫

  1. 選定 No proguard-rules.pro apk
  2. 用 r2 改 .so file
  3. 用 pm install 安裝 apk 進 genymotion
  
2018/05/29

  1. with proguard-rules.pro/ no proguard-rules.pro
  2. r2 改/ vim 改/ MadEdit 改
  3. genymotion / android studio emulator
  4. adb pm install

  1. with proguard-rules.pro -> r2 -> genymotion
  2. with proguard-rules.pro -> vim -> genymotion
  3. with proguard-rules.pro -> MadEdit -> genymotion
  4. with proguard-rules.pro -> r2 -> android studio emulator
  5. with proguard-rules.pro -> vim -> android studio emulator
  6. with proguard-rules.pro -> MadEdit -> android studio emulator
  7. no proguard-rules.pro -> r2 -> genymotion
  8. no proguard-rules.pro -> vim -> genymotion
  9. no proguard-rules.pro -> MadEdit -> genymotion
  10. no proguard-rules.pro -> r2 -> android studio emulator
  11. no proguard-rules.pro -> vim -> android studio emulator
  12. no proguard-rules.pro -> MadEdit -> android studio emulator
  
2015/05/30
  在 ubuntu 中安裝 madedit
  並更新逆向環境安裝包 re-env
```
