---
title: 通話受付管理設定エキスパンダー
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/25/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PdpSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dc94f75e-9abe-4e02-b835-3c845b317d65
description: 通話受付管理 (CAC) は、地域、サイト、およびサブネットで構成されるネットワークで、使用可能な帯域幅に基づいてオーディオおよびビデオ伝送に制限を課すことができます。CAC のネットワークを構成した後は、帯域幅の制限を有効にするために CAC を有効にする必要があります。
ms.openlocfilehash: f7731c77ded47be47068022ca708c2efa17773b9
ms.sourcegitcommit: 9d816453083c26fd24f8a1cdc0f53f3d218c43b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2018
---
# <a name="call-admission-control-settings-expander"></a><span data-ttu-id="229b9-104">通話受付管理設定エキスパンダー</span><span class="sxs-lookup"><span data-stu-id="229b9-104">Call Admission Control Settings Expander</span></span>
 
<span data-ttu-id="229b9-p102">通話受付管理 (CAC) は、地域、サイト、およびサブネットで構成されるネットワークで、使用可能な帯域幅に基づいてオーディオおよびビデオ伝送に制限を課すことができます。CAC のネットワークを構成した後は、帯域幅の制限を有効にするために CAC を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="229b9-p102">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth. After you configure the network for CAC, you must enable CAC in order for the bandwidth limitations to be enforced.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="229b9-107">コントロール パネルまたは管理シェル コマンドレットを使用して CAC を有効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="229b9-107">You can also use control panel or the management shell cmdlets to enable CAC.</span></span> 
  
<span data-ttu-id="229b9-108">サイトの [**プロパティの編集**] ダイアログ ボックスの [**通話受付管理の設定**] セクションでは、次の設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="229b9-108">In the **Call Admission Control Setting** section of the **Edit Properties** dialog box for your site, you can change the following settings:</span></span>
  
- <span data-ttu-id="229b9-109">**呼受付制御を有効にします。** CAC を有効にするには、この設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="229b9-109">**Enable Call Admission Control** Select this setting to enable CAC.</span></span> <span data-ttu-id="229b9-110">ネットワーク全体の CAC を無効にするには、この設定をオフにします。</span><span class="sxs-lookup"><span data-stu-id="229b9-110">Clear this setting to disable CAC for your entire network.</span></span> <span data-ttu-id="229b9-111">CAC を有効にするには、する必要がありますネットワークを構成した CAC のです。</span><span class="sxs-lookup"><span data-stu-id="229b9-111">To enable CAC, you must have configured your network for CAC.</span></span> <span data-ttu-id="229b9-112">詳細については、展開に関するドキュメントで[ビジネス サーバー 2015 の Skype での受付制御を呼び出し配置](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="229b9-112">For details, see [Deploy call admission control in Skype for Business Server 2015](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) in the Deployment documentation.</span></span>
    
- <span data-ttu-id="229b9-113">**受付制御の呼び出しを実行するフロント エンド プール**CAC を有効にした場合は、それを実行するプールを変更します。</span><span class="sxs-lookup"><span data-stu-id="229b9-113">**Front End pool to run Call Admission Control** If you enabled CAC, you can change the pool that runs it.</span></span> <span data-ttu-id="229b9-114">ドロップダウン リストからプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="229b9-114">Select the pool from the drop-down list.</span></span>
    

