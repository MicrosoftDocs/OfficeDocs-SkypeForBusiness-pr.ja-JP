---
title: フロントエンドプールまたは Standard Edition サーバーの削除
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove Front End pool or Standard Edition server
ms:assetid: 83c39a36-49a1-4ac6-9cc5-b0e441b1fdec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688115(v=OCS.15)
ms:contentKeyID: 49733713
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47aa2edebe202f6ed21d1b802d899faea563feba
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189540"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-front-end-pool-or-standard-edition-server"></a>フロントエンドプールまたは Standard Edition サーバーの削除

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-04_

このトピックでは、フロントエンドプールまたは Standard Edition フロントエンドサーバーを削除するプロセスについて説明します。 フロントエンドプールを削除する場合は、プール削除処理の一部として、そのプールに属する各フロントエンドサーバーを削除します。 Standard Edition フロントエンドサーバーを削除する場合は、トポロジビルダーから SQL ストア定義を削除する必要があります。

<div>

## <a name="to-remove-a-front-end-server-pool"></a>フロントエンド サーバー プールを削除するには

1.  トポロジ ビルダーを開きます。

2.  [Lync Server 2010 ノードに移動します。

3.  [ **Enterprise Edition フロントエンド**プール] を展開し、フロントエンドプールを展開して、削除するフロントエンドプールを右クリックし、[**削除**] をクリックします。

4.  トポロジを公開し、レプリケーションの状態を確認してから、必要に応じて Lync Server 展開ウィザードを実行します。

</div>

<div>

## <a name="to-remove-a-standard-edition-front-end-server"></a>Standard Edition フロントエンド サーバーを削除するには

1.  トポロジ ビルダーを開きます。

2.  [Lync Server 2010 ノードに移動します。

3.  [ **Standard Edition フロントエンドサーバー**] を展開し、削除するフロントエンドサーバーを右クリックして、[**削除**] をクリックします。

4.  [ **Sql ストア**] を展開し、Standard Edition フロントエンドサーバーに関連付けられている sql Server データベースを右クリックし、[**削除**] をクリックします。
    
    <div>
    

    > [!IMPORTANT]  
    > 併置された SQL Server データベースの定義は、Standard Edition フロントエンドサーバーから削除する必要があります。

    
    </div>

5.  トポロジを公開し、レプリケーションの状態を確認してから、必要に応じて Lync Server 展開ウィザードを実行します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

