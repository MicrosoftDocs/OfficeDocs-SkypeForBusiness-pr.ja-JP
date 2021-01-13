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
description: '概要: 環境での TLS 1.0 および 1.1 の無効化を準備して実装します。'
ms.openlocfilehash: da76280540f9d18435ed929aace6cf6fc439a4cf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826397"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a><span data-ttu-id="e35e9-103">Skype for Business Server 2015 で TLS 1.0/1.1 を無効にする</span><span class="sxs-lookup"><span data-stu-id="e35e9-103">Disable TLS 1.0/1.1 in Skype for Business Server 2015</span></span>

<span data-ttu-id="e35e9-104">この記事の目的は、環境で TLS 1.0 および 1.1 の無効化を準備および実装するために必要なガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="e35e9-104">The purpose of this article is to provide the necessary guidance for you to prepare for and implement disabling TLS 1.0 and 1.1 in your environments.</span></span> <span data-ttu-id="e35e9-105">このプロセスでは、広範な計画と準備が必要です。</span><span class="sxs-lookup"><span data-stu-id="e35e9-105">This process requires extensive planning and preparation.</span></span> <span data-ttu-id="e35e9-106">組織で TLS 1.0 と 1.1 を無効にする計画を立て、この記事のすべての情報を慎重に確認してください。</span><span class="sxs-lookup"><span data-stu-id="e35e9-106">Please carefully review all of the information in this article as you make your plan to disable TLS 1.0 and 1.1 for your organization.</span></span> <span data-ttu-id="e35e9-107">TLS 1.0/1.1 を無効にすることで影響を受け得る多くの外部依存関係と接続条件があります。そのため、広範囲の計画とテストが必要です。</span><span class="sxs-lookup"><span data-stu-id="e35e9-107">Note that there are many external dependencies and connectivity conditions that could be impacted by disabling TLS 1.0/1.1, so extensive planning and testing is warranted.</span></span>

## <a name="in-this-article"></a><span data-ttu-id="e35e9-108">この記事の内容</span><span class="sxs-lookup"><span data-stu-id="e35e9-108">In this article</span></span>

- [<span data-ttu-id="e35e9-109">バックグラウンドとスコープ</span><span class="sxs-lookup"><span data-stu-id="e35e9-109">Background and scope</span></span>](#background)
- [<span data-ttu-id="e35e9-110">前提条件とプロセス</span><span class="sxs-lookup"><span data-stu-id="e35e9-110">Prerequisites and process</span></span>](#prerequisites-and-process)
- [<span data-ttu-id="e35e9-111">高度な展開シナリオ</span><span class="sxs-lookup"><span data-stu-id="e35e9-111">Advanced deployment scenarios</span></span>](#advanced-deployment-scenarios)

## <a name="background"></a><span data-ttu-id="e35e9-112">背景</span><span class="sxs-lookup"><span data-stu-id="e35e9-112">Background</span></span>

<span data-ttu-id="e35e9-113">TLS 1.0 および 1.1 を提供するための主要なドライバーは、Skype for Business Server On-Premises のサポートを無効にするための主要なドライバーは、Payment Card Industry (PCI) Security Standards Council および Federal Information Processing Standards の要件です。</span><span class="sxs-lookup"><span data-stu-id="e35e9-113">The primary drivers for providing TLS 1.0 and 1.1 disable support for Skype for Business Server On-Premises are Payment Card Industry (PCI) Security Standards Council and Federal Information Processing Standards requirements.</span></span> <span data-ttu-id="e35e9-114">PCI 要件の詳細については、こちらを参照 [してください](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls)。</span><span class="sxs-lookup"><span data-stu-id="e35e9-114">More information for PCI requirements can be found [here](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).</span></span>  <span data-ttu-id="e35e9-115">Microsoft は、お客様の組織がこれらの要件または他の要件に従う必要があるかどうかに関するガイダンスを提供できません。</span><span class="sxs-lookup"><span data-stu-id="e35e9-115">Microsoft cannot provide guidance on whether or not your organization is required to adhere to these or other requirements.</span></span> <span data-ttu-id="e35e9-116">環境で TLS 1.0 または 1.1 を無効にする必要があるかどうかを判断する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e35e9-116">You must determine if it is required for you to disable TLS 1.0 and/or 1.1 in your environments.</span></span>

<span data-ttu-id="e35e9-117">Microsoft では、TLS に関する[](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/)ホワイト ペーパーをここで作成しました。また、この Exchange ブログで利用できるバックグラウンドの閲覧をお[勧めします](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)。</span><span class="sxs-lookup"><span data-stu-id="e35e9-117">Microsoft has produced a white paper on TLS available [here](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/), and we also recommend the background reading available in this [Exchange blog](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/).</span></span>

## <a name="supportability-scope"></a><span data-ttu-id="e35e9-118">サポートスコープ</span><span class="sxs-lookup"><span data-stu-id="e35e9-118">Supportability Scope</span></span>

<span data-ttu-id="e35e9-119">*スコープとは* 、サポートの境界を指します。</span><span class="sxs-lookup"><span data-stu-id="e35e9-119">*Scope* refers to supportability boundaries.</span></span> <span data-ttu-id="e35e9-120">*完全にテストされ、* サポートされているということは、リストされている製品バージョンに対して TLS 1.0 と 1.1 の無効化を完全にサポートし、テスト済みです。</span><span class="sxs-lookup"><span data-stu-id="e35e9-120">*Fully tested and supported* means we fully support and have tested disabling of TLS 1.0 and 1.1 for the listed product versions.</span></span> <span data-ttu-id="e35e9-121">*現在調査中の場合* は、次の意味が必要です。これらの製品を TLS 無効化サポートの範囲に含め、積極的に調査中です。</span><span class="sxs-lookup"><span data-stu-id="e35e9-121">*Currently being investigated* means just that; we are actively investigating bringing these products into scope for TLS disable support.</span></span> <span data-ttu-id="e35e9-122">*スコープ外の* 場合、これらの製品バージョンは TLS 1.0 または 1.1 の無効化をサポートしていないので、示されている例外を除き機能しません。</span><span class="sxs-lookup"><span data-stu-id="e35e9-122">*Out of scope* means these product versions do not support disabling TLS 1.0 or 1.1 and will not work, with noted exceptions.</span></span>

### <a name="fully-tested-and-supported-servers"></a><span data-ttu-id="e35e9-123">完全にテストされ、サポートされているサーバー</span><span class="sxs-lookup"><span data-stu-id="e35e9-123">Fully tested and supported servers</span></span>

- <span data-ttu-id="e35e9-124">Skype for Business Server 2019 CU1 17.0.2046.123 (2019 年 6 月) 以上</span><span class="sxs-lookup"><span data-stu-id="e35e9-124">Skype for Business Server 2019 CU1 17.0.2046.123 (June 2019) or higher</span></span>
- <span data-ttu-id="e35e9-125">Skype for Business Server 2015 CU9 6.0.9319.548 (2019 年 5 月)、Windows Server 2012 (KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) 以上の更新プログラムを適用)、2012 R2 または 2016 以上。</span><span class="sxs-lookup"><span data-stu-id="e35e9-125">Skype for Business Server 2015 CU9 6.0.9319.548 (May 2019) or higher on Windows Server 2012 (with KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseding update), 2012 R2 or 2016.</span></span>
- <span data-ttu-id="e35e9-126">Windows Server 2008 R2、2012 年 (KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) または更新プログラムの代用)、または 2012 R2 の CU9 6.0.9319.548 (2019 年 5 月) 以上を使用する、一時アップグレードされた Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="e35e9-126">In-place Upgraded Skype for Business Server 2015, with CU9 6.0.9319.548 (May 2019) or higher on Windows Server 2008 R2, 2012 (with KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseding update), or 2012 R2.</span></span>
- <span data-ttu-id="e35e9-127">Exchange Connectivity and Outlook Web App with Exchange Server 2010 SP3 RU19 or higher, guidance [here](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span><span class="sxs-lookup"><span data-stu-id="e35e9-127">Exchange Connectivity and Outlook Web App with Exchange Server 2010 SP3 RU19 or higher, guidance [here](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span></span>
- <span data-ttu-id="e35e9-128">Skype for Business Server 2015 CU6 HF2 以上の存続可能ブランチ アプライアンス (SBA) (適切な更新プログラムがパッケージ化され、アプライアンスで利用可能にされたベンダーに確認してください)</span><span class="sxs-lookup"><span data-stu-id="e35e9-128">Survivable Branch Appliance (SBA) with Skype for Business Server 2015 CU6 HF2 or higher (confirm with your vendor that they packaged the appropriate updates and have been made available for your appliance)</span></span>
- <span data-ttu-id="e35e9-129">Skype for Business Server 2015 CU6 HF2 以上の存続可能ブランチ サーバー (SBS)</span><span class="sxs-lookup"><span data-stu-id="e35e9-129">Survivable Branch Server (SBS) with Skype for Business Server 2015 CU6 HF2 or higher</span></span>
- <span data-ttu-id="e35e9-130">Lync Server 2013 エッジの役割 **のみ**。これは、エッジの役割が Windows Fabric 1.0 に依存していないためです。</span><span class="sxs-lookup"><span data-stu-id="e35e9-130">Lync Server 2013 **Edge Role Only**, this is because Edge role does not have a dependency on Windows Fabric 1.0.</span></span>

### <a name="fully-tested-and-supported-clients"></a><span data-ttu-id="e35e9-131">完全にテストされ、サポートされているクライアント</span><span class="sxs-lookup"><span data-stu-id="e35e9-131">Fully tested and supported clients</span></span>

- <span data-ttu-id="e35e9-132">Lync 2013 (Skype for Business) デスクトップ クライアント、MSI、C2R (Basic [15.0.5023.1000 以上を含む](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334))</span><span class="sxs-lookup"><span data-stu-id="e35e9-132">Lync 2013 (Skype for Business) Desktop Client, MSI and C2R, including Basic [15.0.5023.1000 or higher](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)</span></span>
- <span data-ttu-id="e35e9-133">Skype for Business 2016 デスクトップ クライアント、MSI [16.0.4678.1000](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323)以上 (基本を含む)</span><span class="sxs-lookup"><span data-stu-id="e35e9-133">Skype for Business 2016 Desktop Client, MSI [16.0.4678.1000 or higher](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), including Basic</span></span>
- <span data-ttu-id="e35e9-134">Skype for Business 2016 Click to Run Require the [April 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) Updates:</span><span class="sxs-lookup"><span data-stu-id="e35e9-134">Skype for Business 2016 Click to Run Require the [April 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) Updates:</span></span> 
    - <span data-ttu-id="e35e9-135">月次およびSemi-Annual対象、16 \. \. 0 9126 \. 2152 以上</span><span class="sxs-lookup"><span data-stu-id="e35e9-135">Monthly and Semi-Annual Targeted, 16\.0\.9126\.2152 or higher</span></span>
    - <span data-ttu-id="e35e9-136">Semi-Annualおよび Deferred Channel、16 \. 0 \. 8431 \. 2242 以上</span><span class="sxs-lookup"><span data-stu-id="e35e9-136">Semi-Annual and Deferred Channel, 16\.0\.8431\.2242 or higher</span></span>
- <span data-ttu-id="e35e9-137">Mac 16.15 以上の Skype for Business</span><span class="sxs-lookup"><span data-stu-id="e35e9-137">Skype for Business on Mac 16.15 or higher</span></span>
- <span data-ttu-id="e35e9-138">Skype for Business for iOS および Android 6.19 以上</span><span class="sxs-lookup"><span data-stu-id="e35e9-138">Skype for Business for iOS and Android 6.19 or higher</span></span>
- <span data-ttu-id="e35e9-139">Microsoft Teams Rooms (以前の Skype Room System V2 SRS V2) 4.0.64.0 (2018 年 12 月) 以上</span><span class="sxs-lookup"><span data-stu-id="e35e9-139">Microsoft Teams Rooms (previously known as Skype Room System V2 SRS V2) 4.0.64.0 (December 2018) or higher</span></span>
- <span data-ttu-id="e35e9-140">KB4499162 (2019 年 5 月、OS ビルド 15063.1835) 以上に基づく Team エディションの Surface Hub 更新プログラム</span><span class="sxs-lookup"><span data-stu-id="e35e9-140">Surface Hub update for Team edition based on KB4499162 (May 2019, OS Build 15063.1835) or higher</span></span>
- <span data-ttu-id="e35e9-141">Skype Web App 2015 CU6 HF2 以上 (サーバーに含む)</span><span class="sxs-lookup"><span data-stu-id="e35e9-141">Skype Web App 2015 CU6 HF2 or higher (ships with Server)</span></span>

### <a name="currently-being-investigated"></a><span data-ttu-id="e35e9-142">現在調査中</span><span class="sxs-lookup"><span data-stu-id="e35e9-142">Currently being investigated</span></span>

- <span data-ttu-id="e35e9-143">通話品質ダッシュボード (TLS 1.0、1.1 が無効にされた後の新しいインストール(下記を参照)\*</span><span class="sxs-lookup"><span data-stu-id="e35e9-143">Call Quality Dashboard (new install after TLS 1.0, 1.1 have been disabled, see below)\*</span></span>
 
### <a name="out-of-scope"></a><span data-ttu-id="e35e9-144">対象外</span><span class="sxs-lookup"><span data-stu-id="e35e9-144">Out of scope</span></span>

<span data-ttu-id="e35e9-145">特に示されている場合を除き、次の製品は TLS 1.0/1.1 のサポートの対象ではなく、TLS 1.0 と 1.1 が無効になっている環境では機能しません。</span><span class="sxs-lookup"><span data-stu-id="e35e9-145">Except where noted, the following products are not in scope for TLS 1.0/1.1 disable support and will not function in an environment where TLS 1.0 and 1.1 have been disabled.</span></span> <span data-ttu-id="e35e9-146">つまり、スコープ外のサーバーまたはクライアントをまだ利用している場合は、Skype for Business Server のオンプレミス展開の任意の場所で TLS 1.0/1.1 を無効にする必要がある場合は、これらを更新または削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e35e9-146">What this means: if you still utilize out-of-scope servers or clients, you must update or remove these if you need to disable TLS 1.0/1.1 anywhere in your Skype for Business Server on-premises deployment.</span></span>

- <span data-ttu-id="e35e9-147">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e35e9-147">Lync Server 2013</span></span>
- <span data-ttu-id="e35e9-148">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="e35e9-148">Lync Server 2010</span></span>
- <span data-ttu-id="e35e9-149">Windows Server 2008 以下</span><span class="sxs-lookup"><span data-stu-id="e35e9-149">Windows Server 2008 or lower</span></span>
- <span data-ttu-id="e35e9-150">Lync for Mac 2011</span><span class="sxs-lookup"><span data-stu-id="e35e9-150">Lync for Mac 2011</span></span>
- <span data-ttu-id="e35e9-151">Lync 2013 for Mobile - iOS、iPad、Android、または Windows Phone</span><span class="sxs-lookup"><span data-stu-id="e35e9-151">Lync 2013 for Mobile - iOS, iPad, Android or Windows Phone</span></span>
- <span data-ttu-id="e35e9-152">Lync "MX" Windows ストア クライアント</span><span class="sxs-lookup"><span data-stu-id="e35e9-152">Lync "MX" Windows Store client</span></span>
- <span data-ttu-id="e35e9-153">Lync Room System (a.k.a.</span><span class="sxs-lookup"><span data-stu-id="e35e9-153">Lync Room System (a.k.a.</span></span> <span data-ttu-id="e35e9-154">SRSv1)。</span><span class="sxs-lookup"><span data-stu-id="e35e9-154">SRSv1).</span></span> <span data-ttu-id="e35e9-155">LRS は 2018 年 10 月 9 日にサポート終了に達し、TLS 1.2 をサポートするために更新されません。</span><span class="sxs-lookup"><span data-stu-id="e35e9-155">LRS reached end of support on October 9, 2018 and will not be updated to support TLS 1.2.</span></span>
- <span data-ttu-id="e35e9-156">すべての Lync 2010 クライアント</span><span class="sxs-lookup"><span data-stu-id="e35e9-156">All Lync 2010 clients</span></span>
- <span data-ttu-id="e35e9-157">Lync Phone Edition - ここで更新された [ガイダンス](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035)。</span><span class="sxs-lookup"><span data-stu-id="e35e9-157">Lync Phone Edition - updated guidance [here](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).</span></span>
- <span data-ttu-id="e35e9-158">2013 ベースの存続可能ブランチ アプライアンス (SBA) または存続可能ブランチ サーバー (SBS)</span><span class="sxs-lookup"><span data-stu-id="e35e9-158">2013 based Survivable Branch Appliance (SBA) or Survivable Branch Server (SBS)</span></span>
- <span data-ttu-id="e35e9-159">Cloud Connector エディション (CCE)</span><span class="sxs-lookup"><span data-stu-id="e35e9-159">Cloud Connector Edition (CCE)</span></span>
- <span data-ttu-id="e35e9-160">Skype for Business for Windows Phone</span><span class="sxs-lookup"><span data-stu-id="e35e9-160">Skype for Business for Windows Phone</span></span>

### <a name="exceptions"></a><span data-ttu-id="e35e9-161">例外</span><span class="sxs-lookup"><span data-stu-id="e35e9-161">Exceptions</span></span>

#### <a name="lync-server-2013"></a><span data-ttu-id="e35e9-162">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e35e9-162">Lync Server 2013</span></span>

<span data-ttu-id="e35e9-163">Lync Server 2013 は Windows Fabric バージョン 1.0 に依存します。</span><span class="sxs-lookup"><span data-stu-id="e35e9-163">Lync Server 2013 takes a dependency on Windows Fabric version 1.0.</span></span>  <span data-ttu-id="e35e9-164">Lync Server 2013 の設計フェーズでは、レプリケーション、高可用性、およびフォールト トレランスを実現するために、Windows Fabric 1.0 が魅力的で新しい分散アーキテクチャとして選択されました。</span><span class="sxs-lookup"><span data-stu-id="e35e9-164">In the design phase for Lync Server 2013, Windows Fabric 1.0 was chosen for its compelling and new distributed architecture to provide replication, high availability, and fault tolerance.</span></span>  <span data-ttu-id="e35e9-165">Skype for Business Server と Windows Fabric の両方で、この共同アーキテクチャは、後のバージョンで大幅に再設計され、時間のとともに大幅に改善されています。</span><span class="sxs-lookup"><span data-stu-id="e35e9-165">Over time, both Skype for Business Server and Windows Fabric have greatly improved this joint architecture with significant re-design in subsequent versions.</span></span>  <span data-ttu-id="e35e9-166">現在の Skype for Business 2015 Server では、たとえば Windows Fabric 3.0 を使用します。</span><span class="sxs-lookup"><span data-stu-id="e35e9-166">Current Skype for Business 2015 Server uses Windows Fabric 3.0, for example.</span></span>

<span data-ttu-id="e35e9-167">残念ながら、Windows Fabric 1.0 **では TLS 1.2 はサポートされていません。 ただし、TLS 1.2 で動作するために Lync Server 2013 を更新します**。</span><span class="sxs-lookup"><span data-stu-id="e35e9-167">Unfortunately, Windows Fabric 1.0 **does not support TLS 1.2.  However, we will be updating Lync Server 2013 to work with TLS 1.2**.</span></span> <span data-ttu-id="e35e9-168">これは、Lync Server 2013 の次の累積的な更新プログラムで提供される予定です。</span><span class="sxs-lookup"><span data-stu-id="e35e9-168">This will be coming in the next Cumulative Update for Lync Server 2013.</span></span>  <span data-ttu-id="e35e9-169">TLS 1.2 のサポートを提供して、共同存在、移行、フェデレーション、およびハイブリッドのシナリオを有効にします。</span><span class="sxs-lookup"><span data-stu-id="e35e9-169">We're providing TLS 1.2 support to enable co-existence, migration, federation, and hybrid scenarios.</span></span>

<span data-ttu-id="e35e9-170">組織で TLS 1.0 と 1.1 を無効にする必要がある場合に、現在 Lync Server 2013 を使用している場合は、計画プロセスを開始することをお勧めします。計画プロセスは、Skype for Business Server 2015 以上への一時アップグレードまたはサイド バイ サイド移行 (新しいプール、ユーザーの移動) が必要になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e35e9-170">If your organization is required to disable TLS 1.0 and 1.1, and you currently use Lync Server 2013, we recommend you begin your planning process, with the possibility you may have to In-place upgrade or Side-by-Side migrate (new pools, move users) to Skype for Business Server 2015 or higher.</span></span>  <span data-ttu-id="e35e9-171">または、Skype for Business Online への移行を加速したい場合があります。</span><span class="sxs-lookup"><span data-stu-id="e35e9-171">Or you may want to accelerate migration to Skype for Business Online.</span></span>

#### <a name="call-quality-dashboard"></a><span data-ttu-id="e35e9-172">通話品質ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="e35e9-172">Call Quality Dashboard</span></span>

<span data-ttu-id="e35e9-173">現在、オンプレミス通話品質ダッシュボードは、新しいインストール時 (オンプレミス環境への初回インストール時) に TLS 1.0 に依存しています。</span><span class="sxs-lookup"><span data-stu-id="e35e9-173">On-Premises Call Quality Dashboard currently has a dependency on TLS 1.0 during new install (first time installing into your On-Premises environments).</span></span>  <span data-ttu-id="e35e9-174">We are currently investigating this issue and plan to release a fix in the near future.</span><span class="sxs-lookup"><span data-stu-id="e35e9-174">We are currently investigating this issue and plan to release a fix in the near future.</span></span>  <span data-ttu-id="e35e9-175">CQD のインストールと TLS 1.0 の無効化を計画している場合は、まず CQD インストールを完了してから、TLS 1.0 の無効化に進みます。</span><span class="sxs-lookup"><span data-stu-id="e35e9-175">If you are planning to install CQD and also disable TLS 1.0, we recommend that you complete CQD installation first, and then proceed with TLS 1.0 disabling.</span></span>

#### <a name="skype-for-business-sdn-manager"></a><span data-ttu-id="e35e9-176">Skype for Business SDN Manager</span><span class="sxs-lookup"><span data-stu-id="e35e9-176">Skype for Business SDN Manager</span></span>

<span data-ttu-id="e35e9-177">新しいインストール時にデータベースSQL使用する Skype for Business SDN Manager は TLS 1.0 に依存します。</span><span class="sxs-lookup"><span data-stu-id="e35e9-177">Skype for Business SDN Manager using SQL a database has a dependency on TLS 1.0 during new install.</span></span> <span data-ttu-id="e35e9-178">SQL データベースを使用して Skype for Business SDN Manager をインストールし、TLS 1.0 も無効にする予定の場合は、最初に Skype for Business SDN Manager を完了してから、TLS 1.0 の無効化に進みます。</span><span class="sxs-lookup"><span data-stu-id="e35e9-178">If you are planning to install Skype for Business SDN Manager using SQL a database and also disable TLS 1.0, we recommend that you complete Skype for Business SDN Manager first, and then proceed with TLS 1.0 disabling.</span></span> <span data-ttu-id="e35e9-179">インストール前に TLS 1.0 が無効にされた場合は、Skype for Business SDN Manager SQL データベースをホストするために使用される SQL Server バックエンド サーバーで TLS 1.0 を一時的に有効に戻す必要があります。</span><span class="sxs-lookup"><span data-stu-id="e35e9-179">In case TLS 1.0 was disabled prior to installation, you should temporarily enabled TLS 1.0 back in SQL Server backend server that will be used to host Skype for Business SDN Manager SQL database.</span></span>

#### <a name="third-party-devices"></a><span data-ttu-id="e35e9-180">サード パーティ製デバイス</span><span class="sxs-lookup"><span data-stu-id="e35e9-180">Third-party devices</span></span>

<span data-ttu-id="e35e9-181">3PIP 電話、ビデオ会議、リバース プロキシ、ロード バランサーなどのサード パーティ製デバイスでは、TLS 1.2 のサポート可能性を検証し、慎重にテストし、必要に応じてベンダーに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="e35e9-181">On third-party devices such as 3PIP phones, Video conferencing, Reverse Proxies and Load Balancers, be sure to validate TLS 1.2 supportability, test carefully, and contact the vendor if needed.</span></span>

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a><span data-ttu-id="e35e9-182">エッジ サーバーで TLS 1.0/1.1 を無効にする場合のフェデレーションに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="e35e9-182">Federation considerations when disabling TLS 1.0/1.1 on Edge servers</span></span>

<span data-ttu-id="e35e9-183">エッジ サーバーで TLS 1.0/1.1 を無効にした場合の影響を慎重に計画し、検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e35e9-183">You must carefully plan for and consider the impact of disabling TLS 1.0/1.1 on your Edge servers.</span></span>  <span data-ttu-id="e35e9-184">TLS 1.0 および 1.1 を無効にすると、他の組織が組織とのフェデレーションを行えなくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e35e9-184">Once TLS 1.0 and 1.1 are disabled, you may find that other organizations are no longer be able to federate with your organization.</span></span>

<span data-ttu-id="e35e9-185">修正プログラムが適用されていない (SfB 2015、Lync 2013) 以前の (2010) 外部システムとの下位互換性を維持するために、エッジ サーバーで TLS 1.0/1.1 を有効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="e35e9-185">You may opt to keep TLS 1.0/1.1 enabled on your Edge servers to maintain backward compatibility with non-patched (SfB 2015, Lync 2013) or older (2010) external systems.</span></span>

<span data-ttu-id="e35e9-186">Microsoft は、お客様のエッジ ネットワーク (またはネットワーク) が PCI 標準に準拠するかどうかに関するアドバイスや推奨事項を提供できません。個別の会社によって決定される必要があります。</span><span class="sxs-lookup"><span data-stu-id="e35e9-186">Microsoft cannot provide advice or recommendations on whether or not your Edge network (or any network) falls under PCI standard; that must be determined by the individual company.</span></span>

<span data-ttu-id="e35e9-187">Skype for Business Online は現在 TLS 1.2 に対応しています。そのため、ハイブリッド/オンラインとのフェデレーションへの影響は期待されません。</span><span class="sxs-lookup"><span data-stu-id="e35e9-187">Skype for Business Online is capable of TLS 1.2 today, so no impact to Hybrid/Federation with Online is expected.</span></span>

<span data-ttu-id="e35e9-188">PIC (Public IM Connectivity) to Skype Consumer service: We do not expecting TLS 1.0/1.1 to impact [Skype Connectivity](../../deploy/deploy-skype-connectivity.md);Microsoft PIC ゲートウェイは既に TLS 1.2 に対応しています。</span><span class="sxs-lookup"><span data-stu-id="e35e9-188">PIC (Public IM Connectivity) to Skype Consumer service: We do not expect disabling TLS 1.0/1.1 to impact [Skype Connectivity](../../deploy/deploy-skype-connectivity.md); Microsoft PIC Gateways are already TLS 1.2 capable.</span></span>

## <a name="prerequisites-and-process"></a><span data-ttu-id="e35e9-189">前提条件とプロセス</span><span class="sxs-lookup"><span data-stu-id="e35e9-189">Prerequisites and process</span></span>

<span data-ttu-id="e35e9-190">上記で説明した場合を除き、TLS 1.0 および 1.1 がスコープ外のサーバーで無効にされた場合、クライアントとデバイスは正常に機能するか、またはすべて機能します。</span><span class="sxs-lookup"><span data-stu-id="e35e9-190">Except where noted above, once TLS 1.0 and 1.1 are disabled out-of-scope servers, clients and devices will longer function properly, or at all.</span></span> <span data-ttu-id="e35e9-191">これは、Microsoft からの更新されたガイダンスを一時停止して待つ必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="e35e9-191">This may mean you need to pause and wait for updated guidance from Microsoft.</span></span> <span data-ttu-id="e35e9-192">すべての要件を満たしていることを確認し、ギャップに対処する計画を立てしたら、次に進みます。</span><span class="sxs-lookup"><span data-stu-id="e35e9-192">Once you are satisfied that you meet all requirements and have a plan to address gaps, proceed.</span></span>

<span data-ttu-id="e35e9-193">大きなレベルでは、Skype for Business Server 2019 をインストールする準備が整っている間、Skype for Business Server 2015 では CU9 のインストール、.NET と SQL への前提条件の更新プログラムの適用、前提条件となるレジストリ キーの展開、最後に別の OS 構成更新のラウンド (つまり、レジストリ ファイルのインポートによる TLS 1.0 と 1.1 の無効化) が必要です。</span><span class="sxs-lookup"><span data-stu-id="e35e9-193">At a high level, while Skype for Business Server 2019 is ready for procedure at install, Skype for Business Server 2015 will require that you install CU9, applying pre-requisite updates to .NET and SQL, deploying prerequisite registry keys, and finally a separate round of OS configuration updates (i.e. disabling TLS 1.0 and 1.1 via registry file import).</span></span> <span data-ttu-id="e35e9-194">環境内の任意のサーバーで TLS 1.0 と 1.1 を無効にする前に、Skype for Business Server 2015 CU6 HF2 を含むすべての前提条件のインストールを完了することが非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="e35e9-194">It is critically important that you complete installation of all prerequisites, including Skype for Business Server 2015 CU6 HF2, prior to disabling TLS 1.0 and 1.1 on any server in your environment.</span></span> <span data-ttu-id="e35e9-195">エッジの役割やバックエンドの管理を含むすべての Skype for Business サーバー SQL更新プログラムが必要です。</span><span class="sxs-lookup"><span data-stu-id="e35e9-195">Every Skype for Business server, including Edge role and SQL Backends, requires the updates.</span></span> <span data-ttu-id="e35e9-196">また、サポート対象 (範囲内) のすべてのクライアントが必要な最小バージョンに更新されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e35e9-196">Also ensure that all supported (in-scope) clients have been updated to the required minimum versions.</span></span> <span data-ttu-id="e35e9-197">管理ワークステーションも忘れずに更新してください。</span><span class="sxs-lookup"><span data-stu-id="e35e9-197">Don’t forget to update management workstations as well.</span></span>

<span data-ttu-id="e35e9-198">Skype for Business サーバーをアップグレードする場合は、"インサイド アウト" の通常の運用順序に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="e35e9-198">We want to follow the usual order of operations of "inside out" for upgrading Skype for Business servers.</span></span> <span data-ttu-id="e35e9-199">ディレクター プール、常設チャット、ペアリングされたプールは、通常と同じ方法で扱います。</span><span class="sxs-lookup"><span data-stu-id="e35e9-199">Treat Director pools, Persistent chat, and Paired Pools in the same manner you normally would.</span></span> <span data-ttu-id="e35e9-200">アップグレードの順序と方法については、ここ [とここを](topology.md) 参照 [してください](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)。</span><span class="sxs-lookup"><span data-stu-id="e35e9-200">Order and methods for upgrade are covered [here](topology.md) and [here](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>

### <a name="high-level-process"></a><span data-ttu-id="e35e9-201">プロセスのレベルが高い</span><span class="sxs-lookup"><span data-stu-id="e35e9-201">High-level process</span></span>

1. <span data-ttu-id="e35e9-202">実稼働サーバーを構成する前に、ラボのすべての手順をテストします。</span><span class="sxs-lookup"><span data-stu-id="e35e9-202">Test all steps in your lab prior to configuring production servers.</span></span>
2. <span data-ttu-id="e35e9-203">更新する個々のサーバーごとに、エクスポートされたレジストリのコピーをバックアップして保持します。</span><span class="sxs-lookup"><span data-stu-id="e35e9-203">Back up and preserve a copy of exported registry on each and every individual server to be updated.</span></span> <span data-ttu-id="e35e9-204">サーバー間でレジストリを共有することはできません。コンピューターベースの一意のキーが含まれている。</span><span class="sxs-lookup"><span data-stu-id="e35e9-204">You cannot share registries between servers; they contain unique machine-based keys.</span></span>
3. <span data-ttu-id="e35e9-205">すべての Skype for Business 2015 サーバーを CU9 以上にアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="e35e9-205">Upgrade all Skype for Business 2015 servers to CU9 or higher.</span></span> <span data-ttu-id="e35e9-206">Skype for Business Server 2019 の場合は、CU1 以上にアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="e35e9-206">For Skype for Business Server 2019, upgrade to CU1 or higher.</span></span>
4. <span data-ttu-id="e35e9-207">すべての必須コンポーネントをすべてのサーバーにインストールします。</span><span class="sxs-lookup"><span data-stu-id="e35e9-207">Install all prerequisites to all servers.</span></span>
5. <span data-ttu-id="e35e9-208">前提条件となるレジストリ キーを展開します。</span><span class="sxs-lookup"><span data-stu-id="e35e9-208">Deploy prerequisite registry keys.</span></span>
6. <span data-ttu-id="e35e9-209">スコープ内のすべてのクライアントが更新されます。</span><span class="sxs-lookup"><span data-stu-id="e35e9-209">Ensure that all in-scope clients are updated.</span></span>
7. <span data-ttu-id="e35e9-210">レジストリ のインポートを使用して TLS 1.0 および 1.1 を無効にします。</span><span class="sxs-lookup"><span data-stu-id="e35e9-210">Disable TLS 1.0 and 1.1 via registry import.</span></span>
8. <span data-ttu-id="e35e9-211">ワークロードが期待通り機能しているのを検証します。</span><span class="sxs-lookup"><span data-stu-id="e35e9-211">Validate that workloads are functioning as expected.</span></span>
    - <span data-ttu-id="e35e9-212">問題が発生した場合は、トラブルシューティングと解決、または</span><span class="sxs-lookup"><span data-stu-id="e35e9-212">If problems are encountered, troubleshoot and resolve, or</span></span>
    - <span data-ttu-id="e35e9-213">手順 2 からレジストリを復元して TLS 1.0 と 1.1 を再び有効にする</span><span class="sxs-lookup"><span data-stu-id="e35e9-213">Restore registry from step 2 to re-enable TLS 1.0 and 1.1</span></span>
9. <span data-ttu-id="e35e9-214">TLS 1.2 だけが使用されているのを検証します。</span><span class="sxs-lookup"><span data-stu-id="e35e9-214">Validate that only TLS 1.2 is being used.</span></span>

### <a name="install-prerequisites-to-all-servers"></a><span data-ttu-id="e35e9-215">すべてのサーバーに必須コンポーネントをインストールする</span><span class="sxs-lookup"><span data-stu-id="e35e9-215">Install prerequisites to all servers</span></span>

<span data-ttu-id="e35e9-216">Skype for Business Server 2015 展開のオペレーティング システム レベルで TLS 1.0 および 1.1 の無効化を開始する前に、広範な依存関係の更新が必要です。</span><span class="sxs-lookup"><span data-stu-id="e35e9-216">Extensive dependency updating is required before you begin to disable TLS 1.0 and 1.1 at the operating system level in your Skype for Business Server 2015 deployments.</span></span> <span data-ttu-id="e35e9-217">TLS 1.2 をサポートできる最小バージョンを次に示します。</span><span class="sxs-lookup"><span data-stu-id="e35e9-217">The following are the minimum versions that can support TLS 1.2.</span></span> <span data-ttu-id="e35e9-218">TLS 1.0 と 1.1 の無効化を開始する前に、環境内のすべての Skype for Business サーバーに前提条件の更新プログラムを展開します。</span><span class="sxs-lookup"><span data-stu-id="e35e9-218">Deploy all prerequisite updates across every Skype for Business server in your environment before you begin disabling TLS 1.0 and 1.1.</span></span>

- <span data-ttu-id="e35e9-219">Skype for Business Server 2015 CU9 6.0.9319.548 (2019 年 5 月) 以上</span><span class="sxs-lookup"><span data-stu-id="e35e9-219">Skype for Business Server 2015 CU9 6.0.9319.548 (May 2019) or higher</span></span>
- <span data-ttu-id="e35e9-220">レジストリで SchUseStrongCrypto を有効にした[.NET Framework 4.7](https://www.microsoft.com/download/details.aspx?id=55167)以上 (下記参照)</span><span class="sxs-lookup"><span data-stu-id="e35e9-220">[.NET Framework 4.7](https://www.microsoft.com/download/details.aspx?id=55167) or higher with SchUseStrongCrypto enabled in the registry (provided below)</span></span>
- <span data-ttu-id="e35e9-221">SQL Skype for Business 2015 サーバーとバックエンドで更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e35e9-221">SQL must be updated on all Skype for Business 2015 servers and backends.</span></span> <span data-ttu-id="e35e9-222">最初に Enterprise Edition プールSQLバックエンドを更新し、次にそれぞれの FEs を更新します。</span><span class="sxs-lookup"><span data-stu-id="e35e9-222">Update Enterprise Edition Pool SQL Backends first, then their respective FEs.</span></span> 
    - <span data-ttu-id="e35e9-223">[SQL Server 2014 SP1 + CU5](https://support.microsoft.com/help/3130926)以上 / SQL Server 2012 SP2 + CU16 以上 / [SQL Server 2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014)以上 / SQL Server 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="e35e9-223">[SQL Server 2014 SP1 + CU5](https://support.microsoft.com/help/3130926), or higher / SQL Server 2012 SP2 + CU16 or higher / [SQL Server 2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014), or higher / SQL Server 2014 SP2</span></span>
     - [<span data-ttu-id="e35e9-224">SQL Server 2012 SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="e35e9-224">SQL Server Native Client for SQL Server 2012</span></span>](https://www.microsoft.com/download/details.aspx?id=50402)
     - <span data-ttu-id="e35e9-225">[Microsoft ODBC Driver 11 for SQL Server](https://www.microsoft.com/download/details.aspx?id=36434)or higher</span><span class="sxs-lookup"><span data-stu-id="e35e9-225">[Microsoft ODBC Driver 11 for SQL Server](https://www.microsoft.com/download/details.aspx?id=36434), or higher</span></span>
     - [<span data-ttu-id="e35e9-226">SQL Server 2014 SP2 の共有管理オブジェクト</span><span class="sxs-lookup"><span data-stu-id="e35e9-226">Shared Management Objects for SQL Server 2014 SP2</span></span>](https://www.microsoft.com/download/details.aspx?id=53164)
     - [<span data-ttu-id="e35e9-227">SQLSysClrTypes for SQL server 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="e35e9-227">SQLSysClrTypes for SQL server 2014 SP2</span></span>](https://www.microsoft.com/download/details.aspx?id=42295)

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a><span data-ttu-id="e35e9-228">前提条件をインストールするための基本的な手順 (推奨される操作順)</span><span class="sxs-lookup"><span data-stu-id="e35e9-228">Basic steps to install pre-requisites, in recommended order of operations</span></span>

1. <span data-ttu-id="e35e9-229">Skype for Business Server CU9 更新プログラムをすべてのサーバーにインストールします。</span><span class="sxs-lookup"><span data-stu-id="e35e9-229">Install the Skype for Business Server CU9 update to all servers.</span></span> 
    1. <span data-ttu-id="e35e9-230">アップデータツールを使用してコンポーネントに更新プログラムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="e35e9-230">Install the update to components using the updater.</span></span>
    2. <span data-ttu-id="e35e9-231">文書化されている手順に従ってデータベースを更新します。</span><span class="sxs-lookup"><span data-stu-id="e35e9-231">Update databases according to documented procedures.</span></span> <span data-ttu-id="e35e9-232">Skype for Business Server 2015 の場合は、KB [3061064 を参照してください](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)。</span><span class="sxs-lookup"><span data-stu-id="e35e9-232">For Skype for Business Server 2015, see KB [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>
    3. <span data-ttu-id="e35e9-233">他の変更を進む前に、展開の製品機能を検証します。</span><span class="sxs-lookup"><span data-stu-id="e35e9-233">Validate product functionality in the deployment prior to moving forward with any other changes.</span></span>
2. <span data-ttu-id="e35e9-234">.NET 4.7 オフライン インストーラーをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="e35e9-234">Download .NET 4.7 Offline Installer.</span></span> 
    1. <span data-ttu-id="e35e9-235">リファレンス: [https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)</span><span class="sxs-lookup"><span data-stu-id="e35e9-235">Reference: [https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)</span></span>
    2. <span data-ttu-id="e35e9-236">フロント エンド サーバーで Skype for Business Server 2015 サービスが停止している必要があります。</span><span class="sxs-lookup"><span data-stu-id="e35e9-236">Ensure that Skype for Business Server 2015 services are stopped on the Front End server.</span></span>
    3. <span data-ttu-id="e35e9-237">リファレンス: [https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="e35e9-237">Reference: [https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span></span>
    4. <span data-ttu-id="e35e9-238">Ex (Standard Edition): ```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="e35e9-238">Ex (Standard Edition): ```Stop-CsWindowsService```</span></span>
    5. <span data-ttu-id="e35e9-239">例 (Enterprise Edition): ```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="e35e9-239">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    6. <span data-ttu-id="e35e9-240">インストーラー パッケージを実行します。</span><span class="sxs-lookup"><span data-stu-id="e35e9-240">Run the installer package.</span></span>
    7. <span data-ttu-id="e35e9-241">サーバーを再起動します。</span><span class="sxs-lookup"><span data-stu-id="e35e9-241">Reboot the server.</span></span>
3. <span data-ttu-id="e35e9-242">すべてのSQL Express 2014 を更新します。</span><span class="sxs-lookup"><span data-stu-id="e35e9-242">Update SQL Express 2014 on all servers.</span></span> 
    1. <span data-ttu-id="e35e9-243">リファレンス: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span><span class="sxs-lookup"><span data-stu-id="e35e9-243">Reference: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span></span>
    2. <span data-ttu-id="e35e9-244">2014 SP2 SQLダウンロード</span><span class="sxs-lookup"><span data-stu-id="e35e9-244">Download SQL 2014 SP2</span></span> 
        - <span data-ttu-id="e35e9-245">リファレンス: [https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)</span><span class="sxs-lookup"><span data-stu-id="e35e9-245">Reference: [https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)</span></span>
    3. <span data-ttu-id="e35e9-246">インストール メディアをサーバー上のフォルダーにコピーします (例: C:\01_2014SqlSp2)</span><span class="sxs-lookup"><span data-stu-id="e35e9-246">Copy the installation media to a folder on the server (Ex: C:\01_2014SqlSp2)</span></span>
    4. <span data-ttu-id="e35e9-247">フロント エンド サーバーで Skype for Business Server 2015 サービスが停止している</span><span class="sxs-lookup"><span data-stu-id="e35e9-247">Ensure Skype for Business Server 2015 services are stopped on the Front End server</span></span> 
        - <span data-ttu-id="e35e9-248">Ex (Standard Edition): ```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="e35e9-248">Ex (Standard Edition): ```Stop-CsWindowsService```</span></span>
        - <span data-ttu-id="e35e9-249">例 (Enterprise Edition): ```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="e35e9-249">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    5. <span data-ttu-id="e35e9-250">管理者コマンド プロンプトを開き、インストール済みのすべてのコンポーネントとインスタンスをアップグレードする</span><span class="sxs-lookup"><span data-stu-id="e35e9-250">Open an Admin Command Prompt, and upgrade all installed components and instances</span></span> 
        - <span data-ttu-id="e35e9-251">例: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action=Patch /AllInstances</span><span class="sxs-lookup"><span data-stu-id="e35e9-251">Example: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action=Patch /AllInstances</span></span>
4. <span data-ttu-id="e35e9-252">ネイティブ SQL更新します。</span><span class="sxs-lookup"><span data-stu-id="e35e9-252">Update SQL Native Client.</span></span> 
    1. <span data-ttu-id="e35e9-253">リファレンス: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server) .</span><span class="sxs-lookup"><span data-stu-id="e35e9-253">Reference: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span></span>
    2. <span data-ttu-id="e35e9-254">ダウンロード [https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)</span><span class="sxs-lookup"><span data-stu-id="e35e9-254">Download from [https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)</span></span>
    3. <span data-ttu-id="e35e9-255">フロント エンド サーバーで Skype for Business Server 2015 サービスが停止します。</span><span class="sxs-lookup"><span data-stu-id="e35e9-255">Ensure Skype for Business Server 2015 services are stopped on the Front End server.</span></span> 
        - <span data-ttu-id="e35e9-256">Ex (Standard Edition): ```Stop-CsWindowsServices```</span><span class="sxs-lookup"><span data-stu-id="e35e9-256">Ex (Standard Edition): ```Stop-CsWindowsServices```</span></span>
        - <span data-ttu-id="e35e9-257">例 (Enterprise Edition): ```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="e35e9-257">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    4. <span data-ttu-id="e35e9-258">インストールされたSQLインスタンスの実行を停止する</span><span class="sxs-lookup"><span data-stu-id="e35e9-258">Stop the SQL instances installed from running</span></span> 
        - <span data-ttu-id="e35e9-259">例: ```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="e35e9-259">Ex: ```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```</span></span>
        - <span data-ttu-id="e35e9-260">例: ```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="e35e9-260">Ex: ```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```</span></span>
        - <span data-ttu-id="e35e9-261">Ex (Standard Edition のみ): ```Get-Service 'MSSQL$RTC' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="e35e9-261">Ex (Standard Edition Only): ```Get-Service 'MSSQL$RTC' | Stop-Service```</span></span>
    5. <span data-ttu-id="e35e9-262">更新プログラムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="e35e9-262">Install the update.</span></span>
5. <span data-ttu-id="e35e9-263">ODBC Driver 11 for SQL Server TLS 1.2 (KB [3135244)](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)のサポートを含める。</span><span class="sxs-lookup"><span data-stu-id="e35e9-263">Update ODBC Driver 11 for SQL Server to include support for TLS 1.2 (KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)).</span></span>
    1. <span data-ttu-id="e35e9-264">ODBC [Driver 11 for SQL Server - Windows をダウンロードします](https://www.microsoft.com/download/confirmation.aspx?id=36434)。</span><span class="sxs-lookup"><span data-stu-id="e35e9-264">Download [ODBC Driver 11 for SQL Server - Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434).</span></span>
    2. <span data-ttu-id="e35e9-265">フロント エンド サーバーで Skype for Business Server 2015 サービスが停止している必要があります。</span><span class="sxs-lookup"><span data-stu-id="e35e9-265">Ensure that Skype for Business Server 2015 services are stopped on the Front End server.</span></span>
        - <span data-ttu-id="e35e9-266">例 (Standard Edition): ```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="e35e9-266">Example (Standard Edition): ```Stop-CsWindowsService```</span></span>
        - <span data-ttu-id="e35e9-267">例 (Enterprise Edition): ```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="e35e9-267">Example (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    3. <span data-ttu-id="e35e9-268">更新プログラムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="e35e9-268">Install the update.</span></span>
6. <span data-ttu-id="e35e9-269">前提条件となるレジストリ キーを展開します。</span><span class="sxs-lookup"><span data-stu-id="e35e9-269">Deploy prerequisite registry keys.</span></span>

### <a name="pre-requisite-registry-keys"></a><span data-ttu-id="e35e9-270">前提条件のレジストリ キー</span><span class="sxs-lookup"><span data-stu-id="e35e9-270">Pre-requisite registry keys</span></span>

<span data-ttu-id="e35e9-271">次のテストをコピー/貼り付けしてメモ帳に貼り付け、TLSPreReq.reg または選択した名前の名前を変更してから、インポートします。</span><span class="sxs-lookup"><span data-stu-id="e35e9-271">Copy/paste the following test into Notepad and rename TLSPreReq.reg or a name of your choice, then import:</span></span>

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

<span data-ttu-id="e35e9-272">Enterprise Edition SQLのバック エンドの場合、前提条件と TLS の無効化は、次に示す任意SQLまたは OS の更新プログラムとして扱う必要があります。参照: [https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span><span class="sxs-lookup"><span data-stu-id="e35e9-272">For SQL back ends for Enterprise Edition Pools, prerequisites and TLS disable should be treated as any SQL or OS updates would; refer to: [https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span></span>

<span data-ttu-id="e35e9-273">前提条件となるアプリケーションと TLS の両方の無効化手順を組み合わせることができますが、オペレーティング システム レベルでの TLS 1.0 と 1.1 の無効化に進む前に、すべての前提条件を適用することを強く推奨します。</span><span class="sxs-lookup"><span data-stu-id="e35e9-273">While both the prerequisite application and TLS disabling steps can be combined, we strongly recommend all prerequisites be applied before proceeding with disabling of TLS 1.0 and 1.1 at the operating system level.</span></span> <span data-ttu-id="e35e9-274">ベスト プラクティスのアプローチは、すべての前提条件を展開し、すべてのワークロードが正常に正常に機能していることを検証し、後で TLS 1.0/1.1 を無効にすることで環境を準備する方法です。</span><span class="sxs-lookup"><span data-stu-id="e35e9-274">The best practice approach would be to prepare the environment by deploying all prerequisites, validating that workloads all function correctly and as expected, and then proceeding with TLS 1.0/1.1 disable at a later time.</span></span>

### <a name="disable-tls-10-and-11-via-registry-import"></a><span data-ttu-id="e35e9-275">レジストリ インポートによる TLS 1.0 および 1.1 の無効化</span><span class="sxs-lookup"><span data-stu-id="e35e9-275">Disable TLS 1.0 and 1.1 via registry import</span></span>

<span data-ttu-id="e35e9-276">次の手順に進む前に、すべての前提条件と更新された Skype for Business Servers が完了 *していることを確認してください*。</span><span class="sxs-lookup"><span data-stu-id="e35e9-276">Before you proceed with the next steps, *make sure you have completed all prerequisites and updated Skype for Business Servers*.</span></span>

<span data-ttu-id="e35e9-277">次のテキストをメモ帳ファイルにコピーし **、TLSDisable.reg という名前に変更します**。</span><span class="sxs-lookup"><span data-stu-id="e35e9-277">Copy the following text into a Notepad file and rename it **TLSDisable.reg**:</span></span>

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

<span data-ttu-id="e35e9-278">TLS 1.0 と 1.1 を無効にする各サーバーに .reg ファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="e35e9-278">Import the .reg file on each server you wish to disable TLS 1.0 and 1.1.</span></span> <span data-ttu-id="e35e9-279">サーバーを再起動します。</span><span class="sxs-lookup"><span data-stu-id="e35e9-279">Reboot the server.</span></span> <span data-ttu-id="e35e9-280">サービスがオンラインに戻った後、次のサーバーに移動します。</span><span class="sxs-lookup"><span data-stu-id="e35e9-280">Once the services have come back online, move to the next server.</span></span> <span data-ttu-id="e35e9-281">Enterprise Edition プールのアプローチは、すべての OS 更新プログラムで使用する方法と同じです。</span><span class="sxs-lookup"><span data-stu-id="e35e9-281">The approach for Enterprise Edition Pools is the same you would take for any OS update.</span></span>

<span data-ttu-id="e35e9-282">ここで TLS 1.0 と 1.1 を無効にしている以上のことを行っていることに気付いた可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e35e9-282">You may have noticed we are doing more than just disabling TLS 1.0 and 1.1 here.</span></span> <span data-ttu-id="e35e9-283">暗号スイートの再順序付け (上記のように) と、いくつかの古い弱暗号の無効化をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="e35e9-283">We are supporting Cipher Suite re-order (as shown above) and the disabling of some older weak ciphers.</span></span> <span data-ttu-id="e35e9-284">Skype for Business Server で SCHANNEL と Crypto API に対するこれらの変更を正式にサポートするのは今回が初めてであり、現時点でサポートおよびテストした変更は、これらの変更のみである点に注意することが重要です。</span><span class="sxs-lookup"><span data-stu-id="e35e9-284">This is the first time we have officially supported these changes to SCHANNEL and Crypto API on Skype for Business Server, and it is important to note that these changes are the only ones we support and have tested at this time.</span></span> <span data-ttu-id="e35e9-285">今後、追加の構成を検討する場合がありますが、現在のところ、実装内のレジストリ インポート ファイルは変更してください。</span><span class="sxs-lookup"><span data-stu-id="e35e9-285">We may consider additional configurations in the future, but for now, please do not modify the registry import file in your implementation.</span></span>

### <a name="validate-that-workloads-are-functioning-as-expected"></a><span data-ttu-id="e35e9-286">ワークロードが期待通り機能しているのを検証する</span><span class="sxs-lookup"><span data-stu-id="e35e9-286">Validate that workloads are functioning as expected</span></span>

<span data-ttu-id="e35e9-287">環境で TLS 1.0 と 1.1 が無効にされた後は、IM & プレゼンス、P2P 通話、エンタープライズ VoIP など、すべての主要なワークロードが期待通り機能している必要があります。</span><span class="sxs-lookup"><span data-stu-id="e35e9-287">Once TLS 1.0 and 1.1 have been disabled in your environment, ensure that all your main workloads are functioning as expected, such as IM & Presence, P2P calls, Enterprise Voice, etc.</span></span>

<span data-ttu-id="e35e9-288">**TLS 1.2 のみを使用している検証**</span><span class="sxs-lookup"><span data-stu-id="e35e9-288">**Validate only TLS 1.2 is being used**</span></span>

<span data-ttu-id="e35e9-289">セキュリティ チームに Skype for Business トラフィックの新しい監査を実行して、古いプロトコル TLS 1.0 と 1.1 が使用されなくなったか確認します。</span><span class="sxs-lookup"><span data-stu-id="e35e9-289">Have your Security Team perform a new audit of Skype for Business traffic to ensure that the older protocols TLS 1.0 and 1.1 are no longer in use.</span></span>

<span data-ttu-id="e35e9-290">または、Internet Explorer を使用して、TLS 1.0 と TLS 1.1 が無効にされた後に、Skype for Business Server 2015 から Web サービスへの TLS 接続をテストできます。</span><span class="sxs-lookup"><span data-stu-id="e35e9-290">Alternatively, you can use Internet Explorer to test TLS connections to web services from Skype for Business Server 2015 after TLS 1.0 and TLS 1.1 have been disabled.</span></span>

1. <span data-ttu-id="e35e9-291">起動Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="e35e9-291">Launch Internet Explorer.</span></span>
2. <span data-ttu-id="e35e9-292">[**ツールインターネット オプション**  >  **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e35e9-292">Select **Tools** > **Internet Options**.</span></span>
3. <span data-ttu-id="e35e9-293">[詳細設定] **タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="e35e9-293">Select the **Advanced** tab.</span></span>
4. <span data-ttu-id="e35e9-294">[ **設定] で**、一番下までスクロールします。</span><span class="sxs-lookup"><span data-stu-id="e35e9-294">Under **Settings**, scroll to the bottom.</span></span>
5. <span data-ttu-id="e35e9-295">TLS 1.0、TLS 1.1、および TLS 1.2 が有効になっているか確認します。</span><span class="sxs-lookup"><span data-stu-id="e35e9-295">Verify that TLS 1.0, TLS 1.1, and TLS 1.2 are enabled.</span></span>
6. <span data-ttu-id="e35e9-296">SfB 2015 プールの内部 Web サービス URL を参照します (正常に接続する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="e35e9-296">Browse the Internal Web Service URL of your SfB 2015 pool (should connect successfully).</span></span>
7. <span data-ttu-id="e35e9-297">サーバーに戻りInternet Explorer **TLS 1.2** のみを使用するオプションを無効にします。</span><span class="sxs-lookup"><span data-stu-id="e35e9-297">Go back into Internet Explorer and disable the option to **Use TLS 1.2** only.</span></span>
8. <span data-ttu-id="e35e9-298">SfB 2015 プールの内部 Web サービス URL を再び参照します (接続に失敗する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="e35e9-298">Browse the Internal Web Service URL of your SfB 2015 pool again (should fail to connect).</span></span>

![インターネット オプション](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a><span data-ttu-id="e35e9-300">高度な展開シナリオ</span><span class="sxs-lookup"><span data-stu-id="e35e9-300">Advanced deployment scenarios</span></span>

<span data-ttu-id="e35e9-301">Skype for Business Server 2015 で TLS 1.2 をサポートするには依存関係の前提条件がいくつか必要なので、TLS 1.0 と 1.1 が無効になっているシステムでは RTM メディアからのインストールが失敗します。</span><span class="sxs-lookup"><span data-stu-id="e35e9-301">Because some dependency prerequisites are required to support TLS 1.2 in Skype for Business Server 2015, installing from RTM media will fail on any system where TLS 1.0 and 1.1 have been disabled.</span></span>

<span data-ttu-id="e35e9-302">**環境内で TLS 1.0 および 1.1 を使用した場合の新しい Standard Edition サーバーまたは Enterprise Edition プールの展開は無効になっています。**</span><span class="sxs-lookup"><span data-stu-id="e35e9-302">**Deploying New Standard Edition Servers or Enterprise Edition Pools once TLS 1.0 and 1.1 have been disabled in your environment.**</span></span>

<span data-ttu-id="e35e9-303">**オプション 1:**[SmartSetup を使用します](../../deploy/install/install-skype-for-business-server.md)。</span><span class="sxs-lookup"><span data-stu-id="e35e9-303">**Option 1:** Use [SmartSetup](../../deploy/install/install-skype-for-business-server.md).</span></span> <span data-ttu-id="e35e9-304">SmartSetup は今後の CU で更新された SQL バイナリに対応するように更新中であり、この記事は今後更新される予定です。</span><span class="sxs-lookup"><span data-stu-id="e35e9-304">Note that we are updating SmartSetup to accommodate the updated SQL binaries in a future CU, and will update this article in the future.</span></span>

<span data-ttu-id="e35e9-305">**オプション 2:** ローカル サーバー インスタンスのSQL (RTCLOCAL および LYNCLOCAL)</span><span class="sxs-lookup"><span data-stu-id="e35e9-305">**Option 2:** Pre-install local SQL instances (RTCLOCAL and LYNCLOCAL)</span></span>

1. <span data-ttu-id="e35e9-306">Express 2014 SP2 (SQL) をダウンロードし、FE SQLEXPR_x64.exeフォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="e35e9-306">Download and copy SQL Express 2014 SP2 (SQLEXPR_x64.exe) to local folder on FE.</span></span> <span data-ttu-id="e35e9-307">たとえば、フォルダー パス <SQL_FOLDER_PATH>。</span><span class="sxs-lookup"><span data-stu-id="e35e9-307">Let’s say folder path <SQL_FOLDER_PATH>.</span></span>
2. <span data-ttu-id="e35e9-308">PowerShell またはコマンド プロンプトを起動し、<SQL_FOLDER_PATH ファイルに>。</span><span class="sxs-lookup"><span data-stu-id="e35e9-308">Launch PowerShell or Command Prompt and navigate to <SQL_FOLDER_PATH>.</span></span>
3. <span data-ttu-id="e35e9-309">次のコマンドを実行して、SQL RTCLOCAL インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="e35e9-309">Create the RTCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="e35e9-310">処理が完了SQLEXPR_x64.exe、次の処理に進みます。</span><span class="sxs-lookup"><span data-stu-id="e35e9-310">Wait until SQLEXPR_x64.exe finishes before proceeding:</span></span>

    <span data-ttu-id="e35e9-311">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=RTCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automati</span><span class="sxs-lookup"><span data-stu-id="e35e9-311">SQLEXPR_x64.exe  /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=RTCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automati</span></span>
1. <span data-ttu-id="e35e9-312">以下のコマンドを実行SQL LYNCLOCAL サービス インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="e35e9-312">Create the LYNCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="e35e9-313">次の手順SQLEXPR_x64.exeに進む前に、次の手順が完了するまで待ちます。</span><span class="sxs-lookup"><span data-stu-id="e35e9-313">Wait until SQLEXPR_x64.exe finishes before proceeding to the next step:</span></span>

    <span data-ttu-id="e35e9-314">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=LYNCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automatic</span><span class="sxs-lookup"><span data-stu-id="e35e9-314">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=LYNCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automatic</span></span>
1. <span data-ttu-id="e35e9-315">Skype for Business Server 2015 RTM セットアッププログラムを実行します。</span><span class="sxs-lookup"><span data-stu-id="e35e9-315">Run Skype for Business Server 2015 RTM setup.</span></span>
2. <span data-ttu-id="e35e9-316">上記の前提条件セクションの残りの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="e35e9-316">Follow the remaining steps from the prerequisites section above.</span></span>

<span data-ttu-id="e35e9-317">**オプション 3:** 次のように、ローカル インストール メディア ディレクトリ内のバイナリを手動で置き換える場合があります。</span><span class="sxs-lookup"><span data-stu-id="e35e9-317">**Option 3:** You may also manually replace binaries in a local installation media directory as follows:</span></span>

1. [<span data-ttu-id="e35e9-318">Skype for Business Server の前提条件のインストール</span><span class="sxs-lookup"><span data-stu-id="e35e9-318">Install prerequisites for Skype for Business Server</span></span>](../../deploy/install/install-prerequisites.md)  
2. <span data-ttu-id="e35e9-319">.NET 4.7 をインストールします。</span><span class="sxs-lookup"><span data-stu-id="e35e9-319">Install .NET 4.7:</span></span> 
      - <span data-ttu-id="e35e9-320">**注:** Skype for Business Server 2015 CU5 (6.0.9319.281) で .NET 4.7 のサポートを初めて導入しました。</span><span class="sxs-lookup"><span data-stu-id="e35e9-320">**Note:** We first introduced support for .NET 4.7 in Skype for Business Server 2015 CU5 (6.0.9319.281).</span></span> <span data-ttu-id="e35e9-321">したがって、次の手順では、メイン インストールの前にコア コンポーネントを更新します。</span><span class="sxs-lookup"><span data-stu-id="e35e9-321">Therefore, in later steps below we will be updating Core Components prior to the main install.</span></span>
      - <span data-ttu-id="e35e9-322">ダウンロード: https://www.microsoft.com/download/details.aspx?id=55167 .</span><span class="sxs-lookup"><span data-stu-id="e35e9-322">Download: https://www.microsoft.com/download/details.aspx?id=55167.</span></span> 
      - <span data-ttu-id="e35e9-323">リファレンス: [Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)の展開前にインストールする必要があるソフトウェア</span><span class="sxs-lookup"><span data-stu-id="e35e9-323">Reference: [Software that should be installed before a Skype for Business Server 2015 deployment](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span></span>
3. <span data-ttu-id="e35e9-324">ISO ファイル/フォルダーをコピーする:</span><span class="sxs-lookup"><span data-stu-id="e35e9-324">Copy ISO Files/Folders:</span></span> 
    - <span data-ttu-id="e35e9-325">Skype for Business Server 2015 ISO が接続されている場合は、添付されているドライブのルート ディレクトリを開きます (例: D: \) エクスプローラーで)。</span><span class="sxs-lookup"><span data-stu-id="e35e9-325">With the Skype for Business Server 2015 ISO attached, open the root directory of the drive it is attached as (Ex: D:\) in File Explorer.</span></span>
    - <span data-ttu-id="e35e9-326">すべてのフォルダーとファイルをローカル ディスク上のフォルダー (例: C:\SkypeForBusiness2015ISO) にコピーします。</span><span class="sxs-lookup"><span data-stu-id="e35e9-326">Copy all folders and files to a folder on a local disk (Ex: C:\SkypeForBusiness2015ISO).</span></span>
    - <span data-ttu-id="e35e9-327">**注:** コンポーネントをインストールする前に、TLS 1.2 のサポートのために一部のファイルを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e35e9-327">**Note:** Prior to installing components, some files will need to be updated for support of TLS 1.2.</span></span>
4. <span data-ttu-id="e35e9-328">MSI/EXE パッケージを置き換える:</span><span class="sxs-lookup"><span data-stu-id="e35e9-328">Replace MSI/EXE Packages:</span></span> 
    - <span data-ttu-id="e35e9-329">ローカル コンピューター上のインストール メディアの /Setup/amd64/ フォルダーにある既存の MSI パッケージと EXE パッケージを置き換える。</span><span class="sxs-lookup"><span data-stu-id="e35e9-329">Replace the existing MSI and EXE packages in the /Setup/amd64/ folder of the installation media on the local machine.</span></span>
    - <span data-ttu-id="e35e9-330">SQL 2014 SP2 Express: https://www.microsoft.com/download/details.aspx?id=53167</span><span class="sxs-lookup"><span data-stu-id="e35e9-330">SQL 2014 SP2 Express: https://www.microsoft.com/download/details.aspx?id=53167</span></span> 
        - <span data-ttu-id="e35e9-331">ローカル コンピューター SQLEXPR_x64名前を変更し、インストール メディアの Setup/amd64/ フォルダーにある既存のファイルを置き換える。</span><span class="sxs-lookup"><span data-stu-id="e35e9-331">Rename to SQLEXPR_x64 on the local machine, and replace the existing file in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="e35e9-332">SQL クライアント: https://www.microsoft.com/download/details.aspx?id=50402</span><span class="sxs-lookup"><span data-stu-id="e35e9-332">SQL Native Client: https://www.microsoft.com/download/details.aspx?id=50402</span></span> 
        - <span data-ttu-id="e35e9-333">**注:** 必要に応じて名前を変更してsqlncli.msiし、インストール メディアの Setup/amd64/ フォルダーに存在する既存のファイルを置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="e35e9-333">**Note:** Rename this if necessary to sqlncli.msi, and then replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="e35e9-334">SQL管理オブジェクト: https://www.microsoft.com/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="e35e9-334">SQL Management Objects: https://www.microsoft.com/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="e35e9-335">**注:** フィーチャー パックには、ダウンロードできるアイテムが多く含まれています。</span><span class="sxs-lookup"><span data-stu-id="e35e9-335">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="e35e9-336">ダウンロードのみを選択SharedManagementObjects.msiします。</span><span class="sxs-lookup"><span data-stu-id="e35e9-336">Select to download SharedManagementObjects.msi only.</span></span>
        - <span data-ttu-id="e35e9-337">**注:** インストール メディアの Setup/amd64/ フォルダーに存在する既存のファイルを置き換える。</span><span class="sxs-lookup"><span data-stu-id="e35e9-337">**Note:** Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="e35e9-338">SQL CLR 型: https://www.microsoft.com/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="e35e9-338">SQL CLR Types: https://www.microsoft.com/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="e35e9-339">**注:** フィーチャー パックには、ダウンロードできるアイテムが多く含まれています。</span><span class="sxs-lookup"><span data-stu-id="e35e9-339">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="e35e9-340">Select to download CQLSysClrTypes.msi only</span><span class="sxs-lookup"><span data-stu-id="e35e9-340">Select to download CQLSysClrTypes.msi only</span></span>
        - <span data-ttu-id="e35e9-341">**注**: インストール メディアの Setup/amd64/ フォルダーに存在する既存のファイルを置き換える。</span><span class="sxs-lookup"><span data-stu-id="e35e9-341">**Note**: Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
5. <span data-ttu-id="e35e9-342">コア コンポーネントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="e35e9-342">Install Core Components:</span></span> 
    - <span data-ttu-id="e35e9-343">インストール Setup.exe Setup/amd64/ フォルダーからこのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e35e9-343">Run Setup.exe from the Setup/amd64/ folder of the installation media.</span></span> <span data-ttu-id="e35e9-344">指示に従ってコア コンポーネントをインストールする</span><span class="sxs-lookup"><span data-stu-id="e35e9-344">Follow the instructions to install Core Components</span></span>
    - <span data-ttu-id="e35e9-345">コア コンポーネントを閉じます。</span><span class="sxs-lookup"><span data-stu-id="e35e9-345">Close Core Components.</span></span>
6. <span data-ttu-id="e35e9-346">コア コンポーネントの更新:</span><span class="sxs-lookup"><span data-stu-id="e35e9-346">Update Core Components:</span></span> 
    - <span data-ttu-id="e35e9-347">Skype for Business Update インストーラーをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="e35e9-347">Download the Skype for Business Update Installer.</span></span>
    - <span data-ttu-id="e35e9-348">インストーラーを実行してコア コンポーネントを更新し、パフォーマンス カウンターをインストールします。</span><span class="sxs-lookup"><span data-stu-id="e35e9-348">Run the installer to update Core Components and install the performance counters.</span></span>
    - <span data-ttu-id="e35e9-349">**注:** CU6HF2 のリリースの現在、自動更新機能は CU6 までしかインストールされなに。</span><span class="sxs-lookup"><span data-stu-id="e35e9-349">**Note:** As of the release of CU6HF2, the auto-update feature currently only will install up to CU6.</span></span> <span data-ttu-id="e35e9-350">したがって、コア コンポーネントを 6.0.9319.516 に更新するには、アップデータツールを個別に実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e35e9-350">Therefore, the updater must be run separately to update Core Components to 6.0.9319.516.</span></span>
    - <span data-ttu-id="e35e9-351">リファレンス: https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015</span><span class="sxs-lookup"><span data-stu-id="e35e9-351">Reference: https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015</span></span>
7. <span data-ttu-id="e35e9-352">管理ツールをインストールする (オプション):</span><span class="sxs-lookup"><span data-stu-id="e35e9-352">Install Administrative Tools (Optional):</span></span> 
    - <span data-ttu-id="e35e9-353">これにより、更新されたファイルを使用して Microsoft SQL Server 2012 Native Client、SQL Server 2014 Management Objects (x64)、および Microsoft System CLR Types for SQL Server 2014 (x64) がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="e35e9-353">This will install the Microsoft SQL Server 2012 Native Client, SQL Server 2014 Management Objects (x64), and Microsoft System CLR Types for SQL Server 2014 (x64) using the updated files.</span></span> <span data-ttu-id="e35e9-354">また、Skype for Business Server 2015 トポロジ ビルダーとコントロール パネルは、ローカル コンピューターで使用できます。</span><span class="sxs-lookup"><span data-stu-id="e35e9-354">Additionally, the Skype for Business Server 2015 Topology Builder and Control Panel will be available on the local machine.</span></span>
8. <span data-ttu-id="e35e9-355">ローカル構成ストアのインストール (手順 1):</span><span class="sxs-lookup"><span data-stu-id="e35e9-355">Install Local Configuration Store (Step 1):</span></span> 
     - <span data-ttu-id="e35e9-356">展開ウィザードを開き、[Skype for Business Server システムのインストールまたは更新] をクリックし、[ステップ 1: ローカル構成ストアのインストール] で [実行] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e35e9-356">Open the Deployment Wizard, click Install or Update Skype for Business Server System, and click on **Run** at Step 1: Install Local Configuration Store.</span></span>
     - <span data-ttu-id="e35e9-357">[ローカル **構成ストア** の **インストール] ダイアログ ボックスで [次へ** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e35e9-357">Click **Next** in the **Install Local Configuration Store** dialog box.</span></span>
     <span data-ttu-id="e35e9-358">![[ローカル構成ストアのインストール] ダイアログ ボックス](../../media/local-configuration-store.png)</span><span class="sxs-lookup"><span data-stu-id="e35e9-358">![Install Local Configuration Store dialog box](../../media/local-configuration-store.png)</span></span>
     - <span data-ttu-id="e35e9-359">結果を確認し、タスクの状態が完了した状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="e35e9-359">Review the results, and ensure that the Task Status is Completed.</span></span> <span data-ttu-id="e35e9-360">[ログの表示] をクリックして、結果のログ ファイル **を確認します**。</span><span class="sxs-lookup"><span data-stu-id="e35e9-360">Review the resulting log file by clicking **View Log**.</span></span>
     <span data-ttu-id="e35e9-361">![タスクの状態が完了として表示される](../../media/local-configuration-task-completed.png)</span><span class="sxs-lookup"><span data-stu-id="e35e9-361">![Task status shows as Completed](../../media/local-configuration-task-completed.png)</span></span>
     - <span data-ttu-id="e35e9-362">**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e35e9-362">Click **Finish**.</span></span>
9. <span data-ttu-id="e35e9-363">Skype for Business Server コンポーネントをセットアップまたは削除する (手順 2):</span><span class="sxs-lookup"><span data-stu-id="e35e9-363">Set up or remove Skype for Business Server Components (Step 2):</span></span>
    - <span data-ttu-id="e35e9-364">展開ウィザードを開き **、[Skype for Business Server システム** のインストールまたは更新] をクリックし、[ステップ 2: Skype for Business Server コンポーネントのセットアップまたは削除] で [実行] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e35e9-364">Open the Deployment Wizard, click **Install or Update Skype for Business Server System**, and click **Run** at Step 2: Set up or Remove Skype for Business Server Components</span></span>
    - <span data-ttu-id="e35e9-365">**[Skype** for Business Server コンポーネントのセットアップ] ダイアログ ボックスで [次へ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e35e9-365">Click **Next** in the Set Up Skype for Business Server Components dialog box.</span></span>
    <span data-ttu-id="e35e9-366">![[Skype for Business Server コンポーネントのセットアップ] ウィンドウ](../../media/set-up-skype-for-business-server-components-window.png)</span><span class="sxs-lookup"><span data-stu-id="e35e9-366">![the Set Up Skype for Business Server Components window](../../media/set-up-skype-for-business-server-components-window.png)</span></span>
    - <span data-ttu-id="e35e9-367">ログの表示を使用してログを確認し、セットアップが問題なく完了したと確認します。</span><span class="sxs-lookup"><span data-stu-id="e35e9-367">Review the log using View Log, and validate that setup completed without issues.</span></span> 
    - <span data-ttu-id="e35e9-368">**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e35e9-368">Click **Finish**.</span></span>
10. <span data-ttu-id="e35e9-369">必要に応じて追加のインストールと構成を続行します (この時点で通常のインストール手順を再開できます)。</span><span class="sxs-lookup"><span data-stu-id="e35e9-369">Proceed with additional installation and configuration as required (you can resume normal installation procedures at this point).</span></span>
