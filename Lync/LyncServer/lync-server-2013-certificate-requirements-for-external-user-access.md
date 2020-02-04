---
title: 'Lync Server 2013: 外部ユーザー アクセスに対する証明書要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate requirements for external user access
ms:assetid: d45b6b10-556f-4b10-b1a7-fb0d0a64a498
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398920(v=OCS.15)
ms:contentKeyID: 48185503
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1b6495dbad5350f94873099985922f1adc198f2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736837"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-external-user-access-in-lync-server-2013"></a>Lync Server 2013 における外部ユーザー アクセスに対する証明書要件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2016-03-29_

Microsoft Lync Server 2013 通信ソフトウェアは、アクセスおよび web 会議エッジの外部インターフェイスに加えて、A/V 認証サービスによる単一のパブリック証明書の使用をサポートしています。 通常、Edge 内部インターフェイスでは、内部証明機関 (CA) によって発行されたプライベート証明書を使用しますが、信頼できる公開 CA から提供されている公開証明書を使うこともできます。 展開内のリバースプロキシは、公開証明書を使用して、リバースプロキシからクライアントへの通信と、HTTP (つまり、HTTP を経由したトランスポートレイヤーのセキュリティ) を使用した内部サーバーへの通信を暗号化します。

Access および web 会議エッジの外部インターフェイスと A/V 認証サービスで使用される公開証明書の要件を次に示します。

  - 証明書は、サブジェクト代替名をサポートする承認済みのパブリック CA によって発行される必要があります。 詳細については、Microsoft サポート技術情報の記事929395「Exchange Server および通信サーバーのユニファイドコミュニケーション証明書[http://go.microsoft.com/fwlink/p/?linkId=202834](http://go.microsoft.com/fwlink/p/?linkid=202834)パートナー」を参照してください。

  - エッジプールで証明書を使用する場合は、エッジプールの各エッジサーバーで使用されるものと同じ証明書を使って、エクスポート可能として作成する必要があります。 エクスポート可能な秘密キーの要件は、A/V 認証サービスの目的であり、プール内のすべてのエッジサーバーで同じ秘密キーを使用する必要があります。

  - オーディオ/ビデオサービスの稼働時間を最大化する必要がある場合は、分離型 A/V エッジサービス証明書を実装するための証明書要件を確認します (つまり、他の外部エッジ証明書の目的に関する個別の A/V Edge サービス証明書です)。 詳細については、「 [lync server の計画に影響を与える lync server 2013 の変更点](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)」を参照してください。 lync server [2013 でのエッジサーバーの証明](lync-server-2013-plan-for-edge-server-certificates.md)書と、lync server [2013 での [ステージング AV] および [OAuth 証明書] を使用して、[設定-cscertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)] を選びます。

  - 証明書のサブジェクト名は、アクセスエッジサービスの外部インターフェイスの完全修飾ドメイン名 (FQDN) またはハードウェアロードバランサー VIP (たとえば、access.contoso.com) です。 ). サブジェクト名にワイルドカード文字を使用することはできません。明示的な名前を指定する必要があります。
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013 の場合、これは必須ではありませんが、Office Communications Server との互換性を確保することをお勧めします。

    
    </div>

  - サブジェクト代替名の一覧には、次の Fqdn が含まれます。
    
      - アクセスエッジサービスの外部インターフェイスまたはハードウェアロードバランサー VIP (たとえば、sip.contoso.com)。
        
        <div>
        

        > [!NOTE]  
        > 証明書の件名はアクセスエッジ FQDN と同じですが、トランスポート層セキュリティ (TLS) ではサブジェクト名が無視され、サブジェクトの代替名エントリが使用されるため、アクセスエッジの fqdn を含める必要があります。入力規則.

        
        </div>
    
      - Web 会議エッジの外部インターフェイスまたはハードウェアのロードバランサー VIP (たとえば、webcon.contoso.com)。
    
      - クライアントの自動構成またはフェデレーションを使用している場合は、会社内で使用されている SIP ドメイン Fqdn も含めます (たとえば、sip.contoso.com、sip.fabrikam.com)。
    
      - A/V Edge サービスでは、サブジェクト名、またはサブジェクトの代替名のエントリは使用されません。
    
    <div>
    

    > [!NOTE]  
    > [サブジェクト代替名] リストの Fqdn の順序は問題ではありません。

    
    </div>

複数の負荷分散エッジサーバーをサイトに展開している場合は、各エッジサーバーにインストールされている A/V 認証サービスの証明書が同じ CA からのものであり、同じ秘密キーを使用している必要があります。 証明書の秘密キーは、1つのエッジサーバーで使用するか、多数のエッジサーバーで使用するかに関係なく、エクスポート可能である必要があることに注意してください。 また、エッジサーバー以外のコンピューターから証明書を要求した場合も、エクスポート可能である必要があります。 A/V 認証サービスではサブジェクト名またはサブジェクトの別名を使用しないため、アクセスエッジおよび web 会議エッジに対してサブジェクト名と件名の代替名の要件が満たされている限り、アクセスエッジ証明書を再利用することができます。また、証明書の秘密キーはエクスポートできます。

エッジ内部インターフェイスに使用されるプライベート (またはパブリック) 証明書の要件は、次のとおりです。

  - 証明書は、内部 CA または承認された公開証明機関によって発行できます。

  - 証明書のサブジェクト名は、通常、エッジ内部インターフェイス FQDN またはハードウェアロードバランサー VIP (lsedge.contoso.com など) です。 ただし、内部でワイルドカード証明書を使用することはできます。

  - 件名の代替名リストは必須ではありません。

展開サービスが要求するリバースプロキシ:

  - 会議の会議コンテンツへの外部ユーザーアクセス

  - 配布グループのメンバーを展開して表示するための外部ユーザーアクセス

  - アドレス帳サービスからダウンロード可能なファイルへの外部ユーザーアクセス

  - Lync Web App クライアントへの外部ユーザーアクセス

  - [ダイヤルイン会議の設定] web ページへの外部ユーザーアクセス

  - 位置情報サービスへの外部ユーザーアクセス

  - デバイス更新サービスへの外部デバイスアクセスと更新プログラムの入手

リバースプロキシは、内部サーバー Web コンポーネントの Url を公開します。 Web コンポーネントの Url は、監督、フロントエンドサーバー、またはフロントエンドプールで、トポロジビルダーの**外部 Web サービス**として定義されています。

逆プロキシに割り当てられている証明書のサブジェクトの別名フィールドでは、ワイルドカードエントリがサポートされます。 リバースプロキシの証明書の要求を構成する方法の詳細については、「 [Lync Server 2013 でリバース HTTP プロキシ用の証明書を要求および構成](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md)する」を参照してください。

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 のワイルドカード証明書のサポート](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

