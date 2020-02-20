---
title: プールからのフロントエンドサーバーの削除
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove a Front End Server from a pool
ms:assetid: 767225c9-7c0b-4d54-a407-d77134ba2abe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688095(v=OCS.15)
ms:contentKeyID: 49733694
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c6e161fd5392f194cc19d7ffa01f20ea1f98f3b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148320"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-a-front-end-server-from-a-pool"></a>プールからのフロントエンドサーバーの削除

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

3.  [ **Enterprise Edition フロントエンドプール**] を展開し、削除するフロントエンドサーバーのフロントエンドプールを展開して、削除するフロントエンドサーバーを右クリックし、[**削除**] をクリックします。

</div>

</div>

<span> </span>

</div>

</div>

</div>

