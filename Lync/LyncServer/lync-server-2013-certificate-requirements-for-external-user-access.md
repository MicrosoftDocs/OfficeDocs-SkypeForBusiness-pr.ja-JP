---
title: 'Lync Server 2013: 外部ユーザーアクセスの証明書要件'
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
ms.openlocfilehash: 37494b3f8389709681ffc92a17d388b71baddd70
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517954"
---
# <a name="certificate-requirements-for-external-user-access-in-lync-server-2013"></a>Lync Server 2013 での外部ユーザーアクセスの証明書要件

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2016-03-29_

Microsoft Lync Server 2013 communications software は、アクセスおよび web 会議エッジの外部インターフェイスに対する単一のパブリック証明書、および音声ビデオ認証サービスの使用をサポートしています。 エッジ内部インターフェイスでは、通常であれば内部証明機関 (CA) が発行するプライベート証明書を使用しますが、信頼されたパブリック CA が発行したものであればパブリック証明書も使用できます。 展開のリバース プロキシでは、パブリック証明書を使用し、リバース プロキシからクライアントへの通信およびリバース プロキシから内部サーバーへの通信を、HTTP を使用して暗号化します (つまり、Transport Layer Security over HTTP)。

以下に、アクセスおよび Web 会議のエッジ外部インターフェイスで使用されるパブリック証明書、および音声ビデオ認証サービスの要件を示します。

  - 証明書は、サブジェクトの別名をサポートする承認されたパブリック CA によって発行される必要があります。 詳細については、Microsoft サポート技術情報の記事929395「Exchange Server と通信サーバーのための統合コミュニケーション証明書パートナー」 () を参照してください [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834) 。

  - 証明書をエッジ プールで使用する場合は、エッジ プール内の各エッジ サーバーで使用される同じ証明書を使用して、エクスポート可能として作成する必要があります。エクスポート可能な秘密キーの要件は音声ビデオ認証サービスのためのもので、プール内のすべてのエッジ サーバーで同じ秘密キーを使用する必要があります。

  - 音声ビデオサービスの稼働時間を最大にする場合は、分離された音声ビデオエッジサービス証明書を実装するための証明書の要件を確認します (つまり、他の外部エッジ証明書の目的からの個別の音声ビデオエッジサービス証明書)。 詳細については、「 [変更2013点](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)」を参照してください。エッジサーバーの計画、「lync server [2013 でのエッジサーバー証明書の計画](lync-server-2013-plan-for-edge-server-certificates.md) 」、および「Lync server [2013 のステージングの AV および OAuth 証明書を使用した設定-cscertificate」](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)を参照してください。

  - 証明書のサブジェクト名は、アクセスエッジサービスの外部インターフェイスの完全修飾ドメイン名 (FQDN) またはハードウェアロードバランサーの VIP (たとえば、access.contoso.com) です。 ). サブジェクト名にワイルドカード文字を使用することはできません。明示的な名前である必要があります。
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013 の場合、これは要件ではありませんが、Office Communications Server との互換性を維持することをお勧めします。

    
    </div>

  - サブジェクトの別名リストには、以下のコンポーネントの FQDN が含まれています。
    
      - アクセスエッジサービスの外部インターフェイスまたはハードウェアロードバランサーの VIP (たとえば、sip.contoso.com)。
        
        <div>
        

        > [!NOTE]  
        > 証明書のサブジェクト名はアクセス エッジの FQDN と等しくなりますが、サブジェクトの別名にもアクセス エッジの FQDN を含める必要があります。これは、トランスポート層セキュリティ (TLS) がサブジェクト名を無視し、検証でサブジェクトの別名エントリを使用するからです。

        
        </div>
    
      - Web 会議エッジ外部インターフェイスまたはハードウェア ロード バランサーの VIP (たとえば、webcon.contoso.com)。
    
      - クライアントの自動構成またはフェデレーションを使用し、会社内で使用されるすべての SIP ドメインの FQDN を含める場合 (たとえば、sip.contoso.com や sip.fabrikam.com)。
    
      - 音声ビデオエッジサービスでは、サブジェクト名またはサブジェクトの別名エントリは使用されません。
    
    <div>
    

    > [!NOTE]  
    > サブジェクトの別名リストでの FQDN の順番は問題ではありません。

    
    </div>

1 つのサイトで負荷分散が有効な複数のエッジ サーバーを展開する場合、各エッジ サーバーにインストールする音声ビデオ認証サービス証明書は、同じ CA が発行したもので、同じ秘密キーを使用する必要があります。証明書の秘密キーは、1 つのエッジ サーバーと多くのエッジ サーバーのどちらで使用するかに関係なく、エクスポート可能にする必要があります。また、エッジ サーバー以外のコンピューターから証明書を要求する場合にもエクスポート可能にする必要があります。音声ビデオ認証サービスはサブジェクト名またはサブジェクトの別名を使用しないので、サブジェクト名およびサブジェクトの別名の要件がアクセス エッジおよび Web 会議エッジに対して満たされていて、証明書の秘密キーがエクスポート可能である限り、アクセス エッジ証明書を再利用できます。

エッジ内部インターフェイスで使用するプライベート (またはパブリック) 証明書の要件は以下のとおりです。

  - 証明書は、内部 CA または承認されたパブリック証明書 CA が発行できます。

  - 証明書のサブジェクト名は、通常、エッジ内部インターフェイスの FQDN またはハードウェア ロード バランサーの VIP (たとえば、lsedge.contoso.com) です。 ただし、エッジ内部でワイルドカード証明書を使用できます。

  - 必須のサブジェクトの別名リストはありません。

展開サービス内のリバース プロキシは、以下のことを要求します。

  - 会議の会議コンテンツへの外部ユーザー アクセス

  - 配布グループのメンバーを展開および表示するための外部ユーザー アクセス

  - アドレス帳サービスからダウンロード可能なファイルへの外部ユーザー アクセス

  - Lync Web App クライアントへの外部ユーザーアクセス

  - [ダイヤルイン会議の設定] Web ページへの外部ユーザー アクセス

  - 場所情報サービスへの外部ユーザー アクセス

  - デバイス更新サービスおよび更新の取得への外部デバイス アクセス

リバース プロキシは、内部サーバーの Web コンポーネント URL を発行します。 Web コンポーネントの Url は、トポロジビルダーの **外部 Web サービス** として、ディレクター、フロントエンドサーバー、またはフロントエンドプールで定義されます。

リバース プロキシに割り当てられている証明書のサブジェクトの別名フィールドでは、ワイルドカードの入力がサポートされています。 リバースプロキシの証明書要求を構成する方法の詳細については、「 [Lync Server 2013 のリバース HTTP プロキシの証明書を要求および構成](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md)する」を参照してください。

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのワイルドカード証明書のサポート](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

