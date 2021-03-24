---
title: Microsoft Teams 会議室の Windows 更新プログラムを管理する
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
description: Microsoft Teams 会議室の Windows 更新プログラムを管理する
ms.openlocfilehash: cb3007acd31f84cedb8996f440b9634f0551f638
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103203"
---
# <a name="manage-windows-updates"></a><span data-ttu-id="32903-103">Windows 更新プログラムの管理</span><span class="sxs-lookup"><span data-stu-id="32903-103">Manage Windows Updates</span></span>

<span data-ttu-id="32903-104">Microsoft Teams Rooms は、Windows 10 Enterprise IoT または Windows 10 Enterprise (VL) で実行され、標準デスクトップと同じ Windows 更新プログラムと OS ビルドを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="32903-104">Microsoft Teams Rooms runs on Windows 10 Enterprise IoT or Windows 10 Enterprise (VL) and receives the same Windows Updates and OS builds as a standard desktop.</span></span>

<span data-ttu-id="32903-105">Windows の更新プログラムは、次に示すいくつかの方法で管理できます。</span><span class="sxs-lookup"><span data-stu-id="32903-105">Windows Updates can be managed in a few different ways:</span></span>

## <a name="hands-off-approach"></a><span data-ttu-id="32903-106">ハンズオフのアプローチ</span><span class="sxs-lookup"><span data-stu-id="32903-106">Hands-off approach</span></span> 
- <span data-ttu-id="32903-107">更新プログラムは、Windows の更新プログラムから直接自動的にダウンロードし、オフ時間にインストールできます。</span><span class="sxs-lookup"><span data-stu-id="32903-107">Updates can be downloaded directly from Windows Updates automatically and installed during off-hours.</span></span> <span data-ttu-id="32903-108">構成に変更が行われた場合、これは既定の状態です。</span><span class="sxs-lookup"><span data-stu-id="32903-108">If no change is made to configuration this is the default state.</span></span>
- <span data-ttu-id="32903-109">遅延不可の更新プログラムは、リリースの 1 日目を自動的にインストールします。</span><span class="sxs-lookup"><span data-stu-id="32903-109">Non-deferrable Updates will install day-one of release automatically.</span></span> 
- <span data-ttu-id="32903-110">品質更新プログラムとドライバーは、1 日目を自動的にダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="32903-110">Quality Updates and drivers will download and install day-one automatically.</span></span> 
- <span data-ttu-id="32903-111">機能更新。</span><span class="sxs-lookup"><span data-stu-id="32903-111">Feature Updates.</span></span> <span data-ttu-id="32903-112">以下のその他のメモを参照してください。</span><span class="sxs-lookup"><span data-stu-id="32903-112">See additional notes below.</span></span> 

## <a name="windows-updates-for-business-gpo-or-intune"></a><span data-ttu-id="32903-113">[Windows Updates for Business](/windows/deployment/update/waas-manage-updates-wufb) (GPO または Intune)</span><span class="sxs-lookup"><span data-stu-id="32903-113">[Windows Updates for Business](/windows/deployment/update/waas-manage-updates-wufb) (GPO or Intune)</span></span>   
- <span data-ttu-id="32903-114">更新プログラムは WU または WSUS からダウンロードされますが、KB の元のリリース日を過ぎた遅延が構成されています。</span><span class="sxs-lookup"><span data-stu-id="32903-114">Updates are downloaded from WU or your WSUS but with configured delays past the KB’s original release date.</span></span> 
- <span data-ttu-id="32903-115">複数の OU またはフィルター処理されたポリシーと組み合わせると、展開 "リング" を作成できます。これにより、管理者は最初に品質更新プログラムをインストールするデバイスと、後でインストールするデバイスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="32903-115">Combined with multiple OU’s or filtered policies, this allows for the creation of deployment “rings”, where administrators can specify which devices install Quality Updates first and which ones will install later.</span></span> <span data-ttu-id="32903-116">これにより、たとえば Microsoft Endpoint Configuration Manager で Windows 更新プログラムを管理するオーバーヘッドなしに、展開全体で更新プログラムを展開する前に、システムのサブセットで信頼性とパフォーマンステストを行えます。</span><span class="sxs-lookup"><span data-stu-id="32903-116">This allows for reliability and performance testing on a subset of systems before rolling out updates across the entire deployment without the overhead of managing Windows Updates in Microsoft Endpoint Configuration Manager for example.</span></span>
- <span data-ttu-id="32903-117">帯域幅管理と Windows Updates for [](/windows/deployment/update/waas-integrate-wufb) Business が提供するコントロールの両方が必要な場合は、WSUS と Windows Updates for Business を同時に構成できます。</span><span class="sxs-lookup"><span data-stu-id="32903-117">WSUS and Windows Updates for Business can be [configured at the same time](/windows/deployment/update/waas-integrate-wufb) if you desire both bandwidth management and the control Windows Updates for Business provides.</span></span>
- <span data-ttu-id="32903-118">機能の更新。</span><span class="sxs-lookup"><span data-stu-id="32903-118">Feature updates.</span></span> <span data-ttu-id="32903-119">以下のその他のメモを参照してください。</span><span class="sxs-lookup"><span data-stu-id="32903-119">See additional notes below.</span></span>

## <a name="wsusconfiguration-manager"></a>[<span data-ttu-id="32903-120">WSUS/Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="32903-120">WSUS/Configuration Manager</span></span>](/windows/deployment/update/waas-manage-updates-configuration-manager)
- <span data-ttu-id="32903-121">Windows Update for Business と同様ですが、各 "リング" または展開全体の中で特定の KB をターゲットに設定するオプションが追加されています。</span><span class="sxs-lookup"><span data-stu-id="32903-121">Much like Windows Update for Business, but with the additional option of targeting specific KB's within each "ring" or the entire deployment.</span></span> <span data-ttu-id="32903-122">各更新プログラムは、遅延だけに依存するのではなく、個別に展開およびテストできます。</span><span class="sxs-lookup"><span data-stu-id="32903-122">Each Update can be individually deployed and tested at will, rather than relying on only a delay.</span></span> 
- <span data-ttu-id="32903-123">機能の更新。</span><span class="sxs-lookup"><span data-stu-id="32903-123">Feature updates.</span></span> <span data-ttu-id="32903-124">以下のその他のメモを参照してください。</span><span class="sxs-lookup"><span data-stu-id="32903-124">See additional notes below.</span></span>


### <a name="feature-updates"></a><span data-ttu-id="32903-125">機能の更新プログラム</span><span class="sxs-lookup"><span data-stu-id="32903-125">Feature updates</span></span>

<span data-ttu-id="32903-126">品質および延期不可の更新プログラムとは異なり、Windows 10 の "機能更新プログラム" (主要な OS リリース) は、Microsoft Teams Rooms で特定の更新プログラムの機能をテストして検証した後にのみインストールされます。</span><span class="sxs-lookup"><span data-stu-id="32903-126">Unlike Quality and Non-Deferable updates, Windows 10 "Feature Updates" (major OS releases) will only be installed after Microsoft tests and validates a given updates functionality with Microsoft Teams Rooms.</span></span> <span data-ttu-id="32903-127">Semi-Annual チャネル (またはテスト用にシステムが設定されている場合はターゲット) にリリースされた場合や、独自の試行または構成によって手動でプッシュされた場合でも、エンド のブロックが削除されるまでインストールは許可されません。</span><span class="sxs-lookup"><span data-stu-id="32903-127">Even if it is released to the Semi-Annual Channel (or Targeted if you have systems set to that channel for testing) or even manually pushed by your own attempts or configurations, it will not allow the installation until the block on our end is removed.</span></span>

<span data-ttu-id="32903-128">Microsoft Teams Room "アウトオブボックス" は、ハンズオフアプローチを使用して、Windows Update をインストールしたり、Windows Update のためにデバイスを自動的に再起動したりしません。</span><span class="sxs-lookup"><span data-stu-id="32903-128">Microsoft Teams Room "out-of-box", using the hands off approach, will not install a Windows Update or reboot a device automatically because of a Windows Update.</span></span> <span data-ttu-id="32903-129">ただし、システムは更新プログラムをダウンロードし、次回の再起動がインストールされるのを待つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="32903-129">Systems may, however, download an update and wait for the next reboot to install it.</span></span> <span data-ttu-id="32903-130">誰かが手動で再起動しない限り、インストールは自動夜間再起動で行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="32903-130">Unless someone reboots it manually, installation should happen at the automatic nightly reboot.</span></span> <span data-ttu-id="32903-131">Windows の更新プログラムは、ルーム内で透過的である必要があります。UI は Windows 更新プログラムによって中断される必要があります。</span><span class="sxs-lookup"><span data-stu-id="32903-131">Windows Updates should be transparent in the room, the UI should never be interrupted by Windows Updates.</span></span>

<span data-ttu-id="32903-132">ドメインへの参加を選択した場合は、Microsoft Endpoint Configuration Manager または WSUS を使用し、デバイスが更新プログラムをインストールしたり、営業時間内に再起動を行う可能性があるポリシーやアクションに特に注意してください。</span><span class="sxs-lookup"><span data-stu-id="32903-132">If you choose to domain join, use Microsoft Endpoint Configuration Manager or WSUS, and please pay special attention to policies or actions that may result in the device installing an update or forcing a reboot during business hours.</span></span> <span data-ttu-id="32903-133">UI を使用して Windows 更新プログラムに関する警告を表示したり、使用中にシステムを再起動している場合は、構成を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="32903-133">If you have systems in your deployment rebooting during use or alerting about Windows Updates over the UI, you will want to look into your configuration.</span></span>