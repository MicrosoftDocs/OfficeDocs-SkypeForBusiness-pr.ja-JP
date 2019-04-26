---
title: Skype のビジネス サーバーのファイル共有を作成します。
ms.reviewer: ''
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
ms.openlocfilehash: b92d85d375b76b43dcf65f01205c3826e5637905
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32238273"
---
# <a name="create-a-file-share-in-skype-for-business-server"></a><span data-ttu-id="750ab-104">Skype のビジネス サーバーのファイル共有を作成します。</span><span class="sxs-lookup"><span data-stu-id="750ab-104">Create a file share in Skype for Business Server</span></span>
 
<span data-ttu-id="750ab-105">**の概要:** Skype のビジネス サーバーのインストールの一部として、Windows サーバーのファイル共有を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="750ab-105">**Summary:** Learn how to create a Windows Server file share as part of the installation of Skype for Business Server.</span></span> <span data-ttu-id="750ab-106">ビジネスのサーバーで Microsoft の評価の中心からの Skype の無料試用版をダウンロード:[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)。</span><span class="sxs-lookup"><span data-stu-id="750ab-106">Download a free trial of Skype for Business Server from the Microsoft Evaluation center at:[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="750ab-107">ビジネス サーバーの Skype では、トポロジ内のコンピューターにファイルを交換できるように、ファイル共有が必要です。</span><span class="sxs-lookup"><span data-stu-id="750ab-107">Skype for Business Server requires a file share so that computers throughout the topology can exchange files.</span></span> <span data-ttu-id="750ab-108">Skype ビジネス サーバーのインストール プロセスでの 8 のステップ 2 は、ファイル共有を作成します。</span><span class="sxs-lookup"><span data-stu-id="750ab-108">Creating a file share is step 2 of 8 in the installation process for Skype for Business Server.</span></span> <span data-ttu-id="750ab-109">手順 1 ～ 5 は任意の順序で実行できます。</span><span class="sxs-lookup"><span data-stu-id="750ab-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="750ab-110">ただし、図に示すように手順 6、7、および 8 では、手順 1 5 からの後を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="750ab-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5 as outlined in the diagram.</span></span> <span data-ttu-id="750ab-111">ファイル共有についての詳細を計画するため、 [Skype のビジネス サーバーの環境要件](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)や[ビジネス サーバー 2019 の Skype のサーバーの要件](../../../SfBServer2019/plan/system-requirements.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="750ab-111">For planning details about file share, see [Environmental requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span></span>
  
![概要図](../../media/e69de059-3040-45ab-9379-1932f9fbb37f.png)
  
## <a name="create-a-basic-file-share"></a><span data-ttu-id="750ab-113">基本的なファイル共有を作成する</span><span class="sxs-lookup"><span data-stu-id="750ab-113">Create a basic file share</span></span>

<span data-ttu-id="750ab-114">ここでは、基本的な Windows Server ファイル共有を作成する方法を詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="750ab-114">This section walks you through creating a basic Windows Server file share.</span></span> <span data-ttu-id="750ab-115">ビジネス サーバーの Skype で基本的な Windows Server のファイル共有がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="750ab-115">A basic Windows Server file share is supported with Skype for Business Server.</span></span> <span data-ttu-id="750ab-116">ただし、明示的には行いません高可用性を実現します。</span><span class="sxs-lookup"><span data-stu-id="750ab-116">However, it does not explicitly provide high availability.</span></span> <span data-ttu-id="750ab-117">高可用性環境が必要な場合は、分散ファイル システム (DFS) ファイル共有をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="750ab-117">For a high availability environment, a Distributed File System (DFS) file share is recommended.</span></span> <span data-ttu-id="750ab-118">高可用性のファイル共有および DFS の詳細については、[高可用性とビジネスのサーバー用の Skype での災害復旧の計画](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="750ab-118">For more information about a high availability file share and DFS, see [Plan for high availability and disaster recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="750ab-119">Windows Server 2012 R2 は、Windows Server プラットフォームを使用した記憶域ネットワーク (SAN) のようなファイル共有ソリューションの提供において大きな飛躍を遂げました。</span><span class="sxs-lookup"><span data-stu-id="750ab-119">Windows Server 2012 R2 has made major leaps in providing Storage Area Network (SAN)-like file share solutions using the Windows Server platform.</span></span> <span data-ttu-id="750ab-120">Windows Server 2012 R2 ストレージ ソリューションは従来の SAN ベースのアプライアンスに比べて、パフォーマンスへの影響を最小限に抑えつつコストを半減できます。</span><span class="sxs-lookup"><span data-stu-id="750ab-120">When compared to a traditional SAN-based appliance, a Windows Server 2012 R2 storage solution can cut costs in half with very minimal impact to performance.</span></span> <span data-ttu-id="750ab-121">Windows Server 2012 R2 のファイル共有オプションの詳細については、 [Windows Server 2012 R2 のストレージ](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf)ダウンロード可能なホワイト ペーパーを参照してください。</span><span class="sxs-lookup"><span data-stu-id="750ab-121">For more information about file share options in Windows Server 2012 R2, see the downloadable white paper [Windows Server 2012 R2 Storage](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf).</span></span> 
  
<span data-ttu-id="750ab-122">**ファイル共有の作成**手順に関するビデオをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="750ab-122">Watch the video steps for **create a file share**:</span></span>
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/dbef31be-e899-4a32-a1ca-370053284f56?autoplay=false]
  
### <a name="create-a-basic-file-share"></a><span data-ttu-id="750ab-123">基本的なファイル共有を作成する</span><span class="sxs-lookup"><span data-stu-id="750ab-123">Create a basic file share</span></span>

1. <span data-ttu-id="750ab-124">ファイル共有をホストするコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="750ab-124">Log on to the computer that will host the file share.</span></span>
    
2. <span data-ttu-id="750ab-125">共有するフォルダーを右クリックし、[**プロパティ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="750ab-125">Right-click the folder you plan to share, and select **Properties**.</span></span>
    
3. <span data-ttu-id="750ab-126">[**共有**] タブを選択し、[**詳細な共有**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="750ab-126">Select the **Sharing** tab, and click **Advanced Sharing**.</span></span>
    
4. <span data-ttu-id="750ab-127">[**このフォルダーを共有する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="750ab-127">Click **Share this folder**.</span></span>
    
5. <span data-ttu-id="750ab-128">[**アクセス許可**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="750ab-128">Click **Permissions**.</span></span>
    
6. <span data-ttu-id="750ab-129">ファイル共有をホストするサーバーのローカルの **Administrators** グループを追加し、**フル コントロール、変更、読み取り**の権限を付与し、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="750ab-129">Add the local **Administrators** group of the server hosting the file share, grant **Allow: Full Control, Change, and Read** rights, and then click **OK**.</span></span>
    
7. <span data-ttu-id="750ab-130">[**OK**] をもう一度クリックして、ネットワーク パスをメモします。</span><span class="sxs-lookup"><span data-stu-id="750ab-130">Click **OK** again and take note of the network path.</span></span>
    
8. <span data-ttu-id="750ab-131">[**完了**] をクリックして、ウィザードを終了します。</span><span class="sxs-lookup"><span data-stu-id="750ab-131">Click **Done** to close the wizard.</span></span>
    
     ![フォルダー共有のための [共有] タブ](../../media/78fe8441-dead-43ed-9a04-3c7c8c657c15.png)
  
> [!NOTE]
><span data-ttu-id="750ab-133">ファイル ストアがでホストされている場合は、DFS 共有、次の警告メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="750ab-133">If the file store is hosted on a DFS share, the following warning will be received:</span></span>

<span data-ttu-id="750ab-134">警告: に対する共有アクセス許可にアクセスできません"\\<domain>\<share>」です。</span><span class="sxs-lookup"><span data-stu-id="750ab-134">Warning: Unable to access share permissions for "\\<domain>\<share>".</span></span>

><span data-ttu-id="750ab-135">ファイル サーバーの管理者でない場合、または分散ファイル システム (DFS) 共有の場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="750ab-135">This is expected if you are not an administrator on the file server, or if this is a Distributed File System (DFS) share.</span></span> <span data-ttu-id="750ab-136">共有のアクセス許可が既に構成されて場合、この警告は無視できます。</span><span class="sxs-lookup"><span data-stu-id="750ab-136">If the share permissions have already been configured, this warning can be ignored.</span></span> <span data-ttu-id="750ab-137">新しい共有である場合は、共有のアクセス許可を手動で構成の詳細についてはマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="750ab-137">If it is a new share, refer to the documentation for details on manually configuring share permissions.</span></span>

><span data-ttu-id="750ab-138">DFS 共有に共有のアクセス許可にアクセスできない、ため Skype ビジネス サーバーのファイル共有のグループを明示的に設定することができません。</span><span class="sxs-lookup"><span data-stu-id="750ab-138">Due to the inability to access the share permissions on a DFS share, Skype for Business Server will not be able to explicitly set groups on the file share.</span></span> <span data-ttu-id="750ab-139">Skype ビジネス サーバー コンポーネントの適切なアクセス許可でファイル共有にアクセスできることを確認するには、RTC の次のグループ レベルの共有アクセス許可の変更だけでなくローカルの管理者フル コントロールの共有アクセス許可の追加を確認します。</span><span class="sxs-lookup"><span data-stu-id="750ab-139">To ensure Skype for Business Server components can access the file share with the appropriate permissions, ensure the following RTC groups are added with Change level share permissions in addition to the local Administrators with Full Control share permissions.</span></span>

<span data-ttu-id="750ab-140">RTCHSUniversalServices RTCComponentUniversalServices RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="750ab-140">RTCHSUniversalServices RTCComponentUniversalServices RTCUniversalServerAdmins</span></span>
