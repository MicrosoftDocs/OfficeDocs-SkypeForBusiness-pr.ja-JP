---
title: 'Lync Server 2013: フロントエンドサーバーの追加または削除'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add or remove a Front End Server
ms:assetid: ab748733-6bad-4c93-8dda-db8d5271653d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205153(v=OCS.15)
ms:contentKeyID: 48185050
ms.date: 01/21/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29c1b3800b05ac4318f853ece95b935c6e65c16c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144994"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="add-or-remove-a-front-end-server-in-lync-server-2013"></a>Lync Server 2013 でのフロントエンドサーバーの追加または削除

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2016-01-21_

フロントエンド サーバーをプールに追加したり、フロントエンド サーバーをプールから削除した場合は、プールを再起動する必要があります。ユーザーへのサービスを中断しないようにするには、フロントエンド サーバーを追加または削除するときに次の手順を使用します。

<div>


> [!NOTE]  
> プールに新しいサーバーを追加している場合は、プール内の既存のサーバーと同じ累積更新レベルになるように、新しいプールサーバーを更新します。



</div>

<div>

## <a name="to-add-or-remove-front-end-servers"></a>フロントエンドサーバーを追加または削除するには

1.  フロントエンド サーバーを削除する場合、最初にこれらのサーバーへの新しい接続を停止します。これを実行するには、次のコマンドレットを使用できます。
    
        Stop-CsWindowsServices -Graceful

2.  削除するサーバーに現在使用しているセッションがない場合、それらの Lync Server サービスを停止します。

3.  トポロジ ビルダーを開き、必要なサーバーを追加または削除します。

4.  トポロジを公開します。

5.  プールで2台以上のフロントエンドサーバーが2台以上になっていない場合、または2台以上のサーバーから完全に2台になった場合は、次のコマンドレットを入力する必要があります。
    
        Reset-CsPoolRegistrarState-ResetType FullReset -PoolFqdn <PoolFqdn>
    
    プールに 3 つ以上のサーバーがある場合は、このコマンドレットを入力するとき、これらのサーバーのうち少なくとも 3 つのサーバーが実行されている必要があります。

6.  プール内のすべてのフロントエンドサーバーを1つずつ再起動します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

