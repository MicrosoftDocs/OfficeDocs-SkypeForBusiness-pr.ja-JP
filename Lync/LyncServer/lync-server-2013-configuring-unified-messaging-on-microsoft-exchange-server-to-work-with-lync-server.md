---
title: 'Lync Server 2013: Lync Server で動作するように Microsoft Exchange Server でユニファイドメッセージングを構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Unified Messaging on Microsoft Exchange Server to work with Lync Server 2013
ms:assetid: 058da9c4-23af-4ddb-9f63-70133a8aafc6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398106(v=OCS.15)
ms:contentKeyID: 48183289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2cbb859a3cd9f49791eb7b959a59c00c38db6336
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "41995972"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-unified-messaging-on-microsoft-exchange-server-to-work-with-lync-server-2013"></a>Lync Server 2013 で動作するように Microsoft Exchange Server でユニファイドメッセージングを構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-11_

<div>


> [!IMPORTANT]  
> Exchange ユニファイドメッセージング (UM) を使用して、エンタープライズ Voip ユーザーの通話応答、Outlook Voice Access、または自動応答サービスを提供する場合は、「計画」のドキュメントの「 <A href="lync-server-2013-planning-for-exchange-unified-messaging-integration.md">Lync Server 2013 での Exchange ユニファイドメッセージング統合の計画</A>」を読んで、このセクションの指示に従います。



</div>

エンタープライズ Voip を使用するように Exchange ユニファイドメッセージング (UM) を構成するには、次のタスクを実行する必要があります。

  - Exchange ユニファイドメッセージング (UM) サービスを実行しているサーバーで証明書を構成する
    
    <div>
    

    > [!NOTE]  
    > すべてのクライアントアクセスサーバーおよびメールボックスサーバーをすべての UM SIP URI ダイヤルプランに追加します。 そうでない場合は、発信通話のルーティングが期待どおりに機能しません。

    
    </div>

  - 必要に応じて、1つまたは複数の UM SIP URI ダイヤルプランと、サブスクライバーアクセス用の電話番号を作成し、対応する Lync Server のダイヤルプランを作成します。

  - 次のように、 **exchucutil. ps1**スクリプトを使用します。
    
      - UM IP ゲートウェイを作成します。
    
      - UM ハント グループを作成します。
    
      - UM Active Directory ドメインサービスオブジェクトを読み取るための Lync Server 2013 アクセス許可を付与します。

  - UM 自動応答オブジェクトを作成します。

  - サブスクライバーアクセスオブジェクトを作成します。

  - 各ユーザーの SIP URI を作成し、ユーザーと UM SIP URI ダイヤルプランを関連付けます。

<div>

## <a name="requirements-and-recommendations"></a>要件と推奨事項

開始する前に、このセクションのドキュメントでは、次の Exchange 2013 の役割 (クライアントアクセスとメールボックス) を展開していることを前提としています。 Microsoft Exchange Server 2013 では、Exchange UM はこれらのサーバー上でサービスとして実行されます。

Exchange 2013 の展開の詳細については、「」の「Exchange 2013 TechNet ライブラリ」を参照してください。[http://go.microsoft.com/fwlink/p/?LinkId=266637](http://go.microsoft.com/fwlink/p/?linkid=266637)

以下の点にも注意してください。

  - Exchange UM が複数のフォレストにインストールされている場合は、Exchange サーバーの統合手順を各 UM フォレストに対して実行する必要があります。 また、Lync Server 2013 が展開されているフォレストを信頼するように各 UM フォレストを構成する必要があります。また、Lync Server 2013 が展開されているフォレストは、各 UM フォレストを信頼するように構成する必要があります。

  - 統合手順は、ユニファイドメッセージングサービスが実行されている Exchange サーバーの役割と、Lync Server 2013 を実行しているサーバーの両方で実行されます。 Lync Server 2013 の統合手順を実行する前に、Exchange Server ユニファイドメッセージングの統合手順を実行する必要があります。
    
    <div>
    

    > [!NOTE]  
    > どのサーバーに対してどの統合手順が実行されるか、および管理者の役割がどのようになるかを確認するには、「<A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">オンプレミスのユニファイドメッセージングと Lync Server 2013 を統合するための展開プロセス</A>」を参照してください。

    
    </div>

Exchange UM を実行している各サーバーで、次のツールが使用可能である必要があります。

  - Exchange 管理シェル

  - **exchucutil.ps1** スクリプト。このスクリプトは以下のタスクを実行します。
    
      - 各 Lync Server 2013 の UM IP ゲートウェイを作成します。
    
      - 各ゲートウェイのハント グループを作成します。 各ハントグループのパイロット id は、ゲートウェイに関連付けられているフロントエンドプールまたは Standard Edition サーバーによって使用される UM SIP URI ダイヤルプランを指定します。
    
      - Active Directory ドメインサービスの Exchange UM オブジェクトを読み取るための Lync Server 2013 アクセス許可を付与します。

</div>

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [Microsoft Exchange Server ユニファイドメッセージングを実行しているサーバーで証明書を構成する](lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md)

  - [Lync Server 2013 の Microsoft Exchange でのユニファイドメッセージングの構成](lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

