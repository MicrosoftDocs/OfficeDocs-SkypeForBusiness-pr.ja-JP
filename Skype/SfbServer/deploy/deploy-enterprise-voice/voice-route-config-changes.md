---
title: Skype for Business での音声ルーティング構成に対する保留中の変更の公開
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ff941d0b-fb4b-47d2-b866-6d990ac66b81
description: '概要: Skype for Business Server コントロール パネルを使用して、Skype for Business Server の音声ルーティング構成の変更を確認、公開、または取り消す方法について説明します。'
ms.openlocfilehash: 6b75b6a1135cf9abde9551112fc9c29579862a8b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830397"
---
# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-skype-for-business"></a><span data-ttu-id="4d482-103">Skype for Business での音声ルーティング構成に対する保留中の変更の公開</span><span class="sxs-lookup"><span data-stu-id="4d482-103">Publish pending changes to the voice routing configuration in Skype for Business</span></span>
 
<span data-ttu-id="4d482-104">**概要:** Skype for Business Server コントロール パネルを使用して、Skype for Business Server の音声ルーティング構成の変更を確認、公開、または取り消す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4d482-104">**Summary:** Learn how to review, publish, or cancel voice routing configuration changes in Skype for Business Server by using the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="4d482-105">音声ルーティング グループ内のページの構成設定に変更を加えた後、この手順を実行して保留中の変更を確認、公開、または取り消します。</span><span class="sxs-lookup"><span data-stu-id="4d482-105">After you make changes to any of the configuration settings in pages in the **Voice Routing** group, perform this procedure to review, publish, or cancel the pending changes.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="4d482-106">一度に 1 人のユーザーだけが音声ルーティング構成設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="4d482-106">Be sure that only one user at a time modifies the Voice Routing configuration settings.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="4d482-107">保留中のすべての変更は、[すべての確定] コマンドを実行して同時 **に公開する必要** があります。</span><span class="sxs-lookup"><span data-stu-id="4d482-107">All pending changes must be published at the same time by running the **Commit all** command.</span></span> <span data-ttu-id="4d482-108">保留中の変更を選択的に公開することはできません。</span><span class="sxs-lookup"><span data-stu-id="4d482-108">You cannot selectively publish pending changes.</span></span> <span data-ttu-id="4d482-109">保留中の変更を公開する前に、[コミットされていない変更の確認] コマンドを実行し、公開しない構成の変更を取り消します。</span><span class="sxs-lookup"><span data-stu-id="4d482-109">Before you publish pending changes, run the **Review uncommitted changes** command and cancel any configuration changes that you do not want to publish.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4d482-110">保留中の変更をコミットする前に音声ルーティング グループ内のページから移動すると、保留中のすべての変更が失われます。</span><span class="sxs-lookup"><span data-stu-id="4d482-110">If you navigate away from the pages in the **Voice Routing** group before committing pending changes, all pending changes will be lost.</span></span> <span data-ttu-id="4d482-111">ただし、現在の構成 (保留中の変更を含む) を音声構成ファイルにエクスポートし、更新された構成をインポートして発行できます。</span><span class="sxs-lookup"><span data-stu-id="4d482-111">However, you can export the current configuration (including any pending changes) to a voice configuration file, and then import and publish the updated configuration.</span></span> <span data-ttu-id="4d482-112">詳細については [、「Skype for Business でのボイス ルート構成ファイルのエクスポートまたはインポート」を参照してください](voice-route-configuration-import-export.md)。</span><span class="sxs-lookup"><span data-stu-id="4d482-112">For details, see [Export or import a voice route configuration file in Skype for Business](voice-route-configuration-import-export.md).</span></span> 
  
### <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a><span data-ttu-id="4d482-113">音声ルーティング構成の変更を確認、公開、または取り消す方法</span><span class="sxs-lookup"><span data-stu-id="4d482-113">To review, publish, or cancel voice routing configuration changes</span></span>

1. <span data-ttu-id="4d482-114">RTCUniversalServerAdmins グループのメンバーとして、または **CsVoiceAdministrator、CsServerAdministrator、\*\*\*\*または\*\*\*\*CsAdministrator** 管理役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="4d482-114">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="4d482-115">Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="4d482-115">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="4d482-116">左側のナビゲーション バーで [**音声ルーティング**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4d482-116">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="4d482-117">音声ルーティング グループの各ページの設定に必要な構成変更 **を行** います。</span><span class="sxs-lookup"><span data-stu-id="4d482-117">Make the configuration changes you want to the settings on each page of the **Voice Routing** group.</span></span>
    
5. <span data-ttu-id="4d482-118">保留中の変更を公開せずに確認するには、[コミット] メニューの [ **コミット** されていない変更の確認] **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="4d482-118">To review pending changes without publishing them, select **Review uncommitted changes** from the **Commit** menu.</span></span>
    
6. <span data-ttu-id="4d482-119">保留中の変更を取り消す場合は、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="4d482-119">If you want to cancel any of the pending changes, do one of the following:</span></span>
    
   - <span data-ttu-id="4d482-120">[ **コミット] メニューから [コミットされていないすべての変更** を取り消す] **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="4d482-120">Select **Cancel all uncommitted changes** from the **Commit** menu.</span></span>
    
   - <span data-ttu-id="4d482-121">取り消す保留中の変更がある [音声ルーティング] ページのタブに移動し、保留中の変更があるアイテムを選択し、[確定] をクリックして、[選択した変更の取り消し] をクリック **します。**</span><span class="sxs-lookup"><span data-stu-id="4d482-121">Navigate to the tab of the **Voice Routing** page that has pending changes you want to cancel, select the item with the pending changes, click **Commit**, and then click **Cancel selected changes**.</span></span>
    
7. <span data-ttu-id="4d482-122">保留中のすべての変更を確認し、公開しない変更を取り消したら、[確定] をクリックし、[すべて確定] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="4d482-122">After you have reviewed all pending changes and canceled any that you do not want to publish, click **Commit**, and then click **Commit all**.</span></span>
    
8. <span data-ttu-id="4d482-123">保留中のすべての **変更の一覧を** 表示する [コミットされていない音声構成設定] ダイアログ ボックスで **、[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4d482-123">In the **Uncommitted Voice Configuration Settings** dialog box, which displays a list of all of the pending changes, click **OK**.</span></span> 
    
    <span data-ttu-id="4d482-124">Skype for Business Server コントロール パネルが変更をコミットすると、正常に公開された音声ルーティング **構成メッセージが** 表示されます。</span><span class="sxs-lookup"><span data-stu-id="4d482-124">When Skype for Business Server Control Panel has committed the changes, the **Successfully published voice routing configuration** message appears.</span></span>
    

