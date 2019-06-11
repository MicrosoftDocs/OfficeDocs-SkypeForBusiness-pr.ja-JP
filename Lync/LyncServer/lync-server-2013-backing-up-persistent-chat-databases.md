---
title: 'Lync Server 2013: 常設チャットデータベースのバックアップ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Backing up Persistent Chat databases
ms:assetid: b99ebdc0-a025-44d7-9d74-37a7365f330d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945646(v=OCS.15)
ms:contentKeyID: 51541507
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8ffb99effcf0a42bbddefd7151aa40a8d691d9c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840891"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-persistent-chat-databases-in-lync-server-2013"></a><span data-ttu-id="0e703-102">Lync Server 2013 での常設チャットデータベースのバックアップ</span><span class="sxs-lookup"><span data-stu-id="0e703-102">Backing up Persistent Chat databases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0e703-103">_**最終更新日:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="0e703-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="0e703-104">常設チャットルームのコンテンツは、常設チャットデータベース (行う) に保存されます。</span><span class="sxs-lookup"><span data-stu-id="0e703-104">Persistent Chat room content is stored in the Persistent Chat database (Mgc.mdf).</span></span> <span data-ttu-id="0e703-105">コンプライアンス データは非常に重要なビジネス データであり、定期的なバックアップが必要です。</span><span class="sxs-lookup"><span data-stu-id="0e703-105">This is business-critical data that should be backed up regularly.</span></span> <span data-ttu-id="0e703-106">常設チャットデータベースには、チャットルームのコンテンツに加えて、プリンシパルに関する情報 (ユーザー、ユーザーグループなど) と、チャットルームやチャットルームに必要なロールとアクセスも保存されます。</span><span class="sxs-lookup"><span data-stu-id="0e703-106">In addition to the chat room content, the Persistent Chat database also stores information about the principals (such as users and user groups), and the roles and access that they have to chat rooms and chat room.</span></span>

<span data-ttu-id="0e703-107">常設チャットデータをバックアップするには、2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="0e703-107">There are two ways of backing up Persistent Chat data.</span></span>

  - <span data-ttu-id="0e703-108">SQL Server バックアップ</span><span class="sxs-lookup"><span data-stu-id="0e703-108">SQL Server Backup</span></span>

  - <span data-ttu-id="0e703-109">この`Export-CsPersistentChatData`コマンドレットは永続的なチャットデータをファイルとしてエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="0e703-109">The `Export-CsPersistentChatData` cmdlet, which exports Persistent Chat data as a file</span></span>

<span data-ttu-id="0e703-110">SQL Server のバックアップを使用して作成されたデータには、より多くのディスク領域が必要です`Export-CsPersistentChatData`。これは、によって作成された場合よりも20倍ですが、sql Server バックアップは管理者が理解している手順である可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="0e703-110">Data that is created by using SQL Server backup requires significantly more disk space—possibly 20 times more—than that created by `Export-CsPersistentChatData`, but SQL Server backup is more likely to be a procedure that administrators are familiar with.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

