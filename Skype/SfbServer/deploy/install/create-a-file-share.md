---
title: Skype のビジネス サーバーのファイル共有を作成します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 053076b0-441c-44d9-8dbc-7a36d8ecafe4
description: '概要: は、Skype のビジネス サーバーのインストールの一部として、Windows サーバーのファイル共有を作成する方法を説明します。 ビジネスのサーバーで Microsoft の評価の中心からの Skype の無料試用版をダウンロード: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server。'
ms.openlocfilehash: a6a040c60d3c5a41df8dfa24abd5948d85180f2e
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23884622"
---
# <a name="create-a-file-share-in-skype-for-business-server"></a><span data-ttu-id="10d2e-104">Skype のビジネス サーバーのファイル共有を作成します。</span><span class="sxs-lookup"><span data-stu-id="10d2e-104">Create a file share in Skype for Business Server</span></span>
 
<span data-ttu-id="10d2e-105">**の概要:** Skype のビジネス サーバーのインストールの一部として、Windows サーバーのファイル共有を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="10d2e-105">**Summary:** Learn how to create a Windows Server file share as part of the installation of Skype for Business Server.</span></span> <span data-ttu-id="10d2e-106">ビジネスのサーバーで Microsoft の評価の中心からの Skype の無料試用版をダウンロード:[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)。</span><span class="sxs-lookup"><span data-stu-id="10d2e-106">Download a free trial of Skype for Business Server from the Microsoft Evaluation center at:[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="10d2e-107">ビジネス サーバーの Skype では、トポロジ内のコンピューターにファイルを交換できるように、ファイル共有が必要です。</span><span class="sxs-lookup"><span data-stu-id="10d2e-107">Skype for Business Server requires a file share so that computers throughout the topology can exchange files.</span></span> <span data-ttu-id="10d2e-108">Skype ビジネス サーバーのインストール プロセスでの 8 のステップ 2 は、ファイル共有を作成します。</span><span class="sxs-lookup"><span data-stu-id="10d2e-108">Creating a file share is step 2 of 8 in the installation process for Skype for Business Server.</span></span> <span data-ttu-id="10d2e-109">手順 1 ～ 5 は任意の順序で実行できます。</span><span class="sxs-lookup"><span data-stu-id="10d2e-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="10d2e-110">ただし、図に示すように手順 6、7、および 8 では、手順 1 5 からの後を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="10d2e-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5 as outlined in the diagram.</span></span> <span data-ttu-id="10d2e-111">ファイル共有についての詳細を計画するため、 [Skype のビジネス サーバーの環境要件](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)や[ビジネス サーバー 2019 の Skype のサーバーの要件](../../../SfBServer2019/plan/system-requirements.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10d2e-111">For planning details about file share, see [Environmental requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span></span>
  
![概要図](../../media/e69de059-3040-45ab-9379-1932f9fbb37f.png)
  
## <a name="create-a-basic-file-share"></a><span data-ttu-id="10d2e-113">基本的なファイル共有を作成する</span><span class="sxs-lookup"><span data-stu-id="10d2e-113">Create a basic file share</span></span>

<span data-ttu-id="10d2e-114">ここでは、基本的な Windows Server ファイル共有を作成する方法を詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="10d2e-114">This section walks you through creating a basic Windows Server file share.</span></span> <span data-ttu-id="10d2e-115">ビジネス サーバーの Skype で基本的な Windows Server のファイル共有がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="10d2e-115">A basic Windows Server file share is supported with Skype for Business Server.</span></span> <span data-ttu-id="10d2e-116">ただし、明示的には行いません高可用性を実現します。</span><span class="sxs-lookup"><span data-stu-id="10d2e-116">However, it does not explicitly provide high availability.</span></span> <span data-ttu-id="10d2e-117">高可用性環境が必要な場合は、分散ファイル システム (DFS) ファイル共有をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="10d2e-117">For a high availability environment, a Distributed File System (DFS) file share is recommended.</span></span> <span data-ttu-id="10d2e-118">高可用性のファイル共有および DFS の詳細については、[高可用性とビジネスのサーバー用の Skype での災害復旧の計画](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10d2e-118">For more information about a high availability file share and DFS, see [Plan for high availability and disaster recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="10d2e-119">Windows Server 2012 R2 は、Windows Server プラットフォームを使用した記憶域ネットワーク (SAN) のようなファイル共有ソリューションの提供において大きな飛躍を遂げました。</span><span class="sxs-lookup"><span data-stu-id="10d2e-119">Windows Server 2012 R2 has made major leaps in providing Storage Area Network (SAN)-like file share solutions using the Windows Server platform.</span></span> <span data-ttu-id="10d2e-120">Windows Server 2012 R2 ストレージ ソリューションは従来の SAN ベースのアプライアンスに比べて、パフォーマンスへの影響を最小限に抑えつつコストを半減できます。</span><span class="sxs-lookup"><span data-stu-id="10d2e-120">When compared to a traditional SAN-based appliance, a Windows Server 2012 R2 storage solution can cut costs in half with very minimal impact to performance.</span></span> <span data-ttu-id="10d2e-121">Windows Server 2012 R2 のファイル共有オプションの詳細については、 [Windows Server 2012 R2 のストレージ](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf)ダウンロード可能なホワイト ペーパーを参照してください。</span><span class="sxs-lookup"><span data-stu-id="10d2e-121">For more information about file share options in Windows Server 2012 R2, see the downloadable white paper [Windows Server 2012 R2 Storage](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf).</span></span> 
  
<span data-ttu-id="10d2e-122">**ファイル共有の作成**手順に関するビデオをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="10d2e-122">Watch the video steps for **create a file share**:</span></span>
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/dbef31be-e899-4a32-a1ca-370053284f56?autoplay=false]
  
### <a name="create-a-basic-file-share"></a><span data-ttu-id="10d2e-123">基本的なファイル共有を作成する</span><span class="sxs-lookup"><span data-stu-id="10d2e-123">Create a basic file share</span></span>

1. <span data-ttu-id="10d2e-124">ファイル共有をホストするコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="10d2e-124">Log on to the computer that will host the file share.</span></span>
    
2. <span data-ttu-id="10d2e-125">共有するフォルダーを右クリックし、[**プロパティ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="10d2e-125">Right-click the folder you plan to share, and select **Properties**.</span></span>
    
3. <span data-ttu-id="10d2e-126">[**共有**] タブを選択し、[**詳細な共有**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="10d2e-126">Select the **Sharing** tab, and click **Advanced Sharing**.</span></span>
    
4. <span data-ttu-id="10d2e-127">[**このフォルダーを共有する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="10d2e-127">Click **Share this folder**.</span></span>
    
5. <span data-ttu-id="10d2e-128">[**アクセス許可**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="10d2e-128">Click **Permissions**.</span></span>
    
6. <span data-ttu-id="10d2e-129">ファイル共有をホストするサーバーのローカルの **Administrators** グループを追加し、**フル コントロール、変更、読み取り**の権限を付与し、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="10d2e-129">Add the local **Administrators** group of the server hosting the file share, grant **Allow: Full Control, Change, and Read** rights, and then click **OK**.</span></span>
    
7. <span data-ttu-id="10d2e-130">[**OK**] をもう一度クリックして、ネットワーク パスをメモします。</span><span class="sxs-lookup"><span data-stu-id="10d2e-130">Click **OK** again and take note of the network path.</span></span>
    
8. <span data-ttu-id="10d2e-131">[**完了**] をクリックして、ウィザードを終了します。</span><span class="sxs-lookup"><span data-stu-id="10d2e-131">Click **Done** to close the wizard.</span></span>
    
     ![フォルダー共有のための [共有] タブ](../../media/78fe8441-dead-43ed-9a04-3c7c8c657c15.png)
  

