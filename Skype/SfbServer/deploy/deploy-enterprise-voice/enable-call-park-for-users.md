---
title: Skype for Business でユーザーのコール パークを有効にする
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
ms.assetid: 9430763f-3394-467c-9c6d-426bf761604e
description: Skype for Business Server のコール パークに対してユーザーを有効エンタープライズ VoIP。
ms.openlocfilehash: e9bbc42f5940af0cfc94ab83eae981dd023c9fcd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830957"
---
# <a name="enable-call-park-for-users-in-skype-for-business"></a><span data-ttu-id="f63c2-103">Skype for Business でユーザーのコール パークを有効にする</span><span class="sxs-lookup"><span data-stu-id="f63c2-103">Enable Call Park for users in Skype for Business</span></span>
 
<span data-ttu-id="f63c2-104">Skype for Business Server のコール パークに対してユーザーを有効エンタープライズ VoIP。</span><span class="sxs-lookup"><span data-stu-id="f63c2-104">Enable users for Call Park in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="f63c2-105">既定では、コール パークはすべてのユーザーに対して無効になっています。</span><span class="sxs-lookup"><span data-stu-id="f63c2-105">By default, Call Park is disabled for all users.</span></span> <span data-ttu-id="f63c2-106">ユーザーは、音声ポリシーでコール パークが有効になるまで、通話をパークしたり、パークされた通話を取得したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="f63c2-106">Users cannot park calls or retrieve parked calls until they are enabled for Call Park in voice policy.</span></span>
  
<span data-ttu-id="f63c2-107">コール パークは、グローバル スコープまたはサイト スコープまたはユーザー スコープで有効にできます。</span><span class="sxs-lookup"><span data-stu-id="f63c2-107">You can enable Call Park at the global scope, or at the site scope or user scope.</span></span> <span data-ttu-id="f63c2-108">ユーザー スコープはサイト スコープより優先され、サイト スコープはグローバル スコープよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="f63c2-108">User scope takes precedence over site scope, and site scope takes precedence over global scope.</span></span> <span data-ttu-id="f63c2-109">複数の音声ポリシーがある場合は、グローバル ポリシーではなく、すべてのポリシーを確認してコール パークを有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="f63c2-109">If you have multiple voice policies, review all the policies to enable Call Park, not just the global policy.</span></span>
  
### <a name="to-use-skype-for-business-server-control-panel-to-enable-call-park-for-users"></a><span data-ttu-id="f63c2-110">Skype for Business Server コントロール パネルを使用してユーザーのコール パークを有効にするには</span><span class="sxs-lookup"><span data-stu-id="f63c2-110">To Use Skype for Business Server Control Panel to Enable Call Park for Users</span></span>

1. <span data-ttu-id="f63c2-111">**RTCUniversalServerAdmins** グループのメンバーとして、または **CsVoiceAdministrator、CsServerAdministrator、\*\*\*\*または\*\*\*\*CsAdministrator** 管理役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="f63c2-111">Log on to the computer as a member of the **RTCUniversalServerAdmins** group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="f63c2-112">Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="f63c2-112">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="f63c2-113">左側のナビゲーション バーで [**音声ルーティング**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f63c2-113">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="f63c2-114">[音声ポリシー **] タブをクリック** します。</span><span class="sxs-lookup"><span data-stu-id="f63c2-114">Click the **Voice Policy** tab.</span></span>
    
5. <span data-ttu-id="f63c2-115">既存の音声ポリシーをダブルクリックして、[音声ポリシーの編集 **] ダイアログ ボックスを** 開きます。</span><span class="sxs-lookup"><span data-stu-id="f63c2-115">Double-click an existing voice policy to open the **Edit Voice Policy** dialog box.</span></span>
    
6. <span data-ttu-id="f63c2-116">[通話 **機能] で、[** コール パーク **を有効にする] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f63c2-116">Under **Calling features**, select **Enable call park**.</span></span>
    
7. <span data-ttu-id="f63c2-117">**[OK] を** クリックして音声ポリシーを保存する</span><span class="sxs-lookup"><span data-stu-id="f63c2-117">Click **OK** to save the voice policy</span></span>
    
### <a name="to-use-cmdlets-to-enable-call-park-for-users"></a><span data-ttu-id="f63c2-118">コマンドレットを使用してユーザーのコール パークを有効にするには</span><span class="sxs-lookup"><span data-stu-id="f63c2-118">To Use Cmdlets to Enable Call Park for Users</span></span>

1. <span data-ttu-id="f63c2-119">RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator 管理者役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="f63c2-119">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="f63c2-120">Skype for Business Server 管理シェルを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business 2015]** をクリックして **、[Skype for Business Server 管理シェル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f63c2-120">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="f63c2-121">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f63c2-121">Run:</span></span>
    
   ```powershell
   Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
   ```

    <span data-ttu-id="f63c2-122">たとえば、既定のグローバル音声ポリシーに対してコール パークを有効にするには、</span><span class="sxs-lookup"><span data-stu-id="f63c2-122">For example, to enable Call Park for the default global voice policy:</span></span>
    
   ```powershell
   Set-CsVoicePolicy -EnableCallPark $true
   ```

## <a name="see-also"></a><span data-ttu-id="f63c2-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="f63c2-123">See also</span></span>



[<span data-ttu-id="f63c2-124">音声ポリシーを作成または変更し、Skype for Business で PSTN 使用法レコードを構成する</span><span class="sxs-lookup"><span data-stu-id="f63c2-124">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>](voice-policy-and-pstn-usage-records.md)

