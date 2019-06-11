---
title: 'Lync Server 2013: 外部の音声ビデオ ファイアウォールおよびポートの要件を決定する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Determine external A/V firewall and port requirements
ms:assetid: 3b849dc7-175d-40d1-820d-80e6ade6d332
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425882(v=OCS.15)
ms:contentKeyID: 48183872
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b278c60eaca69fd17508d0e82198a002484ce586
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833446"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="determine-external-av-firewall-and-port-requirements-for-lync-server-2013"></a>Lync Server 2013 の外部の音声ビデオ ファイアウォールおよびポートの要件を決定する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-29_

音声/ビデオ (A/V) 通信は複雑な場合があります。 A/V で使用されるプロトコルの性質、およびクライアントとサーバーでのプロトコルの使用方法については、クライアントとサーバーのバージョンの違いを説明するための特別なセクションが保証されています。

ファイアウォール要件と開くポートを決定するには、次の A/V ファイアウォールとポートテーブルを使用します。 次に、NAT がさまざまな方法で実装されるため、ネットワークアドレス変換 (NAT) 用語を確認します。 ファイアウォールポート設定の詳細な例については、「 [Lync Server 2013 での外部ユーザーアクセスのシナリオ](lync-server-2013-scenarios-for-external-user-access.md)でのリファレンスアーキテクチャ」を参照してください。

### <a name="general-protocol-usage-for-udp-and-tcp-in-audiovideo-and-media-traffic"></a>音声/ビデオおよびメディアトラフィックでの UDP および TCP の一般的なプロトコルの使用

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>音声/ビデオトランスポート</th>
<th>用途</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>UDP</p></td>
<td><p>オーディオおよびビデオの優先トランスポート層プロトコル</p></td>
</tr>
<tr class="even">
<td><p>TCP</p></td>
<td><p>オーディオおよびビデオのフォールバックトランスポート層プロトコル</p>
<p>Office Communications Server 2007 R2、Lync Server 2010、Lync Server 2013 へのアプリケーション共有に必要なトランスポートレイヤープロトコル</p>
<p>Lync Server 2010 および Lync Server 2013 へのファイル転送に必要なトランスポートレイヤープロトコル</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="external-av-firewall-port-requirements-for-external-user-access"></a>外部ユーザーアクセスの外部の A/V ファイアウォールポートの要件

クライアントのバージョンやフェデレーションパートナーのバージョンに関係なく、外部 (および内部) SIP と会議インターフェイスのファイアウォールポート要件は一貫しています。

オーディオ/ビデオエッジの外部インターフェイスには、同じことが当てはまりません。 Office Communications Server 2007 とのフェデレーションの場合、A/V Edge サービスでは、外部ファイアウォールルールによって、5万 ~ 59999 ポート範囲内の RTP/TCP トラフィックと RTP/UDP トラフィックが両方の方向に流れるようにする必要があります。 上記の表では、Lync Server 2013 がプライマリフェデレーションパートナーであり、一覧されている他のフェデレーションパートナーのいずれかと通信するように構成されていることを前提としています。

59,999 の音声/ビデオポート範囲を構成するには、ポート範囲にフェデレーションパートナーへの通信のソースポートが含まれている必要があります。 詳細については、通信がフェデレーションパートナーから開始されることを考慮してください。 59,999 範囲の A/V Edge サービスポートからの通信は、パートナーの A/V Edge サービスの予期されるポート TCP 443 に接続します。 反対に、A/V Edge サービス443ポートへの受信トラフィックは、59,999 の範囲のソースポートを持ちます。

ファイアウォール管理用のさまざまなファイアウォールとポリシーには、構成するためのターゲットルールのみを設定するか、またはソースとターゲットの両方を設定する必要があります。 目的が宛先ポート専用の場合は、オーディオ/ビデオの要件は次のとおりです。


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
<th>送信先ポート</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>A/V Edge サービスインターフェイス</p></td>
<td><p>任意</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>A/V Edge サービスインターフェイス</p></td>
<td><p>任意</p></td>
<td><p>UDP 3478</p></td>
</tr>
<tr class="odd">
<td><p>任意</p></td>
<td><p>A/V Edge サービスインターフェイス</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>任意</p></td>
<td><p>A/V Edge サービスインターフェイス</p></td>
<td><p>UDP 3478</p></td>
</tr>
</tbody>
</table>


ポリシーで受信と送信の両方のファイアウォール規則の定義が必要な場合、音声/ビデオの要件は次のとおりです。


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
<th>発信元ポート</th>
<th>送信先ポート</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>A/V Edge サービスインターフェイス</p></td>
<td><p>任意</p></td>
<td><p>TCP 50,000 ～ 59,999</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>A/V Edge サービスインターフェイス</p></td>
<td><p>任意</p></td>
<td><p>UDP 3478</p></td>
<td><p>UDP 3478</p></td>
</tr>
<tr class="odd">
<td><p>任意</p></td>
<td><p>A/V Edge サービスインターフェイス</p></td>
<td><p>任意</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>任意</p></td>
<td><p>A/V Edge サービスインターフェイス</p></td>
<td><p>任意</p></td>
<td><p>UDP 3478</p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> Microsoft Office Communications Server 2007 では、若干異なる構成が必要です。 59,999 の TCP ポート範囲と UDP ポート範囲は、受信と送信が開いている必要があります。 この要件は、Office Communicator 2007 に限定されます。 Office Communications Server 2007 R2、Lync Server 2010、Lync Server 2013 には、TCP 範囲 50000-59,999 open outbound が必要です。



</div>

</div>

<div>

## <a name="nat-requirements-for-the-edge-service"></a>エッジサービスの NAT 要件

エッジサービスに対してルーティングできないプライベート IP アドレスを構成する場合は、次の NAT 要件が適用されます。

  - NAT は、DNS の負荷分散でのみ使用できます。 NAT は、ハードウェア負荷分散 (HLB) エッジトポロジではサポートされていません。

  - NAT は、外部 Edge インターフェイスでのみ使うことができます。 NAT は、内部エッジインターフェイスではサポートされていません。

  - NAT は、受信トラフィックと発信トラフィックに対称である必要があります。
    
  - インターネットからのトラフィックの場合、NAT は、宛先の IP アドレスを、A/V Edge サービスの NAT 対応のパブリック IP アドレスから外部 IP アドレスに変更する必要があります。 ソース IP アドレスはそのままにしておく必要があります。そのため、A/V Edge サービスは最適なメディアパスを見つけることができます。
  
  たとえば、次の図の受信方向では、パブリック IP アドレスの131.107.155.30 が外部 (プライベート) IP アドレス10.45.16.10 に変更されました。 ソース IP アドレスは変更されていません。
  
  - NAT では、A/v Edge サービスからインターネットへのトラフィックについて、ソース IP アドレスを、A/V Edge サービスの外部 IP アドレスから NAT 対応のパブリック IP アドレスに変更する必要があります。

たとえば、次の図のような送信方向の場合、外部 (プライベート) IP アドレス10.45.16.10 はパブリック IP アドレス131.107.155.30 に変更されました。

**次の図は、NAT で受信トラフィックの送信先 IP アドレスと送信トラフィックのソース IP アドレスを変更する方法を示しています。**

![送信先/ソース IP アドレスを変更する](images/Gg425882.0fee7ec5-4cb8-4aff-9164-e7fbab73336d(OCS.15).jpg "送信先/ソース IP アドレスを変更する")

重要なポイントは次のとおりです。

  - A/V Edge サービスを実行しているサーバーへのトラフィックは、ソース IP アドレスは変更されませんが、宛先 IP アドレスは131.107.155.30 から10.45.16.10 の変換済み IP アドレスに変わります。

  - A/V Edge サービスを実行しているサーバーからワークステーションに送信されるトラフィックについては、ソース IP アドレスがサーバーのパブリック IP アドレスから、A/V Edge サービスを実行しているサーバーのパブリック IP アドレスに変わります。 送信先 IP は、ワークステーションのパブリック IP アドレスのままです。 パケットが最初の NAT デバイスから送信されると、NAT デバイス上のルールによって、A/V Edge サービスの外部インターフェイス IP アドレス (10.45.16.10) を実行しているサーバーのソース IP アドレスが、そのパブリック IP アドレス (131.107.155.30) に変更されます。

</div>

</div>

<span> </span>

</div>

</div>

</div>

