---
title: 'Lync Server 2013: 存続可能ブランチ アプライアンスまたはサーバーの展開'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying a Survivable Branch Appliance or Server
ms:assetid: cb780c14-dc5f-41ba-8092-f20ae905bd16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398849(v=OCS.15)
ms:contentKeyID: 48185643
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7cf894fe6650ff3c06eaaa37f6ba05d70f50eeb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833566"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-a-survivable-branch-appliance-or-server-with-lync-server-2013"></a>Lync Server 2013 を使用した存続可能ブランチ アプライアンスまたはサーバーの展開

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-12-10_

耐障害性のあるエンタープライズボイスとは、ブランチサイトの回復性 (セントラルサイトへのリンクが利用できなくなった場合に、継続的なエンタープライズボイスサービスを提供して、サイトのユーザーをブランチサイトユーザーに提供することを意味します)。

小規模または中規模のブランチサイト (25 ~ 1000 ユーザーの支店) の場合は、Survivable Branch Appliance を導入することをお勧めします。このアプライアンスは、内蔵の PSTN ゲートウェイまたは SIP トランクを電話に接続することで、公衆交換電話網 (PSTN) 通話を終了します。サービスプロバイダ。 Survivable Branch Appliance は、Windows Server 2008 R2 オペレーティングシステムを実行しているブレードサーバー、Lync Server 2013 レジストラー、仲介サーバーソフトウェア、PSTN ゲートウェイがすべて1つのアプライアンスシャーシに含まれているサードパーティ製のデバイスです。

1000 5000 を使用している支社と、回復できる WAN がないブランチサイトの場合は、PSTN ゲートウェイまたは電話サービスプロバイダーへの SIP トランクのどちらかに接続された Survivable Branch Server をお勧めします。 Survivable Branch Server は、レジストラーと仲介サーバーソフトウェアがインストールされている Windows Server ベースのコンピューターです。

<div>


> [!NOTE]  
> 5000ユーザーと専用の Lync Server 管理者がいる支店サイトの場合は、中央サイトとは別の Lync Server 2013 の展開をお勧めします。<BR>組織内のブランチサイトに最適な復元策を選択する方法について詳しくは、「計画のための前提条件と計画の考慮事項」を参照して<A href="lync-server-2013-branch-site-resiliency-requirements.md">2013</A>ください。



</div>

<div>


> [!NOTE]  
> Lync Server Survivable Branch Appliance をホームとして使用しているユーザーは、新しいチャットルームを作成したり、既存のルームの会議室カードを表示したりすることはできません。



</div>

<div>

## <a name="in-this-section"></a>このセクション中

  - [Lync Server 2013 による存続可能ブランチ アプライアンスまたはサーバーの展開 - 中央サイトのタスク](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md)

  - [Lync Server 2013 での存続可能ブランチ アプライアンスまたは存続可能ブランチ サーバーの展開 - ブランチ サイトのタスク](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)

  - [Lync Server 2013 でブランチ サイト復元を実現するためのユーザーの構成](lync-server-2013-configuring-users-for-branch-site-resiliency.md)

  - [Lync Server 2013 で存続可能ブランチ アプライアンスまたは存続可能ブランチ サーバーにユーザーを所属させる](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md)

  - [付録: Lync Server 2013 の存続可能ブランチ アプライアンスとサーバー](lync-server-2013-appendices-survivable-branch-appliances-and-servers.md)

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 の展開](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

