---
title: Skype for Business の音声ルーティング構成に保留中の変更を公開する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ff941d0b-fb4b-47d2-b866-6d990ac66b81
description: '概要: skype for business Server コントロールパネルを使用して、Skype for Business Server のボイスルーティング構成の変更を確認、発行、またはキャンセルする方法について説明します。'
ms.openlocfilehash: 1ff33dee1518581e4a94aac56ecae34d9bfd1159
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34300888"
---
# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-skype-for-business"></a><span data-ttu-id="e56c6-103">Skype for Business の音声ルーティング構成に保留中の変更を公開する</span><span class="sxs-lookup"><span data-stu-id="e56c6-103">Publish pending changes to the voice routing configuration in Skype for Business</span></span>
 
<span data-ttu-id="e56c6-104">**概要:** Skype for business Server コントロールパネルを使用して、Skype for Business Server の音声ルーティング構成の変更を確認、発行、またはキャンセルする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e56c6-104">**Summary:** Learn how to review, publish, or cancel voice routing configuration changes in Skype for Business Server by using the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="e56c6-105">[**音声ルーティング**] グループの各ページで会議設定のいずれかを変更した後は、ここでの手順を実行して、保留中の変更を確認、公開、またはキャンセルします。</span><span class="sxs-lookup"><span data-stu-id="e56c6-105">After you make changes to any of the configuration settings in pages in the **Voice Routing** group, perform this procedure to review, publish, or cancel the pending changes.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e56c6-106">必ず、一度に 1 人のユーザーだけが音声ルーティング構成の設定を変更するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="e56c6-106">Be sure that only one user at a time modifies the Voice Routing configuration settings.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="e56c6-p101">保留中の変更すべては、[**すべて確定**] コマンドを実行することによって同時に公開する必要があります。保留中の変更のどれかを選択して公開することはできません。保留中の変更を公開する前に、[**未確定の変更の確認**] コマンドを実行し、公開しない保留中の変更をすべてキャンセルしてください。</span><span class="sxs-lookup"><span data-stu-id="e56c6-p101">All pending changes must be published at the same time by running the **Commit all** command. You cannot selectively publish pending changes. Before you publish pending changes, run the **Review uncommitted changes** command and cancel any configuration changes that you do not want to publish.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e56c6-110">保留中の変更を確定する前に [**音声ルーティング**] グループのページから移動して離れると、すべての保留中の変更が失われます。</span><span class="sxs-lookup"><span data-stu-id="e56c6-110">If you navigate away from the pages in the **Voice Routing** group before committing pending changes, all pending changes will be lost.</span></span> <span data-ttu-id="e56c6-111">ただし、現在の構成 (保留中の変更を含む) を音声構成ファイルにエクスポートしておき、後でインポートして更新された構成を公開することができます。</span><span class="sxs-lookup"><span data-stu-id="e56c6-111">However, you can export the current configuration (including any pending changes) to a voice configuration file, and then import and publish the updated configuration.</span></span> <span data-ttu-id="e56c6-112">詳細については、「 [Skype For business のボイスルート構成ファイルをエクスポートまたはインポートする](voice-route-configuration-import-export.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e56c6-112">For details, see [Export or import a voice route configuration file in Skype for Business](voice-route-configuration-import-export.md).</span></span> 
  
### <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a><span data-ttu-id="e56c6-113">音声ルーティング構成の変更を確認、公開、または取り消すには</span><span class="sxs-lookup"><span data-stu-id="e56c6-113">To review, publish, or cancel voice routing configuration changes</span></span>

1. <span data-ttu-id="e56c6-114">RTCUniversalServerAdmins グループのメンバーとしてコンピューターにログオンするか、**CsVoiceAdministrator**、**CsServerAdministrator**、または **CsAdministrator** 管理者役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="e56c6-114">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="e56c6-115">Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="e56c6-115">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="e56c6-116">左側のナビゲーション バーで [**音声ルーティング**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e56c6-116">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="e56c6-117">[**音声ルーティング**] グループの各ページの設定について、必要な構成の変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="e56c6-117">Make the configuration changes you want to the settings on each page of the **Voice Routing** group.</span></span>
    
5. <span data-ttu-id="e56c6-118">公開せずに保留中の変更を確認するには、[**確定**] メニューで [**未確定の変更の確認**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e56c6-118">To review pending changes without publishing them, select **Review uncommitted changes** from the **Commit** menu.</span></span>
    
6. <span data-ttu-id="e56c6-119">保留中の変更のいずれかを取り消す場合は、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e56c6-119">If you want to cancel any of the pending changes, do one of the following:</span></span>
    
   - <span data-ttu-id="e56c6-120">[**確定**] メニューで [**すべての未確定の変更のキャンセル**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e56c6-120">Select **Cancel all uncommitted changes** from the **Commit** menu.</span></span>
    
   - <span data-ttu-id="e56c6-121">取り消す保留中の変更が含まれる [**音声ルーティング**] ページのタブに移動し、保留中の変更を含む項目を選択し、[**確定**] をクリックして、[**選択した変更のキャンセル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e56c6-121">Navigate to the tab of the **Voice Routing** page that has pending changes you want to cancel, select the item with the pending changes, click **Commit**, and then click **Cancel selected changes**.</span></span>
    
7. <span data-ttu-id="e56c6-122">保留中の変更をすべて確認し、公開しない変更をすべてキャンセルしたら、[**確定**] をクリックして、[**すべて確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e56c6-122">After you have reviewed all pending changes and canceled any that you do not want to publish, click **Commit**, and then click **Commit all**.</span></span>
    
8. <span data-ttu-id="e56c6-123">保留中の変更すべての一覧が表示された [**未確定の音声構成設定**] ダイアログ ボックスで、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e56c6-123">In the **Uncommitted Voice Configuration Settings** dialog box, which displays a list of all of the pending changes, click **OK**.</span></span> 
    
    <span data-ttu-id="e56c6-124">Skype for Business Server コントロールパネルが変更をコミットすると、**正常に公開された音声ルーティング構成**のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e56c6-124">When Skype for Business Server Control Panel has committed the changes, the **Successfully published voice routing configuration** message appears.</span></span>
    

