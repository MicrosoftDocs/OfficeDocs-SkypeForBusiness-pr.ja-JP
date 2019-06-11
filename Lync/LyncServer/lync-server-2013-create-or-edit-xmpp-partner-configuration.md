---
title: 'Lync Server 2013: XMPP パートナー構成の作成または編集'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or edit XMPP partner configuration
ms:assetid: 362dbe5e-8ee9-4aba-8c26-5907312b4a60
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552447(v=OCS.15)
ms:contentKeyID: 48679558
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 488fa84a3f24133c6ebcde4467cacdbdcffe7ff8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833836"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-edit-xmpp-partner-configuration-in-lync-server-2013"></a>Lync Server 2013 での XMPP パートナー構成の作成または編集

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-09-03_

Microsoft Lync Server 2013 は、エッジサーバー上の拡張メッセージングおよびプレゼンスプロトコル (XMPP) プロキシと、フロントエンドサーバーまたはフロントエンドプール上の XMPP ゲートウェイを統合します。 他の XMPP の展開からの接続を許可するには、Lync Server コントロールパネルで XMPP を設定する必要があります。 設定は XMPP ドメイン単位で構成します。 新しいパートナーの関連付けを作成するには、次の操作を行います。

<div>

## <a name="to-create-a-new-federated-partner-or-edit-an-existing-configuration"></a>新しいフェデレーションパートナーを作成する、または既存の構成を編集するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで、[**フェデレーションと外部アクセス**] をクリックし、[ **Xmpp フェデレーションパートナー**] をクリックします。

4.  新しい構成を作成するには、[**新規**] をクリックします。

5.  既存の構成を編集するには、構成を選択して [**編集**] をクリックします。

6.  **Xmpp フェデレーションパートナー**の構成を作成または編集するには、次の設定を定義します。

7.  **プライマリドメイン**(必須)。 プライマリドメインは、XMPP パートナーのベースドメインです。 たとえば、XMPP パートナードメイン名の**fabrikam.com**を入力します。 このエントリは必須です。

8.  **説明**。 説明は、この特定の構成のメモまたはその他の識別情報に使用されます。 このエントリは省略可能です。

9.  **追加ドメイン**。 さらに多くのドメインは、XMPP パートナーのドメインの一部であり、許可されている XMPP 通信の一部として含める必要があります。 たとえば、プライマリドメインが**fabrikam.com**の場合は、fabrikam.com の下にある他のすべてのドメインを一覧表示します。これにより、xmpp で通信することができます。 たとえば、企業の XMPP ドメインと、corp.fabrikam.com のメイン XMPP ドメインの下にある Information Technologies XMPP ドメインの場合は、「 **** 」と「 **it.fabrikam.com** 」と入力できます。

10. **パートナーの種類**。 **パートナーの種類**は必須の設定であり、ドロップダウンメニューで3つの選択肢を選ぶことができます。 追加できる連絡先を説明して適用するには、次のいずれかを選択する必要があります。 次のいずれかを選択できます。
    
      - **フェデレーション**。 **フェデレーション**パートナーの種類は、Lync Server または Office Communications Server 2007 R2 パートナー展開との間の信頼できる接続です。
    
      - **公開確認済み**。 **公開確認**パートナーとは、プロバイダーによって確認された展開の一部である連絡先をユーザーの連絡先リストに追加できることです。 招待は Lync ユーザーから送信できます。また、Lync ユーザーはパートナーの連絡先から招待を受け入れることができます。
    
      - **公開未検証**。 **公開**されていないリレーションシップは、2つの展開間で確立され、検証可能な状態ではないことを意味します。 Lync ユーザーは、連絡先リストに Lync ユーザーを追加できるように、その連絡先の未確認の連絡先を招待する必要があります。 たとえば、Google GTalk は、Lync Server に関連しているのと同じように、公開確認済みの XMPP サービスではありません。 ユーザーは、Lync ユーザーからの明示的な招待が送信されていない場合、Lync ユーザーを連絡先として追加することはできません。

11. ストリームのネゴシエーションとセキュリティメソッドトランスポート層セキュリティ (TLS) とソフトウェア認証とセキュリティレイヤー (SASL) についての注意事項:
    
    **Xmpp 規格ファンデーション**(XSF) と**Internet Engineering Task Force** (IETF) は、tls クライアント証明書、tls サーバー証明書、および SASL メカニズムを使用および管理するためのルールと標準のセットを定義しています。 TLS と SASL の使用は、XMPP ストリームをセキュリティで保護するために必要なプロセスです。 XMPP 標準ドキュメント**Xmpp-0178**では、PKIX 証明書を使った SASL 外部機構の使用に推奨されるプロトコルフローを指定します。特に、xmpp サービスで TLS が必須であることを示すのは、TLS が必須であることを示しています。 PKIX は、XSF ドキュメントで説明されているように、公開キー基盤 (PKI とも呼ばれます) を指します。
    
    XEP の要件の詳細については、「XSF ドキュメント XEP-0178」を参照してください。 詳細については、「XEP-0178: 証明書付きの SASL 外部を使用するためのベストプラクティス」を参照してください。 <http://xmpp.org/extensions/xep-0178.html>
    
    IETF ドキュメント「拡張可能なメッセージングとプレゼンスプロトコル (XMPP): Core "、Section 5.0、STARTTLS のネゴシエーション<http://tools.ietf.org/html/rfc6120>」を参照してください。
    
      - **TLS ネゴシエーション**。 TLS ネゴシエーションルールを定義します。 XMPP サービスでは TLS が必要になる場合があります。 TLS をオプションにすることも、TLS がサポートされないことを定義することもできます。 [オプションを選択すると、必須のネゴシエーションの意思決定を行うための XMPP サービスの要件が残ります。 使用可能な SASL、TLS、およびダイヤルバックのネゴシエーションに関するすべての設定と詳細を表示するには、「有効なエラーと既知のエラー構成」を参照してください。詳しくは、「 [Lync Server 2013 での XMPP フェデレーションパートナーのネゴシエーション設定](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md)」をご覧ください。
        
          - <span></span>  
            **必須**。 XMPP サービスには TLS ネゴシエーションが必要です。
        
          - <span></span>  
            **省略可能**。 XMPP サービスは、TLS が必須からネゴシエートされていることを示します。
        
          - <span></span>  
            **サポートされません**。 XMPP サービスでは、TLS はサポートされていません。
    
      - **SASL ネゴシエーション**。 SASL ネゴシエーション規則を定義します。 XMPP サービスでは、SASL を要求できるほか、SASL をオプションとして使うこともできます。また、SASL がサポートされていないことを定義することもできます。 [オプションを選択すると、必須のネゴシエーションの意思決定を行うために、パートナーの XMPP サービスまでの要件が残ります。
        
        <div>
        

        > [!WARNING]  
        > SASL には TLS が必要です。 SASL を使うには、TLS が必要かオプションである必要があります。 SASL を required または optional として定義する構成では、TLS サポートを利用する必要があります。 [<STRONG>コミット</STRONG>] をクリックして変更を保存するときに、tls を required に設定していない場合は、SASL に tls サポートが必要であり、変更が保存されていないことを示す警告が表示されます。 エラーを解決するには、TLS を<STRONG>Required</STRONG>または<STRONG>Optional</STRONG>に設定します。 SASL がオプションであり、TLS ネゴシエーションがサポートされていない場合は、SASL ネゴシエーションを<STRONG>サポートしない</STRONG>ように設定する必要があります。 XMPP サービスで、TLS および SASL に対応する適切なネゴシエーションストリームが必要であることを確認します。また、サービスの中断が発生します。

        
        </div>
        
          - <span></span>  
            **必須**。 XMPP サービスでは、SASL ネゴシエーションが必要です。
        
          - <span></span>  
            **省略可能**。 XMPP サービスは、SASL のネゴシエーションが必須であることを示します。
        
          - <span></span>  
            **サポートされません**。 XMPP サービスでは、SASL はサポートされていません。
    
      - **ダイヤルバックのネゴシエーション**。 ダイヤルバックのネゴシエーションは、ドキュメント**Xep-220: サーバーのダイヤルバック** <http://xmpp.org/extensions/xep-0220.html>の XSF で定義されています。 サーバーコールバックプロセスでは、ドメインネームシステム (DNS) と権限を持つサーバーを使用して、要求が有効な XMPP パートナーから送信されたことを確認します。 これを行うために、発信元のサーバーは、生成されたダイヤルバックキーを使用して、特定の種類のメッセージを作成し、DNS で受信側サーバーを検索します。 送信元のサーバーは、受信側サーバーであると思われるように、XML ストリームのキーを結果の DNS 参照に送信します。 XML ストリームを介してキーを受け取ると、受信側サーバーは元のサーバーには応答しませんが、既知の権限を持つサーバーにキーを送信します。 権限を持つサーバーは、キーが有効であるか無効であるかを確認します。 有効でない場合、受信側サーバーは元のサーバーには応答しません。 キーが有効である場合、受信側のサーバーは、id とキーが有効であり、会話を開始できます。
        
        **ダイヤルバックのネゴシエーション**には、次の2つの有効な状態があります。
        
          - <span></span>  
            **True**。 発信元のサーバーから要求を受信する必要がある場合に、ダイヤルバックのネゴシエーションを使用するように XMPP サーバーが構成されている
        
          - <span></span>  
            **False**。 XMPP サーバーは、ダイヤルバックのネゴシエーションを使用するように構成されておらず、発信元のサーバーから要求を受信した場合、無視されます。

</div>

</div>

<span> </span>

</div>

</div>

</div>

