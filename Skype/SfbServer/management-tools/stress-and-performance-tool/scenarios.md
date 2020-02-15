---
title: Skype for Business Server 2015 ストレスおよびパフォーマンスツールのパフォーマンスシナリオ
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 12/17/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d972382f-971e-4fa7-b7ee-8ab9d3a5c11d
description: パフォーマンスと負荷テストを実行するために、ストレスおよびパフォーマンスツールを使用して Skype for Business Server 2015 を構成するために必要なタスク。
ms.openlocfilehash: 5531627ab7d5072d32dfcf60fed41eac47f5373f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "41983852"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="1119a-103">Skype for Business Server 2015 ストレスおよびパフォーマンスツールのパフォーマンスシナリオ</span><span class="sxs-lookup"><span data-stu-id="1119a-103">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="1119a-104">パフォーマンスと負荷テストを実行するために、ストレスおよびパフォーマンスツールを使用して Skype for Business Server 2015 を構成するために必要なタスク。</span><span class="sxs-lookup"><span data-stu-id="1119a-104">Tasks you'll need to do to configure Skype for Business Server 2015 to do performance and load-testing, using the Stress and Performance Tool.</span></span>
  
<span data-ttu-id="1119a-105">Skype for business Server 2015 のストレスおよびパフォーマンスツール (LyncPerfTool) を実行するには、Skype for Business Server 2015 トポロジを、ユーザーに関連するシナリオに対して最初に構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1119a-105">To run the Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool), the Skype for Business Server 2015 topology must first be configured for scenarios relevant to you.</span></span> <span data-ttu-id="1119a-106">Skype for Business Server 2015 が構成されていない場合、または正しく構成されていない場合は、負荷シミュレーションが失敗する可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="1119a-106">If Skype for Business Server 2015 isn't configured, or is configured incorrectly, your load simulation is very likely to fail.</span></span> <span data-ttu-id="1119a-107">Skype for business Server 2015 のストレスおよびパフォーマンスツールを使用して、Skype for business Server 管理シェルスクリプトと基本的なリソースファイルを[ツールのダウンロード](https://www.microsoft.com/download/details.aspx?id=50367)の一部として提供しています。</span><span class="sxs-lookup"><span data-stu-id="1119a-107">With the Skype for Business Server 2015 Stress and Performance Tool, we're providing example Skype for Business Server Management Shell scripts and basic resource files as part of the [tool download](https://www.microsoft.com/download/details.aspx?id=50367).</span></span> <span data-ttu-id="1119a-108">これらは、Skype for Business Server の展開を構成するための開始点として使用できます。</span><span class="sxs-lookup"><span data-stu-id="1119a-108">These can be used as a starting point for configuring your Skype for Business Server deployment.</span></span> <span data-ttu-id="1119a-109">この記事では、提供されている Windows PowerShell の例について説明します。</span><span class="sxs-lookup"><span data-stu-id="1119a-109">This article describes the Windows PowerShell examples provided.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1119a-110">このトピックでは、Skype for Business Server 2015 の構成方法を説明するのに役立つ情報はありません。一般的に、そのための計画と展開に関するトピックがあります。</span><span class="sxs-lookup"><span data-stu-id="1119a-110">This topic won't help you describe how to configure Skype for Business Server 2015 generally, we have other Planning and Deployment topics for that.</span></span> <span data-ttu-id="1119a-111">Skype for Business Server 2015 での Windows PowerShell の使用の詳細については、「挿入の概要」の「Skype for Business Server Management Shell」のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1119a-111">For details about working with Windows PowerShell in Skype for Business Server 2015, see the Skype for Business Server Management Shell documentation at Insert introduction HERE.</span></span> 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a><span data-ttu-id="1119a-112">Skype for Business Server 管理シェルスクリプトの実行について</span><span class="sxs-lookup"><span data-stu-id="1119a-112">About running Skype for Business Server management shell scripts</span></span>

<span data-ttu-id="1119a-113">ロードシミュレーションの準備に使用できるサンプル PowerShell スクリプトを提供しています。</span><span class="sxs-lookup"><span data-stu-id="1119a-113">We're providing sample PowerShell scripts you can use to prepare for your load simulations.</span></span> <span data-ttu-id="1119a-114">これらのスクリプトは負荷シミュレーションを目的としているため、シンプルで寛容なものであることがわかります。</span><span class="sxs-lookup"><span data-stu-id="1119a-114">Because these scripts are intended for load simulation, you'll find them to be simple and permissive.</span></span> <span data-ttu-id="1119a-115">これは、運用環境には適していない場合があります。</span><span class="sxs-lookup"><span data-stu-id="1119a-115">That may not be appropriate for your production environment.</span></span> <span data-ttu-id="1119a-116">これらのスクリプトはサンプルなので、これらを確認する必要があり、多くの場合、環境に関連する変更を行ってから、実際に使用できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1119a-116">Again we stress that these scripts are samples, you'll need to review them and in many cases make changes relevant to your environment before being able to make practical use of them.</span></span> <span data-ttu-id="1119a-117">少なくとも、トポロジ (エージェントグループに割り当てられているエージェントを指定する場合) を考慮して、Response Service グループ (RSG) スクリプトを変更する必要があると考えられます。</span><span class="sxs-lookup"><span data-stu-id="1119a-117">At a minimum, we'd expect you'd need to modify the Response Service Group (RSG) script with your topology in mind (to specify the agents assigned to the agent groups).</span></span> <span data-ttu-id="1119a-118">しかし、必要でなければ、それを実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="1119a-118">But you don't have to run that, if you don't need to.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="1119a-119">これらのサンプルを確認し、理解してください。</span><span class="sxs-lookup"><span data-stu-id="1119a-119">Please take care in reviewing and understanding these samples.</span></span> <span data-ttu-id="1119a-120">スクリプトを実行すると、トポロジ内の既存の設定がすべて上書きされます。</span><span class="sxs-lookup"><span data-stu-id="1119a-120">Scripts will overwrite any existing settings in the topology when run.</span></span> 
  
## <a name="stress-and-performance-tool-client-version-names"></a><span data-ttu-id="1119a-121">ストレスおよびパフォーマンスツールクライアントのバージョン名</span><span class="sxs-lookup"><span data-stu-id="1119a-121">Stress and Performance Tool client version names</span></span>

<span data-ttu-id="1119a-122">以前に既定値の設定を変更したことがある場合は、クライアントバージョンチェックポリシーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1119a-122">You might need to configure the Client Version Check policy if you've previously changed the settings from the default values.</span></span> <span data-ttu-id="1119a-123">この点をよく理解していない場合は、[クライアントバージョンチェックのドキュメント](https://msdn.microsoft.com/vsto/jj923060)を確認してください。</span><span class="sxs-lookup"><span data-stu-id="1119a-123">If you're unsure about this, check the [Client Version Check documentation](https://msdn.microsoft.com/vsto/jj923060).</span></span>
  
<span data-ttu-id="1119a-124">ストレスおよびパフォーマンスツールでは、Skype for Business Server 2015 と通信するときに既定で次のユーザーエージェントバージョンが使用されます。</span><span class="sxs-lookup"><span data-stu-id="1119a-124">The Stress and Performance Tool uses the following User Agent versions by default when communicating with Skype for Business Server 2015:</span></span>
  
- <span data-ttu-id="1119a-125">LSPT/15.0.0.0 です (Skype for Business Server 2015 ストレスおよびパフォーマンスツール)</span><span class="sxs-lookup"><span data-stu-id="1119a-125">LSPT/15.0.0.0 (Skype for Business Server 2015 Stress and Performance Tool)</span></span>
    
- <span data-ttu-id="1119a-126">OCPHONE/. 0.522</span><span class="sxs-lookup"><span data-stu-id="1119a-126">OCPHONE/.0.522</span></span>
    
<span data-ttu-id="1119a-127">LyncPerfTool のモビリティ (UCWA) クライアントの場合:</span><span class="sxs-lookup"><span data-stu-id="1119a-127">For the Mobility (UCWA) client in LyncPerfTool:</span></span>
  
- <span data-ttu-id="1119a-128">UCWA Perf ツール/Web 会議</span><span class="sxs-lookup"><span data-stu-id="1119a-128">UCWA Perf Tool/Web Conference</span></span>
    
- <span data-ttu-id="1119a-129">UCWA Perf ツール/モバイル</span><span class="sxs-lookup"><span data-stu-id="1119a-129">UCWA Perf Tool/Mobile</span></span>
    

