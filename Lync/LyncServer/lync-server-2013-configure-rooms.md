---
title: 'Lync Server 2013: ルームの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure rooms
ms:assetid: 8956bd2c-c863-4704-bc65-5c0d83556258
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205067(v=OCS.15)
ms:contentKeyID: 48184750
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e78401d0f72f3b29f50453f49f7d7eb66811715
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195740"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-rooms-in-lync-server-2013"></a><span data-ttu-id="b43b6-102">Lync Server 2013 での会議室の構成</span><span class="sxs-lookup"><span data-stu-id="b43b6-102">Configure rooms in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b43b6-103">_**トピックの最終更新日:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="b43b6-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="b43b6-104">常設チャットルームの構成は、通常、Windows PowerShell コマンドラインインターフェイスを使用して、ユーザーまたは他の中央のチームによって処理されます。通常、管理者はチャットルームを管理しません。</span><span class="sxs-lookup"><span data-stu-id="b43b6-104">Configuring Persistent Chat rooms is commonly handled by users or other central teams by using Windows PowerShell command-line interface; an administrator typically does not manage chat rooms.</span></span> <span data-ttu-id="b43b6-105">ただし、チャットルームを作成して管理する必要がある場合は、Windows PowerShell コマンドラインインターフェイスを使用するか、自分をメンバーとしてチャットルームに追加して、Lync 2013 クライアントを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="b43b6-105">However, if you have to create and manage chat rooms, you can use the Windows PowerShell command-line interface, or add yourself as a member to a chat room and use the Lync 2013 client.</span></span>

<span data-ttu-id="b43b6-106">Windows PowerShell コマンドラインインターフェイスを使用したチャットルームの構成の詳細については、「 [Windows powershell コマンドレットを使用して常設チャットサーバーを構成](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)する」の「Room Management」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b43b6-106">For details about configuring chat rooms by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span>

<div>

## <a name="managing-data-in-chat-rooms"></a><span data-ttu-id="b43b6-107">チャット ルームのデータの管理</span><span class="sxs-lookup"><span data-stu-id="b43b6-107">Managing Data in Chat Rooms</span></span>

<span data-ttu-id="b43b6-108">常設チャットサーバーを使用すると、ユーザーは永続的なチャットルームにメッセージを投稿して共同作業を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="b43b6-108">Persistent Chat Server lets users collaborate by posting messages into Persistent Chat rooms.</span></span> <span data-ttu-id="b43b6-109">データはサーバーに保持され、チャット ルームのメンバーは、履歴データなどのデータにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="b43b6-109">The data is persisted on the server, and members of the room can have access to the data, including historical data.</span></span> <span data-ttu-id="b43b6-110">ただし、次に示すように、アクセスできる永続的なデータは、ユーザーの役割によって異なります。</span><span class="sxs-lookup"><span data-stu-id="b43b6-110">However, users with different roles have different access to the persisted data, as outlined in the following list.</span></span>

  - <span data-ttu-id="b43b6-p103">管理者は、データベースが大きくなりすぎないようにチャット ルームから古いコンテンツ (たとえば、特定の日付より前に投稿されたコンテンツ) を削除できます。また、管理者は、特定のチャット ルームにとって不適切と判断されるメッセージを削除または置換することもできます。</span><span class="sxs-lookup"><span data-stu-id="b43b6-p103">Administrators can delete earlier content (for example, content that was posted before a certain date) from any chat room to keep the database from growing too large. Or, they can remove or replace messages that are considered inappropriate for a particular chat room.</span></span>

  - <span data-ttu-id="b43b6-113">エンドユーザー (メッセージの作成者を含む) は、チャット ルームのコンテンツを削除できません。</span><span class="sxs-lookup"><span data-stu-id="b43b6-113">End users, including message authors, cannot delete content from any chat room.</span></span>

  - <span data-ttu-id="b43b6-p104">チャット ルームの管理者は、チャット ルームを無効にできますが、チャット ルームを削除することはできません。チャット ルームを削除できるのは管理者のみです。</span><span class="sxs-lookup"><span data-stu-id="b43b6-p104">Chat room managers can disable rooms, but cannot delete rooms. Only administrators can delete a chat room after it has been created.</span></span>

<span data-ttu-id="b43b6-116">メッセージを削除しても、アクションを元に戻すことはできません。</span><span class="sxs-lookup"><span data-stu-id="b43b6-116">When a message is deleted, you cannot undo the action.</span></span> <span data-ttu-id="b43b6-117">ただし、バックアップがある場合は、削除されたメッセージを復元できます。</span><span class="sxs-lookup"><span data-stu-id="b43b6-117">However, deleted messages can be restored if there is a backup.</span></span> <span data-ttu-id="b43b6-118">常設チャットコンプライアンスサーバーが有効になっている場合、古いメッセージはコンプライアンスデータベースに保持されます。</span><span class="sxs-lookup"><span data-stu-id="b43b6-118">If a Persistent Chat Compliance server is enabled, old messages are persisted in the compliance database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b43b6-119">このチャットルームのデータ使用法は、管理者の役割が関与している場合を除き、Lync Server 2013、常設チャットサーバー API アプリケーションに適用されます。</span><span class="sxs-lookup"><span data-stu-id="b43b6-119">This chat room data usage applies to the Lync Server 2013, Persistent Chat Server API application, except for the case when the administrator role is involved.</span></span> <span data-ttu-id="b43b6-120">常設チャットサーバー API を使用して、管理者の操作を実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="b43b6-120">The Persistent Chat Server API cannot be used to do any of the administrator’s operations.</span></span> <span data-ttu-id="b43b6-121">これらの操作は、Lync Server 管理シェルで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b43b6-121">You must perform these operations in the Lync Server Management Shell.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

