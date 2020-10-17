---
title: 'Lync Server 2013: エッジおよびディレクターのトポロジの作成'
description: 'Lync Server 2013: エッジとディレクターのトポロジを構築する。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Building an edge and Director topology
ms:assetid: 11e5759e-d69f-4c39-8994-f467c279c558
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398202(v=OCS.15)
ms:contentKeyID: 48183451
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bcb2d422136cf0a421c68ebc2adba50f03c5cc85
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569273"
---
# <a name="building-an-edge-and-director-topology-in-lync-server-2013"></a>Lync Server 2013 でのエッジおよびディレクターのトポロジの構築

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-08_

トポロジの構築には、次の計画タスクと展開タスクが含まれます。

  - **計画**    組織に適したトポロジを定義し、それを展開するために必要なコンポーネントを特定する必要があります。 これらは、計画プロセスの標準的なステップです。 Microsoft Lync Server 2013 (Lync Server 2013 で提供される計画ツール) を使用すると、計画プロセスを簡単に開始できます。また、要件やプランが完成すると、簡単に変更することもできます。

  - **展開**    トポロジビルダーを使用して定義したトポロジは、任意の Lync Server 2013 サーバーの展開に不可欠です。 計画作業の一部としてトポロジビルダーを使用してトポロジを定義して公開しない場合は、エッジサーバーを展開する前に、トポロジビルダーを実行してトポロジを公開する必要があります。

少なくとも1つの内部プールを展開するまでエッジサーバーコンポーネントを展開することはできません。また、トポロジビルダーをインストールして内部プールを展開する必要があります。 このセクションでは、内部プールのインストールプロセスの一部であるトポロジビルダーのインストールについては説明しません。

これらのツールの詳細については、「 [Lync Server 2013 の外部ユーザーアクセスの展開チェックリスト](lync-server-2013-deployment-checklist-for-external-user-access.md)」を参照してください。

<div>


> [!NOTE]  
> トポロジビルダーを使用して、エッジトポロジを含む完全なトポロジを定義していた場合は、このセクションの「lync server <A href="lync-server-2013-define-your-edge-topology.md">2013 でのエッジトポロジの定義</A> 」および「lync <A href="lync-server-2013-publish-your-topology.md">server 2013</A> のタスクでのトポロジの公開」を省略できます。ただし、「 <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">Lync server 2013 トポロジをエクスポートして外部メディアにコピー</A> する」を実行してください。



</div>

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 でエッジトポロジを定義する](lync-server-2013-define-your-edge-topology.md)

  - [Lync Server 2013 のトポロジにオプションのディレクタートポロジを定義する](lync-server-2013-define-optional-director-topologies-in-your-topology.md)

  - [Lync Server 2013 でのトポロジの公開](lync-server-2013-publish-your-topology.md)

  - [エッジインストールのために Lync Server 2013 トポロジをエクスポートして外部メディアにコピーする](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

