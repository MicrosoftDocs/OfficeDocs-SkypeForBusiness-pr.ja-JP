---
title: Microsoft Teams ルームの Windows 更新プログラムを管理する
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
ms.date: 10/10/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: M365-voice
ms.assetid: ''
description: Microsoft Teams ルームの Windows 更新プログラムを管理する
ms.openlocfilehash: 346747d3d5731f5b4504c45066a39a28f5289e70
ms.sourcegitcommit: ed3a6789dedf54275e0b1ab41d4a4230eed6eb72
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/30/2020
ms.locfileid: "41628683"
---
# <a name="manage-windows-updates"></a><span data-ttu-id="328b9-103">Windows の更新プログラムを管理する</span><span class="sxs-lookup"><span data-stu-id="328b9-103">Manage Windows Updates</span></span>

<span data-ttu-id="328b9-104">Microsoft Teams の会議は、Windows 10 Enterprise IoT または Windows 10 Enterprise (VL) で実行され、標準デスクトップと同じ Windows 更新プログラムと OS ビルドを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="328b9-104">Microsoft Teams Rooms runs on Windows 10 Enterprise IoT or Windows 10 Enterprise (VL) and receives the same Windows Updates and OS builds as a standard desktop.</span></span>

<span data-ttu-id="328b9-105">Windows 更新プログラムを管理するには、次のような方法があります。</span><span class="sxs-lookup"><span data-stu-id="328b9-105">Windows Updates can be managed in a few different ways:</span></span>

## <a name="hands-off-approach"></a><span data-ttu-id="328b9-106">ハンドオフアプローチ</span><span class="sxs-lookup"><span data-stu-id="328b9-106">Hands-off approach</span></span> 
- <span data-ttu-id="328b9-107">更新プログラムは、Windows 更新プログラムから直接ダウンロードして、業務時間外にインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="328b9-107">Updates can be downloaded directly from Windows Updates automatically and installed during off-hours.</span></span> <span data-ttu-id="328b9-108">構成に変更が行われていない場合は、これが既定の状態になります。</span><span class="sxs-lookup"><span data-stu-id="328b9-108">If no change is made to configuration this is the default state.</span></span>
- <span data-ttu-id="328b9-109">遅延不可の更新プログラムでは、リリースの1日目が自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="328b9-109">Non-deferrable Updates will install day-one of release automatically.</span></span> 
- <span data-ttu-id="328b9-110">品質更新プログラムとドライバーは、1日の予定を自動的にダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="328b9-110">Quality Updates and drivers will download and install day-one automatically.</span></span> 
- <span data-ttu-id="328b9-111">機能の更新。</span><span class="sxs-lookup"><span data-stu-id="328b9-111">Feature Updates.</span></span> <span data-ttu-id="328b9-112">以下の追加のメモを参照してください。</span><span class="sxs-lookup"><span data-stu-id="328b9-112">See additional notes below.</span></span> 

## <a name="windows-updates-for-businesshttpsdocsmicrosoftcomwindowsdeploymentupdatewaas-manage-updates-wufb-gpo-or-intune"></a><span data-ttu-id="328b9-113">[ビジネス向け Windows 更新プログラム](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)(GPO または Intune)</span><span class="sxs-lookup"><span data-stu-id="328b9-113">[Windows Updates for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) (GPO or Intune)</span></span>   
- <span data-ttu-id="328b9-114">更新プログラムは WU または WSUS からダウンロードされますが、KB の最初のリリース日よりも遅延が構成されています。</span><span class="sxs-lookup"><span data-stu-id="328b9-114">Updates are downloaded from WU or your WSUS but with configured delays past the KB’s original release date.</span></span> 
- <span data-ttu-id="328b9-115">複数の OU またはフィルター処理されたポリシーと組み合わせることで、管理者が品質更新プログラムをインストールするデバイスを指定し、後でインストールするデバイスを指定できる展開用の "呼び出し" を作成できます。</span><span class="sxs-lookup"><span data-stu-id="328b9-115">Combined with multiple OU’s or filtered policies, this allows for the creation of deployment “rings”, where administrators can specify which devices install Quality Updates first and which ones will install later.</span></span> <span data-ttu-id="328b9-116">これにより、システムのサブセットに対する信頼性とパフォーマンスのテストが可能になります。これにより、Microsoft Endpoint Configuration Manager での Windows の更新プログラムの管理のオーバーヘッドなしで、展開全体で更新プログラムをロールアウトすることができます。</span><span class="sxs-lookup"><span data-stu-id="328b9-116">This allows for reliability and performance testing on a subset of systems before rolling out updates across the entire deployment without the overhead of managing Windows Updates in Microsoft Endpoint Configuration Manager for example.</span></span>
- <span data-ttu-id="328b9-117">帯域幅の管理と、ビジネス向けの Windows Update の制御の両方が必要な場合は、WSUS と Windows の更新プログラムを同時[に構成](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb)することができます。</span><span class="sxs-lookup"><span data-stu-id="328b9-117">WSUS and Windows Updates for Business can be [configured at the same time](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb) if you desire both bandwidth management and the control Windows Updates for Business provides.</span></span>
- <span data-ttu-id="328b9-118">機能の更新。</span><span class="sxs-lookup"><span data-stu-id="328b9-118">Feature updates.</span></span> <span data-ttu-id="328b9-119">以下の追加のメモを参照してください。</span><span class="sxs-lookup"><span data-stu-id="328b9-119">See additional notes below.</span></span>

## <a name="wsusconfiguration-managerhttpsdocsmicrosoftcomwindowsdeploymentupdatewaas-manage-updates-configuration-manager"></a>[<span data-ttu-id="328b9-120">WSUS/構成マネージャー</span><span class="sxs-lookup"><span data-stu-id="328b9-120">WSUS/Configuration Manager</span></span>](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)
- <span data-ttu-id="328b9-121">一般法人向け Windows Update と同じように、各 "リング" または展開全体で特定の KB をターゲットに設定するための追加オプションがあります。</span><span class="sxs-lookup"><span data-stu-id="328b9-121">Much like Windows Update for Business, but with the additional option of targeting specific KB's within each "ring" or the entire deployment.</span></span> <span data-ttu-id="328b9-122">各更新プログラムは、遅延のみではなく、個別に展開してテストすることができます。</span><span class="sxs-lookup"><span data-stu-id="328b9-122">Each Update can be individually deployed and tested at will, rather than relying on only a delay.</span></span> 
- <span data-ttu-id="328b9-123">機能の更新。</span><span class="sxs-lookup"><span data-stu-id="328b9-123">Feature updates.</span></span> <span data-ttu-id="328b9-124">以下の追加のメモを参照してください。</span><span class="sxs-lookup"><span data-stu-id="328b9-124">See additional notes below.</span></span>


### <a name="feature-updates"></a><span data-ttu-id="328b9-125">機能の更新プログラム</span><span class="sxs-lookup"><span data-stu-id="328b9-125">Feature updates</span></span>

<span data-ttu-id="328b9-126">品質と Deferable 以外の更新プログラムとは異なり、Windows 10 "機能更新プログラム" (メジャー OS リリース) は、Microsoft テストの後にのみインストールされ、Microsoft Teams のルームで特定の更新機能を検証します。</span><span class="sxs-lookup"><span data-stu-id="328b9-126">Unlike Quality and Non-Deferable updates, Windows 10 "Feature Updates" (major OS releases) will only be installed after Microsoft tests and validates a given updates functionality with Microsoft Teams Rooms.</span></span> <span data-ttu-id="328b9-127">半期チャネルにリリースされた場合 (またはテスト用にそのチャネルにシステムを設定している場合)、または独自の試みや構成で手動でプッシュした場合でも、そのエンドのブロックが削除されるまで、インストールは許可されません。</span><span class="sxs-lookup"><span data-stu-id="328b9-127">Even if it is released to the Semi-Annual Channel (or Targeted if you have systems set to that channel for testing) or even manually pushed by your own attempts or configurations, it will not allow the installation until the block on our end is removed.</span></span>

<span data-ttu-id="328b9-128">ハンズオフアプローチを使用した Microsoft Teams Room "box" は、Windows update をインストールしたり、windows update のためにデバイスを自動的に再起動したりすることはありません。</span><span class="sxs-lookup"><span data-stu-id="328b9-128">Microsoft Teams Room "out-of-box", using the hands off approach, will not install a Windows Update or reboot a device automatically because of a Windows Update.</span></span> <span data-ttu-id="328b9-129">ただし、システムによって更新プログラムがダウンロードされ、次に再起動するまで待ってからインストールできる場合があります。</span><span class="sxs-lookup"><span data-stu-id="328b9-129">Systems may, however, download an update and wait for the next reboot to install it.</span></span> <span data-ttu-id="328b9-130">手動で再起動しない限り、自動夜間再起動時にインストールが行われます。</span><span class="sxs-lookup"><span data-stu-id="328b9-130">Unless someone reboots it manually, installation should happen at the automatic nightly reboot.</span></span> <span data-ttu-id="328b9-131">Windows の更新プログラムは、会議室では透過的である必要があります。 UI は Windows 更新プログラムによって中断されることはありません。</span><span class="sxs-lookup"><span data-stu-id="328b9-131">Windows Updates should be transparent in the room, the UI should never be interrupted by Windows Updates.</span></span>

<span data-ttu-id="328b9-132">ドメインへの参加を選択する場合は、Microsoft Endpoint Configuration Manager または WSUS を使用し、デバイスで更新プログラムをインストールしたり、業務時間中に再起動を強制したりするポリシーまたは操作に特に注意を払ってください。</span><span class="sxs-lookup"><span data-stu-id="328b9-132">If you choose to domain join, use Microsoft Endpoint Configuration Manager or WSUS, and please pay special attention to policies or actions that may result in the device installing an update or forcing a reboot during business hours.</span></span> <span data-ttu-id="328b9-133">展開されているシステムが、使用中に、または UI を介した Windows 更新に関する通知中に再起動する場合は、構成を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="328b9-133">If you have systems in your deployment rebooting during use or alerting about Windows Updates over the UI, you will want to look into your configuration.</span></span>
