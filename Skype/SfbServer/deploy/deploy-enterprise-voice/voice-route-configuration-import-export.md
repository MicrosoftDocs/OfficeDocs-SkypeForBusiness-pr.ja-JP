---
title: Skype for Business 2015 でのボイス ルート構成ファイルのエクスポートまたはインポート
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
description: '概要: ビジネス サーバー 2015 のビジネス サーバーのコントロール パネルの Skype を使用して、Skype で音声ルーティング構成ファイルをインポートまたはエクスポートする方法を説明します。'
ms.openlocfilehash: ba16e68ec3218a06d1baf21c238b14e3f566f630
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="export-or-import-a-voice-route-configuration-file-in-skype-for-business-2015"></a><span data-ttu-id="a442c-103">Skype for Business 2015 でのボイス ルート構成ファイルのエクスポートまたはインポート</span><span class="sxs-lookup"><span data-stu-id="a442c-103">Export or import a voice route configuration file in Skype for Business 2015</span></span>
 
<span data-ttu-id="a442c-104">**の概要:** ビジネス サーバー 2015 のビジネス サーバーのコントロール パネルの Skype を使用して、Skype で音声ルーティング構成ファイルをインポートまたはエクスポートする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a442c-104">**Summary:** Learn how to export or import a voice routing configuration file in Skype for Business Server 2015 by using the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="a442c-105">音声ルーティング構成を公開せずに保存する場合、この手順を実行して、音声ルーティング構成のスナップショットを保存して取得します。</span><span class="sxs-lookup"><span data-stu-id="a442c-105">If you want to save your voice routing configuration without publishing it, follow these steps to save and retrieve a snapshot of your voice routing configuration.</span></span> 
  
<span data-ttu-id="a442c-106">音声ルーティング構成ファイル (.vcfg) をインポートしても、音声ルーティングの構成、サーバーの間に変更が加えられて、Skype ビジネス サーバーのコントロール パネルの [**音声のルーティング**グループ内のページが表示されますがあります。ルーティングを音声にコミットされていない変更は。</span><span class="sxs-lookup"><span data-stu-id="a442c-106">When you import a voice routing configuration file (.vcfg), but changes have been made to the voice routing configuration on the server in the meantime, the pages in the **Voice Routing** group in Skype for Business Server Control Panel will indicate that there are uncommitted changes to voice routing.</span></span> <span data-ttu-id="a442c-107">こうした未確定の変更は、調整が必要な 2 つの構成間の相違です。</span><span class="sxs-lookup"><span data-stu-id="a442c-107">Those uncommitted changes are the differences between the two configurations that require reconciliation.</span></span>
  
<span data-ttu-id="a442c-108">グループ内の任意のページの設定をコミットされていない変更を加えた場合、変更は、エクスポートされた音声構成ファイル (.vcfg) に保存されます。</span><span class="sxs-lookup"><span data-stu-id="a442c-108">If you have made any uncommitted changes to the settings on any page within the group, the changes are saved in the exported voice configuration file (.vcfg).</span></span> <span data-ttu-id="a442c-109">これにより、音声の変更を発行する前に複数のセッション中に構成の変更をルーティングすることができます。</span><span class="sxs-lookup"><span data-stu-id="a442c-109">This enables you to make voice routing configuration changes during multiple sessions before you publish the changes.</span></span> 
  
### <a name="to-export-a-voice-routing-configuration"></a><span data-ttu-id="a442c-110">音声ルーティング構成をエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="a442c-110">To export a voice routing configuration</span></span>

1. <span data-ttu-id="a442c-111">RTCUniversalServerAdmins グループのメンバーとしてコンピューターにログオンするか、**CsVoiceAdministrator**、**CsServerAdministrator**、または **CsAdministrator** 管理者役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="a442c-111">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="a442c-112">Skype をビジネス サーバーのコントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="a442c-112">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="a442c-113">左側のナビゲーション バーで [**音声ルーティング**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a442c-113">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="a442c-114">[**アクション**] メニューの [**構成のエクスポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a442c-114">On the **Actions** menu, click **Export configuration**.</span></span>
    
5. <span data-ttu-id="a442c-115">場所とファイル名を指定し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a442c-115">Specify a location and file name, and then click **Save**.</span></span>
    
### <a name="to-import-a-voice-routing-configuration"></a><span data-ttu-id="a442c-116">音声ルーティング構成をインポートするには</span><span class="sxs-lookup"><span data-stu-id="a442c-116">To import a voice routing configuration</span></span>

1. <span data-ttu-id="a442c-117">RTCUniversalServerAdmins グループのメンバーとしてコンピューターにログオンするか、**CsVoiceAdministrator**、**CsServerAdministrator**、または **CsAdministrator** 管理者役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="a442c-117">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="a442c-118">Skype をビジネス サーバーのコントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="a442c-118">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="a442c-119">左側のナビゲーション バーで [**音声ルーティング**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a442c-119">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="a442c-120">[**操作**] メニューの [**構成のインポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a442c-120">On the **Actions** menu, click **Import configuration**.</span></span>
    
5. <span data-ttu-id="a442c-121">インポートする構成ファイルを検索し、[**開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a442c-121">Find the configuration file you want to import and then click **Open**.</span></span>
    
6. <span data-ttu-id="a442c-122">[**確定**] をクリックし、[**すべて確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a442c-122">Click **Commit**, and then click **Commit all**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a442c-123">音声構成ファイルをインポートする場合は、必ず [**すべて確定**] コマンドを実行して構成変更を公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a442c-123">Whenever you import a voice configuration file, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="a442c-124">詳細については、操作マニュアルの[発行保留中のビジネス 2015年の Skype で音声ルーティング構成の変更](voice-route-config-changes.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a442c-124">For details, see [Publish pending changes to the voice routing configuration in Skype for Business 2015](voice-route-config-changes.md) in the Operations documentation.</span></span>
  

