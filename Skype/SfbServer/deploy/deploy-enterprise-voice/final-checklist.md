---
title: Skype for Business Server の通話受付管理展開の最終チェックリスト
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
description: Skype for Business Server サービスに通話受付管理 (CAC) を展開するための最終チェックリストエンタープライズ VoIP。
ms.openlocfilehash: d3a6484e35225627c8f22002823eff7fd5939694
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830837"
---
# <a name="call-admission-control-deployment-final-checklist-for-skype-for-business-server"></a><span data-ttu-id="5e1b1-103">通話受付管理の展開: Skype for Business Server の最終チェックリスト</span><span class="sxs-lookup"><span data-stu-id="5e1b1-103">Call admission control deployment: final checklist for Skype for Business Server</span></span>
 
<span data-ttu-id="5e1b1-104">Skype for Business Server サービスに通話受付管理 (CAC) を展開するための最終チェックリストエンタープライズ VoIP。</span><span class="sxs-lookup"><span data-stu-id="5e1b1-104">Final checklist for deploying Call Admission Control (CAC) in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="5e1b1-105">次のチェックリストを使用して、通話受付管理 (CAC) を展開するために必要なすべての構成タスクが完了したのを確認します。</span><span class="sxs-lookup"><span data-stu-id="5e1b1-105">Use the following checklist to verify that you have completed all the necessary configuration tasks to deploy Call Admission Control (CAC).</span></span>
  
- <span data-ttu-id="5e1b1-p101">1 つまたは複数のエッジ サーバーが展開されている場合には、32 ビット マスクのすべての外部インターフェイス IP アドレスがネットワーク構成設定のサブネット リストに追加されている必要があります。音声ビデオ エッジ サービスが展開されている地理的な場所のネットワーク サイト ID にこのサブネット (IP アドレス) を関連付ける必要もあります。</span><span class="sxs-lookup"><span data-stu-id="5e1b1-p101">If one or more Edge Servers are deployed, each external interface IP address must be added to the subnet list in the network configuration settings, with a bit mask of 32. You should also associate this subnet (IP address) with the network site ID for the geographic location where the A/V Edge service is deployed.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5e1b1-108">CAC を実装するためにエッジ サーバーは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="5e1b1-108">Edge Servers are not required to implement CAC.</span></span> 
  
- <span data-ttu-id="5e1b1-109">「Skype for Business Server で通話受付管理を有効にする」で指定されている CAC [が有効になっている必要があります](enable-call-admission-control.md)。</span><span class="sxs-lookup"><span data-stu-id="5e1b1-109">Make sure that CAC is enabled, as specified in [Enable call admission control in Skype for Business Server](enable-call-admission-control.md).</span></span>
    
- <span data-ttu-id="5e1b1-110">すべてのセントラル サイトで CAC が有効化されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5e1b1-110">Make sure that CAC is enabled in all central sites.</span></span> <span data-ttu-id="5e1b1-111">これは、トポロジ ビルダーを使用して行います。</span><span class="sxs-lookup"><span data-stu-id="5e1b1-111">This can be done through the Topology Builder.</span></span> <span data-ttu-id="5e1b1-112">発行時に警告が生成された場合は  *、無視*  しない。</span><span class="sxs-lookup"><span data-stu-id="5e1b1-112">If a warning is generated when you publish,  *do not*  ignore it.</span></span>
    
- <span data-ttu-id="5e1b1-113">エンタープライズ ネットワークで管理されているすべてのサブネットがネットワーク構成設定で構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5e1b1-113">Make sure that all the subnets that are managed in the enterprise network are configured in the network configuration settings.</span></span> <span data-ttu-id="5e1b1-114">また [、「Skype for Business](deploy-network.md)でのネットワーク地域、サイト、サブネットの展開」で説明したように、すべてのサブネットをネットワーク サイトに関連付けることです。</span><span class="sxs-lookup"><span data-stu-id="5e1b1-114">It is also essential that every subnet be associated to a network site, as explained in [Deploy network regions, sites and subnets in Skype for Business](deploy-network.md).</span></span>
    
- <span data-ttu-id="5e1b1-115">すべてのフロントエンド サーバー、存続可能ブランチ アプライアンス (SBA)、音声ビデオ会議サーバー (別プールの場合)、および仲介サーバーのサブネットまたは IP アドレスがネットワーク構成設定で構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5e1b1-115">Make sure that the subnet or IP addresses of all Front End Servers, Survivable Branch Appliances (SBAs), Audio/Video Conferencing Servers (if in a separate pool), and Mediation Servers are configured in the network configuration settings.</span></span>
    

