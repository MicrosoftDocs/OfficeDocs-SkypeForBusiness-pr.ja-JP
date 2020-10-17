---
title: Lync Server と Office Communications Server のフェデレーションの計画
description: Lync Server と Office Communications Server のフェデレーションの計画。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Lync Server and Office Communications Server federation
ms:assetid: c9eaf06b-054f-41a4-ad0c-499400d6c4c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205335(v=OCS.15)
ms:contentKeyID: 48185640
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5d7385b8fde27446fb0648802544a8840a0f6276
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552373"
---
# <a name="planning-for-lync-server-2013-and-office-communications-server-federation"></a>Lync Server 2013 および Office Communications Server のフェデレーションの計画

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-13_

Microsoft Lync Server 2013、Lync Server 2010、および Office Communications Server の間のフェデレーションは、ピアツーピア通信と複数パーティ通信をサポートします。 ピアツーピアの会話をマルチパーティの会話にエスカレートでき、臨時の会議を実行できます。 会議 – Web 会議または音声ビデオ会議をスケジュールし、組織内の連絡先およびフェデレーションしているパートナーの連絡先を含めることができます。

フェデレーションは、Microsoft Office Live Communications Server 2005 で初めて登場し、サポートされている1種類のフェデレーションである直接フェデレーションをサポートしていました。 直接フェデレーションでは、フェデレーションパートナーのセッション開始プロトコル (SIP) ドメインと、パートナーのエッジサーバーの完全修飾ドメイン名 (FQDN) を知る必要があります。 Live Communications Server 2005 SP1 では、追加のフェデレーションの種類が導入されており、すべての必要なドメインネームシステム (DNS) SRV レコードがフェデレーションパートナーによって公開され、そのエッジサーバーを特定します。 そのリリースで使用されていた用語は次のとおりです。

  - *拡張フェデレーションを開く*: 任意の SIP ドメイン名を受け入れ、DNS SRV を使用してパートナーエッジサーバーを特定する

  - *拡張フェデレーション*: パートナーの SIP ドメイン名を組織のフェデレーションパートナーとして構成し、DNS SRV を使用してパートナーエッジサーバーを検索する

  - *直接フェデレーション*: パートナーの SIP ドメイン名と、パートナーのエッジサーバーに対する FQDN を構成する

  - *サーバーの許可一覧*: 任意のドメインを受け入れ、DNS SRV を使用してホスティングプロバイダーまたはパブリックインスタントメッセージング (IM) 接続プロバイダーのエッジサーバーを検索する

Microsoft Office Communications Server 2007 は、フェデレーションの種類に対して更新された命名を導入し、各フェデレーションの種類が実際に達成したことをより明確にしました。

  - オープン拡張フェデレーションは、*検出済みのパートナー ドメイン*に変更

  - 拡張フェデレーションは、*許可されたパートナー ドメイン*に変更

  - 直接フェデレーションは、*許可されたパートナー サーバー*に変更

  - サーバー許可リストは、*ホスティング プロバイダー*および*パブリック IM プロバイダー*に変更

Microsoft Lync Server 2010 では、Microsoft Lync Online 2010 および Microsoft Office 365 に従ってホスティングプロバイダーの定義が狭められ、また、許可されたパートナードメインのフェデレーションの種類によって定義されたものと同じ許可リストに従うようになりました。

Microsoft Lync Server 2013、Lync Server 2010、および Office Communications Server の間のフェデレーションを有効にするには、エッジサーバーとリバースプロキシを使用して、定義したルールおよび許可されたパートナードメインを適用します。 計画の観点から、他の Lync Server とのフェデレーションでは、Office Communications Server に次のものが必要です。

  - トポロジ ビルダーでフェデレーションを有効にします。 詳細については、「 [Lync Server 2013 での SIP フェデレーション、XMPP フェデレーションおよびパブリックインスタントメッセージングの構成](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md)」の展開に関するトピックを参照してください。

  - フェデレーションされたドメインの検出に対する要件を決定します。
    
      - <span></span>  
        フェデレーションを手動で構成するには、パートナーのエッジサーバーとドメイン名の完全修飾ドメイン名 (FQDN)、または Lync Server コントロールパネル、 **フェデレーションと外部アクセス**、 **SIP フェデレーションドメイン**に入力されたオンラインドメイン名を持っている必要があります。 **新しい**ポリシーを作成するか、既存のポリシーを**編集**して、ドメインを FQDN で許可またはブロックします。
        
        <div>
        

        > [!WARNING]
        > パートナーがエッジサーバーの IP アドレスを変更した場合、フェデレーションパートナーのエッジサーバーを手動で構成すると、障害が発生しやすくなります。

        
        </div>
        
        <div>
        

        > [!NOTE]
        > <STRONG>新しい SIP フェデレーションドメイン</STRONG>の場合は、Microsoft Lync Online および microsoft 365 または Office 365 の<STRONG>ドメイン名 (または FQDN)</STRONG>を指定する必要があります。 Microsoft Lync Server 2013、Lync Server 2010、および Office Communications Server の場合は、<STRONG>アクセスエッジサービス (FQDN)</STRONG>も提供する必要があります。

        
        </div>
    
      - <span></span>  
        パートナーがエッジサーバーを検出できる、検出されたパートナーフェデレーションについては、外部 DNS-sipfederationtls で SRV レコードを作成し \_ ます。 \_tcp.contoso.com –エッジサーバーのポート5061およびホスト (A) レコードを指します。
        
        <div>
        

        > [!IMPORTANT]
        > Windows Phone または Apple iPhone、iPad、またはその他の Apple デバイスで Microsoft Lync Mobile クライアントをサポートしていて、プッシュ通知サービスまたはプッシュ通知サービスを使用している場合は、_sipfederationtls を計画する必要があります。 &lt;&gt;Lync Mobile クライアントを所有している各 sip ドメインの sip ドメイン SRV レコード。 Android および Nokia Symbian Lync Mobile では、プッシュ通知を使用しないでください。この要件の対象にはなりません。

        
        </div>

  - フェデレーションされたドメインをサポートするように外部ユーザー アクセス ポリシーを構成します

  - セッション開始プロトコル (SIP)、Web 会議、音声ビデオ用にファイアウォールのポートを開き、有効にしているフェデレーションまたは連絡先に対応します。 詳細については、「 [Lync Server 2013 の外部の音声ビデオファイアウォールおよびポートの要件を決定する](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)」を参照してください。

次の情報は、Microsoft Lync Server 2013 および Lync Server 2010 とのフェデレーションのための証明書、ポート、プロトコル、および DNS の要件を定義するのに役立ちます。

Microsoft Lync Server 2013 エッジサーバーを計画または展開している場合は、証明書、ファイアウォール、およびポート/プロトコルの要件、および DNS の要件を計画するのが一般的です。 フェデレーションは既存のエッジサーバーを使用する追加機能なので、計画の要件は通常、エッジサーバーの計画と展開によって満たされます。 次の表を使用して要件が満たされていることを確認し、それに従ってポート/プロトコルおよび DNS を変更します。

<div>


> [!IMPORTANT]
> エッジサーバーのプールがあり、Lync Server 2013 または Lync Server 2010 パートナーとのフェデレーションを行っている場合は、エッジサーバーの内部および外部の側で DNS 負荷分散またはハードウェアロードバランサーを使用することができます。 Office Communications Server 2007 または Office Communications Server 2007 R2 を使用している場合は、ハードウェア負荷分散によって、エッジサーバーの障害に対するフェールオーバーサポートが提供されます。 Office Communications Server 2007 および Office Communications Server 2007 R2 は、DNS 負荷分散に対応していません。 パートナーエッジサーバーは、プール内で応答する最初のエッジサーバーとの通信を確立します。 エッジサーバーに障害が発生しても、通信が自動的にフェールオーバーされることはありません。



</div>

通常、証明書の要件は、選択したエッジサーバーまたはプールのエッジサーバープランの証明書の計画によって満たされます。

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [証明書の概要-Lync Server 2013 の SIP、XMPP フェデレーション、およびパブリックインスタントメッセージング](lync-server-2013-certificate-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [ポートの概要-Lync Server 2013 の SIP、XMPP フェデレーション、およびパブリックインスタントメッセージング](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [Lync Server 2013 の DNS の概要-SIP、XMPP フェデレーション、およびパブリックインスタントメッセージング](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でフェデレーションユーザーアクセスを制御するポリシーの構成](lync-server-2013-configure-policies-to-control-federated-user-access.md)  


[Lync Server 2013 での外部ユーザーアクセスのシナリオ](lync-server-2013-scenarios-for-external-user-access.md)  
[Lync Server 2013 の外部の音声ビデオファイアウォールおよびポートの要件を決定する](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
[Lync Server 2013 の DNS 要件を決定する](lync-server-2013-determine-dns-requirements.md)  


[Lync Server 2013 での組織のアクセスエッジ構成の管理](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)  
[Lync Server 2013 での組織の SIP フェデレーションドメインの管理](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[Lync Server 2013 での組織の SIP フェデレーションプロバイダーの管理](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

