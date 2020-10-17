---
title: 'Lync Server 2013: 新しいルームの作成または編集'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or editing a new room
ms:assetid: aa8f4349-cfd9-4036-9c4d-de8fb2c4c8a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215880(v=OCS.15)
ms:contentKeyID: 48706008
ms.date: 03/19/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a6f0abaf45034918873a17adc8a0f396ddc5d6fb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516844"
---
# <a name="creating-or-editing-a-new-room-in-lync-server-2013"></a><span data-ttu-id="7fc0e-102">Lync Server 2013 での新しい会議室の作成または編集</span><span class="sxs-lookup"><span data-stu-id="7fc0e-102">Creating or editing a new room in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7fc0e-103">_**トピックの最終更新日:** 2015-03-19_</span><span class="sxs-lookup"><span data-stu-id="7fc0e-103">_**Topic Last Modified:** 2015-03-19_</span></span>

<span data-ttu-id="7fc0e-104">常設チャットルームの構成は、通常、ユーザーによって処理されます。通常、常設チャット管理者はチャットルームの構成や管理は行いません。</span><span class="sxs-lookup"><span data-stu-id="7fc0e-104">Configuring Persistent Chat rooms is commonly handled by users; a Persistent Chat administrator typically does not configure or manage chat rooms.</span></span> <span data-ttu-id="7fc0e-105">ルームを管理するための Windows PowerShell コマンドレットは、 **CsPersistentChatAdministrator** 管理者のみが利用できます。</span><span class="sxs-lookup"><span data-stu-id="7fc0e-105">Windows PowerShell cmdlets to manage rooms are available only to **CsPersistentChatAdministrator** Administrators.</span></span>

<span data-ttu-id="7fc0e-106">特定のカテゴリの作成 **者である** ユーザーは、Lync クライアントを使用して会議室を作成および管理できます。</span><span class="sxs-lookup"><span data-stu-id="7fc0e-106">Users who are **Creators** in any given category can use the Lync client to create and manage rooms.</span></span> <span data-ttu-id="7fc0e-107">特定のチャット ルームのマネージャーとして指定されているユーザーは、ルームのプロパティまたはメンバーシップの編集など、チャット ルームの継続的な管理を実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="7fc0e-107">Users who have been designated as managers for a specific chat room can also perform ongoing management of the room, such as editing the room properties or membership.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="7fc0e-108">常設チャット管理者は、作成者にすることもできます。また、クリエーターに課される制限の対象にすることもありません。</span><span class="sxs-lookup"><span data-stu-id="7fc0e-108">Persistent Chat administrators can also be Creators, and they are not subject to the restrictions placed on Creators.</span></span>



</div>

<span data-ttu-id="7fc0e-109">必要に応じて、常設チャット管理者は、Windows PowerShell コマンドレットを使用する代わりに、ユーザーインターフェイスを使用してチャットルームを作成および管理できます。</span><span class="sxs-lookup"><span data-stu-id="7fc0e-109">Optionally, if you are a Persistent Chat administrator, you can employ a user interface to create and manage chat rooms instead of using Windows PowerShell cmdlets.</span></span> <span data-ttu-id="7fc0e-110">これを行うには、常設チャットサーバーの管理者を SIP で有効にしてから、Lync クライアントを使用してチャットルームを作成して管理します。</span><span class="sxs-lookup"><span data-stu-id="7fc0e-110">To do this, SIP-enable an administrator for Persistent Chat Server, and then use the Lync client to create and manage chat rooms.</span></span>

<span data-ttu-id="7fc0e-111">ユーザーに対してカスタムの会議室管理ワークフローを作成する場合は、常設チャットサーバー構成の **RoomManagementUrl** プロパティを設定して、ユーザーを Lync クライアントからカスタムソリューションにリダイレクトすることができます。</span><span class="sxs-lookup"><span data-stu-id="7fc0e-111">If you want to create a custom room management workflow for your users, you can set the **RoomManagementUrl** property on your Persistent Chat Server configuration to redirect users to your custom solution from the Lync client.</span></span>

<span data-ttu-id="7fc0e-112">Windows PowerShell コマンドラインインターフェイスを使用したチャットルームの構成の詳細については、「 [Windows powershell コマンドレットを使用して常設チャットサーバーを構成](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)する」の「Room Management」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7fc0e-112">For details about configuring chat rooms by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span>

<span data-ttu-id="7fc0e-113">チャットルームの構成の詳細については、「展開」のドキュメントの「 [Configure 室 In Lync Server 2013](lync-server-2013-configure-rooms.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7fc0e-113">For details about configuring chat rooms, see [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7fc0e-114">常設チャットサーバーを使用すると、ユーザーは特定のサイトのチャットルームを作成して管理できます。</span><span class="sxs-lookup"><span data-stu-id="7fc0e-114">Persistent Chat Server lets users create and manage chat room for a specific site.</span></span> <span data-ttu-id="7fc0e-115">ただし、ユーザーは同じトポロジ内の他のサイトでチャットルームを作成または管理することはできません。</span><span class="sxs-lookup"><span data-stu-id="7fc0e-115">Users cannot, however, create or manage chat rooms on other sites within the same topology.</span></span> <span data-ttu-id="7fc0e-116">組織内のすべてのサイトについて、チャットルームの作成者とマネージャーを必ず指定してください。</span><span class="sxs-lookup"><span data-stu-id="7fc0e-116">Be sure to specify chat room Creators and Managers for all the sites in your organization.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="7fc0e-117">Lync Server 存続可能 Branch アプライアンスに所属しているユーザーは、新しいチャットルームを作成したり、既存のルームのルームカードを表示したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="7fc0e-117">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new chat rooms or view the room card for existing rooms.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

