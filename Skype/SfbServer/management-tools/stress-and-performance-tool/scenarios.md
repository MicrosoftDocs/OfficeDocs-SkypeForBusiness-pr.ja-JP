---
title: Skype for Business Server 2015 ストレス/パフォーマンスツールのパフォーマンスシナリオ
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
description: パフォーマンスと負荷のテストを実行するために Skype for Business Server 2015 を構成するために必要なタスクを、ストレスとパフォーマンスのツールを使って実行する必要があります。
ms.openlocfilehash: 343378d0b0d763d8a290e8d1e930a64c5d114bdb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803877"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="3cfaf-103">Skype for Business Server 2015 ストレス/パフォーマンスツールのパフォーマンスシナリオ</span><span class="sxs-lookup"><span data-stu-id="3cfaf-103">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="3cfaf-104">パフォーマンスと負荷のテストを実行するために Skype for Business Server 2015 を構成するために必要なタスクを、ストレスとパフォーマンスのツールを使って実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3cfaf-104">Tasks you'll need to do to configure Skype for Business Server 2015 to do performance and load-testing, using the Stress and Performance Tool.</span></span>
  
<span data-ttu-id="3cfaf-105">Skype for Business Server 2015 応力とパフォーマンスツール (LyncPerfTool) を実行するには、まず、Skype for Business Server 2015 トポロジを、関連するシナリオに合わせて構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3cfaf-105">To run the Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool), the Skype for Business Server 2015 topology must first be configured for scenarios relevant to you.</span></span> <span data-ttu-id="3cfaf-106">Skype for Business Server 2015 が構成されていない場合、または正しく構成されていない場合は、ロードシミュレーションが失敗する可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="3cfaf-106">If Skype for Business Server 2015 isn't configured, or is configured incorrectly, your load simulation is very likely to fail.</span></span> <span data-ttu-id="3cfaf-107">Skype for Business Server 2015 のストレスとパフォーマンスのツールを使用して、Skype for Business Server 管理シェルスクリプトと基本的なリソースファイルをツールの[ダウンロード](https://www.microsoft.com/download/details.aspx?id=50367)の一部として提供しています。</span><span class="sxs-lookup"><span data-stu-id="3cfaf-107">With the Skype for Business Server 2015 Stress and Performance Tool, we're providing example Skype for Business Server Management Shell scripts and basic resource files as part of the [tool download](https://www.microsoft.com/download/details.aspx?id=50367).</span></span> <span data-ttu-id="3cfaf-108">これらは、Skype for Business Server の展開を構成するための出発点として使用できます。</span><span class="sxs-lookup"><span data-stu-id="3cfaf-108">These can be used as a starting point for configuring your Skype for Business Server deployment.</span></span> <span data-ttu-id="3cfaf-109">この記事では、提供されている Windows PowerShell の例について説明します。</span><span class="sxs-lookup"><span data-stu-id="3cfaf-109">This article describes the Windows PowerShell examples provided.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3cfaf-110">このトピックでは、Skype for Business Server 2015 を構成する方法について説明していません。一般的に、その他の計画と展開のトピックがあります。</span><span class="sxs-lookup"><span data-stu-id="3cfaf-110">This topic won't help you describe how to configure Skype for Business Server 2015 generally, we have other Planning and Deployment topics for that.</span></span> <span data-ttu-id="3cfaf-111">Skype for Business Server 2015 での Windows PowerShell の使用について詳しくは、「ここで概要を挿入する」の「Skype for Business Server 管理シェルのドキュメント」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3cfaf-111">For details about working with Windows PowerShell in Skype for Business Server 2015, see the Skype for Business Server Management Shell documentation at Insert introduction HERE.</span></span> 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a><span data-ttu-id="3cfaf-112">Skype for Business Server 管理シェルスクリプトの実行について</span><span class="sxs-lookup"><span data-stu-id="3cfaf-112">About running Skype for Business Server management shell scripts</span></span>

<span data-ttu-id="3cfaf-113">ロードシミュレーションの準備に使用できる PowerShell スクリプトのサンプルを提供しています。</span><span class="sxs-lookup"><span data-stu-id="3cfaf-113">We're providing sample PowerShell scripts you can use to prepare for your load simulations.</span></span> <span data-ttu-id="3cfaf-114">これらのスクリプトは、読み込みシミュレーション用のものであるため、単純で寛容なものにすることができます。</span><span class="sxs-lookup"><span data-stu-id="3cfaf-114">Because these scripts are intended for load simulation, you'll find them to be simple and permissive.</span></span> <span data-ttu-id="3cfaf-115">これは、実稼働環境に適していない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3cfaf-115">That may not be appropriate for your production environment.</span></span> <span data-ttu-id="3cfaf-116">ここでも、これらのスクリプトはサンプルであり、多くの場合、それらを確認する必要があります。また、多くの場合、環境に関連する変更を行ってから実際に使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="3cfaf-116">Again we stress that these scripts are samples, you'll need to review them and in many cases make changes relevant to your environment before being able to make practical use of them.</span></span> <span data-ttu-id="3cfaf-117">少なくとも、トポロジを念頭に置いて応答サービスグループ (RSG) スクリプトを変更する必要があることを前提としています (エージェントグループに割り当てられているエージェントを指定するため)。</span><span class="sxs-lookup"><span data-stu-id="3cfaf-117">At a minimum, we'd expect you'd need to modify the Response Service Group (RSG) script with your topology in mind (to specify the agents assigned to the agent groups).</span></span> <span data-ttu-id="3cfaf-118">ただし、必要でない場合は、これを実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="3cfaf-118">But you don't have to run that, if you don't need to.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="3cfaf-119">これらのサンプルを確認して理解してください。</span><span class="sxs-lookup"><span data-stu-id="3cfaf-119">Please take care in reviewing and understanding these samples.</span></span> <span data-ttu-id="3cfaf-120">スクリプトは、実行時にトポロジの既存の設定を上書きします。</span><span class="sxs-lookup"><span data-stu-id="3cfaf-120">Scripts will overwrite any existing settings in the topology when run.</span></span> 
  
## <a name="stress-and-performance-tool-client-version-names"></a><span data-ttu-id="3cfaf-121">ストレスとパフォーマンスのツールクライアントのバージョン名</span><span class="sxs-lookup"><span data-stu-id="3cfaf-121">Stress and Performance Tool client version names</span></span>

<span data-ttu-id="3cfaf-122">以前に設定を既定値から変更した場合は、クライアントのバージョンチェックポリシーの構成が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="3cfaf-122">You might need to configure the Client Version Check policy if you've previously changed the settings from the default values.</span></span> <span data-ttu-id="3cfaf-123">この点について不明な点がある場合は、[クライアントのバージョンチェックのドキュメント](https://msdn.microsoft.com/en-us/vsto/jj923060)を確認してください。</span><span class="sxs-lookup"><span data-stu-id="3cfaf-123">If you're unsure about this, check the [Client Version Check documentation](https://msdn.microsoft.com/en-us/vsto/jj923060).</span></span>
  
<span data-ttu-id="3cfaf-124">ストレスとパフォーマンスのツールでは、Skype for Business Server 2015 と通信するときに、既定で次のユーザーエージェントバージョンが使用されます。</span><span class="sxs-lookup"><span data-stu-id="3cfaf-124">The Stress and Performance Tool uses the following User Agent versions by default when communicating with Skype for Business Server 2015:</span></span>
  
- <span data-ttu-id="3cfaf-125">LSPT/15.0.0.0 (Skype for Business Server 2015 応力とパフォーマンスツール)</span><span class="sxs-lookup"><span data-stu-id="3cfaf-125">LSPT/15.0.0.0 (Skype for Business Server 2015 Stress and Performance Tool)</span></span>
    
- <span data-ttu-id="3cfaf-126">OCPHONE 電話/0.522</span><span class="sxs-lookup"><span data-stu-id="3cfaf-126">OCPHONE/.0.522</span></span>
    
<span data-ttu-id="3cfaf-127">LyncPerfTool のモビリティ (UCWA) クライアントの場合:</span><span class="sxs-lookup"><span data-stu-id="3cfaf-127">For the Mobility (UCWA) client in LyncPerfTool:</span></span>
  
- <span data-ttu-id="3cfaf-128">UCWA Perf ツール/Web 会議</span><span class="sxs-lookup"><span data-stu-id="3cfaf-128">UCWA Perf Tool/Web Conference</span></span>
    
- <span data-ttu-id="3cfaf-129">UCWA Perf ツール/モバイル</span><span class="sxs-lookup"><span data-stu-id="3cfaf-129">UCWA Perf Tool/Mobile</span></span>
    

