---
title: 存続可能ブランチ アプライアンスの PSTN の追加
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddBranchOfficeAppliancePstnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7c55a43d-2589-48f9-972b-1e48a3dca52a
description: ブランチ サイトでのリカバリ性に優れたブランチ アプライアンスの公衆交換電話網 (PSTN) ゲートウェイを定義するには、次のように指定します。
ms.openlocfilehash: cefdc46eb2f5b7573e5e5bd9acb93cb5ab384622
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="add-survivable-branch-appliance-pstn"></a><span data-ttu-id="b187b-103">存続可能ブランチ アプライアンスの PSTN の追加</span><span class="sxs-lookup"><span data-stu-id="b187b-103">Add Survivable Branch Appliance PSTN</span></span>
 
<span data-ttu-id="b187b-104">ブランチ サイトでのリカバリ性に優れたブランチ アプライアンスの公衆交換電話網 (PSTN) ゲートウェイを定義するには、次のように指定します。</span><span class="sxs-lookup"><span data-stu-id="b187b-104">To define the public switched telephone network (PSTN) gateway for a Survivable Branch Appliance at a branch site, specify the following:</span></span> 
  
- <span data-ttu-id="b187b-105">リカバリ性に優れたブランチ アプライアンスまたは存続可能ブランチ サーバーが受信と送信のルーティングのために関連付けられているゲートウェイ ピアの IP アドレス、完全修飾ドメイン名 (FQDN) PSTN を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="b187b-105">A fully qualified domain name (FQDN) or IP address for the gateway peer that the Survivable Branch Appliance or Survivable Branch Server is associated with for routing inbound and outbound PSTN calls.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="b187b-106">リカバリ性に優れたブランチ アプライアンスを定義している場合は、リカバリ性に優れたブランチ アプライアンス内部の仲介サーバーの PSTN への接続の接続先のゲートウェイです。</span><span class="sxs-lookup"><span data-stu-id="b187b-106">If you are defining a Survivable Branch Appliance, this is the gateway to which the Mediation Server inside the Survivable Branch Appliance will connect for PSTN connectivity.</span></span> 
  
- <span data-ttu-id="b187b-p101">セッション開始プロトコル (SIP) メッセージで使用するリッスン ポート。ゲートウェイ、構内交換機 (PBX)、またはセッション境界コントローラー (SBC) の場合、伝送制御プロトコル (TCP) の既定ポートは 5066、トランスポート層セキュリティ (TLS) の既定ポートは 5067 です。ブランチ サイトの存続可能ブランチ アプライアンスの場合、TCP の既定ポートは 5081、TLS の既定ポートは 5082 です。</span><span class="sxs-lookup"><span data-stu-id="b187b-p101">The listening port to be used for Session Initiation Protocol (SIP) messages. By default, the ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS) on a gateway, private branch exchange (PBX), or Session Border Controller (SBC). On a Survivable Branch Appliance at a branch site, the default ports are 5081 for TCP and 5082 for TLS.</span></span>
    
- <span data-ttu-id="b187b-110">セキュリティ上の理由により、TLS を使用することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b187b-110">For security reasons, we strongly recommend that you use TLS.</span></span> <span data-ttu-id="b187b-111">リカバリ性に優れたブランチ アプライアンスを定義する場合は、リカバリ性に優れた、ブランチ アプライアンスが TLS プロトコルをサポートしていることを確認するのには、リカバリ性に優れたブランチ アプライアンスのベンダーのマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b187b-111">If you are defining a Survivable Branch Appliance, refer to your Survivable Branch Appliance vendor documentation to verify that your Survivable Branch Appliance supports the TLS protocol.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="b187b-112">セキュリティ上の理由により、TLS を使用可能なゲートウェイを展開することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b187b-112">For security reasons, we strongly recommended that you deploy a gateway that can use TLS.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="b187b-113">PSTN ゲートウェイを追加する場合は後でセットアップできますが、PSTN ゲートウェイを定義して構成するまでは使用可能な機能が制限されます。</span><span class="sxs-lookup"><span data-stu-id="b187b-113">If you want to add a PSTN gateway, you can set it up later, but full functionality will be limited until the PSTN gateway is defined and configured.</span></span> 
  

