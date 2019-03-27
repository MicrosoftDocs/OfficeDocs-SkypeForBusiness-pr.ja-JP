---
title: 呼受付制御を有効にします。
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: " 呼び出し受付制御 (CAC) ネットワークを構成すると、CAC 帯域幅の制限を適用するを有効にする必要があります。"
ms.openlocfilehash: a683fe0f437fc1c3fa92784313135d094e43c8b1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30897644"
---
# <a name="enabling-call-admission-control-in-skype-for-business-server"></a><span data-ttu-id="f9cd4-103">Skype for Business Server での通話受付管理の有効化</span><span class="sxs-lookup"><span data-stu-id="f9cd4-103">Enabling call admission control in Skype for Business Server</span></span>

<span data-ttu-id="f9cd4-104">通話受付管理 (CAC) は、地域、サイト、およびサブネットで構成されるネットワークで、使用可能な帯域幅に基づいてオーディオおよびビデオ伝送に制限を課すことができます。</span><span class="sxs-lookup"><span data-stu-id="f9cd4-104">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth.</span></span> <span data-ttu-id="f9cd4-105">CAC ネットワークを構成した後は、CAC 帯域幅の制限を適用するを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9cd4-105">After you configure the CAC network, you must enable CAC to enforce the bandwidth limitations.</span></span> <span data-ttu-id="f9cd4-106">ビジネス サーバーのコントロール パネルの Skype を使用するにはこれを行う。</span><span class="sxs-lookup"><span data-stu-id="f9cd4-106">You can use the Skype for Business Server Control Panel to do this.</span></span>


## <a name="to-enable-cac-from-the-skype-for-business-server-control-panel"></a><span data-ttu-id="f9cd4-107">ビジネス サーバーのコントロール パネルの Skype から CAC を有効にするには</span><span class="sxs-lookup"><span data-stu-id="f9cd4-107">To enable CAC from the Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="f9cd4-108">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="f9cd4-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f9cd4-109">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="f9cd4-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="f9cd4-110">左側のナビゲーション ・ バーでは、**ネットワーク構成**をクリックし、し、[**グローバル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f9cd4-110">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="f9cd4-111">[**グローバル**] ページで、[**グローバル**構成] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f9cd4-111">On the **Global** page, click the **Global** configuration.</span></span>
   
    > [!NOTE]  
    > <span data-ttu-id="f9cd4-112">決してあるため、ボックスの一覧で複数のネットワーク構成、ビジネスのサーバー展開では、すべての Skype の 1 つだけのネットワークを構成できます。</span><span class="sxs-lookup"><span data-stu-id="f9cd4-112">Only one network can be configured for any Skype for Business Server deployment, so there will never be more than one network configuration in the list.</span></span> <span data-ttu-id="f9cd4-113">グローバル構成の名前を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="f9cd4-113">You cannot rename the Global configuration.</span></span>

5.  <span data-ttu-id="f9cd4-114">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f9cd4-114">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="f9cd4-115">**グローバル設定の編集**] ページで [**呼受付制御の有効にする**] チェック ボックスを選択し、[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f9cd4-115">On the **Edit Global Setting** page, select the **Enable call admission control** check box, and then click **Commit**.</span></span>

<span data-ttu-id="f9cd4-116">**コミット**] をクリックすると、構成のテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="f9cd4-116">When you click **Commit**, you run a test of the configuration.</span></span> <span data-ttu-id="f9cd4-117">**グローバル**のページに戻る場合、**グローバル設定の編集**] ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="f9cd4-117">The **Edit Global Settings** dialog box closes, returning you to the **Global** page.</span></span> <span data-ttu-id="f9cd4-118">(たとえば、interregion のルートを他のすべての領域には、すべての領域は接続されていない) 場合に正常に動作しない可能性が、ネットワーク構成では、エラーまたは不整合が検出された場合、警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f9cd4-118">You will receive a warning if any errors or inconsistencies are discovered in your network configuration that will prevent it from working correctly (for example, if every region is not connected to every other region through an interregion route).</span></span>

<span data-ttu-id="f9cd4-119">ネットワーク構成に変更を加えた場合は、グローバル構成を開き、**コミット**をクリックすると検証チェックをもう一度を実行できます。</span><span class="sxs-lookup"><span data-stu-id="f9cd4-119">If you make changes to your network configuration, you can run the validation check again by opening the Global configuration and clicking **Commit**.</span></span> <span data-ttu-id="f9cd4-120">最初の CAC を無効にする必要はありません: チェック ボックスをオンのままにし、[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f9cd4-120">You do not need to disable CAC first: leave the check box checked and click **Commit**.</span></span> <span data-ttu-id="f9cd4-121">この設定は、構成変更を加えずにいつでも行うことができます。</span><span class="sxs-lookup"><span data-stu-id="f9cd4-121">You can do this at any time without making any configuration changes.</span></span>

## <a name="see-also"></a><span data-ttu-id="f9cd4-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="f9cd4-122">See Also</span></span>

[<span data-ttu-id="f9cd4-123">通話受付管理の計画</span><span class="sxs-lookup"><span data-stu-id="f9cd4-123">Plan for call admission control</span></span>](../../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md) 
 
[<span data-ttu-id="f9cd4-124">通話受付管理の展開</span><span class="sxs-lookup"><span data-stu-id="f9cd4-124">Deploy call admission control</span></span>](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) 

[<span data-ttu-id="f9cd4-125">Get CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="f9cd4-125">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  

[<span data-ttu-id="f9cd4-126">セット CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="f9cd4-126">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  

[<span data-ttu-id="f9cd4-127">削除 CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="f9cd4-127">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
