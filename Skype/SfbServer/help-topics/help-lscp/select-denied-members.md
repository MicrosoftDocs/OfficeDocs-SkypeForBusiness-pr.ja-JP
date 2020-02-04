---
title: 拒否されたメンバーの選択
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.SelectDeniedMembers
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c626b6b4-15f3-4a59-bb1d-55dc8c60f5cb
description: 常設チャット管理者は、チャットルームのカテゴリを作成して管理することができます。 チャットルームのカテゴリの作成と管理の一環として、常設チャット管理者は、特定のカテゴリのチャットルームのメンバー/作成者としてアクセスできるプリンシパル (Active Directory ドメインサービスのグループ/コンテナー/ユーザー) を構成することができます。 常設チャット管理者は、カテゴリに DeniedMembers を追加することもできます。これは、許可リストに明示的に除外されることになります。 DeniedMembers は、AllowedMembers の内容を上書きします。
ms.openlocfilehash: c8b357abe49d794283b7165d9c5decdffaece275
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41685885"
---
# <a name="select-denied-members"></a><span data-ttu-id="e5191-106">拒否されたメンバーの選択</span><span class="sxs-lookup"><span data-stu-id="e5191-106">Select Denied Members</span></span>

<span data-ttu-id="e5191-107">常設チャット管理者は、チャットルームのカテゴリを作成して管理することができます。</span><span class="sxs-lookup"><span data-stu-id="e5191-107">A Persistent Chat Administrator can create and manage chat room categories.</span></span> <span data-ttu-id="e5191-108">チャットルームのカテゴリの作成と管理の一環として、常設チャット管理者は、特定のカテゴリのチャットルームのメンバー/作成者としてアクセスできるプリンシパル (Active Directory ドメインサービスのグループ/コンテナー/ユーザー) を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="e5191-108">As part of creating and managing chat room categories, a Persistent Chat Administrator can configure principals (Active Directory Domain Services groups/containers/users) that have access to be members/creators of chat rooms of a particular category.</span></span> <span data-ttu-id="e5191-109">常設チャット管理者は、カテゴリに DeniedMembers を追加することもできます。これは、許可リストに明示的に除外されることになります。</span><span class="sxs-lookup"><span data-stu-id="e5191-109">A Persistent Chat Administrator can also add DeniedMembers to a category and these become explicit exclusions to the allowed list.</span></span> <span data-ttu-id="e5191-110">DeniedMembers は、AllowedMembers の内容を上書きします。</span><span class="sxs-lookup"><span data-stu-id="e5191-110">DeniedMembers override what's in AllowedMembers.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="e5191-111">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="e5191-111">Tasks that you can perform</span></span>

<span data-ttu-id="e5191-112">[**拒否されたメンバーの選択**] ページでは、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="e5191-112">You can perform the following tasks on the **Select Denied Members** page:</span></span>

- [<span data-ttu-id="e5191-113">Configure Categories</span><span class="sxs-lookup"><span data-stu-id="e5191-113">Configure Categories</span></span>](https://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)

- [<span data-ttu-id="e5191-114">New Persistent Chat Server Features</span><span class="sxs-lookup"><span data-stu-id="e5191-114">New Persistent Chat Server Features</span></span>](https://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)

<span data-ttu-id="e5191-115">Skype for Business Server コントロールパネルを使用して実行できるさまざまな手順の詳細については、「Skype for business [server 2015 を管理](../../manage/manage.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5191-115">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="e5191-116">チャット ルームのカテゴリを構成するには</span><span class="sxs-lookup"><span data-stu-id="e5191-116">To configure categories for chat rooms</span></span>

<span data-ttu-id="e5191-117">[**メンバーシップ**] の [**拒否するメンバー** ] セクションで、会議室から拒否されているメンバーに関連付けられているユーザーおよびその他の Active Directory プリンシパルを追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="e5191-117">In **Membership**, in the **Denied members** section, add or remove users and other Active Directory principals associated with members being denied from the room.</span></span>


<span data-ttu-id="e5191-118">常設チャットサーバーの機能と機能の詳細については、計画ドキュメントの「[常設チャットサーバーの概要](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5191-118">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in the Planning documentation.</span></span> <span data-ttu-id="e5191-119">常設チャットサーバーの構成の使用について詳しくは、「展開ドキュメントで[常設チャットサーバーを構成](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx)する」と「運用ドキュメントで[Lync Server 2013、常設チャットサーバーを管理](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx)する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e5191-119">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="e5191-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="e5191-120">See also</span></span>

[<span data-ttu-id="e5191-121">Understanding Persistent Chat Membership</span><span class="sxs-lookup"><span data-stu-id="e5191-121">Understanding Persistent Chat Membership</span></span>](https://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)
