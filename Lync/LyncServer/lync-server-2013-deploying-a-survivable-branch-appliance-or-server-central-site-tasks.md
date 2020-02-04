---
title: 存続可能ブランチ アプライアンスまたはサーバーの展開 - 中央サイトのタスク
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying a Survivable Branch Appliance or Server - central site tasks
ms:assetid: 0f631a36-fc2e-41cd-8a0d-f27e84f4a89e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398189(v=OCS.15)
ms:contentKeyID: 48183422
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a9aa6d38ec873652feae6ef6a374ee5b771520b1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729627"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-a-survivable-branch-appliance-or-server-with-lync-server-2013---central-site-tasks"></a>Lync Server 2013 による存続可能ブランチ アプライアンスまたはサーバーの展開 - 中央サイトのタスク

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-18_

セントラルサイトでこのセクションのタスクを実行します。 Survivable Branch Server を展開している場合は、最初のタスクをスキップします。

<div>


> [!IMPORTANT]
> このセクションのタスクを実行する前に、次の条件を満たしている必要があります。 
> <UL>
> <LI>
> <P>Lync Server はセントラルサイトで設定する必要があります。</P>
> <LI>
> <P>ブランチサイトのインストール技術者は、RTCUniversalSBATechnicians グループに追加されている必要があります。</P></LI></UL>さらに、次の操作を行うことをお勧めします。
> <UL>
> <LI>
> <P>各ブランチサイトに DHCP サーバーを展開して、クライアントが IP アドレスを取得できるようにします。</P>
> <LI>
> <P>各ブランチサイトに DHCP サーバーを展開する代わりに、Lync Server Management Shell コマンドレットの<STRONG>CsRegistrarConfiguration – EnableDHCPServer $true</STRONG>を使って、Survivable branch Appliance または Survivable branch Server で LYNC server DHCP を有効にします。 詳細については、計画ドキュメントの「 <A href="lync-server-2013-branch-site-resiliency-requirements.md">Lync Server 2013 のブランチサイトの回復要件</A>」の「ハードウェアとソフトウェアの要件」セクションを参照してください。</P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a>このセクション中

  - [Lync Server 2013 での、Active Directory への存続可能ブランチ アプライアンスの追加](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md)

  - [Lync Server 2013 でのトポロジへのブランチ サイトの追加](lync-server-2013-add-branch-sites-to-your-topology.md)

  - [Lync Server 2013 での存続可能ブランチ アプライアンスまたは存続可能ブランチ サーバーの定義](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

