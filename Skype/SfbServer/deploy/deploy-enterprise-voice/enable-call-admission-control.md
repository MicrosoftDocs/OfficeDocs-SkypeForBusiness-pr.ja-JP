---
title: Skype for Business Server で通話受付管理を有効にする
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
ms.assetid: 80201105-18f7-4c02-9c71-8df5a952f6c7
description: Skype for Business Server エンタープライズ VoIP で通話受付管理を有効にします。
ms.openlocfilehash: 9ea8b03b48827abbb73e3d6e93ffb88ab93ad1ff
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831017"
---
# <a name="enable-call-admission-control-in-skype-for-business-server"></a><span data-ttu-id="f7b46-103">Skype for Business Server で通話受付管理を有効にする</span><span class="sxs-lookup"><span data-stu-id="f7b46-103">Enable call admission control in Skype for Business Server</span></span>
 
<span data-ttu-id="f7b46-104">Skype for Business Server エンタープライズ VoIP で通話受付管理を有効にします。</span><span class="sxs-lookup"><span data-stu-id="f7b46-104">Enable call admission control in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="f7b46-105">通話受付管理展開のネットワーク設定を構成したら、帯域幅ポリシーを反映させるために CAC を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7b46-105">After you have configured your network settings for call admission control deployment, you must enable CAC to put your bandwidth policies into effect.</span></span>
  
### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="f7b46-106">Skype for Business Server 管理シェルを使用して通話受付管理を有効にするには</span><span class="sxs-lookup"><span data-stu-id="f7b46-106">To enable call admission control by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="f7b46-107">Skype for Business Server 管理シェルを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business 2015]** をクリックして **、[Skype for Business Server 管理シェル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7b46-107">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="f7b46-p101">Set-CsNetworkConfiguration コマンドレットを実行して、ネットワークの CAC を有効にします。たとえば、以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="f7b46-p101">Run the Set-CsNetworkConfiguration cmdlet to enable CAC in your network. For example, run:</span></span>
    
   ```powershell
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
   ```

    <span data-ttu-id="f7b46-110">ネットワークの CAC を無効にする場合は、次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="f7b46-110">If you want to disable CAC in your network, run the following:</span></span>
    
   ```powershell
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0
   ```

### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="f7b46-111">Skype for Business Server コントロール パネルを使用して通話受付管理を有効にするには</span><span class="sxs-lookup"><span data-stu-id="f7b46-111">To enable call admission control by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="f7b46-112">Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="f7b46-112">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="f7b46-113">左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7b46-113">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="f7b46-114">[**グローバル**] ナビゲーション ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7b46-114">Click the **Global** navigation button.</span></span>
    
4. <span data-ttu-id="f7b46-115">一覧で [**グローバル**] をクリックし、[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7b46-115">Click **Global** in the list, and then select **Show Details** on the **Edit** menu.</span></span>
    
5. <span data-ttu-id="f7b46-116">[**グローバル設定の編集**] ページの [**通話受付管理の有効化**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="f7b46-116">On the **Edit Global Settings** page, select the **Enable call admission control** check box.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f7b46-117">展開全体で通話受付管理を無効にする場合は、このチェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="f7b46-117">If you want to disable call admission control throughout your deployment, clear this check box.</span></span> 
  
6. <span data-ttu-id="f7b46-118">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7b46-118">Click **Commit**.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="f7b46-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="f7b46-119">See also</span></span>

[<span data-ttu-id="f7b46-120">Get-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="f7b46-120">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkconfiguration?view=skype-ps)
  
[<span data-ttu-id="f7b46-121">Set-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="f7b46-121">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkconfiguration?view=skype-ps)
  
[<span data-ttu-id="f7b46-122">Remove-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="f7b46-122">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkconfiguration?view=skype-ps)
