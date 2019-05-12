---
title: ビジネス サーバー 2015 の Skype では、TLS 1.0 または 1.1 を無効にします。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: '概要: を準備してお客様の環境で TLS 1.0 および 1.1 を無効にするを実装します。'
ms.openlocfilehash: 570d691463f117c2c81c1191d1679db9f70e96b4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33911904"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a><span data-ttu-id="357d4-103">ビジネス サーバー 2015 の Skype では、TLS 1.0 または 1.1 を無効にします。</span><span class="sxs-lookup"><span data-stu-id="357d4-103">Disable TLS 1.0/1.1 in Skype for Business Server 2015</span></span>

<span data-ttu-id="357d4-104">この資料の目的は、準備し、TLS 1.0 および 1.1 を無効にすることをお客様の環境で実装するために必要なガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="357d4-104">The purpose of this article is to provide the necessary guidance for you to prepare for and implement disabling TLS 1.0 and 1.1 in your environments.</span></span> <span data-ttu-id="357d4-105">このプロセスには、綿密な計画と準備が必要です。</span><span class="sxs-lookup"><span data-stu-id="357d4-105">This process requires extensive planning and preparation.</span></span> <span data-ttu-id="357d4-106">確認してください慎重にこの資料の情報をすべて TLS 1.0 と 1.1 の組織を無効にするための計画を行うとします。</span><span class="sxs-lookup"><span data-stu-id="357d4-106">Please carefully review all of the information in this article as you make your plan to disable TLS 1.0 and 1.1 for your organization.</span></span> <span data-ttu-id="357d4-107">多くの外部の依存関係および TLS 1.0 または 1.1 を無効にすることによって影響を受ける可能性があります接続条件があるため広範な計画とテストが保証されていることに注意します。</span><span class="sxs-lookup"><span data-stu-id="357d4-107">Note that there are many external dependencies and connectivity conditions that could be impacted by disabling TLS 1.0/1.1, so extensive planning and testing is warranted.</span></span>

## <a name="in-this-article"></a><span data-ttu-id="357d4-108">この資料に記載されて</span><span class="sxs-lookup"><span data-stu-id="357d4-108">In this article</span></span>

- [<span data-ttu-id="357d4-109">背景とスコープ</span><span class="sxs-lookup"><span data-stu-id="357d4-109">Background and scope</span></span>](#background)
- [<span data-ttu-id="357d4-110">前提条件とプロセス</span><span class="sxs-lookup"><span data-stu-id="357d4-110">Prerequisites and process</span></span>](#prerequisites-and-process)
- [<span data-ttu-id="357d4-111">高度な展開シナリオ</span><span class="sxs-lookup"><span data-stu-id="357d4-111">Advanced deployment scenarios</span></span>](#advanced-deployment-scenarios)

## <a name="background"></a><span data-ttu-id="357d4-112">背景</span><span class="sxs-lookup"><span data-stu-id="357d4-112">Background</span></span>

<span data-ttu-id="357d4-113">TLS 1.0 と 1.1 を無効にするためのサポート Skype のビジネス サーバー設置型を提供する主な構成要素は、支払いカード業界 (PCI セキュリティ スタンダード カウンシルと連邦情報処理標準の要件です。</span><span class="sxs-lookup"><span data-stu-id="357d4-113">The primary drivers for providing TLS 1.0 and 1.1 disable support for Skype for Business Server On-Premises are Payment Card Industry (PCI) Security Standards Council and Federal Information Processing Standards requirements.</span></span> <span data-ttu-id="357d4-114">PCI 要件の詳細についてを参照して[ここで](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls)。</span><span class="sxs-lookup"><span data-stu-id="357d4-114">More information for PCI requirements can be found [here](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).</span></span>  <span data-ttu-id="357d4-115">マイクロソフトは、これらやその他の要件に準拠する組織が必要かどうかに関するガイダンスを提供することはできません。</span><span class="sxs-lookup"><span data-stu-id="357d4-115">Microsoft cannot provide guidance on whether or not your organization is required to adhere to these or other requirements.</span></span> <span data-ttu-id="357d4-116">TLS 1.0 および 1.1 の環境で無効にするために必要なかどうかを決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="357d4-116">You must determine if it is required for you to disable TLS 1.0 and/or 1.1 in your environments.</span></span>

<span data-ttu-id="357d4-117">マイクロソフトが TLS 利用可能な[ここでは](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/)、上のホワイト ペーパーを作成し、読み取り、この[ブログの Exchange](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)で使用可能な背景もお勧めします。</span><span class="sxs-lookup"><span data-stu-id="357d4-117">Microsoft has produced a white paper on TLS available [here](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/), and we also recommend the background reading available in this [Exchange blog](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/).</span></span>

## <a name="supportability-scope"></a><span data-ttu-id="357d4-118">サポート範囲</span><span class="sxs-lookup"><span data-stu-id="357d4-118">Supportability Scope</span></span>

<span data-ttu-id="357d4-119">*スコープ*は、サポート範囲を参照します。</span><span class="sxs-lookup"><span data-stu-id="357d4-119">*Scope* refers to supportability boundaries.</span></span> <span data-ttu-id="357d4-120">Skype のビジネス サーバー設置型の場合は、*スコープ内で*完全にサポートされ、TLS 1.0 と表示されている製品のバージョン 1.1 を無効にするテストを意味します。</span><span class="sxs-lookup"><span data-stu-id="357d4-120">For Skype for Business Server On-Premises, *in scope* means we fully support and have tested disabling of TLS 1.0 and 1.1 for the listed product versions.</span></span> <span data-ttu-id="357d4-121">*現在調査中*というだけです。TLS がサポートを無効にするは、スコープ内にこれらの製品を導入を積極的に調査します。</span><span class="sxs-lookup"><span data-stu-id="357d4-121">*Currently being investigated* means just that; we are actively investigating bringing these products into scope for TLS disable support.</span></span> <span data-ttu-id="357d4-122">*スコープの外*には、これらの製品のバージョンが無効にすると、TLS 1.0 または 1.1 をサポートしていないとは、以下の例外を意味します。</span><span class="sxs-lookup"><span data-stu-id="357d4-122">*Out of scope* means these product versions do not support disabling TLS 1.0 or 1.1 and will not work, with noted exceptions.</span></span>

### <a name="fully-tested-and-supported-servers"></a><span data-ttu-id="357d4-123">完全にテストされ、サポートされているサーバー</span><span class="sxs-lookup"><span data-stu-id="357d4-123">Fully tested and supported servers</span></span>

- <span data-ttu-id="357d4-124">Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="357d4-124">Skype for Business Server 2019</span></span>
- <span data-ttu-id="357d4-125">Skype ビジネス サーバー 2015 CU6 HF2 ([2018年 3 月更新](https://support.microsoft.com/en-us/help/4086059/march-2018-cumulative-update-6-0-9319-516-for-skype-for-business)) 6.0.9319.516 のではそれ以上とします。</span><span class="sxs-lookup"><span data-stu-id="357d4-125">Skype for Business Server 2015 CU6 HF2 6.0.9319.516 ([March 2018 update](https://support.microsoft.com/en-us/help/4086059/march-2018-cumulative-update-6-0-9319-516-for-skype-for-business)) and higher on:</span></span> 
    - <span data-ttu-id="357d4-126">(KB 3140245 に優先する更新プログラム) の Windows Server 2012、2012 R2 または 2016</span><span class="sxs-lookup"><span data-stu-id="357d4-126">Windows Server 2012 (with KB 3140245 or superseding update), 2012 R2 or 2016</span></span>
- <span data-ttu-id="357d4-127">インプレース アップグレードの Skype ビジネス サーバー 2015、CU6 HF2 とではそれ以上の</span><span class="sxs-lookup"><span data-stu-id="357d4-127">In-place Upgraded Skype for Business Server 2015, with CU6 HF2 and higher on</span></span> 
    - <span data-ttu-id="357d4-128">Windows Server 2008 R2、2012 で KB [3140245](https://support.microsoft.com/en-us/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in)または優先する更新プログラムを使用)、または 2012 R2</span><span class="sxs-lookup"><span data-stu-id="357d4-128">Windows Server 2008 R2, 2012 (with KB [3140245](https://support.microsoft.com/en-us/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseding update), or 2012 R2</span></span>
- <span data-ttu-id="357d4-129">Exchange の接続と Outlook Web App で Exchange Server 2010 の SP3 RU19 以降のガイダンス[は、ここ](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span><span class="sxs-lookup"><span data-stu-id="357d4-129">Exchange Connectivity and Outlook Web App with Exchange Server 2010 SP3 RU19 or higher, guidance [here](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span></span>
- <span data-ttu-id="357d4-130">Skype サーバー 2015 CU6 HF2 のビジネスまたはそれ以上でリカバリ性に優れたブランチ アプライアンス (SBA) (確認の製造元に問い合わせて、適切な更新プログラムをパッケージ化し、アプライアンスで利用できる必要になった)</span><span class="sxs-lookup"><span data-stu-id="357d4-130">Survivable Branch Appliance (SBA) with Skype for Business Server 2015 CU6 HF2 or higher (confirm with your vendor that they packaged the appropiate updates and have been made available for your appliance)</span></span>
- <span data-ttu-id="357d4-131">Skype サーバー 2015 CU6 HF2 のビジネスまたはそれ以上でリカバリ性に優れたブランチ サーバー (SBS)</span><span class="sxs-lookup"><span data-stu-id="357d4-131">Survivable Branch Server (SBS) with Skype for Business Server 2015 CU6 HF2 or higher</span></span>
- <span data-ttu-id="357d4-132">Lync Server 2013**エッジ ロールのみ**、これはエッジの役割では、ファブリックの 1.0 を Windows には、依存関係はありません。</span><span class="sxs-lookup"><span data-stu-id="357d4-132">Lync Server 2013 **Edge Role Only**, this is because Edge role does not have a dependency on Windows Fabric 1.0.</span></span>


### <a name="fully-tested-and-supported-clients"></a><span data-ttu-id="357d4-133">完全にテストされ、サポートされているクライアント</span><span class="sxs-lookup"><span data-stu-id="357d4-133">Fully tested and supported clients</span></span>

- <span data-ttu-id="357d4-134">Lync 2013 (ビジネス用の Skype) デスクトップ クライアント、MSI および Basic を含む、C2R [15.0.5023.1000 以上](https://support.microsoft.com/en-us/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)</span><span class="sxs-lookup"><span data-stu-id="357d4-134">Lync 2013 (Skype for Business) Desktop Client, MSI and C2R, including Basic [15.0.5023.1000 and higher](https://support.microsoft.com/en-us/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)</span></span>
- <span data-ttu-id="357d4-135">Skype ビジネス 2016年のデスクトップ クライアント、MSI の[16.0.4678.1000 以上](https://support.microsoft.com/en-us/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323)、Basic を含む</span><span class="sxs-lookup"><span data-stu-id="357d4-135">Skype for Business 2016 Desktop Client, MSI [16.0.4678.1000 and higher](https://support.microsoft.com/en-us/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), including Basic</span></span>
- <span data-ttu-id="357d4-136">Skype ビジネス 2016年] をクリックしますを実行するには、 [2018年 4 月](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus)の更新が必要です。</span><span class="sxs-lookup"><span data-stu-id="357d4-136">Skype for Business 2016 Click to Run Require the [April 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) Updates:</span></span> 
    - <span data-ttu-id="357d4-137">毎月および対象とする半年、16\.0\.9126\.2152 と高い</span><span class="sxs-lookup"><span data-stu-id="357d4-137">Monthly and Semi-Annual Targeted, 16\.0\.9126\.2152 and higher</span></span>
    - <span data-ttu-id="357d4-138">半年と延期チャネル、16\.0\.8431\.2242 と高い</span><span class="sxs-lookup"><span data-stu-id="357d4-138">Semi-Annual and Deferred Channel, 16\.0\.8431\.2242 and higher</span></span>
- <span data-ttu-id="357d4-139">Mac 16.15 とそれ以上のビジネスのための Skype</span><span class="sxs-lookup"><span data-stu-id="357d4-139">Skype for Business on Mac 16.15 and higher</span></span>
- <span data-ttu-id="357d4-140">IOS および Android 6.19 のビジネスおよび高い Skype</span><span class="sxs-lookup"><span data-stu-id="357d4-140">Skype for Business for iOS and Android 6.19 and higher</span></span>
- <span data-ttu-id="357d4-141">Skype Web App 2015 CU6 HF2 と高い (サーバーが付属)</span><span class="sxs-lookup"><span data-stu-id="357d4-141">Skype Web App 2015 CU6 HF2 and higher (ships with Server)</span></span>

### <a name="currently-being-investigated"></a><span data-ttu-id="357d4-142">現在調査中</span><span class="sxs-lookup"><span data-stu-id="357d4-142">Currently being investigated</span></span>

#### <a name="devices"></a><span data-ttu-id="357d4-143">デバイス</span><span class="sxs-lookup"><span data-stu-id="357d4-143">Devices</span></span>

- <span data-ttu-id="357d4-144">Lync ルーム システム (別名</span><span class="sxs-lookup"><span data-stu-id="357d4-144">Lync Room System (a.k.a.</span></span> <span data-ttu-id="357d4-145">SRSv1)</span><span class="sxs-lookup"><span data-stu-id="357d4-145">SRSv1)</span></span>
- <span data-ttu-id="357d4-146">Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="357d4-146">Microsoft Teams Rooms</span></span>
- <span data-ttu-id="357d4-147">Surface Hub</span><span class="sxs-lookup"><span data-stu-id="357d4-147">Surface Hub</span></span>
- <span data-ttu-id="357d4-148">2015 ベースのリカバリ性に優れたブランチ アプライアンス (SBA) またはリカバリ性に優れたブランチ サーバー (SBS)</span><span class="sxs-lookup"><span data-stu-id="357d4-148">2015 based Survivable Branch Appliance (SBA) or Survivable Branch Server (SBS)</span></span>

#### <a name="other"></a><span data-ttu-id="357d4-149">その他</span><span class="sxs-lookup"><span data-stu-id="357d4-149">Other</span></span>

- <span data-ttu-id="357d4-150">品質のダッシュ ボードを呼び出す (TLS 1.0、1.1 以降後の新しいインストールを無効にされている、以下を参照してください) \*</span><span class="sxs-lookup"><span data-stu-id="357d4-150">Call Quality Dashboard (new install after TLS 1.0, 1.1 have been disabled, see below)\*</span></span>
 
### <a name="out-of-scope"></a><span data-ttu-id="357d4-151">スコープ外</span><span class="sxs-lookup"><span data-stu-id="357d4-151">Out of scope</span></span>

<span data-ttu-id="357d4-152">を除きは、次の製品は、TLS 1.0 または 1.1 を無効にするサポートの対象ではないと、TLS 1.0 および 1.1 がされて無効になっている環境では動作しません。</span><span class="sxs-lookup"><span data-stu-id="357d4-152">Except where noted, the following products are not in scope for TLS 1.0/1.1 disable support and will not function in an environment where TLS 1.0 and 1.1 have been disabled.</span></span>  <span data-ttu-id="357d4-153">これが何を意味します。 範囲外のサーバーまたはクライアントを引き続き利用する場合を更新またはビジネス サーバー設置型展開のため、TLS 1.0 または 1.1、Skype で任意の場所を無効にする必要がある場合は、これらを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="357d4-153">What this means: if you still utilize out-of-scope servers or clients, you must update or remove these if you need to disable TLS 1.0/1.1 anywhere in your Skype for Business Server on-premises deployment.</span></span>

- <span data-ttu-id="357d4-154">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="357d4-154">Lync Server 2013</span></span>
- <span data-ttu-id="357d4-155">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="357d4-155">Lync Server 2010</span></span>
- <span data-ttu-id="357d4-156">2008 と下の Windows サーバー</span><span class="sxs-lookup"><span data-stu-id="357d4-156">Windows Server 2008 and lower</span></span>
- <span data-ttu-id="357d4-157">Lync for Mac 2011</span><span class="sxs-lookup"><span data-stu-id="357d4-157">Lync for Mac 2011</span></span>
- <span data-ttu-id="357d4-158">モバイルの iOS、Android や Windows Phone、iPad の Lync 2013</span><span class="sxs-lookup"><span data-stu-id="357d4-158">Lync 2013 for Mobile - iOS, iPad, Android or Windows Phone</span></span>
- <span data-ttu-id="357d4-159">"MX"Windows ストアの Lync クライアント</span><span class="sxs-lookup"><span data-stu-id="357d4-159">Lync "MX" Windows Store client</span></span>
- <span data-ttu-id="357d4-160">すべての Lync 2010 クライアント</span><span class="sxs-lookup"><span data-stu-id="357d4-160">All Lync 2010 clients</span></span>
- <span data-ttu-id="357d4-161">Lync の電話のエディション - 更新されたガイド[は、ここ](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035)です。</span><span class="sxs-lookup"><span data-stu-id="357d4-161">Lync Phone Edition - updated guidance [here](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).</span></span>
- <span data-ttu-id="357d4-162">2013 ベースのリカバリ性に優れたブランチ アプライアンス (SBA) またはリカバリ性に優れたブランチ サーバー (SBS)</span><span class="sxs-lookup"><span data-stu-id="357d4-162">2013 based Survivable Branch Appliance (SBA) or Survivable Branch Server (SBS)</span></span>
- <span data-ttu-id="357d4-163">クラウド コネクタ エディション (CCE)</span><span class="sxs-lookup"><span data-stu-id="357d4-163">Cloud Connector Edition (CCE)</span></span>
- <span data-ttu-id="357d4-164">Windows Phone 版 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="357d4-164">Skype for Business for Windows Phone</span></span>

### <a name="exceptions"></a><span data-ttu-id="357d4-165">例外</span><span class="sxs-lookup"><span data-stu-id="357d4-165">Exceptions</span></span>

#### <a name="lync-server-2013"></a><span data-ttu-id="357d4-166">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="357d4-166">Lync Server 2013</span></span>

<span data-ttu-id="357d4-167">Lync Server 2013 では、Windows ファブリック 1.0 のバージョンの依存関係がかかります。</span><span class="sxs-lookup"><span data-stu-id="357d4-167">Lync Server 2013 takes a dependency on Windows Fabric version 1.0.</span></span>  <span data-ttu-id="357d4-168">Lync Server 2013 のデザインの段階で、レプリケーション、高可用性、およびフォールト トレランスを提供する説得力のある新しい分散アーキテクチャのファブリックの 1.0 を Windows が選択されました。</span><span class="sxs-lookup"><span data-stu-id="357d4-168">In the design phase for Lync Server 2013, Windows Fabric 1.0 was chosen for its compelling and new distributed architecture to provide replication, high availability, and fault tolerance.</span></span>  <span data-ttu-id="357d4-169">時間の経過とともにビジネス サーバーと Windows のファブリックの両方の Skype がこの共同のアーキテクチャの大幅な再設計以降のバージョンでは大幅に向上します。</span><span class="sxs-lookup"><span data-stu-id="357d4-169">Over time, both Skype for Business Server and Windows Fabric have greatly improved this joint architecture with significant re-design in subsequent versions.</span></span>  <span data-ttu-id="357d4-170">ビジネス 2015年のサーバーの現在の Skype では、たとえば Windows ファブリック 3.0 を使用します。</span><span class="sxs-lookup"><span data-stu-id="357d4-170">Current Skype for Business 2015 Server uses Windows Fabric 3.0, for example.</span></span>

<span data-ttu-id="357d4-171">残念ながら、Windows ファブリック 1.0**は TLS 1.2 をサポートしていません。 TLS 1.2 を使用するのには、Lync Server 2013 の更新は、** です。</span><span class="sxs-lookup"><span data-stu-id="357d4-171">Unfortunately, Windows Fabric 1.0 **does not support TLS 1.2.  However, we will be updating Lync Server 2013 to work with TLS 1.2**.</span></span> <span data-ttu-id="357d4-172">これについては、Lync Server 2013 の次の累積的な更新プログラムで出勤します。</span><span class="sxs-lookup"><span data-stu-id="357d4-172">This will be coming in the next Cumulative Update for Lync Server 2013.</span></span>  <span data-ttu-id="357d4-173">共存、移行、フェデレーション、およびハイブリッドのシナリオを有効にするのには TLS 1.2 のサポートを提供しています。</span><span class="sxs-lookup"><span data-stu-id="357d4-173">We're providing TLS 1.2 support to enable co-existence, migration, federation, and hybrid scenarios.</span></span>

<span data-ttu-id="357d4-174">TLS 1.0 および 1.1 を無効にするのには、組織が必要な場合は、現在、Lync Server 2013 を使用することをお勧め計画プロセスを開始する、可能性にインプレース アップグレードする必要がありますまたはサイド バイ サイド移行 (新しいプール、ユーザーの移動) の Skype2015 またはそれ以上のビジネスのサーバーです。</span><span class="sxs-lookup"><span data-stu-id="357d4-174">If your organization is required to disable TLS 1.0 and 1.1, and you currently use Lync Server 2013, we recommend you begin your planning process, with the possibility you may have to In-place upgrade or Side-by-Side migrate (new pools, move users) to Skype for Business Server 2015 or higher.</span></span>  <span data-ttu-id="357d4-175">または、オンライン ビジネスの Skype への移行を促進することができます。</span><span class="sxs-lookup"><span data-stu-id="357d4-175">Or you may want to accelerate migration to Skype for Business Online.</span></span>

#### <a name="call-quality-dashboard"></a><span data-ttu-id="357d4-176">通話品質ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="357d4-176">Call Quality Dashboard</span></span>

<span data-ttu-id="357d4-177">設置呼び出し品質ダッシュ ボード現在に依存している TLS 1.0 (最初に、オンプレミス環境にインストールする) の新規インストール中にします。</span><span class="sxs-lookup"><span data-stu-id="357d4-177">On-Premises Call Quality Dashboard currently has a dependency on TLS 1.0 during new install (first time installing into your On-Premises environments).</span></span>  <span data-ttu-id="357d4-178">この問題は現在調査中し、近い将来に修正プログラムをリリースする予定です。</span><span class="sxs-lookup"><span data-stu-id="357d4-178">We are currently investigating this issue and plan to release a fix in the near future.</span></span>  <span data-ttu-id="357d4-179">救難をインストールして、TLS 1.0 を無効にも計画していることを最初に、救難のインストールを完了し、TLS 1.0 を無効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="357d4-179">If you are planning to install CQD and also disable TLS 1.0, we recommend that you complete CQD installation first, and then proceed with TLS 1.0 disabling.</span></span>

#### <a name="third-party-devices"></a><span data-ttu-id="357d4-180">サード ・ パーティ製デバイス</span><span class="sxs-lookup"><span data-stu-id="357d4-180">Third-party devices</span></span>

<span data-ttu-id="357d4-181">3PIP 電話などのサードパーティ製のデバイスでビデオ会議、リバース プロキシとロード バランサーでは、必ず TLS 1.2 のサポート性を検証、慎重にテストが必要な場合、ベンダーにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="357d4-181">On third-party devices such as 3PIP phones, Video conferencing, Reverse Proxies and Load Balancers, be sure to validate TLS 1.2 supportability, test carefully, and contact the vendor if needed.</span></span>

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a><span data-ttu-id="357d4-182">エッジ トランスポート サーバーで TLS 1.0 または 1.1 を無効にすると、フェデレーションに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="357d4-182">Federation considerations when disabling TLS 1.0/1.1 on Edge servers</span></span>

<span data-ttu-id="357d4-183">慎重の計画し、エッジ トランスポート サーバーに TLS 1.0 または 1.1 を無効にすることの影響を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="357d4-183">You must carefully plan for and consider the impact of disabling TLS 1.0/1.1 on your Edge servers.</span></span>  <span data-ttu-id="357d4-184">TLS 1.0 および 1.1 を無効にすると、他の組織は不要になったできる組織とフェデレーションを行うことがあります。</span><span class="sxs-lookup"><span data-stu-id="357d4-184">Once TLS 1.0 and 1.1 are disabled, you may find that other organizations are no longer be able to federate with your organization.</span></span>

<span data-ttu-id="357d4-185">TLS 1.0 または 1.1 適用されていない (デバイス 2015、Lync 2013) との下位互換性を維持するために、エッジ サーバーで有効にしておくことを選択するか、古い (2010) の外部システムです。</span><span class="sxs-lookup"><span data-stu-id="357d4-185">You may opt to keep TLS 1.0/1.1 enabled on your Edge servers to maintain backward compatibility with non-patched (SfB 2015, Lync 2013) or older (2010) external systems.</span></span>

<span data-ttu-id="357d4-186">マイクロソフトを出せないアドバイスや推奨事項であるかどうか、ネットワークのエッジ (または任意のネットワーク) を下回った PCI の標準であります。個々 の会社で決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="357d4-186">Microsoft cannot provide advice or recommendations on whether or not your Edge network (or any network) falls under PCI standard; that must be determined by the individual company.</span></span>

<span data-ttu-id="357d4-187">ビジネス オンラインの Skype は TLS 1.2 現在では、オンラインでは、ハイブリッドまたはフェデレーションへの影響はありませんのでです。</span><span class="sxs-lookup"><span data-stu-id="357d4-187">Skype for Business Online is capable of TLS 1.2 today, so no impact to Hybrid/Federation with Online is expected.</span></span>

<span data-ttu-id="357d4-188">Skype コンシューマー サービスには、PIC (パブリック IM 接続): 予定です[Skype の接続性](../../deploy/deploy-skype-connectivity.md)に影響を与えるに TLS 1.0 または 1.1 を無効にします。Microsoft PIC ゲートウェイが TLS 1.2 の機能では既にあります。</span><span class="sxs-lookup"><span data-stu-id="357d4-188">PIC (Public IM Connectivity) to Skype Consumer service: We do not expect disabling TLS 1.0/1.1 to impact [Skype Connectivity](../../deploy/deploy-skype-connectivity.md); Microsoft PIC Gateways are already TLS 1.2 capable.</span></span>

## <a name="prerequisites-and-process"></a><span data-ttu-id="357d4-189">前提条件とプロセス</span><span class="sxs-lookup"><span data-stu-id="357d4-189">Prerequisites and process</span></span>

<span data-ttu-id="357d4-190">TLS 1.0 および 1.1 は、無効な範囲外のサーバー、クライアントとデバイスは、正しく、またはすべての機能になった後、上記で説明した場合を除きます。</span><span class="sxs-lookup"><span data-stu-id="357d4-190">Except where noted above, once TLS 1.0 and 1.1 are disabled out-of-scope servers, clients and devices will longer function properly, or at all.</span></span> <span data-ttu-id="357d4-191">一時停止し、Microsoft から更新済みのガイダンスを待機する必要があります。</span><span class="sxs-lookup"><span data-stu-id="357d4-191">This may mean you need to pause and wait for updated guidance from Microsoft.</span></span> <span data-ttu-id="357d4-192">セットアップを完了してすべての要件を満たすし、隔たりに対処する計画があることを確認したら、続行します。</span><span class="sxs-lookup"><span data-stu-id="357d4-192">Once you are satisfied that you meet all requirements and have a plan to address gaps, proceed.</span></span>

<span data-ttu-id="357d4-193">高レベルは、ビジネス サーバー 2019 の Skype がインストールでは、プロシージャの準備ができてビジネス サーバー 2015 の Skype が必要 CU6 HF2、.NET と SQL、展開の前提条件となるレジストリ キー、および最後に、個別に事前に必要な更新プログラムを適用することをインストールすることOS 構成のラウンドは、(すなわち無効にする TLS 1.0 と 1.1 を使用してレジストリ ファイルのインポート) を更新します。</span><span class="sxs-lookup"><span data-stu-id="357d4-193">At a high level, while Skype for Business Server 2019 is ready for procedure at install, Skype for Business Server 2015 will require that you install CU6 HF2, applying pre-requisite updates to .NET and SQL, deploying prerequisite registry keys, and finally a separate round of OS configuration updates (i.e. disabling TLS 1.0 and 1.1 via registry file import).</span></span> <span data-ttu-id="357d4-194">ビジネス サーバー 2015 CU6 HF2、TLS 1.0 と 1.1 を環境内の任意のサーバーを無効にする前に Skype を含むすべての必須コンポーネントのインストールを完了することがきわめて重要です。</span><span class="sxs-lookup"><span data-stu-id="357d4-194">It is critically important that you complete installation of all prerequisites, including Skype for Business Server 2015 CU6 HF2, prior to disabling TLS 1.0 and 1.1 on any server in your environment.</span></span> <span data-ttu-id="357d4-195">ビジネス サーバー、エッジの役割と SQL バックエンドを含むすべての Skype では、更新プログラムが必要です。</span><span class="sxs-lookup"><span data-stu-id="357d4-195">Every Skype for Business server, including Edge role and SQL Backends, requires the updates.</span></span> <span data-ttu-id="357d4-196">また (スコープ) 内のすべてのサポートされているクライアントが必要な最小バージョンに更新されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="357d4-196">Also ensure that all supported (in-scope) clients have been updated to the required minimum versions.</span></span> <span data-ttu-id="357d4-197">同様の管理ワークステーションを更新することを忘れないでください。</span><span class="sxs-lookup"><span data-stu-id="357d4-197">Don’t forget to update management workstations as well.</span></span>

<span data-ttu-id="357d4-198">Skype をビジネスのサーバーのアップグレードの次の「表裏」操作通常順序にします。</span><span class="sxs-lookup"><span data-stu-id="357d4-198">We want to follow the usual order of operations of "inside out" for upgrading Skype for Business servers.</span></span> <span data-ttu-id="357d4-199">ディレクター プール、永続的なチャット、およびプールの対応するを通常の方法と同じ方法で扱います。</span><span class="sxs-lookup"><span data-stu-id="357d4-199">Treat Director pools, Persistent chat, and Paired Pools in the same manner you normally would.</span></span> <span data-ttu-id="357d4-200">順序とアップグレードの方法については、[ここ](topology.md)と[ここ](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)。</span><span class="sxs-lookup"><span data-stu-id="357d4-200">Order and methods for upgrade are covered [here](topology.md) and [here](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).</span></span>

### <a name="high-level-process"></a><span data-ttu-id="357d4-201">高度なプロセス</span><span class="sxs-lookup"><span data-stu-id="357d4-201">High-level process</span></span>

1. <span data-ttu-id="357d4-202">運用サーバーを構成する前にテスト環境ですべての手順をテストします。</span><span class="sxs-lookup"><span data-stu-id="357d4-202">Test all steps in your lab prior to configuring production servers.</span></span>
2. <span data-ttu-id="357d4-203">バックアップし、更新するすべての個々 のサーバーにエクスポートしたレジストリのコピーを保持します。</span><span class="sxs-lookup"><span data-stu-id="357d4-203">Back up and preserve a copy of exported registry on each and every individual server to be updated.</span></span> <span data-ttu-id="357d4-204">サーバー間でレジストリを共有することはできません。ベースのコンピューターの一意のキーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="357d4-204">You cannot share registries between servers; they contain unique machine-based keys.</span></span>
3. <span data-ttu-id="357d4-205">ビジネス 2015年サーバーのすべての Skype は、CU6 HF2 以降にアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="357d4-205">Upgrade all Skype for Business 2015 servers to CU6 HF2 or higher.</span></span> <span data-ttu-id="357d4-206">(ビジネス サーバー 2019 の Skype での CU は必要ありません)</span><span class="sxs-lookup"><span data-stu-id="357d4-206">(For Skype for Business Server 2019, no CU is needed)</span></span>
4. <span data-ttu-id="357d4-207">すべてのサーバーにすべての必須コンポーネントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="357d4-207">Install all prerequisites to all servers.</span></span>
5. <span data-ttu-id="357d4-208">前提条件となるレジストリ キーを展開します。</span><span class="sxs-lookup"><span data-stu-id="357d4-208">Deploy prerequisite registry keys.</span></span>
6. <span data-ttu-id="357d4-209">スコープ内のすべてのクライアントが更新されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="357d4-209">Ensure that all in-scope clients are updated.</span></span>
7. <span data-ttu-id="357d4-210">TLS 1.0 および 1.1 レジストリ ・ インポートを使用して無効にします。</span><span class="sxs-lookup"><span data-stu-id="357d4-210">Disable TLS 1.0 and 1.1 via registry import.</span></span>
8. <span data-ttu-id="357d4-211">ワークロードが期待どおりに機能しているかを検証します。</span><span class="sxs-lookup"><span data-stu-id="357d4-211">Validate that workloads are functioning as expected.</span></span>
    - <span data-ttu-id="357d4-212">問題が発生した場合のトラブルシューティングおよび解決するには、または</span><span class="sxs-lookup"><span data-stu-id="357d4-212">If problems are encountered, troubleshoot and resolve, or</span></span>
    - <span data-ttu-id="357d4-213">TLS 1.0 を再度有効にするのには 2 と 1.1 の手順でレジストリを復元します。</span><span class="sxs-lookup"><span data-stu-id="357d4-213">Restore registry from step 2 to re-enable TLS 1.0 and 1.1</span></span>
9. <span data-ttu-id="357d4-214">TLS 1.2 のみが使用されていることを検証します。</span><span class="sxs-lookup"><span data-stu-id="357d4-214">Validate that only TLS 1.2 is being used.</span></span>

### <a name="install-prerequisites-to-all-servers"></a><span data-ttu-id="357d4-215">すべてのサーバーに前提条件をインストールします。</span><span class="sxs-lookup"><span data-stu-id="357d4-215">Install prerequisites to all servers</span></span>

<span data-ttu-id="357d4-216">TLS 1.0 と 1.1 は、オペレーティング システム レベルでサーバー 2015 のビジネス展開では、Skype で無効にする開始する前に、大規模な依存関係の更新が必要です。</span><span class="sxs-lookup"><span data-stu-id="357d4-216">Extensive dependency updating is required before you begin to disable TLS 1.0 and 1.1 at the operating system level in your Skype for Business Server 2015 deployments.</span></span> <span data-ttu-id="357d4-217">TLS 1.2 をサポートする最小のバージョンを次に示します。</span><span class="sxs-lookup"><span data-stu-id="357d4-217">The following are the minimum versions that can support TLS 1.2.</span></span> <span data-ttu-id="357d4-218">TLS 1.0 および 1.1 を無効にすることを開始する前に、環境内のビジネス サーバーのすべての Skype 経由ですべての必須更新プログラムを展開します。</span><span class="sxs-lookup"><span data-stu-id="357d4-218">Deploy all prerequisite updates across every Skype for Business server in your environment before you begin disabling TLS 1.0 and 1.1.</span></span>

- <span data-ttu-id="357d4-219">Skype のビジネス サーバー 2015 CU6 HF2 ([2018年 3 月更新](https://support.microsoft.com/en-us/help/4086059/march-2018-cumulative-update-6-0-9319-516-for-skype-for-business)) 6.0.9319.516 またはそれ以上</span><span class="sxs-lookup"><span data-stu-id="357d4-219">Skype for Business Server 2015 CU6 HF2 6.0.9319.516 ([March 2018 update](https://support.microsoft.com/en-us/help/4086059/march-2018-cumulative-update-6-0-9319-516-for-skype-for-business)) or higher</span></span>
- <span data-ttu-id="357d4-220">[.NET Framework 4.7](https://www.microsoft.com/en-us/download/details.aspx?id=55167)以上 (下記参照) のレジストリで有効になっている SchUseStrongCrypto と</span><span class="sxs-lookup"><span data-stu-id="357d4-220">[.NET Framework 4.7](https://www.microsoft.com/en-us/download/details.aspx?id=55167) or higher with SchUseStrongCrypto enabled in the registry (provided below)</span></span>
- <span data-ttu-id="357d4-221">ビジネス 2015年のサーバーとバックエンドのすべての Skype の SQL を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="357d4-221">SQL must be updated on all Skype for Business 2015 servers and backends.</span></span> <span data-ttu-id="357d4-222">エンタープライズ エディションのプールの SQL バックエンド、最初に更新、それぞれの専用 FEs。</span><span class="sxs-lookup"><span data-stu-id="357d4-222">Update Enterprise Edition Pool SQL Backends first, then their respective FEs.</span></span> 
    - <span data-ttu-id="357d4-223">SQL Server 2014 SP1 + CU5 ([リンク](https://support.microsoft.com/help/3130926)) またはそれ以上と SQL Server 2012 の SP2 + CU16 またはそれ以上/rtm 版 SQL Server の 2014 + CU12 ([リンク](https://support.microsoft.com/en-us/help/3130923/cumulative-update-12-for-sql-server-2014)) またはそれ以上/2014 SP2 の SQL Server</span><span class="sxs-lookup"><span data-stu-id="357d4-223">SQL Server 2014 SP1 + CU5 ([link](https://support.microsoft.com/help/3130926)), or higher / SQL Server 2012 SP2 + CU16 or higher/ SQL Server 2014 RTM + CU12 ([link](https://support.microsoft.com/en-us/help/3130923/cumulative-update-12-for-sql-server-2014)) or higher / SQL Server 2014 SP2</span></span>
    - <span data-ttu-id="357d4-224">SQL Server ネイティブ クライアントを SQL Server 2012 年 5 号 ([リンク](https://www.microsoft.com/en-us/download/details.aspx?id=50402))</span><span class="sxs-lookup"><span data-stu-id="357d4-224">SQL Server Native Client for SQL Server 2012 ([link](https://www.microsoft.com/en-us/download/details.aspx?id=50402))</span></span>
    - <span data-ttu-id="357d4-225">Microsoft ODBC ドライバーの 11 以上の SQL Server ([リンク](https://www.microsoft.com/en-us/download/details.aspx?id=36434))</span><span class="sxs-lookup"><span data-stu-id="357d4-225">Microsoft ODBC Driver 11 for SQL Server ([link](https://www.microsoft.com/en-us/download/details.aspx?id=36434)), or higher</span></span>
    - <span data-ttu-id="357d4-226">2014 SP2 ([リンク](https://www.microsoft.com/en-in/download/details.aspx?id=42295)) の SQL Server の管理オブジェクトを共有します。</span><span class="sxs-lookup"><span data-stu-id="357d4-226">Shared Management Objects for SQL Server 2014 SP2 ([link](https://www.microsoft.com/en-in/download/details.aspx?id=42295))</span></span>
    - <span data-ttu-id="357d4-227">SQL server SP2 の 2014 ([リンク](https://www.microsoft.com/en-in/download/details.aspx?id=42295)) の SQLSysClrTypes</span><span class="sxs-lookup"><span data-stu-id="357d4-227">SQLSysClrTypes for SQL server 2014 SP2 ([link](https://www.microsoft.com/en-in/download/details.aspx?id=42295))</span></span>

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a><span data-ttu-id="357d4-228">操作の推奨される順序で、必須コンポーネントをインストールするのには基本的な手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="357d4-228">Basic steps to install pre-requisites, in recommended order of operations</span></span>

1. <span data-ttu-id="357d4-229">ビジネス サーバー CU6HF2 は、Skype をインストール (6.0.9319.516) のすべてのサーバーを更新します。</span><span class="sxs-lookup"><span data-stu-id="357d4-229">Install the Skype for Business Server CU6HF2 (6.0.9319.516) update to all servers.</span></span> 
    1. <span data-ttu-id="357d4-230">アップデーターを使用してコンポーネントに更新プログラムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="357d4-230">Install the update to components using the updater.</span></span>
    2. <span data-ttu-id="357d4-231">文書化された手順に従って、データベースを更新します。</span><span class="sxs-lookup"><span data-stu-id="357d4-231">Update databases according to documented procedures.</span></span> <span data-ttu-id="357d4-232">指示が記載されています[https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)。</span><span class="sxs-lookup"><span data-stu-id="357d4-232">Instructions are documented at [https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).</span></span>
    3. <span data-ttu-id="357d4-233">その他の変更に進む展開の製品の機能を検証します。</span><span class="sxs-lookup"><span data-stu-id="357d4-233">Validate product functionality in the deployment prior to moving forward with any other changes.</span></span>
2. <span data-ttu-id="357d4-234">.NET 4.7 をダウンロードするオフラインのインストーラーです。</span><span class="sxs-lookup"><span data-stu-id="357d4-234">Download .NET 4.7 Offline Installer.</span></span> 
    1. <span data-ttu-id="357d4-235">参照。[https://www.microsoft.com/en-us/download/details.aspx?id=55167](https://www.microsoft.com/en-us/download/details.aspx?id=55167)</span><span class="sxs-lookup"><span data-stu-id="357d4-235">Reference: [https://www.microsoft.com/en-us/download/details.aspx?id=55167](https://www.microsoft.com/en-us/download/details.aspx?id=55167)</span></span>
    2. <span data-ttu-id="357d4-236">サーバー 2015 のビジネス サービスの Skype がフロント エンド サーバー上で停止していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="357d4-236">Ensure that Skype for Business Server 2015 services are stopped on the Front End server.</span></span>
    3. <span data-ttu-id="357d4-237">参照。[https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="357d4-237">Reference: [https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)</span></span>
    4. <span data-ttu-id="357d4-238">停止-CsWindowsServices ex (標準エディション)。</span><span class="sxs-lookup"><span data-stu-id="357d4-238">Ex (Standard Edition): Stop-CsWindowsServices</span></span>
    5. <span data-ttu-id="357d4-239">(Enterprise Edition): ex を呼び出す-CsComputerFailover</span><span class="sxs-lookup"><span data-stu-id="357d4-239">Ex (Enterprise Edition): Invoke-CsComputerFailover</span></span>
    6. <span data-ttu-id="357d4-240">インストーラー パッケージを実行します。</span><span class="sxs-lookup"><span data-stu-id="357d4-240">Run the installer package.</span></span>
    7. <span data-ttu-id="357d4-241">サーバーを再起動します。</span><span class="sxs-lookup"><span data-stu-id="357d4-241">Reboot the server.</span></span>
3. <span data-ttu-id="357d4-242">すべてのサーバー上の SQL Express 2014 を更新します。</span><span class="sxs-lookup"><span data-stu-id="357d4-242">Update SQL Express 2014 on all servers.</span></span> 
    1. <span data-ttu-id="357d4-243">参照。[https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span><span class="sxs-lookup"><span data-stu-id="357d4-243">Reference: [https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span></span>
    2. <span data-ttu-id="357d4-244">SQL 2014 SP2 をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="357d4-244">Download SQL 2014 SP2</span></span> 
        - <span data-ttu-id="357d4-245">参照。[https://www.microsoft.com/en-us/download/details.aspx?id=53168](https://www.microsoft.com/en-us/download/details.aspx?id=53168)</span><span class="sxs-lookup"><span data-stu-id="357d4-245">Reference: [https://www.microsoft.com/en-us/download/details.aspx?id=53168](https://www.microsoft.com/en-us/download/details.aspx?id=53168)</span></span>
    3. <span data-ttu-id="357d4-246">インストール メディアをサーバー上のフォルダーにコピーする (例: C:\01_2014SqlSp2)</span><span class="sxs-lookup"><span data-stu-id="357d4-246">Copy the installation media to a folder on the server (Ex: C:\01_2014SqlSp2)</span></span>
    4. <span data-ttu-id="357d4-247">Skype をフロント エンド サーバーでサービスが停止して、ビジネス サーバー 2015 のことを確認します。</span><span class="sxs-lookup"><span data-stu-id="357d4-247">Ensure Skype for Business Server 2015 services are stopped on the Front End server</span></span> 
        - <span data-ttu-id="357d4-248">停止-CsWindowsService ex (標準エディション)。</span><span class="sxs-lookup"><span data-stu-id="357d4-248">Ex (Standard Edition): Stop-CsWindowsService</span></span>
        - <span data-ttu-id="357d4-249">(Enterprise Edition): ex を呼び出す-CsComputerFailove</span><span class="sxs-lookup"><span data-stu-id="357d4-249">Ex (Enterprise Edition): Invoke-CsComputerFailove</span></span>
    5. <span data-ttu-id="357d4-250">管理者のコマンド プロンプトを開き、インストールされているすべてのコンポーネントおよびインスタンスをアップグレード</span><span class="sxs-lookup"><span data-stu-id="357d4-250">Open an Admin Command Prompt, and upgrade all installed components and instances</span></span> 
        - <span data-ttu-id="357d4-251">例: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe/qs/IAcceptSQLServerLicenseTerms 行いました修正プログラム/AllInstances を =</span><span class="sxs-lookup"><span data-stu-id="357d4-251">Example: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action=Patch /AllInstances</span></span>
4. <span data-ttu-id="357d4-252">SQL ネイティブ クライアントを更新します。</span><span class="sxs-lookup"><span data-stu-id="357d4-252">Update SQL Native Client.</span></span> 
    1. <span data-ttu-id="357d4-253">参照: [https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server)。</span><span class="sxs-lookup"><span data-stu-id="357d4-253">Reference: [https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span></span>
    2. <span data-ttu-id="357d4-254">ダウンロードします。[https://www.microsoft.com/en-us/download/details.aspx?id=50402](https://www.microsoft.com/en-us/download/details.aspx?id=50402)</span><span class="sxs-lookup"><span data-stu-id="357d4-254">Download from [https://www.microsoft.com/en-us/download/details.aspx?id=50402](https://www.microsoft.com/en-us/download/details.aspx?id=50402)</span></span>
    3. <span data-ttu-id="357d4-255">フロント エンド サーバーでサービスが停止して、ビジネス サーバー 2015 の Skype をことを確認します。</span><span class="sxs-lookup"><span data-stu-id="357d4-255">Ensure Skype for Business Server 2015 services are stopped on the Front End server.</span></span> 
        - <span data-ttu-id="357d4-256">停止-CsWindowsServices ex (標準エディション)。</span><span class="sxs-lookup"><span data-stu-id="357d4-256">Ex (Standard Edition): Stop-CsWindowsServices</span></span>
        - <span data-ttu-id="357d4-257">(Enterprise Edition): ex を呼び出す-CsComputerFailove</span><span class="sxs-lookup"><span data-stu-id="357d4-257">Ex (Enterprise Edition): Invoke-CsComputerFailove</span></span>
    4. <span data-ttu-id="357d4-258">実行がインストールされている SQL インスタンスを停止します。</span><span class="sxs-lookup"><span data-stu-id="357d4-258">Stop the SQL instances installed from running</span></span> 
        - <span data-ttu-id="357d4-259">Ex: Get サービス 'MSSQL$ RTCLOCAL' |停止サービス</span><span class="sxs-lookup"><span data-stu-id="357d4-259">Ex: Get-Service 'MSSQL$RTCLOCAL' | Stop-Servic</span></span>
        - <span data-ttu-id="357d4-260">Ex: Get サービス 'MSSQL$ LYNCLOCAL' |停止サービス</span><span class="sxs-lookup"><span data-stu-id="357d4-260">Ex: Get-Service 'MSSQL$LYNCLOCAL' | Stop-Servic</span></span>
        - <span data-ttu-id="357d4-261">(Standard Edition のみ): ex Get サービス 'MSSQL$ RTC' |停止サービス</span><span class="sxs-lookup"><span data-stu-id="357d4-261">Ex (Standard Edition Only): Get-Service 'MSSQL$RTC' | Stop-Servic</span></span>
    5. <span data-ttu-id="357d4-262">更新をインストールします。</span><span class="sxs-lookup"><span data-stu-id="357d4-262">Install the update.</span></span>
5. <span data-ttu-id="357d4-263">SQL Server の ODBC ドライバー 11 を更新します。</span><span class="sxs-lookup"><span data-stu-id="357d4-263">Update ODBC Driver 11 for SQL Server.</span></span> 
    1. <span data-ttu-id="357d4-264">参照: [https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server)。</span><span class="sxs-lookup"><span data-stu-id="357d4-264">Reference: [https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span></span>
    2. <span data-ttu-id="357d4-265">ダウンロードします。[https://www.microsoft.com/en-us/download/confirmation.aspx?id=36434](https://www.microsoft.com/en-us/download/confirmation.aspx?id=36434)</span><span class="sxs-lookup"><span data-stu-id="357d4-265">Download from [https://www.microsoft.com/en-us/download/confirmation.aspx?id=36434](https://www.microsoft.com/en-us/download/confirmation.aspx?id=36434)</span></span>
    3. <span data-ttu-id="357d4-266">サーバー 2015 のビジネス サービスの Skype がフロント エンド サーバー上で停止していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="357d4-266">Ensure that Skype for Business Server 2015 services are stopped on the Front End server</span></span> 
        - <span data-ttu-id="357d4-267">停止-CsWindowsService ex (標準エディション)。</span><span class="sxs-lookup"><span data-stu-id="357d4-267">Ex (Standard Edition): Stop-CsWindowsService</span></span>
        - <span data-ttu-id="357d4-268">(Enterprise Edition): ex を呼び出す-CsComputerFailove</span><span class="sxs-lookup"><span data-stu-id="357d4-268">Ex (Enterprise Edition): Invoke-CsComputerFailove</span></span>
    4. <span data-ttu-id="357d4-269">更新をインストールします。</span><span class="sxs-lookup"><span data-stu-id="357d4-269">Install the update.</span></span>
6. <span data-ttu-id="357d4-270">前提条件となるレジストリ キーを展開します。</span><span class="sxs-lookup"><span data-stu-id="357d4-270">Deploy prerequisite registry keys.</span></span>

### <a name="pre-requisite-registry-keys"></a><span data-ttu-id="357d4-271">必須のレジストリ キー</span><span class="sxs-lookup"><span data-stu-id="357d4-271">Pre-requisite registry keys</span></span>

<span data-ttu-id="357d4-272">メモ帳に次のテストをコピー/貼り付けと TLSPreReq.reg または任意の名前の名前を変更し、インポートします。</span><span class="sxs-lookup"><span data-stu-id="357d4-272">Copy/paste the following test into Notepad and rename TLSPreReq.reg or a name of your choice, then import:</span></span>

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

<span data-ttu-id="357d4-273">SQL の背面の端のエンタープライズ エディションのプール、前提条件、および TLS を無効にする必要がありますとして扱われ、SQL、または OS の更新プログラムは次のようです。参照してください。[https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span><span class="sxs-lookup"><span data-stu-id="357d4-273">For SQL back ends for Enterprise Edition Pools, prerequisites and TLS disable should be treated as any SQL or OS updates would; refer to: [https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span></span>

<span data-ttu-id="357d4-274">前提条件となるアプリケーションと手順を無効にすると TLS の両方を組み合わせることができます、中に TLS 1.0 と 1.1 は、オペレーティング システム レベルでの無効化を続行する前にすべての前提条件を適用するを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="357d4-274">While both the prerequisite application and TLS disabling steps can be combined, we strongly recommend all prerequisites be applied before proceeding with disabling of TLS 1.0 and 1.1 at the operating system level.</span></span> <span data-ttu-id="357d4-275">後で先に進むには、TLS 1.0 または 1.1 を無効にし、すべての作業負荷を正しくして、期待どおりの機能を検証するすべての前提条件を展開することにより、環境を準備するのには、ベスト プラクティスに基づくアプローチになります。</span><span class="sxs-lookup"><span data-stu-id="357d4-275">The best practice approach would be to prepare the environment by deploying all prerequisites, validating that workloads all function correctly and as expected, and then proceeding with TLS 1.0/1.1 disable at a later time.</span></span>

### <a name="disable-tls-10-and-11-via-registry-import"></a><span data-ttu-id="357d4-276">TLS 1.0 と 1.1 レジストリ ・ インポートを使用して無効にします。</span><span class="sxs-lookup"><span data-stu-id="357d4-276">Disable TLS 1.0 and 1.1 via registry import</span></span>

<span data-ttu-id="357d4-277">*すべての前提条件を完了し、Skype のビジネス サーバーを更新するかどうかを確認*、次の手順に進む前にできます。</span><span class="sxs-lookup"><span data-stu-id="357d4-277">Before you proceed with the next steps, *make sure you have completed all prerequisites and updated Skype for Business Servers*.</span></span>

<span data-ttu-id="357d4-278">メモ帳ファイルに次のテキストをコピーし、 **TLSDisable.reg**名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="357d4-278">Copy the following text into a Notepad file and rename it **TLSDisable.reg**:</span></span>

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

<span data-ttu-id="357d4-279">TLS 1.0 を無効にする各サーバーおよび 1.1 で .reg ファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="357d4-279">Import the .reg file on each server you wish to disable TLS 1.0 and 1.1.</span></span> <span data-ttu-id="357d4-280">サーバーを再起動します。</span><span class="sxs-lookup"><span data-stu-id="357d4-280">Reboot the server.</span></span> <span data-ttu-id="357d4-281">サービスがオンラインに戻る、次のサーバーに移動します。</span><span class="sxs-lookup"><span data-stu-id="357d4-281">Once the services have come back online, move to the next server.</span></span> <span data-ttu-id="357d4-282">エンタープライズ エディションのプールの実行方法については、OS の更新プログラムを実行します。</span><span class="sxs-lookup"><span data-stu-id="357d4-282">The approach for Enterprise Edition Pools is the same you would take for any OS update.</span></span>

<span data-ttu-id="357d4-283">お気付き TLS 1.0 および 1.1 をここでは無効にするより多くを行っています。</span><span class="sxs-lookup"><span data-stu-id="357d4-283">You may have noticed we are doing more than just disabling TLS 1.0 and 1.1 here.</span></span> <span data-ttu-id="357d4-284">暗号パッケージ ・ プログラムは、(上記を参照) のように再注文し、いくつかの古い脆弱な暗号化を無効にすることをサポートします。</span><span class="sxs-lookup"><span data-stu-id="357d4-284">We are supporting Cipher Suite re-order (as shown above) and the disabling of some older weak ciphers.</span></span> <span data-ttu-id="357d4-285">これは私たちが公式にサポートされて SCHANNEL、Crypto API にこれらの変更 Skype のビジネスのサーバーの最初の時間であり、私たちをサポートし、この時点でのテストが唯一のものは、これらの変更することが重要。</span><span class="sxs-lookup"><span data-stu-id="357d4-285">This is the first time we have officially supported these changes to SCHANNEL and Crypto API on Skype for Business Server, and it is important to note that these changes are the only ones we support and have tested at this time.</span></span> <span data-ttu-id="357d4-286">将来、追加の構成を検討することができますが、ここでは、変更しないでください実装では、レジストリ ファイルのインポート。</span><span class="sxs-lookup"><span data-stu-id="357d4-286">We may consider additional configurations in the future, but for now, please do not modify the registry import file in your implementation.</span></span>

### <a name="validate-that-workloads-are-functioning-as-expected"></a><span data-ttu-id="357d4-287">ワークロードが期待どおりに機能しているかを検証します。</span><span class="sxs-lookup"><span data-stu-id="357d4-287">Validate that workloads are functioning as expected</span></span>

<span data-ttu-id="357d4-288">TLS 1.0 および 1.1 は、お客様の環境で無効になっています後、は、メインの作業負荷が期待どおりに機能していることを確認して IM & プレゼンス、P2P 通話、エンタープライズ VoIP などなど。</span><span class="sxs-lookup"><span data-stu-id="357d4-288">Once TLS 1.0 and 1.1 have been disabled in your environment, ensure that all your main workloads are functioning as expected, such as IM & Presence, P2P calls, Enterprise Voice, etc.</span></span>

<span data-ttu-id="357d4-289">**検証のみ TLS 1.2 を使用します。**</span><span class="sxs-lookup"><span data-stu-id="357d4-289">**Validate only TLS 1.2 is being used**</span></span>

<span data-ttu-id="357d4-290">古いプロトコル TLS 1.0 および 1.1 が使用されていないビジネス トラフィック用の Skype の新しい監査を実行する、セキュリティ チームがあります。</span><span class="sxs-lookup"><span data-stu-id="357d4-290">Have your Security Team perform a new audit of Skype for Business traffic to ensure that the older protocols TLS 1.0 and 1.1 are no longer in use.</span></span>

<span data-ttu-id="357d4-291">また、TLS 1.0 と 1.1 の TLS を無効にした後、Skype からビジネス サーバー 2015 の TLS 接続を web サービスをテストするのには、Internet Explorer を使用できます。</span><span class="sxs-lookup"><span data-stu-id="357d4-291">Alternatively, you can use Internet Explorer to test TLS connections to web services from Skype for Business Server 2015 after TLS 1.0 and TLS 1.1 have been disabled.</span></span>

1. <span data-ttu-id="357d4-292">Internet Explorer を起動します。</span><span class="sxs-lookup"><span data-stu-id="357d4-292">Launch Internet Explorer.</span></span>
2. <span data-ttu-id="357d4-293">**ツール**を選択して > **インター ネット オプション**。</span><span class="sxs-lookup"><span data-stu-id="357d4-293">Select **Tools** > **Internet Options**.</span></span>
3. <span data-ttu-id="357d4-294">[**詳細設定**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="357d4-294">Select the **Advanced** tab.</span></span>
4. <span data-ttu-id="357d4-295">[**設定**] の一番下までスクロールします。</span><span class="sxs-lookup"><span data-stu-id="357d4-295">Under **Settings**, scroll to the bottom.</span></span>
5. <span data-ttu-id="357d4-296">TLS 1.0、TLS 1.1 および TLS 1.2 が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="357d4-296">Verify that TLS 1.0, TLS 1.1, and TLS 1.2 are enabled.</span></span>
6. <span data-ttu-id="357d4-297">(正常に接続)、デバイスの 2015年プールの内部の Web サービスの URL を参照してください。</span><span class="sxs-lookup"><span data-stu-id="357d4-297">Browse the Internal Web Service URL of your SfB 2015 pool (should connect successfully).</span></span>
7. <span data-ttu-id="357d4-298">Internet Explorer に戻るし、 **TLS 1.2 を使用**するオプションのみを無効にします。</span><span class="sxs-lookup"><span data-stu-id="357d4-298">Go back into Internet Explorer and disable the option to **Use TLS 1.2** only.</span></span>
8. <span data-ttu-id="357d4-299">(接続に失敗する必要があります) もう一度デバイス 2015年プールの内部の Web サービスの URL を参照してください。</span><span class="sxs-lookup"><span data-stu-id="357d4-299">Browse the Internal Web Service URL of your SfB 2015 pool again (should fail to connect).</span></span>

![インターネット オプション](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a><span data-ttu-id="357d4-301">高度な展開シナリオ</span><span class="sxs-lookup"><span data-stu-id="357d4-301">Advanced deployment scenarios</span></span>

<span data-ttu-id="357d4-302">ビジネス Ser 2015 の Skype で TLS 1.2 をサポートするためにいくつかの依存関係の前提条件が必要であるため、TLS 1.0 および 1.1 が無効になってすべてのシステムで失敗 RTM 版からをインストールすます。</span><span class="sxs-lookup"><span data-stu-id="357d4-302">Because some dependency prerequisites are required to support TLS 1.2 in Skype for Business Ser 2015, installing from RTM media will fail on any system where TLS 1.0 and 1.1 have been disabled.</span></span>

<span data-ttu-id="357d4-303">**環境内で、TLS 1.0 および 1.1 が無効になっていると、新しいの Standard Edition Server またはエンタープライズ エディションのプールを展開します。**</span><span class="sxs-lookup"><span data-stu-id="357d4-303">**Deploying New Standard Edition Servers or Enterprise Edition Pools once TLS 1.0 and 1.1 have been disabled in your environment.**</span></span>

<span data-ttu-id="357d4-304">**オプション 1:**[SmartSetup](../../deploy/install/install-skype-for-business-server.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="357d4-304">**Option 1:** Use [SmartSetup](../../deploy/install/install-skype-for-business-server.md).</span></span> <span data-ttu-id="357d4-305">CU、将来の更新された SQL バイナリに対応するために SmartSetup を更新し、将来的にこの資料を更新ことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="357d4-305">Note that we are updating SmartSetup to accommodate the updated SQL binaries in a future CU, and will update this article in the future.</span></span>

<span data-ttu-id="357d4-306">**オプション 2:**(RTCLOCAL および LYNCLOCAL)、ローカルの SQL インスタンスをインストールする前</span><span class="sxs-lookup"><span data-stu-id="357d4-306">**Option 2:** Pre-install local SQL instances (RTCLOCAL and LYNCLOCAL)</span></span>

1. <span data-ttu-id="357d4-307">ダウンロードし、SQL Express 2014 SP2 (SQLEXPR_x64.exe) を FE 上のローカル フォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="357d4-307">Download and copy SQL Express 2014 SP2 (SQLEXPR_x64.exe) to local folder on FE.</span></span> <span data-ttu-id="357d4-308">フォルダー パスの <SQL_FOLDER_PATH> を考えてみましょう。</span><span class="sxs-lookup"><span data-stu-id="357d4-308">Let’s say folder path <SQL_FOLDER_PATH>.</span></span>
2. <span data-ttu-id="357d4-309">PowerShell またはコマンド プロンプトを起動し、<SQL_FOLDER_PATH> に移動します。</span><span class="sxs-lookup"><span data-stu-id="357d4-309">Launch PowerShell or Command Prompt and navigate to <SQL_FOLDER_PATH>.</span></span>
3. <span data-ttu-id="357d4-310">次のコマンドを実行して、RTCLOCAL の SQL インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="357d4-310">Create the RTCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="357d4-311">続行する前に SQLEXPR_x64.exe が完了するまでに待機します。</span><span class="sxs-lookup"><span data-stu-id="357d4-311">Wait until SQLEXPR_x64.exe finishes before proceeding:</span></span>

    <span data-ttu-id="357d4-312">SQLEXPR_x64.exe/Q/IACCEPTSQLSERVERLICENSETERMS/UPDATEENABLED = 0/HIDECONSOLE 行いました = インストール機能 = SQLEngine、ツールの/INSTANCENAME = RTCLOCAL/TCPENABLED = 1/SQLSVCACCOUNT ="NT AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS ="Builtin\管理者"/BROWSERSVCSTARTUPTYPE =「自動」/AGTSVCACCOUNT ="NTAUTHORITY\NetworkService"/SQLSVCSTARTUPTYPE = 自動的</span><span class="sxs-lookup"><span data-stu-id="357d4-312">SQLEXPR_x64.exe  /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=RTCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automati</span></span>
1. <span data-ttu-id="357d4-313">次のコマンドを実行して、LYNCLOCAL の SQL インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="357d4-313">Create the LYNCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="357d4-314">SQLEXPR_x64.exe は、次の手順に進む前に完了するまでに待機します。</span><span class="sxs-lookup"><span data-stu-id="357d4-314">Wait until SQLEXPR_x64.exe finishes before proceeding to the next step:</span></span>

    <span data-ttu-id="357d4-315">SQLEXPR_x64.exe/Q/IACCEPTSQLSERVERLICENSETERMS/UPDATEENABLED = 0/HIDECONSOLE 行いました = インストール機能 = SQLEngine、ツールの/INSTANCENAME = LYNCLOCAL/TCPENABLED = 1/SQLSVCACCOUNT ="NT AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS ="Builtin\管理者"/BROWSERSVCSTARTUPTYPE =「自動」/AGTSVCACCOUNT ="NTAUTHORITY\NetworkService"/SQLSVCSTARTUPTYPE = 自動</span><span class="sxs-lookup"><span data-stu-id="357d4-315">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=LYNCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automatic</span></span>
1. <span data-ttu-id="357d4-316">Skype をビジネス サーバー 2015 の rtm 版のセットアップを実行します。</span><span class="sxs-lookup"><span data-stu-id="357d4-316">Run Skype for Business Server 2015 RTM setup.</span></span>
2. <span data-ttu-id="357d4-317">上記の前提条件」セクションから、残り手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="357d4-317">Follow the remaining steps from the prerequisites section above.</span></span>

<span data-ttu-id="357d4-318">**オプション 3:** ローカル インストール メディアのディレクトリにバイナリを次のように手動で置き換えることが。</span><span class="sxs-lookup"><span data-stu-id="357d4-318">**Option 3:** You may also manually replace binaries in a local installation media directory as follows:</span></span>

1. [<span data-ttu-id="357d4-319">ビジネス サーバーの Skype のための前提条件をインストールします。</span><span class="sxs-lookup"><span data-stu-id="357d4-319">Install prerequisites for Skype for Business Server</span></span>](../../deploy/install/install-prerequisites.md)  
2. 2. <span data-ttu-id="357d4-320">.NET 4.7 をインストールします。</span><span class="sxs-lookup"><span data-stu-id="357d4-320">Install .NET 4.7:</span></span> 
      - <span data-ttu-id="357d4-321">**注:** まず、Skype で .NET 4.7 のサポートの業務サーバー 2015 CU5 + (6.0.9319.281) を導入しました。</span><span class="sxs-lookup"><span data-stu-id="357d4-321">**Note:** We first introduced support for .NET 4.7 in Skype for Business Server 2015 CU5+ (6.0.9319.281).</span></span> <span data-ttu-id="357d4-322">したがって、次以降の手順で私たちが更新されます。 コア コンポーネント メインのインストールの前にします。</span><span class="sxs-lookup"><span data-stu-id="357d4-322">Therefore, in later steps below we will be updating Core Components prior to the main install.</span></span>
      - <span data-ttu-id="357d4-323">ダウンロード先: https://www.microsoft.com/en-us/download/details.aspx?id=55167。</span><span class="sxs-lookup"><span data-stu-id="357d4-323">Download: https://www.microsoft.com/en-us/download/details.aspx?id=55167.</span></span>
      - <span data-ttu-id="357d4-324">参照:[サーバー 2015 のビジネスを展開するため、Skype の前にインストールするソフトウェア](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span><span class="sxs-lookup"><span data-stu-id="357d4-324">Reference: [Software that should be installed before a Skype for Business Server 2015 deployment](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span></span>
3. <span data-ttu-id="357d4-325">ISO ファイルとフォルダーをコピーします。</span><span class="sxs-lookup"><span data-stu-id="357d4-325">Copy ISO Files/Folders:</span></span> 
    - <span data-ttu-id="357d4-326">として接続されているドライブのルート ディレクトリを開くと、Skype ビジネス サーバー 2015 ISO が接続されているのでは、(例: d:\)ファイル エクスプ ローラーでします。</span><span class="sxs-lookup"><span data-stu-id="357d4-326">With the Skype for Business Server 2015 ISO attached, open the root directory of the drive it is attached as (Ex: D:\) in File Explorer.</span></span>
    - <span data-ttu-id="357d4-327">すべてのフォルダーとファイルをローカル ディスク上のフォルダーにコピーする (例: C:\SkypeForBusiness2015ISO)。</span><span class="sxs-lookup"><span data-stu-id="357d4-327">Copy all folders and files to a folder on a local disk (Ex: C:\SkypeForBusiness2015ISO).</span></span>
    - <span data-ttu-id="357d4-328">**注:** コンポーネントをインストールする前にいくつかのファイルは、TLS 1.2 をサポートするために更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="357d4-328">**Note:** Prior to installing components, some files will need to be updated for support of TLS 1.2.</span></span>
4. <span data-ttu-id="357d4-329">MSI および EXE パッケージを置き換えます。</span><span class="sxs-lookup"><span data-stu-id="357d4-329">Replace MSI/EXE Packages:</span></span> 
    - <span data-ttu-id="357d4-330">/Setup/amd64 フォルダーをローカル コンピューター上のインストール メディアので、既存の MSI および EXE パッケージを交換してください。</span><span class="sxs-lookup"><span data-stu-id="357d4-330">Replace the existing MSI and EXE packages in the /Setup/amd64/ folder of the installation media on the local machine.</span></span>
    - <span data-ttu-id="357d4-331">SQL 2014 SP2 の高速。https://www.microsoft.com/en-us/download/details.aspx?id=53167</span><span class="sxs-lookup"><span data-stu-id="357d4-331">SQL 2014 SP2 Express: https://www.microsoft.com/en-us/download/details.aspx?id=53167</span></span> 
        - <span data-ttu-id="357d4-332">ローカルのマシンでは、SQLEXPR_x64 に名前を変更し、セットアップまたは amd64 では、既存のファイルを置き換えると、インストール メディアのフォルダーです。</span><span class="sxs-lookup"><span data-stu-id="357d4-332">Rename to SQLEXPR_x64 on the local machine, and replace the existing file in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="357d4-333">SQL ネイティブ クライアント:https://www.microsoft.com/en-us/download/details.aspx?id=50402</span><span class="sxs-lookup"><span data-stu-id="357d4-333">SQL Native Client: https://www.microsoft.com/en-us/download/details.aspx?id=50402</span></span> 
        - <span data-ttu-id="357d4-334">**注:** Sqlncli.msi、およびセットアップまたは amd64 に存在する既存のファイルを交換する必要がある場合は、名前を変更またはインストール メディアのフォルダーです。</span><span class="sxs-lookup"><span data-stu-id="357d4-334">**Note:** Rename this if necessary to sqlncli.msi, and then replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="357d4-335">SQL 管理オブジェクト:https://www.microsoft.com/en-us/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="357d4-335">SQL Management Objects: https://www.microsoft.com/en-us/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="357d4-336">**注:** Feature pack には、ダウンロードできる項目の多くがあります。</span><span class="sxs-lookup"><span data-stu-id="357d4-336">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="357d4-337">だけ SharedManagementObjects.msi をダウンロードするを選択します。</span><span class="sxs-lookup"><span data-stu-id="357d4-337">Select to download SharedManagementObjects.msi only.</span></span>
        - <span data-ttu-id="357d4-338">**注:** セットアップと amd64 に存在する既存のファイルを置き換えると、インストール メディアのフォルダーです。</span><span class="sxs-lookup"><span data-stu-id="357d4-338">**Note:** Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="357d4-339">SQL CLR の種類:https://www.microsoft.com/en-us/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="357d4-339">SQL CLR Types: https://www.microsoft.com/en-us/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="357d4-340">**注:** Feature pack には、ダウンロードできる項目の多くがあります。</span><span class="sxs-lookup"><span data-stu-id="357d4-340">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="357d4-341">だけ CQLSysClrTypes.msi をダウンロードするを選択します。</span><span class="sxs-lookup"><span data-stu-id="357d4-341">Select to download CQLSysClrTypes.msi only</span></span>
        - <span data-ttu-id="357d4-342">**注**: セットアップまたは amd64 に存在する既存のファイルを置き換えるとインストール メディアのフォルダーです。</span><span class="sxs-lookup"><span data-stu-id="357d4-342">**Note**: Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
5. <span data-ttu-id="357d4-343">コア コンポーネントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="357d4-343">Install Core Components:</span></span> 
    - <span data-ttu-id="357d4-344">セットアップと amd64 から Setup.exe を実行またはインストール メディアのフォルダーです。</span><span class="sxs-lookup"><span data-stu-id="357d4-344">Run Setup.exe from the Setup/amd64/ folder of the installation media.</span></span> <span data-ttu-id="357d4-345">コア コンポーネントをインストールする指示に従います</span><span class="sxs-lookup"><span data-stu-id="357d4-345">Follow the instructions to install Core Components</span></span>
    - <span data-ttu-id="357d4-346">コア コンポーネントを終了します。</span><span class="sxs-lookup"><span data-stu-id="357d4-346">Close Core Components.</span></span>
6. <span data-ttu-id="357d4-347">コア コンポーネントを更新します。</span><span class="sxs-lookup"><span data-stu-id="357d4-347">Update Core Components:</span></span> 
    - <span data-ttu-id="357d4-348">ビジネスの更新プログラムのインストーラーは、Skype をダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="357d4-348">Download the Skype for Business Update Installer.</span></span>
    - <span data-ttu-id="357d4-349">コア コンポーネントを更新し、パフォーマンス カウンターをインストールするインストーラーを実行します。</span><span class="sxs-lookup"><span data-stu-id="357d4-349">Run the installer to update Core Components and install the performance counters.</span></span>
    - <span data-ttu-id="357d4-350">**注:** CU6HF2 のリリースでは、自動更新機能現在のみがインストールされます CU6 まで。</span><span class="sxs-lookup"><span data-stu-id="357d4-350">**Note:** As of the release of CU6HF2, the auto-update feature currently only will install up to CU6.</span></span> <span data-ttu-id="357d4-351">したがって、アップデーターは、6.0.9319.516 をコア ・ コンポーネントを更新するのには個別に実行してください。</span><span class="sxs-lookup"><span data-stu-id="357d4-351">Therefore, the updater must be run separately to update Core Components to 6.0.9319.516.</span></span>
    - <span data-ttu-id="357d4-352">参照。https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015</span><span class="sxs-lookup"><span data-stu-id="357d4-352">Reference: https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015</span></span>
7. <span data-ttu-id="357d4-353">(省略可能) の管理ツールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="357d4-353">Install Administrative Tools (Optional):</span></span> 
    - <span data-ttu-id="357d4-354">SQL Server 2014 更新されたファイルを使用して (x64) の Microsoft SQL Server 2012 のネイティブ クライアント、SQL Server 2014 管理オブジェクト (x64)、および Microsoft システムの CLR 型がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="357d4-354">This will install the Microsoft SQL Server 2012 Native Client, SQL Server 2014 Management Objects (x64), and Microsoft System CLR Types for SQL Server 2014 (x64) using the updated files.</span></span> <span data-ttu-id="357d4-355">さらに、ビジネス サーバー 2015 のトポロジ ビルダーおよびコントロール パネルの Skype はローカル コンピューターで利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="357d4-355">Additionally, the Skype for Business Server 2015 Topology Builder and Control Panel will be available on the local machine.</span></span>
8. <span data-ttu-id="357d4-356">ローカル構成ストア (ステップ 1) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="357d4-356">Install Local Configuration Store (Step 1):</span></span> 
     - <span data-ttu-id="357d4-357">展開ウィザードを開く、サーバーのビジネス システムのインストールまたは更新プログラムの Skype をクリックしてし、**実行**を手順 1 でをクリックします。 ローカル構成ストアのインストールします。</span><span class="sxs-lookup"><span data-stu-id="357d4-357">Open the Deployment Wizard, click Install or Update Skype for Business Server System, and click on **Run** at Step 1: Install Local Configuration Store.</span></span>
     - <span data-ttu-id="357d4-358">**次**の**ローカル構成ストアのインストール**] ダイアログ ボックスをクリックします。</span><span class="sxs-lookup"><span data-stu-id="357d4-358">Click **Next** in the **Install Local Configuration Store** dialog box.</span></span>
     <span data-ttu-id="357d4-359">![ローカル構成ストアのインストール] ダイアログ ボックス](../../media/local-configuration-store.png)</span><span class="sxs-lookup"><span data-stu-id="357d4-359">![Install Local Configuration Store dialog box](../../media/local-configuration-store.png)</span></span>
     - <span data-ttu-id="357d4-360">結果を確認し、タスクの進捗状況が完了したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="357d4-360">Review the results, and ensure that the Task Status is Completed.</span></span> <span data-ttu-id="357d4-361">**ログの表示**] をクリックして、ログ ・ ファイルを確認します。</span><span class="sxs-lookup"><span data-stu-id="357d4-361">Review the resulting log file by clicking **View Log**.</span></span>
     <span data-ttu-id="357d4-362">![完了としてタスクの進捗状況を示しています](../../media/local-configuration-task-completed.png)</span><span class="sxs-lookup"><span data-stu-id="357d4-362">![Task status shows as Completed](../../media/local-configuration-task-completed.png)</span></span>
     - <span data-ttu-id="357d4-363">[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="357d4-363">Click **Finish**.</span></span>
9. <span data-ttu-id="357d4-364">設定または解除 Skype ビジネス サーバー コンポーネント (ステップ 2)。</span><span class="sxs-lookup"><span data-stu-id="357d4-364">Set up or remove Skype for Business Server Components (Step 2):</span></span>
    - <span data-ttu-id="357d4-365">展開ウィザードを開く、[**インストール]、またはサーバーのビジネス システムの更新プログラムの Skype**、および手順 2 での**実行**] をクリックします設定または Skype をビジネスのサーバー コンポーネントの削除。</span><span class="sxs-lookup"><span data-stu-id="357d4-365">Open the Deployment Wizard, click **Install or Update Skype for Business Server System**, and click **Run** at Step 2: Set up or Remove Skype for Business Server Components</span></span>
    - <span data-ttu-id="357d4-366">内で**次**の設定を Skype ビジネス サーバー コンポーネント] ダイアログ ボックスをクリックします。</span><span class="sxs-lookup"><span data-stu-id="357d4-366">Click **Next** in the Set Up Skype for Business Server Components dialog box.</span></span>
    <span data-ttu-id="357d4-367">![ビジネス サーバー コンポーネント] ウィンドウの設定を Skype](../../media/set-up-skype-for-business-server-components-window.png)</span><span class="sxs-lookup"><span data-stu-id="357d4-367">![the Set Up Skype for Business Server Components window](../../media/set-up-skype-for-business-server-components-window.png)</span></span>
    - <span data-ttu-id="357d4-368">ログの表示] を使用してログを確認し、問題なく完了する設定を検証します。</span><span class="sxs-lookup"><span data-stu-id="357d4-368">Review the log using View Log, and validate that setup completed without issues.</span></span> 
    - <span data-ttu-id="357d4-369">[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="357d4-369">Click **Finish**.</span></span>
10. <span data-ttu-id="357d4-370">追加インストールし、必要に応じて構成を続行 (通常のインストール手順をこの時点でに再開することができます)。</span><span class="sxs-lookup"><span data-stu-id="357d4-370">Proceed with additional installation and configuration as required (you can resume normal installation procedures at this point).</span></span>
