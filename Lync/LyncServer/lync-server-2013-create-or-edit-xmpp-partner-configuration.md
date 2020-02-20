---
title: 'Lync Server 2013: XMPP パートナー構成の作成または編集'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or edit XMPP partner configuration
ms:assetid: 362dbe5e-8ee9-4aba-8c26-5907312b4a60
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552447(v=OCS.15)
ms:contentKeyID: 48679558
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 609729c65240a17b70f7ef7115bd4901f37c687a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151939"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-edit-xmpp-partner-configuration-in-lync-server-2013"></a>Lync Server 2013 での XMPP パートナー構成の作成または編集

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-09-03_

Microsoft Lync Server 2013 では、フロントエンドサーバーまたはフロントエンドプールのエッジサーバーと XMPP ゲートウェイに、拡張可能なメッセージングとプレゼンスプロトコル (XMPP) プロキシが統合されています。 他の XMPP 展開からの接続を許可するには、Lync Server コントロールパネルで XMPP を構成する必要があります。 XMPP ドメインベースで設定を構成します。 新しいパートナー関連付けを作成するには、以下の操作を実行します。

<div>

## <a name="to-create-a-new-federated-partner-or-edit-an-existing-configuration"></a>新しいフェデレーションパートナーを作成する、または既存の構成を編集するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**フェデレーションと外部アクセス**] をクリックし、[**XMPP フェデレーション パートナー**] をクリックします。

4.  新しい較正を作成するには、[**新規作成**] をクリックします。

5.  既存の構成を編集するには、構成を選択して [**編集**] をクリックします。

6.  [**XMPP フェデレーション パートナー**] の構成を作成、または編集するには、以下の設定を定義します。

7.  **プライマリドメイン**(必須)。 プライマリ ドメインは、XMPP パートナーの基本ドメインです。 たとえば、XMPP パートナーのドメイン名として **fabrikam.com** と入力します。 これは必須のエントリです。

8.  **説明**。 説明は、この特定の構成に関するメモまたはその他の識別情報を対象としています。 このエントリは省略可能です。

9.  **追加のドメイン**。 追加のドメインは、許可された XMPP 通信の一部として含める必要がある、XMPP パートナーのドメインの一部であるドメインです。 たとえば、プライマリドメインが**fabrikam.com**の場合は、xmpp を使用して通信する fabrikam.com の下にある他のすべてのドメインを一覧表示します。 たとえば、fabrikam のメイン XMPP ドメインの下に、企業の XMPP ドメインと Information Technologies XMPP ドメインの**corp.fabrikam.com**と**it.fabrikam.com**を入力することができます。

10. **パートナーの種類**。 **パートナーの種類**は必須の設定であり、ドロップダウンメニューから選択できる選択肢は3つあります。 連絡先を追加できるようにするには、次のいずれかを選択する必要があります。 次の中から選択できます。
    
      - **フェデレーション**。 **フェデレーション**パートナーの種類は、Lync server または Office Communications Server 2007 R2 パートナー展開との間の信頼された接続です。
    
      - **パブリック確認済み**。 **一般に確認**されたパートナーとは、プロバイダーによって確認された展開の一部である連絡先をユーザーの連絡先リストに追加できることです。 招待は、Lync ユーザーから送信できます。または Lync ユーザーは、パートナー連絡先からの招待を受け入れることができます。
    
      - **パブリック未確認**。 **公開**されていない関係とは、2つの展開間で確立および検証可能な状態がないことを意味します。 Lync ユーザーは、その連絡先に対して未確認の連絡先を招待して、Lync ユーザーを連絡先リストに追加できるようにする必要があります。 たとえば、Google GTalk は、Lync Server に関連付けられているパブリックに検証された XMPP サービスではありません。 Lync ユーザーから明示的な招待が送信されていない限り、GTalk ユーザーは Lync ユーザーを連絡先として追加することはできません。

11. ストリーム ネゴシエーションとセキュリティ方式についてのメモ - トランスポート層セキュリティ (TLS) と簡易認証およびセキュリティ層 (SASL):
    
    **XMPP Standards Foundation** (XSF) と**インターネット技術標準化委員会** (IETF) は、TLS クライアント証明書、TLS サーバー証明書、および SASL メカニズムの使用と管理についての一連の規則と標準規格を定義しています。TLS と SASL の使用は、XMPP ストリームをセキュリティ保護するうえで必要な過程です。XMPP 標準規格ドキュメント **XEP-0178** では、以下のように記されています。「特に XMPP サービスが TLS でネゴシエーションが必須であると示されているとき、PKIX 証明書と SASL 外部メカニズムの使用での推奨プロトコル フローを指定します。」この XSF ドキュメントでの PKIX とは、公開キー基盤 (PKI) のことです。
    
    XMPP 要件についての詳細は、XSF ドキュメント XEP-0178 を参照してください。 詳細は、「XEP-0178: Best Practices for Use of SASL EXTERNAL with Certificates」を参照してください。 <http://xmpp.org/extensions/xep-0178.html>
    
    IETF ドキュメント「拡張可能なメッセージングおよびプレゼンスプロトコル (XMPP): Core」、Section 5.0、STARTTLS ネゴシエーション<https://tools.ietf.org/html/rfc6120>」を参照してください。
    
      - **TLS ネゴシエーション**。 XMPP サービスでは、TLS を必須にすることも任意にすることもできます。 また、TLS がサポートされないように定義することもできます。 [任意] を選択すると、ネゴシエーションが必須であるかどうかの決定は XMPP サービスに委ねられます。 使用可能なすべての設定と詳細を表示するには、有効でなく既知のエラーの構成を含む、SASL、TLS、およびダイヤルバックのネゴシエーションに関するすべての情報を表示します。「 [Lync Server 2013 の XMPP フェデレーションパートナーのネゴシエーション設定](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md)」を参照してください。
        
          - <span></span>  
            **必須**。 XMPP サービスは TLS ネゴシエーションを必要とします。
        
          - <span></span>  
            **省略可能**です。 XMPP サービスは、TLS がネゴシエーション必須であることを示します。
        
          - <span></span>  
            **サポートされません**。 XMPP サービスは TLS をサポートしません。
    
      - **SASL ネゴシエーション**。 XMPP サービスでは、SASL を必須にすることも任意にすることもできます。 また、SASL がサポートされないように定義することもできます。 [任意] を選択すると、ネゴシエーションが必須であるかどうかの決定は XMPP サービスに委ねられます。
        
        <div>
        

        > [!WARNING]  
        > SASL は TLS を必要とします。SASL を使用するには、TLS を必須とするかオプションにする必要があります。SASL を必須またはオプションと定義するすべての構成は、TLS サポートを持っている必要があります。変更を保存する目的で [<STRONG>コミット</STRONG>] をクリックしたとき、TLS を必須またはオプションに設定していなかった場合は、SASL には TLS サポートが必要という警告が表示され、変更は保存されません。エラーを解決するには、TLS を [<STRONG>必須</STRONG>] または [<STRONG>オプション</STRONG>] に設定します。SASL の使用がオプションで、TLS ネゴシエーションのサポートができない場合は、SASL ネゴシエーションを [<STRONG>サポートなし</STRONG>] に設定する必要があります。サービスが中断しないように、TLS と SASL で適切なネゴシエーション ストリームがなにか、XMPP サービスに確認してください。

        
        </div>
        
          - <span></span>  
            **必須**。 XMPP サービスは SASL ネゴシエーションを必要とします。
        
          - <span></span>  
            **省略可能**です。 XMPP サービスは、SASL がネゴシエーション必須であることを示します。
        
          - <span></span>  
            **サポートされません**。 XMPP サービスは SASL をサポートしません。
    
      - **ダイヤルバックネゴシエーション**。 ダイヤルバックネゴシエーションは、ドキュメント**Xep-220: サーバーダイヤル** <http://xmpp.org/extensions/xep-0220.html>インの XSF によって定義されます。 サーバーダイヤルアウトプロセスは、ドメインネームシステム (DNS) と権限のあるサーバーを使用して、要求が有効な XMPP パートナーから来たものであることを確認します。 これを行うために、送信元サーバーは、生成されたダイヤルバックキーを使用して特定の種類のメッセージを作成し、DNS で受信側サーバーを検索します。 送信元サーバーは、生成された DNS 参照 (受信側サーバーなど) に、XML ストリームでキーを送信します。 XML ストリームの上でキーを受け取ると、受信側サーバーは送信元のサーバーに応答しませんが、既知の権限のあるサーバーにキーを送信します。 権限のあるサーバーは、キーが有効であるか無効であるかを確認します。 有効でない場合、受信側のサーバーは送信元のサーバーに応答しません。 キーが有効である場合、受信側のサーバーは、送信元のサーバーに id とキーが有効であることを通知し、会話を開始できます。
        
        **ダイヤルバック ネゴシエーション**には、2 つの状態があります。
        
          - <span></span>  
            **True**。 発信元サーバーから要求を受信した場合、XMPP サーバーはダイヤルバックネゴシエーションを使用するように構成されます。
        
          - <span></span>  
            **False を返し**ます。 XMPP サーバーはダイヤルバックネゴシエーションを使用するように構成されておらず、発信元サーバーから要求を受信した場合は無視されます。

</div>

</div>

<span> </span>

</div>

</div>

</div>

