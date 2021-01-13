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
description: カテゴリを正しく使用すると、常設チャット ルームの作成と管理がはるかに簡単になります。 常設チャット管理者は、カテゴリごとに AllowedMembers と Creators を定義できます。また、カテゴリで作成されたチャット ルームに適用される既定のチャット ルームの設定と動作を定義することもできます。 常設チャット管理者は、Skype for Business Server コントロール パネルまたはカスタム コマンドレットを使用して、カテゴリをWindows PowerShellします。
ms.openlocfilehash: 9fc8bf615de02a4c9eefcd204c832c5c8691eb7e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821957"
---
# <a name="select-creators"></a><span data-ttu-id="bb502-105">作成者の選択</span><span class="sxs-lookup"><span data-stu-id="bb502-105">Select Creators</span></span>

<span data-ttu-id="bb502-106">カテゴリを正しく使用すると、常設チャット ルームの作成と管理がはるかに簡単になります。</span><span class="sxs-lookup"><span data-stu-id="bb502-106">Creating and managing Persistent Chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="bb502-107">常設チャット管理者は、カテゴリごとに **AllowedMembers** と **Creators** を定義できます。また、カテゴリで作成されたチャット ルームに適用される既定のチャット ルームの設定と動作を定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="bb502-107">A Persistent Chat administrator can define **AllowedMembers** and **Creators** for each category, and can also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="bb502-108">常設チャット管理者は、Skype for Business Server コントロール パネルまたはカスタム コマンドレットを使用して、カテゴリをWindows PowerShellします。</span><span class="sxs-lookup"><span data-stu-id="bb502-108">Persistent Chat administrators create and manage categories by using Skype for Business Server Control Panel or Windows PowerShell cmdlets.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="bb502-109">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="bb502-109">Tasks that you can perform</span></span>

<span data-ttu-id="bb502-110">[**作成者の選択**] ページでは、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="bb502-110">You can perform the following tasks on the **Select Creators** page:</span></span>

- [<span data-ttu-id="bb502-111">カテゴリを構成する</span><span class="sxs-lookup"><span data-stu-id="bb502-111">Configure Categories</span></span>](https://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)

- [<span data-ttu-id="bb502-112">常設チャット サーバーの新機能</span><span class="sxs-lookup"><span data-stu-id="bb502-112">New Persistent Chat Server Features</span></span>](https://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)

<span data-ttu-id="bb502-113">Skype for Business Server コントロール パネルを使用して実行できるさまざまな手順の詳細については [、「Skype for Business Server 2015](../../manage/manage.md)の管理」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb502-113">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="bb502-114">チャット ルームのカテゴリを構成するには</span><span class="sxs-lookup"><span data-stu-id="bb502-114">To configure categories for chat rooms</span></span>

<span data-ttu-id="bb502-115">[ **メンバーシップ]** の **[Creators]** セクションで、カテゴリの作成者に関連付けられているユーザーおよび他の Active Directory プリンシパルを追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="bb502-115">In **Membership**, in the **Creators** section, add or remove users and other Active Directory principals associated with creators for the category.</span></span> <span data-ttu-id="bb502-116">作成者は、チャット ルームを作成し、チャット ルームのマネージャーとメンバーを割り当てるためのアクセス許可が与えられているユーザーです。</span><span class="sxs-lookup"><span data-stu-id="bb502-116">A creator is a user who has permissions to create chat rooms and assign chat room managers and members.</span></span>



<span data-ttu-id="bb502-117">常設チャット サーバーの機能の詳細については、「計画」のドキュメントの [「Overview of Persistent Chat Server」](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb502-117">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in the Planning documentation.</span></span> <span data-ttu-id="bb502-118">常設チャット サーバーの構成の操作の詳細については、「展開」のドキュメントの [「Configuring Persistent Chat Server」](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) および「操作」のドキュメントの [「Managing Lync Server 2013, Persistent Chat Server」](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb502-118">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="bb502-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="bb502-119">See also</span></span>

[<span data-ttu-id="bb502-120">Persistent Chat のメンバーシップについて</span><span class="sxs-lookup"><span data-stu-id="bb502-120">Understanding Persistent Chat Membership</span></span>](https://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)

[<span data-ttu-id="bb502-121">カテゴリを使用して常設チャット サーバーを管理する</span><span class="sxs-lookup"><span data-stu-id="bb502-121">Using Categories to Administer Persistent Chat Server</span></span>](https://technet.microsoft.com/library/dfcb3ad1-da90-467e-b08c-f4e68673b7b5.aspx)

[<span data-ttu-id="bb502-122">1 つのカテゴリから他のカテゴリへのチャット ルームの移動</span><span class="sxs-lookup"><span data-stu-id="bb502-122">Moving a Chat Room from One Category to Another</span></span>](https://technet.microsoft.com/library/7e93b8f6-5a18-4476-a432-3918e01bcfa6.aspx)

[<span data-ttu-id="bb502-123">新しいチャット ルームの作成または編集</span><span class="sxs-lookup"><span data-stu-id="bb502-123">Creating or Editing a New Room</span></span>](https://technet.microsoft.com/library/aa8f4349-cfd9-4036-9c4d-de8fb2c4c8a4.aspx)
