---
title: Lync Server 2013 のフロントエンド プールへの存続可能ブランチ アプライアンスの接続
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Connecting Survivable Branch Appliance to Lync Server 2013 Front End pool
ms:assetid: 3c7ca33f-5295-4d82-9152-41d8bc6f35cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688026(v=OCS.15)
ms:contentKeyID: 49733616
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7a637716f1e5b1a2082f694554951d42f36978f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502024"
---
# <a name="connecting-survivable-branch-appliance-to-lync-server-2013-front-end-pool"></a>Lync Server 2013 のフロントエンド プールへの存続可能ブランチ アプライアンスの接続

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-05_

すべての存続可能 Branch Appliance (SBA) は、SBA のバックアップレジストラーとして機能するフロントエンドプールに関連付けられています。 フロントエンドプールが Lync Server 2013 にアップグレードされた場合、フロントエンドプールがアップグレードされている間は、フロントエンドプールとの関連付けを解除する必要があります。 SBA フロントエンドプールをアップグレードした後は、フロントエンドプールを使用して SBA を reassociated ことができます。 これには、トポロジ ビルダーのトポロジから SBA を削除し、再度 SBA をトポロジ ビルダーに追加する作業が含まれます。 トポロジから SBA を削除する前に、SBA に所属するユーザーを別のフロントエンドプールに移動する必要があります。 SBA をトポロジに戻したら、これらのユーザーは SBA に戻すことができます。

これらの手順の概要を次に示します。

1.  SBA に所属するブランチユーザーを別のフロントエンドプールに移動します。

2.  既存のフロントエンドプールとバックアップレジストラーの関連付けを解除するには、SBA をトポロジから削除します。

3.  フロントエンドプールを Microsoft Lync Server 2013 にアップグレードします。

4.  SBA をトポロジに追加します。

5.  新しいフロントエンドプールをバックアップレジストラーとして SBA に関連付けます。

6.  ブランチ ユーザーを SBA に移動します。

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 存続可能 Branch Appliance ブランチサイトをトポロジに追加する](lync-server-2013-add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology.md)

  - [Lync Server 2010 存続可能 Branch Appliance ブランチサイトをトポロジに追加する](lync-server-2013-add-lync-server-2010-survivable-branch-appliance-branch-site-to-your-topology.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

