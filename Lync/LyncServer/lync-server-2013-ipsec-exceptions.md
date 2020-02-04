---
title: Lync Server 2013 IPsec の例外
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IPsec exceptions
ms:assetid: 241f1eca-6f2f-44de-90b1-2cb659cbe27c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425719(v=OCS.15)
ms:contentKeyID: 48183627
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37d5becaab996d6fe4889086d3a68a45ffc1f6d7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733457"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ipsec-exceptions-in-lync-server-2013"></a>Lync Server 2013 での IPsec の例外

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-06-27_

インターネットプロトコルセキュリティ (IPsec 4301-4309) が展開されているエンタープライズネットワークの場合、オーディオ、ビデオ、およびパノラマビデオの配信に使用するポートの範囲で IPsec を無効にする必要があります。 この操作を行うと、IPsec のネゴシエーションによってメディア用ポートの割り当てに遅延が生じるのを避けることができます。

次の表に、推奨される IPsec 例外設定を示します。

### <a name="recommended-ipsec-exceptions"></a>推奨される IPSec 例外設定

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th>ルール名</th>
<th>発信元 IP アドレス</th>
<th>送信先 IP アドレス</th>
<th>プロトコル</th>
<th>送信元ポート</th>
<th>宛先ポート</th>
<th>認証要件</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>内部音声ビデオ エッジ サーバー/受信</p></td>
<td><p>任意</p></td>
<td><p>内部音声ビデオ エッジ サーバー</p></td>
<td><p>UDP および TCP</p></td>
<td><p>任意 </p></td>
<td><p>任意</p></td>
<td><p>認証しない</p></td>
</tr>
<tr class="even">
<td><p>外部音声ビデオ エッジ サーバー/受信</p></td>
<td><p>任意</p></td>
<td><p>外部音声ビデオ エッジ サーバー</p></td>
<td><p>UDP および TCP</p></td>
<td><p>任意 </p></td>
<td><p>任意</p></td>
<td><p>認証しない</p></td>
</tr>
<tr class="odd">
<td><p>内部音声ビデオ エッジ サーバー/送信</p></td>
<td><p>内部音声ビデオ エッジ サーバー</p></td>
<td><p>任意</p></td>
<td><p>UDP &amp; TCP</p></td>
<td><p>任意 </p></td>
<td><p>任意</p></td>
<td><p>認証しない</p></td>
</tr>
<tr class="even">
<td><p>外部音声ビデオ エッジ サーバー/送信</p></td>
<td><p>外部音声ビデオ エッジ サーバー</p></td>
<td><p>任意</p></td>
<td><p>UDP および TCP</p></td>
<td><p>任意 </p></td>
<td><p>任意</p></td>
<td><p>認証しない</p></td>
</tr>
<tr class="odd">
<td><p>仲介サーバー/受信</p></td>
<td><p>任意</p></td>
<td><p>仲介</p>
<p>サーバー</p></td>
<td><p>UDP および TCP</p></td>
<td><p>任意 </p></td>
<td><p>任意</p></td>
<td><p>認証しない</p></td>
</tr>
<tr class="even">
<td><p>仲介サーバー/送信</p></td>
<td><p>仲介</p>
<p>サーバー</p></td>
<td><p>任意</p></td>
<td><p>UDP および TCP</p></td>
<td><p>任意 </p></td>
<td><p>任意</p></td>
<td><p>認証しない</p></td>
</tr>
<tr class="odd">
<td><p>会議アテンダント/受信</p></td>
<td><p>任意</p></td>
<td><p>会議アテンダントを実行するフロントエンド サーバー</p></td>
<td><p>UDP および TCP</p></td>
<td><p>任意 </p></td>
<td><p>任意</p></td>
<td><p>認証しない</p></td>
</tr>
<tr class="even">
<td><p>会議アテンダント/送信</p></td>
<td><p>会議アテンダントを実行するフロントエンド サーバー</p></td>
<td><p>任意</p></td>
<td><p>UDP および TCP</p></td>
<td><p>任意 </p></td>
<td><p>任意</p></td>
<td><p>認証しない</p></td>
</tr>
<tr class="odd">
<td><p>音声ビデオ会議サーバー/受信</p></td>
<td><p>任意</p></td>
<td><p>フロントエンド サーバー</p></td>
<td><p>UDP および TCP</p></td>
<td><p>任意 </p></td>
<td><p>任意</p></td>
<td><p>認証しない</p></td>
</tr>
<tr class="even">
<td><p>音声ビデオ会議/送信</p></td>
<td><p>フロントエンド サーバー</p></td>
<td><p>任意</p></td>
<td><p>UDP および TCP</p></td>
<td><p>任意 </p></td>
<td><p>任意</p></td>
<td><p>認証しない</p></td>
</tr>
<tr class="odd">
<td><p>Exchange/受信</p></td>
<td><p>任意</p></td>
<td><p>Exchange ユニファイド メッセージング</p></td>
<td><p>UDP および TCP</p></td>
<td><p>任意 </p></td>
<td><p>任意</p></td>
<td><p>認証しない</p></td>
</tr>
<tr class="even">
<td><p>アプリケーション共有サーバー/受信</p></td>
<td><p>任意</p></td>
<td><p>アプリケーション共有サーバー</p></td>
<td><p>TCP</p></td>
<td><p>任意</p></td>
<td><p>任意</p></td>
<td><p>認証しない</p></td>
</tr>
<tr class="odd">
<td><p>アプリケーション共有サーバー/送信</p></td>
<td><p>アプリケーション共有サーバー</p></td>
<td><p>任意</p></td>
<td><p>TCP</p></td>
<td><p>任意 </p></td>
<td><p>任意</p></td>
<td><p>認証しない</p></td>
</tr>
<tr class="even">
<td><p>Exchange/送信</p></td>
<td><p>Exchange ユニファイド メッセージング</p></td>
<td><p>任意</p></td>
<td><p>UDP および TCP</p></td>
<td><p>任意 </p></td>
<td><p>任意</p></td>
<td><p>認証しない</p></td>
</tr>
<tr class="odd">
<td><p>クライアント</p></td>
<td><p>任意 </p></td>
<td><p>任意</p></td>
<td><p>UDP</p></td>
<td><p>指定メディア ポート範囲</p></td>
<td><p>任意</p></td>
<td><p>認証しない</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

