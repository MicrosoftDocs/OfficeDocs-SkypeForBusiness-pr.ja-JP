---
title: ハイブリッド展開で、オーディオ会議プロバイダーのフェデレーションを構成します。
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/8/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
ms.custom: Strat_SB_Hybrid
ms.assetid: 08dedcce-0d3f-45da-8282-cf2634a41665
description: '概要: ビジネス オンラインの Skype のオーディオ会議プロバイダーのフェデレーションを構成する方法を説明します。'
ms.openlocfilehash: 8ac7e8d365b2a46ac37091510c6909ea996d8ada
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-your-hybrid-deployment"></a><span data-ttu-id="b90da-103">ハイブリッド展開で、オーディオ会議プロバイダーのフェデレーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="b90da-103">Configure federation for an audio conferencing provider in your hybrid deployment</span></span>
 
<span data-ttu-id="b90da-104">**の概要:**ビジネス オンラインの Skype のオーディオ会議プロバイダーのフェデレーションを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b90da-104">**Summary:** Learn how to configure federation for an audio conferencing provider in Skype for Business Online.</span></span>
  
<span data-ttu-id="b90da-105">(オンプレミスをオンラインと共に使う) ハイブリッド展開で電話会議プロバイダー (ACP) を使う場合、オンプレミス展開と許可されるパートナー サーバーとしての ACP パートナーとの間にフェデレーションを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b90da-105">If you want to use an Audio Conferencing Provider (ACP) in your hybrid deployment (on-premises with online), you need to configure federation between your on-premises deployment and the ACP partner as an Allowed Partner Server.</span></span> <span data-ttu-id="b90da-106">フェデレーションは、ACP パートナー ドメインとエッジ サーバー (アクセス プロキシとも呼ばれます) をオンプレミス展開のフェデレーション ドメイン リストに追加すると設定できます。</span><span class="sxs-lookup"><span data-stu-id="b90da-106">You can configure federation by adding the ACP partner domain and Edge server (this may also be called the Access Proxy) to the Federated Domains list for your on-premises deployment.</span></span> <span data-ttu-id="b90da-107">その後、APC パートナーは、オンプレミスのエッジ サーバー プールの FQDN を、許可されるフェデレーション ドメイン リストに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b90da-107">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span> <span data-ttu-id="b90da-108">詳細については、ACP プロバイダーに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="b90da-108">Contact your ACP provider for additional details.</span></span> <span data-ttu-id="b90da-109">その後、APC パートナーは、オンプレミスのエッジ サーバー プールの FQDN を、許可されるフェデレーション ドメイン リストに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b90da-109">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span>
  
- <span data-ttu-id="b90da-110">**許可されるフェデレーション ドメインとしての ACP ドメインおよびエッジ サーバーの追加**</span><span class="sxs-lookup"><span data-stu-id="b90da-110">**Adding the ACP Domain and Edge Server as an Allowed Federated Domain**</span></span>
    
    <span data-ttu-id="b90da-111">許可パートナー サーバー (ドメインのフェデレーションを許可する) として、ACP ドメインを追加するのには[外部ドメインの許可の構成のサポート](http://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx)で、手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b90da-111">To add the ACP domain as an Allowed Partner Server (allowed Federated Domain), follow the steps in [Configure Support for Allowed External Domains](http://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx).</span></span> <span data-ttu-id="b90da-112">エッジ サーバーでは、ACP パートナーのエッジ サーバーの FQDN を追加します。</span><span class="sxs-lookup"><span data-stu-id="b90da-112">For the Edge Server, add the FQDN of the ACP partner's Edge Server.</span></span> <span data-ttu-id="b90da-113">ACP からもアクセス プロキシとして参照される可能性があるエッジ サーバーの FQDN を取得するには ACP パートナーへの問い合わせが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b90da-113">You may need to contact your ACP partner to obtain the FQDN for their Edge Server, which may also be referred to by your ACP as their Access Proxy.</span></span>
    
- <span data-ttu-id="b90da-114">**ACP パートナーへのエッジ サーバー プールの FQDN の指定**</span><span class="sxs-lookup"><span data-stu-id="b90da-114">**Provide the FQDN of your Edge Server Pool to the ACP partner**</span></span>
    
    <span data-ttu-id="b90da-115">ACP パートナーは、フェデレーションを構成してオンプレミスのドメインを許可されるパートナー サーバーとして追加する必要があります。そのためには、エッジ サーバー プールの FQDN を許可されるフェデレーション ドメインとして追加します。</span><span class="sxs-lookup"><span data-stu-id="b90da-115">The ACP partner needs to configure federation to add your on-premises domain as an Allowed Partner Server by adding the FQDN of your Edge Server pool as an allowed Federated domain.</span></span>
    

