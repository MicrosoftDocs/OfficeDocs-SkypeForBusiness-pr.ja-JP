---
title: 'Lync Server 2013: Config.xml を使用してインストールタスクを実行する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Config.xml to perform installation tasks
ms:assetid: 0813184a-ab40-417c-b3a3-c2090766b831
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204651(v=OCS.15)
ms:contentKeyID: 48183332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2933da3fc52cc6a5c23f74806ff3a4e81dcb2ba
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212833"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-configxml-to-perform-installation-tasks-in-lync-server-2013"></a>Lync Server 2013 で Config.xml を使用してインストールタスクを実行する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-02_

Office カスタマイズ ツール (OCT) はカスタマイズ インストール向けの主要ツールですが、管理者は OCT では使用できない追加のインストール手順を Config.xml ファイルによって指定できます。以下のカスタマイズは、Config.xml ファイルを使用しないと実行できません。

  - ネットワーク インストール ポイントのパスを指定する。

  - インストールする製品を選択する。

  - ログ記録や、セットアップ カスタマイズ ファイルおよびソフトウェア更新プログラムの場所を構成する。

  - インストール オプション (ユーザー名など) を指定する。

  - Office をインストールせずにローカル インストール ソース (LIS) をユーザーのコンピューターにコピーする。

  - インストールに対して言語の追加または削除を行う。

Config.xml ファイルを使用して Lync 2013 サイレントインストールを構成することをお勧めします。

既定では、コア製品フォルダー (たとえば、product) \\に格納されている config.xml ファイル。WW) セットアップに、その製品をインストールするように指示します。 たとえば、次のフォルダーの Config.xml ファイルでは、Lync 2013 がインストールされます。

  - \\\\サーバー\\共有\\Lync15\\Lync. \\xml

Lync 2013 のインストールに最もよく使用される Config.xml 要素を、次の表に示します。

### <a name="configxml-elements"></a>Config.xml の要素

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
<td><p>インストール中、特定の製品の機能が処理される方法を指定します。 次の属性を使用して、Outlook 2010 に影響を与える共有コンポーネントを含む Business Connectivity Services のインストールを禁止します。</p>
<ul>
<li><p>Id =&quot;lobimain&quot;</p></li>
<li><p>状態 =&quot;存在しない&quot;</p></li>
<li><p>Children =&quot;Force&quot;</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>表示</p></td>
<td><p>セットアップがユーザーに表示する UI のレベル。一般的には次の属性があります。</p>
<ul>
<li><p>完了通知 =&quot;はい&quot; | &quot;No&quot;(既定値)</p></li>
<li><p>AcceptEula =&quot;はい&quot; | &quot;No&quot;(既定値)</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>ログ記録</p></td>
<td><p>セットアップが実行するログ記録の種類のオプション。一般的には次の属性があります。</p>
<ul>
<li><p>Type =&quot;Off&quot; | &quot;Standard&quot;(既定値) |&quot;詳細&quot;</p></li>
<li><p>Template=”filename.txt” (ログファイルの名前)</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>設定</p></td>
<td><p>Windows インストーラーのプロパティの値を指定します。一般的には次の属性があります。</p>
<ul>
<li><p>Setting Id =&quot;Name&quot; (Windows Installer プロパティの名前)</p></li>
<li><p>値 =&quot;value&quot; (プロパティに割り当てる値)</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>DistributionPoint</p></td>
<td><p>インストールを実行するネットワーク インストール ポイントの完全修飾パス</p>
<ul>
<li><p>Location = "path"</p></li>
</ul></td>
</tr>
</tbody>
</table>


次の例は、Lync 2013 の一般的なサイレントインストール用の Config.xml ファイルを示しています。

    <Configuration Product="Lync">
      <OptionState Id="LOBiMain" State="Absent" Children="Force" />
      <Display Level="None" CompletionNotice="No" AcceptEula="Yes" />
      <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
      <Setting Id="SETUP_REBOOT" Value="Never" />
      <DistributionPoint Location="\\server\share\Lync15" />
    </Configuration>

Config.xml ファイルを使用した Office のインストールおよびメンテナンスタスクの実行方法の詳細につい<https://go.microsoft.com/fwlink/p/?linkid=267514>ては、を参照してください。

<div>

## <a name="to-customize-the-configxml-file"></a>Config.xml ファイルをカスタマイズするには

1.  Notepad などのテキスト エディター ツールで Config.xml ファイルを開きます。

2.  変更する要素を含む行に移動します。

3.  使用するサイレント オプションで要素のエントリを変更します。 コメントの区切り文字 "\<\!--" と "--\>" は削除してください。 たとえば、次の構文を使用します。
    
        < DistributionPoint Location="\\server\share\Lync15" />

4.  Config.xml ファイルを保存します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

