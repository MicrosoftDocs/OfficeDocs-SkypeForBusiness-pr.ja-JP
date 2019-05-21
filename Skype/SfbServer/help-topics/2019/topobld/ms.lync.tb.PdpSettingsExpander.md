---
title: 通話受付管理設定エキスパンダー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PdpSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dc94f75e-9abe-4e02-b835-3c845b317d65
ROBOTS: NOINDEX, NOFOLLOW
description: 通話受付管理 (CAC) は、地域、サイト、およびサブネットで構成されるネットワークで、使用可能な帯域幅に基づいてオーディオおよびビデオ伝送に制限を課すことができます。CAC のネットワークを構成した後は、帯域幅の制限を有効にするために CAC を有効にする必要があります。
ms.openlocfilehash: aac6fdb1633216409d876804d7bd132574c94231
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303215"
---
# <a name="call-admission-control-settings-expander"></a><span data-ttu-id="3cbeb-104">通話受付管理設定エキスパンダー</span><span class="sxs-lookup"><span data-stu-id="3cbeb-104">Call Admission Control Settings Expander</span></span>
 
<span data-ttu-id="3cbeb-p102">通話受付管理 (CAC) は、地域、サイト、およびサブネットで構成されるネットワークで、使用可能な帯域幅に基づいてオーディオおよびビデオ伝送に制限を課すことができます。CAC のネットワークを構成した後は、帯域幅の制限を有効にするために CAC を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3cbeb-p102">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth. After you configure the network for CAC, you must enable CAC in order for the bandwidth limitations to be enforced.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="3cbeb-107">コントロール パネルまたは管理シェル コマンドレットを使用して CAC を有効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="3cbeb-107">You can also use control panel or the management shell cmdlets to enable CAC.</span></span> 
  
<span data-ttu-id="3cbeb-108">サイトの [**プロパティの編集**] ダイアログ ボックスの [**通話受付管理の設定**] セクションでは、次の設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="3cbeb-108">In the **Call Admission Control Setting** section of the **Edit Properties** dialog box for your site, you can change the following settings:</span></span>
  
- <span data-ttu-id="3cbeb-109">**通話受付制御を有効にする**この設定を選択すると、CAC が有効になります。</span><span class="sxs-lookup"><span data-stu-id="3cbeb-109">**Enable Call Admission Control** Select this setting to enable CAC.</span></span> <span data-ttu-id="3cbeb-110">ネットワーク全体で CAC を無効にするには、この設定をオフにします。</span><span class="sxs-lookup"><span data-stu-id="3cbeb-110">Clear this setting to disable CAC for your entire network.</span></span> <span data-ttu-id="3cbeb-111">CAC を有効にするには、CAC 用にネットワークを構成しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="3cbeb-111">To enable CAC, you must have configured your network for CAC.</span></span> <span data-ttu-id="3cbeb-112">詳細については、展開ドキュメントの「 [Skype For Business Server での通話受付制御の展開](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3cbeb-112">For details, see [Deploy call admission control in Skype for Business Server](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) in the Deployment documentation.</span></span>
    
- <span data-ttu-id="3cbeb-113">**通話受付制御を実行するフロントエンドプール**CAC を有効にした場合は、それを実行するプールを変更できます。</span><span class="sxs-lookup"><span data-stu-id="3cbeb-113">**Front End pool to run Call Admission Control** If you enabled CAC, you can change the pool that runs it.</span></span> <span data-ttu-id="3cbeb-114">ドロップダウン リストからプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="3cbeb-114">Select the pool from the drop-down list.</span></span>
    

