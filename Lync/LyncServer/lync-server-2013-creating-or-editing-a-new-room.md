---
title: 'Lync Server 2013: 新しいチャット ルームの作成または編集'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Creating or editing a new room
ms:assetid: aa8f4349-cfd9-4036-9c4d-de8fb2c4c8a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215880(v=OCS.15)
ms:contentKeyID: 48706008
ms.date: 03/19/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1442454b2afb129fda50d98ed17ccdc2c7ba35c2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833753"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-editing-a-new-room-in-lync-server-2013"></a><span data-ttu-id="7c872-102">Lync Server 2013 での新しいチャット ルームの作成または編集</span><span class="sxs-lookup"><span data-stu-id="7c872-102">Creating or editing a new room in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c872-103">_**最終更新日:** 2015-03-19_</span><span class="sxs-lookup"><span data-stu-id="7c872-103">_**Topic Last Modified:** 2015-03-19_</span></span>

<span data-ttu-id="7c872-104">常設チャットルームの構成は、通常、ユーザーによって処理されます。通常、常設チャット管理者は、チャットルームの構成や管理は行いません。</span><span class="sxs-lookup"><span data-stu-id="7c872-104">Configuring Persistent Chat rooms is commonly handled by users; a Persistent Chat administrator typically does not configure or manage chat rooms.</span></span> <span data-ttu-id="7c872-105">会議室を管理するための Windows PowerShell コマンドレットは、 **CsPersistentChatAdministrator**管理者のみが利用できます。</span><span class="sxs-lookup"><span data-stu-id="7c872-105">Windows PowerShell cmdlets to manage rooms are available only to **CsPersistentChatAdministrator** Administrators.</span></span>

<span data-ttu-id="7c872-106">特定のカテゴリ\*\*\*\* の作成者であるユーザーは、Lync クライアントを使用して、会議室の作成と管理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="7c872-106">Users who are **Creators** in any given category can use the Lync client to create and manage rooms.</span></span> <span data-ttu-id="7c872-107">特定のチャットルームの管理者として指定されているユーザーは、会議室のプロパティやメンバーシップの編集など、会議室の継続的な管理を実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="7c872-107">Users who have been designated as managers for a specific chat room can also perform ongoing management of the room, such as editing the room properties or membership.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="7c872-108">常設チャット管理者も作成者になることができます。また、作成者に課される制限の対象にはなりません。</span><span class="sxs-lookup"><span data-stu-id="7c872-108">Persistent Chat administrators can also be Creators, and they are not subject to the restrictions placed on Creators.</span></span>



</div>

<span data-ttu-id="7c872-109">必要に応じて、常設チャットの管理者である場合は、Windows PowerShell コマンドレットを使う代わりに、ユーザーインターフェイスを使ってチャットルームを作成し、管理することができます。</span><span class="sxs-lookup"><span data-stu-id="7c872-109">Optionally, if you are a Persistent Chat administrator, you can employ a user interface to create and manage chat rooms instead of using Windows PowerShell cmdlets.</span></span> <span data-ttu-id="7c872-110">これを行うには、常設チャットサーバーの管理者を SIP に有効にしてから、Lync クライアントを使ってチャットルームを作成し、管理します。</span><span class="sxs-lookup"><span data-stu-id="7c872-110">To do this, SIP-enable an administrator for Persistent Chat Server, and then use the Lync client to create and manage chat rooms.</span></span>

<span data-ttu-id="7c872-111">ユーザー用のカスタムの会議室管理ワークフローを作成する場合は、常設チャットサーバー構成の**RoomManagementUrl**プロパティを設定して、Lync クライアントからユーザー設定のソリューションにユーザーをリダイレクトすることができます。</span><span class="sxs-lookup"><span data-stu-id="7c872-111">If you want to create a custom room management workflow for your users, you can set the **RoomManagementUrl** property on your Persistent Chat Server configuration to redirect users to your custom solution from the Lync client.</span></span>

<span data-ttu-id="7c872-112">Windows PowerShell コマンドラインインターフェイスを使用してチャットルームを構成する方法について詳しくは、「 [Windows powershell コマンドレットを使用して常設チャットサーバーを構成](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)する」の「会議室の管理」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7c872-112">For details about configuring chat rooms by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span>

<span data-ttu-id="7c872-113">チャットルームの設定の詳細については、展開ドキュメントの「 [Lync Server 2013 で会議室を構成](lync-server-2013-configure-rooms.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c872-113">For details about configuring chat rooms, see [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7c872-114">常設チャットサーバーを使用すると、ユーザーは特定のサイトのチャットルームを作成して管理することができます。</span><span class="sxs-lookup"><span data-stu-id="7c872-114">Persistent Chat Server lets users create and manage chat room for a specific site.</span></span> <span data-ttu-id="7c872-115">ただし、ユーザーは同じトポロジ内の他のサイトのチャットルームを作成または管理することはできません。</span><span class="sxs-lookup"><span data-stu-id="7c872-115">Users cannot, however, create or manage chat rooms on other sites within the same topology.</span></span> <span data-ttu-id="7c872-116">組織内のすべてのサイトについて、必ずチャットルームの作成者と管理者を指定してください。</span><span class="sxs-lookup"><span data-stu-id="7c872-116">Be sure to specify chat room Creators and Managers for all the sites in your organization.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="7c872-117">Lync Server Survivable Branch Appliance をホームとして使用しているユーザーは、新しいチャットルームを作成したり、既存のルームの会議室カードを表示したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="7c872-117">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new chat rooms or view the room card for existing rooms.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

