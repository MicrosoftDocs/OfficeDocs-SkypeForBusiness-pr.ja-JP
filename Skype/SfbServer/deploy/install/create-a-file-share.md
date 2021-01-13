---
title: Skype for Business Server でファイル共有を作成する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: '概要: Skype for Business Server のインストールの一部として Windows Server ファイル共有を作成する方法について学習します。 Microsoft Evaluation Center から Skype for Business Server の無料試用版を次の場所からダウンロードします https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server 。'
ms.openlocfilehash: 63ed4c54154698336bea7adb87db4e81d5fd35b4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812237"
---
# <a name="create-a-file-share-in-skype-for-business-server"></a><span data-ttu-id="5171c-104">Skype for Business Server でファイル共有を作成する</span><span class="sxs-lookup"><span data-stu-id="5171c-104">Create a file share in Skype for Business Server</span></span>
 
<span data-ttu-id="5171c-105">**概要:** Skype for Business Server のインストールの一部として Windows Server ファイル共有を作成する方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="5171c-105">**Summary:** Learn how to create a Windows Server file share as part of the installation of Skype for Business Server.</span></span> <span data-ttu-id="5171c-106">Microsoft Evaluation Center から Skype for Business Server の無料試用版を次の場所からダウンロードします [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server) 。</span><span class="sxs-lookup"><span data-stu-id="5171c-106">Download a free trial of Skype for Business Server from the Microsoft Evaluation center at:[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="5171c-107">Skype for Business Server では、トポロジ全体のコンピューターがファイルを交換できるよう、ファイル共有が必要です。</span><span class="sxs-lookup"><span data-stu-id="5171c-107">Skype for Business Server requires a file share so that computers throughout the topology can exchange files.</span></span> <span data-ttu-id="5171c-108">ファイル共有の作成は、Skype for Business Server のインストール プロセスの手順 2/8 です。</span><span class="sxs-lookup"><span data-stu-id="5171c-108">Creating a file share is step 2 of 8 in the installation process for Skype for Business Server.</span></span> <span data-ttu-id="5171c-109">手順 1. ~ 5. は任意の順序で実行できます。</span><span class="sxs-lookup"><span data-stu-id="5171c-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="5171c-110">ただし、手順 6、7、および 8 を順番に実行し、図に示されている手順 1 ~ 5 の後に実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5171c-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5 as outlined in the diagram.</span></span> <span data-ttu-id="5171c-111">ファイル共有の計画の詳細については [、「Environmental requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or Server [requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5171c-111">For planning details about file share, see [Environmental requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span></span>
  
![概要図](../../media/e69de059-3040-45ab-9379-1932f9fbb37f.png)
  
## <a name="create-a-basic-file-share"></a><span data-ttu-id="5171c-113">基本的なファイル共有を作成する</span><span class="sxs-lookup"><span data-stu-id="5171c-113">Create a basic file share</span></span>

<span data-ttu-id="5171c-114">このセクションでは、基本的な Windows Server ファイル共有を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5171c-114">This section walks you through creating a basic Windows Server file share.</span></span> <span data-ttu-id="5171c-115">基本的な Windows Server ファイル共有は、Skype for Business Server でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="5171c-115">A basic Windows Server file share is supported with Skype for Business Server.</span></span> <span data-ttu-id="5171c-116">ただし、明示的に高可用性を提供するわけではありません。</span><span class="sxs-lookup"><span data-stu-id="5171c-116">However, it does not explicitly provide high availability.</span></span> <span data-ttu-id="5171c-117">高可用性環境では、分散ファイル システム (DFS) ファイル共有をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5171c-117">For a high availability environment, a Distributed File System (DFS) file share is recommended.</span></span> <span data-ttu-id="5171c-118">高可用性ファイル共有と DFS の詳細については [、「Plan for high availability and disaster recovery in Skype for Business Server 」を参照してください](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="5171c-118">For more information about a high availability file share and DFS, see [Plan for high availability and disaster recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="5171c-119">Windows Server 2012 R2 は、Windows Server プラットフォームを使用して記憶域ネットワーク (SAN) に似たファイル共有ソリューションを提供する上で大きな飛び上がりを見た。</span><span class="sxs-lookup"><span data-stu-id="5171c-119">Windows Server 2012 R2 has made major leaps in providing Storage Area Network (SAN)-like file share solutions using the Windows Server platform.</span></span> <span data-ttu-id="5171c-120">従来の SAN ベースのアプライアンスと比較すると、Windows Server 2012 R2 ストレージ ソリューションはパフォーマンスへの影響を最小限に抑え、コストを半分に削減できます。</span><span class="sxs-lookup"><span data-stu-id="5171c-120">When compared to a traditional SAN-based appliance, a Windows Server 2012 R2 storage solution can cut costs in half with very minimal impact to performance.</span></span> <span data-ttu-id="5171c-121">Windows Server 2012 R2 のファイル共有オプションの詳細については、R2 Storage のダウンロード可能なホワイト [ペーパー Windows Server 2012参照してください](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf)。</span><span class="sxs-lookup"><span data-stu-id="5171c-121">For more information about file share options in Windows Server 2012 R2, see the downloadable white paper [Windows Server 2012 R2 Storage](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf).</span></span> 
  
<span data-ttu-id="5171c-122">ファイル共有を作成するためのビデオ **の手順をご覧ください**。</span><span class="sxs-lookup"><span data-stu-id="5171c-122">Watch the video steps for **create a file share**:</span></span>
  
> [!video https://www.microsoft.com/videoplayer/embed/dbef31be-e899-4a32-a1ca-370053284f56?autoplay=false]
  
### <a name="create-a-basic-file-share"></a><span data-ttu-id="5171c-123">基本的なファイル共有を作成する</span><span class="sxs-lookup"><span data-stu-id="5171c-123">Create a basic file share</span></span>

1. <span data-ttu-id="5171c-124">ファイル共有をホストするコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="5171c-124">Log on to the computer that will host the file share.</span></span>
    
2. <span data-ttu-id="5171c-125">共有するフォルダーを右クリックし、[プロパティ] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="5171c-125">Right-click the folder you plan to share, and select **Properties**.</span></span>
    
3. <span data-ttu-id="5171c-126">[共有] **タブを選択** し、[高度な共有] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="5171c-126">Select the **Sharing** tab, and click **Advanced Sharing**.</span></span>
    
4. <span data-ttu-id="5171c-127">[この **フォルダーの共有] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="5171c-127">Click **Share this folder**.</span></span>
    
5. <span data-ttu-id="5171c-128">**[アクセス許可]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5171c-128">Click **Permissions**.</span></span>
    
6. <span data-ttu-id="5171c-129">ファイル共有を **ホストしているサーバーのローカルの Administrators** グループを追加し、[ **許可:** フル コントロール、変更、読み取り権限] を付与して **、[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5171c-129">Add the local **Administrators** group of the server hosting the file share, grant **Allow: Full Control, Change, and Read** rights, and then click **OK**.</span></span>
    
7. <span data-ttu-id="5171c-130">もう **一度 [OK]** をクリックし、ネットワーク パスをメモします。</span><span class="sxs-lookup"><span data-stu-id="5171c-130">Click **OK** again and take note of the network path.</span></span>
    
8. <span data-ttu-id="5171c-131">[ **完了] を** クリックしてウィザードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="5171c-131">Click **Done** to close the wizard.</span></span>
    
     ![フォルダーを共有する [共有] タブ。](../../media/78fe8441-dead-43ed-9a04-3c7c8c657c15.png)
  
> [!NOTE]
><span data-ttu-id="5171c-133">ファイル ストアが DFS 共有でホストされている場合は、次の警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5171c-133">If the file store is hosted on a DFS share, the following warning will be received:</span></span>

<span data-ttu-id="5171c-134">警告: " " の共有アクセス許可にアクセスできません \\ <domain> \<share> 。</span><span class="sxs-lookup"><span data-stu-id="5171c-134">Warning: Unable to access share permissions for "\\<domain>\<share>".</span></span>

><span data-ttu-id="5171c-135">これは、ファイル サーバーの管理者ではない場合、またはこれが分散ファイル システム (DFS) 共有の場合に想定されます。</span><span class="sxs-lookup"><span data-stu-id="5171c-135">This is expected if you are not an administrator on the file server, or if this is a Distributed File System (DFS) share.</span></span> <span data-ttu-id="5171c-136">共有アクセス許可が既に構成されている場合、この警告は無視できます。</span><span class="sxs-lookup"><span data-stu-id="5171c-136">If the share permissions have already been configured, this warning can be ignored.</span></span> <span data-ttu-id="5171c-137">新しい共有の場合は、手動で共有アクセス許可を構成する方法の詳細については、ドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5171c-137">If it is a new share, refer to the documentation for details on manually configuring share permissions.</span></span>

><span data-ttu-id="5171c-138">DFS 共有の共有アクセス許可にアクセスできないので、Skype for Business Server はファイル共有にグループを明示的に設定できません。</span><span class="sxs-lookup"><span data-stu-id="5171c-138">Due to the inability to access the share permissions on a DFS share, Skype for Business Server will not be able to explicitly set groups on the file share.</span></span> <span data-ttu-id="5171c-139">Skype for Business Server コンポーネントが適切なアクセス許可を持つファイル共有にアクセスするには、フル コントロール共有アクセス許可を持つローカル管理者に加えて、読み取りおよび変更レベルの共有アクセス許可を持つ次の RTC グループが追加されます。</span><span class="sxs-lookup"><span data-stu-id="5171c-139">To ensure Skype for Business Server components can access the file share with the appropriate permissions, ensure the following RTC groups are added with Read and Change level share permissions in addition to the local Administrators with Full Control share permissions.</span></span>
* <span data-ttu-id="5171c-140">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="5171c-140">RTCHSUniversalServices</span></span>
* <span data-ttu-id="5171c-141">RTCComponentUniversalServices</span><span class="sxs-lookup"><span data-stu-id="5171c-141">RTCComponentUniversalServices</span></span>
* <span data-ttu-id="5171c-142">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="5171c-142">RTCUniversalServerAdmins</span></span>
