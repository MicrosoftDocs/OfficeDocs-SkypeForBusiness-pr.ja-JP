---
title: 通話受付管理の有効化
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: " 通話受付管理 (CAC) ネットワークを構成した後、CAC を有効にして帯域幅制限を適用する必要があります。"
ms.openlocfilehash: 8e996b4d2272144a35f667a5d6987b2cb91af708
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816507"
---
# <a name="enabling-call-admission-control-in-skype-for-business-server"></a><span data-ttu-id="fbf3e-103">Skype for Business Server での通話受付管理の有効化</span><span class="sxs-lookup"><span data-stu-id="fbf3e-103">Enabling call admission control in Skype for Business Server</span></span>

<span data-ttu-id="fbf3e-104">通話受付管理 (CAC) は、使用可能な帯域幅に基づいてオーディオおよびビデオ伝送に制限を課すことができる地域、サイト、およびサブネットで構成されるネットワークです。</span><span class="sxs-lookup"><span data-stu-id="fbf3e-104">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth.</span></span> <span data-ttu-id="fbf3e-105">CAC ネットワークの構成後、CAC を有効にして、帯域幅制限を強制的に適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fbf3e-105">After you configure the CAC network, you must enable CAC to enforce the bandwidth limitations.</span></span> <span data-ttu-id="fbf3e-106">これを行うには、Skype for Business Server コントロール パネルを使用します。</span><span class="sxs-lookup"><span data-stu-id="fbf3e-106">You can use the Skype for Business Server Control Panel to do this.</span></span>


## <a name="to-enable-cac-from-the-skype-for-business-server-control-panel"></a><span data-ttu-id="fbf3e-107">Skype for Business Server コントロール パネルから CAC を有効にするには</span><span class="sxs-lookup"><span data-stu-id="fbf3e-107">To enable CAC from the Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="fbf3e-108">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="fbf3e-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="fbf3e-109">ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="fbf3e-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="fbf3e-110">左側のナビゲーション バーで、[ネットワーク構成] **をクリック** し、[グローバル] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="fbf3e-110">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="fbf3e-111">[**グローバル**] ページで [**グローバル**] 構成をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fbf3e-111">On the **Global** page, click the **Global** configuration.</span></span>
   
    > [!NOTE]  
    > <span data-ttu-id="fbf3e-112">すべての Skype for Business Server 展開に対して構成できるネットワークは 1 つだけなので、一覧に複数のネットワーク構成が含めになる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fbf3e-112">Only one network can be configured for any Skype for Business Server deployment, so there will never be more than one network configuration in the list.</span></span> <span data-ttu-id="fbf3e-113">グローバル構成の名前は変更できません。</span><span class="sxs-lookup"><span data-stu-id="fbf3e-113">You cannot rename the Global configuration.</span></span>

5.  <span data-ttu-id="fbf3e-114">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fbf3e-114">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="fbf3e-115">[**グローバル設定の編集**] ページの [**通話受付管理の有効化**] チェック ボックスをオンにして、[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fbf3e-115">On the **Edit Global Setting** page, select the **Enable call admission control** check box, and then click **Commit**.</span></span>

<span data-ttu-id="fbf3e-p103">[**確定**] をクリックすると、構成のテストが実行されます。 [**グローバル設定の編集**] ダイアログ ボックスが閉じ、再び、[**グローバル**] ページが表示されます。 ネットワーク構成で、ネットワークの正しい動作を妨げるエラーまたは不整合 (たとえば、すべての地域が他のすべての地域に地域間ルート経由でそれぞれ接続される必要があるがそうなっていない場合) が検出されると、警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fbf3e-p103">When you click **Commit**, you run a test of the configuration. The **Edit Global Settings** dialog box closes, returning you to the **Global** page. You will receive a warning if any errors or inconsistencies are discovered in your network configuration that will prevent it from working correctly (for example, if every region is not connected to every other region through an interregion route).</span></span>

<span data-ttu-id="fbf3e-p104">ネットワーク構成に変更を加えた場合は、グローバル構成を開き [**確定**] をクリックすることで、検証チェックを再度実行できます。 最初に、CAC を無効にする必要はありません。 チェック ボックスをオンのままにして、[**確定**] をクリックしてください。 これは、構成に変更を加えていない場合も含め、いつでも実行できます。</span><span class="sxs-lookup"><span data-stu-id="fbf3e-p104">If you make changes to your network configuration, you can run the validation check again by opening the Global configuration and clicking **Commit**. You do not need to disable CAC first: leave the check box checked and click **Commit**. You can do this at any time without making any configuration changes.</span></span>

## <a name="see-also"></a><span data-ttu-id="fbf3e-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="fbf3e-122">See Also</span></span>

[<span data-ttu-id="fbf3e-123">通話受付管理を計画する</span><span class="sxs-lookup"><span data-stu-id="fbf3e-123">Plan for call admission control</span></span>](../../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md) 
 
[<span data-ttu-id="fbf3e-124">通話受付管理の展開</span><span class="sxs-lookup"><span data-stu-id="fbf3e-124">Deploy call admission control</span></span>](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) 

[<span data-ttu-id="fbf3e-125">Get-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="fbf3e-125">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  

[<span data-ttu-id="fbf3e-126">Set-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="fbf3e-126">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  

[<span data-ttu-id="fbf3e-127">Remove-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="fbf3e-127">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
