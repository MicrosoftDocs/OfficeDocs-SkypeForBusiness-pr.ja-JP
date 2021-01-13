---
title: 存続可能ブランチ アプライアンスの PSTN を追加する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddBranchOfficeAppliancePstnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7c55a43d-2589-48f9-972b-1e48a3dca52a
ROBOTS: NOINDEX, NOFOLLOW
description: ブランチ サイトでの存続可能ブランチ アプライアンスの公衆交換電話網 (PSTN) ゲートウェイを定義するには、次の情報を指定します。
ms.openlocfilehash: 30b5922e3d18b4dfe57bef23ddb0f00a25df7f9f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49811947"
---
# <a name="add-survivable-branch-appliance-pstn"></a><span data-ttu-id="ae57f-103">存続可能ブランチ アプライアンスの PSTN の追加</span><span class="sxs-lookup"><span data-stu-id="ae57f-103">Add Survivable Branch Appliance PSTN</span></span>
 
<span data-ttu-id="ae57f-104">ブランチ サイトでの存続可能ブランチ アプライアンスの公衆交換電話網 (PSTN) ゲートウェイを定義するには、次の情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="ae57f-104">To define the public switched telephone network (PSTN) gateway for a Survivable Branch Appliance at a branch site, specify the following:</span></span> 
  
- <span data-ttu-id="ae57f-105">着信と発信の PSTN 通話のルーティングで、存続可能ブランチ アプライアンスまたは存続可能ブランチ サーバーが関連付けられているゲートウェイ ピアの完全修飾ドメイン名 (FQDN) または IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="ae57f-105">A fully qualified domain name (FQDN) or IP address for the gateway peer that the Survivable Branch Appliance or Survivable Branch Server is associated with for routing inbound and outbound PSTN calls.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="ae57f-106">存続可能ブランチ アプライアンスを定義すると、このアプライアンスは、PSTN 接続で存続可能ブランチ アプライアンス内部の仲介サーバーが接続するゲートウェイとなります。</span><span class="sxs-lookup"><span data-stu-id="ae57f-106">If you are defining a Survivable Branch Appliance, this is the gateway to which the Mediation Server inside the Survivable Branch Appliance will connect for PSTN connectivity.</span></span> 
  
- <span data-ttu-id="ae57f-p101">セッション開始プロトコル (SIP) メッセージで使用するリッスン ポート。ゲートウェイ、構内交換機 (PBX)、またはセッション境界コントローラー (SBC) の場合、伝送制御プロトコル (TCP) の既定ポートは 5066、トランスポート層セキュリティ (TLS) の既定ポートは 5067 です。ブランチ サイトの存続可能ブランチ アプライアンスの場合、TCP の既定ポートは 5081、TLS の既定ポートは 5082 です。</span><span class="sxs-lookup"><span data-stu-id="ae57f-p101">The listening port to be used for Session Initiation Protocol (SIP) messages. By default, the ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS) on a gateway, private branch exchange (PBX), or Session Border Controller (SBC). On a Survivable Branch Appliance at a branch site, the default ports are 5081 for TCP and 5082 for TLS.</span></span>
    
- <span data-ttu-id="ae57f-p102">セキュリティ上の理由により、TLS を使用することを強くお勧めします。存続可能ブランチ アプライアンスを定義する場合は、存続可能ブランチ アプライアンスのベンダー ドキュメントを参照して、その存続可能ブランチ アプライアンスが TLS プロトコルをサポートすることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="ae57f-p102">For security reasons, we strongly recommend that you use TLS. If you are defining a Survivable Branch Appliance, refer to your Survivable Branch Appliance vendor documentation to verify that your Survivable Branch Appliance supports the TLS protocol.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="ae57f-112">セキュリティ上の理由により、TLS を使用可能なゲートウェイを展開することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ae57f-112">For security reasons, we strongly recommended that you deploy a gateway that can use TLS.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="ae57f-113">PSTN ゲートウェイを追加する場合は後でセットアップできますが、PSTN ゲートウェイを定義して構成するまでは使用可能な機能が制限されます。</span><span class="sxs-lookup"><span data-stu-id="ae57f-113">If you want to add a PSTN gateway, you can set it up later, but full functionality will be limited until the PSTN gateway is defined and configured.</span></span> 
  

