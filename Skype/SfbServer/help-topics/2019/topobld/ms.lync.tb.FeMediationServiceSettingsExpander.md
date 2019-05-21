---
title: 仲介サービス設定エキスパンダー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FeMediationServiceSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 142c1acd-cdaa-4922-8379-aa1bdf56a964
ROBOTS: NOINDEX, NOFOLLOW
description: '[仲介サーバー] では、次の情報を指定できます。'
ms.openlocfilehash: 701fe25213211e044a33cd91893a3509df6148a4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34292746"
---
# <a name="mediation-service-settings-expander"></a><span data-ttu-id="7fc7e-103">仲介サービス設定エキスパンダー</span><span class="sxs-lookup"><span data-stu-id="7fc7e-103">Mediation Service Settings Expander</span></span>

<span data-ttu-id="7fc7e-104">[**仲介サーバー**] では、次の情報を指定できます。</span><span class="sxs-lookup"><span data-stu-id="7fc7e-104">For **Mediation Server**, you can specify the following:</span></span>

<span data-ttu-id="7fc7e-105">仲介サーバーをフロントエンドプールまたは Standard Edition サーバーに配置している場合は、[併置された**仲介サーバーを有効に**する] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="7fc7e-105">If you are collocating the Mediation Server onto the Front End pool or the Standard Edition server, select the check box **Collocated Mediation Server enabled**.</span></span> <span data-ttu-id="7fc7e-106">仲介サーバーを検索しないことにした場合、このセクションには定義されている設定はありません。</span><span class="sxs-lookup"><span data-stu-id="7fc7e-106">If you choose not to collocate the Mediation Server, there are no definable settings in this section.</span></span>

<span data-ttu-id="7fc7e-107">仲介サーバーの collocation を有効にしている場合、トランスポート層セキュリティ (TLS) 用にサーバー上のリッスンポートの範囲を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7fc7e-107">If you have enabled the collocation of the Mediation Server, you need to define the listening port range on the server for Transport Layer Security (TLS).</span></span> <span data-ttu-id="7fc7e-108">既定では、このポートは5067です。</span><span class="sxs-lookup"><span data-stu-id="7fc7e-108">By default, this port is 5067.</span></span> <span data-ttu-id="7fc7e-109">[ **Tcp ポートを有効に**する] を選択した場合、併置された仲介サーバーに対して伝送制御プロトコル (TCP) ポートを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7fc7e-109">If you select **Enable TCP port**, you must define a Transmission Control Protocol (TCP) port for the collocated Mediation Server.</span></span> <span data-ttu-id="7fc7e-110">これはオプションの設定であり、必要に応じてゲートウェイまたは公衆交換電話網 (PSTN) の要件を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7fc7e-110">This is an optional setting, and you should refer to the requirements of your gateway or public switched telephone network (PSTN) requirements to determine if you need this.</span></span> <span data-ttu-id="7fc7e-111">既定では、[TCP ポート] の値は5068です。</span><span class="sxs-lookup"><span data-stu-id="7fc7e-111">By default, the TCP port value is 5068.</span></span>

<span data-ttu-id="7fc7e-112">併置された仲介サーバーに関連付けられている PSTN ゲートウェイを定義します。</span><span class="sxs-lookup"><span data-stu-id="7fc7e-112">You define PSTN gateways that are associated with the collocated Mediation Server.</span></span> <span data-ttu-id="7fc7e-113">既にゲートウェイが定義されている場合は、それらを仲介サーバーと関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="7fc7e-113">If you have already defined gateways, they will be available to associate with the Mediation Server.</span></span>

<span data-ttu-id="7fc7e-114">仲介サーバーと関連付けられているゲートウェイが複数ある場合は、最初に関連付けられたゲートウェイが既定のゲートウェイになります。</span><span class="sxs-lookup"><span data-stu-id="7fc7e-114">If you have more than one gateway associated with a Mediation Server, the first gateway associated will be the default gateway.</span></span> <span data-ttu-id="7fc7e-115">既定のゲートウェイとして別のゲートウェイを選択する必要がある場合は、既定にするゲートウェイを選択して、[**既定にする**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7fc7e-115">If you need to choose another gateway as the default gateway, select the gateway that you want to make the default, and click **Make Default**.</span></span> <span data-ttu-id="7fc7e-116">既定のゲートウェイとしての選択を解除するには、[**既定値の解除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7fc7e-116">To unselect the gateway as the default, click **Unmake Default**.</span></span>

<span data-ttu-id="7fc7e-117">Enterprise Edition フロントエンドプールまたは Standard Edition サーバーの設定と構成の詳細については、「[トポロジの定義と構成](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx)」および「[仲介サーバーの展開とピアの定義](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7fc7e-117">For details about defining and configuring the settings for the Enterprise Edition Front End pool or Standard Edition server, see [Defining and Configuring the Topology](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) and [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).</span></span>


