---
title: Skype ルームの Windows の更新プログラムを管理システム v2
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 10/10/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ''
description: Skype ルームの Windows の更新プログラムを管理システム v2
ms.openlocfilehash: 4b1b0bc27be3f8277fde0c641efe5359ca002d65
ms.sourcegitcommit: 7d65eafd5b0163ece91deb7801458c7a45fcc4f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2018
ms.locfileid: "25839706"
---
# <a name="manage-windows-updates"></a><span data-ttu-id="73df6-103">Windows の更新プログラムを管理します。</span><span class="sxs-lookup"><span data-stu-id="73df6-103">Manage Windows Updates</span></span>

<span data-ttu-id="73df6-104">Skype ルーム システム v2 (SRS v2) は、10 企業「IoT の Windows または Windows 10 エンタープライズ (VL) 上で実行され標準のデスクトップと同じ Windows の更新プログラムおよびオペレーティング システムのビルドを受信します。</span><span class="sxs-lookup"><span data-stu-id="73df6-104">Skype Room System v2 (SRS v2) runs on Windows 10 Enterprise IoT or Windows 10 Enterprise (VL) and receives the same Windows Updates and OS builds as a standard desktop.</span></span>

<span data-ttu-id="73df6-105">Windows の更新プログラムは、いくつかの異なる方法で管理できます。</span><span class="sxs-lookup"><span data-stu-id="73df6-105">Windows Updates can be managed in a few different ways:</span></span>

## <a name="hands-off-approach"></a><span data-ttu-id="73df6-106">瞬時のアプローチ</span><span class="sxs-lookup"><span data-stu-id="73df6-106">Hands-off approach</span></span> 
- <span data-ttu-id="73df6-107">更新プログラムを自動的に Windows Update から直接ダウンロードし、業務時間外にインストールします。</span><span class="sxs-lookup"><span data-stu-id="73df6-107">Updates can be downloaded directly from Windows Updates automatically and installed during off-hours.</span></span> <span data-ttu-id="73df6-108">変更が行われていない場合の構成にこれは、既定の状態です。</span><span class="sxs-lookup"><span data-stu-id="73df6-108">If no change is made to configuration this is the default state.</span></span>
- <span data-ttu-id="73df6-109">非遅延更新は、リリースの 1 日目を自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="73df6-109">Non-deferrable Updates will install day-one of release automatically.</span></span> 
- <span data-ttu-id="73df6-110">品質の更新プログラムとドライバーをダウンロードして自動的に 1 日 1 をインストールします。</span><span class="sxs-lookup"><span data-stu-id="73df6-110">Quality Updates and drivers will download and install day-one automatically.</span></span> 
- <span data-ttu-id="73df6-111">機能を更新します。</span><span class="sxs-lookup"><span data-stu-id="73df6-111">Feature Updates.</span></span> <span data-ttu-id="73df6-112">以下の追加の注記を参照してください。</span><span class="sxs-lookup"><span data-stu-id="73df6-112">See additional notes below.</span></span> 

## <a name="windows-updates-for-businesshttpsdocsmicrosoftcomwindowsdeploymentupdatewaas-manage-updates-wufb-gpo-or-intune"></a><span data-ttu-id="73df6-113">[ビジネスのための Windows の更新プログラム](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)GPO (Intune)</span><span class="sxs-lookup"><span data-stu-id="73df6-113">[Windows Updates for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) (GPO or Intune)</span></span>   
- <span data-ttu-id="73df6-114">KB の元のリリース日以降の遅延が構成されているのですが、WU または、WSUS から更新プログラムがダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="73df6-114">Updates are downloaded from WU or your WSUS but with configured delays past the KB’s original release date.</span></span> 
- <span data-ttu-id="73df6-115">複数の OU と組み合わせるか、これにより、作成するためのポリシーをフィルター処理「リング」、管理者が品質の更新プログラムを最初にインストールするデバイスを指定できますの配置となるものは後でインストールします。</span><span class="sxs-lookup"><span data-stu-id="73df6-115">Combined with multiple OU’s or filtered policies, this allows for the creation of deployment “rings”, where administrators can specify which devices install Quality Updates first and which ones will install later.</span></span> <span data-ttu-id="73df6-116">信頼性とパフォーマンスの SCCM で Windows の更新プログラムを管理するオーバーヘッドを生じさせず展開全体で更新プログラムをロールアウトする前にシステムの一部をテストできます。</span><span class="sxs-lookup"><span data-stu-id="73df6-116">This allows for reliability and performance testing on a subset of systems before rolling out updates across the entire deployment without the overhead of managing Windows Updates in SCCM for example.</span></span>
- <span data-ttu-id="73df6-117">WSUS とビジネスのための Windows の更新プログラムは、帯域幅の管理とビジネスのための Windows の更新プログラムのコントロールの両方を希望する場合は、[同時に構成されている](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb)を提供します。</span><span class="sxs-lookup"><span data-stu-id="73df6-117">WSUS and Windows Updates for Business can be [configured at the same time](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb) if you desire both bandwidth management and the control Windows Updates for Business provides.</span></span>
- <span data-ttu-id="73df6-118">機能を更新します。</span><span class="sxs-lookup"><span data-stu-id="73df6-118">Feature updates.</span></span> <span data-ttu-id="73df6-119">以下の追加の注記を参照してください。</span><span class="sxs-lookup"><span data-stu-id="73df6-119">See additional notes below.</span></span>

## <a name="wsussccmhttpsdocsmicrosoftcomwindowsdeploymentupdatewaas-manage-updates-configuration-manager"></a>[<span data-ttu-id="73df6-120">WSUS または SCCM</span><span class="sxs-lookup"><span data-stu-id="73df6-120">WSUS/SCCM</span></span>](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)
- <span data-ttu-id="73df6-121">ビジネスが「リング」または全体の展開内の特定の KB を対象とする追加オプションを使用して Windows の更新プログラムのような。</span><span class="sxs-lookup"><span data-stu-id="73df6-121">Much like Windows Update for Business, but with the additional option of targeting specific KB's within each "ring" or the entire deployment.</span></span> <span data-ttu-id="73df6-122">各更新プログラムは、個別に展開されたとは、テストではなく遅延のみで証明書利用者にあります。</span><span class="sxs-lookup"><span data-stu-id="73df6-122">Each Update can be individually deployed and tested at will, rather than relying on only a delay.</span></span> 
- <span data-ttu-id="73df6-123">機能を更新します。</span><span class="sxs-lookup"><span data-stu-id="73df6-123">Feature updates.</span></span> <span data-ttu-id="73df6-124">以下の追加の注記を参照してください。</span><span class="sxs-lookup"><span data-stu-id="73df6-124">See additional notes below.</span></span>


### <a name="feature-updates"></a><span data-ttu-id="73df6-125">機能の更新</span><span class="sxs-lookup"><span data-stu-id="73df6-125">Feature updates</span></span>

<span data-ttu-id="73df6-126">品質と非 Deferable の更新プログラム、Windows の 10 とは異なり機能更新プログラム」(OS のメジャー リリース) は、Microsoft がテストして、SRS v2 を指定した更新プログラムの機能を評価した後のみインストールができます。</span><span class="sxs-lookup"><span data-stu-id="73df6-126">Unlike Quality and Non-Deferable updates, Windows 10 "Feature Updates" (major OS releases) will only be installed after Microsoft tests and validates a given updates functionality with SRS v2.</span></span> <span data-ttu-id="73df6-127">半年チャネル (または対象システムがテスト用には、そのチャネルに設定されている場合) にリリースするか、試行または構成によって手動でもプッシュは、たとえ、マイクロソフト側のブロックが解除されるまでインストールは許可がします。</span><span class="sxs-lookup"><span data-stu-id="73df6-127">Even if it is released to the Semi-Annual Channel (or Targeted if you have systems set to that channel for testing) or even manually pushed by your own attempts or configurations, it will not allow the installation until the block on our end is removed.</span></span>

<span data-ttu-id="73df6-128">SRS v2」の標準」を自動化された方法を使用しての Windows の更新プログラムをインストールまたは Windows の更新プログラムがあるため、デバイスを自動的に再起動ができません。</span><span class="sxs-lookup"><span data-stu-id="73df6-128">An SRS v2 "out-of-box", using the hands off approach, will not install a Windows Update or reboot a device automatically because of a Windows Update.</span></span> <span data-ttu-id="73df6-129">システムは可能性があります、ただし、更新プログラムをダウンロードし、それをインストールするのには次の再起動を待ちます。</span><span class="sxs-lookup"><span data-stu-id="73df6-129">Systems may, however, download an update and wait for the next reboot to install it.</span></span> <span data-ttu-id="73df6-130">手動で再起動誰かしない限り、インストールは自動の夜間の再起動時に発生します。</span><span class="sxs-lookup"><span data-stu-id="73df6-130">Unless someone reboots it manually, installation should happen at the automatic nightly reboot.</span></span> <span data-ttu-id="73df6-131">Windows の更新プログラムは、部屋に透過的でなければならない、UI は、Windows の更新プログラムによって中断されることはありませんする必要があります。</span><span class="sxs-lookup"><span data-stu-id="73df6-131">Windows Updates should be transparent in the room, the UI should never be interrupted by Windows Updates.</span></span>

<span data-ttu-id="73df6-132">ドメインへの参加を選択した場合は、SCCM または WSUS を使用し、ポリシーまたはデバイスの更新プログラムをインストールするか、業務時間中に再起動を強制することにつながるアクションに特に注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="73df6-132">If you choose to domain join, use SCCM or WSUS, and please pay special attention to policies or actions that may result in the device installing an update or forcing a reboot during business hours.</span></span> <span data-ttu-id="73df6-133">システム展開の使用時に再起動するか、UI 上で Windows の更新プログラムに関する警告である場合は、する場合の構成を検討します。</span><span class="sxs-lookup"><span data-stu-id="73df6-133">If you have systems in your deployment rebooting during use or alerting about Windows Updates over the UI, you will want to look into your configuration.</span></span>