---
title: Skype for Business Server 2015 Stress and Performance Tool のパフォーマンス シナリオ
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Stress and Performance Tool を使用して、パフォーマンスと負荷テストを実行するために Skype for Business Server 2015 を構成するために必要なタスク。
ms.openlocfilehash: 3edc945f09ef5b2c7c6ecdefcbc66166f0945aec
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814707"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="83e01-103">Skype for Business Server 2015 Stress and Performance Tool のパフォーマンス シナリオ</span><span class="sxs-lookup"><span data-stu-id="83e01-103">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="83e01-104">Stress and Performance Tool を使用して、パフォーマンスと負荷テストを実行するために Skype for Business Server 2015 を構成するために必要なタスク。</span><span class="sxs-lookup"><span data-stu-id="83e01-104">Tasks you'll need to do to configure Skype for Business Server 2015 to do performance and load-testing, using the Stress and Performance Tool.</span></span>
  
<span data-ttu-id="83e01-105">Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool) を実行するには、まず Skype for Business Server 2015 トポロジを、関連するシナリオ用に構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83e01-105">To run the Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool), the Skype for Business Server 2015 topology must first be configured for scenarios relevant to you.</span></span> <span data-ttu-id="83e01-106">Skype for Business Server 2015 が構成されていないか、正しく構成されていない場合、負荷シミュレーションが失敗する可能性が非常に高い。</span><span class="sxs-lookup"><span data-stu-id="83e01-106">If Skype for Business Server 2015 isn't configured, or is configured incorrectly, your load simulation is very likely to fail.</span></span> <span data-ttu-id="83e01-107">Skype for Business Server 2015 Stress and Performance Tool では、ツールダウンロードの一部として、Skype for Business Server 管理シェル スクリプトと基本的なリソース ファイルの例を [提供しています](https://www.microsoft.com/download/details.aspx?id=50367)。</span><span class="sxs-lookup"><span data-stu-id="83e01-107">With the Skype for Business Server 2015 Stress and Performance Tool, we're providing example Skype for Business Server Management Shell scripts and basic resource files as part of the [tool download](https://www.microsoft.com/download/details.aspx?id=50367).</span></span> <span data-ttu-id="83e01-108">これらは、Skype for Business Server 展開を構成するための開始点として使用できます。</span><span class="sxs-lookup"><span data-stu-id="83e01-108">These can be used as a starting point for configuring your Skype for Business Server deployment.</span></span> <span data-ttu-id="83e01-109">この記事では、以下の例Windows PowerShell説明します。</span><span class="sxs-lookup"><span data-stu-id="83e01-109">This article describes the Windows PowerShell examples provided.</span></span>
  
> [!NOTE]
> <span data-ttu-id="83e01-110">このトピックは、Skype for Business Server 2015 を一般的に構成する方法については説明しません。その他の計画および展開に関するトピックがあります。</span><span class="sxs-lookup"><span data-stu-id="83e01-110">This topic won't help you describe how to configure Skype for Business Server 2015 generally, we have other Planning and Deployment topics for that.</span></span> <span data-ttu-id="83e01-111">Skype for Business Server 2015 での Windows PowerShell の操作の詳細については、「Insert introduction HERE」にある Skype for Business Server 管理シェルのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="83e01-111">For details about working with Windows PowerShell in Skype for Business Server 2015, see the Skype for Business Server Management Shell documentation at Insert introduction HERE.</span></span> 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a><span data-ttu-id="83e01-112">Skype for Business Server 管理シェル スクリプトの実行について</span><span class="sxs-lookup"><span data-stu-id="83e01-112">About running Skype for Business Server management shell scripts</span></span>

<span data-ttu-id="83e01-113">負荷シミュレーションの準備に使用できるサンプル PowerShell スクリプトを提供しています。</span><span class="sxs-lookup"><span data-stu-id="83e01-113">We're providing sample PowerShell scripts you can use to prepare for your load simulations.</span></span> <span data-ttu-id="83e01-114">これらのスクリプトは読み込みシミュレーションを目的とします。このため、これらのスクリプトは単純で制限が少ない場合があります。</span><span class="sxs-lookup"><span data-stu-id="83e01-114">Because these scripts are intended for load simulation, you'll find them to be simple and permissive.</span></span> <span data-ttu-id="83e01-115">これは、ご使用の実稼働環境には適していない場合があります。</span><span class="sxs-lookup"><span data-stu-id="83e01-115">That may not be appropriate for your production environment.</span></span> <span data-ttu-id="83e01-116">繰り返しになりますが、これらのスクリプトはサンプルです。実際に使用する前に、スクリプトを確認する必要があります。多くの場合、環境に関連する変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="83e01-116">Again we stress that these scripts are samples, you'll need to review them and in many cases make changes relevant to your environment before being able to make practical use of them.</span></span> <span data-ttu-id="83e01-117">少なくとも、(エージェント グループに割り当てられているエージェントを指定するために) トポロジを念頭に置いて応答サービス グループ (RSG) スクリプトを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83e01-117">At a minimum, we'd expect you'd need to modify the Response Service Group (RSG) script with your topology in mind (to specify the agents assigned to the agent groups).</span></span> <span data-ttu-id="83e01-118">ただし、必要ない場合は、このコマンドを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83e01-118">But you don't have to run that, if you don't need to.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="83e01-119">これらのサンプルの確認と理解に注意してください。</span><span class="sxs-lookup"><span data-stu-id="83e01-119">Please take care in reviewing and understanding these samples.</span></span> <span data-ttu-id="83e01-120">スクリプトは、実行時にトポロジ内の既存の設定を上書きします。</span><span class="sxs-lookup"><span data-stu-id="83e01-120">Scripts will overwrite any existing settings in the topology when run.</span></span> 
  
## <a name="stress-and-performance-tool-client-version-names"></a><span data-ttu-id="83e01-121">Stress and Performance Tool クライアントのバージョン名</span><span class="sxs-lookup"><span data-stu-id="83e01-121">Stress and Performance Tool client version names</span></span>

<span data-ttu-id="83e01-122">以前に既定値から設定を変更した場合は、クライアント バージョン チェック ポリシーの構成が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="83e01-122">You might need to configure the Client Version Check policy if you've previously changed the settings from the default values.</span></span> <span data-ttu-id="83e01-123">不明な場合は、クライアント バージョン チェックのドキュメント [を確認してください](https://msdn.microsoft.com/vsto/jj923060)。</span><span class="sxs-lookup"><span data-stu-id="83e01-123">If you're unsure about this, check the [Client Version Check documentation](https://msdn.microsoft.com/vsto/jj923060).</span></span>
  
<span data-ttu-id="83e01-124">Stress and Performance Tool は、Skype for Business Server 2015 と通信するときに、既定で次のユーザー エージェント バージョンを使用します。</span><span class="sxs-lookup"><span data-stu-id="83e01-124">The Stress and Performance Tool uses the following User Agent versions by default when communicating with Skype for Business Server 2015:</span></span>
  
- <span data-ttu-id="83e01-125">LSPT/15.0.0.0 (Skype for Business Server 2015 Stress and Performance Tool)</span><span class="sxs-lookup"><span data-stu-id="83e01-125">LSPT/15.0.0.0 (Skype for Business Server 2015 Stress and Performance Tool)</span></span>
    
- <span data-ttu-id="83e01-126">OCPHONE/.0.522</span><span class="sxs-lookup"><span data-stu-id="83e01-126">OCPHONE/.0.522</span></span>
    
<span data-ttu-id="83e01-127">LyncPerfTool の Mobility (UCWA) クライアントの場合:</span><span class="sxs-lookup"><span data-stu-id="83e01-127">For the Mobility (UCWA) client in LyncPerfTool:</span></span>
  
- <span data-ttu-id="83e01-128">UCWA Perf ツール/Web 会議</span><span class="sxs-lookup"><span data-stu-id="83e01-128">UCWA Perf Tool/Web Conference</span></span>
    
- <span data-ttu-id="83e01-129">UCWA Perf ツール/モバイル</span><span class="sxs-lookup"><span data-stu-id="83e01-129">UCWA Perf Tool/Mobile</span></span>
    

