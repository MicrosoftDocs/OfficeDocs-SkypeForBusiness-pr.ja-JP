---
title: インストール タスクを実行するための Using Config.xml の使用
TOCTitle: インストール タスクを実行するための Using Config.xml の使用
ms:assetid: 0813184a-ab40-417c-b3a3-c2090766b831
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204651(v=OCS.15)
ms:contentKeyID: 48271162
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# インストール タスクを実行するための Using Config.xml の使用

 

_**トピックの最終更新日:** 2016-12-08_

Office カスタマイズ ツール (OCT) はカスタマイズ インストール向けの主要ツールですが、管理者は OCT では使用できない追加のインストール手順を Config.xml ファイルによって指定できます。以下のカスタマイズは、Config.xml ファイルを使用しないと実行できません。

  - ネットワーク インストール ポイントのパスを指定する。

  - インストールする製品を選択する。

  - ログ記録や、セットアップ カスタマイズ ファイルおよびソフトウェア更新プログラムの場所を構成する。

  - インストール オプション (ユーザー名など) を指定する。

  - Office をインストールせずにローカル インストール ソース (LIS) をユーザーのコンピューターにコピーする。

  - インストールに対する言語の追加または削除を行う。

Config.xml ファイルを使用して、Lync 2013 のサイレント インストールを構成することをお勧めします。

既定では、コア製品のフォルダー (たとえば \\product.WW) に格納されている Config.xml ファイルがその製品をインストールするようにセットアップに指示します。たとえば、次に示すフォルダーの Config.xml ファイルは Lync 2013 をインストールします。

  - \\\\server\\share\\Lync15\\Lync.WW \\Config.xml

Lync 2013 のインストールで最もよく使用される Config.xml の要素は、次の表のとおりです。

### Config.xml の要素

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>要素</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Configuration</p></td>
<td><p>最上位の要素 (必須)。製品属性が含まれます。例: Product=Lync</p></td>
</tr>
<tr class="even">
<td><p>OptionState</p></td>
<td><p>インストール中、特定の製品の機能が処理される方法を指定します。次の属性を使用して、Outlook 2010 を中断する共有コンポーネントが含まれる Business Connectivity Services がインストールされないようにします。</p>
<ul>
<li><p>Id=&quot;LOBiMain&quot;</p></li>
<li><p>State=&quot;Absent&quot;</p></li>
<li><p>Children=&quot;Force&quot;</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Display</p>
<p></p></td>
<td><p>セットアップがユーザーに表示する UI のレベル。一般的には次の属性があります。</p>
<ul>
<li><p>CompletionNotice=&quot;Yes&quot; | &quot;No&quot;(既定)</p></li>
<li><p>AcceptEula=&quot;Yes&quot; | &quot;No&quot;(既定)</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Logging</p></td>
<td><p>セットアップが実行するログ記録の種類のオプション。一般的には次の属性があります。</p>
<ul>
<li><p>Type =&quot;Off&quot; | &quot;Standard&quot;(既定) | &quot;Verbose&quot;</p></li>
<li><p>Template=”<em>filename</em>.txt” (ログファイルの名前)</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Setting</p></td>
<td><p>Windows インストーラーのプロパティの値を指定します。一般的には次の属性があります。</p>
<ul>
<li><p>Setting Id=&quot;<em>name</em>&quot; (Windows インストーラーのプロパティの名前)</p></li>
<li><p>Value=&quot;<em>value</em>&quot; (プロパティに割り当てる値)</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>DistributionPoint</p></td>
<td><p>インストールを実行するネットワーク インストール ポイントの完全修飾パス</p>
<ul>
<li><p>Location=”<em>path</em>”</p></li>
</ul></td>
</tr>
</tbody>
</table>


次の例は、一般的な Lync 2013 のサイレント インストールのための Config.xml file を示しています。

    <Configuration Product="Lync">
      <OptionState Id="LOBiMain" State="Absent" Children="Force" />
      <Display Level="None" CompletionNotice="No" AcceptEula="Yes" />
      <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
      <Setting Id="SETUP_REBOOT" Value="Never" />
      <DistributionPoint Location="\\server\share\Lync15" />
    </Configuration>

Config.xml ファイルを使用して Office のインストールおよびメンテナンスのタスクを実行する方法の詳細については、[http://go.microsoft.com/fwlink/?linkid=267514\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=267514%26clcid=0x411) を参照してください。

## Config.xml ファイルをカスタマイズするには

1.  Notepad などのテキスト エディター ツールで Config.xml ファイルを開きます。

2.  変更する要素を含む行に移動します。

3.  使用するサイレント オプションで要素のエントリを変更します。"\<\!--" や "--\>" などのコメント区切り文字は削除してください。たとえば、次の構文を使用します。
    
        < DistributionPoint Location="\\server\share\Lync15" />

4.  Config.xml ファイルを保存します。

