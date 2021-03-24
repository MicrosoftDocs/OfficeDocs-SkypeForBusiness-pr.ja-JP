---
title: 仲介サービス設定の展開
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.FeMediationServiceSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 142c1acd-cdaa-4922-8379-aa1bdf56a964
ROBOTS: NOINDEX, NOFOLLOW
description: '[仲介サーバー] では、次の情報を指定できます。'
ms.openlocfilehash: e3593fd98c9207b6dd7033e5aac26170988ae956
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096903"
---
# <a name="mediation-service-settings-expander"></a><span data-ttu-id="8cc1e-103">仲介サービス設定エキスパンダー</span><span class="sxs-lookup"><span data-stu-id="8cc1e-103">Mediation Service Settings Expander</span></span>

<span data-ttu-id="8cc1e-104">[**仲介サーバー**] では、次の情報を指定できます。</span><span class="sxs-lookup"><span data-stu-id="8cc1e-104">For **Mediation Server**, you can specify the following:</span></span>

<span data-ttu-id="8cc1e-105">仲介サーバーをフロント エンド プールまたは Standard Edition サーバーに照合する場合は、[仲介サーバーを有効にする] チェック **ボックスをオンにします**。</span><span class="sxs-lookup"><span data-stu-id="8cc1e-105">If you are collocating the Mediation Server onto the Front End pool or the Standard Edition server, select the check box **Collocated Mediation Server enabled**.</span></span> <span data-ttu-id="8cc1e-106">仲介サーバーを併置しない場合、このセクションで定義可能な設定はありません。</span><span class="sxs-lookup"><span data-stu-id="8cc1e-106">If you choose not to collocate the Mediation Server, there are no definable settings in this section.</span></span>

<span data-ttu-id="8cc1e-p102">仲介サーバーの併置を有効にした場合は、サーバーでのトランスポート層セキュリティ (TLS) のリッスン ポートの範囲を定義する必要があります。既定のポートは 5067 です。[**TCP ポートを有効にする**] を選択した場合は、併置される仲介サーバーの 伝送制御プロトコル (TCP) ポートを定義する必要があります。これは省略可能な設定です。この設定が必要かどうかは、ゲートウェイまたは公衆交換電話網 (PSTN) の要件を参照して判断してください。既定では、TCP ポートの値は 5068 です。</span><span class="sxs-lookup"><span data-stu-id="8cc1e-p102">If you have enabled the collocation of the Mediation Server, you need to define the listening port range on the server for Transport Layer Security (TLS). By default, this port is 5067. If you select **Enable TCP port**, you must define a Transmission Control Protocol (TCP) port for the collocated Mediation Server. This is an optional setting, and you should refer to the requirements of your gateway or public switched telephone network (PSTN) requirements to determine if you need this. By default, the TCP port value is 5068.</span></span>

<span data-ttu-id="8cc1e-p103">併置された仲介サーバーに関連付ける PSTN ゲートウェイを定義します。このゲートウェイを既に定義している場合は、それらのゲートウェイを仲介サーバーに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="8cc1e-p103">You define PSTN gateways that are associated with the collocated Mediation Server. If you have already defined gateways, they will be available to associate with the Mediation Server.</span></span>

<span data-ttu-id="8cc1e-p104">仲介サーバーに複数のゲートウェイを関連付けている場合は、関連付けた最初のゲートウェイが既定のゲートウェイとなります。既定のゲートウェイとして別のゲートウェイを選択する必要がある場合は、既定にするゲートウェイを選択して、[**既定にする**] をクリックします。既定のゲートウェイとしての選択を解除するには、[**既定値の解除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8cc1e-p104">If you have more than one gateway associated with a Mediation Server, the first gateway associated will be the default gateway. If you need to choose another gateway as the default gateway, select the gateway that you want to make the default, and click **Make Default**. To unselect the gateway as the default, click **Unmake Default**.</span></span>

<span data-ttu-id="8cc1e-117">Enterprise Edition フロントエンド プールまたは Standard Edition サーバーの設定の定義と構成の詳細については[](/previous-versions/office/lync-server-2013/lync-server-2013-defining-and-configuring-the-topology)、「トポロジの定義と構成」および「[](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-mediation-servers-and-defining-peers)仲介サーバーの展開」および「ピアの定義」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8cc1e-117">For details about defining and configuring the settings for the Enterprise Edition Front End pool or Standard Edition server, see [Defining and Configuring the Topology](/previous-versions/office/lync-server-2013/lync-server-2013-defining-and-configuring-the-topology) and [Deploying Mediation Servers and Defining Peers](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-mediation-servers-and-defining-peers).</span></span>