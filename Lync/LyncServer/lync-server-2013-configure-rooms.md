---
title: 'Lync Server 2013: ルームを構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure rooms
ms:assetid: 8956bd2c-c863-4704-bc65-5c0d83556258
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205067(v=OCS.15)
ms:contentKeyID: 48184750
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d08b7cb0146f96b151af021a63ef97a485a0a9dc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840333"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-rooms-in-lync-server-2013"></a><span data-ttu-id="26d39-102">Lync Server 2013 でルームを構成する</span><span class="sxs-lookup"><span data-stu-id="26d39-102">Configure rooms in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="26d39-103">_**最終更新日:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="26d39-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="26d39-104">常設チャットルームの構成は、一般に、Windows PowerShell コマンドラインインターフェイスを使用して、ユーザーまたは他の中央チームによって処理されます。通常、管理者はチャットルームを管理しません。</span><span class="sxs-lookup"><span data-stu-id="26d39-104">Configuring Persistent Chat rooms is commonly handled by users or other central teams by using Windows PowerShell command-line interface; an administrator typically does not manage chat rooms.</span></span> <span data-ttu-id="26d39-105">ただし、チャットルームを作成して管理する必要がある場合は、Windows PowerShell コマンドラインインターフェイスを使用するか、自分をメンバーとしてチャットルームに追加して、Lync 2013 クライアントを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="26d39-105">However, if you have to create and manage chat rooms, you can use the Windows PowerShell command-line interface, or add yourself as a member to a chat room and use the Lync 2013 client.</span></span>

<span data-ttu-id="26d39-106">Windows PowerShell コマンドラインインターフェイスを使用してチャットルームを構成する方法について詳しくは、「 [Windows powershell コマンドレットを使用して常設チャットサーバーを構成](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)する」の「会議室の管理」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="26d39-106">For details about configuring chat rooms by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span>

<div>

## <a name="managing-data-in-chat-rooms"></a><span data-ttu-id="26d39-107">チャットルームでデータを管理する</span><span class="sxs-lookup"><span data-stu-id="26d39-107">Managing Data in Chat Rooms</span></span>

<span data-ttu-id="26d39-108">常設チャットサーバーを使うと、ユーザーは永続的なチャットルームにメッセージを投稿して共同作業を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="26d39-108">Persistent Chat Server lets users collaborate by posting messages into Persistent Chat rooms.</span></span> <span data-ttu-id="26d39-109">データはサーバー上に保持され、会議室のメンバーは履歴データなどのデータにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="26d39-109">The data is persisted on the server, and members of the room can have access to the data, including historical data.</span></span> <span data-ttu-id="26d39-110">ただし、異なるロールを持つユーザーは、次の一覧に示すように、保持されているデータに異なるアクセス権を持っています。</span><span class="sxs-lookup"><span data-stu-id="26d39-110">However, users with different roles have different access to the persisted data, as outlined in the following list.</span></span>

  - <span data-ttu-id="26d39-111">管理者は、データベースが大きくなりすぎないようにチャット ルームから古いコンテンツ (たとえば、特定の日付より前に投稿されたコンテンツ) を削除できます。</span><span class="sxs-lookup"><span data-stu-id="26d39-111">Administrators can delete earlier content (for example, content that was posted before a certain date) from any chat room to keep the database from growing too large.</span></span> <span data-ttu-id="26d39-112">また、特定のチャットルームでは不適切と見なされるメッセージを削除したり、置き換えたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="26d39-112">Or, they can remove or replace messages that are considered inappropriate for a particular chat room.</span></span>

  - <span data-ttu-id="26d39-113">エンド ユーザーは、メッセージの作成者を含めて、チャット ルームからコンテンツを削除できません。</span><span class="sxs-lookup"><span data-stu-id="26d39-113">End users, including message authors, cannot delete content from any chat room.</span></span>

  - <span data-ttu-id="26d39-114">チャットルーム管理者は、ルームを無効にすることはできますが、ルームを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="26d39-114">Chat room managers can disable rooms, but cannot delete rooms.</span></span> <span data-ttu-id="26d39-115">チャットルームを作成した後に削除できるのは管理者だけです。</span><span class="sxs-lookup"><span data-stu-id="26d39-115">Only administrators can delete a chat room after it has been created.</span></span>

<span data-ttu-id="26d39-116">メッセージが削除された場合、操作を元に戻すことはできません。</span><span class="sxs-lookup"><span data-stu-id="26d39-116">When a message is deleted, you cannot undo the action.</span></span> <span data-ttu-id="26d39-117">ただし、バックアップがある場合は、削除されたメッセージを復元することができます。</span><span class="sxs-lookup"><span data-stu-id="26d39-117">However, deleted messages can be restored if there is a backup.</span></span> <span data-ttu-id="26d39-118">常設チャットのコンプライアンスサーバーが有効になっている場合、古いメッセージはコンプライアンスデータベースに保存されます。</span><span class="sxs-lookup"><span data-stu-id="26d39-118">If a Persistent Chat Compliance server is enabled, old messages are persisted in the compliance database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="26d39-119">このチャットルームのデータ使用は、管理者の役割が関係する場合を除き、Lync Server 2013、常設 Chat Server API アプリケーションに適用されます。</span><span class="sxs-lookup"><span data-stu-id="26d39-119">This chat room data usage applies to the Lync Server 2013, Persistent Chat Server API application, except for the case when the administrator role is involved.</span></span> <span data-ttu-id="26d39-120">常設チャットサーバー API を使用して、管理者の操作を実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="26d39-120">The Persistent Chat Server API cannot be used to do any of the administrator’s operations.</span></span> <span data-ttu-id="26d39-121">これらの操作は、Lync Server 管理シェルで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="26d39-121">You must perform these operations in the Lync Server Management Shell.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

