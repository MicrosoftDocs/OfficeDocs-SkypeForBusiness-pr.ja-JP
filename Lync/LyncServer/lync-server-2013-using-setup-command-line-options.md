---
title: 'Lync Server 2013: セットアップコマンドラインオプションを使用する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Setup command-line options
ms:assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205129(v=OCS.15)
ms:contentKeyID: 48184957
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aacaa402b325fbefe13d70dea4f3e74af1d896cb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007546"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-setup-command-line-options-in-lync-server-2013"></a>Lync Server 2013 でのセットアップコマンドラインオプションの使用

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-03_

Setup.exe コマンド ラインは、Office セットアップの操作ではほとんど使用されません。製品のセットアップや機能のカスタマイズには、セットアップ コマンドライン オプションではなく Office カスタマイズ ツールと Config.xml ファイルを使用するのが一般的です。

Office Setup.exe コマンド ラインは、次の表に示すコマンドライン オプションを認識します。

### <a name="office-setup-command-line-options"></a>Office セットアップ コマンドライン オプション

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
<td><p>インストール時にセットアップによって使用される Config.xml ファイルを指定します。 次の例のように、/config オプションを使用して、Lync 2013 のインストール用にカスタマイズした Config.xml ファイルを指定します。<code>/config \\server\share\Lync15\Lync.WW\Config.xml</code></p></td>
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


セットアップコマンドラインオプションの使用の詳細については<http://go.microsoft.com/fwlink/p/?linkid=267515>、「」を参照してください。

</div>

<span> </span>

</div>

</div>

</div>

