# Windows と Linux(max)のコマンド違い




|  操作  |  windows  | Linux  |
| ---- | ---- |---- |
|  現在のディレクトリの場所を確認する  |  @cd  |  pwd   |
|  ファイルやディレクトリの情報を表示する	  |  TD  |     |ディレクトリ間の移動　| cd (or) chdir | cd | 
| ディレクトリを作成 | md (or) mkdir |  |
| ディレクトリを移動 | move |mv -r  |
| ディレクトリをコピー | xcopy /e /c /h | cp -r |
| ディレクトリを削除 | rmdir /s | rm -r |
| ファイルを移動 | move | mv |
| ファイルをコピー | copy | cp |
| ファイルを削除 |del (or) erase  | rm |
| テキストファイルの内容を表示 | type |cat (or) less	  |
|  |  |  |
|  |  |  |
|  |  |  |
|  |  |  |

```
ffmpeg -i input.mp4 -s resolution -crf 18 output.mp4
```


-sのresolutionには映像の解像度を指定します。


-crfの後の数値は、大きいほど圧縮効率が高まります。


ただし品質が落ちますので、十分吟味してください。
