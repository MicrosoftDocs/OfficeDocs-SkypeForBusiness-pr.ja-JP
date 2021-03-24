---
title: 拒否されたメンバーの選択
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
- ms.lync.lscp.SelectDeniedMembers
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c626b6b4-15f3-4a59-bb1d-55dc8c60f5cb
description: 常設チャット管理者は、チャット ルーム のカテゴリを作成および管理できます。 常設チャット 管理者は、チャット ルーム カテゴリの作成と管理の一環として、特定のカテゴリのチャット ルームのメンバー/作成者にアクセスできるプリンシパル (Active Directory ドメイン サービス グループ/コンテナー/ユーザー) を構成できます。 常設チャット管理者は、DeniedMembers をカテゴリに追加して、許可リストに明示的に除外することもできます。 DeniedMembers は AllowedMembers の値を上書きします。
ms.openlocfilehash: 5a31716c2fae15c6216ed050b543673479415a76
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51107963"
---
# <a name="select-denied-members"></a><span data-ttu-id="45d8e-106">拒否されたメンバーの選択</span><span class="sxs-lookup"><span data-stu-id="45d8e-106">Select Denied Members</span></span>

<span data-ttu-id="45d8e-107">常設チャット管理者は、チャット ルーム のカテゴリを作成および管理できます。</span><span class="sxs-lookup"><span data-stu-id="45d8e-107">A Persistent Chat Administrator can create and manage chat room categories.</span></span> <span data-ttu-id="45d8e-108">常設チャット 管理者は、チャット ルーム カテゴリの作成と管理の一環として、特定のカテゴリのチャット ルームのメンバー/作成者にアクセスできるプリンシパル (Active Directory ドメイン サービス グループ/コンテナー/ユーザー) を構成できます。</span><span class="sxs-lookup"><span data-stu-id="45d8e-108">As part of creating and managing chat room categories, a Persistent Chat Administrator can configure principals (Active Directory Domain Services groups/containers/users) that have access to be members/creators of chat rooms of a particular category.</span></span> <span data-ttu-id="45d8e-109">常設チャット管理者は、DeniedMembers をカテゴリに追加して、許可リストに明示的に除外することもできます。</span><span class="sxs-lookup"><span data-stu-id="45d8e-109">A Persistent Chat Administrator can also add DeniedMembers to a category and these become explicit exclusions to the allowed list.</span></span> <span data-ttu-id="45d8e-110">DeniedMembers は AllowedMembers の値を上書きします。</span><span class="sxs-lookup"><span data-stu-id="45d8e-110">DeniedMembers override what's in AllowedMembers.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="45d8e-111">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="45d8e-111">Tasks that you can perform</span></span>

<span data-ttu-id="45d8e-112">[拒否されたメンバーの選択] ページで次の **タスクを実行** できます。</span><span class="sxs-lookup"><span data-stu-id="45d8e-112">You can perform the following tasks on the **Select Denied Members** page:</span></span>

- [<span data-ttu-id="45d8e-113">カテゴリの構成</span><span class="sxs-lookup"><span data-stu-id="45d8e-113">Configure Categories</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-configure-categories)

- [<span data-ttu-id="45d8e-114">常設チャット サーバーの新機能</span><span class="sxs-lookup"><span data-stu-id="45d8e-114">New Persistent Chat Server Features</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-new-persistent-chat-server-features)

<span data-ttu-id="45d8e-115">Skype for Business Server コントロール パネルを使用して実行できるさまざまな手順の詳細については [、「Manage Skype for Business Server 2015」を参照](../../manage/manage.md)してください。</span><span class="sxs-lookup"><span data-stu-id="45d8e-115">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="45d8e-116">チャット ルームのカテゴリを構成するには</span><span class="sxs-lookup"><span data-stu-id="45d8e-116">To configure categories for chat rooms</span></span>

<span data-ttu-id="45d8e-117">[ **メンバーシップ]** の [ **拒否** されたメンバー] セクションで、ルームから拒否されているメンバーに関連付けられているユーザーや他の Active Directory プリンシパルを追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="45d8e-117">In **Membership**, in the **Denied members** section, add or remove users and other Active Directory principals associated with members being denied from the room.</span></span>


<span data-ttu-id="45d8e-118">常設チャット サーバーの機能の詳細については、「計画」のドキュメントの「 [常設](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-persistent-chat-server) チャット サーバーの概要」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45d8e-118">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-persistent-chat-server) in the Planning documentation.</span></span> <span data-ttu-id="45d8e-119">常設チャット サーバー構成の操作の詳細については、「展開[](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-persistent-chat-server)」のドキュメントの「常設チャット サーバーの構成」および「操作」のドキュメントの[「Lync Server 2013](/previous-versions/office/lync-server-2013/managing-lync-server-2013-persistent-chat-server)の管理」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45d8e-119">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-persistent-chat-server) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](/previous-versions/office/lync-server-2013/managing-lync-server-2013-persistent-chat-server) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="45d8e-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="45d8e-120">See also</span></span>

[<span data-ttu-id="45d8e-121">Persistent Chat のメンバーシップについて</span><span class="sxs-lookup"><span data-stu-id="45d8e-121">Understanding Persistent Chat Membership</span></span>](/previous-versions/office/lync-server-2013/understanding-persistent-chat-membership)