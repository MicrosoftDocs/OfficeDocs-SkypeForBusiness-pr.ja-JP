---
title: 作成者の選択
ms.author: kenwith
author: kenwith
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
ms.openlocfilehash: 9a814a5a6408e80fc1b51679fad80ef8c44f6b49
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "21005585"
---
# <a name="select-creators"></a><span data-ttu-id="f94b3-105">作成者の選択</span><span class="sxs-lookup"><span data-stu-id="f94b3-105">Select Creators</span></span>
 
<span data-ttu-id="f94b3-106">作成し、永続的なチャット ルームを管理するカテゴリを使用して簡単にです。</span><span class="sxs-lookup"><span data-stu-id="f94b3-106">Creating and managing Persistent Chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="f94b3-107">永続的なチャット管理者は、各カテゴリに属している**AllowedMembers**および**作成者**を定義して、チャット ルームのデフォルトの設定と、カテゴリで作成したすべてのチャット ルームに適用される動作を定義することも。</span><span class="sxs-lookup"><span data-stu-id="f94b3-107">A Persistent Chat administrator can define **AllowedMembers** and **Creators** for each category, and can also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="f94b3-108">永続的なチャット管理者は、作成し、Skype をビジネス サーバーのコントロール パネルまたは Windows PowerShell コマンドレットを使用してカテゴリを管理します。</span><span class="sxs-lookup"><span data-stu-id="f94b3-108">Persistent Chat administrators create and manage categories by using Skype for Business Server Control Panel or Windows PowerShell cmdlets.</span></span>
  
## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="f94b3-109">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="f94b3-109">Tasks that you can perform</span></span>

<span data-ttu-id="f94b3-110">[**作成者の選択**] ページでは、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="f94b3-110">You can perform the following tasks on the **Select Creators** page:</span></span>
  
- [<span data-ttu-id="f94b3-111">カテゴリを構成します。</span><span class="sxs-lookup"><span data-stu-id="f94b3-111">Configure Categories</span></span>](http://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)
    
- [<span data-ttu-id="f94b3-112">永続的なチャット サーバーの新機能</span><span class="sxs-lookup"><span data-stu-id="f94b3-112">New Persistent Chat Server Features</span></span>](http://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)
    
<span data-ttu-id="f94b3-113">詳細ビジネス サーバーのコントロール パネルの Skype を使用して実行できるさまざまな手順については、[ビジネス サーバー 2015 の Skype の管理](../../manage/manage.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f94b3-113">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>
  
## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="f94b3-114">チャット ルームのカテゴリを構成するには</span><span class="sxs-lookup"><span data-stu-id="f94b3-114">To configure categories for chat rooms</span></span>

<span data-ttu-id="f94b3-115">**メンバーシップ**、[**作成者**] セクションで追加またはユーザーとその他のカテゴリの作成者に関連付けられている Active Directory のプリンシパルを削除します。</span><span class="sxs-lookup"><span data-stu-id="f94b3-115">In **Membership**, in the **Creators** section, add or remove users and other Active Directory principals associated with creators for the category.</span></span> <span data-ttu-id="f94b3-116">作成者は、チャット ルームを作成し、チャット ルームのマネージャーとメンバーを割り当てることができるアクセス許可を持つユーザーです。</span><span class="sxs-lookup"><span data-stu-id="f94b3-116">A creator is a user who has permissions to create chat rooms and assign chat room managers and members.</span></span>
  


<span data-ttu-id="f94b3-117">永続的なチャット サーバーの機能と機能の詳細については、計画ドキュメントの[概要の永続的なチャット サーバー](http://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f94b3-117">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](http://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in the Planning documentation.</span></span> <span data-ttu-id="f94b3-118">永続的なチャット サーバーの構成の操作に関する詳細についてを参照してください[永続的なチャット サーバーの構成](http://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx)、展開に関するドキュメントおよび[Lync Server 2013 を管理する、永続的なチャット サーバー](http://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx)の操作マニュアルを参照します。</span><span class="sxs-lookup"><span data-stu-id="f94b3-118">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](http://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](http://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f94b3-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="f94b3-119">See also</span></span>

[<span data-ttu-id="f94b3-120">永続的なチャットのメンバーシップを理解します。</span><span class="sxs-lookup"><span data-stu-id="f94b3-120">Understanding Persistent Chat Membership</span></span>](http://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)
  
[<span data-ttu-id="f94b3-121">カテゴリを使用して永続的なチャット サーバーを管理するには</span><span class="sxs-lookup"><span data-stu-id="f94b3-121">Using Categories to Administer Persistent Chat Server</span></span>](http://technet.microsoft.com/library/dfcb3ad1-da90-467e-b08c-f4e68673b7b5.aspx)
  
[<span data-ttu-id="f94b3-122">チャット ルームを 1 つのカテゴリ間で移動するには</span><span class="sxs-lookup"><span data-stu-id="f94b3-122">Moving a Chat Room from One Category to Another</span></span>](http://technet.microsoft.com/library/7e93b8f6-5a18-4476-a432-3918e01bcfa6.aspx)
  
[<span data-ttu-id="f94b3-123">作成または新しいルームを編集します。</span><span class="sxs-lookup"><span data-stu-id="f94b3-123">Creating or Editing a New Room</span></span>](http://technet.microsoft.com/library/aa8f4349-cfd9-4036-9c4d-de8fb2c4c8a4.aspx)