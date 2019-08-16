---
title: Microsoft Teams ルームの Windows 更新プログラムを管理する
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 10/10/2018
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
ms.collection: M365-voice
ms.assetid: ''
description: Microsoft Teams ルームの Windows 更新プログラムを管理する
ms.openlocfilehash: 842831875d3654e5b1d75cdd936d8cc1a6ddf540
ms.sourcegitcommit: 1401ee484a2bc8e72d96649b0571bb59198f9dab
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2019
ms.locfileid: "36427711"
---
# <a name="manage-windows-updates"></a><span data-ttu-id="8361e-103">Windows の更新プログラムを管理する</span><span class="sxs-lookup"><span data-stu-id="8361e-103">Manage Windows Updates</span></span>

<span data-ttu-id="8361e-104">Microsoft Teams の会議は、Windows 10 Enterprise IoT または Windows 10 Enterprise (VL) で実行され、標準デスクトップと同じ Windows 更新プログラムと OS ビルドを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="8361e-104">Microsoft Teams Rooms runs on Windows 10 Enterprise IoT or Windows 10 Enterprise (VL) and receives the same Windows Updates and OS builds as a standard desktop.</span></span>

<span data-ttu-id="8361e-105">Windows 更新プログラムを管理するには、次のような方法があります。</span><span class="sxs-lookup"><span data-stu-id="8361e-105">Windows Updates can be managed in a few different ways:</span></span>

## <a name="hands-off-approach"></a><span data-ttu-id="8361e-106">ハンドオフアプローチ</span><span class="sxs-lookup"><span data-stu-id="8361e-106">Hands-off approach</span></span> 

- <span data-ttu-id="8361e-107">更新プログラムは、Windows 更新プログラムから直接ダウンロードして、業務時間外にインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="8361e-107">Updates can be downloaded directly from Windows Updates automatically and installed during off-hours.</span></span> <span data-ttu-id="8361e-108">これは既定の構成です。</span><span class="sxs-lookup"><span data-stu-id="8361e-108">This is the default configuration.</span></span>
- <span data-ttu-id="8361e-109">無遅延更新プログラムによって、リリース日が自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="8361e-109">Non-deferrable Updates install day-one of release automatically.</span></span>
- <span data-ttu-id="8361e-110">品質更新プログラムとドライバーのダウンロードとインストールが自動的に行われます。</span><span class="sxs-lookup"><span data-stu-id="8361e-110">Quality Updates and drivers download and install day-one automatically.</span></span>
- <span data-ttu-id="8361e-111">機能の更新。</span><span class="sxs-lookup"><span data-stu-id="8361e-111">Feature Updates.</span></span> <span data-ttu-id="8361e-112">以下のメモを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8361e-112">See the notes that follow.</span></span>

## <a name="windows-updates-for-business-gpo-or-intune"></a><span data-ttu-id="8361e-113">ビジネス向け Windows 更新プログラム (GPO または Intune)</span><span class="sxs-lookup"><span data-stu-id="8361e-113">Windows Updates for Business (GPO or Intune)</span></span>  

- <span data-ttu-id="8361e-114">一般[法人向けダウンロード用の Windows 更新プログラム](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)</span><span class="sxs-lookup"><span data-stu-id="8361e-114">[Windows Updates for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) download</span></span>
- <span data-ttu-id="8361e-115">更新プログラムは WU または WSUS からダウンロードされますが、KB の最初のリリース日よりも遅延が構成されています。</span><span class="sxs-lookup"><span data-stu-id="8361e-115">Updates are downloaded from WU or your WSUS but with configured delays past the KB’s original release date.</span></span>
- <span data-ttu-id="8361e-116">複数の OU またはフィルター処理されたポリシーと共に使用することで、管理者が品質更新プログラムをインストールするデバイスを指定し、後でインストールすることを指定できます。</span><span class="sxs-lookup"><span data-stu-id="8361e-116">Used with multiple OU’s or filtered policies, you can create deployment “rings” where administrators can specify which devices install Quality Updates first and which ones install later.</span></span> <span data-ttu-id="8361e-117">これにより、システムのサブセットに対する信頼性とパフォーマンスのテストを行うことができます。これにより、SCCM での Windows の更新プログラムの管理に伴うオーバーヘッドを生じることなく、展開全体で更新プログラムをロールアウトすることができます。</span><span class="sxs-lookup"><span data-stu-id="8361e-117">This allows for reliability and performance testing on a subset of systems before rolling out updates across the entire deployment without the overhead of managing Windows Updates in SCCM for example.</span></span>
- <span data-ttu-id="8361e-118">ビジネス向けの帯域幅管理と Windows Update の制御の両方が必要な場合は、WSUS と Windows の更新プログラムを同時[に構成](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb)することができます。</span><span class="sxs-lookup"><span data-stu-id="8361e-118">WSUS and Windows Updates for Business can be [configured at the same time](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb) if you desire both the bandwidth management and the control Windows Updates for Business provides.</span></span>
- <span data-ttu-id="8361e-119">機能の更新。</span><span class="sxs-lookup"><span data-stu-id="8361e-119">Feature updates.</span></span> <span data-ttu-id="8361e-120">以下のメモを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8361e-120">See the notes that follow.</span></span>

## <a name="wsussccm"></a><span data-ttu-id="8361e-121">WSUS/SCCM</span><span class="sxs-lookup"><span data-stu-id="8361e-121">WSUS/SCCM</span></span>

- <span data-ttu-id="8361e-122">[WSUS/SCCM](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)のダウンロード</span><span class="sxs-lookup"><span data-stu-id="8361e-122">[WSUS/SCCM](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager) download</span></span>
- <span data-ttu-id="8361e-123">一般法人向け Windows Update と同じように、各 "リング" または展開全体で特定の KB をターゲットに設定するための追加オプションがあります。</span><span class="sxs-lookup"><span data-stu-id="8361e-123">Much like Windows Update for Business, but with the additional option of targeting specific KB's within each "ring" or the entire deployment.</span></span> <span data-ttu-id="8361e-124">各更新プログラムは、遅延のみではなく、個別に展開してテストすることができます。</span><span class="sxs-lookup"><span data-stu-id="8361e-124">Each Update can be individually deployed and tested at will, rather than relying on only a delay.</span></span>
- <span data-ttu-id="8361e-125">機能の更新。</span><span class="sxs-lookup"><span data-stu-id="8361e-125">Feature updates.</span></span> <span data-ttu-id="8361e-126">以下のメモを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8361e-126">See the notes that follow.</span></span>

### <a name="feature-updates"></a><span data-ttu-id="8361e-127">機能の更新プログラム</span><span class="sxs-lookup"><span data-stu-id="8361e-127">Feature updates</span></span>

<span data-ttu-id="8361e-128">品質と不確認可能な更新プログラムとは異なり、Windows 10 "機能更新プログラム" (メジャー OS リリース) は、Microsoft テストの後にのみインストールされ、Microsoft Teams のルームで特定の更新機能を検証します。</span><span class="sxs-lookup"><span data-stu-id="8361e-128">Unlike Quality and Non-Deferrable updates, Windows 10 "Feature Updates" (major OS releases) will only be installed after Microsoft tests and validates a given updates functionality with Microsoft Teams Rooms.</span></span> <span data-ttu-id="8361e-129">半期チャネルに更新プログラムがリリースされている場合 (またはテスト用にシステムを設定している場合)、または手動でプッシュした場合でも、Microsoft Room Systems デバイスでは、テストされていない更新プログラムをインストールすることはできません。</span><span class="sxs-lookup"><span data-stu-id="8361e-129">Even if the update is released to the Semi-Annual Channel (or Targeted if you have systems set to that channel for testing) or manually pushed, a Microsoft Room Systems device won't allow the untested update to install.</span></span>

<span data-ttu-id="8361e-130">ハンズオフアプローチを使用した Microsoft Teams の会議室では、windows update をインストールしたり、Windows Update 用のデバイスを自動的に再起動したりすることはありません。</span><span class="sxs-lookup"><span data-stu-id="8361e-130">Microsoft Teams Rooms "out-of-box", using the hands off approach, will not install a Windows Update or reboot a device automatically for a Windows Update.</span></span> <span data-ttu-id="8361e-131">システムによって更新プログラムがダウンロードされ、次に再起動するまで待機してからインストールされることがあります。</span><span class="sxs-lookup"><span data-stu-id="8361e-131">Systems may download an update and wait for the next reboot to install it.</span></span> <span data-ttu-id="8361e-132">手動で再起動しない限り、自動夜間再起動時にインストールが行われます。</span><span class="sxs-lookup"><span data-stu-id="8361e-132">Unless someone reboots it manually, installation should happen at the automatic nightly reboot.</span></span> <span data-ttu-id="8361e-133">Windows の更新プログラムは、会議室では透過的である必要があります。 UI は Windows 更新プログラムによって中断されることはありません。</span><span class="sxs-lookup"><span data-stu-id="8361e-133">Windows Updates should be transparent in the room, the UI should never be interrupted by Windows Updates.</span></span>

<span data-ttu-id="8361e-134">ドメインに参加しているデバイスを選択する場合は、SCCM または WSUS を使用します。</span><span class="sxs-lookup"><span data-stu-id="8361e-134">If you choose to domain joined devices, use SCCM or WSUS.</span></span> <span data-ttu-id="8361e-135">デバイスで更新プログラムをインストールしたり、業務時間中に再起動を強制したりする可能性のあるポリシーまたはアクションには、特別な注意を払ってください。</span><span class="sxs-lookup"><span data-stu-id="8361e-135">Pay special attention to policies or actions that may result in the device installing an update or forcing a reboot during business hours.</span></span> <span data-ttu-id="8361e-136">展開内のシステムは使用中に再起動しないようにする必要があります。または、使用時間中に UI を介した Windows 更新についての通知で、動作が発生した場合は構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="8361e-136">Systems in your deployment should not reboot during use or alert about Windows Updates over the UI during usage hours, review your configuration if that behavior happens.</span></span>