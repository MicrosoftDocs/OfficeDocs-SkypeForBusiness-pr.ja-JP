---
title: Lync Server 2013 のバックアップレジストラー関係
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup Registrar relationships
ms:assetid: 7e078271-84b9-4666-989c-c4507a0cdf4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205033(v=OCS.15)
ms:contentKeyID: 48184631
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 07380cbea030f5c9219cef2654b4761f215988e2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140650"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backup-registrar-relationships-in-lync-server-2013"></a>Lync Server 2013 のバックアップレジストラーの関係

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-06-28_

障害復旧の機能を提供するほか、ペアになった 2 つのプールは互いにバックアップ レジストラーの役割も果たします。 Lync Server 2013 では、フロントエンドプール間のバックアップレジストラーの関係は、常に1:1 および相互になります。 これは、P1 が P2 のバックアップであれば P2 が P1 のバックアップでなければならず、また双方がその他のいかなるフロントエンド プールのバックアップにもなれないことを意味します。 これは、Lync Server 2010 からの変更で、フロントエンドプールのバックアップの関係は最大でも1です。

2つのフロントエンドプール間のバックアップ関係は、1:1 および対称である必要がありますが、各フロントエンドプールは、Lync Server 2010 の場合と同様に、任意の数の存続可能ブランチアプライアンスのバックアップレジストラーにすることもできます。

Lync Server 2013 では、存続可能ブランチアプライアンスに所属しているユーザーに対して障害復旧サポートが拡張されないことに注意してください。 存続可能ブランチアプライアンスのバックアップとして機能するフロントエンドプールが停止すると、存続可能ブランチアプライアンスにサインインしたユーザーは、フロントエンドプールに所属するユーザーがバックアップフロントエンドプールにフェールオーバーした後でも復元モードになります。

</div>

<span> </span>

</div>

</div>

</div>

