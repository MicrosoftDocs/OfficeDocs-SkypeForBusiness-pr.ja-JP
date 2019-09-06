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
ms.openlocfilehash: 09be03b0308dfcf00a39421e2e84b75fe94a9fae
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "36775318"
---
# <a name="manage-windows-updates"></a><span data-ttu-id="01754-103">Windows の更新プログラムを管理する</span><span class="sxs-lookup"><span data-stu-id="01754-103">Manage Windows Updates</span></span>

<span data-ttu-id="01754-104">Microsoft Teams の会議は、Windows 10 Enterprise IoT または Windows 10 Enterprise (VL) で実行され、標準デスクトップと同じ Windows 更新プログラムと OS ビルドを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="01754-104">Microsoft Teams Rooms runs on Windows 10 Enterprise IoT or Windows 10 Enterprise (VL) and receives the same Windows Updates and OS builds as a standard desktop.</span></span>

<span data-ttu-id="01754-105">Windows 更新プログラムを管理するには、次のような方法があります。</span><span class="sxs-lookup"><span data-stu-id="01754-105">Windows Updates can be managed in a few different ways:</span></span>

## <a name="hands-off-approach"></a><span data-ttu-id="01754-106">ハンドオフアプローチ</span><span class="sxs-lookup"><span data-stu-id="01754-106">Hands-off approach</span></span> 
- <span data-ttu-id="01754-107">更新プログラムは、Windows 更新プログラムから直接ダウンロードして、業務時間外にインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="01754-107">Updates can be downloaded directly from Windows Updates automatically and installed during off-hours.</span></span> <span data-ttu-id="01754-108">構成に変更が行われていない場合は、これが既定の状態になります。</span><span class="sxs-lookup"><span data-stu-id="01754-108">If no change is made to configuration this is the default state.</span></span>
- <span data-ttu-id="01754-109">遅延不可の更新プログラムでは、リリースの1日目が自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="01754-109">Non-deferrable Updates will install day-one of release automatically.</span></span> 
- <span data-ttu-id="01754-110">品質更新プログラムとドライバーは、1日の予定を自動的にダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="01754-110">Quality Updates and drivers will download and install day-one automatically.</span></span> 
- <span data-ttu-id="01754-111">機能の更新。</span><span class="sxs-lookup"><span data-stu-id="01754-111">Feature Updates.</span></span> <span data-ttu-id="01754-112">以下の追加のメモを参照してください。</span><span class="sxs-lookup"><span data-stu-id="01754-112">See additional notes below.</span></span> 

## <a name="windows-updates-for-businesshttpsdocsmicrosoftcomwindowsdeploymentupdatewaas-manage-updates-wufb-gpo-or-intune"></a><span data-ttu-id="01754-113">一般[法人向け Windows 更新プログラム](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)(GPO または Intune)</span><span class="sxs-lookup"><span data-stu-id="01754-113">[Windows Updates for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) (GPO or Intune)</span></span>   
- <span data-ttu-id="01754-114">更新プログラムは WU または WSUS からダウンロードされますが、KB の最初のリリース日よりも遅延が構成されています。</span><span class="sxs-lookup"><span data-stu-id="01754-114">Updates are downloaded from WU or your WSUS but with configured delays past the KB’s original release date.</span></span> 
- <span data-ttu-id="01754-115">複数の OU またはフィルター処理されたポリシーと組み合わせることで、管理者が品質更新プログラムをインストールするデバイスを指定し、後でインストールするデバイスを指定できる展開用の "呼び出し" を作成できます。</span><span class="sxs-lookup"><span data-stu-id="01754-115">Combined with multiple OU’s or filtered policies, this allows for the creation of deployment “rings”, where administrators can specify which devices install Quality Updates first and which ones will install later.</span></span> <span data-ttu-id="01754-116">これにより、システムのサブセットに対する信頼性とパフォーマンスのテストを行うことができます。これにより、SCCM での Windows の更新プログラムの管理に伴うオーバーヘッドを生じることなく、展開全体で更新プログラムをロールアウトすることができます。</span><span class="sxs-lookup"><span data-stu-id="01754-116">This allows for reliability and performance testing on a subset of systems before rolling out updates across the entire deployment without the overhead of managing Windows Updates in SCCM for example.</span></span>
- <span data-ttu-id="01754-117">帯域幅の管理と、ビジネス向けの Windows Update の制御の両方が必要な場合は、WSUS と Windows の更新プログラムを同時[に構成](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb)することができます。</span><span class="sxs-lookup"><span data-stu-id="01754-117">WSUS and Windows Updates for Business can be [configured at the same time](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb) if you desire both bandwidth management and the control Windows Updates for Business provides.</span></span>
- <span data-ttu-id="01754-118">機能の更新。</span><span class="sxs-lookup"><span data-stu-id="01754-118">Feature updates.</span></span> <span data-ttu-id="01754-119">以下の追加のメモを参照してください。</span><span class="sxs-lookup"><span data-stu-id="01754-119">See additional notes below.</span></span>

## <a name="wsussccmhttpsdocsmicrosoftcomwindowsdeploymentupdatewaas-manage-updates-configuration-manager"></a>[<span data-ttu-id="01754-120">WSUS/SCCM</span><span class="sxs-lookup"><span data-stu-id="01754-120">WSUS/SCCM</span></span>](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)
- <span data-ttu-id="01754-121">一般法人向け Windows Update と同じように、各 "リング" または展開全体で特定の KB をターゲットに設定するための追加オプションがあります。</span><span class="sxs-lookup"><span data-stu-id="01754-121">Much like Windows Update for Business, but with the additional option of targeting specific KB's within each "ring" or the entire deployment.</span></span> <span data-ttu-id="01754-122">各更新プログラムは、遅延のみではなく、個別に展開してテストすることができます。</span><span class="sxs-lookup"><span data-stu-id="01754-122">Each Update can be individually deployed and tested at will, rather than relying on only a delay.</span></span> 
- <span data-ttu-id="01754-123">機能の更新。</span><span class="sxs-lookup"><span data-stu-id="01754-123">Feature updates.</span></span> <span data-ttu-id="01754-124">以下の追加のメモを参照してください。</span><span class="sxs-lookup"><span data-stu-id="01754-124">See additional notes below.</span></span>


### <a name="feature-updates"></a><span data-ttu-id="01754-125">機能の更新プログラム</span><span class="sxs-lookup"><span data-stu-id="01754-125">Feature updates</span></span>

<span data-ttu-id="01754-126">品質と Deferable 以外の更新プログラムとは異なり、Windows 10 "機能更新プログラム" (メジャー OS リリース) は、Microsoft テストの後にのみインストールされ、Microsoft Teams のルームで特定の更新機能を検証します。</span><span class="sxs-lookup"><span data-stu-id="01754-126">Unlike Quality and Non-Deferable updates, Windows 10 "Feature Updates" (major OS releases) will only be installed after Microsoft tests and validates a given updates functionality with Microsoft Teams Rooms.</span></span> <span data-ttu-id="01754-127">半期チャネルにリリースされた場合 (またはテスト用にそのチャネルにシステムを設定している場合)、または独自の試みや構成で手動でプッシュした場合でも、そのエンドのブロックが削除されるまで、インストールは許可されません。</span><span class="sxs-lookup"><span data-stu-id="01754-127">Even if it is released to the Semi-Annual Channel (or Targeted if you have systems set to that channel for testing) or even manually pushed by your own attempts or configurations, it will not allow the installation until the block on our end is removed.</span></span>

<span data-ttu-id="01754-128">ハンズオフアプローチを使用した Microsoft Teams Room "box" は、Windows update をインストールしたり、windows update のためにデバイスを自動的に再起動したりすることはありません。</span><span class="sxs-lookup"><span data-stu-id="01754-128">Microsoft Teams Room "out-of-box", using the hands off approach, will not install a Windows Update or reboot a device automatically because of a Windows Update.</span></span> <span data-ttu-id="01754-129">ただし、システムによって更新プログラムがダウンロードされ、次に再起動するまで待ってからインストールできる場合があります。</span><span class="sxs-lookup"><span data-stu-id="01754-129">Systems may, however, download an update and wait for the next reboot to install it.</span></span> <span data-ttu-id="01754-130">手動で再起動しない限り、自動夜間再起動時にインストールが行われます。</span><span class="sxs-lookup"><span data-stu-id="01754-130">Unless someone reboots it manually, installation should happen at the automatic nightly reboot.</span></span> <span data-ttu-id="01754-131">Windows の更新プログラムは、会議室では透過的である必要があります。 UI は Windows 更新プログラムによって中断されることはありません。</span><span class="sxs-lookup"><span data-stu-id="01754-131">Windows Updates should be transparent in the room, the UI should never be interrupted by Windows Updates.</span></span>

<span data-ttu-id="01754-132">ドメイン参加を選択する場合は、SCCM または WSUS を使用し、デバイスで更新プログラムをインストールしたり、業務時間中に再起動を強制したりする可能性のあるポリシーまたは操作に特に注意してください。</span><span class="sxs-lookup"><span data-stu-id="01754-132">If you choose to domain join, use SCCM or WSUS, and please pay special attention to policies or actions that may result in the device installing an update or forcing a reboot during business hours.</span></span> <span data-ttu-id="01754-133">展開されているシステムが、使用中に、または UI を介した Windows 更新に関する通知中に再起動する場合は、構成を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="01754-133">If you have systems in your deployment rebooting during use or alerting about Windows Updates over the UI, you will want to look into your configuration.</span></span>
