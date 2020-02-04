---
title: 'Lync Server 2013: ホスト型 Exchange UM 統合のサポート'
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
ms.openlocfilehash: 24139ad5294bf908a85b797300397fa8b2ac9140
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764383"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="support-for-hosted-exchange-um-integration-in-lync-server-2013"></a>Lync Server 2013 でのホスト型 Exchange UM 統合のサポート

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-21_

Lync server 2013 ExUM ルーティングアプリケーションでは、オンプレミス環境での Exchange ユニファイドメッセージング (UM) との統合をサポートしています。ここでは、Lync Server 2013 と Exchange UM が企業内のローカルにインストールされている場合、または a によってホストされている Exchange UM を使用している場合です。次の図に示すように、サービスプロバイダ。

![オンプレミスの Lync Server Exchange UM の展開](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "オンプレミスの Lync Server Exchange UM の展開")

次のモードがサポートされています。

  - **オンプレミスモード**   の Lync Server 2013 および Exchange UM は、両方とも企業内のローカルサーバーに展開されます。

  - **クロスプレミスモード**   の Lync Server 2013 は、企業内のローカルサーバーに展開され、exchange UM は Microsoft Exchange online のデータセンターなどのオンラインサービスプロバイダーの機能でホストされます。

  - **混在モード**   Lync Server 2013 の展開では、組織内の Microsoft Exchange Server を実行しているローカルサーバー上の一部のユーザーメールボックスと、ホスティングされている exchange service データセンターにある一部のメールボックスを使用しています。
    
    <div>
    

    > [!NOTE]  
    > 混在モードは、評価中にユーザーをホストされた Exchange UM に移行するときに、移行ソリューションとして使用することができます。また、他のユーザーを移行した後で、一部のユーザーの Exchange UM サービスをオンプレミスのままにしておくと、永続的な解決策として使用できます。

    
    </div>

Lync Server 2013 をホストされた Exchange UM と統合するには、*共有 SIP アドレス空間*(*分割ドメイン*とも呼ばれます) を構成する必要があります。 この構成では、Lync Server 2013 とサードパーティがホストする Exchange UM サービスプロバイダーは両方とも、同じ SIP ドメインアドレス空間にアクセスできます。 詳細については、計画ドキュメントの「 [Lync Server 2013 の Hosted EXCHANGE UM 統合アーキテクチャ](lync-server-2013-hosted-exchange-um-integration-architecture.md)」を参照してください。

</div>

<span> </span>

</div>

</div>

</div>

