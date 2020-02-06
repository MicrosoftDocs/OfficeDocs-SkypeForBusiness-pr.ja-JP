---
title: 許可されたメンバーの選択
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.SelectAllowedMembers
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e9e6df4a-e58a-4104-9f72-2f5c818353e1
description: 永続的なチャットルームの作成と管理は、カテゴリを適切に使用することで非常に簡単になります。 常設チャット管理者は、各カテゴリの AllowedMembers とクリエーターを定義できます。また、カテゴリで作成されたすべてのチャットルームに適用される既定のチャットルームの設定と動作も定義できます。 常設チャット管理者は、コントロールパネルまたは Windows PowerShell コマンドレットを使用して、カテゴリの作成と管理を行います。
ms.openlocfilehash: ad371fada6bbb7e8c9a2620eb5ec533cc60a0673
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822300"
---
# <a name="select-allowed-members"></a><span data-ttu-id="7db72-105">許可されたメンバーの選択</span><span class="sxs-lookup"><span data-stu-id="7db72-105">Select Allowed Members</span></span>

<span data-ttu-id="7db72-106">永続的なチャットルームの作成と管理は、カテゴリを適切に使用することで非常に簡単になります。</span><span class="sxs-lookup"><span data-stu-id="7db72-106">Creating and managing Persistent Chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="7db72-107">常設チャット管理者は、各カテゴリの**Allowedmembers**と**クリエーター**を定義できます。また、カテゴリで作成されたすべてのチャットルームに適用される既定のチャットルームの設定と動作も定義できます。</span><span class="sxs-lookup"><span data-stu-id="7db72-107">A Persistent Chat Administrator can define **AllowedMembers** and **Creators** for each category, and can also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="7db72-108">常設チャット管理者は、コントロールパネルまたは Windows PowerShell コマンドレットを使用して、カテゴリの作成と管理を行います。</span><span class="sxs-lookup"><span data-stu-id="7db72-108">Persistent Chat Administrators create and manage categories by using the control panel or Windows PowerShell cmdlets.</span></span>

<span data-ttu-id="7db72-109">カテゴリの Creators として特定されるユーザー、組織単位 (OU)、ユーザー グループは、そのカテゴリのチャット ルームの作成を許可されている個人およびグループです。</span><span class="sxs-lookup"><span data-stu-id="7db72-109">Users, Organizational Units (OUs), and user groups that are identified as Creators of the category are the only individuals and groups that are allowed to create rooms in the category.</span></span> <span data-ttu-id="7db72-110">カテゴリを作成した後、カテゴリの**allowedmembers**リストからユーザー、ou、ユーザーグループを選ぶことができます。チャットルーム管理者として、会議室への参加を管理するメンバーとして選択できます。</span><span class="sxs-lookup"><span data-stu-id="7db72-110">After the category is created, they can choose users, OUs, and user groups from the category's **AllowedMembers** list as chat room managers and members to manage and participate in the room.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="7db72-111">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="7db72-111">Tasks that you can perform</span></span>

<span data-ttu-id="7db72-112">[**許可されたメンバーの選択**] ページでは、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="7db72-112">You can perform the following tasks on the **Select Allowed Members** page:</span></span>

- [<span data-ttu-id="7db72-113">Configure Categories</span><span class="sxs-lookup"><span data-stu-id="7db72-113">Configure Categories</span></span>](https://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)

- [<span data-ttu-id="7db72-114">New Persistent Chat Server Features</span><span class="sxs-lookup"><span data-stu-id="7db72-114">New Persistent Chat Server Features</span></span>](https://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)

<span data-ttu-id="7db72-115">Skype for Business Server コントロールパネルを使用して実行できるさまざまな手順の詳細については、「Skype for business [server 2015 を管理](../../manage/manage.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7db72-115">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="7db72-116">チャット ルームのカテゴリを構成するには</span><span class="sxs-lookup"><span data-stu-id="7db72-116">To configure categories for chat rooms</span></span>

<span data-ttu-id="7db72-117">[許可された**メンバー** ] セクションの [**メンバーシップ**] で、カテゴリに属するチャットルームのメンバーとして追加することを許可されているユーザーおよびその他の Active Directory ドメインサービスプリンシパル (ユーザー、配布グループ、組織単位など) を追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="7db72-117">In **Membership**, in the **Allowed members** section, add or remove users and other Active Directory Domain Services principals (users, distribution groups, organizational units, and so on) that are permitted to be added as members of chat rooms belonging to the category.</span></span> <span data-ttu-id="7db72-118">カテゴリで許可されているプリンシパルは、カテゴリ内のルームを検索することができます (ルームが非表示になっている場合を除き、ルームのメンバーだけがディレクトリ内で検索できます)。</span><span class="sxs-lookup"><span data-stu-id="7db72-118">Principals permitted by a category can search for the rooms in the category (unless the room is hidden, in which case only members of the room can search for it in the directory).</span></span>


<span data-ttu-id="7db72-119">常設チャットサーバーの機能と機能の詳細については、計画ドキュメントの「[常設チャットサーバーの概要](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7db72-119">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in the Planning documentation.</span></span> <span data-ttu-id="7db72-120">常設チャットサーバーの構成の使用について詳しくは、「展開ドキュメントで[常設チャットサーバーを構成](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx)する」と「運用ドキュメントで[Lync Server 2013、常設チャットサーバーを管理](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx)する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7db72-120">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="7db72-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="7db72-121">See also</span></span>

[<span data-ttu-id="7db72-122">Understanding Persistent Chat Membership</span><span class="sxs-lookup"><span data-stu-id="7db72-122">Understanding Persistent Chat Membership</span></span>](https://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)
