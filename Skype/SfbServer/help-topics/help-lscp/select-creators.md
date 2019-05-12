---
title: 作成者の選択
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.SelectCreators
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f8d9ed6f-22ba-470e-b0b4-0da3cea5e961
description: 作成し、永続的なチャット ルームを管理するカテゴリを使用して簡単にです。 永続的なチャット管理者は、各カテゴリに属している AllowedMembers および作成者を定義して、チャット ルームのデフォルトの設定と、カテゴリで作成したすべてのチャット ルームに適用される動作を定義することも。 永続的なチャット管理者は、作成し、Skype をビジネス サーバーのコントロール パネルまたは Windows PowerShell コマンドレットを使用してカテゴリを管理します。
ms.openlocfilehash: 26a99cd950e05810e65d3f51c7737fba2703fd9a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924529"
---
# <a name="select-creators"></a><span data-ttu-id="ea34f-105">作成者の選択</span><span class="sxs-lookup"><span data-stu-id="ea34f-105">Select Creators</span></span>

<span data-ttu-id="ea34f-106">作成し、永続的なチャット ルームを管理するカテゴリを使用して簡単にです。</span><span class="sxs-lookup"><span data-stu-id="ea34f-106">Creating and managing Persistent Chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="ea34f-107">永続的なチャット管理者は、各カテゴリに属している**AllowedMembers**および**作成者**を定義して、チャット ルームのデフォルトの設定と、カテゴリで作成したすべてのチャット ルームに適用される動作を定義することも。</span><span class="sxs-lookup"><span data-stu-id="ea34f-107">A Persistent Chat administrator can define **AllowedMembers** and **Creators** for each category, and can also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="ea34f-108">永続的なチャット管理者は、作成し、Skype をビジネス サーバーのコントロール パネルまたは Windows PowerShell コマンドレットを使用してカテゴリを管理します。</span><span class="sxs-lookup"><span data-stu-id="ea34f-108">Persistent Chat administrators create and manage categories by using Skype for Business Server Control Panel or Windows PowerShell cmdlets.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="ea34f-109">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="ea34f-109">Tasks that you can perform</span></span>

<span data-ttu-id="ea34f-110">[**作成者の選択**] ページでは、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="ea34f-110">You can perform the following tasks on the **Select Creators** page:</span></span>

- [<span data-ttu-id="ea34f-111">Configure Categories</span><span class="sxs-lookup"><span data-stu-id="ea34f-111">Configure Categories</span></span>](https://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)

- [<span data-ttu-id="ea34f-112">New Persistent Chat Server Features</span><span class="sxs-lookup"><span data-stu-id="ea34f-112">New Persistent Chat Server Features</span></span>](https://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)

<span data-ttu-id="ea34f-113">詳細ビジネス サーバーのコントロール パネルの Skype を使用して実行できるさまざまな手順については、[ビジネス サーバー 2015 の Skype の管理](../../manage/manage.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea34f-113">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="ea34f-114">チャット ルームのカテゴリを構成するには</span><span class="sxs-lookup"><span data-stu-id="ea34f-114">To configure categories for chat rooms</span></span>

<span data-ttu-id="ea34f-115">**メンバーシップ**、[**作成者**] セクションで追加またはユーザーとその他のカテゴリの作成者に関連付けられている Active Directory のプリンシパルを削除します。</span><span class="sxs-lookup"><span data-stu-id="ea34f-115">In **Membership**, in the **Creators** section, add or remove users and other Active Directory principals associated with creators for the category.</span></span> <span data-ttu-id="ea34f-116">作成者は、チャット ルームを作成し、チャット ルームのマネージャーとメンバーを割り当てることができるアクセス許可を持つユーザーです。</span><span class="sxs-lookup"><span data-stu-id="ea34f-116">A creator is a user who has permissions to create chat rooms and assign chat room managers and members.</span></span>



<span data-ttu-id="ea34f-117">永続的なチャット サーバーの機能と機能の詳細については、計画ドキュメントの[概要の永続的なチャット サーバー](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea34f-117">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in the Planning documentation.</span></span> <span data-ttu-id="ea34f-118">永続的なチャット サーバーの構成の操作に関する詳細についてを参照してください[永続的なチャット サーバーの構成](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx)、展開に関するドキュメントおよび[Lync Server 2013 を管理する、永続的なチャット サーバー](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx)の操作マニュアルを参照します。</span><span class="sxs-lookup"><span data-stu-id="ea34f-118">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="ea34f-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="ea34f-119">See also</span></span>

[<span data-ttu-id="ea34f-120">Understanding Persistent Chat Membership</span><span class="sxs-lookup"><span data-stu-id="ea34f-120">Understanding Persistent Chat Membership</span></span>](https://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)

[<span data-ttu-id="ea34f-121">カテゴリを使用して永続的なチャット サーバーを管理するには</span><span class="sxs-lookup"><span data-stu-id="ea34f-121">Using Categories to Administer Persistent Chat Server</span></span>](https://technet.microsoft.com/library/dfcb3ad1-da90-467e-b08c-f4e68673b7b5.aspx)

[<span data-ttu-id="ea34f-122">チャット ルームを 1 つのカテゴリ間で移動するには</span><span class="sxs-lookup"><span data-stu-id="ea34f-122">Moving a Chat Room from One Category to Another</span></span>](https://technet.microsoft.com/library/7e93b8f6-5a18-4476-a432-3918e01bcfa6.aspx)

[<span data-ttu-id="ea34f-123">作成または新しいルームを編集します。</span><span class="sxs-lookup"><span data-stu-id="ea34f-123">Creating or Editing a New Room</span></span>](https://technet.microsoft.com/library/aa8f4349-cfd9-4036-9c4d-de8fb2c4c8a4.aspx)
