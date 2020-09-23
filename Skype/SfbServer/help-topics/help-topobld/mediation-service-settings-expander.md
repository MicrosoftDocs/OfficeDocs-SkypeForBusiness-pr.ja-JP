---
title: 仲介サービス設定の展開
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.FeMediationServiceSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 142c1acd-cdaa-4922-8379-aa1bdf56a964
description: '[仲介サーバー] では、次の情報を指定できます。'
ms.openlocfilehash: 9a6da594452b4675b3eed1ca734fa3b54c9117b9
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215148"
---
# <a name="mediation-service-settings-expander"></a><span data-ttu-id="28728-103">仲介サービス設定の展開</span><span class="sxs-lookup"><span data-stu-id="28728-103">Mediation Service Settings Expander</span></span>

<span data-ttu-id="28728-104">[**仲介サーバー**] では、次の情報を指定できます。</span><span class="sxs-lookup"><span data-stu-id="28728-104">For **Mediation Server**, you can specify the following:</span></span>

<span data-ttu-id="28728-105">仲介サーバーをフロントエンドプールまたは Standard Edition サーバーに併置する場合は、[併置された **仲介サーバーを有効に**する] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="28728-105">If you are collocating the Mediation Server onto the Front End pool or the Standard Edition server, select the check box **Collocated Mediation Server enabled**.</span></span> <span data-ttu-id="28728-106">仲介サーバーを併置しない場合、このセクションで定義可能な設定はありません。</span><span class="sxs-lookup"><span data-stu-id="28728-106">If you choose not to collocate the Mediation Server, there are no definable settings in this section.</span></span>

<span data-ttu-id="28728-p102">仲介サーバーの併置を有効にした場合は、サーバーでのトランスポート層セキュリティ (TLS) のリッスン ポートの範囲を定義する必要があります。既定のポートは 5067 です。[**TCP ポートを有効にする**] を選択した場合は、併置される仲介サーバーの 伝送制御プロトコル (TCP) ポートを定義する必要があります。これは省略可能な設定です。この設定が必要かどうかは、ゲートウェイまたは公衆交換電話網 (PSTN) の要件を参照して判断してください。既定では、TCP ポートの値は 5068 です。</span><span class="sxs-lookup"><span data-stu-id="28728-p102">If you have enabled the collocation of the Mediation Server, you need to define the listening port range on the server for Transport Layer Security (TLS). By default, this port is 5067. If you select **Enable TCP port**, you must define a Transmission Control Protocol (TCP) port for the collocated Mediation Server. This is an optional setting, and you should refer to the requirements of your gateway or public switched telephone network (PSTN) requirements to determine if you need this. By default, the TCP port value is 5068.</span></span>

<span data-ttu-id="28728-p103">併置された仲介サーバーに関連付ける PSTN ゲートウェイを定義します。このゲートウェイを既に定義している場合は、それらのゲートウェイを仲介サーバーに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="28728-p103">You define PSTN gateways that are associated with the collocated Mediation Server. If you have already defined gateways, they will be available to associate with the Mediation Server.</span></span>

<span data-ttu-id="28728-p104">仲介サーバーに複数のゲートウェイを関連付けている場合は、関連付けた最初のゲートウェイが既定のゲートウェイとなります。既定のゲートウェイとして別のゲートウェイを選択する必要がある場合は、既定にするゲートウェイを選択して、[**既定にする**] をクリックします。既定のゲートウェイとしての選択を解除するには、[**既定値の解除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="28728-p104">If you have more than one gateway associated with a Mediation Server, the first gateway associated will be the default gateway. If you need to choose another gateway as the default gateway, select the gateway that you want to make the default, and click **Make Default**. To unselect the gateway as the default, click **Unmake Default**.</span></span>

<span data-ttu-id="28728-117">Enterprise Edition フロントエンドプールまたは Standard Edition サーバーの設定の定義と構成の詳細については、「 [トポロジの定義と構成](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) 」、および「 [仲介サーバーの展開とピアの定義](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28728-117">For details about defining and configuring the settings for the Enterprise Edition Front End pool or Standard Edition server, see [Defining and Configuring the Topology](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) and [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).</span></span>


