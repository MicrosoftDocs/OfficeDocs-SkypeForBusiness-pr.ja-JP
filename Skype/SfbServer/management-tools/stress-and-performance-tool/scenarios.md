---
title: ビジネス 2015 のサーバの負荷とパフォーマンス ツールの Skype のパフォーマンスのシナリオ
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
ms.date: 12/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d972382f-971e-4fa7-b7ee-8ab9d3a5c11d
description: タスクのストレスおよびパフォーマンス ツールを使用してパフォーマンスとロード テストを実行するサーバー 2015 のビジネス用の Skype を構成するのには実行する必要があります。
ms.openlocfilehash: 53504b714304b4b3cd18e44397ce0f06fcc59b63
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32194619"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="47be2-103">ビジネス 2015 のサーバの負荷とパフォーマンス ツールの Skype のパフォーマンスのシナリオ</span><span class="sxs-lookup"><span data-stu-id="47be2-103">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="47be2-104">タスクのストレスおよびパフォーマンス ツールを使用してパフォーマンスとロード テストを実行するサーバー 2015 のビジネス用の Skype を構成するのには実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="47be2-104">Tasks you'll need to do to configure Skype for Business Server 2015 to do performance and load-testing, using the Stress and Performance Tool.</span></span>
  
<span data-ttu-id="47be2-105">実行するには、Skype のビジネス サーバー 2015 のストレスおよびパフォーマンス ツール (LyncPerfTool) ビジネス サーバー 2015 トポロジの Skype が最初に関連するシナリオを構成しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="47be2-105">To run the Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool), the Skype for Business Server 2015 topology must first be configured for scenarios relevant to you.</span></span> <span data-ttu-id="47be2-106">ビジネス サーバー 2015 の Skype では、設定されていない、または構成が正しくない、負荷シミュレーションが失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="47be2-106">If Skype for Business Server 2015 isn't configured, or is configured incorrectly, your load simulation is very likely to fail.</span></span> <span data-ttu-id="47be2-107">ビジネス サーバー 2015 のストレスおよびパフォーマンス ツールの Skype、私たちの[ツールのダウンロード](https://www.microsoft.com/download/details.aspx?id=50367)の一部として、ビジネスのサーバー管理シェル スクリプトと基本的なリソース ファイルの Skype の使用例を提供しています。</span><span class="sxs-lookup"><span data-stu-id="47be2-107">With the Skype for Business Server 2015 Stress and Performance Tool, we're providing example Skype for Business Server Management Shell scripts and basic resource files as part of the [tool download](https://www.microsoft.com/download/details.aspx?id=50367).</span></span> <span data-ttu-id="47be2-108">ビジネス サーバーの展開について、Skype を構成するための開始点として使用することができます。</span><span class="sxs-lookup"><span data-stu-id="47be2-108">These can be used as a starting point for configuring your Skype for Business Server deployment.</span></span> <span data-ttu-id="47be2-109">この資料では、Windows PowerShell に示す例について説明します。</span><span class="sxs-lookup"><span data-stu-id="47be2-109">This article describes the Windows PowerShell examples provided.</span></span>
  
> [!NOTE]
> <span data-ttu-id="47be2-110">このトピックには、ビジネス サーバー 2015 の Skype を一般に構成する方法について説明することはできません、その他の計画と展開のトピックがあります。</span><span class="sxs-lookup"><span data-stu-id="47be2-110">This topic won't help you describe how to configure Skype for Business Server 2015 generally, we have other Planning and Deployment topics for that.</span></span> <span data-ttu-id="47be2-111">ビジネス サーバー 2015 の Skype で Windows PowerShell の使用に関する詳細については、Skype の挿入については、ここでビジネスのサーバー管理シェルのマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="47be2-111">For details about working with Windows PowerShell in Skype for Business Server 2015, see the Skype for Business Server Management Shell documentation at Insert introduction HERE.</span></span> 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a><span data-ttu-id="47be2-112">Skype ビジネス サーバーの管理にシェル スクリプトの実行について</span><span class="sxs-lookup"><span data-stu-id="47be2-112">About running Skype for Business Server management shell scripts</span></span>

<span data-ttu-id="47be2-113">負荷シミュレーション用に準備することができますを使用するサンプルの PowerShell スクリプトを提供しています。</span><span class="sxs-lookup"><span data-stu-id="47be2-113">We're providing sample PowerShell scripts you can use to prepare for your load simulations.</span></span> <span data-ttu-id="47be2-114">これらのスクリプトは、負荷のシミュレーションとしているために、それらをシンプルかつ寛容な型指定を入手できます。</span><span class="sxs-lookup"><span data-stu-id="47be2-114">Because these scripts are intended for load simulation, you'll find them to be simple and permissive.</span></span> <span data-ttu-id="47be2-115">実稼働環境に適切なことがあります。</span><span class="sxs-lookup"><span data-stu-id="47be2-115">That may not be appropriate for your production environment.</span></span> <span data-ttu-id="47be2-116">もう一度、これらのスクリプトのサンプルは、それらを確認し、多くの場合に変更を加える、環境に関連する前に実際に使用することにする必要がありますを強調します。</span><span class="sxs-lookup"><span data-stu-id="47be2-116">Again we stress that these scripts are samples, you'll need to review them and in many cases make changes relevant to your environment before being able to make practical use of them.</span></span> <span data-ttu-id="47be2-117">最低限、予想されるが、(エージェント グループに割り当てられたエージェントを指定します) に、トポロジに関する応答サービス グループ (RSG) スクリプトを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="47be2-117">At a minimum, we'd expect you'd need to modify the Response Service Group (RSG) script with your topology in mind (to specify the agents assigned to the agent groups).</span></span> <span data-ttu-id="47be2-118">必要はありません、実行する必要がある場合。</span><span class="sxs-lookup"><span data-stu-id="47be2-118">But you don't have to run that, if you don't need to.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="47be2-119">確認して、これらのサンプルを理解することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="47be2-119">Please take care in reviewing and understanding these samples.</span></span> <span data-ttu-id="47be2-120">スクリプトを実行すると、トポロジ内の既存の設定が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="47be2-120">Scripts will overwrite any existing settings in the topology when run.</span></span> 
  
## <a name="stress-and-performance-tool-client-version-names"></a><span data-ttu-id="47be2-121">ストレスおよびパフォーマンス ツールのクライアント バージョンの名前</span><span class="sxs-lookup"><span data-stu-id="47be2-121">Stress and Performance Tool client version names</span></span>

<span data-ttu-id="47be2-122">以前の既定値から設定を変更した場合にクライアントのバージョンの確認ポリシーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="47be2-122">You might need to configure the Client Version Check policy if you've previously changed the settings from the default values.</span></span> <span data-ttu-id="47be2-123">このことを確認していない場合は、[クライアントのバージョンを確認するドキュメント](https://msdn.microsoft.com/en-us/vsto/jj923060)を確認してください。</span><span class="sxs-lookup"><span data-stu-id="47be2-123">If you're unsure about this, check the [Client Version Check documentation](https://msdn.microsoft.com/en-us/vsto/jj923060).</span></span>
  
<span data-ttu-id="47be2-124">ストレスおよびパフォーマンス ツールは、ビジネス サーバー 2015 の Skype で通信するときに、既定で次のユーザー エージェントのバージョンを使用します。</span><span class="sxs-lookup"><span data-stu-id="47be2-124">The Stress and Performance Tool uses the following User Agent versions by default when communicating with Skype for Business Server 2015:</span></span>
  
- <span data-ttu-id="47be2-125">LSPT/15.0.0.0 (Skype ビジネス サーバー 2015 のストレスおよびパフォーマンス ツールを)</span><span class="sxs-lookup"><span data-stu-id="47be2-125">LSPT/15.0.0.0 (Skype for Business Server 2015 Stress and Performance Tool)</span></span>
    
- <span data-ttu-id="47be2-126">OCPHONE/.0.522</span><span class="sxs-lookup"><span data-stu-id="47be2-126">OCPHONE/.0.522</span></span>
    
<span data-ttu-id="47be2-127">LyncPerfTool の移動性 (UCWA) のクライアント。</span><span class="sxs-lookup"><span data-stu-id="47be2-127">For the Mobility (UCWA) client in LyncPerfTool:</span></span>
  
- <span data-ttu-id="47be2-128">UCWA のパフォーマンス ツールと Web 会議</span><span class="sxs-lookup"><span data-stu-id="47be2-128">UCWA Perf Tool/Web Conference</span></span>
    
- <span data-ttu-id="47be2-129">UCWA のパフォーマンス ツールやモバイル</span><span class="sxs-lookup"><span data-stu-id="47be2-129">UCWA Perf Tool/Mobile</span></span>
    

