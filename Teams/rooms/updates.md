---
title: 更新プログラムWindows管理Microsoft Teams ミーティング
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.assetid: ''
description: 管理者は、更新プログラムを管理し、Windows更新プログラムWindows更新プログラムを管理する方法についてMicrosoft Teams ミーティング。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c7bb233ceedadeaf9c7f14ddf831bd9d324d9211
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117365"
---
# <a name="manage-windows-updates"></a><span data-ttu-id="dec81-103">更新プログラムWindows管理する</span><span class="sxs-lookup"><span data-stu-id="dec81-103">Manage Windows Updates</span></span>

<span data-ttu-id="dec81-104">Microsoft Teams ミーティング IoT または Windows 10 Enterprise Windows 10 Enterprise (VL) で実行され、標準のデスクトップ コンピューターと同じ Windows 更新プログラムと OS ビルドを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="dec81-104">Microsoft Teams Rooms runs on Windows 10 Enterprise IoT or Windows 10 Enterprise (VL) and receives the same Windows Updates and OS builds as a standard desktop computer.</span></span>

<span data-ttu-id="dec81-105">Windows更新プログラムは、次のセクションで説明したように管理できます。</span><span class="sxs-lookup"><span data-stu-id="dec81-105">Windows Updates can be managed as discussed in the following sections:</span></span>

## <a name="hands-off-approach"></a><span data-ttu-id="dec81-106">ハンズオフアプローチ</span><span class="sxs-lookup"><span data-stu-id="dec81-106">Hands-off approach</span></span> 

- <span data-ttu-id="dec81-107">既定では、更新プログラムは、Windowsから直接ダウンロードされ、時間外にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="dec81-107">By default, updates are downloaded directly from Windows Updates automatically and installed during off-hours.</span></span>
- <span data-ttu-id="dec81-108">遅延不可の更新プログラムは、1 日目のリリースを自動的にインストールします。</span><span class="sxs-lookup"><span data-stu-id="dec81-108">Non-deferrable Updates install day-one of release automatically.</span></span>
- <span data-ttu-id="dec81-109">品質更新プログラムとドライバーは、1 日目を自動的にダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="dec81-109">Quality Updates and drivers download and install day-one automatically.</span></span>
- <span data-ttu-id="dec81-110">機能の更新。</span><span class="sxs-lookup"><span data-stu-id="dec81-110">Feature Updates.</span></span> <span data-ttu-id="dec81-111">次のノートを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dec81-111">See the notes that follow.</span></span>

## <a name="windows-updates-for-business-gpo-or-intune"></a><span data-ttu-id="dec81-112">Windowsビジネス向け更新プログラム (GPO または Intune)</span><span class="sxs-lookup"><span data-stu-id="dec81-112">Windows Updates for Business (GPO or Intune)</span></span>  

- <span data-ttu-id="dec81-113">[Windows for Business の更新プログラムの](/windows/deployment/update/waas-manage-updates-wufb)ダウンロード</span><span class="sxs-lookup"><span data-stu-id="dec81-113">[Windows Updates for Business](/windows/deployment/update/waas-manage-updates-wufb) download</span></span>
- <span data-ttu-id="dec81-114">更新プログラムは更新プログラムWindows WSUS からダウンロードされますが、元のリリース日を過ぎた遅延が構成されています。</span><span class="sxs-lookup"><span data-stu-id="dec81-114">Updates are downloaded from Windows Update or your WSUS but with configured delays past the original release date.</span></span>
- <span data-ttu-id="dec81-115">複数の OUs またはフィルター処理されたポリシーを使用してデプロイ "リング" を作成できます。この場合、管理者は、品質更新プログラムを最初にインストールするデバイスと、後でインストールするデバイスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="dec81-115">You can use multiple OUs or filtered policies to create deployment "rings" where administrators can specify which devices install Quality Updates first and which ones install later.</span></span> <span data-ttu-id="dec81-116">信頼性とパフォーマンスは、Configuration Manager で Windows 更新プログラムを管理するオーバーヘッドなしに、デプロイ全体に更新プログラムを展開する前に、一部のシステムでテストできます。</span><span class="sxs-lookup"><span data-stu-id="dec81-116">Reliability and performance can be tested on a subset of systems before rolling out updates across the entire deployment without the overhead of managing Windows Updates in Configuration Manager.</span></span>
- <span data-ttu-id="dec81-117">WSUS と Windows for Business の[](/windows/deployment/update/waas-integrate-wufb)更新プログラムは、帯域幅管理とビジネス向け更新プログラムの制御の両方が必要な場合Windows同時に構成できます。</span><span class="sxs-lookup"><span data-stu-id="dec81-117">WSUS and Windows Updates for Business can be [configured at the same time](/windows/deployment/update/waas-integrate-wufb) if you desire both the bandwidth management and the control Windows Updates for Business provides.</span></span>
- <span data-ttu-id="dec81-118">機能の更新。</span><span class="sxs-lookup"><span data-stu-id="dec81-118">Feature updates.</span></span> <span data-ttu-id="dec81-119">次のノートを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dec81-119">See the notes that follow.</span></span>

## <a name="wsusconfiguration-manager"></a><span data-ttu-id="dec81-120">WSUS/構成マネージャー</span><span class="sxs-lookup"><span data-stu-id="dec81-120">WSUS/Configuration Manager</span></span>

- <span data-ttu-id="dec81-121">[WSUS/Configuration Manager の](/windows/deployment/update/waas-manage-updates-configuration-manager) ダウンロード</span><span class="sxs-lookup"><span data-stu-id="dec81-121">[WSUS/Configuration Manager](/windows/deployment/update/waas-manage-updates-configuration-manager) download</span></span>
- <span data-ttu-id="dec81-122">ビジネス向Windows更新プログラムと同様ですが、各 "リング" またはデプロイ全体内の特定の KB を対象とする追加オプションがあります。</span><span class="sxs-lookup"><span data-stu-id="dec81-122">Much like Windows Update for Business, but with the additional option of targeting specific KB's within each "ring" or the entire deployment.</span></span> <span data-ttu-id="dec81-123">各更新プログラムは、遅延だけに依存するのではなく、個別にデプロイおよびテストできます。</span><span class="sxs-lookup"><span data-stu-id="dec81-123">Each Update can be individually deployed and tested at will, rather than relying on only a delay.</span></span>
- <span data-ttu-id="dec81-124">機能の更新。</span><span class="sxs-lookup"><span data-stu-id="dec81-124">Feature updates.</span></span> <span data-ttu-id="dec81-125">次のノートを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dec81-125">See the notes that follow.</span></span>

### <a name="feature-updates"></a><span data-ttu-id="dec81-126">機能の更新</span><span class="sxs-lookup"><span data-stu-id="dec81-126">Feature updates</span></span>

<span data-ttu-id="dec81-127">品質および遅延不可の更新プログラムとは異なり、Windows 10 "機能更新プログラム" (メジャー OS リリース) は、Microsoft が Microsoft Teams ミーティング で特定の更新プログラム機能をテストして検証した後にのみインストールされます。</span><span class="sxs-lookup"><span data-stu-id="dec81-127">Unlike Quality and Non-Deferrable updates, Windows 10 "Feature Updates" (major OS releases) will only be installed after Microsoft tests and validates a given updates functionality with Microsoft Teams Rooms.</span></span> <span data-ttu-id="dec81-128">更新プログラムが Semi-Annual チャネルにリリースされた場合 (またはテスト用にシステムがチャネルに設定されている場合は対象指定済み) または手動でプッシュされた場合でも、Microsoft Room Systems デバイスはテストされていない更新プログラムのインストールを許可されません。</span><span class="sxs-lookup"><span data-stu-id="dec81-128">Even if the update is released to the Semi-Annual Channel (or Targeted if you have systems set to that channel for testing) or manually pushed, a Microsoft Room Systems device won't allow the untested update to install.</span></span>

<span data-ttu-id="dec81-129">Microsoft Teams ミーティングはハンズオフアプローチで "アウトオブボックス" 機能を提供し、Windows Update をインストールしたり、Windows Update のデバイスを自動的に再起動したりしません。</span><span class="sxs-lookup"><span data-stu-id="dec81-129">Microsoft Teams Rooms functions "out-of-box" with a hands-off approach, and will not install a Windows Update or reboot a device automatically for a Windows Update.</span></span> <span data-ttu-id="dec81-130">システムは更新プログラムをダウンロードし、次回の再起動がインストールされるのを待ちます。</span><span class="sxs-lookup"><span data-stu-id="dec81-130">Systems download an update and wait for the next reboot to install it.</span></span> <span data-ttu-id="dec81-131">誰かが手動で再起動しない限り、インストールは夜間の自動再起動時にのみ行います。</span><span class="sxs-lookup"><span data-stu-id="dec81-131">Unless someone reboots it manually, installation only happens at the automatic nightly reboot.</span></span> <span data-ttu-id="dec81-132">Windows更新はルーム内で透過的に行う必要があります。また、通常の操作が更新プログラムによって中断Windows必要があります。</span><span class="sxs-lookup"><span data-stu-id="dec81-132">Windows Updates should be transparent in the room, and normal operation should never be interrupted by Windows Updates.</span></span>

<span data-ttu-id="dec81-133">ドメイン参加デバイスを選択する場合は、Microsoft Endpoint Configuration Manager または WSUS を使用します。</span><span class="sxs-lookup"><span data-stu-id="dec81-133">If you choose to domain join devices, use Microsoft Endpoint Configuration Manager or WSUS.</span></span> <span data-ttu-id="dec81-134">営業時間内にデバイスの更新または強制再起動が発生するポリシーまたはアクションに特に注意してください。</span><span class="sxs-lookup"><span data-stu-id="dec81-134">Pay special attention to policies or actions that result in a device update or forced reboot during business hours.</span></span> <span data-ttu-id="dec81-135">デプロイ内のシステムは、使用中に再起動したり、使用時間中に UI Windows 更新プログラムに関するアラートを送信したりし、その動作が発生した場合は構成を確認してください。</span><span class="sxs-lookup"><span data-stu-id="dec81-135">Systems in your deployment should not reboot during use or alert about Windows Updates over the UI during usage hours, review your configuration if that behavior happens.</span></span>