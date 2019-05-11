---
title: ビジネス用の Skype のユーザーのコール パークを有効にします。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9430763f-3394-467c-9c6d-426bf761604e
description: ビジネス サーバーのエンタープライズ VoIP のユーザーが Skype のコール パークを有効にします。
ms.openlocfilehash: 228ff5549487df04a264ed217bed43196d93ca8d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33892469"
---
# <a name="enable-call-park-for-users-in-skype-for-business"></a><span data-ttu-id="06bd5-103">ビジネス用の Skype のユーザーのコール パークを有効にします。</span><span class="sxs-lookup"><span data-stu-id="06bd5-103">Enable Call Park for users in Skype for Business</span></span>
 
<span data-ttu-id="06bd5-104">ビジネス サーバーのエンタープライズ VoIP のユーザーが Skype のコール パークを有効にします。</span><span class="sxs-lookup"><span data-stu-id="06bd5-104">Enable users for Call Park in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="06bd5-105">既定では、すべてのユーザーに対してコール パークが無効になります。</span><span class="sxs-lookup"><span data-stu-id="06bd5-105">By default, Call Park is disabled for all users.</span></span> <span data-ttu-id="06bd5-106">ユーザーが呼び出しを駐車または音声ポリシーでコール パークの有効になるまで停止の呼び出しを取得できません。</span><span class="sxs-lookup"><span data-stu-id="06bd5-106">Users cannot park calls or retrieve parked calls until they are enabled for Call Park in voice policy.</span></span>
  
<span data-ttu-id="06bd5-107">グローバル スコープまたはサイト スコープまたはユーザー スコープで、コール パークを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="06bd5-107">You can enable Call Park at the global scope, or at the site scope or user scope.</span></span> <span data-ttu-id="06bd5-108">ユーザー スコープはサイト スコープより優先され、サイト スコープはグローバル スコープよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="06bd5-108">User scope takes precedence over site scope, and site scope takes precedence over global scope.</span></span> <span data-ttu-id="06bd5-109">複数のボイス ポリシーがある場合は、コール パーク、グローバル ポリシーだけではなくを有効にするすべてのポリシーを確認します。</span><span class="sxs-lookup"><span data-stu-id="06bd5-109">If you have multiple voice policies, review all the policies to enable Call Park, not just the global policy.</span></span>
  
### <a name="to-use-skype-for-business-server-control-panel-to-enable-call-park-for-users"></a><span data-ttu-id="06bd5-110">ユーザーに対してコール パークを有効にするビジネス サーバーのコントロール パネルの Skype を使用するには</span><span class="sxs-lookup"><span data-stu-id="06bd5-110">To Use Skype for Business Server Control Panel to Enable Call Park for Users</span></span>

1. <span data-ttu-id="06bd5-111">**RTCUniversalServerAdmins** グループのメンバーとしてコンピューターにログオンするか、**CsVoiceAdministrator**、**CsServerAdministrator**、または **CsAdministrator** 管理者役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="06bd5-111">Log on to the computer as a member of the **RTCUniversalServerAdmins** group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="06bd5-112">Skype をビジネス サーバーのコントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="06bd5-112">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="06bd5-113">左側のナビゲーション バーで [**音声ルーティング**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="06bd5-113">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="06bd5-114">[**音声ポリシー**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="06bd5-114">Click the **Voice Policy** tab.</span></span>
    
5. <span data-ttu-id="06bd5-115">既存の音声ポリシーをダブルクリックして、[**音声ポリシーの編集**] ダイアログ ボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="06bd5-115">Double-click an existing voice policy to open the **Edit Voice Policy** dialog box.</span></span>
    
6. <span data-ttu-id="06bd5-116">[**通話機能**] の [**コール パークを有効にする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="06bd5-116">Under **Calling features**, select **Enable call park**.</span></span>
    
7. <span data-ttu-id="06bd5-117">[**OK**] をクリックして音声ポリシーを保存します。</span><span class="sxs-lookup"><span data-stu-id="06bd5-117">Click **OK** to save the voice policy</span></span>
    
### <a name="to-use-cmdlets-to-enable-call-park-for-users"></a><span data-ttu-id="06bd5-118">ユーザーのコール パークを有効にするコマンドレットを使用するには</span><span class="sxs-lookup"><span data-stu-id="06bd5-118">To Use Cmdlets to Enable Call Park for Users</span></span>

1. <span data-ttu-id="06bd5-119">RTCUniversalServerAdmins グループのメンバーとしてコンピューターにログオンするか、CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator 管理者役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="06bd5-119">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="06bd5-120">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="06bd5-120">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="06bd5-121">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="06bd5-121">Run:</span></span>
    
   ```
   Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
   ```

    <span data-ttu-id="06bd5-122">たとえば、既定のグローバル音声ポリシーのコール パークを有効にします。</span><span class="sxs-lookup"><span data-stu-id="06bd5-122">For example, to enable Call Park for the default global voice policy:</span></span>
    
   ```
   Set-CsVoicePolicy -EnableCallPark $true
   ```

## <a name="see-also"></a><span data-ttu-id="06bd5-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="06bd5-123">See also</span></span>



[<span data-ttu-id="06bd5-124">作成し、音声ポリシーを変更または Skype ビジネスのために PSTN 使用法レコードを構成します。</span><span class="sxs-lookup"><span data-stu-id="06bd5-124">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>](voice-policy-and-pstn-usage-records.md)

