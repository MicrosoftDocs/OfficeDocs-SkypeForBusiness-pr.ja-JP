---
title: Skype のビジネス サーバー 2015 の受付制御の展開の最終チェックリストを呼び出す
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
description: ビジネス サーバーのエンタープライズ VoIP の電話受付制御 (CAC) Skype でを展開するための最終的なチェックリストです。
ms.openlocfilehash: beec5c03f47d8f06ec862c3e9a3609fba7b66f2c
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="call-admission-control-deployment-final-checklist-for-skype-for-business-server-2015"></a><span data-ttu-id="d87ed-103">通話受付管理の展開: Skype for Business Server 2015 の最終チェックリスト</span><span class="sxs-lookup"><span data-stu-id="d87ed-103">Call admission control deployment: final checklist for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="d87ed-104">ビジネス サーバーのエンタープライズ VoIP の電話受付制御 (CAC) Skype でを展開するための最終的なチェックリストです。</span><span class="sxs-lookup"><span data-stu-id="d87ed-104">Final checklist for deploying Call Admission Control (CAC) in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="d87ed-105">次のチェック リストを使用して、通話受付管理サービス (CAC) を展開するために必要なすべての構成タスクを完了したことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="d87ed-105">Use the following checklist to verify that you have completed all the necessary configuration tasks to deploy Call Admission Control (CAC).</span></span>
  
- <span data-ttu-id="d87ed-106">1 つまたは複数のエッジ サーバーを展開する場合は、ネットワーク構成の設定で、32 ビット マスクのサブネットの一覧に各外部インターフェイスの IP アドレスを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d87ed-106">If one or more Edge Servers are deployed, each external interface IP address must be added to the subnet list in the network configuration settings, with a bit mask of 32.</span></span> <span data-ttu-id="d87ed-107">音声ビデオ エッジ サービスが展開されている地理的な場所のネットワーク サイト ID にこのサブネット (IP アドレス) を関連付ける必要もあります。</span><span class="sxs-lookup"><span data-stu-id="d87ed-107">You should also associate this subnet (IP address) with the network site ID for the geographic location where the A/V Edge service is deployed.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d87ed-108">エッジ サーバーは CAC を実装する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d87ed-108">Edge Servers are not required to implement CAC.</span></span> 
  
- <span data-ttu-id="d87ed-109">指定された[ビジネス サーバー 2015 の Skype で通話受付制御を有効にする](enable-call-admission-control.md)と、CAC が有効であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d87ed-109">Make sure that CAC is enabled, as specified in [Enable call admission control in Skype for Business Server 2015](enable-call-admission-control.md).</span></span>
    
- <span data-ttu-id="d87ed-110">すべてのセントラル サイトで CAC が有効化されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d87ed-110">Make sure that CAC is enabled in all central sites.</span></span> <span data-ttu-id="d87ed-111">これは、トポロジ ビルダーを実行できます。</span><span class="sxs-lookup"><span data-stu-id="d87ed-111">This can be done through the Topology Builder.</span></span> <span data-ttu-id="d87ed-112">警告が生成されるは、発行するとき場合は、無視*しません*。</span><span class="sxs-lookup"><span data-stu-id="d87ed-112">If a warning is generated when you publish,  *do not*  ignore it.</span></span>
    
- <span data-ttu-id="d87ed-113">エンタープライズ ネットワークで管理されているすべてのサブネットがネットワーク構成設定で構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d87ed-113">Make sure that all the subnets that are managed in the enterprise network are configured in the network configuration settings.</span></span> <span data-ttu-id="d87ed-114">[展開ネットワーク領域、サイト、およびビジネス 2015年の Skype でのサブネット](deploy-network.md)で説明したようにもすべてのサブネットがネットワーク サイトに関連付けられていることが重要です。</span><span class="sxs-lookup"><span data-stu-id="d87ed-114">It is also essential that every subnet be associated to a network site, as explained in [Deploy network regions, sites and subnets in Skype for Business 2015](deploy-network.md).</span></span>
    
- <span data-ttu-id="d87ed-115">すべてのフロントエンド サーバー、存続可能ブランチ アプライアンス (SBA)、音声ビデオ会議サーバー (別プールの場合)、および仲介サーバーのサブネットまたは IP アドレスがネットワーク構成設定で構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d87ed-115">Make sure that the subnet or IP addresses of all Front End Servers, Survivable Branch Appliances (SBAs), Audio/Video Conferencing Servers (if in a separate pool), and Mediation Servers are configured in the network configuration settings.</span></span>
    

