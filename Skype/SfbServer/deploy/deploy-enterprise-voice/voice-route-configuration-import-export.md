---
title: Skype for Business のボイスルート構成ファイルをエクスポートまたはインポートする
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
description: '概要: skype for business server コントロールパネルを使用して、Skype for Business Server でボイスルーティング構成ファイルをエクスポートまたはインポートする方法について説明します。'
ms.openlocfilehash: ec5a3d0c7f14d85a7b64eaad1edc73ebe4e24cd2
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239916"
---
# <a name="export-or-import-a-voice-route-configuration-file-in-skype-for-business"></a><span data-ttu-id="1385b-103">Skype for Business のボイスルート構成ファイルをエクスポートまたはインポートする</span><span class="sxs-lookup"><span data-stu-id="1385b-103">Export or import a voice route configuration file in Skype for Business</span></span>
 
<span data-ttu-id="1385b-104">**概要:** Skype for business Server コントロールパネルを使用して、Skype for Business Server でボイスルーティング構成ファイルをエクスポートまたはインポートする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1385b-104">**Summary:** Learn how to export or import a voice routing configuration file in Skype for Business Server by using the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="1385b-105">音声ルーティング構成を公開せずに保存する場合、この手順を実行して、音声ルーティング構成のスナップショットを保存して取得します。</span><span class="sxs-lookup"><span data-stu-id="1385b-105">If you want to save your voice routing configuration without publishing it, follow these steps to save and retrieve a snapshot of your voice routing configuration.</span></span> 
  
<span data-ttu-id="1385b-106">ボイスルーティング構成ファイル (vcfg) をインポートするときに、その間にサーバー上の音声ルーティング構成に変更が加えられた場合、Skype for Business Server コントロールパネルの [**ボイスルーティング**] グループのページには、は、音声ルーティングのコミットされていない変更です。</span><span class="sxs-lookup"><span data-stu-id="1385b-106">When you import a voice routing configuration file (.vcfg), but changes have been made to the voice routing configuration on the server in the meantime, the pages in the **Voice Routing** group in Skype for Business Server Control Panel will indicate that there are uncommitted changes to voice routing.</span></span> <span data-ttu-id="1385b-107">こうした未確定の変更は、調整が必要な 2 つの構成間の相違です。</span><span class="sxs-lookup"><span data-stu-id="1385b-107">Those uncommitted changes are the differences between the two configurations that require reconciliation.</span></span>
  
<span data-ttu-id="1385b-108">グループ内の任意のページの設定にコミットされていない変更を加えた場合、変更はエクスポートされた音声構成ファイル (vcfg) に保存されます。</span><span class="sxs-lookup"><span data-stu-id="1385b-108">If you have made any uncommitted changes to the settings on any page within the group, the changes are saved in the exported voice configuration file (.vcfg).</span></span> <span data-ttu-id="1385b-109">これにより、変更を公開する前に、複数のセッション中にボイスルーティング構成の変更を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="1385b-109">This enables you to make voice routing configuration changes during multiple sessions before you publish the changes.</span></span> 
  
### <a name="to-export-a-voice-routing-configuration"></a><span data-ttu-id="1385b-110">音声ルーティング構成をエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="1385b-110">To export a voice routing configuration</span></span>

1. <span data-ttu-id="1385b-111">RTCUniversalServerAdmins グループのメンバーとしてコンピューターにログオンするか、**CsVoiceAdministrator**、**CsServerAdministrator**、または **CsAdministrator** 管理者役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="1385b-111">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="1385b-112">Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="1385b-112">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="1385b-113">左側のナビゲーション バーで [**音声ルーティング**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1385b-113">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="1385b-114">[**アクション**] メニューの [**構成のエクスポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1385b-114">On the **Actions** menu, click **Export configuration**.</span></span>
    
5. <span data-ttu-id="1385b-115">場所とファイル名を指定し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1385b-115">Specify a location and file name, and then click **Save**.</span></span>
    
### <a name="to-import-a-voice-routing-configuration"></a><span data-ttu-id="1385b-116">音声ルーティング構成をインポートするには</span><span class="sxs-lookup"><span data-stu-id="1385b-116">To import a voice routing configuration</span></span>

1. <span data-ttu-id="1385b-117">RTCUniversalServerAdmins グループのメンバーとしてコンピューターにログオンするか、**CsVoiceAdministrator**、**CsServerAdministrator**、または **CsAdministrator** 管理者役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="1385b-117">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="1385b-118">Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="1385b-118">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="1385b-119">左側のナビゲーション バーで [**音声ルーティング**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1385b-119">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="1385b-120">[**操作**] メニューの [**構成のインポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1385b-120">On the **Actions** menu, click **Import configuration**.</span></span>
    
5. <span data-ttu-id="1385b-121">インポートする構成ファイルを検索し、[**開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1385b-121">Find the configuration file you want to import and then click **Open**.</span></span>
    
6. <span data-ttu-id="1385b-122">[**確定**] をクリックし、[**すべて確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1385b-122">Click **Commit**, and then click **Commit all**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1385b-123">音声構成ファイルをインポートする場合は、必ず [**すべて確定**] コマンドを実行して構成変更を公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1385b-123">Whenever you import a voice configuration file, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="1385b-124">詳細については、「 [Skype For business の音声ルーティング構成に保留中の変更を発行する](voice-route-config-changes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1385b-124">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>
  

