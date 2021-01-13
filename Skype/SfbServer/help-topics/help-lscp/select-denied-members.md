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
description: 常設チャット管理者は、チャット ルームカテゴリを作成および管理できます。 常設チャット管理者は、チャット ルーム カテゴリの作成と管理の一環として、特定のカテゴリのチャット ルームのメンバー/作成者にアクセスできるプリンシパル (Active Directory ドメイン サービス グループ/コンテナー/ユーザー) を構成できます。 常設チャット管理者は、DeniedMembers をカテゴリに追加して、許可リストへの明示的な除外にすることもできます。 DeniedMembers は AllowedMembers の値を上書きします。
ms.openlocfilehash: c5f942723937fe2da28025fba5da1fc7ee121c83
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814577"
---
# <a name="select-denied-members"></a><span data-ttu-id="7e1e3-106">拒否されたメンバーの選択</span><span class="sxs-lookup"><span data-stu-id="7e1e3-106">Select Denied Members</span></span>

<span data-ttu-id="7e1e3-107">常設チャット管理者は、チャット ルームカテゴリを作成および管理できます。</span><span class="sxs-lookup"><span data-stu-id="7e1e3-107">A Persistent Chat Administrator can create and manage chat room categories.</span></span> <span data-ttu-id="7e1e3-108">常設チャット管理者は、チャット ルーム カテゴリの作成と管理の一環として、特定のカテゴリのチャット ルームのメンバー/作成者にアクセスできるプリンシパル (Active Directory ドメイン サービス グループ/コンテナー/ユーザー) を構成できます。</span><span class="sxs-lookup"><span data-stu-id="7e1e3-108">As part of creating and managing chat room categories, a Persistent Chat Administrator can configure principals (Active Directory Domain Services groups/containers/users) that have access to be members/creators of chat rooms of a particular category.</span></span> <span data-ttu-id="7e1e3-109">常設チャット管理者は、DeniedMembers をカテゴリに追加して、許可リストへの明示的な除外にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="7e1e3-109">A Persistent Chat Administrator can also add DeniedMembers to a category and these become explicit exclusions to the allowed list.</span></span> <span data-ttu-id="7e1e3-110">DeniedMembers は AllowedMembers の値を上書きします。</span><span class="sxs-lookup"><span data-stu-id="7e1e3-110">DeniedMembers override what's in AllowedMembers.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="7e1e3-111">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="7e1e3-111">Tasks that you can perform</span></span>

<span data-ttu-id="7e1e3-112">[拒否されたメンバーの選択] ページでは、次 **のタスクを実行** できます。</span><span class="sxs-lookup"><span data-stu-id="7e1e3-112">You can perform the following tasks on the **Select Denied Members** page:</span></span>

- [<span data-ttu-id="7e1e3-113">カテゴリを構成する</span><span class="sxs-lookup"><span data-stu-id="7e1e3-113">Configure Categories</span></span>](https://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)

- [<span data-ttu-id="7e1e3-114">常設チャット サーバーの新機能</span><span class="sxs-lookup"><span data-stu-id="7e1e3-114">New Persistent Chat Server Features</span></span>](https://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)

<span data-ttu-id="7e1e3-115">Skype for Business Server コントロール パネルを使用して実行できるさまざまな手順の詳細については [、「Skype for Business Server 2015](../../manage/manage.md)の管理」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e1e3-115">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="7e1e3-116">チャット ルームのカテゴリを構成するには</span><span class="sxs-lookup"><span data-stu-id="7e1e3-116">To configure categories for chat rooms</span></span>

<span data-ttu-id="7e1e3-117">メンバーシップ **の**[拒否されたメンバー] セクションで、ルームから拒否されているメンバーに関連付けられているユーザーおよび他の Active Directory プリンシパルを追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="7e1e3-117">In **Membership**, in the **Denied members** section, add or remove users and other Active Directory principals associated with members being denied from the room.</span></span>


<span data-ttu-id="7e1e3-118">常設チャット サーバーの機能の詳細については、「計画」のドキュメントの [「Overview of Persistent Chat Server」](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e1e3-118">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in the Planning documentation.</span></span> <span data-ttu-id="7e1e3-119">常設チャット サーバーの構成の操作の詳細については、「展開」のドキュメントの [「Configuring Persistent Chat Server」](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) および「操作」のドキュメントの [「Managing Lync Server 2013, Persistent Chat Server」](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e1e3-119">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="7e1e3-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="7e1e3-120">See also</span></span>

[<span data-ttu-id="7e1e3-121">Persistent Chat のメンバーシップについて</span><span class="sxs-lookup"><span data-stu-id="7e1e3-121">Understanding Persistent Chat Membership</span></span>](https://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)
