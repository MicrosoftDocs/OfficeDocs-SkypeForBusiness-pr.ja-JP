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
ms.openlocfilehash: 5d9c49299452f579cd7c58adf54facb09f0b8a21
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118976"
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-your-hybrid-deployment"></a><span data-ttu-id="aeb1c-103">ハイブリッド展開で電話会議プロバイダーのフェデレーションを構成する</span><span class="sxs-lookup"><span data-stu-id="aeb1c-103">Configure federation for an audio conferencing provider in your hybrid deployment</span></span>

<span data-ttu-id="aeb1c-104">**概要:** Skype for Business Online で電話会議プロバイダーのフェデレーションを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="aeb1c-104">**Summary:** Learn how to configure federation for an audio conferencing provider in Skype for Business Online.</span></span>

<span data-ttu-id="aeb1c-105">ハイブリッド展開 (オンプレミスとオンライン) で電話会議プロバイダー (ACP) を使用する場合は、オンプレミス展開と ACP パートナー間のフェデレーションを許可パートナー サーバーとして構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aeb1c-105">If you want to use an Audio Conferencing Provider (ACP) in your hybrid deployment (on-premises with online), you need to configure federation between your on-premises deployment and the ACP partner as an Allowed Partner Server.</span></span> <span data-ttu-id="aeb1c-106">フェデレーションを構成するには、ACP パートナー ドメインとエッジ サーバー (アクセス プロキシとも呼ばれる場合があります) をオンプレミス展開のフェデレーション ドメイン リストに追加します。</span><span class="sxs-lookup"><span data-stu-id="aeb1c-106">You can configure federation by adding the ACP partner domain and Edge server (this may also be called the Access Proxy) to the Federated Domains list for your on-premises deployment.</span></span> <span data-ttu-id="aeb1c-107">その後、ACP パートナーは、オンプレミスエッジ サーバー プールの FQDN を許可されたフェデレーション ドメイン リストに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aeb1c-107">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span> <span data-ttu-id="aeb1c-108">詳細については、ACP プロバイダーにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="aeb1c-108">Contact your ACP provider for additional details.</span></span> <span data-ttu-id="aeb1c-109">その後、ACP パートナーは、オンプレミスエッジ サーバー プールの FQDN を許可されたフェデレーション ドメイン リストに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aeb1c-109">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span>

- <span data-ttu-id="aeb1c-110">**ACP ドメインとエッジ サーバーを許可されたフェデレーション ドメインとして追加する**</span><span class="sxs-lookup"><span data-stu-id="aeb1c-110">**Adding the ACP Domain and Edge Server as an Allowed Federated Domain**</span></span>

    <span data-ttu-id="aeb1c-111">ACP ドメインを許可パートナー サーバー (許可されたフェデレーション ドメイン) として追加するには、「許可された外部ドメインのサポートを構成する」 [の手順に従います](/previous-versions/office/lync-server-2013/lync-server-2013-configure-support-for-allowed-external-domains)。</span><span class="sxs-lookup"><span data-stu-id="aeb1c-111">To add the ACP domain as an Allowed Partner Server (allowed Federated Domain), follow the steps in [Configure Support for Allowed External Domains](/previous-versions/office/lync-server-2013/lync-server-2013-configure-support-for-allowed-external-domains).</span></span> <span data-ttu-id="aeb1c-112">エッジ サーバーの場合は、ACP パートナーのエッジ サーバーの FQDN を追加します。</span><span class="sxs-lookup"><span data-stu-id="aeb1c-112">For the Edge Server, add the FQDN of the ACP partner's Edge Server.</span></span> <span data-ttu-id="aeb1c-113">エッジ サーバーの FQDN を取得するには、ACP パートナーに問い合わせが必要な場合があります。これは、ACP がアクセス プロキシと呼ばれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="aeb1c-113">You may need to contact your ACP partner to obtain the FQDN for their Edge Server, which may also be referred to by your ACP as their Access Proxy.</span></span>

- <span data-ttu-id="aeb1c-114">**エッジ サーバー プールの FQDN を ACP パートナーに提供する**</span><span class="sxs-lookup"><span data-stu-id="aeb1c-114">**Providing the FQDN of your Edge Server Pool to the ACP partner**</span></span>

    <span data-ttu-id="aeb1c-115">ACP パートナーは、許可されたフェデレーション ドメインとしてエッジ サーバー プールの FQDN を追加して、オンプレミス ドメインを許可パートナー サーバーとして追加するフェデレーションを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aeb1c-115">The ACP partner needs to configure federation to add your on-premises domain as an Allowed Partner Server by adding the FQDN of your Edge Server pool as an allowed Federated domain.</span></span>