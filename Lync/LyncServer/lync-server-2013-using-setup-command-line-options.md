---
title: セットアップ コマンドライン オプションの使用
TOCTitle: セットアップ コマンドライン オプションの使用
ms:assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205129(v=OCS.15)
ms:contentKeyID: 48272936
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# セットアップ コマンドライン オプションの使用

 

_**トピックの最終更新日:** 2016-12-08_

Setup.exe コマンド ラインは、Office セットアップの操作ではほとんど使用されません。製品のセットアップや機能のカスタマイズには、セットアップ コマンドライン オプションではなく Office カスタマイズ ツールと Config.xml ファイルを使用するのが一般的です。

Office Setup.exe コマンド ラインは、次の表に示すコマンドライン オプションを認識します。

### Office セットアップ コマンドライン オプション

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>セットアップ コマンドライン オプション</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>/admin</p></td>
<td><p>Office カスタマイズ ツールを実行してセットアップ カスタマイズ ファイル (.msp ファイル) を作成します。</p></td>
</tr>
<tr class="even">
<td><p>/adminfile [パス]</p></td>
<td><p>指定したセットアップ カスタマイズ ファイルをインストールに適用します。特定のカスタマイズ ファイル (.msp ファイル) のパスを指定することも、カスタマイズ ファイルが格納されているフォルダーのパスを指定することもできます。</p></td>
</tr>
<tr class="odd">
<td><p>/config [パス]</p></td>
<td><p>インストール時にセットアップで使用する Config.xml ファイルを指定します。/config オプションを使用して、Lync 2013 のインストール用にカスタマイズした Config.xml ファイルを指定します (例: <code>/config \\server\share\Lync15\Lync.WW\Config.xml</code>)。</p></td>
</tr>
<tr class="even">
<td><p>/modify Lync</p></td>
<td><p>変更した Config.xml ファイルと共に使用して、セットアップをメンテナンス モードで実行して Office の既存のインストールを変更します。たとえば、/modify オプションを使用して Lync 機能を追加または削除できます。</p></td>
</tr>
<tr class="odd">
<td><p>/repair Lync</p></td>
<td><p>ユーザーのコンピューターからセットアップを実行して Lync を修復します。</p></td>
</tr>
<tr class="even">
<td><p>/uninstall Lync</p></td>
<td><p>セットアップを実行してユーザーのコンピューターから Lync を削除します。</p></td>
</tr>
</tbody>
</table>


セットアップ コマンドライン オプションの使用の詳細については、[http://go.microsoft.com/fwlink/?linkid=267515\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=267515%26clcid=0x411) を参照してください。

