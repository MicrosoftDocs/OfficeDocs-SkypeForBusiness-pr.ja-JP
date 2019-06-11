---
title: DNS の概要 - 拡張統合エッジ (ロード バランサー機器を使用)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - Scaled consolidated edge with hardware load balancers
ms:assetid: 8453297c-da1d-4b9e-a37e-6721458c6feb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398670(v=OCS.15)
ms:contentKeyID: 48184700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d411b004edde96314e3c06d7f28a9f9d294688ad
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833353"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a>DNS の概要 - Lync Server 2013 の拡張統合エッジ (ロード バランサー機器を使用)

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-01-27_

Lync Server 2013 へのリモートアクセスの DNS レコード要件は、証明書やポートの場合と非常に簡単です。 また、Lync 2013 を実行しているクライアントの構成方法とフェデレーションを有効にするかどうかによって、多くのレコードがオプションになります。

Lync 2013 DNS の要件の詳細については、「 [Lync Server 2013 の dns 要件を確認](lync-server-2013-determine-dns-requirements.md)する」を参照してください。

Lync 2013 クライアントの自動構成の構成の詳細については、「 [Lync Server 2013 の DNS 要件を特定](lync-server-2013-determine-dns-requirements.md)する」の「スプリットブレイン dns を使わない自動構成」を参照してください。

次の表には、スケーリングされた統合エッジトポロジ (ハードウェア負荷分散) 図をサポートするために必要な DNS レコードの概要が記載されています。 特定の DNS レコードは、Lync クライアントの自動構成の場合にのみ必須であることに注意してください。 グループポリシーオブジェクト (Gpo) を使って Lync クライアントを構成することを計画している場合は、関連付けられたレコードは必要ありません。

<div>

## <a name="important-edge-server-network-adapter-requirements"></a>重要: エッジサーバーのネットワークアダプターの要件

ルーティングの問題を回避するには、エッジサーバーに少なくとも2つのネットワークアダプターがあり、その外部インターフェイスに関連付けられているネットワークアダプターでのみ既定のゲートウェイが設定されていることを確認します。 たとえば、スケーリングされた統合エッジシナリオでは、 [Lync Server 2013 のハードウェアロードバランサーを使用したスケーリング](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)された統合エッジの図に示すように、既定のゲートウェイは外部ファイアウォールを指しています。

次のように、各エッジサーバーで2つのネットワークアダプターを構成できます。

  - **ネットワークアダプター 1 (内部インターフェイス)**
    
    172.25.33.10 が割り当てられている内部インターフェイス。
    
    既定のゲートウェイがありません。
    
    Lync Server クライアントまたは Lync Server が実行されているサーバー (172.25.33.0 から192.168.10.0 など) に、エッジサーバーの内部インターフェイスが含まれているネットワークからのルートがあることを確認します。

  - **ネットワークアダプター 2 (外部インターフェイス)**
    
    3つのパブリック IP アドレスがこのネットワークアダプターに割り当てられます。たとえば、アクセスエッジサービスの場合は131.107.155.10、Web 会議エッジサービスの場合は131.107.155.20、A/V Edge サービスの場合は131.107.155.30。
    
    <div>
    

    > [!NOTE]
    > エッジサーバーの実際の外部ネットワークインターフェイスに割り当てられている IP アドレスは、どのハードウェアロードバランサーを選択するかによって異なります。 実際の IP アドレス要件については、ハードウェアロードバランサーのドキュメントを参照してください。<BR>すべての3エッジサービスインターフェイスで単一の IP アドレスを使うことはできますが、お勧めしません。 これにより、IP アドレスが保存されますが、サービスごとに異なるポート番号が必要になります。 既定のポート番号は 443/TCP であり、ほとんどのリモートファイアウォールでトラフィックが許可されます。 ポートの値を変更する (たとえば、アクセスエッジサービスの場合は、5061/tcp、Web 会議エッジサービスの場合は 444/TCP、A/V Edge サービスの場合は 443/TCP) と、相手が背後にあるファイアウォールでトラフィックが許可されていないリモートユーザーに問題が発生する可能性があります。5061/TCP および 444/TCP。 さらに、3つの異なる IP アドレスで、IP アドレスをフィルター処理できるため、トラブルシューティングが容易になります。

    
    </div>
    
    アクセスエッジサービスの IP アドレスは、既定のゲートウェイがインターネットフェーシングルータ (131.107.155.1) に設定されているプライマリサーバーです。
    
    Web 会議エッジサービスと A/V Edge サービス IP アドレスセカンダリ。

<div>


> [!TIP]
> 2つのネットワークアダプターでエッジサーバーを構成するには、2つのオプションのいずれかを使用します。 もう1つの方法として、内部側とエッジサーバーの外部側の3つのネットワークアダプター用に1つのネットワークアダプターを使うことができます。 このオプションの主な利点は、Edge Server サービスごとの個別のネットワークアダプターであり、トラブルシューティングが必要な場合は、より簡潔なデータ収集を行うことです。



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-hardware-load-balanced-example"></a>スケーリングされた統合エッジに必要な DNS レコード、ハードウェア負荷分散 (例)

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
<th>マップ先/コメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部 DNS/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>131.107.155.10</p></td>
<td><p>Access Edge サービスの外部インターフェイス (Contoso)。 Lync を有効にしたユーザーがいるすべての SIP ドメインで、必要に応じて繰り返す</p></td>
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
<td><p>131.107.155.30</p></td>
<td><p>A/V Edge サービスの外部インターフェイス</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/SRV/443</p></td>
<td><p>_sip._tls.contoso.com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Access Edge サービスの外部インターフェイス。 Lync 2013 および Lync 2010 クライアントを外部で動作させるために、自動構成が必要です。 Lync が有効になっているユーザーがいるすべての SIP ドメインで、必要に応じてこの手順を繰り返します。</p></td>
</tr>
<tr class="odd">
<td><p>外部 DNS/SRV/5061</p></td>
<td><p>_sipfederationtls._tcp.contoso.com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>SIP アクセスエッジサービスの外部インターフェイスは、"許可された SIP ドメイン" と呼ばれるフェデレーションパートナー (以前のリリースで拡張フェデレーションと呼ばれる) を自動的に検出するために必要です。 Lync が有効なユーザーと、プッシュ通知サービスまたは Apple プッシュ通知サービスを使用している Microsoft Lync モバイルクライアントが含まれるすべての SIP ドメインで、必要に応じてこの手順を繰り返します。</p></td>
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

