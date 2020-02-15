---
title: Skype for Business Server 2015 で TLS 1.0/1.1 を無効にする
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: '概要: お使いの環境で TLS 1.0 および1.1 を無効にするための準備と実装を行います。'
ms.openlocfilehash: 0a25060463ed3b67db8ca523171c2bc48660293d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42012750"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a><span data-ttu-id="8ae3c-103">Skype for Business Server 2015 で TLS 1.0/1.1 を無効にする</span><span class="sxs-lookup"><span data-stu-id="8ae3c-103">Disable TLS 1.0/1.1 in Skype for Business Server 2015</span></span>

<span data-ttu-id="8ae3c-104">この記事の目的は、お客様の環境で TLS 1.0 および1.1 を無効にするための準備と実装に必要なガイダンスを提供することです。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-104">The purpose of this article is to provide the necessary guidance for you to prepare for and implement disabling TLS 1.0 and 1.1 in your environments.</span></span> <span data-ttu-id="8ae3c-105">このプロセスには、広範な計画と準備が必要です。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-105">This process requires extensive planning and preparation.</span></span> <span data-ttu-id="8ae3c-106">お客様の組織で TLS 1.0 および1.1 を無効にすることを計画している場合は、この記事に記載されているすべての情報を慎重に確認してください。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-106">Please carefully review all of the information in this article as you make your plan to disable TLS 1.0 and 1.1 for your organization.</span></span> <span data-ttu-id="8ae3c-107">TLS 1.0/1.1 を無効にすることによって影響を受ける可能性がある、多くの外部依存関係と接続条件があることに注意してください。詳細な計画とテストが保証されています。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-107">Note that there are many external dependencies and connectivity conditions that could be impacted by disabling TLS 1.0/1.1, so extensive planning and testing is warranted.</span></span>

## <a name="in-this-article"></a><span data-ttu-id="8ae3c-108">この記事の内容</span><span class="sxs-lookup"><span data-stu-id="8ae3c-108">In this article</span></span>

- [<span data-ttu-id="8ae3c-109">背景と範囲</span><span class="sxs-lookup"><span data-stu-id="8ae3c-109">Background and scope</span></span>](#background)
- [<span data-ttu-id="8ae3c-110">前提条件とプロセス</span><span class="sxs-lookup"><span data-stu-id="8ae3c-110">Prerequisites and process</span></span>](#prerequisites-and-process)
- [<span data-ttu-id="8ae3c-111">高度な展開シナリオ</span><span class="sxs-lookup"><span data-stu-id="8ae3c-111">Advanced deployment scenarios</span></span>](#advanced-deployment-scenarios)

## <a name="background"></a><span data-ttu-id="8ae3c-112">背景</span><span class="sxs-lookup"><span data-stu-id="8ae3c-112">Background</span></span>

<span data-ttu-id="8ae3c-113">TLS 1.0 および1.1 のサポートを無効にするための主なドライバーは、オンプレミスの Skype for Business Server のサポートを無効にすることです。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-113">The primary drivers for providing TLS 1.0 and 1.1 disable support for Skype for Business Server On-Premises are Payment Card Industry (PCI) Security Standards Council and Federal Information Processing Standards requirements.</span></span> <span data-ttu-id="8ae3c-114">PCI 要件の詳細については、[こちら](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-114">More information for PCI requirements can be found [here](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).</span></span>  <span data-ttu-id="8ae3c-115">Microsoft は、組織がこれらの要件に従う必要があるかどうかについてのガイダンスを提供することはできません。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-115">Microsoft cannot provide guidance on whether or not your organization is required to adhere to these or other requirements.</span></span> <span data-ttu-id="8ae3c-116">ご使用の環境で TLS 1.0 または1.1 を無効にする必要があるかどうかを判断する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-116">You must determine if it is required for you to disable TLS 1.0 and/or 1.1 in your environments.</span></span>

<span data-ttu-id="8ae3c-117">Microsoft は、[ここ](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/)で使用可能な TLS に関するホワイトペーパーを作成しました。また、この[Exchange ブログ](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)では背景の読み取りも推奨されています。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-117">Microsoft has produced a white paper on TLS available [here](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/), and we also recommend the background reading available in this [Exchange blog](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/).</span></span>

## <a name="supportability-scope"></a><span data-ttu-id="8ae3c-118">サポートの範囲</span><span class="sxs-lookup"><span data-stu-id="8ae3c-118">Supportability Scope</span></span>

<span data-ttu-id="8ae3c-119">*範囲*は、サポートの境界を参照します。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-119">*Scope* refers to supportability boundaries.</span></span> <span data-ttu-id="8ae3c-120">*完全にテストおよびサポート*されているということは、リストされている製品バージョンに対して TLS 1.0 および1.1 の無効化を完全にサポートしていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-120">*Fully tested and supported* means we fully support and have tested disabling of TLS 1.0 and 1.1 for the listed product versions.</span></span> <span data-ttu-id="8ae3c-121">現時点では、*調査中*であることを意味します。これらの製品を TLS 無効化サポートの対象にすることについて、積極的に調査しています。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-121">*Currently being investigated* means just that; we are actively investigating bringing these products into scope for TLS disable support.</span></span> <span data-ttu-id="8ae3c-122">*スコープが不足*している場合は、これらの製品バージョンは TLS 1.0 または1.1 の無効化をサポートしておらず、例外が報告されます。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-122">*Out of scope* means these product versions do not support disabling TLS 1.0 or 1.1 and will not work, with noted exceptions.</span></span>

### <a name="fully-tested-and-supported-servers"></a><span data-ttu-id="8ae3c-123">完全にテストおよびサポートされているサーバー</span><span class="sxs-lookup"><span data-stu-id="8ae3c-123">Fully tested and supported servers</span></span>

- <span data-ttu-id="8ae3c-124">Skype for Business Server 2019 CU1 17.0.2046.123 (2019 年6月) 以降</span><span class="sxs-lookup"><span data-stu-id="8ae3c-124">Skype for Business Server 2019 CU1 17.0.2046.123 (June 2019) or higher</span></span>
- <span data-ttu-id="8ae3c-125">Skype for Business Server 2015 CU9 6.0.9319.548 (2019 年5月) または Windows Server 2012 (KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in)または優先する更新プログラム)、2012 R2 または2016。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-125">Skype for Business Server 2015 CU9 6.0.9319.548 (May 2019) or higher on Windows Server 2012 (with KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseding update), 2012 R2 or 2016.</span></span>
- <span data-ttu-id="8ae3c-126">Windows Server 2008 R2、2012 (KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in)または優先される更新プログラム)、または 2012 R2 で、CU9 6.0.9319.548 (2019) またはそれ以上のインプレースアップグレードされた Skype For business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-126">In-place Upgraded Skype for Business Server 2015, with CU9 6.0.9319.548 (May 2019) or higher on Windows Server 2008 R2, 2012 (with KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseding update), or 2012 R2.</span></span>
- <span data-ttu-id="8ae3c-127">Exchange 接続と Outlook Web App と Exchange Server 2010 SP3 RU19 以降[のガイダンス](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span><span class="sxs-lookup"><span data-stu-id="8ae3c-127">Exchange Connectivity and Outlook Web App with Exchange Server 2010 SP3 RU19 or higher, guidance [here](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span></span>
- <span data-ttu-id="8ae3c-128">存続可能 Branch Appliance (SBA) (Skype for Business Server 2015 CU6 HF2 以降) (ベンダーによって、適切な更新プログラムがパッケージ化され、アプライアンスで利用可能になっていることをご確認ください)</span><span class="sxs-lookup"><span data-stu-id="8ae3c-128">Survivable Branch Appliance (SBA) with Skype for Business Server 2015 CU6 HF2 or higher (confirm with your vendor that they packaged the appropiate updates and have been made available for your appliance)</span></span>
- <span data-ttu-id="8ae3c-129">存続可能 Branch Server (SBS)、Skype for Business Server 2015 CU6 HF2 以降</span><span class="sxs-lookup"><span data-stu-id="8ae3c-129">Survivable Branch Server (SBS) with Skype for Business Server 2015 CU6 HF2 or higher</span></span>
- <span data-ttu-id="8ae3c-130">Lync Server 2013**エッジの役割のみ**。これはエッジの役割が Windows Fabric 1.0 に依存していないためです。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-130">Lync Server 2013 **Edge Role Only**, this is because Edge role does not have a dependency on Windows Fabric 1.0.</span></span>

### <a name="fully-tested-and-supported-clients"></a><span data-ttu-id="8ae3c-131">完全にテストおよびサポートされているクライアント</span><span class="sxs-lookup"><span data-stu-id="8ae3c-131">Fully tested and supported clients</span></span>

- <span data-ttu-id="8ae3c-132">Lync 2013 (Skype for Business) デスクトップクライアント、MSI、C2R (基本的な[15.0.5023.1000 またはそれ以降](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334))</span><span class="sxs-lookup"><span data-stu-id="8ae3c-132">Lync 2013 (Skype for Business) Desktop Client, MSI and C2R, including Basic [15.0.5023.1000 or higher](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)</span></span>
- <span data-ttu-id="8ae3c-133">Skype for Business 2016 デスクトップクライアント、MSI [16.0.4678.1000 またはそれ](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323)以上 (Basic を含む)</span><span class="sxs-lookup"><span data-stu-id="8ae3c-133">Skype for Business 2016 Desktop Client, MSI [16.0.4678.1000 or higher](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), including Basic</span></span>
- <span data-ttu-id="8ae3c-134">Skype for Business 2016 クリックして実行します。 [2018 年4月](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus)の更新プログラムが必要です。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-134">Skype for Business 2016 Click to Run Require the [April 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) Updates:</span></span> 
    - <span data-ttu-id="8ae3c-135">月間および半期の対象、16\.0\.9126\.2152 以降</span><span class="sxs-lookup"><span data-stu-id="8ae3c-135">Monthly and Semi-Annual Targeted, 16\.0\.9126\.2152 or higher</span></span>
    - <span data-ttu-id="8ae3c-136">半期チャネルと繰延チャネル、16\.0\.8431\.2242 以降</span><span class="sxs-lookup"><span data-stu-id="8ae3c-136">Semi-Annual and Deferred Channel, 16\.0\.8431\.2242 or higher</span></span>
- <span data-ttu-id="8ae3c-137">Mac 16.15 以降の Skype for Business</span><span class="sxs-lookup"><span data-stu-id="8ae3c-137">Skype for Business on Mac 16.15 or higher</span></span>
- <span data-ttu-id="8ae3c-138">IOS および Android 用の Skype for Business 6.19 以降</span><span class="sxs-lookup"><span data-stu-id="8ae3c-138">Skype for Business for iOS and Android 6.19 or higher</span></span>
- <span data-ttu-id="8ae3c-139">Microsoft Teams ルーム (以前の Skype Room System V2 SRS V2) の 4.0.64.0 (12 月 2018) 以上</span><span class="sxs-lookup"><span data-stu-id="8ae3c-139">Microsoft Teams Rooms (previously known as Skype Room System V2 SRS V2) 4.0.64.0 (December 2018) or higher</span></span>
- <span data-ttu-id="8ae3c-140">KB4499162 に基づく Team edition の Surface Hub 更新プログラム (2019 年5月、OS ビルド 15063.1835) 以降</span><span class="sxs-lookup"><span data-stu-id="8ae3c-140">Surface Hub update for Team edition based on KB4499162 (May 2019, OS Build 15063.1835) or higher</span></span>
- <span data-ttu-id="8ae3c-141">Skype Web App 2015 CU6 HF2 またはそれ以上 (サーバーに付属)</span><span class="sxs-lookup"><span data-stu-id="8ae3c-141">Skype Web App 2015 CU6 HF2 or higher (ships with Server)</span></span>

### <a name="currently-being-investigated"></a><span data-ttu-id="8ae3c-142">現在調査中</span><span class="sxs-lookup"><span data-stu-id="8ae3c-142">Currently being investigated</span></span>

- <span data-ttu-id="8ae3c-143">通話品質ダッシュボード (TLS 1.0 の後に新規インストールされます。1.1 は無効になっています。次を参照) \*</span><span class="sxs-lookup"><span data-stu-id="8ae3c-143">Call Quality Dashboard (new install after TLS 1.0, 1.1 have been disabled, see below)\*</span></span>
 
### <a name="out-of-scope"></a><span data-ttu-id="8ae3c-144">対象外</span><span class="sxs-lookup"><span data-stu-id="8ae3c-144">Out of scope</span></span>

<span data-ttu-id="8ae3c-145">記載されている場合を除き、次の製品は TLS 1.0/1.1 の無効化をサポートしていません。また、TLS 1.0 および1.1 が無効になっている環境では機能しません。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-145">Except where noted, the following products are not in scope for TLS 1.0/1.1 disable support and will not function in an environment where TLS 1.0 and 1.1 have been disabled.</span></span> <span data-ttu-id="8ae3c-146">その意味: スコープ外のサーバーまたはクライアントを引き続き使用している場合、Skype for Business Server のオンプレミス展開で TLS 1.0/1.1 を無効にする必要がある場合は、これらを更新または削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-146">What this means: if you still utilize out-of-scope servers or clients, you must update or remove these if you need to disable TLS 1.0/1.1 anywhere in your Skype for Business Server on-premises deployment.</span></span>

- <span data-ttu-id="8ae3c-147">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8ae3c-147">Lync Server 2013</span></span>
- <span data-ttu-id="8ae3c-148">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="8ae3c-148">Lync Server 2010</span></span>
- <span data-ttu-id="8ae3c-149">Windows Server 2008 またはそれ以降</span><span class="sxs-lookup"><span data-stu-id="8ae3c-149">Windows Server 2008 or lower</span></span>
- <span data-ttu-id="8ae3c-150">Lync for Mac 2011</span><span class="sxs-lookup"><span data-stu-id="8ae3c-150">Lync for Mac 2011</span></span>
- <span data-ttu-id="8ae3c-151">Lync 2013 for Mobile-iOS、iPad、Android、または Windows Phone</span><span class="sxs-lookup"><span data-stu-id="8ae3c-151">Lync 2013 for Mobile - iOS, iPad, Android or Windows Phone</span></span>
- <span data-ttu-id="8ae3c-152">Lync "MX" Windows ストアクライアント</span><span class="sxs-lookup"><span data-stu-id="8ae3c-152">Lync "MX" Windows Store client</span></span>
- <span data-ttu-id="8ae3c-153">Lync Room System (別名</span><span class="sxs-lookup"><span data-stu-id="8ae3c-153">Lync Room System (a.k.a.</span></span> <span data-ttu-id="8ae3c-154">SRSv1).</span><span class="sxs-lookup"><span data-stu-id="8ae3c-154">SRSv1).</span></span> <span data-ttu-id="8ae3c-155">LRS は、2018年10月9日にサポートの最後に達したため、TLS 1.2 をサポートするように更新されません。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-155">LRS reached end of support on October 9, 2018 and will not be updated to support TLS 1.2.</span></span>
- <span data-ttu-id="8ae3c-156">すべての Lync 2010 クライアント</span><span class="sxs-lookup"><span data-stu-id="8ae3c-156">All Lync 2010 clients</span></span>
- <span data-ttu-id="8ae3c-157">Lync Phone Edition-[ここで](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035)更新されたガイダンス。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-157">Lync Phone Edition - updated guidance [here](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).</span></span>
- <span data-ttu-id="8ae3c-158">2013ベースの存続可能 Branch Appliance (SBA) または存続可能 Branch Server (SBS)</span><span class="sxs-lookup"><span data-stu-id="8ae3c-158">2013 based Survivable Branch Appliance (SBA) or Survivable Branch Server (SBS)</span></span>
- <span data-ttu-id="8ae3c-159">Cloud Connector Edition (CCE)</span><span class="sxs-lookup"><span data-stu-id="8ae3c-159">Cloud Connector Edition (CCE)</span></span>
- <span data-ttu-id="8ae3c-160">Windows Phone 版 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="8ae3c-160">Skype for Business for Windows Phone</span></span>

### <a name="exceptions"></a><span data-ttu-id="8ae3c-161">Exceptions</span><span class="sxs-lookup"><span data-stu-id="8ae3c-161">Exceptions</span></span>

#### <a name="lync-server-2013"></a><span data-ttu-id="8ae3c-162">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8ae3c-162">Lync Server 2013</span></span>

<span data-ttu-id="8ae3c-163">Lync Server 2013 は、Windows Fabric バージョン1.0 に依存しています。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-163">Lync Server 2013 takes a dependency on Windows Fabric version 1.0.</span></span>  <span data-ttu-id="8ae3c-164">Lync Server 2013 の設計フェーズでは、レプリケーション、高可用性、フォールトトレランスを提供するために、魅力的で新しい分散アーキテクチャに Windows Fabric 1.0 が選択されました。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-164">In the design phase for Lync Server 2013, Windows Fabric 1.0 was chosen for its compelling and new distributed architecture to provide replication, high availability, and fault tolerance.</span></span>  <span data-ttu-id="8ae3c-165">時間の経過とともに、Skype for Business Server と Windows Fabric の両方が、今後のバージョンでの大幅な再設計により、この共同アーキテクチャを大幅に改善しました。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-165">Over time, both Skype for Business Server and Windows Fabric have greatly improved this joint architecture with significant re-design in subsequent versions.</span></span>  <span data-ttu-id="8ae3c-166">現在の Skype for Business 2015 Server は、Windows Fabric 3.0 を使用しています (例:)。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-166">Current Skype for Business 2015 Server uses Windows Fabric 3.0, for example.</span></span>

<span data-ttu-id="8ae3c-167">残念ながら、Windows Fabric 1.0**は TLS 1.2 をサポートしていません。 ただし、Lync Server 2013 を TLS 1.2 と連携するように更新**します。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-167">Unfortunately, Windows Fabric 1.0 **does not support TLS 1.2.  However, we will be updating Lync Server 2013 to work with TLS 1.2**.</span></span> <span data-ttu-id="8ae3c-168">これは、Lync Server 2013 の次の累積的な更新プログラムで提供されます。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-168">This will be coming in the next Cumulative Update for Lync Server 2013.</span></span>  <span data-ttu-id="8ae3c-169">マイクロソフトは、共存、移行、フェデレーション、およびハイブリッドシナリオを可能にするために TLS 1.2 サポートを提供しています。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-169">We're providing TLS 1.2 support to enable co-existence, migration, federation, and hybrid scenarios.</span></span>

<span data-ttu-id="8ae3c-170">組織で TLS 1.0 および1.1 を無効にする必要があり、現在 Lync Server 2013 を使用している場合は、計画プロセスを開始することをお勧めします。これにより、一括アップグレードまたは並行移行 (新しいプール、ユーザーの移動) が Skype for Business で必要になる可能性があります。Business Server 2015 以降。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-170">If your organization is required to disable TLS 1.0 and 1.1, and you currently use Lync Server 2013, we recommend you begin your planning process, with the possibility you may have to In-place upgrade or Side-by-Side migrate (new pools, move users) to Skype for Business Server 2015 or higher.</span></span>  <span data-ttu-id="8ae3c-171">または、Skype for Business Online への移行を高速化する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-171">Or you may want to accelerate migration to Skype for Business Online.</span></span>

#### <a name="call-quality-dashboard"></a><span data-ttu-id="8ae3c-172">通話品質ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="8ae3c-172">Call Quality Dashboard</span></span>

<span data-ttu-id="8ae3c-173">現在、オンプレミスの通話品質ダッシュボードは、新しいインストール時に TLS 1.0 に依存しています (オンプレミス環境への初めてのインストール)。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-173">On-Premises Call Quality Dashboard currently has a dependency on TLS 1.0 during new install (first time installing into your On-Premises environments).</span></span>  <span data-ttu-id="8ae3c-174">現在、この問題について調査しており、近い将来、修正プログラムのリリースを計画しています。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-174">We are currently investigating this issue and plan to release a fix in the near future.</span></span>  <span data-ttu-id="8ae3c-175">CQD のインストールと TLS 1.0 の無効化を計画している場合は、CQD のインストールを最初に完了してから、TLS 1.0 無効化を続行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-175">If you are planning to install CQD and also disable TLS 1.0, we recommend that you complete CQD installation first, and then proceed with TLS 1.0 disabling.</span></span>

#### <a name="third-party-devices"></a><span data-ttu-id="8ae3c-176">サードパーティ製デバイス</span><span class="sxs-lookup"><span data-stu-id="8ae3c-176">Third-party devices</span></span>

<span data-ttu-id="8ae3c-177">3PIP 電話、ビデオ会議、リバースプロキシ、ロードバランサーなどのサードパーティ製デバイスでは、TLS 1.2 のサポートを検証し、必要に応じて、ベンダーに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-177">On third-party devices such as 3PIP phones, Video conferencing, Reverse Proxies and Load Balancers, be sure to validate TLS 1.2 supportability, test carefully, and contact the vendor if needed.</span></span>

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a><span data-ttu-id="8ae3c-178">エッジサーバーで TLS 1.0/1.1 を無効にするときのフェデレーションに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="8ae3c-178">Federation considerations when disabling TLS 1.0/1.1 on Edge servers</span></span>

<span data-ttu-id="8ae3c-179">エッジサーバーで TLS 1.0/1.1 を無効にすることによる影響を慎重に計画し、検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-179">You must carefully plan for and consider the impact of disabling TLS 1.0/1.1 on your Edge servers.</span></span>  <span data-ttu-id="8ae3c-180">TLS 1.0 および1.1 を無効にすると、他の組織が組織とフェデレーションできなくなることがあります。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-180">Once TLS 1.0 and 1.1 are disabled, you may find that other organizations are no longer be able to federate with your organization.</span></span>

<span data-ttu-id="8ae3c-181">エッジサーバー上で TLS 1.0/1.1 を有効にしたままにして、適用されていない (SfB 2015、Lync 2013) または古い (2010) 外部システムとの下位互換性を維持することができます。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-181">You may opt to keep TLS 1.0/1.1 enabled on your Edge servers to maintain backward compatibility with non-patched (SfB 2015, Lync 2013) or older (2010) external systems.</span></span>

<span data-ttu-id="8ae3c-182">Microsoft は、エッジネットワーク (またはネットワーク) が PCI standard の下にあるかどうかに関するアドバイスや推奨事項を提供することはできません。これは、個々の会社によって決定される必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-182">Microsoft cannot provide advice or recommendations on whether or not your Edge network (or any network) falls under PCI standard; that must be determined by the individual company.</span></span>

<span data-ttu-id="8ae3c-183">Skype for Business Online は現在、TLS 1.2 をサポートしているため、オンラインとのハイブリッド/フェデレーションへの影響は期待できません。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-183">Skype for Business Online is capable of TLS 1.2 today, so no impact to Hybrid/Federation with Online is expected.</span></span>

<span data-ttu-id="8ae3c-184">PIC (パブリック IM 接続) から Skype コンシューマサービスへ: [Skype 接続](../../deploy/deploy-skype-connectivity.md)に影響を与えるために TLS 1.0/1.1 を無効にすることは想定されていません。Microsoft PIC ゲートウェイは、既に TLS 1.2 に対応しています。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-184">PIC (Public IM Connectivity) to Skype Consumer service: We do not expect disabling TLS 1.0/1.1 to impact [Skype Connectivity](../../deploy/deploy-skype-connectivity.md); Microsoft PIC Gateways are already TLS 1.2 capable.</span></span>

## <a name="prerequisites-and-process"></a><span data-ttu-id="8ae3c-185">前提条件とプロセス</span><span class="sxs-lookup"><span data-stu-id="8ae3c-185">Prerequisites and process</span></span>

<span data-ttu-id="8ae3c-186">上記の場合を除き、TLS 1.0 および1.1 がスコープ外のサーバーを無効にすると、クライアントとデバイスは正常に機能しなくなります。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-186">Except where noted above, once TLS 1.0 and 1.1 are disabled out-of-scope servers, clients and devices will longer function properly, or at all.</span></span> <span data-ttu-id="8ae3c-187">これは、更新されたガイダンスを Microsoft から一時停止して待つ必要があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-187">This may mean you need to pause and wait for updated guidance from Microsoft.</span></span> <span data-ttu-id="8ae3c-188">すべての要件を満たしていて、ギャップに対処するための計画を立てることができれば、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-188">Once you are satisfied that you meet all requirements and have a plan to address gaps, proceed.</span></span>

<span data-ttu-id="8ae3c-189">詳細については、「skype for business Server 2019 をインストール時に準備する」の手順を実行する必要があります。 Skype for business Server 2015 では、CU9 をインストールし、前提条件の更新プログラムを .NET および SQL に適用して、必要なレジストリキーを展開し、最終的に別のオペレーティングシステム構成の更新 (レジストリファイルのインポートによる TLS 1.0 および1.1 の無効化)</span><span class="sxs-lookup"><span data-stu-id="8ae3c-189">At a high level, while Skype for Business Server 2019 is ready for procedure at install, Skype for Business Server 2015 will require that you install CU9, applying pre-requisite updates to .NET and SQL, deploying prerequisite registry keys, and finally a separate round of OS configuration updates (i.e. disabling TLS 1.0 and 1.1 via registry file import).</span></span> <span data-ttu-id="8ae3c-190">環境内のすべてのサーバーで TLS 1.0 および1.1 を無効にする前に、Skype for Business Server 2015 CU6 HF2 などのすべての必須コンポーネントのインストールを完了することが非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-190">It is critically important that you complete installation of all prerequisites, including Skype for Business Server 2015 CU6 HF2, prior to disabling TLS 1.0 and 1.1 on any server in your environment.</span></span> <span data-ttu-id="8ae3c-191">エッジの役割と SQL バックエンドを含む、すべての Skype for Business server は更新を必要とします。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-191">Every Skype for Business server, including Edge role and SQL Backends, requires the updates.</span></span> <span data-ttu-id="8ae3c-192">また、サポートされている (スコープ内の) すべてのクライアントが必要な最小バージョンに更新されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-192">Also ensure that all supported (in-scope) clients have been updated to the required minimum versions.</span></span> <span data-ttu-id="8ae3c-193">管理ワークステーションも更新することを忘れないでください。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-193">Don’t forget to update management workstations as well.</span></span>

<span data-ttu-id="8ae3c-194">Skype for Business サーバーをアップグレードする場合、"インサイド out" の通常の操作順序に従ってください。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-194">We want to follow the usual order of operations of "inside out" for upgrading Skype for Business servers.</span></span> <span data-ttu-id="8ae3c-195">通常と同じ方法で、ディレクタープール、常設チャット、およびペアプールを処理します。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-195">Treat Director pools, Persistent chat, and Paired Pools in the same manner you normally would.</span></span> <span data-ttu-id="8ae3c-196">[ここ](topology.md)では、アップグレードの順序と方法に[ついて説明します。](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="8ae3c-196">Order and methods for upgrade are covered [here](topology.md) and [here](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>

### <a name="high-level-process"></a><span data-ttu-id="8ae3c-197">高レベルのプロセス</span><span class="sxs-lookup"><span data-stu-id="8ae3c-197">High-level process</span></span>

1. <span data-ttu-id="8ae3c-198">運用サーバーを構成する前に、ラボのすべての手順をテストします。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-198">Test all steps in your lab prior to configuring production servers.</span></span>
2. <span data-ttu-id="8ae3c-199">更新する個々のサーバーごとに、エクスポートされたレジストリのコピーをバックアップして保持します。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-199">Back up and preserve a copy of exported registry on each and every individual server to be updated.</span></span> <span data-ttu-id="8ae3c-200">サーバー間でレジストリを共有することはできません。これには、マシンベースの一意のキーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-200">You cannot share registries between servers; they contain unique machine-based keys.</span></span>
3. <span data-ttu-id="8ae3c-201">すべての Skype for Business 2015 サーバーを CU9 以降にアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-201">Upgrade all Skype for Business 2015 servers to CU9 or higher.</span></span> <span data-ttu-id="8ae3c-202">Skype for Business Server 2019 の場合は、CU1 以降にアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-202">For Skype for Business Server 2019, upgrade to CU1 or higher.</span></span>
4. <span data-ttu-id="8ae3c-203">すべての必須コンポーネントをすべてのサーバーにインストールします。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-203">Install all prerequisites to all servers.</span></span>
5. <span data-ttu-id="8ae3c-204">前提条件となるレジストリキーを展開します。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-204">Deploy prerequisite registry keys.</span></span>
6. <span data-ttu-id="8ae3c-205">範囲内のすべてのクライアントが更新されるようにします。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-205">Ensure that all in-scope clients are updated.</span></span>
7. <span data-ttu-id="8ae3c-206">レジストリインポート経由で TLS 1.0 および1.1 を無効にします。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-206">Disable TLS 1.0 and 1.1 via registry import.</span></span>
8. <span data-ttu-id="8ae3c-207">ワークロードが予想どおりに機能していることを検証します。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-207">Validate that workloads are functioning as expected.</span></span>
    - <span data-ttu-id="8ae3c-208">問題が発生した場合、トラブルシューティングと解決、または</span><span class="sxs-lookup"><span data-stu-id="8ae3c-208">If problems are encountered, troubleshoot and resolve, or</span></span>
    - <span data-ttu-id="8ae3c-209">手順2のレジストリを復元して、TLS 1.0 および1.1 を再度有効にする</span><span class="sxs-lookup"><span data-stu-id="8ae3c-209">Restore registry from step 2 to re-enable TLS 1.0 and 1.1</span></span>
9. <span data-ttu-id="8ae3c-210">TLS 1.2 のみが使用されていることを検証します。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-210">Validate that only TLS 1.2 is being used.</span></span>

### <a name="install-prerequisites-to-all-servers"></a><span data-ttu-id="8ae3c-211">必須コンポーネントをすべてのサーバーにインストールする</span><span class="sxs-lookup"><span data-stu-id="8ae3c-211">Install prerequisites to all servers</span></span>

<span data-ttu-id="8ae3c-212">Skype for Business Server の2015展開で、オペレーティングシステムレベルで TLS 1.0 および1.1 の無効化を開始する前に、広範な依存関係の更新を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-212">Extensive dependency updating is required before you begin to disable TLS 1.0 and 1.1 at the operating system level in your Skype for Business Server 2015 deployments.</span></span> <span data-ttu-id="8ae3c-213">TLS 1.2 をサポートできる最小バージョンは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-213">The following are the minimum versions that can support TLS 1.2.</span></span> <span data-ttu-id="8ae3c-214">TLS 1.0 および1.1 の無効化を開始する前に、前提条件となるすべての更新プログラムを環境内のすべての Skype for Business サーバーに展開します。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-214">Deploy all prerequisite updates across every Skype for Business server in your environment before you begin disabling TLS 1.0 and 1.1.</span></span>

- <span data-ttu-id="8ae3c-215">Skype for Business Server 2015 CU9 6.0.9319.548 (2019 年5月) 以降</span><span class="sxs-lookup"><span data-stu-id="8ae3c-215">Skype for Business Server 2015 CU9 6.0.9319.548 (May 2019) or higher</span></span>
- <span data-ttu-id="8ae3c-216">レジストリで SchUseStrongCrypto が有効になっている[.Net Framework 4.7](https://www.microsoft.com/download/details.aspx?id=55167)またはそれ以降 (以下に提供)</span><span class="sxs-lookup"><span data-stu-id="8ae3c-216">[.NET Framework 4.7](https://www.microsoft.com/download/details.aspx?id=55167) or higher with SchUseStrongCrypto enabled in the registry (provided below)</span></span>
- <span data-ttu-id="8ae3c-217">すべての Skype for Business 2015 サーバーおよびバックエンドで、SQL を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-217">SQL must be updated on all Skype for Business 2015 servers and backends.</span></span> <span data-ttu-id="8ae3c-218">最初に Enterprise Edition プールの SQL バックエンドを更新し、次にそれぞれの FEs を更新します。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-218">Update Enterprise Edition Pool SQL Backends first, then their respective FEs.</span></span> 
    - <span data-ttu-id="8ae3c-219">[Sql server 2014 SP1 + CU5](https://support.microsoft.com/help/3130926)、またはそれ以降の sql SERVER 2012 SP2 + CU16 または sql SERVER [2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014)、またはそれ以降の/sql server 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="8ae3c-219">[SQL Server 2014 SP1 + CU5](https://support.microsoft.com/help/3130926), or higher / SQL Server 2012 SP2 + CU16 or higher / [SQL Server 2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014), or higher / SQL Server 2014 SP2</span></span>
     - [<span data-ttu-id="8ae3c-220">Sql Server の sql server Native Client 2012</span><span class="sxs-lookup"><span data-stu-id="8ae3c-220">SQL Server Native Client for SQL Server 2012</span></span>](https://www.microsoft.com/download/details.aspx?id=50402)
     - <span data-ttu-id="8ae3c-221">[SQL Server 以降の MICROSOFT ODBC Driver 11](https://www.microsoft.com/download/details.aspx?id=36434)</span><span class="sxs-lookup"><span data-stu-id="8ae3c-221">[Microsoft ODBC Driver 11 for SQL Server](https://www.microsoft.com/download/details.aspx?id=36434), or higher</span></span>
     - [<span data-ttu-id="8ae3c-222">SQL Server 2014 SP2 の共有管理オブジェクト</span><span class="sxs-lookup"><span data-stu-id="8ae3c-222">Shared Management Objects for SQL Server 2014 SP2</span></span>](https://www.microsoft.com/download/details.aspx?id=53164)
     - [<span data-ttu-id="8ae3c-223">SQL server 2014 SP2 の SQLSysClrTypes</span><span class="sxs-lookup"><span data-stu-id="8ae3c-223">SQLSysClrTypes for SQL server 2014 SP2</span></span>](https://www.microsoft.com/download/details.aspx?id=42295)

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a><span data-ttu-id="8ae3c-224">推奨される操作順序で必要な前提条件をインストールするための基本的な手順</span><span class="sxs-lookup"><span data-stu-id="8ae3c-224">Basic steps to install pre-requisites, in recommended order of operations</span></span>

1. <span data-ttu-id="8ae3c-225">Skype for Business Server CU9 の更新プログラムをすべてのサーバーにインストールします。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-225">Install the Skype for Business Server CU9 update to all servers.</span></span> 
    1. <span data-ttu-id="8ae3c-226">アップデーターを使用して、コンポーネントの更新プログラムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-226">Install the update to components using the updater.</span></span>
    2. <span data-ttu-id="8ae3c-227">ドキュメントに記載されている手順に従ってデータベースを更新します。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-227">Update databases according to documented procedures.</span></span> <span data-ttu-id="8ae3c-228">Skype for Business Server 2015 については、「KB [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-228">For Skype for Business Server 2015, see KB [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>
    3. <span data-ttu-id="8ae3c-229">他の変更を加えて前に進む前に、展開の製品機能を検証します。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-229">Validate product functionality in the deployment prior to moving forward with any other changes.</span></span>
2. <span data-ttu-id="8ae3c-230">.NET 4.7 オフラインインストーラーをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-230">Download .NET 4.7 Offline Installer.</span></span> 
    1. <span data-ttu-id="8ae3c-231">参考[https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)</span><span class="sxs-lookup"><span data-stu-id="8ae3c-231">Reference: [https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)</span></span>
    2. <span data-ttu-id="8ae3c-232">フロントエンドサーバーで、Skype for Business Server 2015 サービスが停止していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-232">Ensure that Skype for Business Server 2015 services are stopped on the Front End server.</span></span>
    3. <span data-ttu-id="8ae3c-233">参考[https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="8ae3c-233">Reference: [https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span></span>
    4. <span data-ttu-id="8ae3c-234">Ex (Standard Edition):```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="8ae3c-234">Ex (Standard Edition): ```Stop-CsWindowsService```</span></span>
    5. <span data-ttu-id="8ae3c-235">Ex (Enterprise Edition):```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="8ae3c-235">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    6. <span data-ttu-id="8ae3c-236">インストーラパッケージを実行します。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-236">Run the installer package.</span></span>
    7. <span data-ttu-id="8ae3c-237">サーバーを再起動します。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-237">Reboot the server.</span></span>
3. <span data-ttu-id="8ae3c-238">すべてのサーバーで SQL Express 2014 を更新します。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-238">Update SQL Express 2014 on all servers.</span></span> 
    1. <span data-ttu-id="8ae3c-239">参考[https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span><span class="sxs-lookup"><span data-stu-id="8ae3c-239">Reference: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span></span>
    2. <span data-ttu-id="8ae3c-240">SQL 2014 SP2 をダウンロードする</span><span class="sxs-lookup"><span data-stu-id="8ae3c-240">Download SQL 2014 SP2</span></span> 
        - <span data-ttu-id="8ae3c-241">参考[https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)</span><span class="sxs-lookup"><span data-stu-id="8ae3c-241">Reference: [https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)</span></span>
    3. <span data-ttu-id="8ae3c-242">インストールメディアをサーバー上のフォルダー (例: C:\ 01_2014SqlSp2) にコピーします。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-242">Copy the installation media to a folder on the server (Ex: C:\01_2014SqlSp2)</span></span>
    4. <span data-ttu-id="8ae3c-243">フロントエンドサーバーで Skype for Business Server 2015 サービスが停止していることを確認する</span><span class="sxs-lookup"><span data-stu-id="8ae3c-243">Ensure Skype for Business Server 2015 services are stopped on the Front End server</span></span> 
        - <span data-ttu-id="8ae3c-244">Ex (Standard Edition):```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="8ae3c-244">Ex (Standard Edition): ```Stop-CsWindowsService```</span></span>
        - <span data-ttu-id="8ae3c-245">Ex (Enterprise Edition):```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="8ae3c-245">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    5. <span data-ttu-id="8ae3c-246">管理者コマンドプロンプトを開き、インストールされているすべてのコンポーネントとインスタンスをアップグレードする</span><span class="sxs-lookup"><span data-stu-id="8ae3c-246">Open an Admin Command Prompt, and upgrade all installed components and instances</span></span> 
        - <span data-ttu-id="8ae3c-247">例: C:\ 01_2014SqlSp2 \SQLServer2014SP2-KB3171021-x64-ENU.exe/qs/IAcceptSQLServerLicenseTerms/Action = Patch/allinstances</span><span class="sxs-lookup"><span data-stu-id="8ae3c-247">Example: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action=Patch /AllInstances</span></span>
4. <span data-ttu-id="8ae3c-248">SQL ネイティブクライアントを更新します。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-248">Update SQL Native Client.</span></span> 
    1. <span data-ttu-id="8ae3c-249">リファレンス: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-249">Reference: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span></span>
    2. <span data-ttu-id="8ae3c-250">ダウンロード元[https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)</span><span class="sxs-lookup"><span data-stu-id="8ae3c-250">Download from [https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)</span></span>
    3. <span data-ttu-id="8ae3c-251">フロントエンドサーバーで Skype for Business Server 2015 サービスが停止していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-251">Ensure Skype for Business Server 2015 services are stopped on the Front End server.</span></span> 
        - <span data-ttu-id="8ae3c-252">Ex (Standard Edition):```Stop-CsWindowsServices```</span><span class="sxs-lookup"><span data-stu-id="8ae3c-252">Ex (Standard Edition): ```Stop-CsWindowsServices```</span></span>
        - <span data-ttu-id="8ae3c-253">Ex (Enterprise Edition):```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="8ae3c-253">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    4. <span data-ttu-id="8ae3c-254">実行時にインストールされた SQL インスタンスを停止する</span><span class="sxs-lookup"><span data-stu-id="8ae3c-254">Stop the SQL instances installed from running</span></span> 
        - <span data-ttu-id="8ae3c-255">渡し```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="8ae3c-255">Ex: ```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```</span></span>
        - <span data-ttu-id="8ae3c-256">渡し```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="8ae3c-256">Ex: ```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```</span></span>
        - <span data-ttu-id="8ae3c-257">Ex (Standard Edition のみ):```Get-Service 'MSSQL$RTC' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="8ae3c-257">Ex (Standard Edition Only): ```Get-Service 'MSSQL$RTC' | Stop-Service```</span></span>
    5. <span data-ttu-id="8ae3c-258">更新プログラムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-258">Install the update.</span></span>
5. <span data-ttu-id="8ae3c-259">SQL Server 用の ODBC Driver 11 を更新して、TLS 1.2 のサポートを含めます (KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server))。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-259">Update ODBC Driver 11 for SQL Server to include support for TLS 1.2 (KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)).</span></span>
    1. <span data-ttu-id="8ae3c-260">[SQL Server の ODBC Driver 11 をダウンロードしてください-Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434)。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-260">Download [ODBC Driver 11 for SQL Server - Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434).</span></span>
    2. <span data-ttu-id="8ae3c-261">フロントエンドサーバーで、Skype for Business Server 2015 サービスが停止していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-261">Ensure that Skype for Business Server 2015 services are stopped on the Front End server.</span></span>
        - <span data-ttu-id="8ae3c-262">例 (Standard Edition):```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="8ae3c-262">Example (Standard Edition): ```Stop-CsWindowsService```</span></span>
        - <span data-ttu-id="8ae3c-263">例 (Enterprise Edition):```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="8ae3c-263">Example (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    3. <span data-ttu-id="8ae3c-264">更新プログラムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-264">Install the update.</span></span>
6. <span data-ttu-id="8ae3c-265">前提条件となるレジストリキーを展開します。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-265">Deploy prerequisite registry keys.</span></span>

### <a name="pre-requisite-registry-keys"></a><span data-ttu-id="8ae3c-266">前提条件となるレジストリキー</span><span class="sxs-lookup"><span data-stu-id="8ae3c-266">Pre-requisite registry keys</span></span>

<span data-ttu-id="8ae3c-267">次のテストをコピーしてメモ帳に貼り付け、TLSPreReq または任意の名前を変更してから、インポートします。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-267">Copy/paste the following test into Notepad and rename TLSPreReq.reg or a name of your choice, then import:</span></span>

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

<span data-ttu-id="8ae3c-268">Enterprise Edition プールの SQL バックエンドの場合、前提条件と TLS の無効化は、SQL または OS の更新と同様に処理する必要があります。以下を参照してください。[https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span><span class="sxs-lookup"><span data-stu-id="8ae3c-268">For SQL back ends for Enterprise Edition Pools, prerequisites and TLS disable should be treated as any SQL or OS updates would; refer to: [https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span></span>

<span data-ttu-id="8ae3c-269">前提条件となるアプリケーションと TLS の無効化手順の両方を組み合わせることができますが、オペレーティングシステムレベルで TLS 1.0 および1.1 を無効にする前に、すべての前提条件を適用することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-269">While both the prerequisite application and TLS disabling steps can be combined, we strongly recommend all prerequisites be applied before proceeding with disabling of TLS 1.0 and 1.1 at the operating system level.</span></span> <span data-ttu-id="8ae3c-270">ベストプラクティスの方法は、すべての前提条件を展開して環境を準備し、ワークロードがすべて正常に機能していることを検証して、後で TLS 1.0/1.1 を無効にすることです。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-270">The best practice approach would be to prepare the environment by deploying all prerequisites, validating that workloads all function correctly and as expected, and then proceeding with TLS 1.0/1.1 disable at a later time.</span></span>

### <a name="disable-tls-10-and-11-via-registry-import"></a><span data-ttu-id="8ae3c-271">レジストリインポートによる TLS 1.0 および1.1 の無効化</span><span class="sxs-lookup"><span data-stu-id="8ae3c-271">Disable TLS 1.0 and 1.1 via registry import</span></span>

<span data-ttu-id="8ae3c-272">次の手順に進む前に、*すべての前提条件と更新された Skype For Business サーバーを完了*していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-272">Before you proceed with the next steps, *make sure you have completed all prerequisites and updated Skype for Business Servers*.</span></span>

<span data-ttu-id="8ae3c-273">次のテキストをメモ帳ファイルにコピーして、 **TLSDisable**の名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-273">Copy the following text into a Notepad file and rename it **TLSDisable.reg**:</span></span>

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

<span data-ttu-id="8ae3c-274">TLS 1.0 および1.1 を無効にする各サーバーに .reg ファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-274">Import the .reg file on each server you wish to disable TLS 1.0 and 1.1.</span></span> <span data-ttu-id="8ae3c-275">サーバーを再起動します。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-275">Reboot the server.</span></span> <span data-ttu-id="8ae3c-276">サービスがオンラインに戻ったら、次のサーバーに移動します。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-276">Once the services have come back online, move to the next server.</span></span> <span data-ttu-id="8ae3c-277">Enterprise Edition プールのアプローチは、すべての OS 更新に対して実行するのと同じです。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-277">The approach for Enterprise Edition Pools is the same you would take for any OS update.</span></span>

<span data-ttu-id="8ae3c-278">ここでは、TLS 1.0 および1.1 を無効にするだけではありません。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-278">You may have noticed we are doing more than just disabling TLS 1.0 and 1.1 here.</span></span> <span data-ttu-id="8ae3c-279">(前述のように) 暗号スイートの再オーダーをサポートしており、一部の古い弱い暗号を無効にしています。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-279">We are supporting Cipher Suite re-order (as shown above) and the disabling of some older weak ciphers.</span></span> <span data-ttu-id="8ae3c-280">この変更は、Skype for Business Server での SCHANNEL および Crypto API への初めての変更を正式にサポートしています。これらの変更は、現時点でサポートおよびテストしたものだけであることに注意することが重要です。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-280">This is the first time we have officially supported these changes to SCHANNEL and Crypto API on Skype for Business Server, and it is important to note that these changes are the only ones we support and have tested at this time.</span></span> <span data-ttu-id="8ae3c-281">今後、追加の構成を検討する場合がありますが、現時点では、実装でレジストリインポートファイルを変更しないでください。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-281">We may consider additional configurations in the future, but for now, please do not modify the registry import file in your implementation.</span></span>

### <a name="validate-that-workloads-are-functioning-as-expected"></a><span data-ttu-id="8ae3c-282">ワークロードが予想どおりに機能していることを検証する</span><span class="sxs-lookup"><span data-stu-id="8ae3c-282">Validate that workloads are functioning as expected</span></span>

<span data-ttu-id="8ae3c-283">ご使用の環境で TLS 1.0 および1.1 が無効になったら、IM & プレゼンス、P2P 呼び出し、エンタープライズ Voip など、すべての主要なワークロードが想定どおりに機能していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-283">Once TLS 1.0 and 1.1 have been disabled in your environment, ensure that all your main workloads are functioning as expected, such as IM & Presence, P2P calls, Enterprise Voice, etc.</span></span>

<span data-ttu-id="8ae3c-284">**TLS 1.2 のみが使用されていることを確認する**</span><span class="sxs-lookup"><span data-stu-id="8ae3c-284">**Validate only TLS 1.2 is being used**</span></span>

<span data-ttu-id="8ae3c-285">セキュリティチームが Skype for Business トラフィックの新しい監査を実行して、古いプロトコルの TLS 1.0 および1.1 が使用されなくなっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-285">Have your Security Team perform a new audit of Skype for Business traffic to ensure that the older protocols TLS 1.0 and 1.1 are no longer in use.</span></span>

<span data-ttu-id="8ae3c-286">または、Internet Explorer を使用して、TLS 1.0 および TLS 1.1 を無効にした後、Skype for Business Server 2015 から web サービスへの TLS 接続をテストすることもできます。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-286">Alternatively, you can use Internet Explorer to test TLS connections to web services from Skype for Business Server 2015 after TLS 1.0 and TLS 1.1 have been disabled.</span></span>

1. <span data-ttu-id="8ae3c-287">Internet Explorer を起動します。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-287">Launch Internet Explorer.</span></span>
2. <span data-ttu-id="8ae3c-288">[**ツール** > ] [**インターネットオプション**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-288">Select **Tools** > **Internet Options**.</span></span>
3. <span data-ttu-id="8ae3c-289">[**詳細設定**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-289">Select the **Advanced** tab.</span></span>
4. <span data-ttu-id="8ae3c-290">[**設定**] で、一番下までスクロールします。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-290">Under **Settings**, scroll to the bottom.</span></span>
5. <span data-ttu-id="8ae3c-291">TLS 1.0、TLS 1.1、および TLS 1.2 が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-291">Verify that TLS 1.0, TLS 1.1, and TLS 1.2 are enabled.</span></span>
6. <span data-ttu-id="8ae3c-292">SfB 2015 プールの内部 Web サービス URL を参照します (正常に接続されている必要があります)。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-292">Browse the Internal Web Service URL of your SfB 2015 pool (should connect successfully).</span></span>
7. <span data-ttu-id="8ae3c-293">Internet Explorer に戻り、 **TLS 1.2**のみを使用するオプションを無効にします。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-293">Go back into Internet Explorer and disable the option to **Use TLS 1.2** only.</span></span>
8. <span data-ttu-id="8ae3c-294">SfB 2015 プールの内部 Web サービス URL をもう一度参照してください (接続に失敗する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-294">Browse the Internal Web Service URL of your SfB 2015 pool again (should fail to connect).</span></span>

![インターネットオプション](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a><span data-ttu-id="8ae3c-296">高度な展開シナリオ</span><span class="sxs-lookup"><span data-stu-id="8ae3c-296">Advanced deployment scenarios</span></span>

<span data-ttu-id="8ae3c-297">Skype for Business Ser 2015 で TLS 1.2 をサポートするには、いくつかの依存関係の前提条件が必要になるため、TLS 1.0 および1.1 が無効になっているシステムでは、RTM メディアからのインストールは失敗します。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-297">Because some dependency prerequisites are required to support TLS 1.2 in Skype for Business Ser 2015, installing from RTM media will fail on any system where TLS 1.0 and 1.1 have been disabled.</span></span>

<span data-ttu-id="8ae3c-298">**TLS 1.0 および1.1 が環境で無効になっている場合、新しい Standard Edition サーバーまたは Enterprise Edition プールを展開します。**</span><span class="sxs-lookup"><span data-stu-id="8ae3c-298">**Deploying New Standard Edition Servers or Enterprise Edition Pools once TLS 1.0 and 1.1 have been disabled in your environment.**</span></span>

<span data-ttu-id="8ae3c-299">**オプション 1:**[Smartsetup](../../deploy/install/install-skype-for-business-server.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-299">**Option 1:** Use [SmartSetup](../../deploy/install/install-skype-for-business-server.md).</span></span> <span data-ttu-id="8ae3c-300">今後の CU では、更新された SQL バイナリに対応するように SmartSetup を更新しています。今後、この記事を更新します。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-300">Note that we are updating SmartSetup to accommodate the updated SQL binaries in a future CU, and will update this article in the future.</span></span>

<span data-ttu-id="8ae3c-301">**オプション 2:** ローカル SQL インスタンスのインストール前 (RTCLOCAL および LYNCLOCAL)</span><span class="sxs-lookup"><span data-stu-id="8ae3c-301">**Option 2:** Pre-install local SQL instances (RTCLOCAL and LYNCLOCAL)</span></span>

1. <span data-ttu-id="8ae3c-302">SQL Express 2014 SP2 (SQLEXPR_x64) を FE のローカルフォルダーにダウンロードしてコピーします。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-302">Download and copy SQL Express 2014 SP2 (SQLEXPR_x64.exe) to local folder on FE.</span></span> <span data-ttu-id="8ae3c-303">フォルダーのパス <SQL_FOLDER_PATH> について説明します。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-303">Let’s say folder path <SQL_FOLDER_PATH>.</span></span>
2. <span data-ttu-id="8ae3c-304">PowerShell またはコマンドプロンプトを起動し、<SQL_FOLDER_PATH> に移動します。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-304">Launch PowerShell or Command Prompt and navigate to <SQL_FOLDER_PATH>.</span></span>
3. <span data-ttu-id="8ae3c-305">次のコマンドを実行して、RTCLOCAL SQL インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-305">Create the RTCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="8ae3c-306">続行する前に SQLEXPR_x64 exe が終了するまで待機します。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-306">Wait until SQLEXPR_x64.exe finishes before proceeding:</span></span>

    <span data-ttu-id="8ae3c-307">SQLEXPR_x64/IACCEPTSQLSERVERLICENSETERMS/Q/updateenabled = 0/hideconall/ACTION = Install/FEATURES = SQLEngine, Tools/INSTANCENAME = RTCLOCAL/tcpenabled = 1/SQLSVCACCOUNT = "NT AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS = "Builtin\Administrators"/BROWSERSVCSTARTUPTYPE = "Automatic"/AGTSVCACCOUNT = "NTAUTHORITY\NetworkService"/SQLSVCSTARTUPTYPE = Automati</span><span class="sxs-lookup"><span data-stu-id="8ae3c-307">SQLEXPR_x64.exe  /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=RTCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automati</span></span>
1. <span data-ttu-id="8ae3c-308">次のコマンドを実行して、LYNCLOCAL SQL インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-308">Create the LYNCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="8ae3c-309">SQLEXPR_x64 .exe が終了するまで待ってから、次の手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-309">Wait until SQLEXPR_x64.exe finishes before proceeding to the next step:</span></span>

    <span data-ttu-id="8ae3c-310">SQLEXPR_x64. .exe/Q/IACCEPTSQLSERVERLICENSETERMS/updateenabled = 0/HIDECON/ACTION = Install/FEATURES = SQLEngine, Tools/INSTANCENAME = LYNCLOCAL/tcpenabled = 1/SQLSVCACCOUNT = "NT AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS = "Builtin\Administrators"/BROWSERSVCSTARTUPTYPE = "Automatic"/AGTSVCACCOUNT = "NTAUTHORITY\NetworkService"/SQLSVCSTARTUPTYPE = [自動]</span><span class="sxs-lookup"><span data-stu-id="8ae3c-310">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=LYNCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automatic</span></span>
1. <span data-ttu-id="8ae3c-311">Skype for Business Server 2015 RTM セットアップを実行します。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-311">Run Skype for Business Server 2015 RTM setup.</span></span>
2. <span data-ttu-id="8ae3c-312">上記の前提条件のセクションにある残りの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-312">Follow the remaining steps from the prerequisites section above.</span></span>

<span data-ttu-id="8ae3c-313">**オプション 3:** また、次のようにして、ローカルインストールメディアディレクトリのバイナリを手動で置き換えることもできます。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-313">**Option 3:** You may also manually replace binaries in a local installation media directory as follows:</span></span>

1. [<span data-ttu-id="8ae3c-314">Skype for Business Server の必須コンポーネントをインストールする</span><span class="sxs-lookup"><span data-stu-id="8ae3c-314">Install prerequisites for Skype for Business Server</span></span>](../../deploy/install/install-prerequisites.md)  
2. <span data-ttu-id="8ae3c-315">.NET 4.7 をインストールします。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-315">Install .NET 4.7:</span></span> 
      - <span data-ttu-id="8ae3c-316">**注:** 最初に、Skype for Business Server 2015 CU5 (6.0.9319.281) での .NET 4.7 のサポートを導入しました。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-316">**Note:** We first introduced support for .NET 4.7 in Skype for Business Server 2015 CU5 (6.0.9319.281).</span></span> <span data-ttu-id="8ae3c-317">そのため、次の手順では、主要なコンポーネントを更新してから、メインインストールの前に実行します。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-317">Therefore, in later steps below we will be updating Core Components prior to the main install.</span></span>
      - <span data-ttu-id="8ae3c-318">ダウンロード: https://www.microsoft.com/download/details.aspx?id=55167。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-318">Download: https://www.microsoft.com/download/details.aspx?id=55167.</span></span> 
      - <span data-ttu-id="8ae3c-319">リファレンス: [Skype For Business Server 2015 の展開前にインストールする必要があるソフトウェア](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span><span class="sxs-lookup"><span data-stu-id="8ae3c-319">Reference: [Software that should be installed before a Skype for Business Server 2015 deployment](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span></span>
3. <span data-ttu-id="8ae3c-320">ISO ファイル/フォルダーをコピーします。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-320">Copy ISO Files/Folders:</span></span> 
    - <span data-ttu-id="8ae3c-321">Skype for Business Server 2015 ISO が接続されている場合は、ファイルエクスプローラーで、接続されているドライブの\)ルートディレクトリ (Ex: D:) を開きます。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-321">With the Skype for Business Server 2015 ISO attached, open the root directory of the drive it is attached as (Ex: D:\) in File Explorer.</span></span>
    - <span data-ttu-id="8ae3c-322">すべてのフォルダーとファイルをローカルディスク上のフォルダー (例: C:\ skypeforbusiness2015iso) にコピーします。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-322">Copy all folders and files to a folder on a local disk (Ex: C:\SkypeForBusiness2015ISO).</span></span>
    - <span data-ttu-id="8ae3c-323">**注:** コンポーネントをインストールする前に、TLS 1.2 のサポートのためにいくつかのファイルを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-323">**Note:** Prior to installing components, some files will need to be updated for support of TLS 1.2.</span></span>
4. <span data-ttu-id="8ae3c-324">MSI/EXE パッケージを置換する:</span><span class="sxs-lookup"><span data-stu-id="8ae3c-324">Replace MSI/EXE Packages:</span></span> 
    - <span data-ttu-id="8ae3c-325">ローカルコンピューターのインストールメディアの/Setup/Amd64/フォルダー内の既存の MSI および EXE パッケージを置換します。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-325">Replace the existing MSI and EXE packages in the /Setup/amd64/ folder of the installation media on the local machine.</span></span>
    - <span data-ttu-id="8ae3c-326">SQL 2014 SP2 Express:https://www.microsoft.com/download/details.aspx?id=53167</span><span class="sxs-lookup"><span data-stu-id="8ae3c-326">SQL 2014 SP2 Express: https://www.microsoft.com/download/details.aspx?id=53167</span></span> 
        - <span data-ttu-id="8ae3c-327">ローカルコンピューター上の SQLEXPR_x64 の名前に変更し、インストールメディアの Setup/amd64/フォルダーにある既存のファイルを置き換えます。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-327">Rename to SQLEXPR_x64 on the local machine, and replace the existing file in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="8ae3c-328">SQL Native Client:https://www.microsoft.com/download/details.aspx?id=50402</span><span class="sxs-lookup"><span data-stu-id="8ae3c-328">SQL Native Client: https://www.microsoft.com/download/details.aspx?id=50402</span></span> 
        - <span data-ttu-id="8ae3c-329">**注:** 必要に応じて、この名前を sqlncli.msi に変更し、インストールメディアの Setup/amd64/フォルダーに存在する既存のファイルを置き換えます。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-329">**Note:** Rename this if necessary to sqlncli.msi, and then replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="8ae3c-330">SQL 管理オブジェクト:https://www.microsoft.com/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="8ae3c-330">SQL Management Objects: https://www.microsoft.com/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="8ae3c-331">**注:** 機能パックには、ダウンロード可能な多くのアイテムがあります。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-331">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="8ae3c-332">SharedManagementObjects をダウンロードする場合は、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-332">Select to download SharedManagementObjects.msi only.</span></span>
        - <span data-ttu-id="8ae3c-333">**注:** インストールメディアの Setup/amd64/フォルダーに存在する既存のファイルを置換します。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-333">**Note:** Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="8ae3c-334">SQL CLR の種類:https://www.microsoft.com/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="8ae3c-334">SQL CLR Types: https://www.microsoft.com/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="8ae3c-335">**注:** 機能パックには、ダウンロード可能な多くのアイテムがあります。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-335">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="8ae3c-336">CQLSysClrTypes のダウンロードのみを選択する</span><span class="sxs-lookup"><span data-stu-id="8ae3c-336">Select to download CQLSysClrTypes.msi only</span></span>
        - <span data-ttu-id="8ae3c-337">**注**: インストールメディアの Setup/amd64/フォルダーに存在する既存のファイルを置き換えます。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-337">**Note**: Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
5. <span data-ttu-id="8ae3c-338">コアコンポーネントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-338">Install Core Components:</span></span> 
    - <span data-ttu-id="8ae3c-339">インストールメディアの Setup/amd64/フォルダーから Setup.exe を実行します。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-339">Run Setup.exe from the Setup/amd64/ folder of the installation media.</span></span> <span data-ttu-id="8ae3c-340">手順に従ってコアコンポーネントをインストールする</span><span class="sxs-lookup"><span data-stu-id="8ae3c-340">Follow the instructions to install Core Components</span></span>
    - <span data-ttu-id="8ae3c-341">コアコンポーネントを閉じます。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-341">Close Core Components.</span></span>
6. <span data-ttu-id="8ae3c-342">コアコンポーネントを更新します。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-342">Update Core Components:</span></span> 
    - <span data-ttu-id="8ae3c-343">Skype for Business 更新プログラムインストーラーをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-343">Download the Skype for Business Update Installer.</span></span>
    - <span data-ttu-id="8ae3c-344">インストーラーを実行してコアコンポーネントを更新し、パフォーマンスカウンターをインストールします。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-344">Run the installer to update Core Components and install the performance counters.</span></span>
    - <span data-ttu-id="8ae3c-345">**注:** CU6HF2 のリリースの時点で、自動更新機能は現在、CU6 にのみインストールされます。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-345">**Note:** As of the release of CU6HF2, the auto-update feature currently only will install up to CU6.</span></span> <span data-ttu-id="8ae3c-346">したがって、コアコンポーネントを6.0.9319.516 に更新するには、updater を個別に実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-346">Therefore, the updater must be run separately to update Core Components to 6.0.9319.516.</span></span>
    - <span data-ttu-id="8ae3c-347">参考https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015</span><span class="sxs-lookup"><span data-stu-id="8ae3c-347">Reference: https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015</span></span>
7. <span data-ttu-id="8ae3c-348">管理ツールをインストールする (オプション):</span><span class="sxs-lookup"><span data-stu-id="8ae3c-348">Install Administrative Tools (Optional):</span></span> 
    - <span data-ttu-id="8ae3c-349">これにより、更新されたファイルを使用して、Microsoft SQL Server 2012 Native Client、SQL Server 2014 Management Objects (x64)、および Microsoft System CLR Types for SQL Server 2014 (x64) がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-349">This will install the Microsoft SQL Server 2012 Native Client, SQL Server 2014 Management Objects (x64), and Microsoft System CLR Types for SQL Server 2014 (x64) using the updated files.</span></span> <span data-ttu-id="8ae3c-350">また、Skype for Business Server 2015 トポロジビルダーとコントロールパネルは、ローカルコンピューターで利用できます。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-350">Additionally, the Skype for Business Server 2015 Topology Builder and Control Panel will be available on the local machine.</span></span>
8. <span data-ttu-id="8ae3c-351">ローカル構成ストアのインストール (手順 1):</span><span class="sxs-lookup"><span data-stu-id="8ae3c-351">Install Local Configuration Store (Step 1):</span></span> 
     - <span data-ttu-id="8ae3c-352">展開ウィザードを開き、[Skype for Business Server システムのインストールまたは更新] をクリックし、[ステップ 1: ローカル構成ストアのインストール] で [**実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-352">Open the Deployment Wizard, click Install or Update Skype for Business Server System, and click on **Run** at Step 1: Install Local Configuration Store.</span></span>
     - <span data-ttu-id="8ae3c-353">[**ローカル構成ストアのインストール**] ダイアログボックスで [**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-353">Click **Next** in the **Install Local Configuration Store** dialog box.</span></span>
     <span data-ttu-id="8ae3c-354">![[ローカル構成ストアのインストール] ダイアログボックス](../../media/local-configuration-store.png)</span><span class="sxs-lookup"><span data-stu-id="8ae3c-354">![Install Local Configuration Store dialog box](../../media/local-configuration-store.png)</span></span>
     - <span data-ttu-id="8ae3c-355">結果を確認し、タスクの状態が [完了] になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-355">Review the results, and ensure that the Task Status is Completed.</span></span> <span data-ttu-id="8ae3c-356">[**ログの表示**] をクリックして、結果のログファイルを確認します。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-356">Review the resulting log file by clicking **View Log**.</span></span>
     <span data-ttu-id="8ae3c-357">![タスクの進捗状況が完了と表示される](../../media/local-configuration-task-completed.png)</span><span class="sxs-lookup"><span data-stu-id="8ae3c-357">![Task status shows as Completed](../../media/local-configuration-task-completed.png)</span></span>
     - <span data-ttu-id="8ae3c-358">[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-358">Click **Finish**.</span></span>
9. <span data-ttu-id="8ae3c-359">Skype for Business Server コンポーネントのセットアップまたは削除 (手順 2):</span><span class="sxs-lookup"><span data-stu-id="8ae3c-359">Set up or remove Skype for Business Server Components (Step 2):</span></span>
    - <span data-ttu-id="8ae3c-360">展開ウィザードを開き、[ **skype for Business Server システムのインストールまたは更新**] をクリックし **、[手順**2: Skype for Business server コンポーネントのセットアップまたは削除] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-360">Open the Deployment Wizard, click **Install or Update Skype for Business Server System**, and click **Run** at Step 2: Set up or Remove Skype for Business Server Components</span></span>
    - <span data-ttu-id="8ae3c-361">[Skype for Business Server コンポーネントのセットアップ] ダイアログボックスで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-361">Click **Next** in the Set Up Skype for Business Server Components dialog box.</span></span>
    <span data-ttu-id="8ae3c-362">![[Skype for Business Server コンポーネントのセットアップ] ウィンドウ](../../media/set-up-skype-for-business-server-components-window.png)</span><span class="sxs-lookup"><span data-stu-id="8ae3c-362">![the Set Up Skype for Business Server Components window](../../media/set-up-skype-for-business-server-components-window.png)</span></span>
    - <span data-ttu-id="8ae3c-363">View ログを使用してログを確認し、問題なくセットアップが完了したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-363">Review the log using View Log, and validate that setup completed without issues.</span></span> 
    - <span data-ttu-id="8ae3c-364">[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-364">Click **Finish**.</span></span>
10. <span data-ttu-id="8ae3c-365">必要に応じて、追加のインストールと構成を続行します (この時点では、通常のインストール手順を再開できます)。</span><span class="sxs-lookup"><span data-stu-id="8ae3c-365">Proceed with additional installation and configuration as required (you can resume normal installation procedures at this point).</span></span>
