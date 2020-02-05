---
title: Skype for Business のユーザーに対してコールパークを有効にする
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.assetid: 9430763f-3394-467c-9c6d-426bf761604e
description: Skype for Business Server Enterprise Voice でのコールパークのユーザーを有効にします。
ms.openlocfilehash: 6642af2a7af698a1127ff2a9bb4e45df73d18c50
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767280"
---
# <a name="enable-call-park-for-users-in-skype-for-business"></a><span data-ttu-id="9febb-103">Skype for Business のユーザーに対してコールパークを有効にする</span><span class="sxs-lookup"><span data-stu-id="9febb-103">Enable Call Park for users in Skype for Business</span></span>
 
<span data-ttu-id="9febb-104">Skype for Business Server Enterprise Voice でのコールパークのユーザーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="9febb-104">Enable users for Call Park in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="9febb-105">既定では、すべてのユーザーに対して [コールパーク] が無効になっています。</span><span class="sxs-lookup"><span data-stu-id="9febb-105">By default, Call Park is disabled for all users.</span></span> <span data-ttu-id="9febb-106">ユーザーは、音声ポリシーでのコールパークが有効になるまで、通話をパークしたり、保留中の通話を取得したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="9febb-106">Users cannot park calls or retrieve parked calls until they are enabled for Call Park in voice policy.</span></span>
  
<span data-ttu-id="9febb-107">グローバルスコープまたはサイトのスコープまたはユーザーの範囲で、通話パークを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="9febb-107">You can enable Call Park at the global scope, or at the site scope or user scope.</span></span> <span data-ttu-id="9febb-108">ユーザー スコープはサイト スコープより優先され、サイト スコープはグローバル スコープよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="9febb-108">User scope takes precedence over site scope, and site scope takes precedence over global scope.</span></span> <span data-ttu-id="9febb-109">複数のボイスポリシーがある場合は、グローバルポリシーだけでなく、すべてのポリシーを確認してコールパークを有効にします。</span><span class="sxs-lookup"><span data-stu-id="9febb-109">If you have multiple voice policies, review all the policies to enable Call Park, not just the global policy.</span></span>
  
### <a name="to-use-skype-for-business-server-control-panel-to-enable-call-park-for-users"></a><span data-ttu-id="9febb-110">Skype for Business Server コントロールパネルを使用して、ユーザーに対してコールパークを有効にするには</span><span class="sxs-lookup"><span data-stu-id="9febb-110">To Use Skype for Business Server Control Panel to Enable Call Park for Users</span></span>

1. <span data-ttu-id="9febb-111">**RTCUniversalServerAdmins** グループのメンバーとしてコンピューターにログオンするか、**CsVoiceAdministrator**、**CsServerAdministrator**、または **CsAdministrator** 管理者役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="9febb-111">Log on to the computer as a member of the **RTCUniversalServerAdmins** group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="9febb-112">Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="9febb-112">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="9febb-113">左側のナビゲーション バーで [**音声ルーティング**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9febb-113">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="9febb-114">[**音声ポリシー**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9febb-114">Click the **Voice Policy** tab.</span></span>
    
5. <span data-ttu-id="9febb-115">既存の音声ポリシーをダブルクリックして、[**音声ポリシーの編集**] ダイアログ ボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="9febb-115">Double-click an existing voice policy to open the **Edit Voice Policy** dialog box.</span></span>
    
6. <span data-ttu-id="9febb-116">[**通話機能**] の [**コール パークを有効にする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9febb-116">Under **Calling features**, select **Enable call park**.</span></span>
    
7. <span data-ttu-id="9febb-117">[**OK**] をクリックして音声ポリシーを保存します。</span><span class="sxs-lookup"><span data-stu-id="9febb-117">Click **OK** to save the voice policy</span></span>
    
### <a name="to-use-cmdlets-to-enable-call-park-for-users"></a><span data-ttu-id="9febb-118">コマンドレットを使用してユーザーのコールパークを有効にするには</span><span class="sxs-lookup"><span data-stu-id="9febb-118">To Use Cmdlets to Enable Call Park for Users</span></span>

1. <span data-ttu-id="9febb-119">RTCUniversalServerAdmins グループのメンバーとしてコンピューターにログオンするか、CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator 管理者役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="9febb-119">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="9febb-120">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="9febb-120">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="9febb-121">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="9febb-121">Run:</span></span>
    
   ```powershell
   Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
   ```

    <span data-ttu-id="9febb-122">たとえば、既定のグローバルボイスポリシーのコールパークを有効にするには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="9febb-122">For example, to enable Call Park for the default global voice policy:</span></span>
    
   ```powershell
   Set-CsVoicePolicy -EnableCallPark $true
   ```

## <a name="see-also"></a><span data-ttu-id="9febb-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="9febb-123">See also</span></span>



[<span data-ttu-id="9febb-124">Skype for Business で音声ポリシーを作成または変更し、PSTN 使用状況レコードを構成する</span><span class="sxs-lookup"><span data-stu-id="9febb-124">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>](voice-policy-and-pstn-usage-records.md)

