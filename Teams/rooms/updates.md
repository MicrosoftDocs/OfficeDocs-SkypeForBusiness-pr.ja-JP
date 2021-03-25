---
title: Microsoft Teams ルームの Windows 更新プログラムを管理する
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
description: 管理者は、Microsoft Teams ルームの Windows 更新プログラムと Windows の機能更新プログラムを管理する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c7bb233ceedadeaf9c7f14ddf831bd9d324d9211
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117365"
---
# <a name="manage-windows-updates"></a><span data-ttu-id="77088-103">Windows 更新プログラムを管理する</span><span class="sxs-lookup"><span data-stu-id="77088-103">Manage Windows Updates</span></span>

<span data-ttu-id="77088-104">Microsoft Teams Rooms は、Windows 10 Enterprise IoT または Windows 10 Enterprise (VL) で実行され、標準デスクトップ コンピューターと同じ Windows 更新プログラムと OS ビルドを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="77088-104">Microsoft Teams Rooms runs on Windows 10 Enterprise IoT or Windows 10 Enterprise (VL) and receives the same Windows Updates and OS builds as a standard desktop computer.</span></span>

<span data-ttu-id="77088-105">Windows 更新プログラムは、次のセクションで説明したように管理できます。</span><span class="sxs-lookup"><span data-stu-id="77088-105">Windows Updates can be managed as discussed in the following sections:</span></span>

## <a name="hands-off-approach"></a><span data-ttu-id="77088-106">ハンズオフ アプローチ</span><span class="sxs-lookup"><span data-stu-id="77088-106">Hands-off approach</span></span> 

- <span data-ttu-id="77088-107">既定では、更新プログラムは Windows 更新プログラムから直接自動的にダウンロードされ、営業時間外にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="77088-107">By default, updates are downloaded directly from Windows Updates automatically and installed during off-hours.</span></span>
- <span data-ttu-id="77088-108">遅延提供不可の更新プログラムは、リリースの 1 日目に自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="77088-108">Non-deferrable Updates install day-one of release automatically.</span></span>
- <span data-ttu-id="77088-109">品質更新プログラムとドライバーは、1 日目を自動的にダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="77088-109">Quality Updates and drivers download and install day-one automatically.</span></span>
- <span data-ttu-id="77088-110">機能の更新。</span><span class="sxs-lookup"><span data-stu-id="77088-110">Feature Updates.</span></span> <span data-ttu-id="77088-111">次のノートを参照してください。</span><span class="sxs-lookup"><span data-stu-id="77088-111">See the notes that follow.</span></span>

## <a name="windows-updates-for-business-gpo-or-intune"></a><span data-ttu-id="77088-112">ビジネス向け Windows 更新プログラム (GPO または Intune)</span><span class="sxs-lookup"><span data-stu-id="77088-112">Windows Updates for Business (GPO or Intune)</span></span>  

- <span data-ttu-id="77088-113">[ビジネス向け Windows 更新プログラムの](/windows/deployment/update/waas-manage-updates-wufb) ダウンロード</span><span class="sxs-lookup"><span data-stu-id="77088-113">[Windows Updates for Business](/windows/deployment/update/waas-manage-updates-wufb) download</span></span>
- <span data-ttu-id="77088-114">更新プログラムは Windows Update または WSUS からダウンロードされますが、元のリリース日を過ぎた遅延が構成されています。</span><span class="sxs-lookup"><span data-stu-id="77088-114">Updates are downloaded from Windows Update or your WSUS but with configured delays past the original release date.</span></span>
- <span data-ttu-id="77088-115">複数の OUs またはフィルター処理されたポリシーを使用して展開 "リング" を作成できます。このリングでは、最初に品質更新プログラムをインストールするデバイスと、後でインストールするデバイスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="77088-115">You can use multiple OUs or filtered policies to create deployment "rings" where administrators can specify which devices install Quality Updates first and which ones install later.</span></span> <span data-ttu-id="77088-116">Configuration Manager で Windows 更新プログラムを管理するオーバーヘッドなしで、展開全体に更新プログラムを展開する前に、システムのサブセットで信頼性とパフォーマンスをテストできます。</span><span class="sxs-lookup"><span data-stu-id="77088-116">Reliability and performance can be tested on a subset of systems before rolling out updates across the entire deployment without the overhead of managing Windows Updates in Configuration Manager.</span></span>
- <span data-ttu-id="77088-117">帯域幅管理とビジネス向け Windows [](/windows/deployment/update/waas-integrate-wufb) Updates の制御の両方が必要な場合は、WSUS と Windows Updates for Business を同時に構成できます。</span><span class="sxs-lookup"><span data-stu-id="77088-117">WSUS and Windows Updates for Business can be [configured at the same time](/windows/deployment/update/waas-integrate-wufb) if you desire both the bandwidth management and the control Windows Updates for Business provides.</span></span>
- <span data-ttu-id="77088-118">機能の更新。</span><span class="sxs-lookup"><span data-stu-id="77088-118">Feature updates.</span></span> <span data-ttu-id="77088-119">次のノートを参照してください。</span><span class="sxs-lookup"><span data-stu-id="77088-119">See the notes that follow.</span></span>

## <a name="wsusconfiguration-manager"></a><span data-ttu-id="77088-120">WSUS/Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="77088-120">WSUS/Configuration Manager</span></span>

- <span data-ttu-id="77088-121">[WSUS/Configuration Manager の](/windows/deployment/update/waas-manage-updates-configuration-manager) ダウンロード</span><span class="sxs-lookup"><span data-stu-id="77088-121">[WSUS/Configuration Manager](/windows/deployment/update/waas-manage-updates-configuration-manager) download</span></span>
- <span data-ttu-id="77088-122">Windows Update for Business と同様ですが、各 "リング" 内または展開全体内の特定の KB を対象とする追加オプションがあります。</span><span class="sxs-lookup"><span data-stu-id="77088-122">Much like Windows Update for Business, but with the additional option of targeting specific KB's within each "ring" or the entire deployment.</span></span> <span data-ttu-id="77088-123">各更新プログラムは、遅延だけに依存するのではなく、個別に展開およびテストすることができます。</span><span class="sxs-lookup"><span data-stu-id="77088-123">Each Update can be individually deployed and tested at will, rather than relying on only a delay.</span></span>
- <span data-ttu-id="77088-124">機能の更新。</span><span class="sxs-lookup"><span data-stu-id="77088-124">Feature updates.</span></span> <span data-ttu-id="77088-125">次のノートを参照してください。</span><span class="sxs-lookup"><span data-stu-id="77088-125">See the notes that follow.</span></span>

### <a name="feature-updates"></a><span data-ttu-id="77088-126">機能の更新</span><span class="sxs-lookup"><span data-stu-id="77088-126">Feature updates</span></span>

<span data-ttu-id="77088-127">品質および非延期更新プログラムとは異なり、Windows 10 の "機能更新プログラム" (メジャー OS リリース) は、Microsoft Teams Rooms で特定の更新プログラム機能をテストして検証した後にのみインストールされます。</span><span class="sxs-lookup"><span data-stu-id="77088-127">Unlike Quality and Non-Deferrable updates, Windows 10 "Feature Updates" (major OS releases) will only be installed after Microsoft tests and validates a given updates functionality with Microsoft Teams Rooms.</span></span> <span data-ttu-id="77088-128">更新プログラムが Semi-Annual チャネルにリリースされた場合 (またはテスト用にシステムをそのチャネルに設定している場合は対象指定済み) または手動でプッシュされた場合でも、Microsoft Room Systems デバイスでは、テストされていない更新プログラムのインストールは許可されません。</span><span class="sxs-lookup"><span data-stu-id="77088-128">Even if the update is released to the Semi-Annual Channel (or Targeted if you have systems set to that channel for testing) or manually pushed, a Microsoft Room Systems device won't allow the untested update to install.</span></span>

<span data-ttu-id="77088-129">Microsoft Teams Rooms は、ハンズオフ アプローチで "アウト オブ ボックス" 機能し、Windows Update をインストールしたり、Windows Update のデバイスを自動的に再起動したりしません。</span><span class="sxs-lookup"><span data-stu-id="77088-129">Microsoft Teams Rooms functions "out-of-box" with a hands-off approach, and will not install a Windows Update or reboot a device automatically for a Windows Update.</span></span> <span data-ttu-id="77088-130">システムは更新プログラムをダウンロードし、次に再起動してインストールされるのを待ちます。</span><span class="sxs-lookup"><span data-stu-id="77088-130">Systems download an update and wait for the next reboot to install it.</span></span> <span data-ttu-id="77088-131">手動で再起動しない限り、インストールは夜間自動再起動でのみ実行されます。</span><span class="sxs-lookup"><span data-stu-id="77088-131">Unless someone reboots it manually, installation only happens at the automatic nightly reboot.</span></span> <span data-ttu-id="77088-132">Windows 更新プログラムはルーム内で透明にする必要があります。また、Windows 更新プログラムによって通常の操作が中断されるのは絶対にありません。</span><span class="sxs-lookup"><span data-stu-id="77088-132">Windows Updates should be transparent in the room, and normal operation should never be interrupted by Windows Updates.</span></span>

<span data-ttu-id="77088-133">ドメイン参加デバイスを選ぶ場合は、Microsoft Endpoint Configuration Manager または WSUS を使用します。</span><span class="sxs-lookup"><span data-stu-id="77088-133">If you choose to domain join devices, use Microsoft Endpoint Configuration Manager or WSUS.</span></span> <span data-ttu-id="77088-134">営業時間内にデバイスが更新または強制的に再起動されるポリシーやアクションには特に注意してください。</span><span class="sxs-lookup"><span data-stu-id="77088-134">Pay special attention to policies or actions that result in a device update or forced reboot during business hours.</span></span> <span data-ttu-id="77088-135">使用時間中に展開内のシステムを再起動したり、UI を使用して Windows 更新プログラムに関する警告を表示したりし、その動作が発生した場合は構成を確認してください。</span><span class="sxs-lookup"><span data-stu-id="77088-135">Systems in your deployment should not reboot during use or alert about Windows Updates over the UI during usage hours, review your configuration if that behavior happens.</span></span>