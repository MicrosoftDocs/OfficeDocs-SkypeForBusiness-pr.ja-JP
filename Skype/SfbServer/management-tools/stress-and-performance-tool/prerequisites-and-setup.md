---
title: Skype for Busines Stress and Performance Tool の前提条件とセットアップ
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Skype for Business Server 2015 Stress and Performance Tool の要件または前提条件。 Stress and Performance Tool をインストールまたはセットアップする方法。
ms.openlocfilehash: a58eb5e291878bea74365cd1b9519983c7a77a84
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814957"
---
# <a name="prerequisites-and-setup-for-the-skype-for-busines-stress-and-performance-tool"></a><span data-ttu-id="ef2a9-104">Skype for Busines Stress and Performance Tool の前提条件とセットアップ</span><span class="sxs-lookup"><span data-stu-id="ef2a9-104">Prerequisites and setup for the Skype for Busines Stress and Performance Tool</span></span>
 
<span data-ttu-id="ef2a9-105">Skype for Business Server 2015 Stress and Performance Tool の要件または前提条件。</span><span class="sxs-lookup"><span data-stu-id="ef2a9-105">Requirements or prerequisites for the Skype for Business Server 2015 Stress and Performance Tool.</span></span> <span data-ttu-id="ef2a9-106">Stress and Performance Tool をインストールまたはセットアップする方法。</span><span class="sxs-lookup"><span data-stu-id="ef2a9-106">How to install or setup the Stress and Performance Tool.</span></span>
  
<span data-ttu-id="ef2a9-107">Stress and Performance Tool を実行する前に知る必要があるハードウェア、ソフトウェア、およびシステム構成の要件については、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef2a9-107">We have the following sections of hardware, software and system configuration requirements you'll need to be aware of prior to running the Stress and Performance Tool:</span></span>
  
- [<span data-ttu-id="ef2a9-108">クライアントのハードウェア要件</span><span class="sxs-lookup"><span data-stu-id="ef2a9-108">Client hardware requirements</span></span>](prerequisites-and-setup.md#ClientHardwareReqs)
    
- [<span data-ttu-id="ef2a9-109">クライアント ソフトウェアの要件</span><span class="sxs-lookup"><span data-stu-id="ef2a9-109">Client software requirements</span></span>](prerequisites-and-setup.md#ClientSoftwareReqs)
    
- [<span data-ttu-id="ef2a9-110">構成要件</span><span class="sxs-lookup"><span data-stu-id="ef2a9-110">Configuration requirements</span></span>](prerequisites-and-setup.md#ConfigReqs)
    
<span data-ttu-id="ef2a9-111">さらに[、Skype for Business Server 2015 Stress and Performance Tool](prerequisites-and-setup.md#Installing)をインストールするセクションも以下に示します。</span><span class="sxs-lookup"><span data-stu-id="ef2a9-111">Additionally, we also have a section below for [Installing the Skype for Business Server 2015 Stress and Performance Tool](prerequisites-and-setup.md#Installing)</span></span>
  
## <a name="client-hardware-requirements"></a><span data-ttu-id="ef2a9-112">クライアント のハードウェア要件</span><span class="sxs-lookup"><span data-stu-id="ef2a9-112">Client hardware requirements</span></span>
<span data-ttu-id="ef2a9-113"><a name="ClientHardwareReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="ef2a9-113"><a name="ClientHardwareReqs"> </a></span></span>

<span data-ttu-id="ef2a9-114">Skype for Business Server 2015 展開に対して Stress and Performance Tool を実行する場合、少なくとも、テストで 4500 ユーザーごとにこれらのハードウェア要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef2a9-114">When running the Stress and Performance Tool against your Skype for Business Server 2015 deployment, you'll, at a minimum, need these hardware requirements met for every 4500 users in your test:</span></span>
  
- <span data-ttu-id="ef2a9-115">1 ギガビット ネットワーク アダプター</span><span class="sxs-lookup"><span data-stu-id="ef2a9-115">1 gigabit network adapter</span></span>
    
- <span data-ttu-id="ef2a9-116">8 GB RAM</span><span class="sxs-lookup"><span data-stu-id="ef2a9-116">8 GB RAM</span></span>
    
- <span data-ttu-id="ef2a9-117">デュアルコア CPU 2 台</span><span class="sxs-lookup"><span data-stu-id="ef2a9-117">2 dual-core CPUs</span></span>
    
## <a name="client-software-requirements"></a><span data-ttu-id="ef2a9-118">クライアント ソフトウェアの要件</span><span class="sxs-lookup"><span data-stu-id="ef2a9-118">Client software requirements</span></span>
<span data-ttu-id="ef2a9-119"><a name="ClientSoftwareReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="ef2a9-119"><a name="ClientSoftwareReqs"> </a></span></span>

<span data-ttu-id="ef2a9-120">Stress and Performance Tool でサポートされているオペレーティング システムは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ef2a9-120">The supported operating systems for the Stress and Performance Tool are:</span></span>
  
- <span data-ttu-id="ef2a9-121">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="ef2a9-121">Windows Server 2012</span></span>
    
- <span data-ttu-id="ef2a9-122">Windows Server 2008 (64 ビット)</span><span class="sxs-lookup"><span data-stu-id="ef2a9-122">Windows Server 2008 (64-bit)</span></span>
    
<span data-ttu-id="ef2a9-123">さらに、コンピューターは次のソフトウェア要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef2a9-123">Additionally, computers need to meet the following software requirements:</span></span>
  
- <span data-ttu-id="ef2a9-124">Microsoft .NET 4.5 Framework がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef2a9-124">You'll need the Microsoft .NET 4.5 Framework installed.</span></span> [<span data-ttu-id="ef2a9-125">ここに .Net 4.5 Framework をダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="ef2a9-125">Download the .Net 4.5 Framework here.</span></span>](https://www.microsoft.com/download/details.aspx?id=30653)
    
- <span data-ttu-id="ef2a9-126">Windows でデスクトップ エクスペリエンス機能を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef2a9-126">You'll need the Desktop Experience feature enabled in Windows.</span></span>
    
- <span data-ttu-id="ef2a9-127">Microsoft Visual C++ 2013 (x64) がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef2a9-127">You'll need Microsoft Visual C++ 2013 (x64) installed.</span></span> [<span data-ttu-id="ef2a9-128">Visual C++ 2013 をここからダウンロードする</span><span class="sxs-lookup"><span data-stu-id="ef2a9-128">Download Visual C++ 2013 here</span></span>](https://www.microsoft.com/download/details.aspx?id=40784)
    
- <span data-ttu-id="ef2a9-129">Skype for Business Server 2015 が正常に展開されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef2a9-129">You're going to need Skype for Business Server 2015 successfully deployed.</span></span>
    
## <a name="configuration-requirements"></a><span data-ttu-id="ef2a9-130">構成要件</span><span class="sxs-lookup"><span data-stu-id="ef2a9-130">Configuration requirements</span></span>
<span data-ttu-id="ef2a9-131"><a name="ConfigReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="ef2a9-131"><a name="ConfigReqs"> </a></span></span>

<span data-ttu-id="ef2a9-132">Stress and Performance Tool を正常に実行するには、次の追加構成が必要です。</span><span class="sxs-lookup"><span data-stu-id="ef2a9-132">You'll need these additional configurations done to run the Stress and Performance Tool successfully:</span></span>
  
- <span data-ttu-id="ef2a9-133">ドメインまたはローカル管理者のグループのメンバーとしてサーバーにログインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef2a9-133">You need to log into the server as a member of the Domain or Local Administrator's group.</span></span>
    
- <span data-ttu-id="ef2a9-134">Skype for Business Server 2015 ユーザー作成ツール (UserProvisioningTool.exe) は、ユーザー アカウントが存在するフロントエンド サーバーまたは Standard Edition サーバーにはインストールできません。</span><span class="sxs-lookup"><span data-stu-id="ef2a9-134">You can't install the Skype for Business Server 2015 User Creation tool (UserProvisioningTool.exe) on any Front End Server or Standard Edition server where the user accounts will reside.</span></span>
    
- <span data-ttu-id="ef2a9-135">ユーザー作成ツールを複数回実行する場合は、Microsoft Unified Communications が有効になっている各ユーザーに一意の電話番号が必要です。</span><span class="sxs-lookup"><span data-stu-id="ef2a9-135">When the User Creation tool is run multiple times, each user who's enabled for Microsoft Unified Communications needs to have a unique phone number.</span></span>
    
- <span data-ttu-id="ef2a9-136">ページ ファイルのサイズはシステムで管理する必要があります。それ以外の場合は、コンピューター システムの RAM の容量の 1.5 倍以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef2a9-136">The page file size should be systems-managed, or otherwise needs to be at least 1.5 times the amount of RAM in the computer system.</span></span>
    
## <a name="installing-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="ef2a9-137">Skype for Business Server 2015 Stress and Performance Tool のインストール</span><span class="sxs-lookup"><span data-stu-id="ef2a9-137">Installing the Skype for Business Server 2015 Stress and Performance Tool</span></span>
<span data-ttu-id="ef2a9-138"><a name="Installing"> </a></span><span class="sxs-lookup"><span data-stu-id="ef2a9-138"><a name="Installing"> </a></span></span>

<span data-ttu-id="ef2a9-139">インストールを簡単に行う必要が生じなかった。</span><span class="sxs-lookup"><span data-stu-id="ef2a9-139">Installing couldn't be simpler.</span></span> <span data-ttu-id="ef2a9-140">Windows インストーラー ファイル **CapacityPlanningTool.msi** を、ユーザー トラフィックのシミュレートに使用する各クライアント コンピューターで実行し、ユーザーと連絡先を作成する各プールのフロント エンド サーバーで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef2a9-140">You need to run the Windows Installer file, **CapacityPlanningTool.msi**, on each client computer you're going to use to simulate user traffic, and on a Front End Server in each pool where you'll create users and contacts.</span></span>
  
<span data-ttu-id="ef2a9-141">.msi を、他の記事で説明されているサンプル スクリプトと共にダウンロードするには、ダウンロード センターのリンク [(Skype for Business Server 2015、Stress and Performance Tool)](https://www.microsoft.com/download/details.aspx?id=50367)に移動します。</span><span class="sxs-lookup"><span data-stu-id="ef2a9-141">To download the .msi, along with the sample scripts mentioned in our other articles, go to the Download Center link: [Skype for Business Server 2015, Stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367).</span></span>
  

