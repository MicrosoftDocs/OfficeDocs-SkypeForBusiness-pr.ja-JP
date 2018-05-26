---
title: 拒否されたメンバーの選択
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.SelectDeniedMembers
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c626b6b4-15f3-4a59-bb1d-55dc8c60f5cb
description: 永続的なチャット管理者は、作成し、チャット ルームのカテゴリを管理できます。 作成して、チャット ルームのカテゴリを管理するの一部として、永続的なチャット管理者は、プリンシパル (Active Directory ドメイン サービス グループ/コンテナー/ユーザー) を特定のカテゴリのチャット ルームのメンバーと作成者のアクセス権を持つを構成できます。 永続的なチャット管理者は、カテゴリに DeniedMembers を追加もでき、許可リストに明示的な除外リストになります。 DeniedMembers は、AllowedMembers では、何をオーバーライドします。
ms.openlocfilehash: 98e57342296f181971c799bafa1b77eccd24b509
ms.sourcegitcommit: 9d816453083c26fd24f8a1cdc0f53f3d218c43b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2018
---
# <a name="select-denied-members"></a><span data-ttu-id="275d6-106">拒否されたメンバーの選択</span><span class="sxs-lookup"><span data-stu-id="275d6-106">Select Denied Members</span></span>
 
<span data-ttu-id="275d6-107">永続的なチャット管理者は、作成し、チャット ルームのカテゴリを管理できます。</span><span class="sxs-lookup"><span data-stu-id="275d6-107">A Persistent Chat Administrator can create and manage chat room categories.</span></span> <span data-ttu-id="275d6-108">作成して、チャット ルームのカテゴリを管理するの一部として、永続的なチャット管理者は、プリンシパル (Active Directory ドメイン サービス グループ/コンテナー/ユーザー) を特定のカテゴリのチャット ルームのメンバーと作成者のアクセス権を持つを構成できます。</span><span class="sxs-lookup"><span data-stu-id="275d6-108">As part of creating and managing chat room categories, a Persistent Chat Administrator can configure principals (Active Directory Domain Services groups/containers/users) that have access to be members/creators of chat rooms of a particular category.</span></span> <span data-ttu-id="275d6-109">永続的なチャット管理者は、カテゴリに DeniedMembers を追加もでき、許可リストに明示的な除外リストになります。</span><span class="sxs-lookup"><span data-stu-id="275d6-109">A Persistent Chat Administrator can also add DeniedMembers to a category and these become explicit exclusions to the allowed list.</span></span> <span data-ttu-id="275d6-110">DeniedMembers は、AllowedMembers では、何をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="275d6-110">DeniedMembers override what's in AllowedMembers.</span></span>
  
## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="275d6-111">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="275d6-111">Tasks that you can perform</span></span>

<span data-ttu-id="275d6-112">[**拒否されたメンバーの選択**] ページでは、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="275d6-112">You can perform the following tasks on the **Select Denied Members** page:</span></span>
  
- [<span data-ttu-id="275d6-113">カテゴリを構成します。</span><span class="sxs-lookup"><span data-stu-id="275d6-113">Configure Categories</span></span>](http://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)
    
- [<span data-ttu-id="275d6-114">永続的なチャット サーバーの新機能</span><span class="sxs-lookup"><span data-stu-id="275d6-114">New Persistent Chat Server Features</span></span>](http://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)
    
<span data-ttu-id="275d6-115">詳細ビジネス サーバーのコントロール パネルの Skype を使用して実行できるさまざまな手順については、[ビジネス サーバー 2015 の Skype の管理](../../../manage/manage.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="275d6-115">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../../manage/manage.md).</span></span>
  
## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="275d6-116">チャット ルームのカテゴリを構成するには</span><span class="sxs-lookup"><span data-stu-id="275d6-116">To configure categories for chat rooms</span></span>

<span data-ttu-id="275d6-117">の**メンバーシップ**、**拒否メンバー** ] セクションで追加またはユーザーと他の部屋から拒否されているメンバーに関連付けられている Active Directory のプリンシパルを削除します。</span><span class="sxs-lookup"><span data-stu-id="275d6-117">In **Membership**, in the **Denied members** section, add or remove users and other Active Directory principals associated with members being denied from the room.</span></span>
  
### 

<span data-ttu-id="275d6-118">永続的なチャット サーバーの機能と機能の詳細については、計画ドキュメントの[概要の永続的なチャット サーバー](http://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="275d6-118">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](http://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in the Planning documentation.</span></span> <span data-ttu-id="275d6-119">永続的なチャット サーバーの構成の操作に関する詳細についてを参照してください[永続的なチャット サーバーの構成](http://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx)、展開に関するドキュメントおよび[Lync Server 2013 を管理する、永続的なチャット サーバー](http://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx)の操作マニュアルを参照します。</span><span class="sxs-lookup"><span data-stu-id="275d6-119">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](http://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](http://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="275d6-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="275d6-120">See also</span></span>

#### 

[<span data-ttu-id="275d6-121">永続的なチャットのメンバーシップを理解します。</span><span class="sxs-lookup"><span data-stu-id="275d6-121">Understanding Persistent Chat Membership</span></span>](http://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)

