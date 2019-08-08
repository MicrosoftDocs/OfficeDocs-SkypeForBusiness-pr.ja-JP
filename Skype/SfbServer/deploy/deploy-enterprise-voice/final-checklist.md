---
title: Skype for Business Server の通話受付制御の展開の最終チェックリスト
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
description: Skype for Business Server Enterprise Voice で通話受付制御 (CAC) を展開するための最終チェックリスト。
ms.openlocfilehash: 275afdfcb3c5e2b7cc635e073bcb5b9ba5edc853
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240318"
---
# <a name="call-admission-control-deployment-final-checklist-for-skype-for-business-server"></a><span data-ttu-id="4e3b9-103">通話受付制御の展開: Skype for Business Server の最終チェックリスト</span><span class="sxs-lookup"><span data-stu-id="4e3b9-103">Call admission control deployment: final checklist for Skype for Business Server</span></span>
 
<span data-ttu-id="4e3b9-104">Skype for Business Server Enterprise Voice で通話受付制御 (CAC) を展開するための最終チェックリスト。</span><span class="sxs-lookup"><span data-stu-id="4e3b9-104">Final checklist for deploying Call Admission Control (CAC) in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="4e3b9-105">次のチェック リストを使用して、通話受付管理サービス (CAC) を展開するために必要なすべての構成タスクを完了したことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="4e3b9-105">Use the following checklist to verify that you have completed all the necessary configuration tasks to deploy Call Admission Control (CAC).</span></span>
  
- <span data-ttu-id="4e3b9-106">1つ以上のエッジサーバーが展開されている場合、各外部インターフェイス IP アドレスは、ネットワーク構成設定のサブネットリストに追加する必要があります。この場合、ビットマスクは32になります。</span><span class="sxs-lookup"><span data-stu-id="4e3b9-106">If one or more Edge Servers are deployed, each external interface IP address must be added to the subnet list in the network configuration settings, with a bit mask of 32.</span></span> <span data-ttu-id="4e3b9-107">音声ビデオ エッジ サービスが展開されている地理的な場所のネットワーク サイト ID にこのサブネット (IP アドレス) を関連付ける必要もあります。</span><span class="sxs-lookup"><span data-stu-id="4e3b9-107">You should also associate this subnet (IP address) with the network site ID for the geographic location where the A/V Edge service is deployed.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4e3b9-108">CAC を実装するためにエッジサーバーは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="4e3b9-108">Edge Servers are not required to implement CAC.</span></span> 
  
- <span data-ttu-id="4e3b9-109">「 [Skype For Business Server で通話受付制御を有効にする](enable-call-admission-control.md)」で指定されているように、CAC が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4e3b9-109">Make sure that CAC is enabled, as specified in [Enable call admission control in Skype for Business Server](enable-call-admission-control.md).</span></span>
    
- <span data-ttu-id="4e3b9-110">すべてのセントラル サイトで CAC が有効化されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4e3b9-110">Make sure that CAC is enabled in all central sites.</span></span> <span data-ttu-id="4e3b9-111">これは、トポロジビルダーで行うことができます。</span><span class="sxs-lookup"><span data-stu-id="4e3b9-111">This can be done through the Topology Builder.</span></span> <span data-ttu-id="4e3b9-112">公開時に警告が生成された場合は、無視しない*で*ください。</span><span class="sxs-lookup"><span data-stu-id="4e3b9-112">If a warning is generated when you publish,  *do not*  ignore it.</span></span>
    
- <span data-ttu-id="4e3b9-113">エンタープライズ ネットワークで管理されているすべてのサブネットがネットワーク構成設定で構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4e3b9-113">Make sure that all the subnets that are managed in the enterprise network are configured in the network configuration settings.</span></span> <span data-ttu-id="4e3b9-114">また、「 [Skype For business でのネットワーク領域、サイト、サブネットの展開](deploy-network.md)」で説明されているように、すべてのサブネットがネットワークサイトに関連付けられていることも重要です。</span><span class="sxs-lookup"><span data-stu-id="4e3b9-114">It is also essential that every subnet be associated to a network site, as explained in [Deploy network regions, sites and subnets in Skype for Business](deploy-network.md).</span></span>
    
- <span data-ttu-id="4e3b9-115">すべてのフロントエンド サーバー、存続可能ブランチ アプライアンス (SBA)、音声ビデオ会議サーバー (別プールの場合)、および仲介サーバーのサブネットまたは IP アドレスがネットワーク構成設定で構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4e3b9-115">Make sure that the subnet or IP addresses of all Front End Servers, Survivable Branch Appliances (SBAs), Audio/Video Conferencing Servers (if in a separate pool), and Mediation Servers are configured in the network configuration settings.</span></span>
    

