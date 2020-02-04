---
title: ポートの概要-SIP、XMPP フェデレーション、パブリックインスタントメッセージ
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
ms.openlocfilehash: 3ae19fb2477f61c0e408ebad3a8abf97fb75b9c4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747467"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>[ポートの概要]-Lync Server 2013 での SIP、XMPP フェデレーション、およびパブリックインスタントメッセージング

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-03-15_

Microsoft Lync Server 2013、Lync Server 2010、および Office Communications Server とのフェデレーションのためのポート、プロトコル、ファイアウォールの要件は、展開されたエッジサーバーの場合と似ています。 クライアントは、TLS/SIP/TCP 443 経由でアクセスエッジサービスとの通信を開始します。 ただし、フェデレーションパートナーは、MTLS/SIP/TCP 5061 経由でアクセスエッジサービスへの通信を開始します。

パブリックインスタントメッセージング接続をサポートするために必要なポートとプロトコル用にファイアウォールを構成するには、まず、SIP/MTLS/TCP 5061 は、パブリック IM プロバイダーの連絡先が Lync クライアントに連絡するか、Lync がパブリック IM の連絡先に連絡できるかどうかを考慮するための双方向です。

Windows Live Messenger は、Lync クライアントとの音声/ビデオ通信に参加できます。 通常、ファイアウォールを使用して、外部ユーザーとして Lync クライアントをサポートする、非常に類似したファイアウォールポートおよびプロトコル構成については、このアカウントをご利用ください。

<div>


> [!IMPORTANT]
> Lync は、組織間、および世界各地の個人と接続するための強力なツールです。 Windows Live Messenger とのフェデレーションには、Lync Standard クライアントアクセスライセンス (CAL) を超える追加のユーザー/デバイスライセンスは必要ありません。 Skype federation はこのリストに追加されます。 Lync ユーザーは、IM と音声を使用して、数百人の何百万ものユーザーに連絡できます。<BR>Messenger クライアント連絡先とのフェデレーションは、2013年3月15日に正式に終了します。中国とは異なります。 Skype は、以前に Messenger を使用したフェデレーションユーザーのフェデレーションクライアントになります。



</div>

エッジサーバーに展開された拡張メッセージングとプレゼンスプロトコル (XMPP) プロキシ用に定義されたポートとプロトコルを使うと、XMPP フェデレーションパートナーからエッジサーバーへの通信が可能になり、エッジサーバーから XMPP への通信も可能になります。フェデレーションパートナー。 フロントエンドサーバーまたはフロントエンドプールからエッジサーバーまたはエッジプールへのルールも定義されています。

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
<th>Role/Protocol/TCP または UDP/ポート</th>
<th>送信元 IP アドレス</th>
<th>宛先 IP アドレス</th>
<th>メモ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>アクセス/SIP (MTLS)/TCP/5061</p></td>
<td><p>アクセスエッジサービスのパブリック IP アドレス</p></td>
<td><p>任意</p></td>
<td><p>SIP を使用するフェデレーションおよびパブリック IM 接続の場合</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a>ファイアウォールの概要–パブリックインスタントメッセージング接続


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Role/Protocol/TCP または UDP/ポート</th>
<th>送信元 IP アドレス</th>
<th>宛先 IP アドレス</th>
<th>メモ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>アクセス/SIP (MTLS)/TCP/5061</p></td>
<td><p>パブリック IM 接続パートナー</p></td>
<td><p>エッジサーバーアクセスインターフェイス</p></td>
<td><p>SIP を使うフェデレーションおよびパブリック IM 接続の場合。</p></td>
</tr>
<tr class="even">
<td><p>アクセス/SIP (MTLS)/TCP/5061</p></td>
<td><p>エッジサーバーアクセスインターフェイス</p></td>
<td><p>パブリック IM 接続パートナー</p></td>
<td><p>SIP を使うフェデレーションおよびパブリック IM 接続の場合。</p></td>
</tr>
<tr class="odd">
<td><p>アクセス/SIP (TLS)/TCP/443</p></td>
<td><p>クライアント</p></td>
<td><p>エッジサーバーアクセスインターフェイス</p></td>
<td><p>外部ユーザー アクセス用のクライアントからサーバーへの SIP トラフィック</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/59,999</p></td>
<td><p>エッジサーバーアクセスインターフェイス</p></td>
<td><p>Live Messenger クライアント</p></td>
<td><p>パブリック IM 接続が構成されている場合、Windows Live Messenger でのセッションに使用されます。</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN、MSTURN/UDP/3478</p></td>
<td><p>エッジサーバーアクセスインターフェイス</p></td>
<td><p>Live Messenger クライアント</p></td>
<td><p>Windows Live Messenger とのパブリック IM 接続に必要。</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN、MSTURN/UDP/3478</p></td>
<td><p>Live Messenger クライアント</p></td>
<td><p>エッジサーバーアクセスインターフェイス</p></td>
<td><p>Windows Live Messenger とのパブリック IM 接続に必要。</p></td>
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
<th>Protocol/TCP または UDP/ポート</th>
<th>ソース (IP アドレス)</th>
<th>宛先 (IP アドレス)</th>
<th>コメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/TCP/5269</p></td>
<td><p>任意</p></td>
<td><p>Access Edge サービスインターフェイスの IP アドレス</p></td>
<td><p>XMPP 向けの標準的なサーバー間通信ポート。 フェデレーションされた XMPP パートナーからエッジサーバーの XMPP プロキシへの通信を許可します。</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>Access Edge サービスインターフェイスの IP アドレス</p></td>
<td><p>任意</p></td>
<td><p>XMPP 向けの標準的なサーバー間通信ポート。 エッジサーバーの XMPP プロキシからフェデレーションされた XMPP パートナーへの通信を許可します。</p></td>
</tr>
<tr class="odd">
<td><p>XMPP/MTLS/23456</p></td>
<td><p>任意</p></td>
<td><p>内部エッジサーバーインターフェイス IP</p></td>
<td><p>フロントエンドサーバーまたはフロントエンドプールの XMPP ゲートウェイからエッジサーバーへの内部の XMPP トラフィック</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 の外部ユーザー アクセスのシナリオ](lync-server-2013-scenarios-for-external-user-access.md)  
[Lync Server 2013 の外部の音声ビデオ ファイアウォールおよびポートの要件を決定する](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  


[Lync Server 2013 での組織の XMPP フェデレーション パートナーの管理](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

