---
title: 通話受付管理設定エキスパンダー
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 通話受付管理 (CAC) は、使用可能な帯域幅に基づいてオーディオおよびビデオ伝送に制限を課すことができる地域、サイト、およびサブネットで構成されるネットワークです。 CAC のネットワークを構成した後、帯域幅制限を適用するには CAC を有効にする必要があります。
ms.openlocfilehash: 1278cb19e4c8df047d97e5f391ca940255f094cc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833117"
---
# <a name="call-admission-control-settings-expander"></a><span data-ttu-id="75769-104">通話受付管理設定エキスパンダー</span><span class="sxs-lookup"><span data-stu-id="75769-104">Call Admission Control Settings Expander</span></span>
 
<span data-ttu-id="75769-105">通話受付管理 (CAC) は、使用可能な帯域幅に基づいてオーディオおよびビデオ伝送に制限を課すことができる地域、サイト、およびサブネットで構成されるネットワークです。</span><span class="sxs-lookup"><span data-stu-id="75769-105">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth.</span></span> <span data-ttu-id="75769-106">CAC のネットワークを構成した後、帯域幅制限を適用するには CAC を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="75769-106">After you configure the network for CAC, you must enable CAC in order for the bandwidth limitations to be enforced.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="75769-107">コントロール パネルまたは管理シェル コマンドレットを使用して CAC を有効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="75769-107">You can also use control panel or the management shell cmdlets to enable CAC.</span></span> 
  
<span data-ttu-id="75769-108">サイトの **[プロパティの編集**]ダイアログ ボックスの [通話受付管理の設定] セクションでは、次の設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="75769-108">In the **Call Admission Control Setting** section of the **Edit Properties** dialog box for your site, you can change the following settings:</span></span>
  
- <span data-ttu-id="75769-109">**通話受付管理を有効にする** CAC を有効にするには、この設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="75769-109">**Enable Call Admission Control** Select this setting to enable CAC.</span></span> <span data-ttu-id="75769-110">ネットワーク全体で CAC を無効にするには、この設定をオフにします。</span><span class="sxs-lookup"><span data-stu-id="75769-110">Clear this setting to disable CAC for your entire network.</span></span> <span data-ttu-id="75769-111">CAC を有効にするには、CAC 用にネットワークを構成している必要があります。</span><span class="sxs-lookup"><span data-stu-id="75769-111">To enable CAC, you must have configured your network for CAC.</span></span> <span data-ttu-id="75769-112">詳細については、「展開」の [ドキュメントの「Deploy call admission control in Skype for Business Server 2015」](../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75769-112">For details, see [Deploy call admission control in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) in the Deployment documentation.</span></span>
    
- <span data-ttu-id="75769-113">**通話受付管理を実行するフロントエンド プール** CAC を有効にした場合は、CAC を実行するプールを変更できます。</span><span class="sxs-lookup"><span data-stu-id="75769-113">**Front End pool to run Call Admission Control** If you enabled CAC, you can change the pool that runs it.</span></span> <span data-ttu-id="75769-114">ドロップダウン リストからプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="75769-114">Select the pool from the drop-down list.</span></span>
    

