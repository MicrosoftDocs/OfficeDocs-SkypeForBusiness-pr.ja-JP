---
title: 'Lync Server 2013: 外部の音声ビデオファイアウォールおよびポートの要件を決定する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Determine external A/V firewall and port requirements
ms:assetid: 3b849dc7-175d-40d1-820d-80e6ade6d332
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425882(v=OCS.15)
ms:contentKeyID: 48183872
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c7b117f68719230151fd19050dbb080f6acde14
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522584"
---
# <a name="determine-external-av-firewall-and-port-requirements-for-lync-server-2013"></a>Lync Server 2013 の外部の音声ビデオファイアウォールおよびポートの要件を決定する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-29_

音声ビデオ (A/V) 通信は複雑な場合があります。 A/V で使用されるプロトコルの性質と、クライアントとサーバーのプロトコルの使用方法によって、クライアントとサーバーのバージョンの違いについて説明する特別なセクションが保証されています。

次の A/V ファイアウォールとポートの表を使用して、ファイアウォール要件と開くポートを決定します。 次に、NAT をさまざまな方法で実装できるため、ネットワークアドレス変換 (NAT) 用語を確認します。 ファイアウォールポート設定の詳細な例については、「 [Lync Server 2013 の外部ユーザーアクセスのシナリオ](lync-server-2013-scenarios-for-external-user-access.md)」の参照アーキテクチャを参照してください。

### <a name="general-protocol-usage-for-udp-and-tcp-in-audiovideo-and-media-traffic"></a>音声ビデオおよびメディアトラフィックでの UDP および TCP の一般的なプロトコル使用法

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>音声ビデオトランスポート</th>
<th>使用方法</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>受信</p></td>
<td><p>オーディオとビデオの優先トランスポート層プロトコル</p></td>
</tr>
<tr class="even">
<td><p>TCP</p></td>
<td><p>オーディオおよびビデオのフォールバックトランスポート層プロトコル</p>
<p>Office Communications Server 2007 R2、Lync Server 2010、Lync Server 2013 へのアプリケーション共有に必要なトランスポート層プロトコル</p>
<p>Lync Server 2010 および Lync Server 2013 へのファイル転送に必要なトランスポート層プロトコル</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="external-av-firewall-port-requirements-for-external-user-access"></a>外部ユーザー アクセス用の外部の音声ビデオ ファイアウォール ポートの要件

外部 (および内部) SIP と会議インターフェイスのファイアウォールポート要件は、クライアントのバージョンやフェデレーションパートナーのバージョンに関係なく一貫しています。

音声ビデオ エッジの外部インターフェイスの場合は、そうではありません。 Office Communications Server 2007 とのフェデレーションの場合、音声ビデオエッジサービスでは、外部ファイアウォールの規則によって、5万 ~ 59999 のポート範囲にある RTP/TCP トラフィックと RTP/UDP トラフィックが双方向に流れることが要求されます。 前の表では、Lync Server 2013 がプライマリフェデレーションパートナーであり、リストされている他のフェデレーションパートナーの種類のいずれかと通信するように構成されていることを前提としています。

59999の音声/ビデオポート範囲を構成するには、ポート範囲にフェデレーションパートナーと通信するための送信元ポートが含まれる必要があることを考慮する必要があります。 詳細については、フェデレーションパートナーからの通信が開始されることを考慮してください。 59999の範囲内の音声ビデオエッジサービスポートからの通信は、パートナーの音声ビデオエッジサービスの TCP 443 の予想ポートに接続します。 反対に、音声ビデオエッジサービスポート TCP 443 への受信トラフィックには、59999の範囲の送信元ポートがあります。

ファイアウォール管理のためのファイアウォールとポリシーによっては、構成する必要があるのは宛先のルールだけであるか、またはソースと宛先の両方を構成する必要がある場合があります。 宛先ポートのみの要件の場合は、音声ビデオの要件は次のとおりです。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>発信元 IP アドレス</th>
<th>送信先 IP アドレス</th>
<th>宛先ポート</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>音声ビデオエッジサービスインターフェイス</p></td>
<td><p>任意</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>音声ビデオエッジサービスインターフェイス</p></td>
<td><p>任意</p></td>
<td><p>UDP 3478</p></td>
</tr>
<tr class="odd">
<td><p>任意</p></td>
<td><p>音声ビデオエッジサービスインターフェイス</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>任意</p></td>
<td><p>音声ビデオエッジサービスインターフェイス</p></td>
<td><p>UDP 3478</p></td>
</tr>
</tbody>
</table>


ポリシーで受信と送信の両方のファイアウォールルール定義が必要な場合、音声/ビデオの要件は次のとおりです。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>発信元 IP アドレス</th>
<th>送信先 IP アドレス</th>
<th>送信元ポート</th>
<th>宛先ポート</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>音声ビデオエッジサービスインターフェイス</p></td>
<td><p>任意</p></td>
<td><p>TCP 50000-59999</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>音声ビデオエッジサービスインターフェイス</p></td>
<td><p>任意</p></td>
<td><p>UDP 3478</p></td>
<td><p>UDP 3478</p></td>
</tr>
<tr class="odd">
<td><p>任意</p></td>
<td><p>音声ビデオエッジサービスインターフェイス</p></td>
<td><p>任意</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>任意</p></td>
<td><p>音声ビデオエッジサービスインターフェイス</p></td>
<td><p>任意</p></td>
<td><p>UDP 3478</p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> Microsoft Office Communications Server 2007 には、若干異なる構成が必要です。 59999の TCP および UDP ポート範囲は、受信および送信を開いている必要があります。 この要件は、Office Communicator 2007 に対してのみ必要です。 Office Communications Server 2007 R2、Lync Server 2010、Lync Server 2013 には、TCP 範囲 50000-59999 open outbound のみが必要です。



</div>

</div>

<div>

## <a name="nat-requirements-for-the-edge-service"></a>エッジサービスの NAT 要件

エッジサービスに対してルーティング不能なプライベート IP アドレスを構成する場合は、次の NAT 要件を適用します。

  - NAT は、DNS 負荷分散でのみ使用できます。 NAT は、ハードウェア負荷分散 (HLB) エッジトポロジではサポートされていません。

  - NAT は、外部エッジインターフェイスでのみ使用できます。 NAT は、内部エッジインターフェイスではサポートされていません。

  - NAT は、受信および送信トラフィック用に対称でなければなりません。
    
  - インターネットからのトラフィックの場合、NAT は、音声ビデオエッジサービスの NAT が有効なパブリック IP アドレスから、外部 IP アドレスに宛先 IP アドレスを変更する必要があります。 音声ビデオエッジサービスが最適なメディアパスを見つけることができるように、送信元 IP アドレスは変更されないままにしておく必要があります。
  
  たとえば、次の図の受信方向では、パブリック IP アドレス 131.107.155.30) が外部 (プライベート) IP アドレス10.45.16.10 というに変更されました。 送信元 IP アドレスは変更されていません。
  
  - 音声ビデオエッジサービスからインターネットへのトラフィックの場合、NAT は、音声ビデオエッジサービスの外部 IP アドレスから NAT が有効なパブリック IP アドレスへの送信元 IP アドレスを変更する必要があります。

たとえば、次の図の送信方向では、外部 (プライベート) IP アドレス10.45.16.10 というがパブリック IP アドレス 131.107.155.30) に変更されました。

**次の図は、NAT が受信トラフィックの宛先 IP アドレスと送信トラフィックの送信元 IP アドレスを変更する方法を示しています。**

![宛先/送信元 IP アドレスの変更](images/Gg425882.0fee7ec5-4cb8-4aff-9164-e7fbab73336d(OCS.15).jpg "宛先/送信元 IP アドレスの変更")

主な点は次のとおりです。

  - 音声ビデオエッジサービスを実行しているサーバーが受信するトラフィックは、送信元 IP アドレスは変更されませんが、宛先 IP アドレスは 131.107.155.30) から10.45.16.10 というの変換された IP アドレスに変更されます。

  - 音声ビデオエッジサービスを実行しているサーバーからワークステーションに送信されるトラフィックは、送信元 IP アドレスがサーバーのパブリック IP アドレスから、音声ビデオエッジサービスを実行しているサーバーのパブリック IP アドレスに変更されます。 宛先 IP はワークステーションのパブリック IP アドレスのままです。 パケットが最初の NAT デバイスを送信した後、NAT デバイス上のルールは、音声ビデオエッジサービスの外部インターフェイスの IP アドレス (10.45.16.10 という) を実行しているサーバーの送信元 IP アドレスをパブリック IP アドレス (131.107.155.30)) に変更します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

