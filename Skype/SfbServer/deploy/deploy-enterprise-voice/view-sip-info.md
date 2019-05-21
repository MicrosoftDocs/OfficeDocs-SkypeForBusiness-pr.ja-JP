---
title: Skype for Business Server の各 SIP trunks に関する情報を表示する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
description: '概要: Skype for Business Server の SIP trunks に関する情報を表示する方法について説明します。'
ms.openlocfilehash: a8cb5559b1431987adeef7c50b7810b7e9b4adc7
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34300917"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a><span data-ttu-id="61c87-103">Skype for Business Server の各 SIP trunks に関する情報を表示する</span><span class="sxs-lookup"><span data-stu-id="61c87-103">View information about individual SIP trunks in Skype for Business Server</span></span>
 
<span data-ttu-id="61c87-104">**概要:** Skype for Business Server の SIP trunks に関する情報を表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="61c87-104">**Summary:** Learn how to view information about SIP trunks in Skype for Business Server.</span></span>
  
<span data-ttu-id="61c87-105">SIP trunks は、Skype for Business Server のボイスオーバー IP 電話ネットワークと公衆交換電話網 (PSTN) を接続するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="61c87-105">SIP trunks are used to connect Skype for Business Server Voice over IP phone network with the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="61c87-106">以前のバージョンの製品では、トランクを使用して仲介サーバーから PSTN ゲートウェイに発信通話がルーティングされ、各ゲートウェイは 1 つのトランクに制限されていました。</span><span class="sxs-lookup"><span data-stu-id="61c87-106">In previous version of the product, trunks were used to route outbound calls from a Mediation Server to a PSTN gateway and each gateway was limited to a single trunk.</span></span> <span data-ttu-id="61c87-107">その結果、PSTN ゲートウェイと SIP トランクは実質的に同一でした。</span><span class="sxs-lookup"><span data-stu-id="61c87-107">As a result, a PSTN gateway and a SIP trunk were essentially identical.</span></span> <span data-ttu-id="61c87-108">管理者にとって、このことは、関連付けられている PSTN ゲートウェイに関する情報を表示するだけで個々の SIP トランクに関する情報を表示できることを意味していました。</span><span class="sxs-lookup"><span data-stu-id="61c87-108">For administrators, that meant they could view information about an individual SIP trunk simply by viewing information about the associated PSTN gateway.</span></span>
  
<span data-ttu-id="61c87-109">ただし、Skype for Business Server では、複数の trunks を単一の PSTN ゲートウェイに割り当てることができるようになりました。これは、ゲートウェイと trunks が1つではなく、同じであることを意味します。</span><span class="sxs-lookup"><span data-stu-id="61c87-109">In Skype for Business Server, however, multiple trunks can now be assigned to a single PSTN gateway; this means that gateways and trunks are no longer one and the same.</span></span> <span data-ttu-id="61c87-110">つまり、個々の SIP トランクに関する情報を表示するために、管理者は新しい[Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/get-cstrunk?view=skype-ps)コマンドレットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="61c87-110">In turn, that means that administrators must use the new [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/get-cstrunk?view=skype-ps) cmdlet in order to view information about an individual SIP trunk.</span></span>
  
### <a name="to-view-information-for-all-your-sip-trunks"></a><span data-ttu-id="61c87-111">すべての SIP トランクに関する情報の表示</span><span class="sxs-lookup"><span data-stu-id="61c87-111">To view information for all your SIP trunks</span></span>

- <span data-ttu-id="61c87-112">次のコマンドは、組織で使用中のすべての SIP トランクに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="61c87-112">The following command returns information about all the SIP trunks in use in your organization:</span></span>
    
  ```
  Get-CsTrunk
  ```

### <a name="to-view-information-for-a-specific-sip-trunk"></a><span data-ttu-id="61c87-113">特定の SIP トランクに関する情報の表示</span><span class="sxs-lookup"><span data-stu-id="61c87-113">To view information for a specific SIP trunk</span></span>

- <span data-ttu-id="61c87-114">このコマンドは、PstnGateway:192.168.0.240 という Identity を持つ SIP トランクに関する情報のみを返します。</span><span class="sxs-lookup"><span data-stu-id="61c87-114">This command returns information only for the SIP trunk with the Identity PstnGateway:192.168.0.240:</span></span>
    
  ```
  Get-CsTrunk -Identity "PstnGateway:192.168.0.240"
  ```

### <a name="view-information-for-all-the-sip-trunks-assigned-to-a-pool"></a><span data-ttu-id="61c87-115">プールに割り当てられているすべての SIP トランクに関する情報を表示する</span><span class="sxs-lookup"><span data-stu-id="61c87-115">View information for all the SIP trunks assigned to a pool</span></span>

- <span data-ttu-id="61c87-116">この例では、プール atl-cs-001.litwareinc.com に割り当てられているすべての SIP トランクについて情報が返されます。</span><span class="sxs-lookup"><span data-stu-id="61c87-116">In this example, information is returned for all the SIP trunks assigned to the pool atl-cs-001.litwareinc.com:</span></span>
    
  ```
  Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"
  ```
