---
title: Skype for Business Server でファイル共有を作成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
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
ms.assetid: 053076b0-441c-44d9-8dbc-7a36d8ecafe4
description: '概要: Skype for Business Server のインストールの一部として Windows Server ファイル共有を作成する方法について説明します。 Skype for Business Server の無料トライアルは、次https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverの Microsoft 評価センターからダウンロードしてください。'
ms.openlocfilehash: 57d1bc348d1fed7a0dc8297723d41d3d90888710
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41790185"
---
# <a name="create-a-file-share-in-skype-for-business-server"></a><span data-ttu-id="936e6-104">Skype for Business Server でファイル共有を作成する</span><span class="sxs-lookup"><span data-stu-id="936e6-104">Create a file share in Skype for Business Server</span></span>
 
<span data-ttu-id="936e6-105">**概要:** Skype for Business Server のインストールの一部として Windows Server ファイル共有を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="936e6-105">**Summary:** Learn how to create a Windows Server file share as part of the installation of Skype for Business Server.</span></span> <span data-ttu-id="936e6-106">Skype for Business Server の無料トライアルは、次[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)の Microsoft 評価センターからダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="936e6-106">Download a free trial of Skype for Business Server from the Microsoft Evaluation center at:[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="936e6-107">Skype for Business Server を使用するには、トポロジ内のコンピューターがファイルを交換できるようにファイル共有が必要です。</span><span class="sxs-lookup"><span data-stu-id="936e6-107">Skype for Business Server requires a file share so that computers throughout the topology can exchange files.</span></span> <span data-ttu-id="936e6-108">ファイル共有を作成するには、Skype for Business Server のインストールプロセスの手順2/3 を実行します。</span><span class="sxs-lookup"><span data-stu-id="936e6-108">Creating a file share is step 2 of 8 in the installation process for Skype for Business Server.</span></span> <span data-ttu-id="936e6-109">手順 1 ～ 5 は任意の順序で実行できます。</span><span class="sxs-lookup"><span data-stu-id="936e6-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="936e6-110">ただし、手順6、7、8を順番に実行する必要があります。また、図に示されている手順 1 ~ 5 の後に行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="936e6-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5 as outlined in the diagram.</span></span> <span data-ttu-id="936e6-111">ファイル共有の詳細については、「skype for business [server の環境要件](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)」または「 [Skype for business Server 2019 のサーバー要件](../../../SfBServer2019/plan/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="936e6-111">For planning details about file share, see [Environmental requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span></span>
  
![概要図](../../media/e69de059-3040-45ab-9379-1932f9fbb37f.png)
  
## <a name="create-a-basic-file-share"></a><span data-ttu-id="936e6-113">基本的なファイル共有を作成する</span><span class="sxs-lookup"><span data-stu-id="936e6-113">Create a basic file share</span></span>

<span data-ttu-id="936e6-114">ここでは、基本的な Windows Server ファイル共有を作成する方法を詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="936e6-114">This section walks you through creating a basic Windows Server file share.</span></span> <span data-ttu-id="936e6-115">Windows Server の基本的なファイル共有は、Skype for Business Server でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="936e6-115">A basic Windows Server file share is supported with Skype for Business Server.</span></span> <span data-ttu-id="936e6-116">ただし、高可用性を明示的に提供するわけではありません。</span><span class="sxs-lookup"><span data-stu-id="936e6-116">However, it does not explicitly provide high availability.</span></span> <span data-ttu-id="936e6-117">高可用性環境が必要な場合は、分散ファイル システム (DFS) ファイル共有をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="936e6-117">For a high availability environment, a Distributed File System (DFS) file share is recommended.</span></span> <span data-ttu-id="936e6-118">高可用性ファイルの共有と DFS の詳細については、「 [Skype For Business Server で高可用性と障害回復を計画](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="936e6-118">For more information about a high availability file share and DFS, see [Plan for high availability and disaster recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="936e6-119">Windows Server 2012 R2 は、Windows Server プラットフォームを使用した記憶域ネットワーク (SAN) のようなファイル共有ソリューションの提供において大きな飛躍を遂げました。</span><span class="sxs-lookup"><span data-stu-id="936e6-119">Windows Server 2012 R2 has made major leaps in providing Storage Area Network (SAN)-like file share solutions using the Windows Server platform.</span></span> <span data-ttu-id="936e6-120">Windows Server 2012 R2 ストレージ ソリューションは従来の SAN ベースのアプライアンスに比べて、パフォーマンスへの影響を最小限に抑えつつコストを半減できます。</span><span class="sxs-lookup"><span data-stu-id="936e6-120">When compared to a traditional SAN-based appliance, a Windows Server 2012 R2 storage solution can cut costs in half with very minimal impact to performance.</span></span> <span data-ttu-id="936e6-121">Windows Server 2012 R2 のファイル共有オプションの詳細については、ダウンロード可能なホワイトペーパー [Windows server 2012 R2 ストレージ](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="936e6-121">For more information about file share options in Windows Server 2012 R2, see the downloadable white paper [Windows Server 2012 R2 Storage](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf).</span></span> 
  
<span data-ttu-id="936e6-122">**ファイル共有の作成**手順に関するビデオをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="936e6-122">Watch the video steps for **create a file share**:</span></span>
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/dbef31be-e899-4a32-a1ca-370053284f56?autoplay=false]
  
### <a name="create-a-basic-file-share"></a><span data-ttu-id="936e6-123">基本的なファイル共有を作成する</span><span class="sxs-lookup"><span data-stu-id="936e6-123">Create a basic file share</span></span>

1. <span data-ttu-id="936e6-124">ファイル共有をホストするコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="936e6-124">Log on to the computer that will host the file share.</span></span>
    
2. <span data-ttu-id="936e6-125">共有するフォルダーを右クリックし、[**プロパティ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="936e6-125">Right-click the folder you plan to share, and select **Properties**.</span></span>
    
3. <span data-ttu-id="936e6-126">[**共有**] タブを選択し、[**詳細な共有**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="936e6-126">Select the **Sharing** tab, and click **Advanced Sharing**.</span></span>
    
4. <span data-ttu-id="936e6-127">[**このフォルダーを共有する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="936e6-127">Click **Share this folder**.</span></span>
    
5. <span data-ttu-id="936e6-128">[**アクセス許可**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="936e6-128">Click **Permissions**.</span></span>
    
6. <span data-ttu-id="936e6-129">ファイル共有をホストするサーバーのローカルの **Administrators** グループを追加し、**フル コントロール、変更、読み取り**の権限を付与し、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="936e6-129">Add the local **Administrators** group of the server hosting the file share, grant **Allow: Full Control, Change, and Read** rights, and then click **OK**.</span></span>
    
7. <span data-ttu-id="936e6-130">[**OK**] をもう一度クリックして、ネットワーク パスをメモします。</span><span class="sxs-lookup"><span data-stu-id="936e6-130">Click **OK** again and take note of the network path.</span></span>
    
8. <span data-ttu-id="936e6-131">[**完了**] をクリックして、ウィザードを終了します。</span><span class="sxs-lookup"><span data-stu-id="936e6-131">Click **Done** to close the wizard.</span></span>
    
     ![フォルダー共有のための [共有] タブ](../../media/78fe8441-dead-43ed-9a04-3c7c8c657c15.png)
  
> [!NOTE]
><span data-ttu-id="936e6-133">ファイルストアが DFS 共有でホストされている場合は、次の警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="936e6-133">If the file store is hosted on a DFS share, the following warning will be received:</span></span>

<span data-ttu-id="936e6-134">警告: "\\<domain>\<共有>" の共有アクセス許可にアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="936e6-134">Warning: Unable to access share permissions for "\\<domain>\<share>".</span></span>

><span data-ttu-id="936e6-135">これは、ファイルサーバーの管理者ではないか、または分散ファイルシステム (DFS) 共有である場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="936e6-135">This is expected if you are not an administrator on the file server, or if this is a Distributed File System (DFS) share.</span></span> <span data-ttu-id="936e6-136">共有のアクセス許可が既に構成されている場合は、この警告を無視できます。</span><span class="sxs-lookup"><span data-stu-id="936e6-136">If the share permissions have already been configured, this warning can be ignored.</span></span> <span data-ttu-id="936e6-137">新しい共有の場合は、共有のアクセス許可を手動で構成する方法に関するドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="936e6-137">If it is a new share, refer to the documentation for details on manually configuring share permissions.</span></span>

><span data-ttu-id="936e6-138">DFS 共有の共有アクセス許可にアクセスできないため、Skype for Business Server では、ファイル共有に対して明示的にグループを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="936e6-138">Due to the inability to access the share permissions on a DFS share, Skype for Business Server will not be able to explicitly set groups on the file share.</span></span> <span data-ttu-id="936e6-139">Skype for Business Server コンポーネントが適切な権限を持つファイル共有にアクセスできるようにするには、フルコントロール共有を使用して、ローカル管理者に加えて、読み取りおよび変更レベルの共有のアクセス許可を使用して、次の RTC グループを追加する必要があります。権限.</span><span class="sxs-lookup"><span data-stu-id="936e6-139">To ensure Skype for Business Server components can access the file share with the appropriate permissions, ensure the following RTC groups are added with Read and Change level share permissions in addition to the local Administrators with Full Control share permissions.</span></span>
* <span data-ttu-id="936e6-140">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="936e6-140">RTCHSUniversalServices</span></span>
* <span data-ttu-id="936e6-141">RTCComponentUniversalServices</span><span class="sxs-lookup"><span data-stu-id="936e6-141">RTCComponentUniversalServices</span></span>
* <span data-ttu-id="936e6-142">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="936e6-142">RTCUniversalServerAdmins</span></span>
