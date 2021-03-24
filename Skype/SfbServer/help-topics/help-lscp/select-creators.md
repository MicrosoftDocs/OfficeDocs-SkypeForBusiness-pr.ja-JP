---
title: 作成者の選択
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
- ms.lync.lscp.SelectCreators
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f8d9ed6f-22ba-470e-b0b4-0da3cea5e961
description: 常設チャット ルームの作成と管理は、カテゴリの正しい使用によりはるかに簡単です。 常設チャット管理者は、カテゴリごとに AllowedMembers と Creators を定義できます。また、カテゴリ内に作成されたチャット ルームに適用される既定のチャット ルームの設定と動作を定義することもできます。 常設チャット管理者は、Skype for Business Server コントロール パネルまたはカスタム コマンドレットを使用してWindows PowerShell管理します。
ms.openlocfilehash: 7d98ff058251b8bd14eb37a0ae5ba633f5a99c48
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51107953"
---
# <a name="select-creators"></a><span data-ttu-id="f4440-105">作成者の選択</span><span class="sxs-lookup"><span data-stu-id="f4440-105">Select Creators</span></span>

<span data-ttu-id="f4440-106">常設チャット ルームの作成と管理は、カテゴリの正しい使用によりはるかに簡単です。</span><span class="sxs-lookup"><span data-stu-id="f4440-106">Creating and managing Persistent Chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="f4440-107">常設チャット管理者は、カテゴリごとに **AllowedMembers** と **Creators** を定義できます。また、カテゴリ内に作成されたチャット ルームに適用される既定のチャット ルームの設定と動作を定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="f4440-107">A Persistent Chat administrator can define **AllowedMembers** and **Creators** for each category, and can also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="f4440-108">常設チャット管理者は、Skype for Business Server コントロール パネルまたはカスタム コマンドレットを使用してWindows PowerShell管理します。</span><span class="sxs-lookup"><span data-stu-id="f4440-108">Persistent Chat administrators create and manage categories by using Skype for Business Server Control Panel or Windows PowerShell cmdlets.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="f4440-109">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="f4440-109">Tasks that you can perform</span></span>

<span data-ttu-id="f4440-110">[**作成者の選択**] ページでは、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="f4440-110">You can perform the following tasks on the **Select Creators** page:</span></span>

- [<span data-ttu-id="f4440-111">カテゴリの構成</span><span class="sxs-lookup"><span data-stu-id="f4440-111">Configure Categories</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-configure-categories)

- [<span data-ttu-id="f4440-112">常設チャット サーバーの新機能</span><span class="sxs-lookup"><span data-stu-id="f4440-112">New Persistent Chat Server Features</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-new-persistent-chat-server-features)

<span data-ttu-id="f4440-113">Skype for Business Server コントロール パネルを使用して実行できるさまざまな手順の詳細については [、「Manage Skype for Business Server 2015」を参照](../../manage/manage.md)してください。</span><span class="sxs-lookup"><span data-stu-id="f4440-113">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="f4440-114">チャット ルームのカテゴリを構成するには</span><span class="sxs-lookup"><span data-stu-id="f4440-114">To configure categories for chat rooms</span></span>

<span data-ttu-id="f4440-115">[ **メンバーシップ]** の **[Creators]** セクションで、カテゴリの作成者に関連付けられているユーザーや他の Active Directory プリンシパルを追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="f4440-115">In **Membership**, in the **Creators** section, add or remove users and other Active Directory principals associated with creators for the category.</span></span> <span data-ttu-id="f4440-116">作成者は、チャット ルームを作成し、チャット ルームのマネージャーとメンバーを割り当てるためのアクセス許可が与えられているユーザーです。</span><span class="sxs-lookup"><span data-stu-id="f4440-116">A creator is a user who has permissions to create chat rooms and assign chat room managers and members.</span></span>



<span data-ttu-id="f4440-117">常設チャット サーバーの機能の詳細については、「計画」のドキュメントの「 [常設](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-persistent-chat-server) チャット サーバーの概要」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4440-117">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-persistent-chat-server) in the Planning documentation.</span></span> <span data-ttu-id="f4440-118">常設チャット サーバー構成の操作の詳細については、「展開[](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-persistent-chat-server)」のドキュメントの「常設チャット サーバーの構成」および「操作」のドキュメントの[「Lync Server 2013](/previous-versions/office/lync-server-2013/managing-lync-server-2013-persistent-chat-server)の管理」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4440-118">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-persistent-chat-server) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](/previous-versions/office/lync-server-2013/managing-lync-server-2013-persistent-chat-server) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="f4440-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="f4440-119">See also</span></span>

[<span data-ttu-id="f4440-120">Persistent Chat のメンバーシップについて</span><span class="sxs-lookup"><span data-stu-id="f4440-120">Understanding Persistent Chat Membership</span></span>](/previous-versions/office/lync-server-2013/understanding-persistent-chat-membership)

[<span data-ttu-id="f4440-121">カテゴリを使用した常設チャット サーバーの管理</span><span class="sxs-lookup"><span data-stu-id="f4440-121">Using Categories to Administer Persistent Chat Server</span></span>](/previous-versions/office/lync-server-2013/using-categories-to-administer-persistent-chat-server)

[<span data-ttu-id="f4440-122">1 つのカテゴリから他のカテゴリへのチャット ルームの移動</span><span class="sxs-lookup"><span data-stu-id="f4440-122">Moving a Chat Room from One Category to Another</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-moving-a-chat-room-from-one-category-to-another)

[<span data-ttu-id="f4440-123">新しいチャット ルームの作成または編集</span><span class="sxs-lookup"><span data-stu-id="f4440-123">Creating or Editing a New Room</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-creating-or-editing-a-new-room)