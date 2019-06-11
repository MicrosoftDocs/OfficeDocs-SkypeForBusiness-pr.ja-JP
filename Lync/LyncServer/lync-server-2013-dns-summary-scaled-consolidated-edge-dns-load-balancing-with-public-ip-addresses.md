---
title: 'Lync Server 2013: DNS の概要 - 拡張統合エッジ、パブリック IP アドレスによる DNS 負荷分散'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - Scaled consolidated edge, DNS load balancing with public IP addresses
ms:assetid: dc8f096a-a0a4-4f71-8930-88ff8fc089d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205319(v=OCS.15)
ms:contentKeyID: 48185594
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 226f0ac1c27b18ea19cc1893300ad3614130c798
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833357"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-in-lync-server-2013"></a>DNS の概要 - Lync Server 2013 における拡張統合エッジ、パブリック IP アドレスによる DNS 負荷分散

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2017-03-09_

Lync Server 2013 へのリモートアクセスの DNS レコード要件は、証明書やポートの場合と非常に簡単です。 また、Lync 2013 を実行しているクライアントの構成方法とフェデレーションを有効にするかどうかによって、多くのレコードがオプションになります。

Lync 2013 DNS の要件の詳細については、「 [Lync Server 2013 の dns 要件を確認](lync-server-2013-determine-dns-requirements.md)する」を参照してください。

Lync 2013 クライアントの自動構成の構成の詳細については、「 [Lync Server 2013 の DNS 要件を特定](lync-server-2013-determine-dns-requirements.md)する」の「スプリットブレイン dns を使わない自動構成」を参照してください。

次の表には、単一の統合されたエッジトポロジの図に示されている単一の統合エッジトポロジをサポートするために必要な DNS レコードの概要を示します。 特定の DNS レコードは、Lync 2013 クライアントの自動構成にのみ必要であることに注意してください。 グループポリシーオブジェクト (Gpo) を使って Lync クライアントを構成することを計画している場合は、関連付けられたレコードは必要ありません。

<div>

## <a name="important-edge-server-network-adapter-requirements"></a>重要: エッジサーバーのネットワークアダプターの要件

ルーティングの問題を回避するには、エッジサーバーに少なくとも2つのネットワークアダプターがあり、その外部インターフェイスに関連付けられているネットワークアダプターでのみ既定のゲートウェイが設定されていることを確認します。 たとえば、スケーリングされた統合エッジシナリオでは、拡大縮小された統合エッジでは、 [Lync Server 2013 でのパブリック IP アドレスを使った DNS 負荷分散](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)の場合、既定のゲートウェイは外部ファイアウォールをポイントします。

次のように、各エッジサーバーで2つのネットワークアダプターを構成できます。

  - **ネットワークアダプター 1-ノード 1 (内部インターフェイス)**
    
    172.25.33.10 が割り当てられている内部インターフェイス。
    
    既定のゲートウェイは定義されていません。
    
    Lync Server 2013 または Lync Server 2013 クライアントを実行しているサーバー (172.25.33.0 から192.168.10.0 など) が含まれているすべてのネットワークへの Edge 内部インターフェイスが含まれているネットワークからのルートがあることを確認します。

  - **ネットワークアダプター 1-ノード 2 (内部インターフェイス)**
    
    172.25.33.11 が割り当てられている内部インターフェイス。
    
    既定のゲートウェイは定義されていません。
    
    Lync Server 2013 または Lync Server 2013 クライアントを実行しているサーバー (172.25.33.0 から192.168.10.0 など) が含まれているすべてのネットワークへの Edge 内部インターフェイスが含まれているネットワークからのルートがあることを確認します。

  - **ネットワークアダプター2ノード 1 (外部インターフェイス)**
    
    3つのプライベート IP アドレスがこのネットワークアダプターに割り当てられます。たとえば、アクセスエッジサービスの131.107.155.10、Web 会議エッジサービスの場合は131.107.155.20、A/V Edge サービスの場合は131.107.155.30。
    
    アクセスエッジサービスのパブリック IP アドレスは、既定のゲートウェイがパブリックルーター (131.107.155.1) に設定されているプライマリ IP アドレスです。
    
    Web 会議エッジサービスと A/V Edge サービスのプライベート IP アドレスは、**インターネットプロトコルバージョン 4 (tcp/IPv4)** および**インターネットプロトコルバージョン 6 (tcp/IPv6)** のプロパティの **[詳細設定**] セクションで追加の ip アドレスとなります。Windows Server の**ローカルエリア接続プロパティ**。
    
    <div>
    

    > [!NOTE]  
    > すべての3エッジサービスインターフェイスで単一の IP アドレスを使うことはできますが、お勧めしません。 これにより、IP アドレスが保存されますが、サービスごとに異なるポート番号が必要になります。 既定のポート番号は 443/TCP であり、ほとんどのリモートファイアウォールでトラフィックが許可されます。 ポートの値を変更する (たとえば、アクセスエッジサービスの場合は、5061/tcp、Web 会議エッジサービスの場合は 444/TCP、A/V Edge サービスの場合は 443/TCP) と、相手が背後にあるファイアウォールでトラフィックが許可されていないリモートユーザーに問題が発生する可能性があります。5061/TCP および 444/TCP。 さらに、3つの異なる IP アドレスで、IP アドレスをフィルター処理できるため、トラブルシューティングが容易になります。

    
    </div>

  - **ネットワークアダプター2ノード 2 (外部インターフェイス)**
    
    3つのプライベート IP アドレスがこのネットワークアダプターに割り当てられます。たとえば、アクセスエッジサービスの131.107.155.11、Web 会議エッジサービスの場合は131.107.155.21、A/V Edge サービスの場合は131.107.155.31。
    
    アクセスエッジサービスのパブリック IP アドレスは、既定のゲートウェイがパブリックルーター (131.107.155.1) に設定されているプライマリ IP アドレスです。
    
    Web 会議エッジサービスと A/V Edge サービスのプライベート IP アドレスは、**インターネットプロトコルバージョン 4 (tcp/IPv4)** および**インターネットプロトコルバージョン 6 (tcp/IPv6)** のプロパティの **[詳細設定**] セクションで追加の ip アドレスとなります。Windows Server の**ローカルエリア接続プロパティ**。

<div>


> [!TIP]  
> 2つのネットワークアダプターでエッジサーバーを構成するには、2つのオプションのいずれかを使用します。 もう1つの方法として、内部側とエッジサーバーの外部側の3つのネットワークアダプター用に1つのネットワークアダプターを使うことができます。 このオプションの主な利点は、Edge Server サービスごとの個別のネットワークアダプターであり、トラブルシューティングが必要な場合は、より簡潔なデータ収集を行うことです。



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-example"></a>スケーリングされた統合エッジに必要な DNS レコード、パブリック IP アドレスを使った DNS 負荷分散 (例)

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
<td><p>131.107.155.10 および 131.107.155.11</p></td>
<td><p>Access Edge service の外部インターフェイス (Contoso) は、Lync を有効にしたユーザーがいるすべての SIP ドメインについて、必要に応じて繰り返します。</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/A</p></td>
<td><p>webcon.contoso.com</p></td>
<td><p>131.107.155.20 および 131.107.155.21</p></td>
<td><p>Web 会議エッジサービスの外部インターフェイス</p></td>
</tr>
<tr class="odd">
<td><p>外部 DNS/A</p></td>
<td><p>av.contoso.com</p></td>
<td><p>131.107.155.30 および 131.107.155.31</p></td>
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
<td><p>Access Edge service の外部インターフェイスは、"許可された SIP ドメイン" と呼ばれるフェデレーションパートナー (以前のリリースで拡張フェデレーションと呼ばれる) を自動的に検出するために必要です。 Lync を有効にしたユーザーがいるすべての SIP ドメインで、必要に応じて繰り返す</p></td>
</tr>
<tr class="even">
<td><p>内部 DNS/A</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>172.25.33.10 および 172.25.33.11</p></td>
<td><p>統合エッジ内部インターフェイス</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="records-required-for-federation"></a>フェデレーションに必要なレコード


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
<th>FQDN</th>
<th>IP アドレス/FQDN ホストレコード</th>
<th>マップ先/コメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部 DNS/SRV/5061</p></td>
<td><p>_sipfederationtls._tcp.contoso.com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>SIP アクセスエッジサービスの外部インターフェイスは、他の潜在的なフェデレーションパートナーとのフェデレーションを自動的に検出するために必要です。また、"許可 SIP ドメイン" と呼ばれます (以前のリリースで拡張フェデレーションと呼ばれます)。</p>
<div>

> [!IMPORTANT]  
> Lync が有効なユーザーと、プッシュ通知サービスまたは Apple プッシュ通知サービスを使用している Microsoft Lync モバイルクライアントが含まれるすべての SIP ドメインで、必要に応じてこの手順を繰り返します。


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a>拡張メッセージングとプレゼンスプロトコルの DNS 概要


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
<th>FQDN</th>
<th>IP アドレス/FQDN ホストレコード</th>
<th>マップ先/コメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部 DNS/SRV/5269</p></td>
<td><p>_xmpp-server._tcp.contoso.com</p></td>
<td><p>xmpp.contoso.com</p></td>
<td><p>アクセスエッジサービスまたはエッジプールの XMPP プロキシ外部インターフェイス。グローバルポリシー、ユーザーが配置されているサイトポリシー、またはユーザーポリシーを使用して、外部アクセスポリシーの構成を通じて、すべての内部 SIP ドメインについて必要に応じてこの手順を繰り返します。Lync 対応ユーザー。 許可されている XMPP ドメインは、XMPP フェデレーションパートナーポリシーでも構成する必要があります。 詳細については、 <strong>「</strong>関連項目」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/A</p></td>
<td><p>xmpp.contoso.com (など)</p></td>
<td><p>エッジサーバーまたは XMPP プロキシをホストしているエッジプールのアクセスエッジサービスの IP アドレス</p></td>
<td><p>XMPP プロキシサービスをホストしているアクセスエッジサービスまたはエッジプールへのポイント。 通常、作成した SRV レコードは、このホスト (A または AAAA) レコードをポイントします。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

