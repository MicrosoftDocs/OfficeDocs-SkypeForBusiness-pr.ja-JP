---
title: 仲介サービス設定エキスパンダー
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FeMediationServiceSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 142c1acd-cdaa-4922-8379-aa1bdf56a964
ROBOTS: NOINDEX, NOFOLLOW
description: '[仲介サーバー] では、次の情報を指定できます。'
ms.openlocfilehash: 7a42bca81f823fd22d933dd8460cf644605d7908
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2018
ms.locfileid: "23261155"
---
# <a name="mediation-service-settings-expander"></a><span data-ttu-id="7e45c-103">仲介サービス設定エキスパンダー</span><span class="sxs-lookup"><span data-stu-id="7e45c-103">Mediation Service Settings Expander</span></span>

<span data-ttu-id="7e45c-104">[**仲介サーバー**] では、次の情報を指定できます。</span><span class="sxs-lookup"><span data-stu-id="7e45c-104">For **Mediation Server**, you can specify the following:</span></span>

<span data-ttu-id="7e45c-105">仲介サーバーをフロント エンド プールまたは Standard Edition サーバーを配置するが場合、は、**仲介サーバーを 1 か所に配置を有効に**するチェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="7e45c-105">If you are collocating the Mediation Server onto the Front End pool or the Standard Edition server, select the check box **Collocated Mediation Server enabled**.</span></span> <span data-ttu-id="7e45c-106">仲介サーバーを連結する場合は、このセクションで定義できる設定はありません。</span><span class="sxs-lookup"><span data-stu-id="7e45c-106">If you choose not to collocate the Mediation Server, there are no definable settings in this section.</span></span>

<span data-ttu-id="7e45c-107">仲介サーバーのコロケーションを有効にした場合は、トランスポート層セキュリティ (TLS) のサーバー上でリッスンしているポートの範囲を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e45c-107">If you have enabled the collocation of the Mediation Server, you need to define the listening port range on the server for Transport Layer Security (TLS).</span></span> <span data-ttu-id="7e45c-108">既定では、このポートは 5067 です。</span><span class="sxs-lookup"><span data-stu-id="7e45c-108">By default, this port is 5067.</span></span> <span data-ttu-id="7e45c-109">**有効にする TCP ポート**を選択する場合は、配置されている仲介サーバーの伝送制御プロトコル (TCP) ポートを定義してください。</span><span class="sxs-lookup"><span data-stu-id="7e45c-109">If you select **Enable TCP port**, you must define a Transmission Control Protocol (TCP) port for the collocated Mediation Server.</span></span> <span data-ttu-id="7e45c-110">これは、オプションの設定、およびゲートウェイの要件や、これが必要なかどうかを決定するのには公衆交換電話網 (PSTN) の要件を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e45c-110">This is an optional setting, and you should refer to the requirements of your gateway or public switched telephone network (PSTN) requirements to determine if you need this.</span></span> <span data-ttu-id="7e45c-111">既定では、TCP ポートの値は 5068 がします。</span><span class="sxs-lookup"><span data-stu-id="7e45c-111">By default, the TCP port value is 5068.</span></span>

<span data-ttu-id="7e45c-112">配置されている仲介サーバーに関連付けられている PSTN ゲートウェイを定義します。</span><span class="sxs-lookup"><span data-stu-id="7e45c-112">You define PSTN gateways that are associated with the collocated Mediation Server.</span></span> <span data-ttu-id="7e45c-113">ゲートウェイが定義されている場合は、仲介サーバーに関連付けるに使用されます。</span><span class="sxs-lookup"><span data-stu-id="7e45c-113">If you have already defined gateways, they will be available to associate with the Mediation Server.</span></span>

<span data-ttu-id="7e45c-114">仲介サーバーに関連付けられている 1 つ以上のゲートウェイがある場合は、関連付けられている最初のゲートウェイがデフォルト ゲートウェイになります。</span><span class="sxs-lookup"><span data-stu-id="7e45c-114">If you have more than one gateway associated with a Mediation Server, the first gateway associated will be the default gateway.</span></span> <span data-ttu-id="7e45c-115">既定のゲートウェイとして別のゲートウェイを選択する必要がある場合は、既定にするゲートウェイを選択して、[**既定にする**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e45c-115">If you need to choose another gateway as the default gateway, select the gateway that you want to make the default, and click **Make Default**.</span></span> <span data-ttu-id="7e45c-116">既定のゲートウェイとしての選択を解除するには、[**既定値の解除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e45c-116">To unselect the gateway as the default, click **Unmake Default**.</span></span>

<span data-ttu-id="7e45c-117">詳細を定義して、エンタープライズ エディションのフロント エンド プールまたは Standard Edition サーバーの設定の構成について[を定義してトポロジの構成](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx)、および[仲介サーバーの展開、および同等の定義](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e45c-117">For details about defining and configuring the settings for the Enterprise Edition Front End pool or Standard Edition server, see [Defining and Configuring the Topology](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) and [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).</span></span>


