---
title: DNS の概要-拡張統合エッジ (ロードバランサー機器を使用)
description: DNS の概要-拡張統合エッジ (ロードバランサー機器を使用)。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Scaled consolidated edge with hardware load balancers
ms:assetid: 8453297c-da1d-4b9e-a37e-6721458c6feb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398670(v=OCS.15)
ms:contentKeyID: 48184700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59581f435267a7db607e03a8cbf52d21f70897f8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570663"
---
# <a name="dns-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a>DNS の概要-Lync Server 2013 でのハードウェアロードバランサーを使用した拡張統合エッジ

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-01-27_

Lync Server 2013 へのリモートアクセスの DNS レコードの要件は、証明書とポートの場合と比べて非常に簡単です。 また、Lync 2013 を実行しているクライアントを構成する方法と、フェデレーションを有効にするかどうかに応じて、多くのレコードがオプションになります。

Lync 2013 DNS の要件の詳細については、「 [Lync Server 2013 の dns 要件を決定](lync-server-2013-determine-dns-requirements.md)する」を参照してください。

スプリットブレイン DNS が構成されていない場合の Lync 2013 クライアントの自動構成の構成の詳細については、「 [Lync Server 2013 の DNS 要件を決定](lync-server-2013-determine-dns-requirements.md)する」の「スプリットブレイン dns なしの自動構成」セクションを参照してください。

次の表に、拡張統合エッジ トポロジ (ロード バランサー機器) の図をサポートするのに必要な DNS レコードの概要を示します。 特定の DNS レコードは、Lync クライアントの自動構成にのみ必要であることに注意してください。 グループポリシーオブジェクト (Gpo) を使用して Lync クライアントを構成することを計画している場合は、関連付けられたレコードは必要ありません。

<div>

## <a name="important-edge-server-network-adapter-requirements"></a>重要: エッジサーバーのネットワークアダプターの要件

ルーティングに関する問題を回避するには、エッジサーバーに少なくとも2つのネットワークアダプターがあり、既定のゲートウェイが、外部インターフェイスに関連付けられているネットワークアダプター上でのみ設定されていることを確認します。 たとえば、スケール統合エッジシナリオの図のように、「 [拡張統合エッジ」と「ハードウェアロードバランサーを使用する Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)」のように、既定のゲートウェイは外部ファイアウォールを指しています。

各エッジサーバーでは、2つのネットワークアダプターを次のように構成できます。

  - **ネットワーク アダプター 1 (内部インターフェイス)**
    
    172.25.33.10 が割り当てられた内部インターフェイス。
    
    デフォルト ゲートウェイはありません。
    
    エッジサーバーの内部インターフェイスを含むネットワークから、lync server クライアントまたは Lync Server を実行しているサーバー (たとえば、172.25.33.0 から 192.168.10.0) があるネットワークからのルートがあることを確認します。

  - **ネットワーク アダプター 2 (外部インターフェイス)**
    
    このネットワークアダプターには3つのパブリック IP アドレスが割り当てられます。たとえば、アクセスエッジサービスの131.107.155.10、Web 会議エッジサービスの131.107.155.20、音声ビデオエッジサービスの 131.107.155.30)。
    
    <div>
    

    > [!NOTE]
    > エッジサーバーの実際の外部ネットワークインターフェイスに割り当てられる IP アドレスは、選択するハードウェアロードバランサーによって異なる場合があります。 実際の IP アドレス要件については、使用するハードウェアロードバランサーのドキュメントを参照してください。<BR>お勧めはできませんが、3 つのエッジ サービス インターフェイスすべてに 1 つの IP アドレスを使用できます。 これによって IP アドレスを節約できますが、サービスごとに異なるポート番号が必要です。 既定のポート番号は 443/TCP で、リモート ファイアウォールの大部分がトラフィックを許可します。 アクセスエッジサービスのポート値 (たとえば、アクセスエッジサービスの 5061/TCP、Web 会議エッジサービスの 444/tcp、および音声ビデオエッジサービスの 443/TCP) を変更すると、遅延しているファイアウォールが 5061/TCP および 444/TCP 経由のトラフィックを許可しないリモートユーザーに対して問題が発生する可能性があります。 また、3 つの異なる IP アドレスを使用すると、IP アドレスのフィルター処理が可能になるのでトラブルシューティングが容易になります。

    
    </div>
    
    アクセスエッジサービスの IP アドレスは、既定のゲートウェイがインターネットに接続するルーター (131.107.155.1) に設定されているプライマリアドレスです。
    
    Web 会議エッジサービスおよび音声ビデオエッジサービスの IP アドレスセカンダリ。

<div>


> [!TIP]
> 2つのネットワークアダプターを使用してエッジサーバーを構成するには、2つのオプションのいずれかを使用します。 もう1つの方法は、エッジサーバーの内部側と外部側に3つのネットワークアダプターを使用する方法です。 このオプションの主な利点は、エッジサーバーサービスごとに別個のネットワークアダプターがあり、トラブルシューティングを行う際により簡潔なデータ収集を行うことができるということです。



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-hardware-load-balanced-example"></a>拡張統合エッジ (ロード バランサー機器) で必要な DNS レコード (例)

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>場所/種類/ポート</th>
<th>FQDN/DNS レコード</th>
<th>IP アドレス/FQDN</th>
<th>マッピング先/コメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部 DNS/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>131.107.155.10</p></td>
<td><p>アクセスエッジサービスの外部インターフェイス (Contoso)。 すべての SIP ドメインと Lync が有効なユーザーについて必要なだけ繰り返します。</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/A</p></td>
<td><p>webcon.contoso.com</p></td>
<td><p>131.107.155.20</p></td>
<td><p>Web 会議エッジサービスの外部インターフェイス</p></td>
</tr>
<tr class="odd">
<td><p>外部 DNS/A</p></td>
<td><p>av.contoso.com</p></td>
<td><p>131.107.155.30)</p></td>
<td><p>音声ビデオエッジサービスの外部インターフェイス</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/SRV/443</p></td>
<td><p>_sip _sip._tls</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>アクセスエッジサービスの外部インターフェイス。 Lync 2013 および Lync 2010 クライアントを外部で動作するように自動構成するために必要です。 必要に応じて、Lync が有効なユーザーのいるすべての SIP ドメインに対して繰り返します。</p></td>
</tr>
<tr class="odd">
<td><p>外部 DNS/SRV/5061</p></td>
<td><p>_sipfederationtls _sipfederationtls._tcp</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>"許可済み SIP ドメイン" (以前のリリースでは拡張フェデレーションと呼ばれました) と呼ばれるフェデレーションパートナーの自動 DNS 検出に必要な、SIP アクセスエッジサービスの外部インターフェイス。 プッシュ通知サービスまたは Apple プッシュ通知サービスのいずれかを使用する Lync が有効なユーザーと Microsoft Lync モバイルクライアントを含むすべての SIP ドメインについて、必要に応じて繰り返します。</p></td>
</tr>
<tr class="even">
<td><p>内部 DNS/A</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>172.25.33.10</p></td>
<td><p>統合エッジ内部インターフェイス</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

