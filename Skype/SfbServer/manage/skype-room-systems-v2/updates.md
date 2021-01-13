---
title: Microsoft Teams ルームの Windows 更新プログラムを管理する
ms.author: v-cichur
author: cichur
ms.reviewer: sohailta
manager: serdars
ms.date: 10/10/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: M365-voice
ms.assetid: ''
description: Microsoft Teams ルームの Windows 更新プログラムを管理する
ms.openlocfilehash: 4f7fd6d49c78b229a3909e88689423dc95ce2c48
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832877"
---
# <a name="manage-windows-updates"></a><span data-ttu-id="c31cc-103">Windows 更新プログラムの管理</span><span class="sxs-lookup"><span data-stu-id="c31cc-103">Manage Windows Updates</span></span>

<span data-ttu-id="c31cc-104">Microsoft Teams Rooms は、Windows 10 Enterprise IoT または Windows 10 Enterprise (VL) で実行され、標準デスクトップと同じ Windows 更新プログラムと OS ビルドを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="c31cc-104">Microsoft Teams Rooms runs on Windows 10 Enterprise IoT or Windows 10 Enterprise (VL) and receives the same Windows Updates and OS builds as a standard desktop.</span></span>

<span data-ttu-id="c31cc-105">Windows 更新プログラムは、いくつかの異なる方法で管理できます。</span><span class="sxs-lookup"><span data-stu-id="c31cc-105">Windows Updates can be managed in a few different ways:</span></span>

## <a name="hands-off-approach"></a><span data-ttu-id="c31cc-106">ハンズオフアプローチ</span><span class="sxs-lookup"><span data-stu-id="c31cc-106">Hands-off approach</span></span> 
- <span data-ttu-id="c31cc-107">更新プログラムは、Windows 更新プログラムから直接自動的にダウンロードし、オフ時間にインストールできます。</span><span class="sxs-lookup"><span data-stu-id="c31cc-107">Updates can be downloaded directly from Windows Updates automatically and installed during off-hours.</span></span> <span data-ttu-id="c31cc-108">構成に変更が行われた場合、これは既定の状態です。</span><span class="sxs-lookup"><span data-stu-id="c31cc-108">If no change is made to configuration this is the default state.</span></span>
- <span data-ttu-id="c31cc-109">延期不可の更新プログラムは、リリースの 1 日目を自動的にインストールします。</span><span class="sxs-lookup"><span data-stu-id="c31cc-109">Non-deferrable Updates will install day-one of release automatically.</span></span> 
- <span data-ttu-id="c31cc-110">品質更新プログラムとドライバーは、1 日目を自動的にダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="c31cc-110">Quality Updates and drivers will download and install day-one automatically.</span></span> 
- <span data-ttu-id="c31cc-111">機能更新。</span><span class="sxs-lookup"><span data-stu-id="c31cc-111">Feature Updates.</span></span> <span data-ttu-id="c31cc-112">以下の追加のメモを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c31cc-112">See additional notes below.</span></span> 

## <a name="windows-updates-for-business-gpo-or-intune"></a><span data-ttu-id="c31cc-113">[Windows Updates for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) (GPO または Intune)</span><span class="sxs-lookup"><span data-stu-id="c31cc-113">[Windows Updates for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) (GPO or Intune)</span></span>   
- <span data-ttu-id="c31cc-114">更新プログラムは WU または WSUS からダウンロードされますが、KB の元のリリース日を過ぎた遅延が構成されています。</span><span class="sxs-lookup"><span data-stu-id="c31cc-114">Updates are downloaded from WU or your WSUS but with configured delays past the KB’s original release date.</span></span> 
- <span data-ttu-id="c31cc-115">複数の OU またはフィルター処理されたポリシーと組み合わせると、展開 "リング" を作成できます。このリングでは、管理者は、最初に品質更新プログラムをインストールするデバイスと、後でインストールするデバイスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="c31cc-115">Combined with multiple OU’s or filtered policies, this allows for the creation of deployment “rings”, where administrators can specify which devices install Quality Updates first and which ones will install later.</span></span> <span data-ttu-id="c31cc-116">これにより、Microsoft Endpoint Configuration Manager で Windows 更新プログラムを管理するオーバーヘッドを発生することなく、展開全体で更新プログラムを展開する前に、システムのサブセットで信頼性とパフォーマンスをテストできます。</span><span class="sxs-lookup"><span data-stu-id="c31cc-116">This allows for reliability and performance testing on a subset of systems before rolling out updates across the entire deployment without the overhead of managing Windows Updates in Microsoft Endpoint Configuration Manager for example.</span></span>
- <span data-ttu-id="c31cc-117">帯域幅管理と Windows Updates for [](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb) Business の制御の両方が必要な場合は、WSUS と Windows Updates for Business を同時に構成できます。</span><span class="sxs-lookup"><span data-stu-id="c31cc-117">WSUS and Windows Updates for Business can be [configured at the same time](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb) if you desire both bandwidth management and the control Windows Updates for Business provides.</span></span>
- <span data-ttu-id="c31cc-118">機能更新プログラム。</span><span class="sxs-lookup"><span data-stu-id="c31cc-118">Feature updates.</span></span> <span data-ttu-id="c31cc-119">以下の追加のメモを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c31cc-119">See additional notes below.</span></span>

## <a name="wsusconfiguration-manager"></a>[<span data-ttu-id="c31cc-120">WSUS/Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="c31cc-120">WSUS/Configuration Manager</span></span>](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)
- <span data-ttu-id="c31cc-121">Windows Update for Business と同様ですが、各 "リング" 内または展開全体内の特定の KB を対象とする追加オプションがあります。</span><span class="sxs-lookup"><span data-stu-id="c31cc-121">Much like Windows Update for Business, but with the additional option of targeting specific KB's within each "ring" or the entire deployment.</span></span> <span data-ttu-id="c31cc-122">各更新プログラムは、遅延だけに依存するのではなく、個別に展開およびテストできます。</span><span class="sxs-lookup"><span data-stu-id="c31cc-122">Each Update can be individually deployed and tested at will, rather than relying on only a delay.</span></span> 
- <span data-ttu-id="c31cc-123">機能更新プログラム。</span><span class="sxs-lookup"><span data-stu-id="c31cc-123">Feature updates.</span></span> <span data-ttu-id="c31cc-124">以下の追加のメモを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c31cc-124">See additional notes below.</span></span>


### <a name="feature-updates"></a><span data-ttu-id="c31cc-125">機能の更新プログラム</span><span class="sxs-lookup"><span data-stu-id="c31cc-125">Feature updates</span></span>

<span data-ttu-id="c31cc-126">品質更新プログラムや延期不可の更新プログラムとは異なり、Windows 10 の "機能更新プログラム" (メジャー OS リリース) は、Microsoft Teams Rooms で特定の更新プログラム機能をテストして検証した後にのみインストールされます。</span><span class="sxs-lookup"><span data-stu-id="c31cc-126">Unlike Quality and Non-Deferable updates, Windows 10 "Feature Updates" (major OS releases) will only be installed after Microsoft tests and validates a given updates functionality with Microsoft Teams Rooms.</span></span> <span data-ttu-id="c31cc-127">Semi-Annual チャネルにリリースされた場合 (またはテスト用にシステムをそのチャネルに設定している場合は対象指定)、または独自の試行または構成によって手動でプッシュされた場合でも、エンドのブロックが削除されるまでインストールは許可されません。</span><span class="sxs-lookup"><span data-stu-id="c31cc-127">Even if it is released to the Semi-Annual Channel (or Targeted if you have systems set to that channel for testing) or even manually pushed by your own attempts or configurations, it will not allow the installation until the block on our end is removed.</span></span>

<span data-ttu-id="c31cc-128">Microsoft Teams Room "out-of-box"は、ハンズオフ アプローチを使用して、Windows Update をインストールしたり、Windows Update のためにデバイスを自動的に再起動したりしません。</span><span class="sxs-lookup"><span data-stu-id="c31cc-128">Microsoft Teams Room "out-of-box", using the hands off approach, will not install a Windows Update or reboot a device automatically because of a Windows Update.</span></span> <span data-ttu-id="c31cc-129">ただし、システムは更新プログラムをダウンロードし、次回の再起動によってインストールされるのを待つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="c31cc-129">Systems may, however, download an update and wait for the next reboot to install it.</span></span> <span data-ttu-id="c31cc-130">ユーザーが手動で再起動しない限り、インストールは夜間の自動再起動時に行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="c31cc-130">Unless someone reboots it manually, installation should happen at the automatic nightly reboot.</span></span> <span data-ttu-id="c31cc-131">Windows 更新プログラムは、ルーム内で透過的である必要があります。UI は Windows 更新プログラムによって中断されません。</span><span class="sxs-lookup"><span data-stu-id="c31cc-131">Windows Updates should be transparent in the room, the UI should never be interrupted by Windows Updates.</span></span>

<span data-ttu-id="c31cc-132">ドメイン参加を選択する場合は、Microsoft Endpoint Configuration Manager または WSUS を使用し、デバイスで更新プログラムをインストールしたり、業務時間中に再起動を実行したりする可能性があるポリシーやアクションに特に注意してください。</span><span class="sxs-lookup"><span data-stu-id="c31cc-132">If you choose to domain join, use Microsoft Endpoint Configuration Manager or WSUS, and please pay special attention to policies or actions that may result in the device installing an update or forcing a reboot during business hours.</span></span> <span data-ttu-id="c31cc-133">展開内のシステムが、使用中に再起動したり、UI を使用して Windows 更新プログラムに関する警告を表示したりしている場合は、構成を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c31cc-133">If you have systems in your deployment rebooting during use or alerting about Windows Updates over the UI, you will want to look into your configuration.</span></span>
