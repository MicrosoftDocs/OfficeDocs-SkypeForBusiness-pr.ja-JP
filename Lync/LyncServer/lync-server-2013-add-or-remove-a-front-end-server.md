---
title: 'Lync Server 2013: フロントエンドサーバーを追加または削除する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Add or remove a Front End Server
ms:assetid: ab748733-6bad-4c93-8dda-db8d5271653d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205153(v=OCS.15)
ms:contentKeyID: 48185050
ms.date: 01/21/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1fe1e81d3983b89d4f68111179c3adc7409bee2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840943"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-or-remove-a-front-end-server-in-lync-server-2013"></a>Add or remove a Front End Server in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2016-01-21_

フロントエンドサーバーをプールに追加する場合、またはプールからフロントエンドサーバーを削除する場合は、プールを再起動する必要があります。 ユーザーによるサービスの中断を防ぐには、フロントエンドサーバーを追加または削除するときに、次の手順を使用します。

<div>


> [!NOTE]  
> プールに新しいサーバーを追加する場合、累積的な更新プログラムがプール内の既存のサーバーと同じレベルになるように、新しいプール サーバーを更新します。



</div>

<div>

## <a name="to-add-or-remove-front-end-servers"></a>フロントエンドサーバーを追加または削除するには

1.  フロントエンドサーバーを削除する場合は、まず、それらのサーバーへの新しい接続を停止します。 これを実行するには、次のコマンドレットを使用できます。
    
        Stop-CsWindowsServices -Graceful

2.  削除するサーバーに現在のセッションがない場合は、Lync Server サービスを停止します。

3.  トポロジビルダーを開き、必要なサーバーを追加または削除します。

4.  トポロジを公開します。

5.  プールの2台以上のフロントエンドサーバーを2つ以上にしたり、2つ以上のサーバーから2台以上のサーバーを使用していなかったりする場合は、次のコマンドレットを入力する必要があります。
    
        Reset-CsPoolRegistrarState-ResetType FullReset -PoolFqdn <PoolFqdn>
    
    プールに3つ以上のサーバーがある場合は、このコマンドレットを入力するときに、これらのサーバーの少なくとも3つを実行している必要があります。

6.  プール内のすべてのフロントエンドサーバーを一度に1つずつ再起動します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

