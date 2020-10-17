---
title: 'Lync Server 2013: IP アドレスの種類の概要'
description: 'Lync Server 2013: IP アドレスの種類の概要。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of IP address types for Lync Server
ms:assetid: ee9a695f-5cf5-441e-94fb-6adeca50e8d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205363(v=OCS.15)
ms:contentKeyID: 48185759
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 81492b2e006a6f44f6deb78e6a0560f6e319992f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559223"
---
# <a name="overview-of-ip-address-types-for-lync-server-2013"></a>Lync Server 2013 の IP アドレスの種類の概要

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-01-29_

Lync Server 2013 で IP アドレスを構成する場合、3つのオプションがあります。 Lync Server 2013 は、IP バージョン 4 (IPv4)、IP バージョン 6 (IPv6) のみ、または両方の組み合わせ ( *デュアルスタック*とも呼ばれます) をサポートするように構成できます。 各構成には、いくつか考慮すべき問題があります。

  - **IPv4 のみ**    世界で IPv4 アドレスが不足しているため、IPv6 が作成されました。 最終的には、IPv6 は完全にサポートされていますが、現時点では、企業が通信する必要がある多くの企業やデバイスが IPv6 をサポートしていない場合があります。 IPv4 のみの構成は、Lync Server の実装が、ほとんどの既存のデバイスと通信できるようにするのに役立ちます。

  - **IPv6 のみ**    反対に、完全な IPv6 実装では、この時点で、多くの既存のデバイスとの通信が除外されます。

  - **デュアルスタック**    デュアルスタックは、IPv4 と IPv6 の両方のアドレスが有効になっているネットワークです。 この構成は、Lync Server 2013 でサポートされています。ほとんどの場合、フル-IPv4 からフル-IPv6 への移行は数年かかります。

次のセクションでは、Lync Server のさまざまな機能について、これらの3つの構成の互換性について概説します。

<div>


> [!NOTE]  
> クライアントまたはサーバーを IPv6 のみの構成にすることは、試験や検証の目的でのみサポートされています。IPv6 のみの構成は運用展開ではサポートされていません。



</div>

<div>

## <a name="client-registration"></a>クライアントの登録


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>クライアント エンドポイント ネットワーク</th>
<th>サーバー ネットワーク</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IPv4</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>IPv4</p></td>
<td><p>デュアル スタック</p></td>
</tr>
<tr class="odd">
<td><p>デュアル スタック</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>デュアル スタック</p></td>
<td><p>デュアル スタック</p></td>
</tr>
<tr class="odd">
<td><p>デュアル スタック</p></td>
<td><p>IPv6</p></td>
</tr>
<tr class="even">
<td><p>IPv6</p></td>
<td><p>デュアル スタック</p></td>
</tr>
<tr class="odd">
<td><p>IPv6</p></td>
<td><p>IPv6</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="peer-to-peer-client"></a>ピアツーピア クライアント

ピアツーピア通信には、オーディオ、音声ビデオ、アプリケーション共有、ファイル転送などがあります。両方のクライアントが正常に登録された後、次の組み合わせがサポートされます。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>クライアント エンドポイント 1</th>
<th>クライアント エンドポイント 2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IPv4</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>IPv4</p></td>
<td><p>デュアル スタック</p></td>
</tr>
<tr class="odd">
<td><p>デュアル スタック</p></td>
<td><p>デュアル スタック</p></td>
</tr>
<tr class="even">
<td><p>IPv6</p></td>
<td><p>デュアル スタック</p></td>
</tr>
<tr class="odd">
<td><p>IPv6</p></td>
<td><p>IPv6</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="conferencing"></a>会議

会議には、音声ビデオ、アプリケーション共有、およびデータ コラボレーション (ホワイト ボードとファイル共有) が含まれます。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>クライアント エンドポイント ネットワーク</th>
<th>サーバー ネットワーク</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IPv4</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>IPv4</p></td>
<td><p>デュアル スタック</p></td>
</tr>
<tr class="odd">
<td><p>デュアル スタック</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>デュアル スタック</p></td>
<td><p>デュアル スタック</p></td>
</tr>
<tr class="odd">
<td><p>デュアル スタック</p></td>
<td><p>IPv6</p></td>
</tr>
<tr class="even">
<td><p>IPv6</p></td>
<td><p>デュアル スタック</p></td>
</tr>
<tr class="odd">
<td><p>IPv6</p></td>
<td><p>IPv6</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="mediation-serverpstn"></a>仲介サーバー/PSTN

Lync Server 2013 は、トラフィックが IPv6 インターフェイスを経由している場合は、公衆交換電話網 (PSTN) 通話のメディアバイパスをサポートしていません。 メディア バイパスが必要な場合は、PSTN ゲートウェイを IPv4 に構成することをお勧めします。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>プライマリ インターフェイス*</th>
<th>PSTN インターフェイス (仲介サーバー上)</th>
<th>PSTN ゲートウェイの設定</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IPv4</p></td>
<td><p>デュアル スタック</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>デュアル スタック</p></td>
<td><p>デュアル スタック</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="odd">
<td><p>デュアル スタック</p></td>
<td><p>デュアル スタック</p></td>
<td><p>IPv6</p></td>
</tr>
</tbody>
</table>


\* プライマリインターフェイスは、Lync Server コンポーネントと通信するインターフェイスです。

</div>

<div>

## <a name="remote-user-peer-to-peer-communications"></a>リモート ユーザーのピアツーピア通信

リモート ユーザーとのピアツーピア通信には、インスタント メッセージング、音声ビデオ、アプリケーション共有、およびファイル転送が含まれます。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>リモート ユーザー ネットワーク</th>
<th>エッジ サーバー (外部エッジ)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IPv4</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>デュアル スタック</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="odd">
<td><p>デュアル スタック</p></td>
<td><p>デュアル スタック</p></td>
</tr>
<tr class="even">
<td><p>IPv6</p></td>
<td><p>デュアル スタック</p></td>
</tr>
<tr class="odd">
<td><p>IPv6</p></td>
<td><p>IPv6</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-pool-and-edge-pool-configuration"></a>フロントエンド プールとエッジ プールの構成

次の表は、フロントエンドサーバープールと内部エッジサーバープールの間のサポートマトリックスを示しています。

### <a name="front-end-pool-and-edge-pool-internal-edge-matrix"></a>フロントエンド プールとエッジ プール (内部エッジ) のマトリックス

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
<td><p><strong>エッジ プール: IPv4</strong></p></td>
<td><p><strong>エッジ プール: デュアル スタック</strong></p></td>
<td><p><strong>エッジ プール: IPv6</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>フロントエンド プール: IPv4</strong></p></td>
<td><p>はい</p></td>
<td><p>必要</p></td>
<td><p>いいえ</p></td>
</tr>
<tr class="odd">
<td><p><strong>フロントエンド プール: デュアル スタック</strong></p></td>
<td><p>はい</p></td>
<td><p>必要</p></td>
<td><p>いいえ</p></td>
</tr>
<tr class="even">
<td><p><strong>フロントエンド プール: IPv6</strong></p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>はい*</p></td>
</tr>
</tbody>
</table>


\* この組み合わせは、ラボ環境でのみ使用します。

次のテーブルは、内部エッジ インターフェイスと外部エッジ インターフェイスの組み合わせのサポート マトリックスです。

### <a name="edge-pool-internal-edge-and-edge-pool-external-edge-matrix"></a>エッジ プール (内部エッジ) とエッジ プール (外部エッジ) のマトリックス

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
<td><p><strong>エッジ プール (外部エッジ): IPv4</strong></p></td>
<td><p><strong>エッジ プール (外部エッジ): デュアル スタック</strong></p></td>
<td><p><strong>エッジ プール (外部エッジ): IPv6</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>エッジ プール (内部エッジ): IPv4</strong></p></td>
<td><p>はい</p></td>
<td><p>必要</p></td>
<td><p>いいえ</p></td>
</tr>
<tr class="odd">
<td><p><strong>エッジ プール (内部エッジ): デュアル スタック</strong></p></td>
<td><p>いいえ</p></td>
<td><p>はい</p></td>
<td><p>いいえ</p></td>
</tr>
<tr class="even">
<td><p><strong>エッジ プール (内部エッジ): IPv6</strong></p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>はい*</p></td>
</tr>
</tbody>
</table>


\* この組み合わせは、ラボ環境でのみ使用します。

</div>

<div>

## <a name="advanced-enterprise-voice-support-for-ipv6"></a>IPv6 の高度なエンタープライズ VoIP のサポート

通話受付管理 (CAC)、拡張 9-1-1 (E9-1-1)、メディア バイパスなどの展開は、IPv4 のみ、またはデュアル スタック実装として構成する必要があります。

<div>


> [!NOTE]  
> デュアルスタック展開では、lync クライアントが IPv6 を使用して Lync サーバーに接続している場合でも、Lync は E9-1-1 をサポートするために適切な IPv4 アドレスをマップするための最善の努力を行います。



</div>

IPv6 アドレスを使用した場所情報サービスはサポートされていません。

Exchange ユニファイド メッセージング (UM) では IPv6 をサポートしていません。Exchange UM の場合は、DNS 解決が IPv6 アドレスを返さないことを確認します。IPv6 を使用すると、通話がボイス メールに送信されたときに障害が発生する可能性があります。

</div>

<div>

## <a name="other-lync-server-2013-feature-support-for-ipv6"></a>その他の Lync Server 2013 機能の IPv6 のサポート

以前に説明した機能とコンポーネントに加えて、Lync Server 2013 は次の機能に対して IPv6 をサポートしています。

  - **常設チャット**
    
    常設チャットには、トポロジビルダーを使用して IPv6 を構成します。 常設チャットの構成の詳細については、「常設チャットサーバーのドキュメントを展開する」を参照してください。

  - **Quality of Experience (QoE) と通話詳細記録 (CDR) のレポート**
    
    IPv4 か IPv6 かにかかわらず、監視レポートには監視サーバー データベースに格納されている IP アドレスがそのまま含まれます。

</div>

</div>

<span> </span>

</div>

</div>

</div>

