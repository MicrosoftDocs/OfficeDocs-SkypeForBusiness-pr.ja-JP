---
title: Lync Server 2013 のフロント エンド プールへの存続可能ブランチ アプライアンスの接続
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Connecting Survivable Branch Appliance to Lync Server 2013 Front End pool
ms:assetid: 3c7ca33f-5295-4d82-9152-41d8bc6f35cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688026(v=OCS.15)
ms:contentKeyID: 49733616
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77d22a71272ae7dd3c426b0439f7a3765ca6848c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840145"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connecting-survivable-branch-appliance-to-lync-server-2013-front-end-pool"></a>Lync Server 2013 のフロント エンド プールへの存続可能ブランチ アプライアンスの接続

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-05_

すべての Survivable Branch Appliance (SBA) は、SBA のバックアップレジストラーとして提供されるフロントエンドプールと関連付けられています。 フロントエンドプールが Lync Server 2013 にアップグレードされた場合、フロントエンドプールがアップグレードされている間、SBA はフロントエンドプールとの関連付けを解除する必要があります。 フロントエンドプールがアップグレードされた後は、フロントエンドプールを使用して SBA を reassociated できます。 これには、トポロジビルダーのトポロジから SBA を削除してから、もう一度 SBA をトポロジビルダーに追加することが含まれます。 トポロジから SBA を削除する前に、SBA をホームにしているユーザーを別のフロントエンドプールに移動する必要があります。 SBA がトポロジに戻された後、それらのユーザーを SBA に戻すことができます。

以下に、これらの手順の概要を示します。

1.  SBA に置かれているブランチユーザーを別のフロントエンドプールに移動します。

2.  トポロジから SBA を削除して、既存のフロントエンドプールとバックアップレジストラーの関連付けを解除します。

3.  フロントエンドプールを Microsoft Lync Server 2013 にアップグレードします。

4.  SBA をトポロジに追加し直します。

5.  新しいフロントエンドプールをバックアップレジストラーとして SBA に関連付けます。

6.  ブランチユーザーを SBA に戻します。

<div>

## <a name="in-this-section"></a>このセクション中

  - [トポロジへの Lync Server 2013 存続可能ブランチ アプライアンスのブランチ サイトの追加](lync-server-2013-add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology.md)

  - [トポロジへの Lync Server 2010 存続可能ブランチ アプライアンスのブランチ サイトの追加](lync-server-2013-add-lync-server-2010-survivable-branch-appliance-branch-site-to-your-topology.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

