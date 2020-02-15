---
title: Skype for Busines ストレスおよびパフォーマンスツールの前提条件とセットアップ
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
description: Skype for Business Server 2015 ストレスおよびパフォーマンスツールの要件または前提条件。 ストレスとパフォーマンスツールをインストールまたはセットアップする方法について説明します。
ms.openlocfilehash: 9389feedb21948604b1ea68319c5fc068a561679
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42005982"
---
# <a name="prerequisites-and-setup-for-the-skype-for-busines-stress-and-performance-tool"></a><span data-ttu-id="c2256-104">Skype for Busines ストレスおよびパフォーマンスツールの前提条件とセットアップ</span><span class="sxs-lookup"><span data-stu-id="c2256-104">Prerequisites and setup for the Skype for Busines Stress and Performance Tool</span></span>
 
<span data-ttu-id="c2256-105">Skype for Business Server 2015 ストレスおよびパフォーマンスツールの要件または前提条件。</span><span class="sxs-lookup"><span data-stu-id="c2256-105">Requirements or prerequisites for the Skype for Business Server 2015 Stress and Performance Tool.</span></span> <span data-ttu-id="c2256-106">ストレスとパフォーマンスツールをインストールまたはセットアップする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c2256-106">How to install or setup the Stress and Performance Tool.</span></span>
  
<span data-ttu-id="c2256-107">次のセクションでは、ストレスおよびパフォーマンスツールを実行する前に知っておく必要があるハードウェア、ソフトウェア、およびシステム構成の要件について説明しています。</span><span class="sxs-lookup"><span data-stu-id="c2256-107">We have the following sections of hardware, software and system configuration requirements you'll need to be aware of prior to running the Stress and Performance Tool:</span></span>
  
- [<span data-ttu-id="c2256-108">クライアントハードウェアの要件</span><span class="sxs-lookup"><span data-stu-id="c2256-108">Client hardware requirements</span></span>](prerequisites-and-setup.md#ClientHardwareReqs)
    
- [<span data-ttu-id="c2256-109">クライアントソフトウェアの要件</span><span class="sxs-lookup"><span data-stu-id="c2256-109">Client software requirements</span></span>](prerequisites-and-setup.md#ClientSoftwareReqs)
    
- [<span data-ttu-id="c2256-110">構成要件</span><span class="sxs-lookup"><span data-stu-id="c2256-110">Configuration requirements</span></span>](prerequisites-and-setup.md#ConfigReqs)
    
<span data-ttu-id="c2256-111">また、 [Skype For Business Server 2015 ストレスおよびパフォーマンスツールをインストール](prerequisites-and-setup.md#Installing)するための以下のセクションもあります。</span><span class="sxs-lookup"><span data-stu-id="c2256-111">Additionally, we also have a section below for [Installing the Skype for Business Server 2015 Stress and Performance Tool](prerequisites-and-setup.md#Installing)</span></span>
  
## <a name="client-hardware-requirements"></a><span data-ttu-id="c2256-112">クライアントハードウェアの要件</span><span class="sxs-lookup"><span data-stu-id="c2256-112">Client hardware requirements</span></span>
<span data-ttu-id="c2256-113"><a name="ClientHardwareReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="c2256-113"><a name="ClientHardwareReqs"> </a></span></span>

<span data-ttu-id="c2256-114">Skype for Business Server 2015 展開に対してストレスおよびパフォーマンスツールを実行する場合は、少なくとも、テスト内のすべてのユーザー4500に対してこれらのハードウェア要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2256-114">When running the Stress and Performance Tool against your Skype for Business Server 2015 deployment, you'll, at a minimum, need these hardware requirements met for every 4500 users in your test:</span></span>
  
- <span data-ttu-id="c2256-115">1ギガビットのネットワークアダプター</span><span class="sxs-lookup"><span data-stu-id="c2256-115">1 gigabit network adapter</span></span>
    
- <span data-ttu-id="c2256-116">8 GB RAM</span><span class="sxs-lookup"><span data-stu-id="c2256-116">8 GB RAM</span></span>
    
- <span data-ttu-id="c2256-117">2つのデュアルコア Cpu</span><span class="sxs-lookup"><span data-stu-id="c2256-117">2 dual-core CPUs</span></span>
    
## <a name="client-software-requirements"></a><span data-ttu-id="c2256-118">クライアントソフトウェアの要件</span><span class="sxs-lookup"><span data-stu-id="c2256-118">Client software requirements</span></span>
<span data-ttu-id="c2256-119"><a name="ClientSoftwareReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="c2256-119"><a name="ClientSoftwareReqs"> </a></span></span>

<span data-ttu-id="c2256-120">ストレスおよびパフォーマンスツールでサポートされているオペレーティングシステムは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c2256-120">The supported operating systems for the Stress and Performance Tool are:</span></span>
  
- <span data-ttu-id="c2256-121">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="c2256-121">Windows Server 2012</span></span>
    
- <span data-ttu-id="c2256-122">Windows Server 2008 (64 ビット)</span><span class="sxs-lookup"><span data-stu-id="c2256-122">Windows Server 2008 (64-bit)</span></span>
    
<span data-ttu-id="c2256-123">また、コンピューターは次のソフトウェア要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2256-123">Additionally, computers need to meet the following software requirements:</span></span>
  
- <span data-ttu-id="c2256-124">Microsoft .NET 4.5 Framework がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2256-124">You'll need the Microsoft .NET 4.5 Framework installed.</span></span> [<span data-ttu-id="c2256-125">.Net 4.5 Framework をダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="c2256-125">Download the .Net 4.5 Framework here.</span></span>](https://www.microsoft.com/download/details.aspx?id=30653)
    
- <span data-ttu-id="c2256-126">Windows では、デスクトップ環境の機能を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2256-126">You'll need the Desktop Experience feature enabled in Windows.</span></span>
    
- <span data-ttu-id="c2256-127">Microsoft Visual C++ 2013 (x64) がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2256-127">You'll need Microsoft Visual C++ 2013 (x64) installed.</span></span> [<span data-ttu-id="c2256-128">Visual C++ 2013 をダウンロードする</span><span class="sxs-lookup"><span data-stu-id="c2256-128">Download Visual C++ 2013 here</span></span>](https://www.microsoft.com/download/details.aspx?id=40784)
    
- <span data-ttu-id="c2256-129">Skype for Business Server 2015 が正常に展開されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2256-129">You're going to need Skype for Business Server 2015 successfully deployed.</span></span>
    
## <a name="configuration-requirements"></a><span data-ttu-id="c2256-130">構成要件</span><span class="sxs-lookup"><span data-stu-id="c2256-130">Configuration requirements</span></span>
<span data-ttu-id="c2256-131"><a name="ConfigReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="c2256-131"><a name="ConfigReqs"> </a></span></span>

<span data-ttu-id="c2256-132">ストレスとパフォーマンスツールを正常に実行するには、次の追加の構成が必要になります。</span><span class="sxs-lookup"><span data-stu-id="c2256-132">You'll need these additional configurations done to run the Stress and Performance Tool successfully:</span></span>
  
- <span data-ttu-id="c2256-133">ドメインまたはローカル管理者のグループのメンバーとしてサーバーにログインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2256-133">You need to log into the server as a member of the Domain or Local Administrator's group.</span></span>
    
- <span data-ttu-id="c2256-134">ユーザーアカウントが存在するフロントエンドサーバーまたは Standard Edition サーバーには、Skype for Business Server 2015 ユーザー作成ツール (Usermsiexec.exe Tool) をインストールすることはできません。</span><span class="sxs-lookup"><span data-stu-id="c2256-134">You can't install the Skype for Business Server 2015 User Creation tool (UserProvisioningTool.exe) on any Front End Server or Standard Edition server where the user accounts will reside.</span></span>
    
- <span data-ttu-id="c2256-135">ユーザー作成ツールを複数回実行する場合、Microsoft ユニファイドコミュニケーションが有効になっている各ユーザーは、一意の電話番号を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2256-135">When the User Creation tool is run multiple times, each user who's enabled for Microsoft Unified Communications needs to have a unique phone number.</span></span>
    
- <span data-ttu-id="c2256-136">ページファイルのサイズは、システムによって管理されている必要があります。それ以外の場合は、コンピューターシステムの RAM の容量の少なくとも1.5 倍にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2256-136">The page file size should be systems-managed, or otherwise needs to be at least 1.5 times the amount of RAM in the computer system.</span></span>
    
## <a name="installing-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="c2256-137">Skype for Business Server 2015 ストレスおよびパフォーマンスツールのインストール</span><span class="sxs-lookup"><span data-stu-id="c2256-137">Installing the Skype for Business Server 2015 Stress and Performance Tool</span></span>
<span data-ttu-id="c2256-138"><a name="Installing"> </a></span><span class="sxs-lookup"><span data-stu-id="c2256-138"><a name="Installing"> </a></span></span>

<span data-ttu-id="c2256-139">インストールは簡単に行うことができませんでした。</span><span class="sxs-lookup"><span data-stu-id="c2256-139">Installing couldn't be simpler.</span></span> <span data-ttu-id="c2256-140">ユーザートラフィックをシミュレートするために使用する各クライアントコンピューターで、またはユーザーと連絡先を作成する各プールのフロントエンドサーバーで、Windows インストーラファイル**CapacityPlanningTool**を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2256-140">You need to run the Windows Installer file, **CapacityPlanningTool.msi**, on each client computer you're going to use to simulate user traffic, and on a Front End Server in each pool where you'll create users and contacts.</span></span>
  
<span data-ttu-id="c2256-141">.Msi をダウンロードするには、その他の記事に記載されているサンプルスクリプトを使用して、「 [Skype For Business Server 2015、ストレスおよびパフォーマンスツール](https://www.microsoft.com/download/details.aspx?id=50367)」のダウンロードセンターへのリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2256-141">To download the .msi, along with the sample scripts mentioned in our other articles, go to the Download Center link: [Skype for Business Server 2015, Stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367).</span></span>
  

