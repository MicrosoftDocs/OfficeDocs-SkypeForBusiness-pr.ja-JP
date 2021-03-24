---
title: Skype for Business Server 2015 で TLS 1.0/1.1 を無効にする
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 環境で TLS 1.0 と 1.1 を無効にする準備と実装を行います。
ms.openlocfilehash: b07b9b5319b858a20a8073de8c6a37dd4d3299ec
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103213"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a><span data-ttu-id="9d238-103">Skype for Business Server 2015 で TLS 1.0/1.1 を無効にする</span><span class="sxs-lookup"><span data-stu-id="9d238-103">Disable TLS 1.0/1.1 in Skype for Business Server 2015</span></span>

<span data-ttu-id="9d238-104">この記事では、環境で TLS 1.0 と 1.1 を無効にする準備と実装に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="9d238-104">This article helps you prepare for and implement disabling TLS 1.0 and 1.1 in your environments.</span></span> <span data-ttu-id="9d238-105">このプロセスには、広範な計画と準備が必要です。</span><span class="sxs-lookup"><span data-stu-id="9d238-105">This process requires extensive planning and preparation.</span></span> <span data-ttu-id="9d238-106">組織で TLS 1.0 と 1.1 を無効にする計画を立て、この記事のすべての情報を慎重に確認してください。</span><span class="sxs-lookup"><span data-stu-id="9d238-106">Carefully review all of the information in this article as you make your plan to disable TLS 1.0 and 1.1 for your organization.</span></span> <span data-ttu-id="9d238-107">TLS 1.0/1.1 を無効にすることで影響を受けかねない多くの外部依存関係と接続条件があります。そのため、広範な計画とテストが保証されます。</span><span class="sxs-lookup"><span data-stu-id="9d238-107">There are many external dependencies and connectivity conditions that could be impacted by disabling TLS 1.0/1.1, so extensive planning and testing is warranted.</span></span>

- [<span data-ttu-id="9d238-108">背景とスコープ</span><span class="sxs-lookup"><span data-stu-id="9d238-108">Background and scope</span></span>](#background-and-scope)
- [<span data-ttu-id="9d238-109">前提条件とプロセス</span><span class="sxs-lookup"><span data-stu-id="9d238-109">Prerequisites and process</span></span>](#prerequisites-and-process)
- [<span data-ttu-id="9d238-110">高度な展開シナリオ</span><span class="sxs-lookup"><span data-stu-id="9d238-110">Advanced deployment scenarios</span></span>](#advanced-deployment-scenarios)

## <a name="background-and-scope"></a><span data-ttu-id="9d238-111">背景とスコープ</span><span class="sxs-lookup"><span data-stu-id="9d238-111">Background and scope</span></span>

<span data-ttu-id="9d238-112">TLS 1.0 および 1.1 を提供するための主要なドライバーは、Skype for Business Server オンプレミスのサポートを無効にしているのが、Payment Card Industry (PCI) セキュリティ標準評議会と連邦情報処理標準の要件です。</span><span class="sxs-lookup"><span data-stu-id="9d238-112">The primary drivers for providing TLS 1.0 and 1.1 disable support for Skype for Business Server On-Premises are Payment Card Industry (PCI) Security Standards Council and Federal Information Processing Standards requirements.</span></span> <span data-ttu-id="9d238-113">PCI 要件の詳細については、こちらを参照 [してください](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls)。</span><span class="sxs-lookup"><span data-stu-id="9d238-113">More information for PCI requirements can be found [here](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).</span></span>  <span data-ttu-id="9d238-114">Microsoft は、組織がこれらの要件または他の要件を遵守する必要があるかどうかに関するガイダンスを提供できません。</span><span class="sxs-lookup"><span data-stu-id="9d238-114">Microsoft cannot provide guidance on whether or not your organization is required to adhere to these or other requirements.</span></span> <span data-ttu-id="9d238-115">環境で TLS 1.0 および/または 1.1 を無効にする必要があるかどうかを判断する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d238-115">You must determine if it is required for you to disable TLS 1.0 and/or 1.1 in your environments.</span></span>

<span data-ttu-id="9d238-116">Microsoft は、ここで利用できる TLS に関するホワイト ペーパーを作成 [しました](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/)。また、この Exchange ブログで利用できる背景の読み取りも [推奨します](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)。</span><span class="sxs-lookup"><span data-stu-id="9d238-116">Microsoft has produced a white paper on TLS available [here](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/), and we also recommend the background reading available in this [Exchange blog](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/).</span></span>

## <a name="supportability-scope"></a><span data-ttu-id="9d238-117">サポートの範囲</span><span class="sxs-lookup"><span data-stu-id="9d238-117">Supportability Scope</span></span>

<span data-ttu-id="9d238-118">*スコープ* は、サポートの境界を参照します。</span><span class="sxs-lookup"><span data-stu-id="9d238-118">*Scope* refers to supportability boundaries.</span></span> <span data-ttu-id="9d238-119">*完全にテストされ* 、サポートされているということは、リストされている製品バージョンの TLS 1.0 と 1.1 の無効化を完全にサポートし、テスト済みです。</span><span class="sxs-lookup"><span data-stu-id="9d238-119">*Fully tested and supported* means we fully support and have tested disabling of TLS 1.0 and 1.1 for the listed product versions.</span></span> <span data-ttu-id="9d238-120">*現在調査中の場合は* 、その情報が必要です。これらの製品を TLS 無効化のサポートの範囲に含め、積極的に調査しています。</span><span class="sxs-lookup"><span data-stu-id="9d238-120">*Currently being investigated* means just that; we are actively investigating bringing these products into scope for TLS disable support.</span></span> <span data-ttu-id="9d238-121">*スコープ外の場合* 、これらの製品バージョンは TLS 1.0 または 1.1 の無効化をサポートしていないので、機能しません。ただし、例外が示されています。</span><span class="sxs-lookup"><span data-stu-id="9d238-121">*Out of scope* means these product versions do not support disabling TLS 1.0 or 1.1 and will not work, with noted exceptions.</span></span>

### <a name="fully-tested-and-supported-servers"></a><span data-ttu-id="9d238-122">完全にテストされ、サポートされているサーバー</span><span class="sxs-lookup"><span data-stu-id="9d238-122">Fully tested and supported servers</span></span>

- <span data-ttu-id="9d238-123">Skype for Business Server 2019 CU1 17.0.2046.123 (2019 年 6 月) 以上</span><span class="sxs-lookup"><span data-stu-id="9d238-123">Skype for Business Server 2019 CU1 17.0.2046.123 (June 2019) or higher</span></span>
- <span data-ttu-id="9d238-124">Skype for Business Server 2015 CU9 6.0.9319.548 (2019 年 5 月) 以上の Windows Server 2012 (KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) 以上の更新プログラムを使用)、2012 R2 または 2016。</span><span class="sxs-lookup"><span data-stu-id="9d238-124">Skype for Business Server 2015 CU9 6.0.9319.548 (May 2019) or higher on Windows Server 2012 (with KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseding update), 2012 R2 or 2016.</span></span>
- <span data-ttu-id="9d238-125">一方でアップグレードされた Skype for Business Server 2015(CU9 6.0.9319.548 (2019 年 5 月) 以上の Windows Server 2008 R2、2012 (KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) または更新プログラムの代用)、または 2012 R2。</span><span class="sxs-lookup"><span data-stu-id="9d238-125">In-place Upgraded Skype for Business Server 2015, with CU9 6.0.9319.548 (May 2019) or higher on Windows Server 2008 R2, 2012 (with KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseding update), or 2012 R2.</span></span>
- <span data-ttu-id="9d238-126">Exchange Connectivity and Outlook Web App 2010 SP3 RU19 Exchange Server 2010 SP3 RU19 以上の場合のガイダンス[](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span><span class="sxs-lookup"><span data-stu-id="9d238-126">Exchange Connectivity and Outlook Web App with Exchange Server 2010 SP3 RU19 or higher, guidance [here](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span></span>
- <span data-ttu-id="9d238-127">Skype for Business Server 2015 CU6 HF2 以上の存続可能ブランチ アプライアンス (SBA) (適切な更新プログラムがパッケージ化され、アプライアンスで使用可能にされたとベンダーに確認してください)</span><span class="sxs-lookup"><span data-stu-id="9d238-127">Survivable Branch Appliance (SBA) with Skype for Business Server 2015 CU6 HF2 or higher (confirm with your vendor that they packaged the appropriate updates and have been made available for your appliance)</span></span>
- <span data-ttu-id="9d238-128">Skype for Business Server 2015 CU6 HF2 以上の存続可能ブランチ サーバー (SBS)</span><span class="sxs-lookup"><span data-stu-id="9d238-128">Survivable Branch Server (SBS) with Skype for Business Server 2015 CU6 HF2 or higher</span></span>
- <span data-ttu-id="9d238-129">Lync Server 2013 **Edge Role Only**,これは、エッジ の役割が Windows Fabric 1.0 に依存していないためです。</span><span class="sxs-lookup"><span data-stu-id="9d238-129">Lync Server 2013 **Edge Role Only**, this is because Edge role does not have a dependency on Windows Fabric 1.0.</span></span>

### <a name="fully-tested-and-supported-clients"></a><span data-ttu-id="9d238-130">完全にテストされ、サポートされているクライアント</span><span class="sxs-lookup"><span data-stu-id="9d238-130">Fully tested and supported clients</span></span>

- <span data-ttu-id="9d238-131">Lync 2013 (Skype for Business) デスクトップ クライアント、MSI、C2R (Basic [15.0.5023.1000 以上を含む](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334))</span><span class="sxs-lookup"><span data-stu-id="9d238-131">Lync 2013 (Skype for Business) Desktop Client, MSI and C2R, including Basic [15.0.5023.1000 or higher](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)</span></span>
- <span data-ttu-id="9d238-132">Skype for Business 2016 デスクトップ クライアント、MSI [16.0.4678.1000](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323)以上 (Basic を含む)</span><span class="sxs-lookup"><span data-stu-id="9d238-132">Skype for Business 2016 Desktop Client, MSI [16.0.4678.1000 or higher](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), including Basic</span></span>
- <span data-ttu-id="9d238-133">Skype for Business 2016 Click to Run Require the [April 2018](/officeupdates/release-notes-office365-proplus) Updates:</span><span class="sxs-lookup"><span data-stu-id="9d238-133">Skype for Business 2016 Click to Run Require the [April 2018](/officeupdates/release-notes-office365-proplus) Updates:</span></span> 
    - <span data-ttu-id="9d238-134">月次およびSemi-Annual対象、16 \. 0 \. 9126 \. 2152 以上</span><span class="sxs-lookup"><span data-stu-id="9d238-134">Monthly and Semi-Annual Targeted, 16\.0\.9126\.2152 or higher</span></span>
    - <span data-ttu-id="9d238-135">Semi-Annualおよび遅延チャネル、16 \. 0 \. 8431 \. 2242 以上</span><span class="sxs-lookup"><span data-stu-id="9d238-135">Semi-Annual and Deferred Channel, 16\.0\.8431\.2242 or higher</span></span>
- <span data-ttu-id="9d238-136">Skype for Business on Mac 16.15 以上</span><span class="sxs-lookup"><span data-stu-id="9d238-136">Skype for Business on Mac 16.15 or higher</span></span>
- <span data-ttu-id="9d238-137">Skype for Business for iOS および Android 6.19 以上</span><span class="sxs-lookup"><span data-stu-id="9d238-137">Skype for Business for iOS and Android 6.19 or higher</span></span>
- <span data-ttu-id="9d238-138">Microsoft Teams Rooms (以前は Skype Room System V2 SRS V2) 4.0.64.0 (2018 年 12 月) 以上</span><span class="sxs-lookup"><span data-stu-id="9d238-138">Microsoft Teams Rooms (previously known as Skype Room System V2 SRS V2) 4.0.64.0 (December 2018) or higher</span></span>
- <span data-ttu-id="9d238-139">KB4499162 (2019 年 5 月、OS ビルド 15063.1835) 以上に基づくチーム エディションの Surface Hub 更新プログラム</span><span class="sxs-lookup"><span data-stu-id="9d238-139">Surface Hub update for Team edition based on KB4499162 (May 2019, OS Build 15063.1835) or higher</span></span>
- <span data-ttu-id="9d238-140">Skype Web App 2015 CU6 HF2 以上 (サーバーに含む)</span><span class="sxs-lookup"><span data-stu-id="9d238-140">Skype Web App 2015 CU6 HF2 or higher (ships with Server)</span></span>

### <a name="currently-being-investigated"></a><span data-ttu-id="9d238-141">現在調査中</span><span class="sxs-lookup"><span data-stu-id="9d238-141">Currently being investigated</span></span>

- <span data-ttu-id="9d238-142">通話品質ダッシュボード (TLS 1.0、1.1 が無効にされた後の新しいインストールは、以下を参照)\*</span><span class="sxs-lookup"><span data-stu-id="9d238-142">Call Quality Dashboard (new install after TLS 1.0, 1.1 have been disabled, see below)\*</span></span>
 
### <a name="out-of-scope"></a><span data-ttu-id="9d238-143">対象外</span><span class="sxs-lookup"><span data-stu-id="9d238-143">Out of scope</span></span>

<span data-ttu-id="9d238-144">ただし、以下の製品は TLS 1.0/1.1 ではサポートを無効にし、TLS 1.0 と 1.1 が無効になっている環境では機能しません。</span><span class="sxs-lookup"><span data-stu-id="9d238-144">Except where noted, the following products are not in scope for TLS 1.0/1.1 disable support and will not function in an environment where TLS 1.0 and 1.1 have been disabled.</span></span> <span data-ttu-id="9d238-145">つまり、スコープ外のサーバーまたはクライアントを引き続き使用する場合は、Skype for Business Server オンプレミス展開の任意の場所で TLS 1.0/1.1 を無効にする必要がある場合は、これらを更新または削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d238-145">What this means: if you still utilize out-of-scope servers or clients, you must update or remove these if you need to disable TLS 1.0/1.1 anywhere in your Skype for Business Server on-premises deployment.</span></span>

- <span data-ttu-id="9d238-146">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9d238-146">Lync Server 2013</span></span>
- <span data-ttu-id="9d238-147">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="9d238-147">Lync Server 2010</span></span>
- <span data-ttu-id="9d238-148">Windows Server 2008 以下</span><span class="sxs-lookup"><span data-stu-id="9d238-148">Windows Server 2008 or lower</span></span>
- <span data-ttu-id="9d238-149">Lync for Mac 2011</span><span class="sxs-lookup"><span data-stu-id="9d238-149">Lync for Mac 2011</span></span>
- <span data-ttu-id="9d238-150">Lync 2013 for Mobile - iOS、iPad、Android、または Windows Phone</span><span class="sxs-lookup"><span data-stu-id="9d238-150">Lync 2013 for Mobile - iOS, iPad, Android or Windows Phone</span></span>
- <span data-ttu-id="9d238-151">Lync "MX" Windows ストア クライアント</span><span class="sxs-lookup"><span data-stu-id="9d238-151">Lync "MX" Windows Store client</span></span>
- <span data-ttu-id="9d238-152">Lync Room System (a.k.a.</span><span class="sxs-lookup"><span data-stu-id="9d238-152">Lync Room System (a.k.a.</span></span> <span data-ttu-id="9d238-153">SRSv1)。</span><span class="sxs-lookup"><span data-stu-id="9d238-153">SRSv1).</span></span> <span data-ttu-id="9d238-154">LRS は 2018 年 10 月 9 日にサポート終了に達し、TLS 1.2 をサポートするために更新されません。</span><span class="sxs-lookup"><span data-stu-id="9d238-154">LRS reached end of support on October 9, 2018 and will not be updated to support TLS 1.2.</span></span>
- <span data-ttu-id="9d238-155">すべての Lync 2010 クライアント</span><span class="sxs-lookup"><span data-stu-id="9d238-155">All Lync 2010 clients</span></span>
- <span data-ttu-id="9d238-156">Lync Phone Edition - ここで更新された [ガイダンス](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035)。</span><span class="sxs-lookup"><span data-stu-id="9d238-156">Lync Phone Edition - updated guidance [here](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).</span></span>
- <span data-ttu-id="9d238-157">2013 ベースの存続可能ブランチ アプライアンス (SBA) または存続可能ブランチ サーバー (SBS)</span><span class="sxs-lookup"><span data-stu-id="9d238-157">2013 based Survivable Branch Appliance (SBA) or Survivable Branch Server (SBS)</span></span>
- <span data-ttu-id="9d238-158">クラウド コネクタ エディション (CCE)</span><span class="sxs-lookup"><span data-stu-id="9d238-158">Cloud Connector Edition (CCE)</span></span>
- <span data-ttu-id="9d238-159">Skype for Business for Windows Phone</span><span class="sxs-lookup"><span data-stu-id="9d238-159">Skype for Business for Windows Phone</span></span>

### <a name="exceptions"></a><span data-ttu-id="9d238-160">例外</span><span class="sxs-lookup"><span data-stu-id="9d238-160">Exceptions</span></span>

#### <a name="lync-server-2013"></a><span data-ttu-id="9d238-161">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9d238-161">Lync Server 2013</span></span>

<span data-ttu-id="9d238-162">Lync Server 2013 は、Windows Fabric バージョン 1.0 に依存します。</span><span class="sxs-lookup"><span data-stu-id="9d238-162">Lync Server 2013 takes a dependency on Windows Fabric version 1.0.</span></span>  <span data-ttu-id="9d238-163">Lync Server 2013 の設計フェーズでは、レプリケーション、高可用性、フォールト トレランスを実現するために、魅力的で新しい分散アーキテクチャとして Windows Fabric 1.0 が選択されました。</span><span class="sxs-lookup"><span data-stu-id="9d238-163">In the design phase for Lync Server 2013, Windows Fabric 1.0 was chosen for its compelling and new distributed architecture to provide replication, high availability, and fault tolerance.</span></span>  <span data-ttu-id="9d238-164">時間がたつ間に、Skype for Business Server と Windows Fabric の両方が、この共同アーキテクチャを大幅に改善し、以降のバージョンでは大幅に再設計されました。</span><span class="sxs-lookup"><span data-stu-id="9d238-164">Over time, both Skype for Business Server and Windows Fabric have greatly improved this joint architecture with significant re-design in subsequent versions.</span></span>  <span data-ttu-id="9d238-165">現在の Skype for Business 2015 Server では、たとえば Windows Fabric 3.0 が使用されます。</span><span class="sxs-lookup"><span data-stu-id="9d238-165">Current Skype for Business 2015 Server uses Windows Fabric 3.0, for example.</span></span>

<span data-ttu-id="9d238-166">残念ながら、Windows Fabric 1.0 **では TLS 1.2 はサポートされていません。 ただし、LYNC Server 2013 を更新して TLS 1.2** で動作します。</span><span class="sxs-lookup"><span data-stu-id="9d238-166">Unfortunately, Windows Fabric 1.0 **does not support TLS 1.2.  However, we will be updating Lync Server 2013 to work with TLS 1.2**.</span></span> <span data-ttu-id="9d238-167">これは、Lync Server 2013 の次の累積的な更新プログラムに含まれる予定です。</span><span class="sxs-lookup"><span data-stu-id="9d238-167">This will be coming in the next Cumulative Update for Lync Server 2013.</span></span>  <span data-ttu-id="9d238-168">TLS 1.2 のサポートを提供して、共存在、移行、フェデレーション、ハイブリッドのシナリオを有効にします。</span><span class="sxs-lookup"><span data-stu-id="9d238-168">We're providing TLS 1.2 support to enable co-existence, migration, federation, and hybrid scenarios.</span></span>

<span data-ttu-id="9d238-169">組織で TLS 1.0 と 1.1 を無効にする必要がある場合に、現在 Lync Server 2013 を使用している場合は、計画プロセスを開始することをお勧めします。計画プロセスを開始すると、一時アップグレードまたはサイド バイ サイド移行 (新しいプール、ユーザーの移動) が Skype for Business Server 2015 以上になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9d238-169">If your organization is required to disable TLS 1.0 and 1.1, and you currently use Lync Server 2013, we recommend you begin your planning process, with the possibility you may have to In-place upgrade or Side-by-Side migrate (new pools, move users) to Skype for Business Server 2015 or higher.</span></span>  <span data-ttu-id="9d238-170">または、Skype for Business Online への移行を加速する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="9d238-170">Or you may want to accelerate migration to Skype for Business Online.</span></span>

#### <a name="call-quality-dashboard"></a><span data-ttu-id="9d238-171">通話品質ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="9d238-171">Call Quality Dashboard</span></span>

<span data-ttu-id="9d238-172">オンプレミス通話品質ダッシュボードは、現在、新しいインストール時 (オンプレミス環境への初回インストール) 中に TLS 1.0 に依存しています。</span><span class="sxs-lookup"><span data-stu-id="9d238-172">On-Premises Call Quality Dashboard currently has a dependency on TLS 1.0 during new install (first time installing into your On-Premises environments).</span></span>  <span data-ttu-id="9d238-173">現在、この問題を調査中であり、近い将来に修正プログラムをリリースする予定です。</span><span class="sxs-lookup"><span data-stu-id="9d238-173">We are currently investigating this issue and plan to release a fix in the near future.</span></span>  <span data-ttu-id="9d238-174">CQD のインストールと TLS 1.0 の無効化を計画している場合は、最初に CQD インストールを完了してから、TLS 1.0 の無効化を続行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9d238-174">If you are planning to install CQD and also disable TLS 1.0, we recommend that you complete CQD installation first, and then proceed with TLS 1.0 disabling.</span></span>

#### <a name="skype-for-business-sdn-manager"></a><span data-ttu-id="9d238-175">Skype for Business SDN Manager</span><span class="sxs-lookup"><span data-stu-id="9d238-175">Skype for Business SDN Manager</span></span>

<span data-ttu-id="9d238-176">データベースを使用する Skype for Business SDN Manager SQL、新しいインストール時に TLS 1.0 に依存します。</span><span class="sxs-lookup"><span data-stu-id="9d238-176">Skype for Business SDN Manager using SQL a database has a dependency on TLS 1.0 during new install.</span></span> <span data-ttu-id="9d238-177">SQL データベースを使用して Skype for Business SDN Manager をインストールし、TLS 1.0 も無効にする場合は、まず Skype for Business SDN Manager を完了してから、TLS 1.0 の無効化を続行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9d238-177">If you are planning to install Skype for Business SDN Manager using SQL a database and also disable TLS 1.0, we recommend that you complete Skype for Business SDN Manager first, and then proceed with TLS 1.0 disabling.</span></span> <span data-ttu-id="9d238-178">インストール前に TLS 1.0 が無効になっている場合は、Skype for Business SDN Manager SQL データベースのホストに使用される SQL Server バックエンド サーバーで TLS 1.0 を一時的に有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d238-178">In case TLS 1.0 was disabled prior to installation, you should temporarily enabled TLS 1.0 back in SQL Server backend server that will be used to host Skype for Business SDN Manager SQL database.</span></span>

#### <a name="third-party-devices"></a><span data-ttu-id="9d238-179">サード パーティ製デバイス</span><span class="sxs-lookup"><span data-stu-id="9d238-179">Third-party devices</span></span>

<span data-ttu-id="9d238-180">3PIP 電話、ビデオ会議、リバース プロキシ、ロード バランサーなどのサード パーティ製デバイスでは、TLS 1.2 のサポートを検証し、慎重にテストし、必要に応じてベンダーに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="9d238-180">On third-party devices such as 3PIP phones, Video conferencing, Reverse Proxies and Load Balancers, be sure to validate TLS 1.2 supportability, test carefully, and contact the vendor if needed.</span></span>

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a><span data-ttu-id="9d238-181">エッジ サーバーで TLS 1.0/1.1 を無効にする場合のフェデレーションに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="9d238-181">Federation considerations when disabling TLS 1.0/1.1 on Edge servers</span></span>

<span data-ttu-id="9d238-182">TLS 1.0/1.1 をエッジ サーバーで無効にした場合の影響を慎重に計画し、検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d238-182">You must carefully plan for and consider the impact of disabling TLS 1.0/1.1 on your Edge servers.</span></span>  <span data-ttu-id="9d238-183">TLS 1.0 と 1.1 が無効になったら、他の組織が組織とフェデレーションできなくなった場合があります。</span><span class="sxs-lookup"><span data-stu-id="9d238-183">Once TLS 1.0 and 1.1 are disabled, you may find that other organizations are no longer be able to federate with your organization.</span></span>

<span data-ttu-id="9d238-184">パッチ適用されていない (SfB 2015、Lync 2013) 以前の (2010 年) 外部システムとの下位互換性を維持するために、エッジ サーバーで TLS 1.0/1.1 を有効に保つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="9d238-184">You may opt to keep TLS 1.0/1.1 enabled on your Edge servers to maintain backward compatibility with non-patched (SfB 2015, Lync 2013) or older (2010) external systems.</span></span>

<span data-ttu-id="9d238-185">Microsoft は、エッジ ネットワーク (または任意のネットワーク) が PCI 標準に該当するかどうかに関するアドバイスや推奨事項を提供できません。個々の会社によって決定される必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d238-185">Microsoft cannot provide advice or recommendations on whether or not your Edge network (or any network) falls under PCI standard; that must be determined by the individual company.</span></span>

<span data-ttu-id="9d238-186">Skype for Business Online は現在 TLS 1.2 に対応しています。そのため、ハイブリッド/オンラインとのフェデレーションへの影響は期待されません。</span><span class="sxs-lookup"><span data-stu-id="9d238-186">Skype for Business Online is capable of TLS 1.2 today, so no impact to Hybrid/Federation with Online is expected.</span></span>

<span data-ttu-id="9d238-187">PIC (パブリック IM Connectivity) から Skype コンシューマー サービスへ: TLS 1.0/1.1 を無効にして [Skype Connectivity](../../deploy/deploy-skype-connectivity.md)に影響を与える可能性はありません。Microsoft PIC ゲートウェイは既に TLS 1.2 に対応しています。</span><span class="sxs-lookup"><span data-stu-id="9d238-187">PIC (Public IM Connectivity) to Skype Consumer service: We do not expect disabling TLS 1.0/1.1 to impact [Skype Connectivity](../../deploy/deploy-skype-connectivity.md); Microsoft PIC Gateways are already TLS 1.2 capable.</span></span>

## <a name="prerequisites-and-process"></a><span data-ttu-id="9d238-188">前提条件とプロセス</span><span class="sxs-lookup"><span data-stu-id="9d238-188">Prerequisites and process</span></span>

<span data-ttu-id="9d238-189">上記の場合を除き、TLS 1.0 と 1.1 が無効になった後は、スコープ外のサーバーが無効になり、クライアントとデバイスが正常に機能しなくなるか、または全く機能しなくなる。</span><span class="sxs-lookup"><span data-stu-id="9d238-189">Except where noted above, once TLS 1.0 and 1.1 are disabled out-of-scope servers, clients and devices will longer function properly, or at all.</span></span> <span data-ttu-id="9d238-190">これは、Microsoft からの更新されたガイダンスを一時停止して待つ必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="9d238-190">This may mean you need to pause and wait for updated guidance from Microsoft.</span></span> <span data-ttu-id="9d238-191">すべての要件を満たしていることを確認し、ギャップに対処する計画を立てしたら、続行します。</span><span class="sxs-lookup"><span data-stu-id="9d238-191">Once you are satisfied that you meet all requirements and have a plan to address gaps, proceed.</span></span>

<span data-ttu-id="9d238-192">高レベルでは、Skype for Business Server 2019 はインストール時に手順を実行する準備ができましたが、Skype for Business Server 2015 では CU9 のインストール、.NET および SQL への前提条件更新プログラムの適用、前提条件のレジストリ キーの展開、および最後に別の OS 構成更新プログラムの展開 (レジストリ ファイルのインポートによる TLS 1.0 と 1.1 の無効化) が必要になります。</span><span class="sxs-lookup"><span data-stu-id="9d238-192">At a high level, while Skype for Business Server 2019 is ready for procedure at install, Skype for Business Server 2015 will require that you install CU9, applying pre-requisite updates to .NET and SQL, deploying prerequisite registry keys, and finally a separate round of OS configuration updates (i.e. disabling TLS 1.0 and 1.1 via registry file import).</span></span> <span data-ttu-id="9d238-193">環境内の任意のサーバーで TLS 1.0 と 1.1 を無効にする前に、Skype for Business Server 2015 CU6 HF2 を含むすべての前提条件のインストールを完了することが非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="9d238-193">It is critically important that you complete installation of all prerequisites, including Skype for Business Server 2015 CU6 HF2, prior to disabling TLS 1.0 and 1.1 on any server in your environment.</span></span> <span data-ttu-id="9d238-194">エッジの役割やバックエンドを含むすべての Skype for Business サーバー SQL更新プログラムが必要です。</span><span class="sxs-lookup"><span data-stu-id="9d238-194">Every Skype for Business server, including Edge role and SQL Backends, requires the updates.</span></span> <span data-ttu-id="9d238-195">また、サポートされている (スコープ内の) すべてのクライアントが必要な最小バージョンに更新されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d238-195">Also ensure that all supported (in-scope) clients have been updated to the required minimum versions.</span></span> <span data-ttu-id="9d238-196">管理ワークステーションも更新することを忘れないでください。</span><span class="sxs-lookup"><span data-stu-id="9d238-196">Don’t forget to update management workstations as well.</span></span>

<span data-ttu-id="9d238-197">Skype for Business サーバーをアップグレードする場合は、「インサイド アウト」の通常の操作順序に従います。</span><span class="sxs-lookup"><span data-stu-id="9d238-197">We want to follow the usual order of operations of "inside out" for upgrading Skype for Business servers.</span></span> <span data-ttu-id="9d238-198">ディレクター プール、常設チャット、ペアリングされたプールは、通常と同じ方法で処理します。</span><span class="sxs-lookup"><span data-stu-id="9d238-198">Treat Director pools, Persistent chat, and Paired Pools in the same manner you normally would.</span></span> <span data-ttu-id="9d238-199">アップグレードの順序と方法については、ここで[説明](topology.md)[します](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)。</span><span class="sxs-lookup"><span data-stu-id="9d238-199">Order and methods for upgrade are covered [here](topology.md) and [here](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>

### <a name="high-level-process"></a><span data-ttu-id="9d238-200">高レベルのプロセス</span><span class="sxs-lookup"><span data-stu-id="9d238-200">High-level process</span></span>

1. <span data-ttu-id="9d238-201">実稼働サーバーを構成する前に、ラボのすべての手順をテストします。</span><span class="sxs-lookup"><span data-stu-id="9d238-201">Test all steps in your lab prior to configuring production servers.</span></span>
2. <span data-ttu-id="9d238-202">更新する個々のサーバーごとに、エクスポートされたレジストリのコピーをバックアップして保持します。</span><span class="sxs-lookup"><span data-stu-id="9d238-202">Back up and preserve a copy of exported registry on each and every individual server to be updated.</span></span> <span data-ttu-id="9d238-203">サーバー間でレジストリを共有することはできません。コンピューター ベースの一意のキーが含まれる。</span><span class="sxs-lookup"><span data-stu-id="9d238-203">You cannot share registries between servers; they contain unique machine-based keys.</span></span>
3. <span data-ttu-id="9d238-204">すべての Skype for Business 2015 サーバーを CU9 以上にアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="9d238-204">Upgrade all Skype for Business 2015 servers to CU9 or higher.</span></span> <span data-ttu-id="9d238-205">Skype for Business Server 2019 の場合は、CU1 以上にアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="9d238-205">For Skype for Business Server 2019, upgrade to CU1 or higher.</span></span>
4. <span data-ttu-id="9d238-206">すべての前提条件をすべてのサーバーにインストールします。</span><span class="sxs-lookup"><span data-stu-id="9d238-206">Install all prerequisites to all servers.</span></span>
5. <span data-ttu-id="9d238-207">前提条件のレジストリ キーを展開します。</span><span class="sxs-lookup"><span data-stu-id="9d238-207">Deploy prerequisite registry keys.</span></span>
6. <span data-ttu-id="9d238-208">スコープ内のすべてのクライアントが更新されます。</span><span class="sxs-lookup"><span data-stu-id="9d238-208">Ensure that all in-scope clients are updated.</span></span>
7. <span data-ttu-id="9d238-209">レジストリ インポートを使用して TLS 1.0 と 1.1 を無効にします。</span><span class="sxs-lookup"><span data-stu-id="9d238-209">Disable TLS 1.0 and 1.1 via registry import.</span></span>
8. <span data-ttu-id="9d238-210">ワークロードが期待通り機能しているのを検証します。</span><span class="sxs-lookup"><span data-stu-id="9d238-210">Validate that workloads are functioning as expected.</span></span>
    - <span data-ttu-id="9d238-211">問題が発生した場合は、トラブルシューティングと解決、または</span><span class="sxs-lookup"><span data-stu-id="9d238-211">If problems are encountered, troubleshoot and resolve, or</span></span>
    - <span data-ttu-id="9d238-212">手順 2 からレジストリを復元し、TLS 1.0 と 1.1 を再び有効にする</span><span class="sxs-lookup"><span data-stu-id="9d238-212">Restore registry from step 2 to re-enable TLS 1.0 and 1.1</span></span>
9. <span data-ttu-id="9d238-213">TLS 1.2 だけが使用されているのを検証します。</span><span class="sxs-lookup"><span data-stu-id="9d238-213">Validate that only TLS 1.2 is being used.</span></span>

### <a name="install-prerequisites-to-all-servers"></a><span data-ttu-id="9d238-214">すべてのサーバーに前提条件をインストールする</span><span class="sxs-lookup"><span data-stu-id="9d238-214">Install prerequisites to all servers</span></span>

<span data-ttu-id="9d238-215">Skype for Business Server 2015 展開のオペレーティング システム レベルで TLS 1.0 と 1.1 を無効にする前に、広範な依存関係の更新が必要です。</span><span class="sxs-lookup"><span data-stu-id="9d238-215">Extensive dependency updating is required before you begin to disable TLS 1.0 and 1.1 at the operating system level in your Skype for Business Server 2015 deployments.</span></span> <span data-ttu-id="9d238-216">TLS 1.2 をサポートできる最小バージョンを次に示します。</span><span class="sxs-lookup"><span data-stu-id="9d238-216">The following are the minimum versions that can support TLS 1.2.</span></span> <span data-ttu-id="9d238-217">TLS 1.0 と 1.1 の無効化を開始する前に、環境内のすべての Skype for Business サーバーに前提条件の更新プログラムを展開します。</span><span class="sxs-lookup"><span data-stu-id="9d238-217">Deploy all prerequisite updates across every Skype for Business server in your environment before you begin disabling TLS 1.0 and 1.1.</span></span>

- <span data-ttu-id="9d238-218">Skype for Business Server 2015 CU9 6.0.9319.548 (2019 年 5 月) 以上</span><span class="sxs-lookup"><span data-stu-id="9d238-218">Skype for Business Server 2015 CU9 6.0.9319.548 (May 2019) or higher</span></span>
- <span data-ttu-id="9d238-219">.NET Frameworkで SchUseStrongCrypto が有効になっている[4.7](https://www.microsoft.com/download/details.aspx?id=55167)以上の場合 (以下に提供)</span><span class="sxs-lookup"><span data-stu-id="9d238-219">[.NET Framework 4.7](https://www.microsoft.com/download/details.aspx?id=55167) or higher with SchUseStrongCrypto enabled in the registry (provided below)</span></span>
- <span data-ttu-id="9d238-220">SQL Skype for Business 2015 サーバーとバックエンドで更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d238-220">SQL must be updated on all Skype for Business 2015 servers and backends.</span></span> <span data-ttu-id="9d238-221">まず、Enterprise Edition Pool SQLバックエンド、次にそれぞれの FEs を更新します。</span><span class="sxs-lookup"><span data-stu-id="9d238-221">Update Enterprise Edition Pool SQL Backends first, then their respective FEs.</span></span> 
    - <span data-ttu-id="9d238-222">[SQL Server 2014 SP1 + CU5、](https://support.microsoft.com/help/3130926)またはより高い / SQL Server 2012 SP2 + CU16 以上 / [SQL Server 2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014)、またはより高い / SQL Server SP2</span><span class="sxs-lookup"><span data-stu-id="9d238-222">[SQL Server 2014 SP1 + CU5](https://support.microsoft.com/help/3130926), or higher / SQL Server 2012 SP2 + CU16 or higher / [SQL Server 2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014), or higher / SQL Server 2014 SP2</span></span>
     - [<span data-ttu-id="9d238-223">SQL Server 2012 年のネイティブ SQL Server クライアント</span><span class="sxs-lookup"><span data-stu-id="9d238-223">SQL Server Native Client for SQL Server 2012</span></span>](https://www.microsoft.com/download/details.aspx?id=50402)
     - <span data-ttu-id="9d238-224">[Microsoft ODBC Driver 11 for SQL Server](https://www.microsoft.com/download/details.aspx?id=36434)以上</span><span class="sxs-lookup"><span data-stu-id="9d238-224">[Microsoft ODBC Driver 11 for SQL Server](https://www.microsoft.com/download/details.aspx?id=36434), or higher</span></span>
     - [<span data-ttu-id="9d238-225">2014 SP2 の共有管理オブジェクトSQL Server 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="9d238-225">Shared Management Objects for SQL Server 2014 SP2</span></span>](https://www.microsoft.com/download/details.aspx?id=53164)
     - [<span data-ttu-id="9d238-226">SQLSysClrTypes for SQL server 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="9d238-226">SQLSysClrTypes for SQL server 2014 SP2</span></span>](https://www.microsoft.com/download/details.aspx?id=42295)

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a><span data-ttu-id="9d238-227">運用の推奨順序で前提条件をインストールするための基本的な手順</span><span class="sxs-lookup"><span data-stu-id="9d238-227">Basic steps to install pre-requisites, in recommended order of operations</span></span>

1. <span data-ttu-id="9d238-228">Skype for Business Server CU9 更新プログラムをすべてのサーバーにインストールします。</span><span class="sxs-lookup"><span data-stu-id="9d238-228">Install the Skype for Business Server CU9 update to all servers.</span></span> 
    1. <span data-ttu-id="9d238-229">アップデータを使用してコンポーネントに更新プログラムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="9d238-229">Install the update to components using the updater.</span></span>
    2. <span data-ttu-id="9d238-230">文書化された手順に従ってデータベースを更新します。</span><span class="sxs-lookup"><span data-stu-id="9d238-230">Update databases according to documented procedures.</span></span> <span data-ttu-id="9d238-231">Skype for Business Server 2015 の場合は、「KB [3061064」を参照してください](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)。</span><span class="sxs-lookup"><span data-stu-id="9d238-231">For Skype for Business Server 2015, see KB [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>
    3. <span data-ttu-id="9d238-232">他の変更を進む前に、展開で製品の機能を検証します。</span><span class="sxs-lookup"><span data-stu-id="9d238-232">Validate product functionality in the deployment prior to moving forward with any other changes.</span></span>
2. <span data-ttu-id="9d238-233">.NET 4.7 オフライン インストーラーをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="9d238-233">Download .NET 4.7 Offline Installer.</span></span> 
    1. <span data-ttu-id="9d238-234">リファレンス: [https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)</span><span class="sxs-lookup"><span data-stu-id="9d238-234">Reference: [https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)</span></span>
    2. <span data-ttu-id="9d238-235">フロント エンド サーバーで Skype for Business Server 2015 サービスが停止している必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d238-235">Ensure that Skype for Business Server 2015 services are stopped on the Front End server.</span></span>
    3. <span data-ttu-id="9d238-236">リファレンス: [https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="9d238-236">Reference: [https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span></span>
    4. <span data-ttu-id="9d238-237">Ex (Standard Edition): ```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="9d238-237">Ex (Standard Edition): ```Stop-CsWindowsService```</span></span>
    5. <span data-ttu-id="9d238-238">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="9d238-238">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    6. <span data-ttu-id="9d238-239">インストーラー パッケージを実行します。</span><span class="sxs-lookup"><span data-stu-id="9d238-239">Run the installer package.</span></span>
    7. <span data-ttu-id="9d238-240">サーバーを再起動します。</span><span class="sxs-lookup"><span data-stu-id="9d238-240">Reboot the server.</span></span>
3. <span data-ttu-id="9d238-241">すべてのSQL Express 2014 を更新します。</span><span class="sxs-lookup"><span data-stu-id="9d238-241">Update SQL Express 2014 on all servers.</span></span> 
    1. <span data-ttu-id="9d238-242">リファレンス: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span><span class="sxs-lookup"><span data-stu-id="9d238-242">Reference: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span></span>
    2. <span data-ttu-id="9d238-243">ダウンロード SQL 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="9d238-243">Download SQL 2014 SP2</span></span> 
        - <span data-ttu-id="9d238-244">リファレンス: [https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)</span><span class="sxs-lookup"><span data-stu-id="9d238-244">Reference: [https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)</span></span>
    3. <span data-ttu-id="9d238-245">サーバー上のフォルダーにインストール メディアをコピーする (例: C:\01_2014SqlSp2)</span><span class="sxs-lookup"><span data-stu-id="9d238-245">Copy the installation media to a folder on the server (Ex: C:\01_2014SqlSp2)</span></span>
    4. <span data-ttu-id="9d238-246">フロント エンド サーバーで Skype for Business Server 2015 サービスが停止する</span><span class="sxs-lookup"><span data-stu-id="9d238-246">Ensure Skype for Business Server 2015 services are stopped on the Front End server</span></span> 
        - <span data-ttu-id="9d238-247">Ex (Standard Edition): ```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="9d238-247">Ex (Standard Edition): ```Stop-CsWindowsService```</span></span>
        - <span data-ttu-id="9d238-248">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="9d238-248">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    5. <span data-ttu-id="9d238-249">管理コマンド プロンプトを開き、インストール済みのすべてのコンポーネントとインスタンスをアップグレードする</span><span class="sxs-lookup"><span data-stu-id="9d238-249">Open an Admin Command Prompt, and upgrade all installed components and instances</span></span> 
        - <span data-ttu-id="9d238-250">例: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action=Patch /AllInstances</span><span class="sxs-lookup"><span data-stu-id="9d238-250">Example: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action=Patch /AllInstances</span></span>
4. <span data-ttu-id="9d238-251">ネイティブ クライアントSQL更新します。</span><span class="sxs-lookup"><span data-stu-id="9d238-251">Update SQL Native Client.</span></span> 
    1. <span data-ttu-id="9d238-252">リファレンス: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server) .</span><span class="sxs-lookup"><span data-stu-id="9d238-252">Reference: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span></span>
    2. <span data-ttu-id="9d238-253">からダウンロードする [https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)</span><span class="sxs-lookup"><span data-stu-id="9d238-253">Download from [https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)</span></span>
    3. <span data-ttu-id="9d238-254">フロント エンド サーバーで Skype for Business Server 2015 サービスが停止している必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d238-254">Ensure Skype for Business Server 2015 services are stopped on the Front End server.</span></span> 
        - <span data-ttu-id="9d238-255">Ex (Standard Edition): ```Stop-CsWindowsServices```</span><span class="sxs-lookup"><span data-stu-id="9d238-255">Ex (Standard Edition): ```Stop-CsWindowsServices```</span></span>
        - <span data-ttu-id="9d238-256">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="9d238-256">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    4. <span data-ttu-id="9d238-257">インストールされているSQLの実行を停止する</span><span class="sxs-lookup"><span data-stu-id="9d238-257">Stop the SQL instances installed from running</span></span> 
        - <span data-ttu-id="9d238-258">例: ```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="9d238-258">Ex: ```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```</span></span>
        - <span data-ttu-id="9d238-259">例: ```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="9d238-259">Ex: ```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```</span></span>
        - <span data-ttu-id="9d238-260">Ex (Standard Edition のみ): ```Get-Service 'MSSQL$RTC' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="9d238-260">Ex (Standard Edition Only): ```Get-Service 'MSSQL$RTC' | Stop-Service```</span></span>
    5. <span data-ttu-id="9d238-261">更新プログラムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="9d238-261">Install the update.</span></span>
5. <span data-ttu-id="9d238-262">TLS 1.2 (KB [3135244)](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)のサポートSQL Server ODBC Driver 11 を更新します。</span><span class="sxs-lookup"><span data-stu-id="9d238-262">Update ODBC Driver 11 for SQL Server to include support for TLS 1.2 (KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)).</span></span>
    1. <span data-ttu-id="9d238-263">ODBC [Driver 11 for SQL Server - Windows をダウンロードします](https://www.microsoft.com/download/confirmation.aspx?id=36434)。</span><span class="sxs-lookup"><span data-stu-id="9d238-263">Download [ODBC Driver 11 for SQL Server - Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434).</span></span>
    2. <span data-ttu-id="9d238-264">フロント エンド サーバーで Skype for Business Server 2015 サービスが停止している必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d238-264">Ensure that Skype for Business Server 2015 services are stopped on the Front End server.</span></span>
        - <span data-ttu-id="9d238-265">例 (Standard Edition): ```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="9d238-265">Example (Standard Edition): ```Stop-CsWindowsService```</span></span>
        - <span data-ttu-id="9d238-266">例 (Enterprise Edition): ```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="9d238-266">Example (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    3. <span data-ttu-id="9d238-267">更新プログラムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="9d238-267">Install the update.</span></span>
6. <span data-ttu-id="9d238-268">前提条件のレジストリ キーを展開します。</span><span class="sxs-lookup"><span data-stu-id="9d238-268">Deploy prerequisite registry keys.</span></span>

### <a name="pre-requisite-registry-keys"></a><span data-ttu-id="9d238-269">前提条件のレジストリ キー</span><span class="sxs-lookup"><span data-stu-id="9d238-269">Pre-requisite registry keys</span></span>

<span data-ttu-id="9d238-270">次のテストをメモ帳にコピー/貼り付け、TLSPreReq.reg または選択した名前の名前を変更してからインポートします。</span><span class="sxs-lookup"><span data-stu-id="9d238-270">Copy/paste the following test into Notepad and rename TLSPreReq.reg or a name of your choice, then import:</span></span>

```console
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\v2.0.50727]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\v4.0.30319]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v2.0.50727]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v4.0.30319]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp]

"DefaultSecureProtocols"=dword:00000AA0

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp]

"DefaultSecureProtocols"=dword:00000AA0

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2\Client]

"DisabledByDefault"=dword:00000000

"Enabled"=dword:00000001

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2\Server]

"DisabledByDefault"=dword:00000000

"Enabled"=dword:00000001
```

<span data-ttu-id="9d238-271">Enterprise Edition SQLバック エンドの場合、前提条件と TLS の無効化は、すべての更新プログラムまたは OS 更新プログラムSQL扱う必要があります。参照: [https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](./patch-or-update-a-back-end-or-standard-edition-server.md)</span><span class="sxs-lookup"><span data-stu-id="9d238-271">For SQL back ends for Enterprise Edition Pools, prerequisites and TLS disable should be treated as any SQL or OS updates would; refer to: [https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](./patch-or-update-a-back-end-or-standard-edition-server.md)</span></span>

<span data-ttu-id="9d238-272">必須アプリケーションと TLS 無効化の両方の手順を組み合わせることができますが、すべての前提条件を適用してから、オペレーティング システム レベルで TLS 1.0 と 1.1 を無効にすることを強く推奨します。</span><span class="sxs-lookup"><span data-stu-id="9d238-272">While both the prerequisite application and TLS disabling steps can be combined, we strongly recommend all prerequisites be applied before proceeding with disabling of TLS 1.0 and 1.1 at the operating system level.</span></span> <span data-ttu-id="9d238-273">ベスト プラクティスの方法は、すべての前提条件を展開し、すべてのワークロードが正しく正常に機能していることを検証し、後で TLS 1.0/1.1 を無効にすることで環境を準備します。</span><span class="sxs-lookup"><span data-stu-id="9d238-273">The best practice approach would be to prepare the environment by deploying all prerequisites, validating that workloads all function correctly and as expected, and then proceeding with TLS 1.0/1.1 disable at a later time.</span></span>

### <a name="disable-tls-10-and-11-via-registry-import"></a><span data-ttu-id="9d238-274">レジストリ インポートを使用して TLS 1.0 および 1.1 を無効にする</span><span class="sxs-lookup"><span data-stu-id="9d238-274">Disable TLS 1.0 and 1.1 via registry import</span></span>

<span data-ttu-id="9d238-275">次の手順に進む前に、すべての前提条件を完了し *、Skype for Business Servers を更新してください*。</span><span class="sxs-lookup"><span data-stu-id="9d238-275">Before you proceed with the next steps, *make sure you have completed all prerequisites and updated Skype for Business Servers*.</span></span>

<span data-ttu-id="9d238-276">次のテキストをメモ帳ファイルにコピーし **、TLSDisable.reg の名前を変更します**。</span><span class="sxs-lookup"><span data-stu-id="9d238-276">Copy the following text into a Notepad file and rename it **TLSDisable.reg**:</span></span>

```console
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Cryptography\Configuration\SSL\00010002]

"Functions"="TLS_ECDHE_ECDSA_WITH_AES_256_GCM_SHA384_P384,TLS_ECDHE_ECDSA_WITH_AES_128_GCM_SHA256_P256,TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384_P384,TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256_P256,TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA384_P384,TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA256_P256,TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384_P384,TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256_P256,TLS_RSA_WITH_AES_256_GCM_SHA384,TLS_RSA_WITH_AES_128_GCM_SHA256,TLS_RSA_WITH_AES_256_CBC_SHA256,TLS_RSA_WITH_AES_128_CBC_SHA256"

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL]

"AllowInsecureRenegoClients"=dword:00000000

"AllowInsecureRenegoServers"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\AES 128/128]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\AES 256/256]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\DES 56/56]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\NULL]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 128/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 40/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 56/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 56/56]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 128/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 40/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 56/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 64/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\Triple DES 168]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\MD5]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA256]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA384]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA512]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms\Diffie-Hellman]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms\ECDH]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms\PKCS]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\Multi-Protocol Unified Hello]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\Multi-Protocol Unified Hello\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\Multi-Protocol Unified Hello\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\PCT 1.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\PCT 1.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\PCT 1.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 2.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 2.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 2.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 3.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 3.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 3.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000
```

<span data-ttu-id="9d238-277">TLS 1.0 および 1.1 を無効にする各サーバーに .reg ファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="9d238-277">Import the .reg file on each server you wish to disable TLS 1.0 and 1.1.</span></span> <span data-ttu-id="9d238-278">サーバーを再起動します。</span><span class="sxs-lookup"><span data-stu-id="9d238-278">Reboot the server.</span></span> <span data-ttu-id="9d238-279">サービスがオンラインに戻ったら、次のサーバーに移動します。</span><span class="sxs-lookup"><span data-stu-id="9d238-279">Once the services have come back online, move to the next server.</span></span> <span data-ttu-id="9d238-280">Enterprise Edition プールのアプローチは、OS 更新プログラムと同じです。</span><span class="sxs-lookup"><span data-stu-id="9d238-280">The approach for Enterprise Edition Pools is the same you would take for any OS update.</span></span>

<span data-ttu-id="9d238-281">ここでは、TLS 1.0 と 1.1 を無効にする以上の機能を行っていることに気付いた可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9d238-281">You may have noticed we are doing more than just disabling TLS 1.0 and 1.1 here.</span></span> <span data-ttu-id="9d238-282">上記のように、暗号スイートの再注文と、いくつかの古い弱暗号の無効化をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="9d238-282">We are supporting Cipher Suite re-order (as shown above) and the disabling of some older weak ciphers.</span></span> <span data-ttu-id="9d238-283">Skype for Business Server で SCHANNEL と Crypto API に対するこれらの変更を公式にサポートしたのはこれが初めてであり、この時点でサポートおよびテストした変更は、これらの変更のみである点に注意することが重要です。</span><span class="sxs-lookup"><span data-stu-id="9d238-283">This is the first time we have officially supported these changes to SCHANNEL and Crypto API on Skype for Business Server, and it is important to note that these changes are the only ones we support and have tested at this time.</span></span> <span data-ttu-id="9d238-284">今後、追加の構成を検討する場合がありますが、今のところ、実装内のレジストリ インポート ファイルは変更しない必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d238-284">We may consider additional configurations in the future, but for now, please do not modify the registry import file in your implementation.</span></span>

### <a name="validate-that-workloads-are-functioning-as-expected"></a><span data-ttu-id="9d238-285">ワークロードが期待通り機能しているのを検証する</span><span class="sxs-lookup"><span data-stu-id="9d238-285">Validate that workloads are functioning as expected</span></span>

<span data-ttu-id="9d238-286">環境で TLS 1.0 と 1.1 を無効にしたら、IM & Presence、P2P 呼び出し、エンタープライズ VoIP など、すべての主要なワークロードが期待通り機能している必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d238-286">Once TLS 1.0 and 1.1 have been disabled in your environment, ensure that all your main workloads are functioning as expected, such as IM & Presence, P2P calls, Enterprise Voice, etc.</span></span>

<span data-ttu-id="9d238-287">**使用されている TLS 1.2 のみを検証する**</span><span class="sxs-lookup"><span data-stu-id="9d238-287">**Validate only TLS 1.2 is being used**</span></span>

<span data-ttu-id="9d238-288">セキュリティ チームに Skype for Business トラフィックの新しい監査を実行して、古いプロトコル TLS 1.0 と 1.1 が使用されなくなったか確認します。</span><span class="sxs-lookup"><span data-stu-id="9d238-288">Have your Security Team perform a new audit of Skype for Business traffic to ensure that the older protocols TLS 1.0 and 1.1 are no longer in use.</span></span>

<span data-ttu-id="9d238-289">または、Internet Explorer を使用して、TLS 1.0 および TLS 1.1 が無効にされた後、Skype for Business Server 2015 から Web サービスへの TLS 接続をテストできます。</span><span class="sxs-lookup"><span data-stu-id="9d238-289">Alternatively, you can use Internet Explorer to test TLS connections to web services from Skype for Business Server 2015 after TLS 1.0 and TLS 1.1 have been disabled.</span></span>

1. <span data-ttu-id="9d238-290">起動Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="9d238-290">Launch Internet Explorer.</span></span>
2. <span data-ttu-id="9d238-291">[ツール **インターネット**  >  **オプション] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="9d238-291">Select **Tools** > **Internet Options**.</span></span>
3. <span data-ttu-id="9d238-292">[**詳細設定**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="9d238-292">Select the **Advanced** tab.</span></span>
4. <span data-ttu-id="9d238-293">[設定 **] の** 下までスクロールします。</span><span class="sxs-lookup"><span data-stu-id="9d238-293">Under **Settings**, scroll to the bottom.</span></span>
5. <span data-ttu-id="9d238-294">TLS 1.0、TLS 1.1、および TLS 1.2 が有効になっているか確認します。</span><span class="sxs-lookup"><span data-stu-id="9d238-294">Verify that TLS 1.0, TLS 1.1, and TLS 1.2 are enabled.</span></span>
6. <span data-ttu-id="9d238-295">SfB 2015 プールの内部 Web サービス URL を参照します (正常に接続する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="9d238-295">Browse the Internal Web Service URL of your SfB 2015 pool (should connect successfully).</span></span>
7. <span data-ttu-id="9d238-296">[TLS **1.2** Internet Explorerを使用する] オプションを無効にします。</span><span class="sxs-lookup"><span data-stu-id="9d238-296">Go back into Internet Explorer and disable the option to **Use TLS 1.2** only.</span></span>
8. <span data-ttu-id="9d238-297">SfB 2015 プールの内部 Web サービス URL を再度参照します (接続に失敗する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="9d238-297">Browse the Internal Web Service URL of your SfB 2015 pool again (should fail to connect).</span></span>

![インターネット オプション](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a><span data-ttu-id="9d238-299">高度な展開シナリオ</span><span class="sxs-lookup"><span data-stu-id="9d238-299">Advanced deployment scenarios</span></span>

<span data-ttu-id="9d238-300">Skype for Business Server 2015 で TLS 1.2 をサポートするには、いくつかの依存関係の前提条件が必要なので、TLS 1.0 および 1.1 が無効になっているシステムでは RTM メディアからのインストールが失敗します。</span><span class="sxs-lookup"><span data-stu-id="9d238-300">Because some dependency prerequisites are required to support TLS 1.2 in Skype for Business Server 2015, installing from RTM media will fail on any system where TLS 1.0 and 1.1 have been disabled.</span></span>

<span data-ttu-id="9d238-301">**環境で TLS 1.0 と 1.1 が無効にされた後に、新しい Standard Edition サーバーまたは Enterprise Edition プールを展開します。**</span><span class="sxs-lookup"><span data-stu-id="9d238-301">**Deploying New Standard Edition Servers or Enterprise Edition Pools once TLS 1.0 and 1.1 have been disabled in your environment.**</span></span>

<span data-ttu-id="9d238-302">**オプション 1:**[SmartSetup を使用します](../../deploy/install/install-skype-for-business-server.md)。</span><span class="sxs-lookup"><span data-stu-id="9d238-302">**Option 1:** Use [SmartSetup](../../deploy/install/install-skype-for-business-server.md).</span></span> <span data-ttu-id="9d238-303">更新されたバイナリを将来の CU に対応SQL SmartSetup を更新中であり、今後この記事を更新する予定です。</span><span class="sxs-lookup"><span data-stu-id="9d238-303">Note that we are updating SmartSetup to accommodate the updated SQL binaries in a future CU, and will update this article in the future.</span></span>

<span data-ttu-id="9d238-304">**オプション 2:** ローカル インスタンスの事前インストールSQL (RTCLOCAL および LYNCLOCAL)</span><span class="sxs-lookup"><span data-stu-id="9d238-304">**Option 2:** Pre-install local SQL instances (RTCLOCAL and LYNCLOCAL)</span></span>

1. <span data-ttu-id="9d238-305">Express 2014 SP2 (SQL) を FE のローカル フォルダーにダウンロードSQLEXPR_x64.exeコピーします。</span><span class="sxs-lookup"><span data-stu-id="9d238-305">Download and copy SQL Express 2014 SP2 (SQLEXPR_x64.exe) to local folder on FE.</span></span> <span data-ttu-id="9d238-306">たとえば、フォルダー パスが<SQL_FOLDER_PATH>。</span><span class="sxs-lookup"><span data-stu-id="9d238-306">Let’s say folder path <SQL_FOLDER_PATH>.</span></span>
2. <span data-ttu-id="9d238-307">PowerShell またはコマンド プロンプトを起動し、<SQL_FOLDER_PATH ファイルに>。</span><span class="sxs-lookup"><span data-stu-id="9d238-307">Launch PowerShell or Command Prompt and navigate to <SQL_FOLDER_PATH>.</span></span>
3. <span data-ttu-id="9d238-308">以下のコマンドを実行してSQL RTCLOCAL インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="9d238-308">Create the RTCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="9d238-309">次の処理がSQLEXPR_x64.exeするまで待ちます。</span><span class="sxs-lookup"><span data-stu-id="9d238-309">Wait until SQLEXPR_x64.exe finishes before proceeding:</span></span>

    <span data-ttu-id="9d238-310">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=RTCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automati</span><span class="sxs-lookup"><span data-stu-id="9d238-310">SQLEXPR_x64.exe  /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=RTCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automati</span></span>
1. <span data-ttu-id="9d238-311">以下のコマンドを実行SQL LYNCLOCAL サーバー インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="9d238-311">Create the LYNCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="9d238-312">次の手順SQLEXPR_x64.exe進む前に、次の手順が完了するまで待ちます。</span><span class="sxs-lookup"><span data-stu-id="9d238-312">Wait until SQLEXPR_x64.exe finishes before proceeding to the next step:</span></span>

    <span data-ttu-id="9d238-313">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=LYNCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automatic</span><span class="sxs-lookup"><span data-stu-id="9d238-313">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=LYNCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automatic</span></span>
1. <span data-ttu-id="9d238-314">Skype for Business Server 2015 RTM セットアップを実行します。</span><span class="sxs-lookup"><span data-stu-id="9d238-314">Run Skype for Business Server 2015 RTM setup.</span></span>
2. <span data-ttu-id="9d238-315">上記の前提条件セクションの残りの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="9d238-315">Follow the remaining steps from the prerequisites section above.</span></span>

<span data-ttu-id="9d238-316">**オプション 3:** 次のように、ローカル インストール メディア ディレクトリのバイナリを手動で置き換えすることもできます。</span><span class="sxs-lookup"><span data-stu-id="9d238-316">**Option 3:** You may also manually replace binaries in a local installation media directory as follows:</span></span>

1. [<span data-ttu-id="9d238-317">Skype for Business Server の前提条件をインストールする</span><span class="sxs-lookup"><span data-stu-id="9d238-317">Install prerequisites for Skype for Business Server</span></span>](../../deploy/install/install-prerequisites.md)  
2. <span data-ttu-id="9d238-318">.NET 4.7 をインストールします。</span><span class="sxs-lookup"><span data-stu-id="9d238-318">Install .NET 4.7:</span></span> 
      - <span data-ttu-id="9d238-319">**注:** 最初に、Skype for Business Server 2015 CU5 (6.0.9319.281) で .NET 4.7 のサポートが導入されました。</span><span class="sxs-lookup"><span data-stu-id="9d238-319">**Note:** We first introduced support for .NET 4.7 in Skype for Business Server 2015 CU5 (6.0.9319.281).</span></span> <span data-ttu-id="9d238-320">したがって、以下の後の手順では、メイン インストールの前にコア コンポーネントを更新します。</span><span class="sxs-lookup"><span data-stu-id="9d238-320">Therefore, in later steps below we will be updating Core Components prior to the main install.</span></span>
      - <span data-ttu-id="9d238-321">ダウンロード: https://www.microsoft.com/download/details.aspx?id=55167 .</span><span class="sxs-lookup"><span data-stu-id="9d238-321">Download: https://www.microsoft.com/download/details.aspx?id=55167.</span></span> 
      - <span data-ttu-id="9d238-322">リファレンス: [Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)展開の前にインストールする必要があるソフトウェア</span><span class="sxs-lookup"><span data-stu-id="9d238-322">Reference: [Software that should be installed before a Skype for Business Server 2015 deployment](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span></span>
3. <span data-ttu-id="9d238-323">ISO ファイル/フォルダーのコピー:</span><span class="sxs-lookup"><span data-stu-id="9d238-323">Copy ISO Files/Folders:</span></span> 
    - <span data-ttu-id="9d238-324">Skype for Business Server 2015 ISO が接続されている場合は、添付されているドライブのルート ディレクトリ (エクスプローラーで Ex: D: ) を \) 開きます。</span><span class="sxs-lookup"><span data-stu-id="9d238-324">With the Skype for Business Server 2015 ISO attached, open the root directory of the drive it is attached as (Ex: D:\) in File Explorer.</span></span>
    - <span data-ttu-id="9d238-325">すべてのフォルダーとファイルをローカル ディスク上のフォルダーにコピーします (例: C:\SkypeForBusiness2015ISO)。</span><span class="sxs-lookup"><span data-stu-id="9d238-325">Copy all folders and files to a folder on a local disk (Ex: C:\SkypeForBusiness2015ISO).</span></span>
    - <span data-ttu-id="9d238-326">**注:** コンポーネントをインストールする前に、TLS 1.2 のサポートのために一部のファイルを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d238-326">**Note:** Prior to installing components, some files will need to be updated for support of TLS 1.2.</span></span>
4. <span data-ttu-id="9d238-327">MSI/EXE パッケージを置き換える:</span><span class="sxs-lookup"><span data-stu-id="9d238-327">Replace MSI/EXE Packages:</span></span> 
    - <span data-ttu-id="9d238-328">ローカル コンピューター上のインストール メディアの /Setup/amd64/ フォルダーにある既存の MSI パッケージと EXE パッケージを置き換える。</span><span class="sxs-lookup"><span data-stu-id="9d238-328">Replace the existing MSI and EXE packages in the /Setup/amd64/ folder of the installation media on the local machine.</span></span>
    - <span data-ttu-id="9d238-329">SQL 2014 SP2 Express: https://www.microsoft.com/download/details.aspx?id=53167</span><span class="sxs-lookup"><span data-stu-id="9d238-329">SQL 2014 SP2 Express: https://www.microsoft.com/download/details.aspx?id=53167</span></span> 
        - <span data-ttu-id="9d238-330">ローカル コンピューター SQLEXPR_x64に名前を変更し、インストール メディアの Setup/amd64/フォルダーにある既存のファイルを置き換える。</span><span class="sxs-lookup"><span data-stu-id="9d238-330">Rename to SQLEXPR_x64 on the local machine, and replace the existing file in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="9d238-331">SQLネイティブ クライアント: https://www.microsoft.com/download/details.aspx?id=50402</span><span class="sxs-lookup"><span data-stu-id="9d238-331">SQL Native Client: https://www.microsoft.com/download/details.aspx?id=50402</span></span> 
        - <span data-ttu-id="9d238-332">**注:** 必要に応じて、sqlncli.msi名前を変更し、インストール メディアの Setup/amd64/フォルダーに存在する既存のファイルを置き換える。</span><span class="sxs-lookup"><span data-stu-id="9d238-332">**Note:** Rename this if necessary to sqlncli.msi, and then replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="9d238-333">SQL管理オブジェクト: https://www.microsoft.com/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="9d238-333">SQL Management Objects: https://www.microsoft.com/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="9d238-334">**注:** フィーチャー パックには、ダウンロードできるアイテムが多く含まれます。</span><span class="sxs-lookup"><span data-stu-id="9d238-334">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="9d238-335">[ダウンロードのみ] をSharedManagementObjects.msiします。</span><span class="sxs-lookup"><span data-stu-id="9d238-335">Select to download SharedManagementObjects.msi only.</span></span>
        - <span data-ttu-id="9d238-336">**注:** インストール メディアの Setup/amd64/フォルダーに存在する既存のファイルを置き換える。</span><span class="sxs-lookup"><span data-stu-id="9d238-336">**Note:** Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="9d238-337">SQL CLR 型: https://www.microsoft.com/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="9d238-337">SQL CLR Types: https://www.microsoft.com/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="9d238-338">**注:** フィーチャー パックには、ダウンロードできるアイテムが多く含まれます。</span><span class="sxs-lookup"><span data-stu-id="9d238-338">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="9d238-339">[選択] をクリックしてCQLSysClrTypes.msiのみ</span><span class="sxs-lookup"><span data-stu-id="9d238-339">Select to download CQLSysClrTypes.msi only</span></span>
        - <span data-ttu-id="9d238-340">**注**: インストール メディアの Setup/amd64/フォルダーに存在する既存のファイルを置き換える。</span><span class="sxs-lookup"><span data-stu-id="9d238-340">**Note**: Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
5. <span data-ttu-id="9d238-341">コア コンポーネントのインストール:</span><span class="sxs-lookup"><span data-stu-id="9d238-341">Install Core Components:</span></span> 
    - <span data-ttu-id="9d238-342">インストール メディアSetup.exeセットアップ/amd64/フォルダーからファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="9d238-342">Run Setup.exe from the Setup/amd64/ folder of the installation media.</span></span> <span data-ttu-id="9d238-343">手順に従ってコア コンポーネントをインストールする</span><span class="sxs-lookup"><span data-stu-id="9d238-343">Follow the instructions to install Core Components</span></span>
    - <span data-ttu-id="9d238-344">コア コンポーネントを閉じます。</span><span class="sxs-lookup"><span data-stu-id="9d238-344">Close Core Components.</span></span>
6. <span data-ttu-id="9d238-345">コア コンポーネントの更新:</span><span class="sxs-lookup"><span data-stu-id="9d238-345">Update Core Components:</span></span> 
    - <span data-ttu-id="9d238-346">Skype for Business Update インストーラーをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="9d238-346">Download the Skype for Business Update Installer.</span></span>
    - <span data-ttu-id="9d238-347">インストーラーを実行してコア コンポーネントを更新し、パフォーマンス カウンターをインストールします。</span><span class="sxs-lookup"><span data-stu-id="9d238-347">Run the installer to update Core Components and install the performance counters.</span></span>
    - <span data-ttu-id="9d238-348">**注:** CU6HF2 のリリースの現在、自動更新機能は現在 CU6 までインストールされます。</span><span class="sxs-lookup"><span data-stu-id="9d238-348">**Note:** As of the release of CU6HF2, the auto-update feature currently only will install up to CU6.</span></span> <span data-ttu-id="9d238-349">したがって、コア コンポーネントを 6.0.9319.516 に更新するには、アップデータを個別に実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d238-349">Therefore, the updater must be run separately to update Core Components to 6.0.9319.516.</span></span>
    - <span data-ttu-id="9d238-350">リファレンス: https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015</span><span class="sxs-lookup"><span data-stu-id="9d238-350">Reference: https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015</span></span>
7. <span data-ttu-id="9d238-351">管理ツールのインストール (オプション):</span><span class="sxs-lookup"><span data-stu-id="9d238-351">Install Administrative Tools (Optional):</span></span> 
    - <span data-ttu-id="9d238-352">これにより、Microsoft SQL Server 2012 ネイティブ クライアント、SQL Server 2014 管理オブジェクト (x64)、および更新されたファイルを使用して microsoft System CLR Types for SQL Server 2014 (x64) がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="9d238-352">This will install the Microsoft SQL Server 2012 Native Client, SQL Server 2014 Management Objects (x64), and Microsoft System CLR Types for SQL Server 2014 (x64) using the updated files.</span></span> <span data-ttu-id="9d238-353">さらに、Skype for Business Server 2015 トポロジ ビルダーとコントロール パネルは、ローカル コンピューターで使用できます。</span><span class="sxs-lookup"><span data-stu-id="9d238-353">Additionally, the Skype for Business Server 2015 Topology Builder and Control Panel will be available on the local machine.</span></span>
8. <span data-ttu-id="9d238-354">ローカル構成ストアのインストール (手順 1):</span><span class="sxs-lookup"><span data-stu-id="9d238-354">Install Local Configuration Store (Step 1):</span></span> 
     - <span data-ttu-id="9d238-355">展開ウィザードを開き、[Skype for Business Server System のインストールまたは更新] をクリックし、[手順 1: ローカル構成ストアのインストール] で [実行] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d238-355">Open the Deployment Wizard, click Install or Update Skype for Business Server System, and click on **Run** at Step 1: Install Local Configuration Store.</span></span>
     - <span data-ttu-id="9d238-356">[ローカル **構成ストアの** インストール **] ダイアログ ボックスの [次へ** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d238-356">Click **Next** in the **Install Local Configuration Store** dialog box.</span></span>
     <span data-ttu-id="9d238-357">![[ローカル構成ストアのインストール] ダイアログ ボックス](../../media/local-configuration-store.png)</span><span class="sxs-lookup"><span data-stu-id="9d238-357">![Install Local Configuration Store dialog box](../../media/local-configuration-store.png)</span></span>
     - <span data-ttu-id="9d238-358">結果を確認し、[タスクの状態] が [完了] に設定されています。</span><span class="sxs-lookup"><span data-stu-id="9d238-358">Review the results, and ensure that the Task Status is Completed.</span></span> <span data-ttu-id="9d238-359">[ログの表示] をクリックして、結果のログ ファイル **を確認します**。</span><span class="sxs-lookup"><span data-stu-id="9d238-359">Review the resulting log file by clicking **View Log**.</span></span>
     <span data-ttu-id="9d238-360">![タスクの状態が [完了] と表示される](../../media/local-configuration-task-completed.png)</span><span class="sxs-lookup"><span data-stu-id="9d238-360">![Task status shows as Completed](../../media/local-configuration-task-completed.png)</span></span>
     - <span data-ttu-id="9d238-361">**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d238-361">Click **Finish**.</span></span>
9. <span data-ttu-id="9d238-362">Skype for Business Server コンポーネントのセットアップまたは削除 (手順 2):</span><span class="sxs-lookup"><span data-stu-id="9d238-362">Set up or remove Skype for Business Server Components (Step 2):</span></span>
    - <span data-ttu-id="9d238-363">展開ウィザードを開き **、[Skype for Business Server** System のインストールまたは更新] をクリックし、[手順 2: Skype for Business Server コンポーネントのセットアップまたは削除] で [実行] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d238-363">Open the Deployment Wizard, click **Install or Update Skype for Business Server System**, and click **Run** at Step 2: Set up or Remove Skype for Business Server Components</span></span>
    - <span data-ttu-id="9d238-364">[Skype **for** Business Server コンポーネントのセットアップ] ダイアログ ボックスの [次へ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d238-364">Click **Next** in the Set Up Skype for Business Server Components dialog box.</span></span>
    <span data-ttu-id="9d238-365">![[Skype for Business Server コンポーネントのセットアップ] ウィンドウ](../../media/set-up-skype-for-business-server-components-window.png)</span><span class="sxs-lookup"><span data-stu-id="9d238-365">![the Set Up Skype for Business Server Components window](../../media/set-up-skype-for-business-server-components-window.png)</span></span>
    - <span data-ttu-id="9d238-366">[ログの表示] を使用してログを確認し、問題なくセットアップが完了したと検証します。</span><span class="sxs-lookup"><span data-stu-id="9d238-366">Review the log using View Log, and validate that setup completed without issues.</span></span> 
    - <span data-ttu-id="9d238-367">**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d238-367">Click **Finish**.</span></span>
10. <span data-ttu-id="9d238-368">必要に応じて追加のインストールと構成を続行します (この時点で通常のインストール手順を再開できます)。</span><span class="sxs-lookup"><span data-stu-id="9d238-368">Proceed with additional installation and configuration as required (you can resume normal installation procedures at this point).</span></span>