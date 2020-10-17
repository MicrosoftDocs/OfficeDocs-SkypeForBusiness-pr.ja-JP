---
title: ポートの概要-SIP、XMPP フェデレーション、およびパブリックインスタントメッセージング
description: ポートの概要-SIP、XMPP フェデレーション、およびパブリックインスタントメッセージング。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - SIP, XMPP federation, and public instant messaging
ms:assetid: ab05bdd6-e9b0-4b1b-9dd9-29ab88e8befe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618373(v=OCS.15)
ms:contentKeyID: 49105660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c58dbf7bdd56b4678d56f96a11332219bb40c17
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566359"
---
# <a name="port-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>ポートの概要-Lync Server 2013 の SIP、XMPP フェデレーション、およびパブリックインスタントメッセージング

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-03-15_

Microsoft Lync Server 2013、Lync Server 2010、および Office Communications Server とのフェデレーションのためのポート、プロトコル、およびファイアウォールの要件は、展開されたエッジサーバーの場合と似ています。 クライアントは、TLS/SIP/TCP 443 経由のアクセスエッジサービスとの通信を開始します。 ただし、フェデレーションパートナーは、MTLS/SIP/TCP 5061 を介してアクセスエッジサービスへの通信を開始します。

パブリックインスタントメッセージング接続をサポートするために必要なポートとプロトコルを使用するようにファイアウォールを構成するには、まず、SIP/MTLS/TCP 5061 は、パブリック IM プロバイダーの連絡先が Lync クライアントに接続する機能、または Lync がパブリック IM 連絡先に連絡することができるようにするための、双方向です。

Windows Live Messenger は、Lync クライアントとの音声/ビデオ通信に参加できます。 このアカウントは、通常、外部ユーザーとして Lync クライアントをサポートするためにファイアウォールを使用するのとよく似ています。

<div>


> [!IMPORTANT]
> Lync は、組織間や世界中の個人と接続するための強力なツールです。 Windows Live Messenger とのフェデレーションでは、Lync Standard クライアントアクセスライセンス (CAL) を超える追加のユーザー/デバイスライセンスは必要ありません。 Skype フェデレーションがこの一覧に追加され、Lync ユーザーが IM と音声を使用して数百人のユーザーにアクセスできるようになります。<BR>Messenger クライアントの連絡先とのフェデレーションは、2013年3月15日に正式に終了します。ただし、中国では、ポルトガルが終了しています。 Skype は、既にメッセンジャーを使用していたフェデレーションユーザーのフェデレーションクライアントになります。



</div>

エッジサーバーに展開されている拡張メッセージングおよびプレゼンスプロトコル (XMPP) プロキシに対して定義されているポートとプロトコルは、XMPP フェデレーションパートナーからエッジサーバーへの通信を許可すると共に、エッジサーバーから XMPP フェデレーションパートナーへの通信を許可します。 ルールは、フロントエンドサーバーまたはフロントエンドプールからエッジサーバーまたはエッジプールへの内部接続ファイアウォール上にも定義されています。

<div>

## <a name="firewall-summary---sip-federation"></a>ファイアウォールの概要-SIP フェデレーション


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>役割/プロトコル/TCP または UDP/ポート</th>
<th>送信元 IP アドレス</th>
<th>宛先 IP アドレス</th>
<th>Notes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>アクセス/SIP (MTLS)/TCP/5061</p></td>
<td><p>アクセス エッジ サービス パブリック IP アドレス</p></td>
<td><p>任意</p></td>
<td><p>SIP を使用したフェデレーションおよびパブリック IM 接続用</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a>ファイアウォールの概要 ‐ パブリック インスタント メッセージング接続


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>役割/プロトコル/TCP または UDP/ポート</th>
<th>送信元 IP アドレス</th>
<th>宛先 IP アドレス</th>
<th>Notes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>アクセス/SIP (MTLS)/TCP/5061</p></td>
<td><p>パブリック IM 接続パートナー</p></td>
<td><p>エッジサーバーアクセスインターフェイス</p></td>
<td><p>フェデレーションとパブリック IM 接続の場合、SIP を使用します。</p></td>
</tr>
<tr class="even">
<td><p>アクセス/SIP (MTLS)/TCP/5061</p></td>
<td><p>エッジサーバーアクセスインターフェイス</p></td>
<td><p>パブリック IM 接続パートナー</p></td>
<td><p>フェデレーションとパブリック IM 接続の場合、SIP を使用します。</p></td>
</tr>
<tr class="odd">
<td><p>アクセス/SIP (TLS)/TCP/443</p></td>
<td><p>クライアント</p></td>
<td><p>エッジサーバーアクセスインターフェイス</p></td>
<td><p>外部ユーザーアクセス用のクライアントからサーバーへの SIP トラフィック。</p></td>
</tr>
<tr class="even">
<td><p>音声/V/RTP/TCP/50,000-59999</p></td>
<td><p>エッジサーバーアクセスインターフェイス</p></td>
<td><p>Live Messenger クライアント</p></td>
<td><p>パブリック IM 接続が構成されている場合に、Windows Live Messenger との音声ビデオ セッションに使用されます。</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN、MSTURN/UDP/3478</p></td>
<td><p>エッジサーバーアクセスインターフェイス</p></td>
<td><p>Live Messenger クライアント</p></td>
<td><p>Windows Live Messenger とのパブリック IM 接続に必要です。</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN、MSTURN/UDP/3478</p></td>
<td><p>Live Messenger クライアント</p></td>
<td><p>エッジサーバーアクセスインターフェイス</p></td>
<td><p>Windows Live Messenger とのパブリック IM 接続に必要です。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary---extensible-messaging-and-presence-protocol-xmpp"></a>ファイアウォールの概要-拡張可能なメッセージングとプレゼンスプロトコル (XMPP)


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>プロトコル/TCP または UDP/ポート</th>
<th>送信元 (IP アドレス)</th>
<th>宛先 (IP アドレス)</th>
<th>Comments</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/TCP/5269</p></td>
<td><p>任意</p></td>
<td><p>アクセスエッジサービスインターフェイスの IP アドレス</p></td>
<td><p>XMPP 用の標準的なサーバー間通信。 フェデレーションされた XMPP パートナーからのエッジサーバー XMPP プロキシへの通信を許可します。</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>アクセスエッジサービスインターフェイスの IP アドレス</p></td>
<td><p>任意</p></td>
<td><p>XMPP 用の標準的なサーバー間通信。 エッジサーバー XMPP プロキシからフェデレーションされた XMPP パートナーへの通信を許可します。</p></td>
</tr>
<tr class="odd">
<td><p>XMPP/MTLS/23456</p></td>
<td><p>任意</p></td>
<td><p>内部エッジサーバーインターフェイス IP</p></td>
<td><p>フロントエンドサーバーまたはフロントエンドプールの XMPP ゲートウェイからエッジサーバーへの内部 XMPP トラフィック</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での外部ユーザーアクセスのシナリオ](lync-server-2013-scenarios-for-external-user-access.md)  
[Lync Server 2013 の外部の音声ビデオファイアウォールおよびポートの要件を決定する](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  


[Lync Server 2013 での XMPP フェデレーションパートナーの管理](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

