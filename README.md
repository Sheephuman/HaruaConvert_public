# このソフトウェアについて

カジュアルな外観（かなり多分）のffmpegフロントエンド兼簡易コーデックチェッカーです<br>
砂雲空風氏作成のキャラクターによる **同人ウェア** 
です<br>
Twitter:https://x.com/shiyokatadragon<br>
pixsiv:https://www.pixiv.net/users/3998554<br>

著作権は砂雲氏にあるので、**内部の画像素材の再利用を一切禁じます。**

# 動作環境
Windows10以降、**.net Framework8以降**がインストールされている環境。<br>
<br>
フレームワーク：https://dotnet.microsoft.com/ja-jp/download/dotnet/8.0#:~:text=.NET%208.0%20d<br>
SDK 8.0.403for Windowsのダウンロード(x64)：https://dotnet.microsoft.com/ja-jp/download/dotnet/thank-you/sdk-8.0.403-windows-x64-installer

フレームワーク不要の自己完結型も用意するつもりです（ファイルサイズがデカい）。<br>
<br>
WPF/C# で制作しています。<br>
aviutlのLog表示の挙動を取り入れてます<br>

元ネタは　Twitter用に動画変換するヤツ([2016_twitter_convert](https://cloth.moe/2016_twitter_convert))（2019）　で、ffmpegに渡すパラメータを随時変更出来、bitrate指定により動画圧縮まで可能にします。
~~最近も誰かに言われたけど別にバグだらけという訳ではない(笑)~~

<br>
機能の概要<br>
a.ドラッグ&ドロップで動画をTwitter（X）に投稿可能な動画ファイルとして出力します。<br>
　-b:v 1200k -codec:v h264 -vf yadif=0:-1:1 -pix_fmt yuv420p -acodec aac -y -threads 2<br>
h264とvf yadif=0:-1:1　がポイントらしいです。<br>

<br>今は-b:v 700k **-codec:v libx265** -vf yadif=0:-1:1 -pix_fmt yuv420p -acodec aac -y -threads 2<br><br>
libx265の使用がおすすめ。高圧縮率・高画質です

![image](https://github.com/user-attachments/assets/06cf0cc7-eb18-40a3-9c2c-c00b546119bc)


<br>
パラメータは公開されており、好みのパラメータに差し替え可能です。
 
 <br>
b.ffmpegに渡すパラメーターを任意に変更出来るため、画像出力やgif出力にも対応します。<br>

<br>
c.パラメーターを100個まで保存しておけます。<br>

![image](https://github.com/user-attachments/assets/f1c6d41f-d48a-494d-b97a-3300b44cca1e)


<br>

4.bitrateを指定する事で、動画のサイズ圧縮を可能にします<br>
　→ソース動画を読み込むとbitrateなどの情報が出るようになっています。表示されたbitrate以下の数を指定してください。<br>
 　　最低でも500k以上を指定した方が画質を維持出来ます。<br>
  →簡易の動画Codec情報閲覧ツールとしても使えなくもないです。<br>



2024/8/17　開発版<br>
　
## Download

[暫定的な開発版(v1.1.0-alpha)](https://github.com/Sheephuman/HaruaConvert_public/releases/tag/TestVersion)) 


# 最近の更新
・パラメータ組み立て機能の追加　<br>
Codec取得はffmpeg.exeにコマンドラインを流して行っています。<br>
性能が高いCodecを使えるように厳選しました（つもり）<br>
　<br>![image](https://github.com/user-attachments/assets/f4e47872-ec97-4abe-b584-934fd683bbf7)



最新のffmpegバイナリを同梱しています。ライセンスに基づきソースコードへのリンクを貼っています。<br>ffmpeg自体は``LGPLv3``でライセンスされています。

<br>
ffmpegのソースコード<br>
https://github.com/FFmpeg/FFmpeg　<br>
https://ffmpeg.org/download.html<br>

# ffmpegについて
## 使用条件
FFmpegの使用に関する条件は、ライセンス文書に明記されています。ライセンスの詳細については、[LGPLライセンスの公式ページ](https://www.gnu.org/licenses/lgpl-3.0.html)をご参照ください。
## 免責事項
FFmpegは無償で提供されており、著作権者または提供者は、FFmpegの使用に関連するいかなる保証も行いません。ソフトウェアの使用に際して生じるいかなる問題についても責任を負いませんので、あらかじめご了承ください。

# 今後の更新予定<br>
・任意の画像でWaterMarkを付けられるようにする
<br>
・変換する添え字を変えられるように改良<br>
・GIFアニメ等を付ける<br>
・拡張パラメータシステムの機能追加<br>
・色合いも変更出来るように


# 最後に
ご覧になっていただきまして、ありがとうございます。
