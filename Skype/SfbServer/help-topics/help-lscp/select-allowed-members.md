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
description: 常設チャット ルームの作成と管理は、カテゴリの正しい使用によりはるかに簡単です。 常設チャット管理者は、カテゴリごとに AllowedMembers と Creators を定義できます。また、カテゴリ内に作成されたチャット ルームに適用される既定のチャット ルームの設定と動作を定義することもできます。 常設チャット管理者は、コントロール パネルまたは管理者のコマンドレットを使用してWindows PowerShell管理します。
ms.openlocfilehash: 47abbec64f6799a85f3f6123a898eeae00becbdb
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51107993"
---
# <a name="select-allowed-members"></a><span data-ttu-id="8c96e-105">許可されたメンバーの選択</span><span class="sxs-lookup"><span data-stu-id="8c96e-105">Select Allowed Members</span></span>

<span data-ttu-id="8c96e-106">常設チャット ルームの作成と管理は、カテゴリの正しい使用によりはるかに簡単です。</span><span class="sxs-lookup"><span data-stu-id="8c96e-106">Creating and managing Persistent Chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="8c96e-107">常設チャット管理者は、カテゴリごとに **AllowedMembers** と **Creators** を定義できます。また、カテゴリ内に作成されたチャット ルームに適用される既定のチャット ルームの設定と動作を定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="8c96e-107">A Persistent Chat Administrator can define **AllowedMembers** and **Creators** for each category, and can also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="8c96e-108">常設チャット管理者は、コントロール パネルまたは管理者のコマンドレットを使用してWindows PowerShell管理します。</span><span class="sxs-lookup"><span data-stu-id="8c96e-108">Persistent Chat Administrators create and manage categories by using the control panel or Windows PowerShell cmdlets.</span></span>

<span data-ttu-id="8c96e-109">カテゴリの作成者として識別されるユーザー、組織単位 (OUs)、およびユーザー グループは、カテゴリ内に会議室を作成できる唯一の個人およびグループです。</span><span class="sxs-lookup"><span data-stu-id="8c96e-109">Users, Organizational Units (OUs), and user groups that are identified as Creators of the category are the only individuals and groups that are allowed to create rooms in the category.</span></span> <span data-ttu-id="8c96e-110">カテゴリを作成したら、カテゴリの **AllowedMembers** リストからユーザー、OUs、およびユーザー グループをチャット ルームの管理者として選択し、メンバーがルームを管理および参加できます。</span><span class="sxs-lookup"><span data-stu-id="8c96e-110">After the category is created, they can choose users, OUs, and user groups from the category's **AllowedMembers** list as chat room managers and members to manage and participate in the room.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="8c96e-111">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="8c96e-111">Tasks that you can perform</span></span>

<span data-ttu-id="8c96e-112">[許可されたメンバーの選択] ページで次 **のタスクを実行** できます。</span><span class="sxs-lookup"><span data-stu-id="8c96e-112">You can perform the following tasks on the **Select Allowed Members** page:</span></span>

- [<span data-ttu-id="8c96e-113">カテゴリの構成</span><span class="sxs-lookup"><span data-stu-id="8c96e-113">Configure Categories</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-configure-categories)

- [<span data-ttu-id="8c96e-114">常設チャット サーバーの新機能</span><span class="sxs-lookup"><span data-stu-id="8c96e-114">New Persistent Chat Server Features</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-new-persistent-chat-server-features)

<span data-ttu-id="8c96e-115">Skype for Business Server コントロール パネルを使用して実行できるさまざまな手順の詳細については [、「Manage Skype for Business Server 2015」を参照](../../manage/manage.md)してください。</span><span class="sxs-lookup"><span data-stu-id="8c96e-115">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="8c96e-116">チャット ルームのカテゴリを構成するには</span><span class="sxs-lookup"><span data-stu-id="8c96e-116">To configure categories for chat rooms</span></span>

<span data-ttu-id="8c96e-117">[**メンバーシップ**] の[許可されたメンバー] セクションで、カテゴリに属するチャット ルームのメンバーとして追加できるユーザーおよび他の Active Directory ドメイン サービス プリンシパル (ユーザー、配布グループ、組織単位など) を追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="8c96e-117">In **Membership**, in the **Allowed members** section, add or remove users and other Active Directory Domain Services principals (users, distribution groups, organizational units, and so on) that are permitted to be added as members of chat rooms belonging to the category.</span></span> <span data-ttu-id="8c96e-118">カテゴリで許可されているプリンシパルは、カテゴリ内のルームを検索できます (ルームが非表示の場合を指定しない限り、ディレクトリ内で検索できるのは会議室のメンバーのみです)。</span><span class="sxs-lookup"><span data-stu-id="8c96e-118">Principals permitted by a category can search for the rooms in the category (unless the room is hidden, in which case only members of the room can search for it in the directory).</span></span>


<span data-ttu-id="8c96e-119">常設チャット サーバーの機能の詳細については、「計画」のドキュメントの「 [常設](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-persistent-chat-server) チャット サーバーの概要」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c96e-119">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-persistent-chat-server) in the Planning documentation.</span></span> <span data-ttu-id="8c96e-120">常設チャット サーバー構成の操作の詳細については、「展開[](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-persistent-chat-server)」のドキュメントの「常設チャット サーバーの構成」および「操作」のドキュメントの[「Lync Server 2013](/previous-versions/office/lync-server-2013/managing-lync-server-2013-persistent-chat-server)の管理」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c96e-120">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-persistent-chat-server) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](/previous-versions/office/lync-server-2013/managing-lync-server-2013-persistent-chat-server) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="8c96e-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="8c96e-121">See also</span></span>

[<span data-ttu-id="8c96e-122">Persistent Chat のメンバーシップについて</span><span class="sxs-lookup"><span data-stu-id="8c96e-122">Understanding Persistent Chat Membership</span></span>](/previous-versions/office/lync-server-2013/understanding-persistent-chat-membership)