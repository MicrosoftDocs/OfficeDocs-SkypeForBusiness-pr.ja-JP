---
title: 'Lync Server 2013: 存続可能ブランチアプライアンスまたはサーバーの展開'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying a Survivable Branch Appliance or Server
ms:assetid: cb780c14-dc5f-41ba-8092-f20ae905bd16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398849(v=OCS.15)
ms:contentKeyID: 48185643
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 258f53cf16287b29c739c5a232376fa629b401f6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531354"
---
# <a name="deploying-a-survivable-branch-appliance-or-server-with-lync-server-2013"></a>Lync Server 2013 を使用した存続可能ブランチアプライアンスまたはサーバーの展開

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-12-10_

弾性エンタープライズ Voip は、ブランチサイトの復元 (つまり、セントラルサイトへのリンクが利用できなくなった場合に、ブランチサイトのユーザーに継続的なエンタープライズ Voip サービスを提供する機能) を指します。

小規模および中規模のブランチサイト (25 ~ 1000 ユーザーのブランチサイト) では、存続可能 Branch Appliance を展開することをお勧めします。このアプライアンスは、組み込みの PSTN ゲートウェイまたは電話サービスプロバイダーへの SIP トランクを使用して、公衆交換電話網 (PSTN) 通話を終了します。 存続可能 Branch Appliance は、Windows Server 2008 R2 オペレーティングシステム、Lync Server 2013 レジストラー、仲介サーバーソフトウェア、および PSTN ゲートウェイをすべて単一のアプライアンスシャーシに搭載するブレードサーバーを含むサードパーティ製のデバイスです。

1000 ~ 5000 ユーザーが存在し、回復可能な WAN がないブランチサイトでは、PSTN ゲートウェイまたは電話サービスプロバイダーへの SIP トランクのどちらかに接続された存続可能ブランチサーバーをお勧めします。 存続可能ブランチサーバーは、レジストラーと仲介サーバーソフトウェアがインストールされている Windows Server ベースのコンピューターです。

<div>


> [!NOTE]  
> 5000ユーザーと専用の Lync Server 管理者がいるブランチサイトでは、中央サイトとは別の完全な Lync Server 2013 の展開をお勧めします。<BR>前提条件と計画の考慮事項を含む、組織内のブランチサイトに最適な復元ソリューションを選択する方法の詳細については、「計画」のドキュメントの「 <A href="lync-server-2013-branch-site-resiliency-requirements.md">Lync Server 2013 のブランチサイトの復元要件</A> 」を参照してください。



</div>

<div>


> [!NOTE]  
> Lync Server 存続可能 Branch アプライアンスに所属しているユーザーは、新しいチャットルームを作成したり、既存のルームのルームカードを表示したりすることはできません。



</div>

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 を使用した存続可能ブランチアプライアンスまたはサーバーの展開-中央サイトのタスク](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md)

  - [Lync Server 2013-ブランチサイトタスクを使用して存続可能ブランチアプライアンスまたはサーバーを展開する](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)

  - [Lync Server 2013 でブランチサイトの復元のユーザーを構成する](lync-server-2013-configuring-users-for-branch-site-resiliency.md)

  - [Lync Server 2013 の存続可能ブランチアプライアンスまたはサーバー上のホームユーザー](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md)

  - [付録: 存続可能 Branch アプライアンスおよび Lync Server 2013 のサーバー](lync-server-2013-appendices-survivable-branch-appliances-and-servers.md)

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 の展開 ](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

