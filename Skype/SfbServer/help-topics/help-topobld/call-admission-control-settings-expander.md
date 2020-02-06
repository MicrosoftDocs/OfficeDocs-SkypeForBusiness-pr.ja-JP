---
title: 通話受付管理設定エキスパンダー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.PdpSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dc94f75e-9abe-4e02-b835-3c845b317d65
description: 通話受付管理 (CAC) は、地域、サイト、およびサブネットで構成されるネットワークで、使用可能な帯域幅に基づいてオーディオおよびビデオ伝送に制限を課すことができます。CAC のネットワークを構成した後は、帯域幅の制限を有効にするために CAC を有効にする必要があります。
ms.openlocfilehash: 8060c6d17cf39472f0d0f0618d9f423050c0278b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820259"
---
# <a name="call-admission-control-settings-expander"></a><span data-ttu-id="31ee0-104">通話受付管理設定エキスパンダー</span><span class="sxs-lookup"><span data-stu-id="31ee0-104">Call Admission Control Settings Expander</span></span>
 
<span data-ttu-id="31ee0-p102">通話受付管理 (CAC) は、地域、サイト、およびサブネットで構成されるネットワークで、使用可能な帯域幅に基づいてオーディオおよびビデオ伝送に制限を課すことができます。CAC のネットワークを構成した後は、帯域幅の制限を有効にするために CAC を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="31ee0-p102">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth. After you configure the network for CAC, you must enable CAC in order for the bandwidth limitations to be enforced.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="31ee0-107">コントロール パネルまたは管理シェル コマンドレットを使用して CAC を有効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="31ee0-107">You can also use control panel or the management shell cmdlets to enable CAC.</span></span> 
  
<span data-ttu-id="31ee0-108">サイトの [**プロパティの編集**] ダイアログ ボックスの [**通話受付管理の設定**] セクションでは、次の設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="31ee0-108">In the **Call Admission Control Setting** section of the **Edit Properties** dialog box for your site, you can change the following settings:</span></span>
  
- <span data-ttu-id="31ee0-109">**通話受付制御を有効にする**この設定を選択すると、CAC が有効になります。</span><span class="sxs-lookup"><span data-stu-id="31ee0-109">**Enable Call Admission Control** Select this setting to enable CAC.</span></span> <span data-ttu-id="31ee0-110">ネットワーク全体で CAC を無効にするには、この設定をオフにします。</span><span class="sxs-lookup"><span data-stu-id="31ee0-110">Clear this setting to disable CAC for your entire network.</span></span> <span data-ttu-id="31ee0-111">CAC を有効にするには、CAC 用にネットワークを構成しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="31ee0-111">To enable CAC, you must have configured your network for CAC.</span></span> <span data-ttu-id="31ee0-112">詳細については、展開ドキュメントの「 [Skype For Business Server 2015 での通話受付制御の展開](../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31ee0-112">For details, see [Deploy call admission control in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) in the Deployment documentation.</span></span>
    
- <span data-ttu-id="31ee0-113">**通話受付制御を実行するフロントエンドプール**CAC を有効にした場合は、それを実行するプールを変更できます。</span><span class="sxs-lookup"><span data-stu-id="31ee0-113">**Front End pool to run Call Admission Control** If you enabled CAC, you can change the pool that runs it.</span></span> <span data-ttu-id="31ee0-114">ドロップダウン リストからプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="31ee0-114">Select the pool from the drop-down list.</span></span>
    

