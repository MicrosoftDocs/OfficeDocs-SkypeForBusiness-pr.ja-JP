---
title: 存続可能ブランチアプライアンスまたはサーバー-中央サイトのタスクの展開
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
ms.openlocfilehash: ced7b5262880b23540bf3465f787f6512781f2e3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213973"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-a-survivable-branch-appliance-or-server-with-lync-server-2013---central-site-tasks"></a>Lync Server 2013 を使用した存続可能ブランチアプライアンスまたはサーバーの展開-中央サイトのタスク

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-18_

このセクションに示すタスクをセントラル サイトで完了します。 存続可能ブランチサーバーを展開している場合は、最初のタスクをスキップします。

<div>


> [!IMPORTANT]
> このセクションのタスクを実行する前に、次の条件が満たされている必要があります。 
> <UL>
> <LI>
> <P>中央サイトで Lync Server がセットアップされている必要があります。</P>
> <LI>
> <P>RTCUniversalSBATechnicians グループにブランチ サイトのインストール技術者が追加されている必要があります。</P></LI></UL>また、次の内容の実行をお勧めします。
> <UL>
> <LI>
> <P>各ブランチ サイトで DHCP サーバーを展開し、クライアントが IP アドレスを取得できるようにします。</P>
> <LI>
> <P>各ブランチサイトに DHCP サーバーを展開する代わりに、Lync Server 管理シェルコマンドレット<STRONG>get-csregistrarconfiguration – EnableDHCPServer $true</STRONG>を使用して、存続可能 branch Appliance または存続可能ブランチサーバーで LYNC server DHCP を有効にします。 詳細については、「計画」のドキュメントの「 <A href="lync-server-2013-branch-site-resiliency-requirements.md">Lync Server 2013 のブランチサイトの復元要件</A>」の「ハードウェアとソフトウェアの要件」セクションを参照してください。</P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 で存続可能 Branch Appliance を Active Directory に追加する](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md)

  - [Lync Server 2013 でのトポロジへのブランチサイトの追加](lync-server-2013-add-branch-sites-to-your-topology.md)

  - [Lync Server 2013 での存続可能ブランチアプライアンスまたはサーバーの定義](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

