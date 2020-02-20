---
title: 'Lync Server 2013: 常設チャットデータベースのバックアップ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up Persistent Chat databases
ms:assetid: b99ebdc0-a025-44d7-9d74-37a7365f330d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945646(v=OCS.15)
ms:contentKeyID: 51541507
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9dc1f448c248f80bfcc636c900b6601fda4aa200
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146620"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backing-up-persistent-chat-databases-in-lync-server-2013"></a><span data-ttu-id="712f0-102">Lync Server 2013 での常設チャットデータベースのバックアップ</span><span class="sxs-lookup"><span data-stu-id="712f0-102">Backing up Persistent Chat databases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="712f0-103">_**トピックの最終更新日:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="712f0-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="712f0-104">常設チャットルームのコンテンツは、常設チャットデータベース (Mgc) に保存されます。</span><span class="sxs-lookup"><span data-stu-id="712f0-104">Persistent Chat room content is stored in the Persistent Chat database (Mgc.mdf).</span></span> <span data-ttu-id="712f0-105">これは、定期的にバックアップする必要があるビジネスクリティカルなデータです。</span><span class="sxs-lookup"><span data-stu-id="712f0-105">This is business-critical data that should be backed up regularly.</span></span> <span data-ttu-id="712f0-106">常設チャットデータベースには、チャットルームのコンテンツに加えて、プリンシパル (ユーザーやユーザーグループなど) に関する情報と、チャットルームやチャットルームに対して必要な役割とアクセスも格納されます。</span><span class="sxs-lookup"><span data-stu-id="712f0-106">In addition to the chat room content, the Persistent Chat database also stores information about the principals (such as users and user groups), and the roles and access that they have to chat rooms and chat room.</span></span>

<span data-ttu-id="712f0-107">常設チャットデータをバックアップするには、2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="712f0-107">There are two ways of backing up Persistent Chat data.</span></span>

  - <span data-ttu-id="712f0-108">SQL Server のバックアップ</span><span class="sxs-lookup"><span data-stu-id="712f0-108">SQL Server Backup</span></span>

  - <span data-ttu-id="712f0-109">`Export-CsPersistentChatData`コマンドレット。常設チャットデータをファイルとしてエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="712f0-109">The `Export-CsPersistentChatData` cmdlet, which exports Persistent Chat data as a file</span></span>

<span data-ttu-id="712f0-110">SQL Server のバックアップを使用して作成されたデータには、より多くのディスク領域が必要に`Export-CsPersistentChatData`なります。これは、によって作成されるよりも20倍になることもありますが、SQL server のバックアップは、管理者が熟知している手順になる可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="712f0-110">Data that is created by using SQL Server backup requires significantly more disk space—possibly 20 times more—than that created by `Export-CsPersistentChatData`, but SQL Server backup is more likely to be a procedure that administrators are familiar with.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

