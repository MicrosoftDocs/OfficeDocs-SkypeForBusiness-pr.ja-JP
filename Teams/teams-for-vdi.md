---
title: 仮想デスクトップ インフラストラクチャ用の Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi, jmorrow
audience: admin
description: 仮想化されたデスクトップインフラストラクチャ (VDI) 環境で Microsoft Teams を実行する方法について説明します。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c5bc574fc760929d416ce3f62c921bc522c2997c
ms.sourcegitcommit: 35de08b532eb7cf58c3221210c2b3b52f8aa047e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2020
ms.locfileid: "42339462"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a><span data-ttu-id="92d5a-103">仮想デスクトップ インフラストラクチャ用の Teams</span><span class="sxs-lookup"><span data-stu-id="92d5a-103">Teams for Virtualized Desktop Infrastructure</span></span>

<span data-ttu-id="92d5a-104">この記事では、仮想化された環境で Microsoft Teams を使用する場合の要件と制限について説明します。</span><span class="sxs-lookup"><span data-stu-id="92d5a-104">This article describes the requirements and limitations for using Microsoft Teams in a virtualized environment.</span></span>

## <a name="what-is-vdi"></a><span data-ttu-id="92d5a-105">VDI とは</span><span class="sxs-lookup"><span data-stu-id="92d5a-105">What is VDI?</span></span>

<span data-ttu-id="92d5a-106">仮想デスクトップインフラストラクチャ (VDI) は、デスクトップオペレーティングシステムと、データセンターの中央サーバー上のアプリケーションをホストする仮想化テクノロジです。</span><span class="sxs-lookup"><span data-stu-id="92d5a-106">Virtual Desktop Infrastructure (VDI) is virtualization technology that hosts a desktop operating system and applications on a centralized server in a data center.</span></span> <span data-ttu-id="92d5a-107">これにより、完全にセキュリティが設定された一元的な中央集中ソースを持つユーザーに、完全にカスタマイズされたデスクトップエクスペリエンスを提供できます。</span><span class="sxs-lookup"><span data-stu-id="92d5a-107">This enables a fully personalized desktop experience to users with a fully secured and compliant centralized source.</span></span>
 
<span data-ttu-id="92d5a-108">仮想環境での Microsoft Teams はチャットと共同作業をサポートしており、Citrix プラットフォームでは、通話と会議機能もサポートされています。</span><span class="sxs-lookup"><span data-stu-id="92d5a-108">Microsoft Teams in a virtualized environment supports chat and collaboration, and with the Citrix platform, calling and meeting functionality are also supported.</span></span>

<span data-ttu-id="92d5a-109">仮想環境の Teams では、複数の構成がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="92d5a-109">Teams in a virtualized environment supports multiple configurations.</span></span> <span data-ttu-id="92d5a-110">これには、VDI、専用、共有、常設、非永続的モードが含まれます。</span><span class="sxs-lookup"><span data-stu-id="92d5a-110">These include VDI, dedicated, shared, persistent and non-persistent modes.</span></span> <span data-ttu-id="92d5a-111">機能は継続的な開発中であり、定期的に追加されており、今後数ヶ月にわたって機能が拡張されます。</span><span class="sxs-lookup"><span data-stu-id="92d5a-111">Features are in continuous development and are added on a regular basis, and functionality will expand in the coming months and years.</span></span>
 
<span data-ttu-id="92d5a-112">仮想環境で Teams を使用する場合は、仮想化されていない環境での Teams の使用とは多少異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="92d5a-112">Using Teams in a virtualized environment may be somewhat different from using Teams in a non-virtualized environment.</span></span> <span data-ttu-id="92d5a-113">たとえば、一部の高度な機能は仮想化された環境では使用できず、ビデオ解像度が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="92d5a-113">For example, some advanced features may not be available in a virtualized environment and video resolution may differ.</span></span> <span data-ttu-id="92d5a-114">最適なユーザーエクスペリエンスを実現するには、この記事のガイダンスに従ってください。</span><span class="sxs-lookup"><span data-stu-id="92d5a-114">To ensure an optimal user experience, follow the guidance in this article.</span></span>

## <a name="teams-on-vdi-components"></a><span data-ttu-id="92d5a-115">VDI コンポーネントの Teams</span><span class="sxs-lookup"><span data-stu-id="92d5a-115">Teams on VDI components</span></span>

<span data-ttu-id="92d5a-116">仮想環境で Teams を使用するには、次のコンポーネントが必要です。</span><span class="sxs-lookup"><span data-stu-id="92d5a-116">Using Teams in a virtualized environment requires the following components.</span></span>

- <span data-ttu-id="92d5a-117">**仮想ブローカー**: Azure などの仮想化プロバイダーへのリソースと接続マネージャー</span><span class="sxs-lookup"><span data-stu-id="92d5a-117">**Virtualization broker**: The resource and connection manager to the virtualization provider, such as Azure</span></span>
- <span data-ttu-id="92d5a-118">**仮想デスクトップ**: Microsoft Teams を実行する仮想マシン (VM) スタック</span><span class="sxs-lookup"><span data-stu-id="92d5a-118">**Virtual desktop**: The Virtual Machine (VM) stack that runs Microsoft Teams</span></span>
- <span data-ttu-id="92d5a-119">**シンクライアント**: ユーザーが物理的にインターフェイスを使用するエンドポイント</span><span class="sxs-lookup"><span data-stu-id="92d5a-119">**Thin client**: The endpoint that the user physically interfaces with</span></span>
- <span data-ttu-id="92d5a-120">**Teams デスクトップアプリ**: これは teams デスクトップクライアントアプリです</span><span class="sxs-lookup"><span data-stu-id="92d5a-120">**Teams desktop app**: This is the Teams desktop client app</span></span>

## <a name="teams-on-vdi-requirements"></a><span data-ttu-id="92d5a-121">VDI の要件に関するチーム</span><span class="sxs-lookup"><span data-stu-id="92d5a-121">Teams on VDI requirements</span></span>

### <a name="virtualization-provider-requirements"></a><span data-ttu-id="92d5a-122">仮想化プロバイダーの要件</span><span class="sxs-lookup"><span data-stu-id="92d5a-122">Virtualization provider requirements</span></span>

<span data-ttu-id="92d5a-123">Teams デスクトップアプリは、主要な仮想化ソリューションプロバイダーと共に検証されました。</span><span class="sxs-lookup"><span data-stu-id="92d5a-123">The Teams desktop app was validated with leading virtualization solution providers.</span></span> <span data-ttu-id="92d5a-124">市場プロバイダーが複数ある場合は、最小要件が満たされるように仮想化ソリューションプロバイダーに問い合わせることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="92d5a-124">With multiple market providers, we recommend that you consult your virtualization solution provider to ensure minimum requirements are met.</span></span>
  
<span data-ttu-id="92d5a-125">現時点では、音声/ビデオ (AV) 最適化による VDI 上の Teams は、Citrix で認定されています。</span><span class="sxs-lookup"><span data-stu-id="92d5a-125">Currently, Teams on VDI with audio/video (AV) optimization is certified with Citrix.</span></span> <span data-ttu-id="92d5a-126">このセクションの情報を確認して、Citrix と Teams の両方の要件が適切に機能するようになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="92d5a-126">Review the information in this section to ensure both Citrix and Teams requirements are met for proper functionality.</span></span>

### <a name="partners-certified-for-teams"></a><span data-ttu-id="92d5a-127">チームの認定パートナー</span><span class="sxs-lookup"><span data-stu-id="92d5a-127">Partners certified for Teams</span></span>

<span data-ttu-id="92d5a-128">次のパートナーには、Teams の仮想デスクトップインフラストラクチャソリューションがあります。</span><span class="sxs-lookup"><span data-stu-id="92d5a-128">The following partners have virtual desktop infrastructure solutions for Teams.</span></span>

|<span data-ttu-id="92d5a-129">パートナー</span><span class="sxs-lookup"><span data-stu-id="92d5a-129">Partner</span></span>|<span data-ttu-id="92d5a-130">パートナー ソリューション</span><span class="sxs-lookup"><span data-stu-id="92d5a-130">Partner solution</span></span>|
|----|---|
|![Citrix を表すロゴ](media/citrix.png)| <span data-ttu-id="92d5a-132"><a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix の仮想アプリとデスクトップ</a></span><span class="sxs-lookup"><span data-stu-id="92d5a-132"><a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix Virtual Apps and Desktops</a></span></span> |

### <a name="citrix-virtual-apps-and-desktops-requirements"></a><span data-ttu-id="92d5a-133">Citrix の仮想アプリとデスクトップの要件</span><span class="sxs-lookup"><span data-stu-id="92d5a-133">Citrix Virtual Apps and Desktops requirements</span></span>

<span data-ttu-id="92d5a-134">Citrix の仮想アプリとデスクトップ (以前は XenApp と XenDesktop) は、VDI 上の Teams で AV の最適化を実現します。</span><span class="sxs-lookup"><span data-stu-id="92d5a-134">Citrix Virtual Apps and Desktops (formerly known as XenApp and XenDesktop) provides AV optimization for Teams on VDI.</span></span> <span data-ttu-id="92d5a-135">Citrix の仮想アプリとデスクトップを使用すると、VDI 上の Teams では、チャットや共同作業に加えて、通話と会議機能がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="92d5a-135">With Citrix Virtual Apps and Desktops, Teams on VDI supports calling and meeting functionality in addition to chat and collaboration.</span></span>

<span data-ttu-id="92d5a-136">[このページで](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/)は、Citrix の仮想アプリとデスクトップの最新バージョンをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="92d5a-136">You can download the latest version of Citrix Virtual Apps and Desktops [here](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/).</span></span> <span data-ttu-id="92d5a-137">(最初にサインインする必要があります。)必要なコンポーネントは、既定で[Citrix Workspace アプリ (CWA)](https://www.citrix.com/downloads/workspace-app/)と仮想配信エージェント (VDA) にまとめられています。</span><span class="sxs-lookup"><span data-stu-id="92d5a-137">(You'll need to sign in first.) The necessary components are bundled into the [Citrix Workspace app (CWA)](https://www.citrix.com/downloads/workspace-app/) and Virtual Delivery Agent (VDA) by default.</span></span> <span data-ttu-id="92d5a-138">CWA または VDA に追加のコンポーネントまたはプラグインをインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="92d5a-138">You don't need to install any additional components or plugins on CWA or the VDA.</span></span>

<span data-ttu-id="92d5a-139">最新のサーバーとクライアントの要件については、[この Citrix の web サイト](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="92d5a-139">For the latest server and client requirements, see [this Citrix website](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html).</span></span>

## <a name="install-or-update-the-teams-desktop-app-on-vdi"></a><span data-ttu-id="92d5a-140">VDI で Teams デスクトップアプリをインストールまたは更新する</span><span class="sxs-lookup"><span data-stu-id="92d5a-140">Install or update the Teams desktop app on VDI</span></span>

<span data-ttu-id="92d5a-141">MSI パッケージを使用してコンピューターごとのインストールまたはユーザーごとのインストールを使用して、VDI 用の Teams デスクトップアプリを展開することができます。</span><span class="sxs-lookup"><span data-stu-id="92d5a-141">You can deploy the Teams desktop app for VDI using a per-machine installation or per-user installation using the MSI package.</span></span> <span data-ttu-id="92d5a-142">使用する方法を決定するのは、永続的なセットアップと非永続的な設定のどちらを使用するか、または組織に関連する機能のニーズによって異なります。</span><span class="sxs-lookup"><span data-stu-id="92d5a-142">Deciding on which approach to use depends on whether you use a persistent or non-persistent setup and the associated functionality needs of your organization.</span></span>
<span data-ttu-id="92d5a-143">専用の永続的なセットアップの場合、どちらのアプローチも機能します。</span><span class="sxs-lookup"><span data-stu-id="92d5a-143">For a dedicated persistent setup, either approach would work.</span></span>  <span data-ttu-id="92d5a-144">ただし、非永続的なセットアップでは、チームが効率的に作業するために、コンピューターごとにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="92d5a-144">However, for a non-persistent setup, per-machine installation is required for Teams to work efficiently.</span></span> <span data-ttu-id="92d5a-145">「[非永続的なセットアップ](#non-persistent-setup)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="92d5a-145">See the [Non-persistent setup](#non-persistent-setup) section.</span></span>

<span data-ttu-id="92d5a-146">コンピューター単位のインストールでは、自動更新が無効になっています。</span><span class="sxs-lookup"><span data-stu-id="92d5a-146">With per-machine installation, automatic updates is disabled.</span></span> <span data-ttu-id="92d5a-147">つまり、Teams アプリを更新するには、現在のバージョンをアンインストールして、新しいバージョンに更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92d5a-147">This means that to update the Teams app, you must uninstall the current version to update to a newer version.</span></span> <span data-ttu-id="92d5a-148">ユーザーごとのインストールでは、自動更新が有効になっています。</span><span class="sxs-lookup"><span data-stu-id="92d5a-148">With per-user installation, automatic updates is enabled.</span></span> <span data-ttu-id="92d5a-149">ほとんどの VDI の展開では、コンピューターごとのインストールを使用してチームを展開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="92d5a-149">For most VDI deployments, we recommend you deploy Teams using per-machine installation.</span></span>

<span data-ttu-id="92d5a-150">最新のチームバージョンに更新するには、まずアンインストール手順を実行し、次に最新のチームバージョン展開を実行します。</span><span class="sxs-lookup"><span data-stu-id="92d5a-150">To update to the latest Teams version, start with the uninstall procedure followed by latest Teams version deployment.</span></span>

<span data-ttu-id="92d5a-151">VDI 環境での Teams の AV 最適化を適切に機能させるには、シンクライアントエンドポイントがインターネットにアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="92d5a-151">For Teams AV optimization in VDI environments to work properly, the thin client endpoint must have access to the internet.</span></span> <span data-ttu-id="92d5a-152">インターネットアクセスがシンクライアントエンドポイントで利用できない場合、最適化の起動は成功しません。</span><span class="sxs-lookup"><span data-stu-id="92d5a-152">If internet access isn't available at the thin client endpoint, optimization startup won't be successful.</span></span> <span data-ttu-id="92d5a-153">これは、ユーザーが最適化されていないメディアの状態であることを意味します。</span><span class="sxs-lookup"><span data-stu-id="92d5a-153">This means that the user is in a non-optimized media state.</span></span>

#### <a name="dedicated-persistent-setup"></a><span data-ttu-id="92d5a-154">専用の永続的なセットアップ</span><span class="sxs-lookup"><span data-stu-id="92d5a-154">Dedicated persistent setup</span></span>

<span data-ttu-id="92d5a-155">専用の永続的なセットアップでは、ユーザーのローカルオペレーティングシステムに対する変更は、ユーザーがログオフした後も保持されます。</span><span class="sxs-lookup"><span data-stu-id="92d5a-155">In a dedicated persistent setup, users' local operating system changes are retained after users log off.</span></span>  <span data-ttu-id="92d5a-156">永続的なセットアップの場合、Teams はユーザーごととコンピューターごとの両方のインストールをサポートします。</span><span class="sxs-lookup"><span data-stu-id="92d5a-156">For persistent setup, Teams support both per-user and per-machine installation.</span></span>

<span data-ttu-id="92d5a-157">推奨される最小の VM 構成は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="92d5a-157">The following is the recommended minimum VM configuration.</span></span>

|<span data-ttu-id="92d5a-158">パラメーター</span><span class="sxs-lookup"><span data-stu-id="92d5a-158">Parameter</span></span>  |<span data-ttu-id="92d5a-159">ワークステーションオペレーティングシステム</span><span class="sxs-lookup"><span data-stu-id="92d5a-159">Workstation operating system</span></span>  |<span data-ttu-id="92d5a-160">サーバー操作システム</span><span class="sxs-lookup"><span data-stu-id="92d5a-160">Server operation system</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="92d5a-161">vCPU</span><span class="sxs-lookup"><span data-stu-id="92d5a-161">vCPU</span></span>   |    <span data-ttu-id="92d5a-162">2コア</span><span class="sxs-lookup"><span data-stu-id="92d5a-162">2 cores</span></span>     |  <span data-ttu-id="92d5a-163">4、6、または8</span><span class="sxs-lookup"><span data-stu-id="92d5a-163">4,6, or 8</span></span><br><span data-ttu-id="92d5a-164">基になる non-uniform memory access (NUMA) 構成を理解し、それに応じて Vm を構成することが重要です。</span><span class="sxs-lookup"><span data-stu-id="92d5a-164">It's important to understand the underlying non-uniform memory access (NUMA) configuration and configure your VMs accordingly.</span></span>     |
|<span data-ttu-id="92d5a-165">RAM</span><span class="sxs-lookup"><span data-stu-id="92d5a-165">RAM</span></span>     |   <span data-ttu-id="92d5a-166">4 GB</span><span class="sxs-lookup"><span data-stu-id="92d5a-166">4 GB</span></span>      | <span data-ttu-id="92d5a-167">512 ~ 1024 MB (ユーザーあたり)</span><span class="sxs-lookup"><span data-stu-id="92d5a-167">512 to 1024 MB per user</span></span>        |
|<span data-ttu-id="92d5a-168">ストレージ</span><span class="sxs-lookup"><span data-stu-id="92d5a-168">Storage</span></span>    | <span data-ttu-id="92d5a-169">8 GB</span><span class="sxs-lookup"><span data-stu-id="92d5a-169">8 GB</span></span>        | <span data-ttu-id="92d5a-170">40 ~ 60 GB</span><span class="sxs-lookup"><span data-stu-id="92d5a-170">40 to 60 GB</span></span>        |

#### <a name="non-persistent-setup"></a><span data-ttu-id="92d5a-171">非永続的なセットアップ</span><span class="sxs-lookup"><span data-stu-id="92d5a-171">Non-persistent setup</span></span>

<span data-ttu-id="92d5a-172">非永続的なセットアップでは、ユーザーのローカルオペレーティングシステムによる変更は、ユーザーがログオフした後も保持されません。</span><span class="sxs-lookup"><span data-stu-id="92d5a-172">In a non-persistent setup, users' local operating system changes are not retained after users log off.</span></span> <span data-ttu-id="92d5a-173">このようなセットアップは、一般的に共有されているマルチユーザーセッションです。</span><span class="sxs-lookup"><span data-stu-id="92d5a-173">Such setups are commonly shared multi-user sessions.</span></span> <span data-ttu-id="92d5a-174">VM 構成は、ユーザー数と利用可能な物理ボックスリソースによって異なります。</span><span class="sxs-lookup"><span data-stu-id="92d5a-174">VM configuration varies based on the number of users and available physical box resources.</span></span>

<span data-ttu-id="92d5a-175">非永続的なセットアップの場合、Teams デスクトップアプリはコンピューターごとにゴールデンイメージにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="92d5a-175">For a non-persistent setup, the Teams desktop app must be installed per-machine to the golden image.</span></span> <span data-ttu-id="92d5a-176">詳細については、「 [VDI 上の Teams デスクトップアプリをインストールまたは更新](#install-or-update-the-teams-desktop-app-on-vdi)する」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="92d5a-176">(To learn more, see the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section).</span></span> <span data-ttu-id="92d5a-177">これにより、ユーザーセッション中に Teams アプリを効率的に起動することができます。</span><span class="sxs-lookup"><span data-stu-id="92d5a-177">This ensures an efficient launch of the Teams app during a user session.</span></span> <span data-ttu-id="92d5a-178">非永続的なセットアップで Teams を使用する場合も、効率的な Teams のランタイムデータ同期のためのプロファイルキャッシュマネージャーが必要です。これにより、適切なユーザー固有の情報 (ユーザーデータ、プロファイル、設定など) がユーザーセッション中にキャッシュされます。</span><span class="sxs-lookup"><span data-stu-id="92d5a-178">Using Teams with a non-persistent setup also requires a profile caching manager for efficient Teams runtime data sync. This ensures that the appropriate user-specific information (for example, user data, profile, and settings) are cached during the user session.</span></span>  <span data-ttu-id="92d5a-179">さまざまなキャッシュマネージャーソリューションを利用できます。</span><span class="sxs-lookup"><span data-stu-id="92d5a-179">There are variety of caching manager solutions available.</span></span> <span data-ttu-id="92d5a-180">たとえば、 [Fslogix](https://docs.microsoft.com/fslogix/overview)となります。</span><span class="sxs-lookup"><span data-stu-id="92d5a-180">For example, [FSLogix](https://docs.microsoft.com/fslogix/overview).</span></span> <span data-ttu-id="92d5a-181">特定の構成手順については、キャッシュマネージャープロバイダーにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="92d5a-181">Consult your caching manager provider for specific configuration instructions.</span></span>

##### <a name="teams-cached-content-exclusion-list-for-non-persistent-setup"></a><span data-ttu-id="92d5a-182">非永続的なセットアップ用の Teams キャッシュされたコンテンツ除外リスト</span><span class="sxs-lookup"><span data-stu-id="92d5a-182">Teams cached content exclusion list for non-persistent setup</span></span>

<span data-ttu-id="92d5a-183">[Teams のキャッシュ] フォルダーから次のものを除外します。% appdata%/チーム/teams</span><span class="sxs-lookup"><span data-stu-id="92d5a-183">Exclude the following from the Teams caching folder, %appdata%/Microsoft/Teams.</span></span>  <span data-ttu-id="92d5a-184">これらのヘルプを除外すると、ユーザーのキャッシュサイズが小さくなり、非永続的なセットアップがさらに最適化されます。</span><span class="sxs-lookup"><span data-stu-id="92d5a-184">Excluding these help reduce the user caching size to further optimize your non-persistent setup.</span></span>

- <span data-ttu-id="92d5a-185">.txt ファイル</span><span class="sxs-lookup"><span data-stu-id="92d5a-185">.txt files</span></span>
- <span data-ttu-id="92d5a-186">メディアスタックフォルダー</span><span class="sxs-lookup"><span data-stu-id="92d5a-186">Media-stack folder</span></span>

### <a name="office-365-proplus-considerations"></a><span data-ttu-id="92d5a-187">Office 365 ProPlus の考慮事項</span><span class="sxs-lookup"><span data-stu-id="92d5a-187">Office 365 ProPlus considerations</span></span>

<span data-ttu-id="92d5a-188">Office 365 ProPlus で VDI に Teams を展開する場合は、次の点を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="92d5a-188">Consider the following when you deploy Teams with Office 365 ProPlus on VDI.</span></span>

#### <a name="new-deployments-of-teams-through-office-365-proplus"></a><span data-ttu-id="92d5a-189">Office 365 ProPlus を通じた Teams の新しい展開</span><span class="sxs-lookup"><span data-stu-id="92d5a-189">New deployments of Teams through Office 365 ProPlus</span></span>

<span data-ttu-id="92d5a-190">Office 365 ProPlus を通じてチームを展開する前に、コンピューターごとのインストールを使用して展開された既存の Teams アプリをアンインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="92d5a-190">Before you deploy Teams through Office 365 ProPlus, you must first uninstall any pre-existing Teams apps if they were deployed using per-machine installation.</span></span>

<span data-ttu-id="92d5a-191">Office 365 ProPlus を通じた Teams は、ユーザーごとにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="92d5a-191">Teams through Office 365 ProPlus is installed per-user.</span></span> <span data-ttu-id="92d5a-192">詳細については、「 [VDI 上の Teams デスクトップアプリをインストールまたは更新](#install-or-update-the-teams-desktop-app-on-vdi)する」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="92d5a-192">To learn more, see the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.</span></span>

#### <a name="teams-deployments-through-office-365-proplus-updates"></a><span data-ttu-id="92d5a-193">Office 365 ProPlus の更新プログラムを通じた Teams の展開</span><span class="sxs-lookup"><span data-stu-id="92d5a-193">Teams deployments through Office 365 ProPlus updates</span></span>

<span data-ttu-id="92d5a-194">Teams は、Office 365 ProPlus の既存のインストールにも追加されています。</span><span class="sxs-lookup"><span data-stu-id="92d5a-194">Teams is also being added to existing installations of Office 365 ProPlus.</span></span> <span data-ttu-id="92d5a-195">Office 365 ProPlus はユーザーごとにチームをインストールするため、「 [VDI 上の teams デスクトップアプリをインストールまたは更新](#install-or-update-the-teams-desktop-app-on-vdi)する」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="92d5a-195">Since Office 365 ProPlus installs Teams per-user only, see the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.</span></span>

#### <a name="using-teams-with-per-machine-installation-and-office-365-proplus"></a><span data-ttu-id="92d5a-196">コンピューターごとのインストールと Office 365 ProPlus で Teams を使用する</span><span class="sxs-lookup"><span data-stu-id="92d5a-196">Using Teams with per-machine installation and Office 365 ProPlus</span></span>

<span data-ttu-id="92d5a-197">Office 365 ProPlus では、各コンピューターの Teams のインストールをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="92d5a-197">Office 365 ProPlus doesn't support per-machine installations of Teams.</span></span> <span data-ttu-id="92d5a-198">コンピューターごとのインストールを使用するには、Office 365 ProPlus から Teams を除外する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92d5a-198">To use per-machine installation, you must exclude Teams from Office 365 ProPlus.</span></span> <span data-ttu-id="92d5a-199">「 [Teams デスクトップアプリを VM に展開](#deploy-the-teams-desktop-app-to-the-vm)する」と「 [Office 365 ProPlus セクションを通じてチームの展開を除外する方法](#how-to-exclude-teams-deployment-through-office-365-proplus)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="92d5a-199">See the [Deploy the Teams desktop app to the VM](#deploy-the-teams-desktop-app-to-the-vm) and [How to exclude Teams deployment through Office 365 ProPlus](#how-to-exclude-teams-deployment-through-office-365-proplus) sections.</span></span>

#### <a name="how-to-exclude-teams-deployment-through-office-365-proplus"></a><span data-ttu-id="92d5a-200">Office 365 ProPlus を通じてチームの展開を除外する方法</span><span class="sxs-lookup"><span data-stu-id="92d5a-200">How to exclude Teams deployment through Office 365 ProPlus</span></span>

<span data-ttu-id="92d5a-201">Teams と Office 365 ProPlus の詳細については、「 [office 365 ProPlus の新しいインストールからチームを除外する](https://docs.microsoft.com/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-office-365-proplus)」および「[グループポリシーを使って teams のインストールを制御](https://docs.microsoft.com/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="92d5a-201">To learn more about Teams and Office 365 ProPlus, see [How to exclude Teams from new installations of Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-office-365-proplus) and [Use Group Policy to control the installation of Teams](https://docs.microsoft.com/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams).</span></span>

### <a name="deploy-the-teams-desktop-app-to-the-vm"></a><span data-ttu-id="92d5a-202">Teams デスクトップアプリを VM に展開する</span><span class="sxs-lookup"><span data-stu-id="92d5a-202">Deploy the Teams desktop app to the VM</span></span>

1. <span data-ttu-id="92d5a-203">次のリンクのいずれかを使用して、VDI VM オペレーティングシステムと一致する Teams MSI パッケージをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="92d5a-203">Download the Teams MSI package that matches your VDI VM operating system using one of the following links:</span></span>

    - [<span data-ttu-id="92d5a-204">32ビット版</span><span class="sxs-lookup"><span data-stu-id="92d5a-204">32-bit version</span></span>](https://statics.teams.cdn.office.net/production-windows/1.2.00.32462/Teams_windows.msi)
    - [<span data-ttu-id="92d5a-205">64ビット版</span><span class="sxs-lookup"><span data-stu-id="92d5a-205">64-bit version</span></span>](https://statics.teams.cdn.office.net/production-windows-x64/1.2.00.32462/Teams_windows_x64.msi)

    <span data-ttu-id="92d5a-206">必要な Teams デスクトップアプリの最小バージョンはバージョン1.2.00.31357 です。</span><span class="sxs-lookup"><span data-stu-id="92d5a-206">The minimum version of the Teams desktop app that's required is version 1.2.00.31357.</span></span> <span data-ttu-id="92d5a-207">(PSTN 保留は以前のバージョンではサポートされていません)。</span><span class="sxs-lookup"><span data-stu-id="92d5a-207">(PSTN hold is not supported in earlier versions.)</span></span>

2. <span data-ttu-id="92d5a-208">次のいずれかのコマンドを実行して、MSI を VDI VM にインストールします。</span><span class="sxs-lookup"><span data-stu-id="92d5a-208">Install the MSI to the VDI VM by running one of the following commands:</span></span>

    - <span data-ttu-id="92d5a-209">ユーザーごとのインストール (既定)</span><span class="sxs-lookup"><span data-stu-id="92d5a-209">Per-user installation  (default)</span></span>
  
        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name>
        ```
    
        <span data-ttu-id="92d5a-210">これは既定のインストールです。チームは、% AppData% ユーザーフォルダーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="92d5a-210">This is the default installation, which installs Teams to the %AppData% user folder.</span></span> <span data-ttu-id="92d5a-211">この時点で、ゴールデンイメージのセットアップが完了しています。</span><span class="sxs-lookup"><span data-stu-id="92d5a-211">At this point, the golden image setup is complete.</span></span> <span data-ttu-id="92d5a-212">ユーザー単位のインストールでは、非永続的なセットアップでは、チームは適切に動作しません。</span><span class="sxs-lookup"><span data-stu-id="92d5a-212">Teams will not work properly with per-user installation on a non-persistent setup.</span></span>
    
    - <span data-ttu-id="92d5a-213">マシン単位のインストール</span><span class="sxs-lookup"><span data-stu-id="92d5a-213">Per-machine installation</span></span>

        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1
        ```

        <span data-ttu-id="92d5a-214">これにより、チームは64ビットオペレーティングシステムの Program Files (x86) フォルダーと、32ビットオペレーティングシステムの Program Files フォルダーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="92d5a-214">This installs Teams to the Program Files (x86) folder on a 64-bit operating system and to the Program Files folder on a 32-bit operating system.</span></span> <span data-ttu-id="92d5a-215">この時点で、ゴールデンイメージのセットアップが完了しています。</span><span class="sxs-lookup"><span data-stu-id="92d5a-215">At this point, the golden image setup is complete.</span></span> <span data-ttu-id="92d5a-216">非永続的なセットアップでは、コンピューターごとにチームをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="92d5a-216">Installing Teams per-machine is required for non-persistent setups.</span></span>
 
        <span data-ttu-id="92d5a-217">次の対話型ログオンセッションでは、チームが起動し、資格情報を求められます。</span><span class="sxs-lookup"><span data-stu-id="92d5a-217">The next interactive logon session starts Teams and asks for credentials.</span></span>

3. <span data-ttu-id="92d5a-218">VDI VM から MSI をアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="92d5a-218">Uninstall the MSI from the VDI VM.</span></span> 

    <span data-ttu-id="92d5a-219">Teams をアンインストールするには、次の2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="92d5a-219">There are two ways to uninstall Teams:</span></span>  
  
    - <span data-ttu-id="92d5a-220">PowerShell スクリプト (推奨)</span><span class="sxs-lookup"><span data-stu-id="92d5a-220">PowerShell script (recommended)</span></span>
    
    - <span data-ttu-id="92d5a-221">コマンドライン: この方法ではチームが削除されますが、Teams の再インストールはできません。</span><span class="sxs-lookup"><span data-stu-id="92d5a-221">Command line: This approach removes Teams, yet prevents re-installation of Teams.</span></span> <span data-ttu-id="92d5a-222">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="92d5a-222">Run the following command:</span></span>
  
      ```console
      msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>
      ```
      <span data-ttu-id="92d5a-223">これにより、オペレーティングシステムの環境に応じて、Program Files (x86) フォルダーまたは Program Files フォルダーから Teams がアンインストールされます。</span><span class="sxs-lookup"><span data-stu-id="92d5a-223">This uninstalls Teams from the Program Files (x86) folder or Program Files folder, depending on the operating system environment.</span></span>

## <a name="teams-on-vdi-performance-considerations"></a><span data-ttu-id="92d5a-224">VDI のパフォーマンスに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="92d5a-224">Teams on VDI performance considerations</span></span>

<span data-ttu-id="92d5a-225">さまざまな仮想化設定構成があり、それぞれが最適化のために異なるフォーカスが設定されています。</span><span class="sxs-lookup"><span data-stu-id="92d5a-225">There are variety of virtualized setup configurations, each with a different focus for optimization.</span></span> <span data-ttu-id="92d5a-226">たとえば、ユーザーの密度。</span><span class="sxs-lookup"><span data-stu-id="92d5a-226">For example, user density.</span></span> <span data-ttu-id="92d5a-227">計画するときは、組織の作業負荷のニーズに合わせて、次の点を考慮してセットアップを最適化します。</span><span class="sxs-lookup"><span data-stu-id="92d5a-227">When planning, consider the following to help optimize your setup based on the workload needs of your organization:</span></span>

- <span data-ttu-id="92d5a-228">最小要件: 一部のワークロードでは、最小要件を超えるリソースを使用してセットアップを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="92d5a-228">Minimum requirement: Some workloads may require a setup using resources that are above the minimum requirements.</span></span> <span data-ttu-id="92d5a-229">たとえば、より多くのコンピューティングリソースを必要とするアプリケーションを使用している開発者向けのワークロード。</span><span class="sxs-lookup"><span data-stu-id="92d5a-229">For example, workloads for developers who use applications that demand more computing resources.</span></span>
- <span data-ttu-id="92d5a-230">依存関係: チームデスクトップアプリ以外のインフラストラクチャ、作業負荷、その他の環境配慮への依存関係が含まれます。</span><span class="sxs-lookup"><span data-stu-id="92d5a-230">Dependencies: These include dependencies on infrastructure, workload, and other environmental considerations outside the Teams desktop app.</span></span>
- <span data-ttu-id="92d5a-231">VDI で無効になっている機能: Teams では、VDI による負荷の高い機能を無効にします。これにより、一時的な CPU 使用率の向上に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="92d5a-231">Disabled features on VDI: Teams disables GPU-intensive features for VDI, which can help improve transient CPU utilization.</span></span> <span data-ttu-id="92d5a-232">次の機能は無効になります。</span><span class="sxs-lookup"><span data-stu-id="92d5a-232">The following features are disabled:</span></span>
    - <span data-ttu-id="92d5a-233">Teams CSS アニメーション</span><span class="sxs-lookup"><span data-stu-id="92d5a-233">Teams CSS animation</span></span>
    - <span data-ttu-id="92d5a-234">Giphy 自動開始</span><span class="sxs-lookup"><span data-stu-id="92d5a-234">Giphy auto-start</span></span>

## <a name="teams-on-vdi-with-calling-and-meetings"></a><span data-ttu-id="92d5a-235">通話と会議を使った VDI 上の Teams</span><span class="sxs-lookup"><span data-stu-id="92d5a-235">Teams on VDI with calling and meetings</span></span>

<span data-ttu-id="92d5a-236">チャットと共同作業に加えて、通話と会議のサポートを備えた VDI の Teams は、Citrix ベースのプラットフォームで利用できます。</span><span class="sxs-lookup"><span data-stu-id="92d5a-236">In addition to chat and collaboration, Teams on VDI with calling and meeting support is available with Citrix-based platforms.</span></span> <span data-ttu-id="92d5a-237">サポートされている機能は、WebRTC メディアスタックと Citrix 固有の実装に基づいています。</span><span class="sxs-lookup"><span data-stu-id="92d5a-237">Supported features are based on the WebRTC media stack and Citrix-specific implementation.</span></span> <span data-ttu-id="92d5a-238">次の図は、アーキテクチャの概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="92d5a-238">The following diagram provides an overview of the architecture.</span></span>

![VDI アーキテクチャ上の Teams を示す図](media/teams-on-vdi-architecture.png)

<span data-ttu-id="92d5a-240">以下の通話および会議機能はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="92d5a-240">These calling and meeting features are not supported:</span></span>

- <span data-ttu-id="92d5a-241">緊急電話サービスの強化</span><span class="sxs-lookup"><span data-stu-id="92d5a-241">Enhanced emergency services</span></span>
- <span data-ttu-id="92d5a-242">Teams アプリとデバイス間の HID ボタンと LED コントロール</span><span class="sxs-lookup"><span data-stu-id="92d5a-242">HID buttons and LED controls between the Teams app and devices</span></span>
- <span data-ttu-id="92d5a-243">背景のぼかしと効果</span><span class="sxs-lookup"><span data-stu-id="92d5a-243">Background blur and effects</span></span>
- <span data-ttu-id="92d5a-244">ブロードキャスト/ライブイベント</span><span class="sxs-lookup"><span data-stu-id="92d5a-244">Broadcast/live events</span></span>
- <span data-ttu-id="92d5a-245">位置情報に基づくルーティング (LBR)</span><span class="sxs-lookup"><span data-stu-id="92d5a-245">Location-Based Routing (LBR)</span></span>
- <span data-ttu-id="92d5a-246">コール パーク</span><span class="sxs-lookup"><span data-stu-id="92d5a-246">Call park</span></span>
- <span data-ttu-id="92d5a-247">通話キュー</span><span class="sxs-lookup"><span data-stu-id="92d5a-247">Call queue</span></span>

> [!IMPORTANT]
> <span data-ttu-id="92d5a-248">現在、AV を最適化せずに team を VDI で実行していて、最適化のためにまだサポートされていない機能を使用している場合 (アプリの共有時に制御を許可する場合など)、[Teams] ポリシーを設定して Teams のリダイレクションを無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="92d5a-248">If you currently run Teams without AV optimization in VDI and you use features that are not supported yet for optimization (such as Give and take control when app sharing), you have to set Citrix policies to turn off Teams redirection.</span></span> <span data-ttu-id="92d5a-249">これは、Teams メディアセッションが最適化されないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="92d5a-249">This means that Teams media sessions won’t be optimized.</span></span> <span data-ttu-id="92d5a-250">Teams のリダイレクションを無効にするポリシーを設定する手順については、この[Citrix の web サイト](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/policies/reference/ica-policy-settings/multimedia-policy-settings.html)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="92d5a-250">For steps on how to set policies to turn off Teams redirection, see this [Citrix website](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/policies/reference/ica-policy-settings/multimedia-policy-settings.html).</span></span>

<span data-ttu-id="92d5a-251">現時点では、VDI 以外の環境でのみ利用可能な通話と会議機能の追加に取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="92d5a-251">We're working on adding calling and meeting features that are currently only available in non-VDI environments.</span></span> <span data-ttu-id="92d5a-252">これには、品質、追加の画面共有シナリオ、チームに最近追加された高度な機能など、より多くの管理者の制御が含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="92d5a-252">These may include more admin control over quality, additional screen sharing scenarios, and advanced features recently added to Teams.</span></span> <span data-ttu-id="92d5a-253">今後の機能の詳細については、チームの担当者にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="92d5a-253">Contact your Teams representative to learn more about upcoming features.</span></span>

### <a name="network-requirements"></a><span data-ttu-id="92d5a-254">ネットワーク要件</span><span class="sxs-lookup"><span data-stu-id="92d5a-254">Network requirements</span></span>

<span data-ttu-id="92d5a-255">クラウドの全体的な音声とビデオの展開に影響を与える可能性のあるリスクと要件を特定するために、環境を評価することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="92d5a-255">We recommend that you evaluate your environment to identify any risks and requirements that can influence your overall cloud voice and video deployment.</span></span> <span data-ttu-id="92d5a-256">[Skype For Business ネットワーク評価ツール](https://www.microsoft.com/download/details.aspx?id=53885)を使用して、自分のネットワークが Teams に対応しているかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="92d5a-256">Use the [Skype for Business Network Assessment Tool](https://www.microsoft.com/download/details.aspx?id=53885) to test whether your network is ready for Teams.</span></span>

<span data-ttu-id="92d5a-257">Teams のネットワークを準備する方法について詳しくは、「 [teams 用に組織のネットワークを準備](prepare-network.md)する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="92d5a-257">To learn more about how to prepare your network for Teams, see [Prepare your organization's network for  Teams](prepare-network.md).</span></span>

### <a name="migrate-from-skype-for-business-on-vdi-to-teams-on-vdi"></a><span data-ttu-id="92d5a-258">Vdi での Skype for Business から VDI 上の Teams への移行</span><span class="sxs-lookup"><span data-stu-id="92d5a-258">Migrate from Skype for Business on VDI to Teams on VDI</span></span>

<span data-ttu-id="92d5a-259">Vdi での Skype for Business から VDI 上の Teams への移行を行っている場合、2つのアプリケーションの違いに加えて、VDI も実装するといくつかの違いがあります。</span><span class="sxs-lookup"><span data-stu-id="92d5a-259">If you're migrating from Skype for Business on VDI to Teams on VDI, besides the differences between the two applications, there are some differences when VDI is also implemented.</span></span> <span data-ttu-id="92d5a-260">Skype for Business VDI で現在サポートされていない Teams VDI の機能には、次のような機能があります。</span><span class="sxs-lookup"><span data-stu-id="92d5a-260">Some capabilities that aren’t currently supported in Teams VDI that are in Skype for Business VDI are as follows:</span></span>

- <span data-ttu-id="92d5a-261">メディアのビットレートを制限するためのポリシーを使った VDI 通話エクスペリエンスの制御</span><span class="sxs-lookup"><span data-stu-id="92d5a-261">Control of VDI calling experiences with policies for limiting media bitrate</span></span>
- <span data-ttu-id="92d5a-262">VDI の一部の AV 機能を無効にするプラットフォームごとのポリシー</span><span class="sxs-lookup"><span data-stu-id="92d5a-262">Per-platform policy to disable some AV features in VDI</span></span>
- <span data-ttu-id="92d5a-263">アプリ共有を行うときの制御</span><span class="sxs-lookup"><span data-stu-id="92d5a-263">Give and take control when app sharing</span></span>
- <span data-ttu-id="92d5a-264">音声なしのチャットからの画面共有</span><span class="sxs-lookup"><span data-stu-id="92d5a-264">Screen share from chat without audio</span></span>
- <span data-ttu-id="92d5a-265">同時にビデオと画面共有の送受信を行うことができる</span><span class="sxs-lookup"><span data-stu-id="92d5a-265">Simultaneous video and screen sharing send and receive</span></span>

### <a name="teams-on-chrome-browser-versus-teams-desktop-app-for-vdi"></a><span data-ttu-id="92d5a-266">Chrome ブラウザーと VDI 用 Teams デスクトップアプリのチーム</span><span class="sxs-lookup"><span data-stu-id="92d5a-266">Teams on Chrome browser versus Teams desktop app for VDI</span></span>

<span data-ttu-id="92d5a-267">Chrome ブラウザーの teams では、AV の最適化を備えた VDI 用の Teams デスクトップアプリに代わる機能は提供されていません。</span><span class="sxs-lookup"><span data-stu-id="92d5a-267">Teams on Chrome browser doesn't provide a replacement for the Teams desktop app for VDI with AV optimization.</span></span> <span data-ttu-id="92d5a-268">チャットと共同作業のエクスペリエンスは期待どおりに動作します。</span><span class="sxs-lookup"><span data-stu-id="92d5a-268">The chat and collaboration experience works as expected.</span></span> <span data-ttu-id="92d5a-269">メディアが必要な場合は、Chrome ブラウザーでユーザーの期待を満たせない場合があります。</span><span class="sxs-lookup"><span data-stu-id="92d5a-269">When media is needed, there are some experiences that may not meet user expectations on the Chrome browser:</span></span>

- <span data-ttu-id="92d5a-270">オーディオとビデオのストリーミングのエクスペリエンスが最適でないことがあります。</span><span class="sxs-lookup"><span data-stu-id="92d5a-270">The audio and video streaming experience may not be optimal.</span></span> <span data-ttu-id="92d5a-271">ユーザーには、遅延または品質の低下が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="92d5a-271">Users may experiences delays or reduced quality.</span></span>
- <span data-ttu-id="92d5a-272">[デバイスの設定] は [ブラウザーの設定] では利用できません。</span><span class="sxs-lookup"><span data-stu-id="92d5a-272">Device settings aren't available in browser settings.</span></span>
- <span data-ttu-id="92d5a-273">デバイス管理はブラウザーで処理され、ブラウザーの [サイトの設定] では複数の設定が必要です。</span><span class="sxs-lookup"><span data-stu-id="92d5a-273">Device management is handled through the browser and requires multiple settings in browser site settings.</span></span>
- <span data-ttu-id="92d5a-274">デバイスの設定は、Windows デバイス管理でも設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92d5a-274">Device settings may also need to be set in Windows device management.</span></span>

## <a name="teams-on-vdi-with-chat-and-collaboration"></a><span data-ttu-id="92d5a-275">チャットと共同作業による VDI on Teams</span><span class="sxs-lookup"><span data-stu-id="92d5a-275">Teams on VDI with chat and collaboration</span></span>

<span data-ttu-id="92d5a-276">組織で Teams のチャット機能と共同作業機能のみを使用する場合は、ユーザーレベルのポリシーを設定して、Teams の呼び出しと会議の機能を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="92d5a-276">If your organization wants to only use chat and collaboration features in Teams, you can set user-level policies to turn off calling and meeting functionality in Teams.</span></span> <span data-ttu-id="92d5a-277">この機能レベルでは、Citrix 仮想アプリとデスクトップは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="92d5a-277">This feature level doesn't require Citrix Virtual Apps and Desktops.</span></span>

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a><span data-ttu-id="92d5a-278">通話と会議の機能を無効にするポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="92d5a-278">Set policies to turn off calling and meeting functionality</span></span>

<span data-ttu-id="92d5a-279">ポリシーを設定するには、Microsoft Teams 管理センターまたは PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="92d5a-279">You can set policies by using the Microsoft Teams admin center or PowerShell.</span></span> <span data-ttu-id="92d5a-280">ポリシーの変更が反映されるまでには、多少時間がかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="92d5a-280">It can take some time (a few hours) for the policy changes to propagate.</span></span> <span data-ttu-id="92d5a-281">特定のアカウントの変更がすぐに表示されない場合は、数時間後にもう一度お試しください。</span><span class="sxs-lookup"><span data-stu-id="92d5a-281">If you don’t see changes for a given account immediately, try again in a few hours.</span></span>

<span data-ttu-id="92d5a-282">[**通話ポリシー**](teams-calling-policy.md): Teams には組み込みの DisallowCalling 通話ポリシーが含まれており、すべての通話機能がオフになっています。</span><span class="sxs-lookup"><span data-stu-id="92d5a-282">[**Calling polices**](teams-calling-policy.md): Teams includes the built-in DisallowCalling calling policy, in which all calling features are turned off.</span></span> <span data-ttu-id="92d5a-283">仮想化された環境で Teams を使用する組織内のすべてのユーザーに DisallowCalling ポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="92d5a-283">Assign the DisallowCalling policy to all users in your organization who use Teams in a virtualized environment.</span></span>

<span data-ttu-id="92d5a-284">[**会議ポリシー**](meeting-policies-in-teams.md): Teams には、すべての会議機能がオフになっている組み込みの "いいね!" の会議ポリシーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="92d5a-284">[**Meeting policies**](meeting-policies-in-teams.md): Teams includes the built-in AllOff meeting policy, in which all meeting features are turned off.</span></span> <span data-ttu-id="92d5a-285">仮想化された環境で Teams を使用する組織内のすべてのユーザーに対して、割り当てられた Ff ポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="92d5a-285">Assign the AllOff policy to all users in your organization who use Teams in a virtualized environment.</span></span>

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a><span data-ttu-id="92d5a-286">Microsoft Teams 管理センターを使用してポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="92d5a-286">Assign policies using the Microsoft Teams admin center</span></span>

<span data-ttu-id="92d5a-287">DisallowCalling の通話ポリシーと、割り当てられているユーザーに割り当てることができる会議ポリシーを割り当てるには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="92d5a-287">To assign the DisallowCalling calling policy and the AllOff meeting policy to users, follow these steps:</span></span>

1. <span data-ttu-id="92d5a-288">Microsoft Teams 管理センターの左のナビゲーションで、[**ユーザー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="92d5a-288">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="92d5a-289">ユーザー名の左側をクリックしてユーザーを選び、[**設定の編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="92d5a-289">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="92d5a-290">次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="92d5a-290">Do the following:</span></span>
    1.  <span data-ttu-id="92d5a-291">[**通話ポリシー**] で [ **DisallowCalling**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="92d5a-291">Under **Calling policy**, click **DisallowCalling**.</span></span>
    2.  <span data-ttu-id="92d5a-292">[**会議のポリシー**] で、[割り当てる]**をクリックし**ます。</span><span class="sxs-lookup"><span data-stu-id="92d5a-292">Under **Meeting policy**, click **AllOff**.</span></span>
4. <span data-ttu-id="92d5a-293">[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="92d5a-293">Click **Apply**.</span></span>

<span data-ttu-id="92d5a-294">一度に複数のユーザーにポリシーを割り当てるには、「[チームのユーザー設定を一括](edit-user-settings-in-bulk.md)して編集する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="92d5a-294">To assign a policy to multiple users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="92d5a-295">または、次の操作も行うことができます。</span><span class="sxs-lookup"><span data-stu-id="92d5a-295">Or, you can also do the following:</span></span>

1. <span data-ttu-id="92d5a-296">Microsoft Teams 管理センターの左のナビゲーションで、割り当てるポリシーに移動します。</span><span class="sxs-lookup"><span data-stu-id="92d5a-296">In the left navigation of the Microsoft Teams admin center, go to the policy you want to assign.</span></span> <span data-ttu-id="92d5a-297">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="92d5a-297">For example:</span></span>
    - <span data-ttu-id="92d5a-298">[**音声** > **通話のポリシー**] に移動し、[ **DisallowCalling**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="92d5a-298">Go to **Voice** > **Calling policies**, and then click **DisallowCalling**.</span></span>
    - <span data-ttu-id="92d5a-299">[**会議** > の**ポリシー**] に移動して、[割り当てる**ff**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="92d5a-299">Go to **Meetings** > **Meeting policies**, and then click **AllOff**.</span></span>
3. <span data-ttu-id="92d5a-300">[**ユーザーの管理**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="92d5a-300">Select **Manage users**.</span></span>
4. <span data-ttu-id="92d5a-301">[**ユーザーの管理**] ウィンドウで、[表示名] または [ユーザー名] でユーザーを検索し、名前を選択して [**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="92d5a-301">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="92d5a-302">追加するユーザーごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="92d5a-302">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="92d5a-303">ユーザーの追加が完了したら、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="92d5a-303">When you're finished adding users, click **Save**.</span></span>

#### <a name="assign-policies-using-powershell"></a><span data-ttu-id="92d5a-304">PowerShell を使用してポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="92d5a-304">Assign policies using PowerShell</span></span>

<span data-ttu-id="92d5a-305">次の例は、 [Grant-CsteamDisallowCalling のポリシー](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy)を使って、ユーザーにの呼び出しポリシーを割り当てる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="92d5a-305">The following example shows how to use the [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) to assign the DisallowCalling calling policy to a user.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity “user email id”
```

<span data-ttu-id="92d5a-306">PowerShell を使用して通話ポリシーを管理する方法の詳細については、「 [Set-Csteam拡張性のポリシー](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="92d5a-306">To learn more about using PowerShell to manage calling policies, see [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).</span></span>

<span data-ttu-id="92d5a-307">次の例は、CsTeamsMeetingPolicy を使用して、[グラント](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy)ff 会議ポリシーをユーザーに割り当てる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="92d5a-307">The following example shows how to use the [Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) to assign the AllOff meeting policy to a user.</span></span>

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity “user email id”
```

<span data-ttu-id="92d5a-308">PowerShell を使用して会議のポリシーを管理する方法の詳細については、「 [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="92d5a-308">To learn more about using PowerShell to manage meeting policies, see [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>

## <a name="migrate-teams-on-vdi-with-chat-and-collaboration-to-citrix-with-calling-and-meetings"></a><span data-ttu-id="92d5a-309">通話と会議を使って、VDI 上のチームをチャットとコラボレーションで Citrix に移行する</span><span class="sxs-lookup"><span data-stu-id="92d5a-309">Migrate Teams on VDI with chat and collaboration to Citrix with calling and meetings</span></span>

<span data-ttu-id="92d5a-310">ユーザーレベルのポリシーを設定して、通話と会議機能を無効にしている場合に、チャットと共同作業を行っている VDI 上の Teams の既存の実装がある場合、AV 最適化を有効にして Citrix に移行するには、ポリシーを設定する必要があります。VDI ユーザー向けのチームの会議機能。</span><span class="sxs-lookup"><span data-stu-id="92d5a-310">If you have an existing implementation of Teams on VDI with chat and collaboration in which you had set user-level policies to turn off calling and meeting functionality, and you're migrating to Citrix with AV optimization, you must set policies to turn on calling and meeting functionality for those Teams on VDI users.</span></span>

### <a name="set-policies-to-turn-on-calling-and-meeting-functionality"></a><span data-ttu-id="92d5a-311">通話と会議の機能を有効にするポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="92d5a-311">Set policies to turn on calling and meeting functionality</span></span>

<span data-ttu-id="92d5a-312">Microsoft Teams 管理センターまたは PowerShell を使用して、通話と会議のポリシーを設定し、ユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="92d5a-312">You can use the Microsoft Teams admin center or PowerShell to set and assign calling and meeting policies to your users.</span></span> <span data-ttu-id="92d5a-313">ポリシーの変更が反映されるまでには、多少時間がかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="92d5a-313">It can take some time (a few hours) for policy changes to propagate.</span></span> <span data-ttu-id="92d5a-314">特定のアカウントの変更がすぐに表示されない場合は、数時間後にもう一度お試しください。</span><span class="sxs-lookup"><span data-stu-id="92d5a-314">If you don’t see changes for a given account immediately, try again after a few hours.</span></span>

<span data-ttu-id="92d5a-315">[**通話**](teams-calling-policy.md)ポリシー: Teams の通話ポリシーは、ユーザーが使用できる通話機能を制御します。</span><span class="sxs-lookup"><span data-stu-id="92d5a-315">[**Calling polices**](teams-calling-policy.md): Calling policies in Teams control which calling features are available to users.</span></span> <span data-ttu-id="92d5a-316">Teams には、組み込みの AllowCalling 通話ポリシーが含まれており、すべての通話機能が有効になっています。</span><span class="sxs-lookup"><span data-stu-id="92d5a-316">Teams includes the built-in AllowCalling calling policy, in which all calling features are turned on.</span></span> <span data-ttu-id="92d5a-317">すべての通話機能を有効にするには、AllowCalling ポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="92d5a-317">To turn on all calling features, assign the AllowCalling policy.</span></span> <span data-ttu-id="92d5a-318">または、カスタム通話ポリシーを作成して、必要な通話機能を有効にし、ユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="92d5a-318">Or, create a custom calling policy to turn on the calling features that you want and assign it to users.</span></span> 

<span data-ttu-id="92d5a-319">[**会議ポリシー**](meeting-policies-in-teams.md): Teams の会議ポリシーは、ユーザーが作成できる会議の種類と、組織内のユーザーによってスケジュールされている会議の参加者が使用できる機能を制御します。</span><span class="sxs-lookup"><span data-stu-id="92d5a-319">[**Meeting policies**](meeting-policies-in-teams.md): Meeting policies in Teams control the types of meetings that users can create and the features that are available to meeting participants that are scheduled by users in your organization.</span></span> <span data-ttu-id="92d5a-320">Teams には、すべての会議機能が有効になっている組み込みのすべての会議のポリシーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="92d5a-320">Teams includes the built-in AllOn meeting policy, in which all meeting features are turned on.</span></span> <span data-ttu-id="92d5a-321">すべての会議機能を有効にするには、[すべて] のポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="92d5a-321">To turn on all meeting features, assign the AllOn policy.</span></span> <span data-ttu-id="92d5a-322">または、カスタム会議ポリシーを作成して、必要な会議機能を有効にし、ユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="92d5a-322">Or, create a custom meeting policy to turn on the meeting features that you want and assign it users.</span></span>

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a><span data-ttu-id="92d5a-323">Microsoft Teams 管理センターを使用してポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="92d5a-323">Assign policies using the Microsoft Teams admin center</span></span>

<span data-ttu-id="92d5a-324">AllowCalling の通話ポリシーと [すべての会議] ポリシーをユーザーに割り当てるには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="92d5a-324">To assign the AllowCalling calling policy and the AllOn meeting policy to users, follow these steps:</span></span>

1. <span data-ttu-id="92d5a-325">Microsoft Teams 管理センターの左のナビゲーションで、[**ユーザー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="92d5a-325">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="92d5a-326">ユーザー名の左側をクリックしてユーザーを選び、[**設定の編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="92d5a-326">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="92d5a-327">次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="92d5a-327">Do the following:</span></span>
    1.  <span data-ttu-id="92d5a-328">[**通話ポリシー**] で [ **allowcalling**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="92d5a-328">Under **Calling policy**, click **AllowCalling**.</span></span>
    2.  <span data-ttu-id="92d5a-329">[**会議のポリシー**] で [**すべて**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="92d5a-329">Under **Meeting policy**, click **AllOn**.</span></span>
4. <span data-ttu-id="92d5a-330">[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="92d5a-330">Click **Apply**.</span></span>

<span data-ttu-id="92d5a-331">一度に複数のユーザーにポリシーを割り当てるには、「[チームのユーザー設定を一括](edit-user-settings-in-bulk.md)して編集する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="92d5a-331">To assign a policy to multiple users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="92d5a-332">または、次の操作も行うことができます。</span><span class="sxs-lookup"><span data-stu-id="92d5a-332">Or, you can also do the following:</span></span>

1. <span data-ttu-id="92d5a-333">Microsoft Teams 管理センターの左のナビゲーションで、割り当てるポリシーに移動します。</span><span class="sxs-lookup"><span data-stu-id="92d5a-333">In the left navigation of the Microsoft Teams admin center, go to the policy you want to assign.</span></span> <span data-ttu-id="92d5a-334">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="92d5a-334">For example:</span></span>
    - <span data-ttu-id="92d5a-335">[**音声** > **通話のポリシー**] に移動し、[ **allowcalling**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="92d5a-335">Go to **Voice** > **Calling policies**, and then click **AllowCalling**.</span></span>
    - <span data-ttu-id="92d5a-336">[**会議** > の**ポリシー**] に移動し、[**すべて**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="92d5a-336">Go to **Meetings** > **Meeting policies**, and then click **AllOn**.</span></span>
3. <span data-ttu-id="92d5a-337">[**ユーザーの管理**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="92d5a-337">Select **Manage users**.</span></span>
4. <span data-ttu-id="92d5a-338">[**ユーザーの管理**] ウィンドウで、[表示名] または [ユーザー名] でユーザーを検索し、名前を選択して [**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="92d5a-338">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="92d5a-339">追加するユーザーごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="92d5a-339">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="92d5a-340">ユーザーの追加が完了したら、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="92d5a-340">When you're finished adding users, click **Save**.</span></span>

#### <a name="assign-policies-using-powershell"></a><span data-ttu-id="92d5a-341">PowerShell を使用してポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="92d5a-341">Assign policies using PowerShell</span></span>

<span data-ttu-id="92d5a-342">次の例は、 [Grant-Csteam分解のポリシー](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy)を使って、allowcalling 呼び出しポリシーをユーザーに割り当てる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="92d5a-342">The following example shows how to use the [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) to assign the AllowCalling calling policy to a user.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName AllowCalling -Identity “user email id”
```

<span data-ttu-id="92d5a-343">PowerShell を使用して通話ポリシーを管理する方法の詳細については、「 [Set-Csteam拡張性のポリシー](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="92d5a-343">To learn more about using PowerShell to manage calling policies, see [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).</span></span>

<span data-ttu-id="92d5a-344">次の例は、 [CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy)を使用して、すべての会議ポリシーをユーザーに割り当てる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="92d5a-344">The following example shows how to use the [Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) to assign the AllOn meeting policy to a user.</span></span>

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOn -Identity “user email id”
```

<span data-ttu-id="92d5a-345">PowerShell を使用して会議のポリシーを管理する方法の詳細については、「 [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="92d5a-345">To learn more about using PowerShell to manage meeting policies, see [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>

## <a name="known-issues-and-limitations"></a><span data-ttu-id="92d5a-346">既知の問題と制限事項</span><span class="sxs-lookup"><span data-stu-id="92d5a-346">Known issues and limitations</span></span>

### <a name="client-deployment-installation-and-setup"></a><span data-ttu-id="92d5a-347">クライアントの展開、インストール、セットアップ</span><span class="sxs-lookup"><span data-stu-id="92d5a-347">Client deployment, installation, and setup</span></span>

- <span data-ttu-id="92d5a-348">コンピューターごとにインストールする場合、vdi の Teams は非 VDI Teams クライアントとして自動的に更新されることはありません。</span><span class="sxs-lookup"><span data-stu-id="92d5a-348">With per-machine installation, Teams on VDI isn't automatically updated in the way that non-VDI Teams clients are.</span></span> <span data-ttu-id="92d5a-349">「 [VDI 上の Teams デスクトップアプリをインストールまたは更新](#install-or-update-the-teams-desktop-app-on-vdi)する」セクションで説明されているように、新しい MSI をインストールして VM イメージを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92d5a-349">You have to update the VM image by installing a new MSI as described in the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.</span></span> <span data-ttu-id="92d5a-350">最新バージョンに更新するには、現在のバージョンをアンインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="92d5a-350">You must uninstall the current version to update to a newer version.</span></span>
- <span data-ttu-id="92d5a-351">チームは、ユーザーごとまたはコンピューターごとに展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92d5a-351">Teams should be deployed either per user or per machine.</span></span> <span data-ttu-id="92d5a-352">同時ユーザー数とコンピューター単位のチームの展開はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="92d5a-352">Deployment of Teams for concurrent per user and per machine is not supported.</span></span>  <span data-ttu-id="92d5a-353">コンピューターごとまたはユーザーごとに、これらのモードのいずれかに移行するには、アンインストール手順に従い、どちらかのモードに再展開します。</span><span class="sxs-lookup"><span data-stu-id="92d5a-353">To migrate from either per machine or per user to one of these modes, follow the uninstall procedure and redeploy to either mode.</span></span>
- <span data-ttu-id="92d5a-354">現時点では、MacOs および Linux ベースのクライアントは Citrix でサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="92d5a-354">MacOs and Linux-based clients are not supported by Citrix at this time.</span></span>
- <span data-ttu-id="92d5a-355">Citrix は、エンドポイントで定義された明示的な HTTP プロキシの使用をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="92d5a-355">Citrix doesn't support the use of explicit HTTP proxies defined on an endpoint.</span></span> 

### <a name="calling-and-meetings"></a><span data-ttu-id="92d5a-356">通話と会議</span><span class="sxs-lookup"><span data-stu-id="92d5a-356">Calling and meetings</span></span>

- <span data-ttu-id="92d5a-357">Skype for Business の相互運用性は音声通話に限定され、ビデオ表示には使用できません。</span><span class="sxs-lookup"><span data-stu-id="92d5a-357">Interoperability with Skype for Business is limited to audio calls, no video modality.</span></span>
- <span data-ttu-id="92d5a-358">デュアルトーンマルチ周波数 (DTMF) テレフォニーシステムとの相互操作は、現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="92d5a-358">Dual Tone Multi Frequency (DTMF) interaction with telephony systems  is currently not supported.</span></span>
- <span data-ttu-id="92d5a-359">匿名ユーザーとして Teams 会議に参加することは、AV-最適化されていません。</span><span class="sxs-lookup"><span data-stu-id="92d5a-359">Joining Teams meetings as an anonymous user isn't AV-optimized.</span></span> <span data-ttu-id="92d5a-360">ユーザーは会議に参加し、最適化されていない操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="92d5a-360">The user can join the meeting and have a non-optimized experience.</span></span>
- <span data-ttu-id="92d5a-361">会議またはグループ通話でサポートされているビデオストリームは1つだけです。</span><span class="sxs-lookup"><span data-stu-id="92d5a-361">Only a single incoming video stream is supported in meetings or group calls.</span></span> <span data-ttu-id="92d5a-362">複数のユーザーがビデオを送信する場合、常に表示されている主要なスピーカーのビデオのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="92d5a-362">When multiple people send video, only the dominant speaker's video is shown at any given time.</span></span>  
- <span data-ttu-id="92d5a-363">着信と発信のビデオストリームの解像度は720p の解像度に制限されています。</span><span class="sxs-lookup"><span data-stu-id="92d5a-363">Incoming and outgoing video stream resolution is limited to 720p resolution.</span></span> <span data-ttu-id="92d5a-364">これは WebRTC の制限です。</span><span class="sxs-lookup"><span data-stu-id="92d5a-364">This is a WebRTC limitation.</span></span>
- <span data-ttu-id="92d5a-365">着信カメラまたは画面共有ストリームのビデオストリームは1つだけです。</span><span class="sxs-lookup"><span data-stu-id="92d5a-365">Only one video stream from an incoming camera or screen share stream is supported.</span></span> <span data-ttu-id="92d5a-366">受信画面共有が表示されている場合は、その画面共有が、優先スピーカーのビデオではなく、画面上に表示されます。</span><span class="sxs-lookup"><span data-stu-id="92d5a-366">When there's an incoming screen share, that screen share is shown it instead of the video of the dominant speaker.</span></span>
- <span data-ttu-id="92d5a-367">送信画面の共有:</span><span class="sxs-lookup"><span data-stu-id="92d5a-367">Outgoing screen sharing:</span></span>
    - <span data-ttu-id="92d5a-368">アプリケーション共有はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="92d5a-368">Application sharing is not supported.</span></span>
- <span data-ttu-id="92d5a-369">コントロールを用意して制御します。</span><span class="sxs-lookup"><span data-stu-id="92d5a-369">Give control and take control:</span></span>  
    - <span data-ttu-id="92d5a-370">画面共有またはアプリケーション共有セッション中はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="92d5a-370">Not supported during a screen sharing or application sharing session.</span></span>
    - <span data-ttu-id="92d5a-371">PowerPoint 共有セッション中にサポートされます。</span><span class="sxs-lookup"><span data-stu-id="92d5a-371">Supported during a PowerPoint sharing session.</span></span>
- <span data-ttu-id="92d5a-372">マルチモニターのセットアップで画面共有を行う場合、メインモニターのみが共有されます。</span><span class="sxs-lookup"><span data-stu-id="92d5a-372">When screen sharing in a multi-monitor setup, only the main monitor is shared.</span></span>
- <span data-ttu-id="92d5a-373">CWA での高 DPI スケーリングはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="92d5a-373">High DPI scaling on CWA is not supported.</span></span>

<span data-ttu-id="92d5a-374">VDI に関連していない Teams の既知の問題については、「 [teams の既知の問題](Known-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="92d5a-374">For Teams known issues that aren’t related to VDI, see [Known issues for Teams](Known-issues.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="92d5a-375">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="92d5a-375">Troubleshooting</span></span>

#### <a name="troubleshoot-citrix-components"></a><span data-ttu-id="92d5a-376">Citrix コンポーネントのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="92d5a-376">Troubleshoot Citrix components</span></span>

<span data-ttu-id="92d5a-377">VDA と CWA の問題を解決する方法については、[この Citrix の web サイト](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="92d5a-377">For information on how to troubleshoot VDA and CWA issues, see [this Citrix website](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html).</span></span>

## <a name="related-topics"></a><span data-ttu-id="92d5a-378">関連項目</span><span class="sxs-lookup"><span data-stu-id="92d5a-378">Related topics</span></span>

- [<span data-ttu-id="92d5a-379">MSI を使用して Microsoft Teams をインストールする</span><span class="sxs-lookup"><span data-stu-id="92d5a-379">Install Microsoft Teams using MSI</span></span>](msi-deployment.md)
- [<span data-ttu-id="92d5a-380">Teams での PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="92d5a-380">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
