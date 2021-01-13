---
title: 許可されたメンバーの選択
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: カテゴリを正しく使用すると、常設チャット ルームの作成と管理がはるかに簡単になります。 常設チャット管理者は、カテゴリごとに AllowedMembers と Creators を定義できます。また、カテゴリで作成されたチャット ルームに適用される既定のチャット ルームの設定と動作を定義することもできます。 常設チャット管理者は、コントロール パネルまたは管理コマンドレットを使用して、カテゴリをWindows PowerShellします。
ms.openlocfilehash: 8c45a16f88bf20ab973927e17807b3241f20e942
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829137"
---
# <a name="select-allowed-members"></a><span data-ttu-id="e6a9c-105">許可されたメンバーの選択</span><span class="sxs-lookup"><span data-stu-id="e6a9c-105">Select Allowed Members</span></span>

<span data-ttu-id="e6a9c-106">カテゴリを正しく使用すると、常設チャット ルームの作成と管理がはるかに簡単になります。</span><span class="sxs-lookup"><span data-stu-id="e6a9c-106">Creating and managing Persistent Chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="e6a9c-107">常設チャット管理者は、カテゴリごとに **AllowedMembers** と **Creators** を定義できます。また、カテゴリで作成されたチャット ルームに適用される既定のチャット ルームの設定と動作を定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="e6a9c-107">A Persistent Chat Administrator can define **AllowedMembers** and **Creators** for each category, and can also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="e6a9c-108">常設チャット管理者は、コントロール パネルまたはカスタム コマンドレットを使用して、カテゴリをWindows PowerShellします。</span><span class="sxs-lookup"><span data-stu-id="e6a9c-108">Persistent Chat Administrators create and manage categories by using the control panel or Windows PowerShell cmdlets.</span></span>

<span data-ttu-id="e6a9c-109">カテゴリの作成者として識別されるユーザー、組織単位 (US)、およびユーザー グループは、カテゴリにルームを作成できる唯一の個人およびグループです。</span><span class="sxs-lookup"><span data-stu-id="e6a9c-109">Users, Organizational Units (OUs), and user groups that are identified as Creators of the category are the only individuals and groups that are allowed to create rooms in the category.</span></span> <span data-ttu-id="e6a9c-110">カテゴリが作成されると、カテゴリの **AllowedMembers** リストからユーザー、US、およびユーザー グループをチャット ルームのマネージャーおよびメンバーとして選択し、ルームを管理および参加できます。</span><span class="sxs-lookup"><span data-stu-id="e6a9c-110">After the category is created, they can choose users, OUs, and user groups from the category's **AllowedMembers** list as chat room managers and members to manage and participate in the room.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="e6a9c-111">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="e6a9c-111">Tasks that you can perform</span></span>

<span data-ttu-id="e6a9c-112">[許可されたメンバーの選択] ページでは、 **次のタスクを実行** できます。</span><span class="sxs-lookup"><span data-stu-id="e6a9c-112">You can perform the following tasks on the **Select Allowed Members** page:</span></span>

- [<span data-ttu-id="e6a9c-113">カテゴリを構成する</span><span class="sxs-lookup"><span data-stu-id="e6a9c-113">Configure Categories</span></span>](https://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)

- [<span data-ttu-id="e6a9c-114">常設チャット サーバーの新機能</span><span class="sxs-lookup"><span data-stu-id="e6a9c-114">New Persistent Chat Server Features</span></span>](https://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)

<span data-ttu-id="e6a9c-115">Skype for Business Server コントロール パネルを使用して実行できるさまざまな手順の詳細については [、「Skype for Business Server 2015](../../manage/manage.md)の管理」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6a9c-115">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="e6a9c-116">チャット ルームのカテゴリを構成するには</span><span class="sxs-lookup"><span data-stu-id="e6a9c-116">To configure categories for chat rooms</span></span>

<span data-ttu-id="e6a9c-117">[**メンバーシップ**] の[許可されるメンバー] セクションで、カテゴリに属するチャット ルームのメンバーとして追加できるユーザーおよび他の Active Directory ドメイン サービス プリンシパル (ユーザー、配布グループ、組織単位など) を追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="e6a9c-117">In **Membership**, in the **Allowed members** section, add or remove users and other Active Directory Domain Services principals (users, distribution groups, organizational units, and so on) that are permitted to be added as members of chat rooms belonging to the category.</span></span> <span data-ttu-id="e6a9c-118">カテゴリによって許可されるプリンシパルは、カテゴリ内のルームを検索できます (ルームが非表示の場合を指定しない限り、ルームのメンバーだけがディレクトリで検索できます)。</span><span class="sxs-lookup"><span data-stu-id="e6a9c-118">Principals permitted by a category can search for the rooms in the category (unless the room is hidden, in which case only members of the room can search for it in the directory).</span></span>


<span data-ttu-id="e6a9c-119">常設チャット サーバーの機能の詳細については、「計画」のドキュメントの [「Overview of Persistent Chat Server」](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6a9c-119">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in the Planning documentation.</span></span> <span data-ttu-id="e6a9c-120">常設チャット サーバーの構成の操作の詳細については、「展開」のドキュメントの [「Configuring Persistent Chat Server」](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) および「操作」のドキュメントの [「Managing Lync Server 2013, Persistent Chat Server」](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6a9c-120">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="e6a9c-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="e6a9c-121">See also</span></span>

[<span data-ttu-id="e6a9c-122">Persistent Chat のメンバーシップについて</span><span class="sxs-lookup"><span data-stu-id="e6a9c-122">Understanding Persistent Chat Membership</span></span>](https://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)
