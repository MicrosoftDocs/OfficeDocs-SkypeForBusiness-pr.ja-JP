---
title: 許可されたメンバーの選択
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.SelectAllowedMembers
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e9e6df4a-e58a-4104-9f72-2f5c818353e1
description: 作成し、永続的なチャット ルームを管理するカテゴリを使用して簡単にです。 永続的なチャット管理者は、各カテゴリに属している AllowedMembers および作成者を定義して、チャット ルームのデフォルトの設定と、カテゴリで作成したすべてのチャット ルームに適用される動作を定義することも。 永続的なチャット管理者は、作成し、コントロール パネルまたは Windows PowerShell コマンドレットを使用してカテゴリを管理します。
ms.openlocfilehash: cc35d1659dc7dc7cdc6ba77d17bbc3b439256c63
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874536"
---
# <a name="select-allowed-members"></a><span data-ttu-id="95cf7-105">許可されたメンバーの選択</span><span class="sxs-lookup"><span data-stu-id="95cf7-105">Select Allowed Members</span></span>

<span data-ttu-id="95cf7-106">作成し、永続的なチャット ルームを管理するカテゴリを使用して簡単にです。</span><span class="sxs-lookup"><span data-stu-id="95cf7-106">Creating and managing Persistent Chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="95cf7-107">永続的なチャット管理者は、各カテゴリに属している**AllowedMembers**および**作成者**を定義して、チャット ルームのデフォルトの設定と、カテゴリで作成したすべてのチャット ルームに適用される動作を定義することも。</span><span class="sxs-lookup"><span data-stu-id="95cf7-107">A Persistent Chat Administrator can define **AllowedMembers** and **Creators** for each category, and can also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="95cf7-108">永続的なチャット管理者は、作成し、コントロール パネルまたは Windows PowerShell コマンドレットを使用してカテゴリを管理します。</span><span class="sxs-lookup"><span data-stu-id="95cf7-108">Persistent Chat Administrators create and manage categories by using the control panel or Windows PowerShell cmdlets.</span></span>

<span data-ttu-id="95cf7-109">カテゴリの Creators として特定されるユーザー、組織単位 (OU)、ユーザー グループは、そのカテゴリのチャット ルームの作成を許可されている個人およびグループです。</span><span class="sxs-lookup"><span data-stu-id="95cf7-109">Users, Organizational Units (OUs), and user groups that are identified as Creators of the category are the only individuals and groups that are allowed to create rooms in the category.</span></span> <span data-ttu-id="95cf7-110">カテゴリが作成されると、それらから選択できますユーザー、Ou、およびユーザー グループ カテゴリの**AllowedMembers**のリストとして管理し、ルームに参加するには、チャット ルームの管理者とメンバー。</span><span class="sxs-lookup"><span data-stu-id="95cf7-110">After the category is created, they can choose users, OUs, and user groups from the category's **AllowedMembers** list as chat room managers and members to manage and participate in the room.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="95cf7-111">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="95cf7-111">Tasks that you can perform</span></span>

<span data-ttu-id="95cf7-112">[**許可されたメンバーの選択**] ページでは、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="95cf7-112">You can perform the following tasks on the **Select Allowed Members** page:</span></span>

- [<span data-ttu-id="95cf7-113">Configure Categories</span><span class="sxs-lookup"><span data-stu-id="95cf7-113">Configure Categories</span></span>](https://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)

- [<span data-ttu-id="95cf7-114">New Persistent Chat Server Features</span><span class="sxs-lookup"><span data-stu-id="95cf7-114">New Persistent Chat Server Features</span></span>](https://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)

<span data-ttu-id="95cf7-115">詳細ビジネス サーバーのコントロール パネルの Skype を使用して実行できるさまざまな手順については、[ビジネス サーバー 2015 の Skype の管理](../../manage/manage.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95cf7-115">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="95cf7-116">チャット ルームのカテゴリを構成するには</span><span class="sxs-lookup"><span data-stu-id="95cf7-116">To configure categories for chat rooms</span></span>

<span data-ttu-id="95cf7-117">の**メンバーシップ**、[**許可されたメンバー** ] セクションを追加または削除、ユーザーおよびその他の Active Directory ドメイン サービス プリンシパル (ユーザー、配布グループ、組織単位、およびように) チャット ルームのメンバーとして追加することは許可されません。カテゴリに属しています。</span><span class="sxs-lookup"><span data-stu-id="95cf7-117">In **Membership**, in the **Allowed members** section, add or remove users and other Active Directory Domain Services principals (users, distribution groups, organizational units, and so on) that are permitted to be added as members of chat rooms belonging to the category.</span></span> <span data-ttu-id="95cf7-118">カテゴリで許可されているプリンシパルは、(ルームが表示されない場合、ルームのメンバーのみ検索できるように、ディレクトリに) しない限り、カテゴリの 2 つの部屋を検索できます。</span><span class="sxs-lookup"><span data-stu-id="95cf7-118">Principals permitted by a category can search for the rooms in the category (unless the room is hidden, in which case only members of the room can search for it in the directory).</span></span>


<span data-ttu-id="95cf7-119">永続的なチャット サーバーの機能と機能の詳細については、計画ドキュメントの[概要の永続的なチャット サーバー](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95cf7-119">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in the Planning documentation.</span></span> <span data-ttu-id="95cf7-120">永続的なチャット サーバーの構成の操作に関する詳細についてを参照してください[永続的なチャット サーバーの構成](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx)、展開に関するドキュメントおよび[Lync Server 2013 を管理する、永続的なチャット サーバー](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx)の操作マニュアルを参照します。</span><span class="sxs-lookup"><span data-stu-id="95cf7-120">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="95cf7-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="95cf7-121">See also</span></span>

[<span data-ttu-id="95cf7-122">Understanding Persistent Chat Membership</span><span class="sxs-lookup"><span data-stu-id="95cf7-122">Understanding Persistent Chat Membership</span></span>](https://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)
