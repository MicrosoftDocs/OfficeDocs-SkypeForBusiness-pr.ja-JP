---
title: Skype for Business Server 2015 で TLS 1.0/1.1 を無効にする
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: '概要: お客様の環境で TLS 1.0 および1.1 を無効にするための準備と実装を行います。'
ms.openlocfilehash: f6fa608174bc22bc91512a69cc67a688b9bc7bb9
ms.sourcegitcommit: 0dba0ad1f8f00415c6437cadabed0548ce3281b1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2019
ms.locfileid: "39919311"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a><span data-ttu-id="6a5b3-103">Skype for Business Server 2015 で TLS 1.0/1.1 を無効にする</span><span class="sxs-lookup"><span data-stu-id="6a5b3-103">Disable TLS 1.0/1.1 in Skype for Business Server 2015</span></span>

<span data-ttu-id="6a5b3-104">この記事の目的は、お客様の環境で TLS 1.0 および1.1 を無効にするための準備と実装に必要なガイダンスを提供することです。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-104">The purpose of this article is to provide the necessary guidance for you to prepare for and implement disabling TLS 1.0 and 1.1 in your environments.</span></span> <span data-ttu-id="6a5b3-105">このプロセスには、さまざまな計画と準備が必要です。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-105">This process requires extensive planning and preparation.</span></span> <span data-ttu-id="6a5b3-106">組織で TLS 1.0 および1.1 を無効にする計画を立てるときは、この記事のすべての情報を慎重に確認してください。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-106">Please carefully review all of the information in this article as you make your plan to disable TLS 1.0 and 1.1 for your organization.</span></span> <span data-ttu-id="6a5b3-107">TLS 1.0/1.1 を無効にすることによって影響を受ける可能性のある外部依存関係と接続性の条件が多数あるため、十分な計画とテストを行う必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-107">Note that there are many external dependencies and connectivity conditions that could be impacted by disabling TLS 1.0/1.1, so extensive planning and testing is warranted.</span></span>

## <a name="in-this-article"></a><span data-ttu-id="6a5b3-108">この記事の内容</span><span class="sxs-lookup"><span data-stu-id="6a5b3-108">In this article</span></span>

- [<span data-ttu-id="6a5b3-109">背景と範囲</span><span class="sxs-lookup"><span data-stu-id="6a5b3-109">Background and scope</span></span>](#background)
- [<span data-ttu-id="6a5b3-110">前提条件とプロセス</span><span class="sxs-lookup"><span data-stu-id="6a5b3-110">Prerequisites and process</span></span>](#prerequisites-and-process)
- [<span data-ttu-id="6a5b3-111">高度な展開シナリオ</span><span class="sxs-lookup"><span data-stu-id="6a5b3-111">Advanced deployment scenarios</span></span>](#advanced-deployment-scenarios)

## <a name="background"></a><span data-ttu-id="6a5b3-112">背景</span><span class="sxs-lookup"><span data-stu-id="6a5b3-112">Background</span></span>

<span data-ttu-id="6a5b3-113">オンプレミスの Skype for Business Server のサポートを無効にするため 1.1 1.0 の主なドライバーは、支払いカード産業 (PCI) セキュリティ規格協議会と連邦情報処理規格の要件です。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-113">The primary drivers for providing TLS 1.0 and 1.1 disable support for Skype for Business Server On-Premises are Payment Card Industry (PCI) Security Standards Council and Federal Information Processing Standards requirements.</span></span> <span data-ttu-id="6a5b3-114">PCI の要件の詳細については、[こちら](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-114">More information for PCI requirements can be found [here](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).</span></span>  <span data-ttu-id="6a5b3-115">Microsoft は、組織がこれらの要件に従う必要があるかどうかについてのガイダンスを提供することはできません。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-115">Microsoft cannot provide guidance on whether or not your organization is required to adhere to these or other requirements.</span></span> <span data-ttu-id="6a5b3-116">使用している環境で TLS 1.0 および1.1 を無効にする必要があるかどうかを判断する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-116">You must determine if it is required for you to disable TLS 1.0 and/or 1.1 in your environments.</span></span>

<span data-ttu-id="6a5b3-117">Microsoft は、TLS に関するホワイトペーパーを[ここ](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/)で提供しています。また、この[Exchange ブログ](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)で利用できる背景の読み取りもお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-117">Microsoft has produced a white paper on TLS available [here](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/), and we also recommend the background reading available in this [Exchange blog](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/).</span></span>

## <a name="supportability-scope"></a><span data-ttu-id="6a5b3-118">サポート範囲</span><span class="sxs-lookup"><span data-stu-id="6a5b3-118">Supportability Scope</span></span>

<span data-ttu-id="6a5b3-119">*スコープ*は、サポート性の境界を意味します。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-119">*Scope* refers to supportability boundaries.</span></span> <span data-ttu-id="6a5b3-120">*完全にテストされ、サポートさ*れているということは、一覧されている製品バージョンの TLS 1.0 および1.1 の無効化を完全にサポートし、テストしていることです。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-120">*Fully tested and supported* means we fully support and have tested disabling of TLS 1.0 and 1.1 for the listed product versions.</span></span> <span data-ttu-id="6a5b3-121">*現在調査中*であることを意味します。microsoft は、これらの製品をスコープ内で TLS のサポート対象にすることを積極的に調査しています。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-121">*Currently being investigated* means just that; we are actively investigating bringing these products into scope for TLS disable support.</span></span> <span data-ttu-id="6a5b3-122">*スコープ外の*場合、これらの製品バージョンは、TLS 1.0 または1.1 の無効化をサポートしておらず、例外が報告されていても動作しません。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-122">*Out of scope* means these product versions do not support disabling TLS 1.0 or 1.1 and will not work, with noted exceptions.</span></span>

### <a name="fully-tested-and-supported-servers"></a><span data-ttu-id="6a5b3-123">完全にテストおよびサポートされたサーバー</span><span class="sxs-lookup"><span data-stu-id="6a5b3-123">Fully tested and supported servers</span></span>

- <span data-ttu-id="6a5b3-124">Skype for Business Server 2019 CU1 17.0.2046.123 (2019 年6月) 以降</span><span class="sxs-lookup"><span data-stu-id="6a5b3-124">Skype for Business Server 2019 CU1 17.0.2046.123 (June 2019) or higher</span></span>
- <span data-ttu-id="6a5b3-125">Skype for Business Server 2015 CU9 6.0.9319.548 (2019 年5月) 以上の Windows Server 2012 (KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in)または置き換えられた更新プログラム)、2012 R2、2016。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-125">Skype for Business Server 2015 CU9 6.0.9319.548 (May 2019) or higher on Windows Server 2012 (with KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseding update), 2012 R2 or 2016.</span></span>
- <span data-ttu-id="6a5b3-126">Windows Server 2008 R2、2012 (KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in)または置き換えられた更新プログラム)、または 2012 R2 を使用したインプレースアップグレードされた Skype For business SERVER 2015 CU9 6.0.9319.548 (2019 年5月) 以降。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-126">In-place Upgraded Skype for Business Server 2015, with CU9 6.0.9319.548 (May 2019) or higher on Windows Server 2008 R2, 2012 (with KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseding update), or 2012 R2.</span></span>
- <span data-ttu-id="6a5b3-127">Exchange 接続と Outlook Web App (Exchange Server 2010 SP3 RU19 以降)、[ここで](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)のガイダンス</span><span class="sxs-lookup"><span data-stu-id="6a5b3-127">Exchange Connectivity and Outlook Web App with Exchange Server 2010 SP3 RU19 or higher, guidance [here](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span></span>
- <span data-ttu-id="6a5b3-128">Skype for Business Server 2015 CU6 HF2 以上を搭載した Survivable Branch Appliance (SBA) (お使いのベンダーに、適切な更新プログラムをパッケージしており、お使いのアプライアンスで利用可能になったことを確認してください)</span><span class="sxs-lookup"><span data-stu-id="6a5b3-128">Survivable Branch Appliance (SBA) with Skype for Business Server 2015 CU6 HF2 or higher (confirm with your vendor that they packaged the appropiate updates and have been made available for your appliance)</span></span>
- <span data-ttu-id="6a5b3-129">Survivable Branch Server (SBS) と Skype for Business Server 2015 CU6 HF2 以降</span><span class="sxs-lookup"><span data-stu-id="6a5b3-129">Survivable Branch Server (SBS) with Skype for Business Server 2015 CU6 HF2 or higher</span></span>
- <span data-ttu-id="6a5b3-130">Lync Server 2013 **Edge の役割のみ**。これは、edge の役割が Windows Fabric 1.0 に依存していないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-130">Lync Server 2013 **Edge Role Only**, this is because Edge role does not have a dependency on Windows Fabric 1.0.</span></span>

### <a name="fully-tested-and-supported-clients"></a><span data-ttu-id="6a5b3-131">完全にテストおよびサポートされているクライアント</span><span class="sxs-lookup"><span data-stu-id="6a5b3-131">Fully tested and supported clients</span></span>

- <span data-ttu-id="6a5b3-132">Lync 2013 (Skype for Business) デスクトップクライアント、MSI、C2R (基本的な[15.0.5023.1000 です](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)など)</span><span class="sxs-lookup"><span data-stu-id="6a5b3-132">Lync 2013 (Skype for Business) Desktop Client, MSI and C2R, including Basic [15.0.5023.1000 or higher](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)</span></span>
- <span data-ttu-id="6a5b3-133">Skype for Business 2016 デスクトップクライアント、MSI [16.0.4678.1000 以上](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323)(Basic を含む)</span><span class="sxs-lookup"><span data-stu-id="6a5b3-133">Skype for Business 2016 Desktop Client, MSI [16.0.4678.1000 or higher](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), including Basic</span></span>
- <span data-ttu-id="6a5b3-134">Skype for Business 2016 を実行するには、 [2018 年4月](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus)の更新プログラムが必要です。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-134">Skype for Business 2016 Click to Run Require the [April 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) Updates:</span></span> 
    - <span data-ttu-id="6a5b3-135">毎月および半年のターゲット、16\.0\.9126\.2152 以上</span><span class="sxs-lookup"><span data-stu-id="6a5b3-135">Monthly and Semi-Annual Targeted, 16\.0\.9126\.2152 or higher</span></span>
    - <span data-ttu-id="6a5b3-136">半期および段階的提供チャネル、16\.0\.8431\.2242 以上</span><span class="sxs-lookup"><span data-stu-id="6a5b3-136">Semi-Annual and Deferred Channel, 16\.0\.8431\.2242 or higher</span></span>
- <span data-ttu-id="6a5b3-137">Mac 16.15 以降の Skype for Business</span><span class="sxs-lookup"><span data-stu-id="6a5b3-137">Skype for Business on Mac 16.15 or higher</span></span>
- <span data-ttu-id="6a5b3-138">Skype for Business for iOS および Android 6.19 以降</span><span class="sxs-lookup"><span data-stu-id="6a5b3-138">Skype for Business for iOS and Android 6.19 or higher</span></span>
- <span data-ttu-id="6a5b3-139">Microsoft Teams 室 (以前は Skype Room System V2 SRS V2 と呼ばれていました) 4.0.64.0 (12 月 2018) 以降</span><span class="sxs-lookup"><span data-stu-id="6a5b3-139">Microsoft Teams Rooms (previously known as Skype Room System V2 SRS V2) 4.0.64.0 (December 2018) or higher</span></span>
- <span data-ttu-id="6a5b3-140">KB4499162 に基づく Team edition 向け Surface Hub 更新プログラム (2019 年5月、OS ビルド 15063.1835) 以上</span><span class="sxs-lookup"><span data-stu-id="6a5b3-140">Surface Hub update for Team edition based on KB4499162 (May 2019, OS Build 15063.1835) or higher</span></span>
- <span data-ttu-id="6a5b3-141">Skype Web App 2015 CU6 HF2 以上 (サーバーに付属)</span><span class="sxs-lookup"><span data-stu-id="6a5b3-141">Skype Web App 2015 CU6 HF2 or higher (ships with Server)</span></span>

### <a name="currently-being-investigated"></a><span data-ttu-id="6a5b3-142">現在調査中</span><span class="sxs-lookup"><span data-stu-id="6a5b3-142">Currently being investigated</span></span>

- <span data-ttu-id="6a5b3-143">通話品質ダッシュボード (TLS 1.0 の後の新規インストール、1.1 が無効になりました、下記参照) \*</span><span class="sxs-lookup"><span data-stu-id="6a5b3-143">Call Quality Dashboard (new install after TLS 1.0, 1.1 have been disabled, see below)\*</span></span>
 
### <a name="out-of-scope"></a><span data-ttu-id="6a5b3-144">範囲外</span><span class="sxs-lookup"><span data-stu-id="6a5b3-144">Out of scope</span></span>

<span data-ttu-id="6a5b3-145">特に注記がない限り、次の製品は、TLS 1.0/1.1 のサポートを無効にすることはできません。また、TLS 1.0 および1.1 が無効になっている環境では機能しません。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-145">Except where noted, the following products are not in scope for TLS 1.0/1.1 disable support and will not function in an environment where TLS 1.0 and 1.1 have been disabled.</span></span> <span data-ttu-id="6a5b3-146">その意味: まだスコープ外のサーバーまたはクライアントを使用している場合は、Skype for Business Server のオンプレミスの展開で TLS 1.0/1.1 を無効にする必要がある場合は、これらを更新または削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-146">What this means: if you still utilize out-of-scope servers or clients, you must update or remove these if you need to disable TLS 1.0/1.1 anywhere in your Skype for Business Server on-premises deployment.</span></span>

- <span data-ttu-id="6a5b3-147">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a5b3-147">Lync Server 2013</span></span>
- <span data-ttu-id="6a5b3-148">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="6a5b3-148">Lync Server 2010</span></span>
- <span data-ttu-id="6a5b3-149">Windows Server 2008 またはそれ以降</span><span class="sxs-lookup"><span data-stu-id="6a5b3-149">Windows Server 2008 or lower</span></span>
- <span data-ttu-id="6a5b3-150">Lync for Mac 2011</span><span class="sxs-lookup"><span data-stu-id="6a5b3-150">Lync for Mac 2011</span></span>
- <span data-ttu-id="6a5b3-151">Lync 2013 for Mobile-iOS、iPad、Android、または Windows Phone</span><span class="sxs-lookup"><span data-stu-id="6a5b3-151">Lync 2013 for Mobile - iOS, iPad, Android or Windows Phone</span></span>
- <span data-ttu-id="6a5b3-152">Lync "MX" Windows ストアクライアント</span><span class="sxs-lookup"><span data-stu-id="6a5b3-152">Lync "MX" Windows Store client</span></span>
- <span data-ttu-id="6a5b3-153">Lync Room System (別名</span><span class="sxs-lookup"><span data-stu-id="6a5b3-153">Lync Room System (a.k.a.</span></span> <span data-ttu-id="6a5b3-154">SRSv1).</span><span class="sxs-lookup"><span data-stu-id="6a5b3-154">SRSv1).</span></span> <span data-ttu-id="6a5b3-155">LRS は、2018年10月9日にサポートが終了しました。 TLS 1.2 をサポートするように更新されることはありません。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-155">LRS reached end of support on October 9, 2018 and will not be updated to support TLS 1.2.</span></span>
- <span data-ttu-id="6a5b3-156">すべての Lync 2010 クライアント</span><span class="sxs-lookup"><span data-stu-id="6a5b3-156">All Lync 2010 clients</span></span>
- <span data-ttu-id="6a5b3-157">Lync Phone Edition-[ここで](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035)更新されたガイダンス。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-157">Lync Phone Edition - updated guidance [here](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).</span></span>
- <span data-ttu-id="6a5b3-158">2013ベースの Survivable Branch Appliance (SBA) または Survivable Branch Server (SBS)</span><span class="sxs-lookup"><span data-stu-id="6a5b3-158">2013 based Survivable Branch Appliance (SBA) or Survivable Branch Server (SBS)</span></span>
- <span data-ttu-id="6a5b3-159">Cloud Connector Edition (CCE)</span><span class="sxs-lookup"><span data-stu-id="6a5b3-159">Cloud Connector Edition (CCE)</span></span>
- <span data-ttu-id="6a5b3-160">Windows Phone 版 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="6a5b3-160">Skype for Business for Windows Phone</span></span>

### <a name="exceptions"></a><span data-ttu-id="6a5b3-161">例外</span><span class="sxs-lookup"><span data-stu-id="6a5b3-161">Exceptions</span></span>

#### <a name="lync-server-2013"></a><span data-ttu-id="6a5b3-162">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a5b3-162">Lync Server 2013</span></span>

<span data-ttu-id="6a5b3-163">Lync Server 2013 は、Windows ファブリックバージョン1.0 に依存しています。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-163">Lync Server 2013 takes a dependency on Windows Fabric version 1.0.</span></span>  <span data-ttu-id="6a5b3-164">Lync Server 2013 の設計フェーズでは、新しい分散アーキテクチャが採用され、レプリケーション、高可用性、フォールトトレランスを提供するために、Windows Fabric 1.0 が選ばれました。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-164">In the design phase for Lync Server 2013, Windows Fabric 1.0 was chosen for its compelling and new distributed architecture to provide replication, high availability, and fault tolerance.</span></span>  <span data-ttu-id="6a5b3-165">時間の経過と共に、Skype for Business Server と Windows Fabric のどちらも、以降のバージョンでの大幅な再設計によって、この共同アーキテクチャが大幅に改善されました。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-165">Over time, both Skype for Business Server and Windows Fabric have greatly improved this joint architecture with significant re-design in subsequent versions.</span></span>  <span data-ttu-id="6a5b3-166">現在の Skype for Business 2015 Server では、たとえば Windows Fabric 3.0 が使用されています。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-166">Current Skype for Business 2015 Server uses Windows Fabric 3.0, for example.</span></span>

<span data-ttu-id="6a5b3-167">残念ながら、Windows Fabric 1.0**は TLS 1.2 をサポートしていません。 ただし、Lync Server 2013 は、TLS 1.2 と連携するように更新され**ます。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-167">Unfortunately, Windows Fabric 1.0 **does not support TLS 1.2.  However, we will be updating Lync Server 2013 to work with TLS 1.2**.</span></span> <span data-ttu-id="6a5b3-168">これは、Lync Server 2013 の次の累積的な更新プログラムで提供されます。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-168">This will be coming in the next Cumulative Update for Lync Server 2013.</span></span>  <span data-ttu-id="6a5b3-169">Microsoft は、共同作業、移行、フェデレーション、ハイブリッドシナリオを可能にするために、TLS 1.2 サポートを提供しています。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-169">We're providing TLS 1.2 support to enable co-existence, migration, federation, and hybrid scenarios.</span></span>

<span data-ttu-id="6a5b3-170">お客様の組織が TLS 1.0 および1.1 を無効にする必要があり、現在 Lync Server 2013 を使用している場合は、計画プロセスを開始することをお勧めします。インプレースアップグレードまたはサイドバイサイド移行 (新規プール、ユーザーの移動) が Skype for Business にインストールされている可能性があります。Business Server 2015 以降。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-170">If your organization is required to disable TLS 1.0 and 1.1, and you currently use Lync Server 2013, we recommend you begin your planning process, with the possibility you may have to In-place upgrade or Side-by-Side migrate (new pools, move users) to Skype for Business Server 2015 or higher.</span></span>  <span data-ttu-id="6a5b3-171">または、Skype for Business Online への移行を迅速化したい場合があります。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-171">Or you may want to accelerate migration to Skype for Business Online.</span></span>

#### <a name="call-quality-dashboard"></a><span data-ttu-id="6a5b3-172">通話品質ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="6a5b3-172">Call Quality Dashboard</span></span>

<span data-ttu-id="6a5b3-173">オンプレミスの通話品質ダッシュボードは、現在、新しいインストール中に TLS 1.0 に依存しています (初めてオンプレミス環境にインストールするとき)。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-173">On-Premises Call Quality Dashboard currently has a dependency on TLS 1.0 during new install (first time installing into your On-Premises environments).</span></span>  <span data-ttu-id="6a5b3-174">現在、この問題を調査しており、近い将来、修正プログラムをリリースする予定です。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-174">We are currently investigating this issue and plan to release a fix in the near future.</span></span>  <span data-ttu-id="6a5b3-175">CQD のインストールを計画していて、TLS 1.0 も無効にしている場合は、最初に CQD のインストールを完了してから、TLS 1.0 無効化を続行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-175">If you are planning to install CQD and also disable TLS 1.0, we recommend that you complete CQD installation first, and then proceed with TLS 1.0 disabling.</span></span>

#### <a name="third-party-devices"></a><span data-ttu-id="6a5b3-176">サードパーティ製のデバイス</span><span class="sxs-lookup"><span data-stu-id="6a5b3-176">Third-party devices</span></span>

<span data-ttu-id="6a5b3-177">3PIP 電話、ビデオ会議、リバースプロキシ、ロードバランサーなどのサードパーティ製デバイスでは、TLS 1.2 のサポート性を検証し、必要に応じてベンダーに連絡してください。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-177">On third-party devices such as 3PIP phones, Video conferencing, Reverse Proxies and Load Balancers, be sure to validate TLS 1.2 supportability, test carefully, and contact the vendor if needed.</span></span>

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a><span data-ttu-id="6a5b3-178">エッジサーバーで TLS 1.0/1.1 を無効にするときのフェデレーションに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="6a5b3-178">Federation considerations when disabling TLS 1.0/1.1 on Edge servers</span></span>

<span data-ttu-id="6a5b3-179">エッジサーバーで TLS 1.0/1.1 を無効にすることによる影響について慎重に計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-179">You must carefully plan for and consider the impact of disabling TLS 1.0/1.1 on your Edge servers.</span></span>  <span data-ttu-id="6a5b3-180">TLS 1.0 および1.1 を無効にすると、他の組織が組織とフェデレーションできなくなることがあります。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-180">Once TLS 1.0 and 1.1 are disabled, you may find that other organizations are no longer be able to federate with your organization.</span></span>

<span data-ttu-id="6a5b3-181">エッジサーバーで TLS 1.0/1.1 を有効にしたままにして、更新プログラム (SfB 2015、Lync 2013)、または古い (2010) 外部システムとの下位互換性を維持することができます。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-181">You may opt to keep TLS 1.0/1.1 enabled on your Edge servers to maintain backward compatibility with non-patched (SfB 2015, Lync 2013) or older (2010) external systems.</span></span>

<span data-ttu-id="6a5b3-182">Microsoft は、Edge ネットワーク (またはネットワーク) が PCI standard の下にあるかどうかに関するアドバイスや推奨事項を提供することはできません。これは、個々の会社によって決定される必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-182">Microsoft cannot provide advice or recommendations on whether or not your Edge network (or any network) falls under PCI standard; that must be determined by the individual company.</span></span>

<span data-ttu-id="6a5b3-183">Skype for Business Online は現在、TLS 1.2 に対応しているため、オンラインとのハイブリッド/フェデレーションへの影響は期待されません。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-183">Skype for Business Online is capable of TLS 1.2 today, so no impact to Hybrid/Federation with Online is expected.</span></span>

<span data-ttu-id="6a5b3-184">Skype コンシューマーサービスへの PIC (パブリック IM 接続) の利用: [skype の接続](../../deploy/deploy-skype-connectivity.md)に影響を与えるために TLS 1.0/1.1 の無効化は予期していません。Microsoft PIC ゲートウェイは、既に TLS 1.2 に対応しています。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-184">PIC (Public IM Connectivity) to Skype Consumer service: We do not expect disabling TLS 1.0/1.1 to impact [Skype Connectivity](../../deploy/deploy-skype-connectivity.md); Microsoft PIC Gateways are already TLS 1.2 capable.</span></span>

## <a name="prerequisites-and-process"></a><span data-ttu-id="6a5b3-185">前提条件とプロセス</span><span class="sxs-lookup"><span data-stu-id="6a5b3-185">Prerequisites and process</span></span>

<span data-ttu-id="6a5b3-186">上記の手順を除き、TLS 1.0 および1.1 では、スコープ外のサーバーが無効になっている場合、クライアントとデバイスは適切に機能しなくなります。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-186">Except where noted above, once TLS 1.0 and 1.1 are disabled out-of-scope servers, clients and devices will longer function properly, or at all.</span></span> <span data-ttu-id="6a5b3-187">これは、Microsoft からの更新されたガイダンスを一時停止して待つ必要があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-187">This may mean you need to pause and wait for updated guidance from Microsoft.</span></span> <span data-ttu-id="6a5b3-188">すべての要件を満たし、ギャップの対処計画があることを確認したら、続行します。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-188">Once you are satisfied that you meet all requirements and have a plan to address gaps, proceed.</span></span>

<span data-ttu-id="6a5b3-189">高レベルでは、Skype for business Server 2019 を2015インストールしているときに、CU9 をインストールし、必須の更新プログラムを .NET と SQL に適用する必要があります。また、必須のレジストリキーを展開して、最終的に別の方法で作成する必要があります。OS 構成の更新 (レジストリファイルのインポートによる TLS 1.0 および1.1 の無効化) のラウンド。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-189">At a high level, while Skype for Business Server 2019 is ready for procedure at install, Skype for Business Server 2015 will require that you install CU9, applying pre-requisite updates to .NET and SQL, deploying prerequisite registry keys, and finally a separate round of OS configuration updates (i.e. disabling TLS 1.0 and 1.1 via registry file import).</span></span> <span data-ttu-id="6a5b3-190">環境内のすべてのサーバーで TLS 1.0 と1.1 を無効にする前に、Skype for Business Server 2015 CU6 HF2 を含むすべての前提条件のインストールを完了しておくことが非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-190">It is critically important that you complete installation of all prerequisites, including Skype for Business Server 2015 CU6 HF2, prior to disabling TLS 1.0 and 1.1 on any server in your environment.</span></span> <span data-ttu-id="6a5b3-191">すべての Skype for Business server (Edge の役割と SQL バックエンドを含む) には、更新プログラムが必要です。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-191">Every Skype for Business server, including Edge role and SQL Backends, requires the updates.</span></span> <span data-ttu-id="6a5b3-192">また、サポートされている (スコープ内) クライアントがすべて、必要な最小バージョンに更新されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-192">Also ensure that all supported (in-scope) clients have been updated to the required minimum versions.</span></span> <span data-ttu-id="6a5b3-193">管理ワークステーションも更新することを忘れないでください。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-193">Don’t forget to update management workstations as well.</span></span>

<span data-ttu-id="6a5b3-194">Skype for Business サーバーのアップグレードには、"インサイド out" 機能の通常の順序に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-194">We want to follow the usual order of operations of "inside out" for upgrading Skype for Business servers.</span></span> <span data-ttu-id="6a5b3-195">通常の場合と同じ方法で、ディレクタープール、常設チャット、およびペアリングされたプールを扱うことができます。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-195">Treat Director pools, Persistent chat, and Paired Pools in the same manner you normally would.</span></span> <span data-ttu-id="6a5b3-196">アップグレードの注文と方法については[、ここ](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)[で説明し](topology.md)ます。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-196">Order and methods for upgrade are covered [here](topology.md) and [here](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>

### <a name="high-level-process"></a><span data-ttu-id="6a5b3-197">高レベルプロセス</span><span class="sxs-lookup"><span data-stu-id="6a5b3-197">High-level process</span></span>

1. <span data-ttu-id="6a5b3-198">運用サーバーを構成する前に、ラボのすべての手順をテストします。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-198">Test all steps in your lab prior to configuring production servers.</span></span>
2. <span data-ttu-id="6a5b3-199">エクスポートされたレジストリのコピーをバックアップして、個々のサーバーごとに保持します。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-199">Back up and preserve a copy of exported registry on each and every individual server to be updated.</span></span> <span data-ttu-id="6a5b3-200">サーバー間でレジストリを共有することはできません。マシンベースの一意のキーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-200">You cannot share registries between servers; they contain unique machine-based keys.</span></span>
3. <span data-ttu-id="6a5b3-201">すべての Skype for Business 2015 サーバーを CU9 以降にアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-201">Upgrade all Skype for Business 2015 servers to CU9 or higher.</span></span> <span data-ttu-id="6a5b3-202">Skype for Business Server 2019 の場合は、CU1 以降にアップグレードしてください。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-202">For Skype for Business Server 2019, upgrade to CU1 or higher.</span></span>
4. <span data-ttu-id="6a5b3-203">すべての前提条件をすべてのサーバーにインストールします。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-203">Install all prerequisites to all servers.</span></span>
5. <span data-ttu-id="6a5b3-204">必須のレジストリキーを展開します。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-204">Deploy prerequisite registry keys.</span></span>
6. <span data-ttu-id="6a5b3-205">スコープ内のすべてのクライアントが更新されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-205">Ensure that all in-scope clients are updated.</span></span>
7. <span data-ttu-id="6a5b3-206">レジストリのインポートを使用して、TLS 1.0 および1.1 を無効にします。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-206">Disable TLS 1.0 and 1.1 via registry import.</span></span>
8. <span data-ttu-id="6a5b3-207">ワークロードが予期したとおりに機能していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-207">Validate that workloads are functioning as expected.</span></span>
    - <span data-ttu-id="6a5b3-208">問題が発生した場合は、トラブルシューティングと解決、または</span><span class="sxs-lookup"><span data-stu-id="6a5b3-208">If problems are encountered, troubleshoot and resolve, or</span></span>
    - <span data-ttu-id="6a5b3-209">手順2のレジストリを復元して、TLS 1.0 および1.1 を再度有効にする</span><span class="sxs-lookup"><span data-stu-id="6a5b3-209">Restore registry from step 2 to re-enable TLS 1.0 and 1.1</span></span>
9. <span data-ttu-id="6a5b3-210">TLS 1.2 のみが使用されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-210">Validate that only TLS 1.2 is being used.</span></span>

### <a name="install-prerequisites-to-all-servers"></a><span data-ttu-id="6a5b3-211">すべてのサーバーに前提条件をインストールする</span><span class="sxs-lookup"><span data-stu-id="6a5b3-211">Install prerequisites to all servers</span></span>

<span data-ttu-id="6a5b3-212">TLS 1.0 および1.1 を Skype for Business Server 2015 展開のオペレーティングシステムレベルで無効にする前に、依存関係の詳細な更新が必要です。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-212">Extensive dependency updating is required before you begin to disable TLS 1.0 and 1.1 at the operating system level in your Skype for Business Server 2015 deployments.</span></span> <span data-ttu-id="6a5b3-213">TLS 1.2 をサポートできる最小バージョンを次に示します。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-213">The following are the minimum versions that can support TLS 1.2.</span></span> <span data-ttu-id="6a5b3-214">TLS 1.0 および1.1 の無効化を開始する前に、環境内のすべての Skype for Business サーバーにあるすべての必須更新プログラムを展開します。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-214">Deploy all prerequisite updates across every Skype for Business server in your environment before you begin disabling TLS 1.0 and 1.1.</span></span>

- <span data-ttu-id="6a5b3-215">Skype for Business Server 2015 CU9 6.0.9319.548 (2019 年5月以降) 以降</span><span class="sxs-lookup"><span data-stu-id="6a5b3-215">Skype for Business Server 2015 CU9 6.0.9319.548 (May 2019) or higher</span></span>
- <span data-ttu-id="6a5b3-216">レジストリで SchUseStrongCrypto が有効になっている場合の[.Net Framework 4.7](https://www.microsoft.com/download/details.aspx?id=55167)以上 (以下に記載されています)</span><span class="sxs-lookup"><span data-stu-id="6a5b3-216">[.NET Framework 4.7](https://www.microsoft.com/download/details.aspx?id=55167) or higher with SchUseStrongCrypto enabled in the registry (provided below)</span></span>
- <span data-ttu-id="6a5b3-217">SQL は、すべての Skype for Business 2015 サーバーとバックエンドで更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-217">SQL must be updated on all Skype for Business 2015 servers and backends.</span></span> <span data-ttu-id="6a5b3-218">最初に Enterprise Edition プール SQL バックエンドを更新し、次にそれぞれの FEs を更新します。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-218">Update Enterprise Edition Pool SQL Backends first, then their respective FEs.</span></span> 
    - <span data-ttu-id="6a5b3-219">[Sql server 2014 SP1 + cu5 以降](https://support.microsoft.com/help/3130926)、またはそれ以降の sql SERVER 2012 SP2 + CU16 以上/sql SERVER [2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014)、またはそれ以降の sql server 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="6a5b3-219">[SQL Server 2014 SP1 + CU5](https://support.microsoft.com/help/3130926), or higher / SQL Server 2012 SP2 + CU16 or higher / [SQL Server 2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014), or higher / SQL Server 2014 SP2</span></span>
     - [<span data-ttu-id="6a5b3-220">Sql server Native Client for SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="6a5b3-220">SQL Server Native Client for SQL Server 2012</span></span>](https://www.microsoft.com/download/details.aspx?id=50402)
     - <span data-ttu-id="6a5b3-221">[MICROSOFT ODBC Driver 11 FOR SQL Server](https://www.microsoft.com/download/details.aspx?id=36434)(以降)</span><span class="sxs-lookup"><span data-stu-id="6a5b3-221">[Microsoft ODBC Driver 11 for SQL Server](https://www.microsoft.com/download/details.aspx?id=36434), or higher</span></span>
     - [<span data-ttu-id="6a5b3-222">SQL Server 2014 SP2 の共有管理オブジェクト</span><span class="sxs-lookup"><span data-stu-id="6a5b3-222">Shared Management Objects for SQL Server 2014 SP2</span></span>](https://www.microsoft.com/download/details.aspx?id=53164)
     - [<span data-ttu-id="6a5b3-223">SQL server 2014 SP2 の SQLSysClrTypes</span><span class="sxs-lookup"><span data-stu-id="6a5b3-223">SQLSysClrTypes for SQL server 2014 SP2</span></span>](https://www.microsoft.com/download/details.aspx?id=42295)

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a><span data-ttu-id="6a5b3-224">推奨される操作の順序で必須条件をインストールするための基本的な手順</span><span class="sxs-lookup"><span data-stu-id="6a5b3-224">Basic steps to install pre-requisites, in recommended order of operations</span></span>

1. <span data-ttu-id="6a5b3-225">Skype for Business Server CU9 の更新プログラムをすべてのサーバーにインストールします。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-225">Install the Skype for Business Server CU9 update to all servers.</span></span> 
    1. <span data-ttu-id="6a5b3-226">アップデーターを使ってコンポーネントの更新プログラムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-226">Install the update to components using the updater.</span></span>
    2. <span data-ttu-id="6a5b3-227">ドキュメントに記載されている手順に従ってデータベースを更新します。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-227">Update databases according to documented procedures.</span></span> <span data-ttu-id="6a5b3-228">Skype for Business Server 2015 の場合は、「KB [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-228">For Skype for Business Server 2015, see KB [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>
    3. <span data-ttu-id="6a5b3-229">他の変更を加える前に、展開の製品機能を検証します。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-229">Validate product functionality in the deployment prior to moving forward with any other changes.</span></span>
2. <span data-ttu-id="6a5b3-230">.NET 4.7 のオフラインインストーラーをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-230">Download .NET 4.7 Offline Installer.</span></span> 
    1. <span data-ttu-id="6a5b3-231">文献[https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)</span><span class="sxs-lookup"><span data-stu-id="6a5b3-231">Reference: [https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)</span></span>
    2. <span data-ttu-id="6a5b3-232">フロントエンドサーバーで Skype for Business Server 2015 サービスが停止していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-232">Ensure that Skype for Business Server 2015 services are stopped on the Front End server.</span></span>
    3. <span data-ttu-id="6a5b3-233">文献[https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="6a5b3-233">Reference: [https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span></span>
    4. <span data-ttu-id="6a5b3-234">Ex (標準エディション):```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="6a5b3-234">Ex (Standard Edition): ```Stop-CsWindowsService```</span></span>
    5. <span data-ttu-id="6a5b3-235">Ex (Enterprise Edition):```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="6a5b3-235">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    6. <span data-ttu-id="6a5b3-236">インストーラパッケージを実行します。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-236">Run the installer package.</span></span>
    7. <span data-ttu-id="6a5b3-237">サーバーを再起動します。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-237">Reboot the server.</span></span>
3. <span data-ttu-id="6a5b3-238">すべてのサーバーの SQL Express 2014 を更新します。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-238">Update SQL Express 2014 on all servers.</span></span> 
    1. <span data-ttu-id="6a5b3-239">文献[https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span><span class="sxs-lookup"><span data-stu-id="6a5b3-239">Reference: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span></span>
    2. <span data-ttu-id="6a5b3-240">SQL 2014 SP2 をダウンロードする</span><span class="sxs-lookup"><span data-stu-id="6a5b3-240">Download SQL 2014 SP2</span></span> 
        - <span data-ttu-id="6a5b3-241">文献[https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)</span><span class="sxs-lookup"><span data-stu-id="6a5b3-241">Reference: [https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)</span></span>
    3. <span data-ttu-id="6a5b3-242">インストールメディアをサーバー上のフォルダーにコピーする (例: C:\ 01_2014SqlSp2)</span><span class="sxs-lookup"><span data-stu-id="6a5b3-242">Copy the installation media to a folder on the server (Ex: C:\01_2014SqlSp2)</span></span>
    4. <span data-ttu-id="6a5b3-243">フロントエンドサーバーで Skype for Business Server 2015 サービスが停止していることを確認する</span><span class="sxs-lookup"><span data-stu-id="6a5b3-243">Ensure Skype for Business Server 2015 services are stopped on the Front End server</span></span> 
        - <span data-ttu-id="6a5b3-244">Ex (標準エディション):```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="6a5b3-244">Ex (Standard Edition): ```Stop-CsWindowsService```</span></span>
        - <span data-ttu-id="6a5b3-245">Ex (Enterprise Edition):```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="6a5b3-245">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    5. <span data-ttu-id="6a5b3-246">管理コマンドプロンプトを開き、インストールされているすべてのコンポーネントとインスタンスをアップグレードする</span><span class="sxs-lookup"><span data-stu-id="6a5b3-246">Open an Admin Command Prompt, and upgrade all installed components and instances</span></span> 
        - <span data-ttu-id="6a5b3-247">例: C:\ 01_2014SqlSp2 \SQLServer2014SP2-KB3171021-x64-ENU.exe/qs/IAcceptSQLServerLicenseTerms/Action = Patch/allinstances</span><span class="sxs-lookup"><span data-stu-id="6a5b3-247">Example: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action=Patch /AllInstances</span></span>
4. <span data-ttu-id="6a5b3-248">SQL Native Client を更新します。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-248">Update SQL Native Client.</span></span> 
    1. <span data-ttu-id="6a5b3-249">リファレンス: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-249">Reference: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span></span>
    2. <span data-ttu-id="6a5b3-250">ダウンロード元[https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)</span><span class="sxs-lookup"><span data-stu-id="6a5b3-250">Download from [https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)</span></span>
    3. <span data-ttu-id="6a5b3-251">フロントエンドサーバーで Skype for Business Server 2015 サービスが停止していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-251">Ensure Skype for Business Server 2015 services are stopped on the Front End server.</span></span> 
        - <span data-ttu-id="6a5b3-252">Ex (標準エディション):```Stop-CsWindowsServices```</span><span class="sxs-lookup"><span data-stu-id="6a5b3-252">Ex (Standard Edition): ```Stop-CsWindowsServices```</span></span>
        - <span data-ttu-id="6a5b3-253">Ex (Enterprise Edition):```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="6a5b3-253">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    4. <span data-ttu-id="6a5b3-254">インストールされている SQL インスタンスの実行を停止する</span><span class="sxs-lookup"><span data-stu-id="6a5b3-254">Stop the SQL instances installed from running</span></span> 
        - <span data-ttu-id="6a5b3-255">例```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="6a5b3-255">Ex: ```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```</span></span>
        - <span data-ttu-id="6a5b3-256">例```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="6a5b3-256">Ex: ```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```</span></span>
        - <span data-ttu-id="6a5b3-257">Ex (標準エディションのみ):```Get-Service 'MSSQL$RTC' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="6a5b3-257">Ex (Standard Edition Only): ```Get-Service 'MSSQL$RTC' | Stop-Service```</span></span>
    5. <span data-ttu-id="6a5b3-258">更新をインストールします。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-258">Install the update.</span></span>
5. <span data-ttu-id="6a5b3-259">SQL Server 用の ODBC ドライバー11を更新して、TLS 1.2 (KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)) のサポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-259">Update ODBC Driver 11 for SQL Server to include support for TLS 1.2 (KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)).</span></span>
    1. <span data-ttu-id="6a5b3-260">[ODBC Driver 11 FOR SQL Server (Windows) を](https://www.microsoft.com/download/confirmation.aspx?id=36434)ダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-260">Download [ODBC Driver 11 for SQL Server - Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434).</span></span>
    2. <span data-ttu-id="6a5b3-261">フロントエンドサーバーで Skype for Business Server 2015 サービスが停止していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-261">Ensure that Skype for Business Server 2015 services are stopped on the Front End server.</span></span>
        - <span data-ttu-id="6a5b3-262">例 (標準エディション):```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="6a5b3-262">Example (Standard Edition): ```Stop-CsWindowsService```</span></span>
        - <span data-ttu-id="6a5b3-263">例 (Enterprise Edition):```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="6a5b3-263">Example (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    3. <span data-ttu-id="6a5b3-264">更新をインストールします。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-264">Install the update.</span></span>
6. <span data-ttu-id="6a5b3-265">必須のレジストリキーを展開します。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-265">Deploy prerequisite registry keys.</span></span>

### <a name="pre-requisite-registry-keys"></a><span data-ttu-id="6a5b3-266">前提条件のレジストリキー</span><span class="sxs-lookup"><span data-stu-id="6a5b3-266">Pre-requisite registry keys</span></span>

<span data-ttu-id="6a5b3-267">次のテストをメモ帳にコピーして貼り付け、TLSPreReq または任意の名前を変更して、インポートします。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-267">Copy/paste the following test into Notepad and rename TLSPreReq.reg or a name of your choice, then import:</span></span>

```
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

<span data-ttu-id="6a5b3-268">Enterprise Edition プールの SQL バックエンドの場合、前提条件と TLS の無効化は、SQL または OS のすべての更新として処理する必要があります。参照先:[https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span><span class="sxs-lookup"><span data-stu-id="6a5b3-268">For SQL back ends for Enterprise Edition Pools, prerequisites and TLS disable should be treated as any SQL or OS updates would; refer to: [https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span></span>

<span data-ttu-id="6a5b3-269">必須アプリケーションと TLS を無効にする手順は両方とも組み合わせることができますが、オペレーティングシステムレベルで TLS 1.0 および1.1 を無効にする前に、すべての前提条件を適用することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-269">While both the prerequisite application and TLS disabling steps can be combined, we strongly recommend all prerequisites be applied before proceeding with disabling of TLS 1.0 and 1.1 at the operating system level.</span></span> <span data-ttu-id="6a5b3-270">ベストプラクティスのアプローチとしては、すべての前提条件を展開し、ワークロードが正常に機能していることを検証し、後で TLS 1.0/1.1 を有効にすることによって環境を準備します。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-270">The best practice approach would be to prepare the environment by deploying all prerequisites, validating that workloads all function correctly and as expected, and then proceeding with TLS 1.0/1.1 disable at a later time.</span></span>

### <a name="disable-tls-10-and-11-via-registry-import"></a><span data-ttu-id="6a5b3-271">レジストリのインポートを使用して TLS 1.0 および1.1 を無効にする</span><span class="sxs-lookup"><span data-stu-id="6a5b3-271">Disable TLS 1.0 and 1.1 via registry import</span></span>

<span data-ttu-id="6a5b3-272">次の手順に進む前に、*すべての前提条件を完了していることを確認し、Skype For business のすべてのサーバーを更新*していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-272">Before you proceed with the next steps, *make sure you have completed all prerequisites and updated Skype for Business Servers*.</span></span>

<span data-ttu-id="6a5b3-273">メモ帳のファイルに次のテキストをコピーして、TLSDisable 名前を変更し**ます。**</span><span class="sxs-lookup"><span data-stu-id="6a5b3-273">Copy the following text into a Notepad file and rename it **TLSDisable.reg**:</span></span>

```
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

<span data-ttu-id="6a5b3-274">TLS 1.0 および1.1 を無効にする各サーバーに、.reg ファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-274">Import the .reg file on each server you wish to disable TLS 1.0 and 1.1.</span></span> <span data-ttu-id="6a5b3-275">サーバーを再起動します。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-275">Reboot the server.</span></span> <span data-ttu-id="6a5b3-276">サービスがオンラインに戻ったら、次のサーバーに移動します。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-276">Once the services have come back online, move to the next server.</span></span> <span data-ttu-id="6a5b3-277">Enterprise Edition のプールのアプローチは、OS の更新に使用するのと同じです。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-277">The approach for Enterprise Edition Pools is the same you would take for any OS update.</span></span>

<span data-ttu-id="6a5b3-278">ここでは、TLS 1.0 および1.1 を無効にするだけではありません。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-278">You may have noticed we are doing more than just disabling TLS 1.0 and 1.1 here.</span></span> <span data-ttu-id="6a5b3-279">ここでは、Cipher Suite の順序付け (上記を参照) をサポートしており、一部の古い強度の暗号を無効にする方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-279">We are supporting Cipher Suite re-order (as shown above) and the disabling of some older weak ciphers.</span></span> <span data-ttu-id="6a5b3-280">これは、Skype for Business Server での SCHANNEL および Crypto API への変更を正式に正式にサポートしていることを意味しています。この変更は、現時点でサポートおよびテストされたものだけであることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-280">This is the first time we have officially supported these changes to SCHANNEL and Crypto API on Skype for Business Server, and it is important to note that these changes are the only ones we support and have tested at this time.</span></span> <span data-ttu-id="6a5b3-281">今後、追加の構成を検討することもありますが、現時点では、実装のレジストリインポートファイルを変更しないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-281">We may consider additional configurations in the future, but for now, please do not modify the registry import file in your implementation.</span></span>

### <a name="validate-that-workloads-are-functioning-as-expected"></a><span data-ttu-id="6a5b3-282">ワークロードが期待どおりに機能していることを検証する</span><span class="sxs-lookup"><span data-stu-id="6a5b3-282">Validate that workloads are functioning as expected</span></span>

<span data-ttu-id="6a5b3-283">お客様の環境で TLS 1.0 と1.1 を無効にした後は、IM & プレゼンス、P2P 通話、エンタープライズボイスなどのメインワークロードがすべて正常に機能していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-283">Once TLS 1.0 and 1.1 have been disabled in your environment, ensure that all your main workloads are functioning as expected, such as IM & Presence, P2P calls, Enterprise Voice, etc.</span></span>

<span data-ttu-id="6a5b3-284">**TLS 1.2 のみが使用されていることを確認する**</span><span class="sxs-lookup"><span data-stu-id="6a5b3-284">**Validate only TLS 1.2 is being used**</span></span>

<span data-ttu-id="6a5b3-285">セキュリティチームが Skype for Business トラフィックの新しい監査を実行して、古いプロトコル TLS 1.0 および1.1 が使用されなくなったことを確認します。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-285">Have your Security Team perform a new audit of Skype for Business traffic to ensure that the older protocols TLS 1.0 and 1.1 are no longer in use.</span></span>

<span data-ttu-id="6a5b3-286">または、Internet Explorer を使用して、TLS 1.0 と TLS 1.1 を無効にした後で、Skype for Business Server 2015 から web サービスへの TLS 接続をテストすることもできます。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-286">Alternatively, you can use Internet Explorer to test TLS connections to web services from Skype for Business Server 2015 after TLS 1.0 and TLS 1.1 have been disabled.</span></span>

1. <span data-ttu-id="6a5b3-287">Internet Explorer を起動します。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-287">Launch Internet Explorer.</span></span>
2. <span data-ttu-id="6a5b3-288">[**ツール** > ] の [**インターネットオプション**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-288">Select **Tools** > **Internet Options**.</span></span>
3. <span data-ttu-id="6a5b3-289">[**詳細設定**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-289">Select the **Advanced** tab.</span></span>
4. <span data-ttu-id="6a5b3-290">[**設定**] で、下にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-290">Under **Settings**, scroll to the bottom.</span></span>
5. <span data-ttu-id="6a5b3-291">TLS 1.0、TLS 1.1、および TLS 1.2 が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-291">Verify that TLS 1.0, TLS 1.1, and TLS 1.2 are enabled.</span></span>
6. <span data-ttu-id="6a5b3-292">SfB 2015 プールの内部 Web サービスの URL を参照します (正常に接続されている必要があります)。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-292">Browse the Internal Web Service URL of your SfB 2015 pool (should connect successfully).</span></span>
7. <span data-ttu-id="6a5b3-293">Internet Explorer に戻り、 **TLS 1.2**のみを使うオプションを無効にします。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-293">Go back into Internet Explorer and disable the option to **Use TLS 1.2** only.</span></span>
8. <span data-ttu-id="6a5b3-294">SfB 2015 プールの内部 Web サービスの URL をもう一度参照します (接続に失敗する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-294">Browse the Internal Web Service URL of your SfB 2015 pool again (should fail to connect).</span></span>

![インターネットオプション](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a><span data-ttu-id="6a5b3-296">高度な展開シナリオ</span><span class="sxs-lookup"><span data-stu-id="6a5b3-296">Advanced deployment scenarios</span></span>

<span data-ttu-id="6a5b3-297">Skype for Business Ser 2015 で TLS 1.2 をサポートするには、一部の依存関係の前提条件が必要であるため、TLS 1.0 と1.1 が無効になっているシステムでは、RTM メディアからのインストールは失敗します。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-297">Because some dependency prerequisites are required to support TLS 1.2 in Skype for Business Ser 2015, installing from RTM media will fail on any system where TLS 1.0 and 1.1 have been disabled.</span></span>

<span data-ttu-id="6a5b3-298">**お客様の環境で TLS 1.0 および1.1 が無効になった後、新しい Standard Edition サーバーまたは Enterprise Edition プールを展開します。**</span><span class="sxs-lookup"><span data-stu-id="6a5b3-298">**Deploying New Standard Edition Servers or Enterprise Edition Pools once TLS 1.0 and 1.1 have been disabled in your environment.**</span></span>

<span data-ttu-id="6a5b3-299">**オプション 1:**[Smartsetup](../../deploy/install/install-skype-for-business-server.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-299">**Option 1:** Use [SmartSetup](../../deploy/install/install-skype-for-business-server.md).</span></span> <span data-ttu-id="6a5b3-300">今後の CU で更新された SQL バイナリに対応するように SmartSetup を更新しており、今後この記事が更新されることにご注意ください。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-300">Note that we are updating SmartSetup to accommodate the updated SQL binaries in a future CU, and will update this article in the future.</span></span>

<span data-ttu-id="6a5b3-301">**オプション 2:** インストール前のローカル SQL インスタンス (RTCLOCAL と LYNCLOCAL)</span><span class="sxs-lookup"><span data-stu-id="6a5b3-301">**Option 2:** Pre-install local SQL instances (RTCLOCAL and LYNCLOCAL)</span></span>

1. <span data-ttu-id="6a5b3-302">SQL Express 2014 SP2 (SQLEXPR_x64) を、FE のローカルフォルダーにダウンロードしてコピーします。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-302">Download and copy SQL Express 2014 SP2 (SQLEXPR_x64.exe) to local folder on FE.</span></span> <span data-ttu-id="6a5b3-303">フォルダーパス <SQL_FOLDER_PATH> と言うことができます。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-303">Let’s say folder path <SQL_FOLDER_PATH>.</span></span>
2. <span data-ttu-id="6a5b3-304">PowerShell またはコマンドプロンプトを起動し、<SQL_FOLDER_PATH> に移動します。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-304">Launch PowerShell or Command Prompt and navigate to <SQL_FOLDER_PATH>.</span></span>
3. <span data-ttu-id="6a5b3-305">以下のコマンドを実行して、RTCLOCAL SQL インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-305">Create the RTCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="6a5b3-306">続行する前に SQLEXPR_x64 .exe が終了するまで待ちます。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-306">Wait until SQLEXPR_x64.exe finishes before proceeding:</span></span>

    <span data-ttu-id="6a5b3-307">SQLEXPR_x64 .exe/Q/IACCEPTSQLSERVERLICENSETERMS/updateenabled = 0/hidecon/ACTION = インストール/機能 = SQLEngine、Tools/INSTANCENAME = RTCLOCAL/tcpenabled = 1/SQLSVCACCOUNT = "NT AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS = "Builtin\Administrators"/BROWSERSVCSTARTUPTYPE = ""/AGTSVCACCOUNT = "NTAUTHORITY\NetworkService"/SQLSVCSTARTUPTYPE = "Automati" =</span><span class="sxs-lookup"><span data-stu-id="6a5b3-307">SQLEXPR_x64.exe  /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=RTCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automati</span></span>
1. <span data-ttu-id="6a5b3-308">以下のコマンドを実行して、LYNCLOCAL SQL インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-308">Create the LYNCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="6a5b3-309">次の手順に進む前に SQLEXPR_x64 .exe が終了するまで待ちます。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-309">Wait until SQLEXPR_x64.exe finishes before proceeding to the next step:</span></span>

    <span data-ttu-id="6a5b3-310">SQLEXPR_x64 .exe/Q/IACCEPTSQLSERVERLICENSETERMS/updateenabled = 0/hidecon/ACTION = インストール/機能 = SQLEngine、Tools/INSTANCENAME = LYNCLOCAL/tcpenabled = 1/SQLSVCACCOUNT = "NT AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS = "Builtin\Administrators"/BROWSERSVCSTARTUPTYPE = "自動"/AGTSVCACCOUNT = "NTAUTHORITY\NetworkService"/SQLSVCSTARTUPTYPE = "" = 自動</span><span class="sxs-lookup"><span data-stu-id="6a5b3-310">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=LYNCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automatic</span></span>
1. <span data-ttu-id="6a5b3-311">Skype for Business Server 2015 RTM セットアップを実行します。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-311">Run Skype for Business Server 2015 RTM setup.</span></span>
2. <span data-ttu-id="6a5b3-312">上記の「前提条件」セクションの残りの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-312">Follow the remaining steps from the prerequisites section above.</span></span>

<span data-ttu-id="6a5b3-313">**オプション 3:** また、次のようにして、ローカルインストールメディアディレクトリのバイナリを手動で置き換えることもできます。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-313">**Option 3:** You may also manually replace binaries in a local installation media directory as follows:</span></span>

1. [<span data-ttu-id="6a5b3-314">Skype for Business Server の前提条件をインストールする</span><span class="sxs-lookup"><span data-stu-id="6a5b3-314">Install prerequisites for Skype for Business Server</span></span>](../../deploy/install/install-prerequisites.md)  
2. <span data-ttu-id="6a5b3-315">.NET 4.7 をインストールします。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-315">Install .NET 4.7:</span></span> 
      - <span data-ttu-id="6a5b3-316">**注:** 最初に、Skype for Business Server 2015 CU5 以降 (6.0.9319.281) での .NET 4.7 のサポートについて説明しました。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-316">**Note:** We first introduced support for .NET 4.7 in Skype for Business Server 2015 CU5 (6.0.9319.281).</span></span> <span data-ttu-id="6a5b3-317">そのため、次の手順では、メインインストールの前にコアコンポーネントを更新する予定です。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-317">Therefore, in later steps below we will be updating Core Components prior to the main install.</span></span>
      - <span data-ttu-id="6a5b3-318">ダウンロード: https://www.microsoft.com/download/details.aspx?id=55167。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-318">Download: https://www.microsoft.com/download/details.aspx?id=55167.</span></span> 
      - <span data-ttu-id="6a5b3-319">リファレンス: [Skype For Business Server 2015 の展開前にインストールする必要があるソフトウェア](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span><span class="sxs-lookup"><span data-stu-id="6a5b3-319">Reference: [Software that should be installed before a Skype for Business Server 2015 deployment](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span></span>
3. <span data-ttu-id="6a5b3-320">ISO ファイル/フォルダーをコピーします。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-320">Copy ISO Files/Folders:</span></span> 
    - <span data-ttu-id="6a5b3-321">Skype for Business Server 2015 ISO が添付されている場合、ファイルが添付されているドライブのルートディレクトリ (\)例: D: エクスプローラーで) を開きます。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-321">With the Skype for Business Server 2015 ISO attached, open the root directory of the drive it is attached as (Ex: D:\) in File Explorer.</span></span>
    - <span data-ttu-id="6a5b3-322">すべてのフォルダーとファイルをローカルディスク上のフォルダー (例: c skypeforbusiness2015iso) にコピーします。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-322">Copy all folders and files to a folder on a local disk (Ex: C:\SkypeForBusiness2015ISO).</span></span>
    - <span data-ttu-id="6a5b3-323">**注:** コンポーネントをインストールする前に、TLS 1.2 をサポートするために一部のファイルを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-323">**Note:** Prior to installing components, some files will need to be updated for support of TLS 1.2.</span></span>
4. <span data-ttu-id="6a5b3-324">MSI/EXE パッケージを置き換える:</span><span class="sxs-lookup"><span data-stu-id="6a5b3-324">Replace MSI/EXE Packages:</span></span> 
    - <span data-ttu-id="6a5b3-325">ローカルコンピューター上のインストールメディアの/Setup/Amd64/フォルダーにある既存の MSI パッケージと EXE パッケージを置き換えます。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-325">Replace the existing MSI and EXE packages in the /Setup/amd64/ folder of the installation media on the local machine.</span></span>
    - <span data-ttu-id="6a5b3-326">SQL 2014 SP2 Express:https://www.microsoft.com/en-us/download/details.aspx?id=53167</span><span class="sxs-lookup"><span data-stu-id="6a5b3-326">SQL 2014 SP2 Express: https://www.microsoft.com/en-us/download/details.aspx?id=53167</span></span> 
        - <span data-ttu-id="6a5b3-327">ローカルコンピューター上の SQLEXPR_x64 に名前を変更し、インストールメディアの Setup/amd64/フォルダーで既存のファイルを置き換えます。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-327">Rename to SQLEXPR_x64 on the local machine, and replace the existing file in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="6a5b3-328">SQL Native Client:https://www.microsoft.com/en-us/download/details.aspx?id=50402</span><span class="sxs-lookup"><span data-stu-id="6a5b3-328">SQL Native Client: https://www.microsoft.com/en-us/download/details.aspx?id=50402</span></span> 
        - <span data-ttu-id="6a5b3-329">**注:** 必要に応じて、sqlncli に名前を変更して、インストールメディアの Setup/amd64/フォルダーに存在する既存のファイルを置き換えます。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-329">**Note:** Rename this if necessary to sqlncli.msi, and then replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="6a5b3-330">SQL 管理オブジェクト:https://www.microsoft.com/en-us/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="6a5b3-330">SQL Management Objects: https://www.microsoft.com/en-us/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="6a5b3-331">**注:** 機能パックには、ダウンロードできる多くのアイテムが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-331">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="6a5b3-332">SharedManagementObjects をダウンロードする場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-332">Select to download SharedManagementObjects.msi only.</span></span>
        - <span data-ttu-id="6a5b3-333">**注:** インストールメディアの Setup/amd64/フォルダーに存在する既存のファイルを置き換えます。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-333">**Note:** Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="6a5b3-334">SQL CLR 型:https://www.microsoft.com/en-us/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="6a5b3-334">SQL CLR Types: https://www.microsoft.com/en-us/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="6a5b3-335">**注:** 機能パックには、ダウンロードできる多くのアイテムが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-335">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="6a5b3-336">CQLSysClrTypes をダウンロードする場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-336">Select to download CQLSysClrTypes.msi only</span></span>
        - <span data-ttu-id="6a5b3-337">**注**: インストールメディアの Setup/amd64/フォルダーに存在する既存のファイルを置き換えます。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-337">**Note**: Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
5. <span data-ttu-id="6a5b3-338">コアコンポーネントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-338">Install Core Components:</span></span> 
    - <span data-ttu-id="6a5b3-339">インストールメディアの Setup/amd64/フォルダーから Setup.exe を実行します。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-339">Run Setup.exe from the Setup/amd64/ folder of the installation media.</span></span> <span data-ttu-id="6a5b3-340">指示に従ってコアコンポーネントをインストールする</span><span class="sxs-lookup"><span data-stu-id="6a5b3-340">Follow the instructions to install Core Components</span></span>
    - <span data-ttu-id="6a5b3-341">コアコンポーネントを閉じます。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-341">Close Core Components.</span></span>
6. <span data-ttu-id="6a5b3-342">主要コンポーネントの更新:</span><span class="sxs-lookup"><span data-stu-id="6a5b3-342">Update Core Components:</span></span> 
    - <span data-ttu-id="6a5b3-343">Skype for Business 更新プログラムインストーラーをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-343">Download the Skype for Business Update Installer.</span></span>
    - <span data-ttu-id="6a5b3-344">インストーラーを実行してコアコンポーネントを更新し、パフォーマンスカウンターをインストールします。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-344">Run the installer to update Core Components and install the performance counters.</span></span>
    - <span data-ttu-id="6a5b3-345">**注:** CU6HF2 のリリース時点では、現時点で自動更新機能をインストールできるのは、CU6 までです。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-345">**Note:** As of the release of CU6HF2, the auto-update feature currently only will install up to CU6.</span></span> <span data-ttu-id="6a5b3-346">そのため、アップデーターは、コアコンポーネントを6.0.9319.516 に更新するために個別に実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-346">Therefore, the updater must be run separately to update Core Components to 6.0.9319.516.</span></span>
    - <span data-ttu-id="6a5b3-347">文献https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015</span><span class="sxs-lookup"><span data-stu-id="6a5b3-347">Reference: https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015</span></span>
7. <span data-ttu-id="6a5b3-348">管理ツールをインストールする (オプション):</span><span class="sxs-lookup"><span data-stu-id="6a5b3-348">Install Administrative Tools (Optional):</span></span> 
    - <span data-ttu-id="6a5b3-349">この操作を行うと、更新されたファイルを使用して、Microsoft SQL Server 2012 Native Client、SQL Server 2014 Management Objects (x64)、および Microsoft System CLR の各種類の SQL Server 2014 (x64) がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-349">This will install the Microsoft SQL Server 2012 Native Client, SQL Server 2014 Management Objects (x64), and Microsoft System CLR Types for SQL Server 2014 (x64) using the updated files.</span></span> <span data-ttu-id="6a5b3-350">さらに、Skype for Business Server 2015 のトポロジビルダーとコントロールパネルは、ローカルコンピューターでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-350">Additionally, the Skype for Business Server 2015 Topology Builder and Control Panel will be available on the local machine.</span></span>
8. <span data-ttu-id="6a5b3-351">ローカル構成ストア (手順 1) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-351">Install Local Configuration Store (Step 1):</span></span> 
     - <span data-ttu-id="6a5b3-352">展開ウィザードを開き、[Skype for Business Server システムのインストールまたは更新] をクリックし、手順1で [**実行**] をクリックします。ローカル構成ストアをインストールします。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-352">Open the Deployment Wizard, click Install or Update Skype for Business Server System, and click on **Run** at Step 1: Install Local Configuration Store.</span></span>
     - <span data-ttu-id="6a5b3-353">[**ローカル構成ストアのインストール**] ダイアログボックスで [**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-353">Click **Next** in the **Install Local Configuration Store** dialog box.</span></span>
     <span data-ttu-id="6a5b3-354">![[ローカル構成ストアのインストール] ダイアログボックス](../../media/local-configuration-store.png)</span><span class="sxs-lookup"><span data-stu-id="6a5b3-354">![Install Local Configuration Store dialog box](../../media/local-configuration-store.png)</span></span>
     - <span data-ttu-id="6a5b3-355">結果を確認して、タスクの進捗状況が完了していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-355">Review the results, and ensure that the Task Status is Completed.</span></span> <span data-ttu-id="6a5b3-356">[**ログの表示**] をクリックして、結果のログファイルを確認します。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-356">Review the resulting log file by clicking **View Log**.</span></span>
     <span data-ttu-id="6a5b3-357">![タスクの状態が完了として表示される](../../media/local-configuration-task-completed.png)</span><span class="sxs-lookup"><span data-stu-id="6a5b3-357">![Task status shows as Completed](../../media/local-configuration-task-completed.png)</span></span>
     - <span data-ttu-id="6a5b3-358">[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-358">Click **Finish**.</span></span>
9. <span data-ttu-id="6a5b3-359">Skype for Business Server コンポーネントのセットアップまたは削除 (手順 2):</span><span class="sxs-lookup"><span data-stu-id="6a5b3-359">Set up or remove Skype for Business Server Components (Step 2):</span></span>
    - <span data-ttu-id="6a5b3-360">展開ウィザードを開き、[ **skype For Business Server System をインストールまたは更新**する] をクリックして、手順 2: Skype For Business server**コンポーネントのセットアップ**または削除を行う</span><span class="sxs-lookup"><span data-stu-id="6a5b3-360">Open the Deployment Wizard, click **Install or Update Skype for Business Server System**, and click **Run** at Step 2: Set up or Remove Skype for Business Server Components</span></span>
    - <span data-ttu-id="6a5b3-361">[Skype for Business Server コンポーネントのセットアップ] ダイアログボックスで [**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-361">Click **Next** in the Set Up Skype for Business Server Components dialog box.</span></span>
    <span data-ttu-id="6a5b3-362">![[Skype for Business Server コンポーネントのセットアップ] ウィンドウ](../../media/set-up-skype-for-business-server-components-window.png)</span><span class="sxs-lookup"><span data-stu-id="6a5b3-362">![the Set Up Skype for Business Server Components window](../../media/set-up-skype-for-business-server-components-window.png)</span></span>
    - <span data-ttu-id="6a5b3-363">ビューログを使用してログを確認し、問題なくセットアップが完了したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-363">Review the log using View Log, and validate that setup completed without issues.</span></span> 
    - <span data-ttu-id="6a5b3-364">[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-364">Click **Finish**.</span></span>
10. <span data-ttu-id="6a5b3-365">必要に応じて、追加のインストールと構成を続行します (この時点で通常のインストール手順を再開できます)。</span><span class="sxs-lookup"><span data-stu-id="6a5b3-365">Proceed with additional installation and configuration as required (you can resume normal installation procedures at this point).</span></span>
