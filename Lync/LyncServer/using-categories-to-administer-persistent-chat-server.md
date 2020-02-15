---
title: カテゴリを使用して常設チャットサーバーを管理する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Using categories to administer Persistent Chat Server
ms:assetid: dfcb3ad1-da90-467e-b08c-f4e68673b7b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398988(v=OCS.15)
ms:contentKeyID: 48185628
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eecae8ff3c84861df7c624e8ca5b958c4fb53696
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049829"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-categories-to-administer-persistent-chat-server"></a><span data-ttu-id="0c757-102">カテゴリを使用して常設チャットサーバーを管理する</span><span class="sxs-lookup"><span data-stu-id="0c757-102">Using categories to administer Persistent Chat Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0c757-103">_**トピックの最終更新日:** 2013-10-01_</span><span class="sxs-lookup"><span data-stu-id="0c757-103">_**Topic Last Modified:** 2013-10-01_</span></span>

<span data-ttu-id="0c757-104">常設チャットサーバーの展開では、複数の常設チャットルームをホストできます。</span><span class="sxs-lookup"><span data-stu-id="0c757-104">Your Persistent Chat Server deployment can host many concurrent Persistent Chat rooms.</span></span> <span data-ttu-id="0c757-105">チャット ルームはサーバー上で一連のカテゴリに分類できます。</span><span class="sxs-lookup"><span data-stu-id="0c757-105">Chat rooms can be organized into a set of categories on the server.</span></span> <span data-ttu-id="0c757-106">チャット ルームはそれぞれ 1 つのカテゴリに属し、そのカテゴリからいくつかの設定を継承します。</span><span class="sxs-lookup"><span data-stu-id="0c757-106">Each chat room belongs to one category, and inherits some settings from that category.</span></span> <span data-ttu-id="0c757-107">このように体系化することで、会話を業務目的に基づいて識別するのに役立つ構造が作成され、管理の委任と簡素化が促進されます。</span><span class="sxs-lookup"><span data-stu-id="0c757-107">This organization creates a useful structure for identifying conversations, based on their business purpose, and facilitates delegated administration and simplified management.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0c757-108">チャットルームの管理機能の多くは、ユーザーの常設チャット (Lync client) を実行しているコンピューターで利用できますが、常設チャット管理者 ( <STRONG>cspersistentchatadministrator</STRONG>の役割) では、Lync Server コントロールパネルまたは Windows PowerShell コマンドレットを使用してカテゴリを作成または管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c757-108">Although many of the management features of chat rooms are available in computers running Persistent Chat (Lync client) for the user, Persistent Chat Administrators (in the <STRONG>cspersistentchatadministrator</STRONG> role) must use the Lync Server Control Panel or Windows PowerShell cmdlets to create or manage categories.</span></span>



</div>

<span data-ttu-id="0c757-109">常設チャット管理者は、Lync Server コントロールパネルまたは Windows PowerShell コマンドレットを使用してカテゴリを作成および管理し、組織内のユーザーのためのチャットルームへのアクセスを設計します。</span><span class="sxs-lookup"><span data-stu-id="0c757-109">Persistent Chat administrators use Lync Server Control Panel or Windows PowerShell cmdlets to create and manage categories, and to design access for chat rooms for the users in their organization.</span></span>

<span data-ttu-id="0c757-110">1つまたは複数のチャットルームを管理できる常設チャットルームマネージャーは、Lync クライアントを使用してルーム管理 Web アプリケーションを起動し、会議室を作成および管理します (または、お客様はカスタムソリューションやワークフローを作成して呼び出すことができます)。</span><span class="sxs-lookup"><span data-stu-id="0c757-110">Persistent Chat room managers, who have the ability to manage one or more chat rooms, can use the Lync client to launch a room management Web application to create and manage rooms (or customers can create custom solutions and workflows to be invoked).</span></span> <span data-ttu-id="0c757-111">常設チャット管理者は、Lync Server コントロールパネルまたは Windows PowerShell コマンドレットを使用して、会議室を作成および管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="0c757-111">Persistent Chat administrators can also use Lync Server Control Panel or Windows PowerShell cmdlets to create and manage rooms.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0c757-112">常設チャットルームには、常設チャットのカテゴリと同じ名前を付けることはできません。</span><span class="sxs-lookup"><span data-stu-id="0c757-112">A Persistent Chat room cannot have the same name as a Persistent Chat category.</span></span>



</div>

<span data-ttu-id="0c757-p103">チャット ルームのマネージャーは、ルームのカテゴリを変更することを除いて、チャット ルームのすべてのプロパティを変更できます。チャット ルームのマネージャーによる次の操作を制限することはできません。</span><span class="sxs-lookup"><span data-stu-id="0c757-p103">Chat room managers can make changes to all chat room properties, except for changing the category of the room. They cannot be restricted from performing the following actions:</span></span>

  - <span data-ttu-id="0c757-115">チャット ルームを無効にする</span><span class="sxs-lookup"><span data-stu-id="0c757-115">Disabling a chat room</span></span>

  - <span data-ttu-id="0c757-116">チャット ルームの名前を変更する</span><span class="sxs-lookup"><span data-stu-id="0c757-116">Changing a chat room name</span></span>

  - <span data-ttu-id="0c757-117">チャット ルームの説明を変更する</span><span class="sxs-lookup"><span data-stu-id="0c757-117">Changing a chat room description</span></span>

  - <span data-ttu-id="0c757-118">チャット ルームの種類 (大会議室と標準) を変更する</span><span class="sxs-lookup"><span data-stu-id="0c757-118">Changing a chat room type (Auditorium versus Normal)</span></span>

  - <span data-ttu-id="0c757-119">ルームのプライバシーを変更する (オープンかクローズか秘密か)</span><span class="sxs-lookup"><span data-stu-id="0c757-119">Changing the privacy of a room (open versus closed versus secret)</span></span>

  - <span data-ttu-id="0c757-120">メンバーを追加または削除する</span><span class="sxs-lookup"><span data-stu-id="0c757-120">Adding or removing members</span></span>

  - <span data-ttu-id="0c757-121">チャット ルーム マネージャーを追加または削除する</span><span class="sxs-lookup"><span data-stu-id="0c757-121">Adding or removing chat room managers</span></span>

  - <span data-ttu-id="0c757-122">アドインを追加または削除する</span><span class="sxs-lookup"><span data-stu-id="0c757-122">Adding or removing an add-in</span></span>

  - <span data-ttu-id="0c757-123">招待などの設定を変更する (カテゴリで許可されている操作に応じて)</span><span class="sxs-lookup"><span data-stu-id="0c757-123">Changing settings such as invitations (according to what’s permitted by the category)</span></span>

<div>

## <a name="delegated-administration"></a><span data-ttu-id="0c757-124">委任された管理</span><span class="sxs-lookup"><span data-stu-id="0c757-124">Delegated Administration</span></span>

<span data-ttu-id="0c757-125">カテゴリを適切に使用すると、常設チャットルームの作成と管理が非常に簡単になります。</span><span class="sxs-lookup"><span data-stu-id="0c757-125">Creating and managing Persistent Chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="0c757-126">常設チャット管理者は、各カテゴリに**Allowedmembers**と**クリエーター**を定義でき、カテゴリに作成されたすべてのチャットルームに適用される既定のチャットルームの設定と動作を定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="0c757-126">A Persistent Chat Administrator can define **AllowedMembers** and **Creators** for each category, and can also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="0c757-127">常設チャット管理者は、Lync Server コントロールパネルまたは Windows PowerShell コマンドレットを使用して、カテゴリを作成および管理します。</span><span class="sxs-lookup"><span data-stu-id="0c757-127">Persistent Chat administrators create and manage categories by using Lync Server Control Panel or Windows PowerShell cmdlets.</span></span>

<span data-ttu-id="0c757-128">カテゴリの作成者として識別されるユーザー、組織単位 (Ou)、ユーザーグループは、カテゴリ内のルームの作成を許可されている個人およびグループのみです。</span><span class="sxs-lookup"><span data-stu-id="0c757-128">Users, Organizational Units (OUs), and user groups that are identified as Creators of the category are the only individuals and groups that are allowed to create rooms in the category.</span></span> <span data-ttu-id="0c757-129">カテゴリが作成されると、カテゴリの**Allowedmembers**リストからユーザー、ou、およびユーザーグループを選択して、チャットルームマネージャーと、ルームに参加するためのメンバーを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="0c757-129">After the category is created, they can choose users, OUs, and user groups from the category’s **AllowedMembers** list as chat room managers and members to manage and participate in the room.</span></span>

<span data-ttu-id="0c757-130">カテゴリに作成されたチャットルームは、カテゴリによって適用されるポリシーと設定 (ルームのメンバーシップに含まれるユーザー、ルームを管理できるユーザー、ファイルのアップロードが許可されているかどうか、招待が送信されるかどうかなど) に従います。</span><span class="sxs-lookup"><span data-stu-id="0c757-130">Chat rooms that are created in a category adhere to the policies and settings enforced by the category (such as who can be in the room’s membership, who can manage the room, whether file uploads are allowed, whether invitations are sent, and so on).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

