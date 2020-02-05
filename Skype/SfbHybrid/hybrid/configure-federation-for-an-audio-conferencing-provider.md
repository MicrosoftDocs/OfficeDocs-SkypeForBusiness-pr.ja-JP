---
title: ハイブリッド展開で電話会議プロバイダーのフェデレーションを構成する
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: '概要: Skype for Business Online で電話会議プロバイダーのフェデレーションを構成する方法について説明します。'
ms.openlocfilehash: a19704327d1cf5591a1ebb3f62aa23f46fe09d10
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726887"
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-your-hybrid-deployment"></a><span data-ttu-id="7a16d-103">ハイブリッド展開で電話会議プロバイダーのフェデレーションを構成する</span><span class="sxs-lookup"><span data-stu-id="7a16d-103">Configure federation for an audio conferencing provider in your hybrid deployment</span></span>

<span data-ttu-id="7a16d-104">**概要:** Skype for Business Online で電話会議プロバイダーのフェデレーションを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7a16d-104">**Summary:** Learn how to configure federation for an audio conferencing provider in Skype for Business Online.</span></span>

<span data-ttu-id="7a16d-105">ハイブリッド展開 (オンラインでオンプレミス) で電話会議プロバイダー (ACP) を使用する場合は、オンプレミス展開と ACP パートナーとの間のフェデレーションを許可されたパートナーサーバーとして構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a16d-105">If you want to use an Audio Conferencing Provider (ACP) in your hybrid deployment (on-premises with online), you need to configure federation between your on-premises deployment and the ACP partner as an Allowed Partner Server.</span></span> <span data-ttu-id="7a16d-106">フェデレーションを構成するには、オンプレミス展開のために、ACP パートナードメインとエッジサーバー (アクセスプロキシとも呼ばれることもあります) をフェデレーションドメインリストに追加します。</span><span class="sxs-lookup"><span data-stu-id="7a16d-106">You can configure federation by adding the ACP partner domain and Edge server (this may also be called the Access Proxy) to the Federated Domains list for your on-premises deployment.</span></span> <span data-ttu-id="7a16d-107">その後、ACP パートナーは、オンプレミスのエッジサーバープールの FQDN を、許可されたフェデレーションドメインリストに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a16d-107">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span> <span data-ttu-id="7a16d-108">その他の詳細については、ACP プロバイダーに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="7a16d-108">Contact your ACP provider for additional details.</span></span> <span data-ttu-id="7a16d-109">その後、ACP パートナーは、オンプレミスのエッジサーバープールの FQDN を、許可されたフェデレーションドメインリストに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a16d-109">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span>

- <span data-ttu-id="7a16d-110">**許可されたフェデレーションドメインとしての ACP ドメインおよびエッジサーバーの追加**</span><span class="sxs-lookup"><span data-stu-id="7a16d-110">**Adding the ACP Domain and Edge Server as an Allowed Federated Domain**</span></span>

    <span data-ttu-id="7a16d-111">許可されたパートナーサーバー (許可されたフェデレーションドメイン) として ACP ドメインを追加するには、「 [Configure Support For Allowed External Domains](https://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx)」の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="7a16d-111">To add the ACP domain as an Allowed Partner Server (allowed Federated Domain), follow the steps in [Configure Support for Allowed External Domains](https://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx).</span></span> <span data-ttu-id="7a16d-112">エッジサーバーには、ACP パートナーのエッジサーバーの FQDN を追加します。</span><span class="sxs-lookup"><span data-stu-id="7a16d-112">For the Edge Server, add the FQDN of the ACP partner's Edge Server.</span></span> <span data-ttu-id="7a16d-113">エッジサーバーの FQDN を取得するには、ACP パートナーに連絡する必要がある場合があります。これは、アクセスプロキシとして ACP によって参照されることもあります。</span><span class="sxs-lookup"><span data-stu-id="7a16d-113">You may need to contact your ACP partner to obtain the FQDN for their Edge Server, which may also be referred to by your ACP as their Access Proxy.</span></span>

- <span data-ttu-id="7a16d-114">**ACP パートナーへのエッジサーバープールの FQDN の指定**</span><span class="sxs-lookup"><span data-stu-id="7a16d-114">**Providing the FQDN of your Edge Server Pool to the ACP partner**</span></span>

    <span data-ttu-id="7a16d-115">ACP パートナーは、許可されるフェデレーションドメインとしてエッジサーバープールの FQDN を追加することによって、オンプレミスのドメインを許可されたパートナーサーバーとして追加するようにフェデレーションを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a16d-115">The ACP partner needs to configure federation to add your on-premises domain as an Allowed Partner Server by adding the FQDN of your Edge Server pool as an allowed Federated domain.</span></span>


