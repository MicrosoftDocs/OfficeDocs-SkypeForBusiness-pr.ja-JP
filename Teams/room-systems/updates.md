---
title: Microsoft Teams ルームの Windows 更新プログラムを管理する
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
ms.date: 10/10/2018
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.assetid: ''
description: Microsoft Teams ルームの Windows 更新プログラムを管理する
ms.openlocfilehash: 5f0942efc1b503589412a1de6852d83e42a3b03e
ms.sourcegitcommit: 70bf1669442bbb50cb293c86d6a0c80fb3b2b55a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/16/2019
ms.locfileid: "38675421"
---
# <a name="manage-windows-updates"></a><span data-ttu-id="e47eb-103">Windows の更新プログラムを管理する</span><span class="sxs-lookup"><span data-stu-id="e47eb-103">Manage Windows Updates</span></span>

<span data-ttu-id="e47eb-104">Microsoft Teams のルームは、Windows 10 Enterprise IoT または Windows 10 Enterprise (VL) で実行され、標準のデスクトップコンピューターと同じ Windows 更新プログラムと OS ビルドを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="e47eb-104">Microsoft Teams Rooms runs on Windows 10 Enterprise IoT or Windows 10 Enterprise (VL) and receives the same Windows Updates and OS builds as a standard desktop computer.</span></span>

<span data-ttu-id="e47eb-105">Windows 更新プログラムは、次のセクションで説明するように管理できます。</span><span class="sxs-lookup"><span data-stu-id="e47eb-105">Windows Updates can be managed as discussed in the following sections:</span></span>

## <a name="hands-off-approach"></a><span data-ttu-id="e47eb-106">ハンドオフアプローチ</span><span class="sxs-lookup"><span data-stu-id="e47eb-106">Hands-off approach</span></span> 

- <span data-ttu-id="e47eb-107">既定では、更新プログラムは Windows 更新プログラムから自動的にダウンロードされ、オフ時間中にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="e47eb-107">By default, updates are downloaded directly from Windows Updates automatically and installed during off-hours.</span></span>
- <span data-ttu-id="e47eb-108">無遅延更新プログラムによって、リリース日が自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="e47eb-108">Non-deferrable Updates install day-one of release automatically.</span></span>
- <span data-ttu-id="e47eb-109">品質更新プログラムとドライバーのダウンロードとインストールが自動的に行われます。</span><span class="sxs-lookup"><span data-stu-id="e47eb-109">Quality Updates and drivers download and install day-one automatically.</span></span>
- <span data-ttu-id="e47eb-110">機能の更新。</span><span class="sxs-lookup"><span data-stu-id="e47eb-110">Feature Updates.</span></span> <span data-ttu-id="e47eb-111">以下のメモを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e47eb-111">See the notes that follow.</span></span>

## <a name="windows-updates-for-business-gpo-or-intune"></a><span data-ttu-id="e47eb-112">ビジネス向け Windows 更新プログラム (GPO または Intune)</span><span class="sxs-lookup"><span data-stu-id="e47eb-112">Windows Updates for Business (GPO or Intune)</span></span>  

- <span data-ttu-id="e47eb-113">一般[法人向けダウンロード用の Windows 更新プログラム](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)</span><span class="sxs-lookup"><span data-stu-id="e47eb-113">[Windows Updates for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) download</span></span>
- <span data-ttu-id="e47eb-114">更新プログラムは、Windows Update または WSUS からダウンロードされますが、最初のリリース日以降の遅延は構成されています。</span><span class="sxs-lookup"><span data-stu-id="e47eb-114">Updates are downloaded from Windows Update or your WSUS but with configured delays past the original release date.</span></span>
- <span data-ttu-id="e47eb-115">複数の Ou またはフィルター処理されたポリシーを使用して、管理者が品質更新プログラムをインストールするデバイスを指定し、後でインストールすることを指定できます。</span><span class="sxs-lookup"><span data-stu-id="e47eb-115">You can use multiple OUs or filtered policies to create deployment “rings” where administrators can specify which devices install Quality Updates first and which ones install later.</span></span> <span data-ttu-id="e47eb-116">信頼性とパフォーマンスは、展開全体で更新プログラムをロールアウトする前に、SCCM での Windows 更新プログラムの管理のオーバーヘッドなしで、システムのサブセットに対してテストすることができます。</span><span class="sxs-lookup"><span data-stu-id="e47eb-116">Reliability and performance can be tested on a subset of systems before rolling out updates across the entire deployment without the overhead of managing Windows Updates in SCCM.</span></span>
- <span data-ttu-id="e47eb-117">ビジネス向けの帯域幅管理と Windows Update の制御の両方が必要な場合は、WSUS と Windows の更新プログラムを同時[に構成](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb)することができます。</span><span class="sxs-lookup"><span data-stu-id="e47eb-117">WSUS and Windows Updates for Business can be [configured at the same time](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb) if you desire both the bandwidth management and the control Windows Updates for Business provides.</span></span>
- <span data-ttu-id="e47eb-118">機能の更新。</span><span class="sxs-lookup"><span data-stu-id="e47eb-118">Feature updates.</span></span> <span data-ttu-id="e47eb-119">以下のメモを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e47eb-119">See the notes that follow.</span></span>

## <a name="wsussccm"></a><span data-ttu-id="e47eb-120">WSUS/SCCM</span><span class="sxs-lookup"><span data-stu-id="e47eb-120">WSUS/SCCM</span></span>

- <span data-ttu-id="e47eb-121">[WSUS/SCCM](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)のダウンロード</span><span class="sxs-lookup"><span data-stu-id="e47eb-121">[WSUS/SCCM](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager) download</span></span>
- <span data-ttu-id="e47eb-122">一般法人向け Windows Update と同じように、各 "リング" または展開全体で特定の KB をターゲットに設定するための追加オプションがあります。</span><span class="sxs-lookup"><span data-stu-id="e47eb-122">Much like Windows Update for Business, but with the additional option of targeting specific KB's within each "ring" or the entire deployment.</span></span> <span data-ttu-id="e47eb-123">各更新プログラムは、遅延のみではなく、個別に展開してテストすることができます。</span><span class="sxs-lookup"><span data-stu-id="e47eb-123">Each Update can be individually deployed and tested at will, rather than relying on only a delay.</span></span>
- <span data-ttu-id="e47eb-124">機能の更新。</span><span class="sxs-lookup"><span data-stu-id="e47eb-124">Feature updates.</span></span> <span data-ttu-id="e47eb-125">以下のメモを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e47eb-125">See the notes that follow.</span></span>

### <a name="feature-updates"></a><span data-ttu-id="e47eb-126">機能の更新プログラム</span><span class="sxs-lookup"><span data-stu-id="e47eb-126">Feature updates</span></span>

<span data-ttu-id="e47eb-127">品質と不確認可能な更新プログラムとは異なり、Windows 10 "機能更新プログラム" (メジャー OS リリース) は、Microsoft テストの後にのみインストールされ、Microsoft Teams のルームで特定の更新機能を検証します。</span><span class="sxs-lookup"><span data-stu-id="e47eb-127">Unlike Quality and Non-Deferrable updates, Windows 10 "Feature Updates" (major OS releases) will only be installed after Microsoft tests and validates a given updates functionality with Microsoft Teams Rooms.</span></span> <span data-ttu-id="e47eb-128">半期チャネルに更新プログラムがリリースされている場合 (またはテスト用にシステムを設定している場合)、または手動でプッシュした場合でも、Microsoft Room Systems デバイスでは、テストされていない更新プログラムをインストールすることはできません。</span><span class="sxs-lookup"><span data-stu-id="e47eb-128">Even if the update is released to the Semi-Annual Channel (or Targeted if you have systems set to that channel for testing) or manually pushed, a Microsoft Room Systems device won't allow the untested update to install.</span></span>

<span data-ttu-id="e47eb-129">Microsoft Teams の会議機能は、ハンズオフアプローチを備えた、Windows Update をインストールしたり、Windows Update 用のデバイスを自動的に再起動したりすることはありません。</span><span class="sxs-lookup"><span data-stu-id="e47eb-129">Microsoft Teams Rooms functions "out-of-box" with a hands-off approach, and will not install a Windows Update or reboot a device automatically for a Windows Update.</span></span> <span data-ttu-id="e47eb-130">システムは更新プログラムをダウンロードして、次に再起動するまで待ってからインストールします。</span><span class="sxs-lookup"><span data-stu-id="e47eb-130">Systems download an update and wait for the next reboot to install it.</span></span> <span data-ttu-id="e47eb-131">手動で再起動しない限り、インストールは自動夜間の再起動としてのみ行われます。</span><span class="sxs-lookup"><span data-stu-id="e47eb-131">Unless someone reboots it manually, installation only happens at the automatic nightly reboot.</span></span> <span data-ttu-id="e47eb-132">Windows の更新プログラムはルームで透過的である必要があります。また、通常の操作は Windows 更新プログラムによって中断されることはありません。</span><span class="sxs-lookup"><span data-stu-id="e47eb-132">Windows Updates should be transparent in the room, and normal operation should never be interrupted by Windows Updates.</span></span>

<span data-ttu-id="e47eb-133">ドメインに参加するデバイスを選択する場合は、SCCM または WSUS を使用します。</span><span class="sxs-lookup"><span data-stu-id="e47eb-133">If you choose to domain join devices, use SCCM or WSUS.</span></span> <span data-ttu-id="e47eb-134">デバイスの更新、または営業時間中に再起動が行われるポリシーやアクションには、特別な注意を払ってください。</span><span class="sxs-lookup"><span data-stu-id="e47eb-134">Pay special attention to policies or actions that result in a device update or forced reboot during business hours.</span></span> <span data-ttu-id="e47eb-135">展開内のシステムは使用中に再起動しないようにする必要があります。または、使用時間中に UI を介した Windows 更新についての通知で、動作が発生した場合は構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="e47eb-135">Systems in your deployment should not reboot during use or alert about Windows Updates over the UI during usage hours, review your configuration if that behavior happens.</span></span>