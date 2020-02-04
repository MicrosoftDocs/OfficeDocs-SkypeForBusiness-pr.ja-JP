---
title: 'Lync Server 2013: 内部設置型ユニファイド メッセージングを統合するためのガイドライン'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Guidelines for integrating on-premises Unified Messaging and Lync Server
ms:assetid: 829ac017-6907-40f9-be22-787a28eae0ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398656(v=OCS.15)
ms:contentKeyID: 48184681
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f3e57245f0a8edf5b545f9a67547e6be6f63399
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739617"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="guidelines-for-integrating-on-premises-unified-messaging-and-lync-server-2013"></a>内部設置型ユニファイド メッセージングおよび Lync Server 2013 を統合するためのガイドライン

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-25_

エンタープライズ Voip を展開する際のガイドラインとベストプラクティスを次に示します。

<div>


> [!IMPORTANT]  
> Exchange ユニファイドメッセージング (UM) は、UCMA 4 も使用している場合にのみ、IPv6 をサポートします。



</div>

  - Lync Server 2013 Standard Edition サーバーまたはフロントエンドプールを展開します。 インストールの詳細については、「展開ドキュメントに[Lync Server 2013 を展開](lync-server-2013-deploying-lync-server.md)する」を参照してください。

  - Exchange 管理者と協力して、どのタスクが実行されるかを確認して、円滑かつ確実に統合されるようにします。

  - Exchange UM のユーザーを有効にする exchange の各ユニファイドメッセージング (UM) フォレストに Exchange メールボックスサーバーの役割を展開します。 Exchange server の役割のインストールの詳細については、Microsoft Exchange Server 2013 に関するドキュメントを参照してください。
    
    <div>
    

    > [!IMPORTANT]  
    > Exchange ユニファイドメッセージング (UM) がインストールされている場合は、自己署名証明書を使用するように構成されています。<BR>ただし、自己署名された証明書では、Lync Server 2013 と Exchange UM が相互に信頼することはできません。そのため、両方のサーバーが信頼する証明機関の証明書を個別に要求する必要があります。

    
    </div>

  - Lync Server 2013 および Exchange UM がさまざまなフォレストにインストールされている場合は、各 Exchange フォレストが Lync Server 2013 フォレストと Lync Server 2013 フォレストを信頼するように構成して、各 Exchange フォレストを信頼するようにします。 また、ユーザーの Exchange UM 設定を Lync Server 2013 フォレストのユーザーオブジェクトに対して設定します。通常は、スクリプトまたは Id ライフサイクルマネージャー (ILM) などのフォレスト間ツールを使用します。

  - 必要に応じて、Exchange 管理コンソールをインストールしてユニファイドメッセージングサーバーを管理します。

  - Outlook Voice Access および自動応答の有効な電話番号を取得します。

  - Microsoft Exchange Server 2010 Service Pack 1 (SP1) より前のバージョンの Exchange UM を使用している場合は、Exchange UM SIP URI ダイヤルプランとエンタープライズボイスダイヤルプランの名前を調整します。

<div>

## <a name="deploying-redundant-exchange-um-servers"></a>冗長な Exchange UM サーバーの展開

<div>


> [!IMPORTANT]  
> 組織に対して構成した各 Exchange UM SIP URI ダイヤルプランについて、Exchange UM サービスが実行されている最低2台のサーバーを展開することをお勧めします。 拡張された容量の提供に加えて、冗長サーバーの展開によって可用性が高まります。 サーバーに障害が発生した場合、Lync Server 2013 を別のサーバーにフェールオーバーするように構成できます。



</div>

次に示す構成の例では、Exchange UM の回復性が提供されています。

**例 1: Exchange UM の回復性**

![Exchange UM の例 1](images/Gg398656.3644b847-0847-4550-a989-e3fc51de5c4b(OCS.15).jpg "Exchange UM の例 1")

例1では、Exchange UM サーバー1と2が、データセンターで有効になっています。また、Exchange UM サーバー3と4は、ダブリンデータセンターで有効になっています。 Tua で Exchange UM が停止した場合、サーバー1と2のドメインネームシステム (DNS) A レコードは、それぞれサーバー3と4をポイントするように構成する必要があります。 Dublin で Exchange UM が停止した場合は、サーバー3および4の DNS A レコードをそれぞれサーバー1と2にポイントするように構成する必要があります。

<div>


> [!NOTE]  
> たとえば、1つの Exchange UM サーバーに次のいずれかの証明書を割り当てる必要があります。 
> <UL>
> <LI>
> <P>サブジェクトの別名 (SAN) でワイルドカード付きの証明書を使用します。</P>
> <LI>
> <P>SAN の4つの Exchange UM サーバーのそれぞれについて、完全修飾ドメイン名 (FQDN) を入力します。</P></LI></UL>



</div>

**例 2: Exchange UM の回復性**

![Exchange UM の例 2](images/Gg398656.15754273-306e-448d-b258-84bc2936a2e8(OCS.15).jpg "Exchange UM の例 2")

例2の [通常の運用条件] では、データセンターでの Exchange UM サーバー1と2が有効になっています。また、Exchange UM サーバー3と4は、ダブリンデータセンターで有効になっています。 この4つのサーバーはすべて、ユーザーの SIP URI ダイヤルプランに含まれています。ただし、サーバー3と4は無効です。 Tukwila Exchange UM が停止した場合は、Exchange um サーバー1と2を無効にして、exchange UM サーバー3と4を有効にする必要があります。これにより、exchange um トラフィックが Dublin のサーバーにルーティングされるようになります。

Exchange 2013 でユニファイドメッセージングを有効または無効にする方法について詳しくは、「Exchange 2013 UM と[http://go.microsoft.com/fwlink/p/?LinkId=265372](http://go.microsoft.com/fwlink/p/?linkid=265372)Lync Server の統合」をご覧ください。

Microsoft Exchange Server 2010 でユニファイドメッセージングを有効または無効にする方法の詳細については、以下を参照してください。

  - 「Exchange 2010 でユニファイドメッセージングを有効[http://go.microsoft.com/fwlink/p/?LinkId=204418](http://go.microsoft.com/fwlink/p/?linkid=204418)にする」をご覧ください。

  - "Exchange 2010 でユニファイドメッセージングを無効[http://go.microsoft.com/fwlink/p/?LinkId=204416](http://go.microsoft.com/fwlink/p/?linkid=204416)にする" をオンにします。

</div>

<div>

## <a name="see-also"></a>関連項目


[内部設置型ユニファイド メッセージングと Lync Server 2013 を統合するための展開プロセス](lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

