---
title: Lync Server 2013 hosted Exchange UM 統合のサポート
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Support for hosted Exchange UM integration
ms:assetid: c7573ec3-013c-48d9-b59b-2a5427e6da35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398821(v=OCS.15)
ms:contentKeyID: 48185376
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 714b10cfc10e101439670eda6ff3810be06b8599
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142483"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="support-for-hosted-exchange-um-integration-in-lync-server-2013"></a>Lync Server 2013 での hosted Exchange UM 統合のサポート

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-21_

Lync Server 2013 ExUM ルーティングアプリケーションは、オンプレミス環境での Exchange ユニファイドメッセージング (UM) との統合をサポートしています。これは、Lync Server の2013と Exchange UM の両方が企業内でローカルにインストールされているか、または、によってホストされる Exchange UM と共存しています。次の図に示すように、サービスプロバイダー。

![オンプレミスの Lync Server Exchange UM 展開](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "オンプレミスの Lync Server Exchange UM 展開")

次のモードがサポートされています。

  - **オンプレミスモード**   Lync Server 2013 と Exchange UM は、どちらも企業内のローカルサーバーに展開されます。

  - **クロスプレミスモード**   Lync Server 2013 は、企業内のローカルサーバーに展開され、exchange UM は Microsoft Exchange online データセンターなどのオンラインサービスプロバイダーの施設でホストされます。

  - **混在モード**   Lync Server 2013 の展開には、企業内の Microsoft Exchange Server を実行しているローカルサーバーに所属するユーザーメールボックスと、ホストされている Exchange サービスデータセンターに所属する一部のメールボックスがあります。
    
    <div>
    

    > [!NOTE]  
    > 混在モードは、評価時に、ユーザーをホストされた Exchange UM に移行するための移行ソリューションとして、または他のユーザーの移行後に社内の Exchange UM サービスを社内に保持することを選択した場合の永続的なソリューションとして使用できます。

    
    </div>

Lync Server 2013 を hosted Exchange UM と統合するには、*共有 SIP アドレススペース*(*分割ドメイン*とも呼ばれます) を構成する必要があります。 この構成では、Lync Server 2013 とサードパーティのホストされた Exchange UM サービスプロバイダーの両方が、同じ SIP ドメインアドレススペースにアクセスできます。 詳細については、「計画」のドキュメントの「 [Lync Server 2013 の Hosted EXCHANGE UM 統合アーキテクチャ](lync-server-2013-hosted-exchange-um-integration-architecture.md)」を参照してください。

</div>

<span> </span>

</div>

</div>

</div>

