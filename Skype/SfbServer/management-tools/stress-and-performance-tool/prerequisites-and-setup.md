---
title: Skype for Busines Stress and Performance Tool の前提条件と設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 12/20/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 948c176c-75ce-418d-891a-a68427d61e40
description: Skype for Business Server 2015 Stress and Performance Tool の前提条件と設定。 Stress and Performance Tool のインストールまたは設定方法。
ms.openlocfilehash: f52d92022e09314a8f9467cd939f67b2827cc153
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816176"
---
# <a name="prerequisites-and-setup-for-the-skype-for-busines-stress-and-performance-tool"></a><span data-ttu-id="34c4d-104">Skype for Busines Stress and Performance Tool の前提条件と設定</span><span class="sxs-lookup"><span data-stu-id="34c4d-104">Prerequisites and setup for the Skype for Busines Stress and Performance Tool</span></span>
 
<span data-ttu-id="34c4d-p102">Skype for Business Server 2015 Stress and Performance Tool の前提条件と設定。 Stress and Performance Tool のインストールまたは設定方法。</span><span class="sxs-lookup"><span data-stu-id="34c4d-p102">Requirements or prerequisites for the Skype for Business Server 2015 Stress and Performance Tool. How to install or setup the Stress and Performance Tool.</span></span>
  
<span data-ttu-id="34c4d-107">Stress and Performance Tool を実行する前に注意する必要のあるハードウェア、ソフトウェア、システム構成の要件について、次のセクションに示します。</span><span class="sxs-lookup"><span data-stu-id="34c4d-107">We have the following sections of hardware, software and system configuration requirements you'll need to be aware of prior to running the Stress and Performance Tool:</span></span>
  
- [<span data-ttu-id="34c4d-108">クライアントのハードウェア要件</span><span class="sxs-lookup"><span data-stu-id="34c4d-108">Client hardware requirements</span></span>](prerequisites-and-setup.md#ClientHardwareReqs)
    
- [<span data-ttu-id="34c4d-109">クライアントのソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="34c4d-109">Client software requirements</span></span>](prerequisites-and-setup.md#ClientSoftwareReqs)
    
- [<span data-ttu-id="34c4d-110">構成要件</span><span class="sxs-lookup"><span data-stu-id="34c4d-110">Configuration requirements</span></span>](prerequisites-and-setup.md#ConfigReqs)
    
<span data-ttu-id="34c4d-111">さらに、後述のセクションで [Skype for Business Server 2015 Stress and Performance Tool のインストール](prerequisites-and-setup.md#Installing)についても説明します。</span><span class="sxs-lookup"><span data-stu-id="34c4d-111">Additionally, we also have a section below for [Installing the Skype for Business Server 2015 Stress and Performance Tool](prerequisites-and-setup.md#Installing)</span></span>
  
## <a name="client-hardware-requirements"></a><span data-ttu-id="34c4d-112">クライアントのハードウェア要件</span><span class="sxs-lookup"><span data-stu-id="34c4d-112">Client hardware requirements</span></span>
<span data-ttu-id="34c4d-113"><a name="ClientHardwareReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="34c4d-113"><a name="ClientHardwareReqs"> </a></span></span>

<span data-ttu-id="34c4d-114">Skype for Business Server 2015 の展開で Stress and Performance Tool を実行する場合、少なくとも、テスト内の 4500 人のユーザーに対して次のハードウェア要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="34c4d-114">When running the Stress and Performance Tool against your Skype for Business Server 2015 deployment, you'll, at a minimum, need these hardware requirements met for every 4500 users in your test:</span></span>
  
- <span data-ttu-id="34c4d-115">1 ギガビットのネットワーク アダプター</span><span class="sxs-lookup"><span data-stu-id="34c4d-115">1 gigabit network adapter</span></span>
    
- <span data-ttu-id="34c4d-116">8 GB RAM</span><span class="sxs-lookup"><span data-stu-id="34c4d-116">8 GB RAM</span></span>
    
- <span data-ttu-id="34c4d-117">2 基のデュアルコア CPU</span><span class="sxs-lookup"><span data-stu-id="34c4d-117">2 dual-core CPUs</span></span>
    
## <a name="client-software-requirements"></a><span data-ttu-id="34c4d-118">クライアントのソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="34c4d-118">Client software requirements</span></span>
<span data-ttu-id="34c4d-119"><a name="ClientSoftwareReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="34c4d-119"><a name="ClientSoftwareReqs"> </a></span></span>

<span data-ttu-id="34c4d-120">Stress and Performance Tool のサポートされるオペレーティング システムは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="34c4d-120">The supported operating systems for the Stress and Performance Tool are:</span></span>
  
- <span data-ttu-id="34c4d-121">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="34c4d-121">Windows Server 2012</span></span>
    
- <span data-ttu-id="34c4d-122">Windows Server 2008 (64 ビット)</span><span class="sxs-lookup"><span data-stu-id="34c4d-122">Windows Server 2008 (64-bit)</span></span>
    
<span data-ttu-id="34c4d-123">これに加え、コンピューターは次のソフトウェア要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="34c4d-123">Additionally, computers need to meet the following software requirements:</span></span>
  
- <span data-ttu-id="34c4d-124">Microsoft .NET 4.5 Framework がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="34c4d-124">You'll need the Microsoft .NET 4.5 Framework installed.</span></span> [<span data-ttu-id="34c4d-125">.Net 4.5 フレームワークをダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="34c4d-125">Download the .Net 4.5 Framework here.</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=30653)
    
- <span data-ttu-id="34c4d-126">Windows でデスクトップ エクスペリエンス機能を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="34c4d-126">You'll need the Desktop Experience feature enabled in Windows.</span></span>
    
- <span data-ttu-id="34c4d-127">Microsoft Visual C++ 2013 (x64) がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="34c4d-127">You'll need Microsoft Visual C++ 2013 (x64) installed.</span></span> [<span data-ttu-id="34c4d-128">Visual C++ 2013 のダウンロード</span><span class="sxs-lookup"><span data-stu-id="34c4d-128">Download Visual C++ 2013 here</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=40784)
    
- <span data-ttu-id="34c4d-129">正常に展開された Skype for Business Server 2015 が必要になります。</span><span class="sxs-lookup"><span data-stu-id="34c4d-129">You're going to need Skype for Business Server 2015 successfully deployed.</span></span>
    
## <a name="configuration-requirements"></a><span data-ttu-id="34c4d-130">構成要件</span><span class="sxs-lookup"><span data-stu-id="34c4d-130">Configuration requirements</span></span>
<span data-ttu-id="34c4d-131"><a name="ConfigReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="34c4d-131"><a name="ConfigReqs"> </a></span></span>

<span data-ttu-id="34c4d-132">Stress and Performance Tool を正常に実行するには、次に示す追加の構成が必要となります。</span><span class="sxs-lookup"><span data-stu-id="34c4d-132">You'll need these additional configurations done to run the Stress and Performance Tool successfully:</span></span>
  
- <span data-ttu-id="34c4d-133">ドメインまたはローカル管理者グループのメンバーとしてサーバーにログインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="34c4d-133">You need to log into the server as a member of the Domain or Local Administrator's group.</span></span>
    
- <span data-ttu-id="34c4d-134">ユーザー アカウントが存在するいかなるフロント エンド サーバーまたは Standard Edition サーバーにも Skype for Business Server 2015 User Creation Tool (UserProvisioningTool.exe) をインストールすることはできません。</span><span class="sxs-lookup"><span data-stu-id="34c4d-134">You can't install the Skype for Business Server 2015 User Creation tool (UserProvisioningTool.exe) on any Front End Server or Standard Edition server where the user accounts will reside.</span></span>
    
- <span data-ttu-id="34c4d-135">User Creation Tool が複数回実行される場合、Microsoft Unified Communications を使用できるユーザーは各自ユニークな電話番号を所有する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34c4d-135">When the User Creation tool is run multiple times, each user who's enabled for Microsoft Unified Communications needs to have a unique phone number.</span></span>
    
- <span data-ttu-id="34c4d-136">ページのファイル サイズはシステムにより管理されるか、最小でもコンピューター システム内の RAM の容量の 1.5 倍である必要があります。</span><span class="sxs-lookup"><span data-stu-id="34c4d-136">The page file size should be systems-managed, or otherwise needs to be at least 1.5 times the amount of RAM in the computer system.</span></span>
    
## <a name="installing-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="34c4d-137">Skype for Business Server 2015 Stress and Performance Tool のインストール</span><span class="sxs-lookup"><span data-stu-id="34c4d-137">Installing the Skype for Business Server 2015 Stress and Performance Tool</span></span>
<span data-ttu-id="34c4d-138"><a name="Installing"> </a></span><span class="sxs-lookup"><span data-stu-id="34c4d-138"><a name="Installing"> </a></span></span>

<span data-ttu-id="34c4d-p105">インストールはとても簡単です。 Windows のインストーラー ファイル、**CapacityPlanningTool.msi** を、ユーザー トラフィックのシミュレートのために使用する各クライアント コンピューターで、およびユーザーと連絡先を作成する各プール内のフロントエンド サーバーで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34c4d-p105">Installing couldn't be simpler. You need to run the Windows Installer file, **CapacityPlanningTool.msi**, on each client computer you're going to use to simulate user traffic, and on a Front End Server in each pool where you'll create users and contacts.</span></span>
  
<span data-ttu-id="34c4d-141">.Msi をダウンロードするには、他の記事で説明されているサンプルスクリプトと共に、「 [Skype For Business Server 2015、ストレスおよびパフォーマンスツール」](https://www.microsoft.com/download/details.aspx?id=50367)のダウンロードセンターへのリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="34c4d-141">To download the .msi, along with the sample scripts mentioned in our other articles, go to the Download Center link: [Skype for Business Server 2015, Stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367).</span></span>
  

