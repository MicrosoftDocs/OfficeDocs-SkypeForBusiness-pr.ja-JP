---
title: プールからのフロントエンド サーバーの削除
description: フロントエンドサーバーをプールから削除します。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove a Front End Server from a pool
ms:assetid: 767225c9-7c0b-4d54-a407-d77134ba2abe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688095(v=OCS.15)
ms:contentKeyID: 49733694
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45560a6f43288b47c0f85f880a190e31f2c8c04d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551303"
---
# <a name="remove-a-front-end-server-from-a-pool"></a>プールからのフロントエンド サーバーの削除

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-04_

Microsoft Lync Server 2010 Enterprise Edition フロントエンドサーバーは、スタンドアロンコンピューターとしては存在できません。 プール内にコンピューターが1台しかない場合でも、フロントエンドプールとして定義する必要があります。

このトピックでは、既存のフロントエンドプールから個々のフロントエンドサーバーを削除するプロセスについて手順を追って説明します。 フロントエンドサーバーがプール内の最後のサーバーである場合、またはプールを完全に削除する場合は、「 [Remove Front end pool Or Standard Edition Server](remove-front-end-pool-or-standard-edition-server.md)」を参照してください。 フロントエンドプールを削除する前に、個々のフロントエンドサーバーを削除する必要はありません。 プールを削除すると、各フロントエンドサーバーが削除されます。

<div>

## <a name="to-remove-a-front-end-server-from-a-pool"></a>フロントエンド サーバーをプールから削除するには

1.  Lync Server 2013 フロントエンドサーバーを開き、トポロジビルダーを開きます。

2.  [Lync Server 2010 ノードに移動します。

3.  [ **Enterprise Edition フロントエンドプール**] を展開し、削除するフロントエンドサーバーのフロントエンドプールを展開して、削除するフロントエンドサーバーを右クリックし、[ **削除**] をクリックします。

</div>

</div>

<span> </span>

</div>

</div>

</div>

