---
title: 'Lync Server 2013: 常設チャットデータの復元'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring Persistent Chat data
ms:assetid: c251a7fa-50da-434b-b39a-17f5978ce736
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945649(v=OCS.15)
ms:contentKeyID: 51541516
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c905ee22ed237e908fc72e551f973b6f20fa8f2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144663"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-persistent-chat-data-in-lync-server-2013"></a><span data-ttu-id="dde47-102">Lync Server 2013 での常設チャットデータの復元</span><span class="sxs-lookup"><span data-stu-id="dde47-102">Restoring Persistent Chat data in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dde47-103">_**トピックの最終更新日:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="dde47-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="dde47-104">常設チャットルームのコンテンツは、常設チャットデータベース (mgc) に保存されます。</span><span class="sxs-lookup"><span data-stu-id="dde47-104">Persistent Chat room content is stored in the Persistent Chat database (mgc.mdf).</span></span> <span data-ttu-id="dde47-105">これは、定期的にバックアップする必要があるビジネスクリティカルなデータです。</span><span class="sxs-lookup"><span data-stu-id="dde47-105">This is business-critical data that should be backed up regularly.</span></span> <span data-ttu-id="dde47-106">チャットルームのコンテンツに加えて、プリンシパル (ユーザーやグループなど)、およびチャットルームやチャットルームのコンテンツに対して必要な役割とアクセスも常設チャットデータベースに保存されます。</span><span class="sxs-lookup"><span data-stu-id="dde47-106">In addition to the chat room content, principals (such as users and groups) and the roles and access that they have to chat rooms and chat room content, is also stored in the Persistent Chat database.</span></span>

<span data-ttu-id="dde47-107">常設チャットデータの復元方法は、バックアップに使用した方法によって異なります。</span><span class="sxs-lookup"><span data-stu-id="dde47-107">How you restore your Persistent Chat data depends on the method that you used to back it up.</span></span>

  - <span data-ttu-id="dde47-108">SQL Server のバックアップ手順を使用した場合は、SQL Server の復元手順を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dde47-108">If you used SQL Server backup procedures, you must use SQL Server restore procedures.</span></span>

  - <span data-ttu-id="dde47-109">**Export-cspersistentchatdata**コマンドレットを使用して常設チャットデータをバックアップした場合は、 **export-cspersistentchatdata**コマンドレットを使用してデータを復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dde47-109">If you used the **Export-CsPersistentChatData** cmdlet to back up Persistent Chat data, then you must use the **Import-CsPersistentChatData** cmdlet to restore the data.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

