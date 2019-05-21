---
title: 作成者の選択
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.SelectCreators
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f8d9ed6f-22ba-470e-b0b4-0da3cea5e961
description: 永続的なチャットルームの作成と管理は、カテゴリを適切に使用することで非常に簡単になります。 常設チャット管理者は、各カテゴリの AllowedMembers とクリエーターを定義できます。また、カテゴリで作成されたすべてのチャットルームに適用される既定のチャットルームの設定と動作も定義できます。 常設チャット管理者は、Skype for Business Server コントロールパネルまたは Windows PowerShell コマンドレットを使用して、カテゴリの作成と管理を行います。
ms.openlocfilehash: 6fc3feb4465f1ad55d369ed736ea277853aadc13
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294110"
---
# <a name="select-creators"></a><span data-ttu-id="5c4a6-105">作成者の選択</span><span class="sxs-lookup"><span data-stu-id="5c4a6-105">Select Creators</span></span>

<span data-ttu-id="5c4a6-106">永続的なチャットルームの作成と管理は、カテゴリを適切に使用することで非常に簡単になります。</span><span class="sxs-lookup"><span data-stu-id="5c4a6-106">Creating and managing Persistent Chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="5c4a6-107">常設チャット管理者は、各カテゴリの**Allowedmembers**と**クリエーター**を定義できます。また、カテゴリで作成されたすべてのチャットルームに適用される既定のチャットルームの設定と動作も定義できます。</span><span class="sxs-lookup"><span data-stu-id="5c4a6-107">A Persistent Chat administrator can define **AllowedMembers** and **Creators** for each category, and can also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="5c4a6-108">常設チャット管理者は、Skype for Business Server コントロールパネルまたは Windows PowerShell コマンドレットを使用して、カテゴリの作成と管理を行います。</span><span class="sxs-lookup"><span data-stu-id="5c4a6-108">Persistent Chat administrators create and manage categories by using Skype for Business Server Control Panel or Windows PowerShell cmdlets.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="5c4a6-109">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="5c4a6-109">Tasks that you can perform</span></span>

<span data-ttu-id="5c4a6-110">[**作成者の選択**] ページでは、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="5c4a6-110">You can perform the following tasks on the **Select Creators** page:</span></span>

- [<span data-ttu-id="5c4a6-111">Configure Categories</span><span class="sxs-lookup"><span data-stu-id="5c4a6-111">Configure Categories</span></span>](https://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)

- [<span data-ttu-id="5c4a6-112">New Persistent Chat Server Features</span><span class="sxs-lookup"><span data-stu-id="5c4a6-112">New Persistent Chat Server Features</span></span>](https://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)

<span data-ttu-id="5c4a6-113">Skype for Business Server コントロールパネルを使用して実行できるさまざまな手順の詳細については、「Skype for business [server 2015 を管理](../../manage/manage.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c4a6-113">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="5c4a6-114">チャット ルームのカテゴリを構成するには</span><span class="sxs-lookup"><span data-stu-id="5c4a6-114">To configure categories for chat rooms</span></span>

<span data-ttu-id="5c4a6-115">[**メンバーシップ**] の [ \*\*\*\* 作成者] セクションで、カテゴリの作成者に関連付けられているユーザーおよびその他の Active Directory プリンシパルを追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="5c4a6-115">In **Membership**, in the **Creators** section, add or remove users and other Active Directory principals associated with creators for the category.</span></span> <span data-ttu-id="5c4a6-116">作成者は、チャット ルームを作成し、チャット ルームのマネージャーとメンバーを割り当てることができるアクセス許可を持つユーザーです。</span><span class="sxs-lookup"><span data-stu-id="5c4a6-116">A creator is a user who has permissions to create chat rooms and assign chat room managers and members.</span></span>



<span data-ttu-id="5c4a6-117">常設チャットサーバーの機能と機能の詳細については、計画ドキュメントの「[常設チャットサーバーの概要](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c4a6-117">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in the Planning documentation.</span></span> <span data-ttu-id="5c4a6-118">常設チャットサーバーの構成の使用について詳しくは、「展開ドキュメントで[常設チャットサーバーを構成](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx)する」と「運用ドキュメントで[Lync Server 2013、常設チャットサーバーを管理](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx)する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5c4a6-118">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="5c4a6-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="5c4a6-119">See also</span></span>

[<span data-ttu-id="5c4a6-120">Understanding Persistent Chat Membership</span><span class="sxs-lookup"><span data-stu-id="5c4a6-120">Understanding Persistent Chat Membership</span></span>](https://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)

[<span data-ttu-id="5c4a6-121">カテゴリを使用して常設チャットサーバーを管理する</span><span class="sxs-lookup"><span data-stu-id="5c4a6-121">Using Categories to Administer Persistent Chat Server</span></span>](https://technet.microsoft.com/library/dfcb3ad1-da90-467e-b08c-f4e68673b7b5.aspx)

[<span data-ttu-id="5c4a6-122">1つのカテゴリから別のカテゴリへのチャットルームの移動</span><span class="sxs-lookup"><span data-stu-id="5c4a6-122">Moving a Chat Room from One Category to Another</span></span>](https://technet.microsoft.com/library/7e93b8f6-5a18-4476-a432-3918e01bcfa6.aspx)

[<span data-ttu-id="5c4a6-123">新しい会議室の作成または編集</span><span class="sxs-lookup"><span data-stu-id="5c4a6-123">Creating or Editing a New Room</span></span>](https://technet.microsoft.com/library/aa8f4349-cfd9-4036-9c4d-de8fb2c4c8a4.aspx)
