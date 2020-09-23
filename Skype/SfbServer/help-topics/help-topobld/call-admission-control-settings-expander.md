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
- CSH
ms.custom:
- ms.lync.tb.PdpSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dc94f75e-9abe-4e02-b835-3c845b317d65
description: 通話受付管理 (CAC) は、使用可能な帯域幅に基づいてオーディオおよびビデオ伝送に制限を課すことができる地域、サイト、およびサブネットで構成されるネットワークです。 CAC のネットワークを構成したら、帯域幅制限を適用するために CAC を有効にする必要があります。
ms.openlocfilehash: 4df5a9f5be761e1e039a259d0abf4a38d51170df
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218788"
---
# <a name="call-admission-control-settings-expander"></a><span data-ttu-id="dda79-104">通話受付管理設定エキスパンダー</span><span class="sxs-lookup"><span data-stu-id="dda79-104">Call Admission Control Settings Expander</span></span>
 
<span data-ttu-id="dda79-105">通話受付管理 (CAC) は、使用可能な帯域幅に基づいてオーディオおよびビデオ伝送に制限を課すことができる地域、サイト、およびサブネットで構成されるネットワークです。</span><span class="sxs-lookup"><span data-stu-id="dda79-105">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth.</span></span> <span data-ttu-id="dda79-106">CAC のネットワークを構成したら、帯域幅制限を適用するために CAC を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="dda79-106">After you configure the network for CAC, you must enable CAC in order for the bandwidth limitations to be enforced.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="dda79-107">コントロールパネルまたは管理シェルコマンドレットを使用して CAC を有効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="dda79-107">You can also use control panel or the management shell cmdlets to enable CAC.</span></span> 
  
<span data-ttu-id="dda79-108">サイトの [**プロパティの編集**] ダイアログボックスの [**通話受付管理の設定**] セクションでは、次の設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="dda79-108">In the **Call Admission Control Setting** section of the **Edit Properties** dialog box for your site, you can change the following settings:</span></span>
  
- <span data-ttu-id="dda79-109">**通話受付管理を有効にする** CAC を有効にするには、この設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="dda79-109">**Enable Call Admission Control** Select this setting to enable CAC.</span></span> <span data-ttu-id="dda79-110">ネットワーク全体で CAC を無効にするには、この設定をオフにします。</span><span class="sxs-lookup"><span data-stu-id="dda79-110">Clear this setting to disable CAC for your entire network.</span></span> <span data-ttu-id="dda79-111">CAC を有効にするには、CAC 用にネットワークを構成しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="dda79-111">To enable CAC, you must have configured your network for CAC.</span></span> <span data-ttu-id="dda79-112">詳細については、「展開」のドキュメントの「 [deploy call 受付管理 In Skype For Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dda79-112">For details, see [Deploy call admission control in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) in the Deployment documentation.</span></span>
    
- <span data-ttu-id="dda79-113">**通話受付管理を実行するフロントエンドプール** CAC を有効にした場合、それを実行するプールを変更できます。</span><span class="sxs-lookup"><span data-stu-id="dda79-113">**Front End pool to run Call Admission Control** If you enabled CAC, you can change the pool that runs it.</span></span> <span data-ttu-id="dda79-114">ドロップダウンリストからプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="dda79-114">Select the pool from the drop-down list.</span></span>
    

