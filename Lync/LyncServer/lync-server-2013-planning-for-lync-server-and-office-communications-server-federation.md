---
title: Lync Server と Office Communications Server フェデレーションの計画
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
ms.openlocfilehash: 015f824ff2b8510559a7bd4910be76321d44d242
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41751867"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-lync-server-2013-and-office-communications-server-federation"></a>Lync Server 2013 と Office Communications Server フェデレーションの計画

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-13_

Microsoft Lync Server 2013、Lync Server 2010、および Office Communications Server 間のフェデレーションは、ピアツーピア通信とマルチパーティ通信をサポートしています。 ピアツーピアの会話は、複数の相手との会話にエスカレーションして、臨時の会議を可能にすることができます。 会議– Web 会議や音声/ビジュアル会議–組織内の連絡先、およびフェデレーションするパートナーの連絡先を含めるようにスケジュールできます。

フェデレーションは、Microsoft Office Live Communications Server 2005 で初めて表示され、サポートされているフェデレーションの1つになります。 直接フェデレーションでは、フェデレーションパートナーのセッション開始プロトコル (SIP) ドメインとパートナーのエッジサーバーの完全修飾ドメイン名 (FQDN) を知っている必要があります。 SP1 での Live Communications Server 2005 には、フェデレーションパートナーがエッジサーバーを検索するために必要なすべてのフェデレーションの種類 (DNS) SRV レコードが導入されています。 このリリースの用語は次のとおりです。

  - *拡張フェデレーションを開く*: すべての SIP ドメイン名を受け入れ、DNS SRV を使ってパートナーエッジサーバーを検索する

  - *拡張フェデレーション*: パートナーの SIP ドメイン名を組織のフェデレーションパートナーとして構成し、DNS SRV を使ってパートナーエッジサーバーを検索します。

  - *直接フェデレーション*: パートナーの SIP ドメイン名と、パートナーのエッジサーバーに対して FQDN を構成する

  - *サーバーの許可リスト*: 任意のドメインを承諾し、DNS SRV を使って、ホスティングプロバイダーまたはパブリックインスタントメッセージング (IM) 接続プロバイダーのエッジサーバーを検索します。

Microsoft Office Communications Server 2007 では、フェデレーションの種類の名前が更新され、各フェデレーションの種類が実際にどのように対応しているかがより明確になりました。

  - オープン拡張フェデレーションが検出された*パートナードメイン*として認識される

  - 拡張フェデレーションが*許可パートナードメイン*として認識される

  - 直接フェデレーションが*許可パートナーサーバー*と呼ばれました

  - サーバーの許可リストは、*ホスティングプロバイダー*と*パブリック IM プロバイダー*と呼ばれます

Microsoft Lync Server 2010 は、Microsoft Lync Online 2010 と Microsoft Office 365 に準拠して、ホスティングプロバイダーの幅の狭い定義を導入しました。また、許可パートナードメインフェデレーションタイプで定義されたのと同じ許可一覧も適用されます。

Microsoft Lync Server 2013、Lync Server 2010、Office Communications Server の間のフェデレーションを有効にすると、エッジサーバーとリバースプロキシを使って、定義したルールと許可されたパートナードメインを適用することができます。 計画の観点から、他の Lync Server とのフェデレーションを行うには、Office Communications Server で次のことを行う必要があります。

  - トポロジビルダーでフェデレーションを有効にします。 詳細については、「 [Lync Server 2013 で SIP フェデレーション、XMPP フェデレーションおよびパブリックインスタントメッセージングを構成する展開に](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md)関するトピックを参照してください。

  - フェデレーションドメイン探索の要件を決定する:
    
      - <span></span>  
        フェデレーションを手動で構成するには、パートナーのエッジサーバーとドメイン名の完全修飾ドメイン名 (FQDN)、および Lync Server コントロールパネル、**フェデレーション、外部アクセス**、 **SIP フェデレーションドメイン**に入力されたオンラインドメイン名を持っている必要があります。 ドメインを FQDN で許可またはブロックするには、**新しい**ポリシーを作成するか、既存のポリシーを**編集**します。
        
        <div>
        

        > [!WARNING]
        > フェデレーションパートナーのエッジサーバーを手動で構成すると、パートナーがエッジサーバーの IP アドレスを変更した場合にエラーが発生しやすくなります。

        
        </div>
        
        <div>
        

        > [!NOTE]
        > <STRONG>新しい SIP フェデレーションドメイン</STRONG>の場合は、Microsoft Lync Online、microsoft Office 365 の<STRONG>ドメイン名 (または FQDN)</STRONG>を指定する必要があります。 Microsoft Lync Server 2013、Lync Server 2010、Office Communications Server の場合は、<STRONG>アクセスエッジサービス (FQDN)</STRONG>も指定する必要があります。

        
        </div>
    
      - <span></span>  
        パートナーがエッジサーバーを検出できる検出されたパートナーフェデレーションについては、外部 DNS- \_SIPFEDERATIONTLS で SRV レコードを作成します。\_Tcp.contoso.com –エッジサーバーのポート5061およびホスト (A) レコードを指します。
        
        <div>
        

        > [!IMPORTANT]
        > Windows Phone または Apple iPhone、iPad、またはその他の Apple デバイスで Microsoft Lync モバイルクライアントをサポートしており、プッシュ通知サービスまたはプッシュ通知サービスを使っている場合は、_sipfederationtls を計画する必要があり _tcp ます。 &lt;Lync モバイル&gt;クライアントを使用している sip ドメインごとに sip ドメイン SRV レコード。 Android および Nokia Symbian Lync Mobile では、プッシュ通知は使用されず、この要件の対象にはなりません。

        
        </div>

  - フェデレーションドメインをサポートするように外部ユーザーアクセスポリシーを構成する

  - 有効にしているフェデレーションまたは連絡先に対応するために、セッション開始プロトコル (SIP)、web 会議、およびオーディオ/ビジュアル用のファイアウォールポートを開きます。 詳細については、「 [Lync Server 2013 の外部の A/V ファイアウォールとポートの要件を確認](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)する」を参照してください。

Microsoft Lync Server 2013 および Lync Server 2010 とのフェデレーションのための証明書、ポート/プロトコル、および DNS の要件を定義するには、次の情報を参考にしてください。

Microsoft Lync Server 2013 Edge サーバーを計画または展開した場合、通常、証明書、ファイアウォール、ポート/プロトコルの要件と DNS 要件を計画します。 フェデレーションは、既存のエッジサーバーを使用する追加機能であるため、通常、計画の要件はエッジサーバーの計画と展開によって満たされます。 以下の表を使用して、要件を満たしていることを確認し、それに応じてポート/プロトコルと DNS を変更してください。

<div>


> [!IMPORTANT]
> エッジサーバーのプールと Lync Server 2013 または Lync Server 2010 パートナーとのフェデレーションを行っている場合は、エッジサーバーの内部および外部のサイドで DNS 負荷分散またはハードウェアロードバランサーを使用できます。 Office Communications Server 2007 または Office Communications Server 2007 R2 とのフェデレーションを行う場合、ハードウェア負荷分散によって、エッジサーバーのイベントに対するフェールオーバーサポートが提供されます。 Office Communications Server 2007 と Office Communications Server 2007 R2 は、DNS 負荷分散に対応していません。 パートナーエッジサーバーは、お使いのプールの最初のエッジサーバーとの通信を確立します。 このエッジサーバーに障害が発生した場合、通信が自動的にフェイルオーバーされることはありません。



</div>

通常、証明書の要件は、選択したエッジサーバーまたはプールされたエッジサーバープランの証明書の計画によって満たされます。

<div>

## <a name="in-this-section"></a>このセクション中

  - [証明書の概要-Lync Server 2013 での SIP、XMPP フェデレーション、およびパブリックインスタントメッセージング](lync-server-2013-certificate-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [[ポートの概要]-Lync Server 2013 での SIP、XMPP フェデレーション、およびパブリックインスタントメッセージング](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [DNS 概要-Lync Server 2013 での SIP、XMPP フェデレーション、およびパブリックインスタントメッセージング](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのフェデレーション ユーザー アクセスを制御するポリシーの構成](lync-server-2013-configure-policies-to-control-federated-user-access.md)  


[Lync Server 2013 の外部ユーザー アクセスのシナリオ](lync-server-2013-scenarios-for-external-user-access.md)  
[Lync Server 2013 の外部の音声ビデオ ファイアウォールおよびポートの要件を決定する](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
[Lync Server 2013 の DNS の要件を確認する](lync-server-2013-determine-dns-requirements.md)  


[Lync Server 2013 での組織のアクセス エッジ構成の管理](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)  
[Lync Server 2013 での組織の SIP フェデレーション ドメインの管理](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[Lync Server 2013 での組織の SIP フェデレーション プロバイダーの管理](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

