---
title: 'Lync Server 2013: Lync Server と連動させるための Microsoft Exchange Server のユニファイド メッセージングの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Unified Messaging on Microsoft Exchange Server to work with Lync Server 2013
ms:assetid: 058da9c4-23af-4ddb-9f63-70133a8aafc6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398106(v=OCS.15)
ms:contentKeyID: 48183289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 461d822862e837879f1feb2d3f980b816aae5280
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840166"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-unified-messaging-on-microsoft-exchange-server-to-work-with-lync-server-2013"></a>Lync Server 2013 と連動させるための Microsoft Exchange Server のユニファイド メッセージングの構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-11_

<div>


> [!IMPORTANT]  
> Exchange ユニファイドメッセージング (UM) を使用して、通話応答、Outlook Voice Access、またはエンタープライズボイスユーザー向けの自動応答サービスを提供する場合は、計画で「 <A href="lync-server-2013-planning-for-exchange-unified-messaging-integration.md">Lync Server 2013 での Exchange ユニファイドメッセージングの統合の計画</A>」を参照してください。ドキュメントを参照して、このセクションの手順に従います。



</div>

エンタープライズ Voip と連携するように Exchange ユニファイドメッセージング (UM) を構成するには、次の作業を行う必要があります。

  - Exchange ユニファイドメッセージング (UM) サービスを実行しているサーバーで証明書を構成する
    
    <div>
    

    > [!NOTE]  
    > すべてのクライアントアクセスとメールボックスサーバーを UM SIP のすべての URI ダイヤルプランに追加します。 そうしないと、発信通話のルーティングが予期したとおりに機能しません。

    
    </div>

  - 必要に応じて、サブスクライバーアクセス用電話番号と共に1つまたは複数の UM SIP URI ダイヤルプランを作成して、対応する Lync Server ダイヤルプランを作成します。

  - 次のような操作を実行するために**exchucutil**スクリプトを使います。
    
      - UM IP ゲートウェイを作成します。
    
      - UM ハントグループを作成します。
    
      - UM Active Directory ドメインサービスオブジェクトを読み取るために Lync Server 2013 のアクセス許可を付与します。

  - UM 自動応答オブジェクトを作成します。

  - サブスクライバーアクセスオブジェクトを作成します。

  - ユーザーごとに SIP URI を作成し、UM SIP URI ダイヤルプランを使用してユーザーを関連付けます。

<div>

## <a name="requirements-and-recommendations"></a>要件と推奨事項

作業を始める前に、このセクションのドキュメントでは、次の Exchange 2013 の役割 (クライアントアクセスとメールボックス) が展開されていることを前提としています。 Microsoft Exchange Server 2013 では、Exchange UM はこれらのサーバーでサービスとして実行されます。

Exchange 2013 の展開について詳しくは2013、[http://go.microsoft.com/fwlink/p/?LinkId=266637](http://go.microsoft.com/fwlink/p/?linkid=266637)

次の点にも注意してください。

  - Exchange UM が複数のフォレストにインストールされている場合は、各 UM フォレストで Exchange Server の統合手順を実行する必要があります。 さらに、各 UM フォレストが、Lync Server 2013 が展開されているフォレストを信頼するように構成されている必要があります。また、Lync Server 2013 が展開されているフォレストは、各 UM フォレストを信頼するように構成されている必要があります。

  - 統合手順は、ユニファイドメッセージングサービスが実行されている Exchange Server の役割と、Lync Server 2013 を実行しているサーバーで実行されます。 Lync Server 2013 の統合手順を実行する前に、Exchange Server ユニファイドメッセージング統合の手順を実行する必要があります。
    
    <div>
    

    > [!NOTE]  
    > どのサーバーに対して実行される統合手順と管理者の役割を確認するには、「<A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">オンプレミスユニファイドメッセージングと Lync Server 2013 を統合する展開プロセス</A>」を参照してください。

    
    </div>

Exchange UM を実行している各サーバーでは、次のツールを使用できる必要があります。

  - Exchange 管理シェル

  - スクリプト**exchucutil**は、次のタスクを実行します。
    
      - 各 Lync Server 2013 に対して UM IP ゲートウェイを作成します。
    
      - 各ゲートウェイのハントグループを作成します。 各ハントグループのパイロット識別子は、ゲートウェイに関連付けられているフロントエンドプールまたは Standard Edition サーバーで使用される UM SIP URI ダイヤルプランを指定します。
    
      - Active Directory ドメインサービスで Exchange UM オブジェクトを読み取るための Lync Server 2013 アクセス許可を付与します。

</div>

<div>

## <a name="in-this-section"></a>このセクション中

  - [Microsoft Exchange Server ユニファイドメッセージングを実行しているサーバーで証明書を構成する](lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md)

  - [Lync Server 2013 向けの Microsoft Exchange でユニファイドメッセージングを構成する](lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

