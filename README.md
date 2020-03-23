Adobe Reader DC 不要機能の無効化
================================

* 「共有」ボタンラベルを消す
    * ツールバー上で右クリック → 「共有ボタンラベルを非表示」を選択
    * 参考: [ツールバーをカスタマイズする方法](https://helpx.adobe.com/jp/acrobat/kb/3415.html)
* 「ログイン」ボタンラベルを消す
    * レジストリ `\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Adobe\Acrobat Reader\DC\FeatureLockDown\cServices` にキー `bUpdater` を「DWORD(32ビット)値」で作成する (値は0のまま)
    * 参考: [アップデーターの自動チェックを変更する / 無効にする方法](https://helpx.adobe.com/jp/acrobat/kb/cq05201026.html)
    * 自動アップデートも無効になるため注意 (本来は「ログイン」ボタンラベルと連動する方がおかしい気がする)
* Document Cloud メニューを無効にする
    * レジストリ `\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Adobe\Acrobat Reader\DC\FeatureLockDown\cServices` にキー `bToggleAdobeDocumentServices` を「DWORD(32ビット)値」で作成し、値を1にする
    * 参考: [Document Cloud メニューおよび Mobile Link 機能を無効にする方法](https://helpx.adobe.com/jp/acrobat/kb/cq05150932.html)
* ツールペインを閉じたままにする
    * 下記ページを参考に設定を変更した後、Adobe Reader を立ち上げ直してからツールペインを閉じる
    * 参考: [Acrobat Reader DC のツールペインを閉じる](https://helpx.adobe.com/jp/acrobat/kb/disable-right-hand-pane-in-acrobat-reader.html)
* その他参考資料
    * [A preference dictionary for Acrobat products](https://www.adobe.com/devnet-docs/acrobatetk/tools/PrefRef/Windows/index.html)
        * [FeatureLockdown (Lockable Settings)](https://www.adobe.com/devnet-docs/acrobatetk/tools/PrefRef/Windows/FeatureLockdown.html)
