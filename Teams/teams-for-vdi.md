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
ms.openlocfilehash: f9c8f0fe24cfb94be368fb2afa6446f311f2f790
ms.sourcegitcommit: 5fbb57c5f0692afcb8e65516c63b96814f51ca65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2020
ms.locfileid: "42417882"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a><span data-ttu-id="232c3-103">仮想デスクトップ インフラストラクチャ用の Teams</span><span class="sxs-lookup"><span data-stu-id="232c3-103">Teams for Virtualized Desktop Infrastructure</span></span>

<span data-ttu-id="232c3-104">この記事では、仮想化された環境で Microsoft Teams を使用する場合の要件と制限について説明します。</span><span class="sxs-lookup"><span data-stu-id="232c3-104">This article describes the requirements and limitations for using Microsoft Teams in a virtualized environment.</span></span>

## <a name="what-is-vdi"></a><span data-ttu-id="232c3-105">VDI とは</span><span class="sxs-lookup"><span data-stu-id="232c3-105">What is VDI?</span></span>

<span data-ttu-id="232c3-106">仮想デスクトップインフラストラクチャ (VDI) は、デスクトップオペレーティングシステムと、データセンターの中央サーバー上のアプリケーションをホストする仮想化テクノロジです。</span><span class="sxs-lookup"><span data-stu-id="232c3-106">Virtual Desktop Infrastructure (VDI) is virtualization technology that hosts a desktop operating system and applications on a centralized server in a data center.</span></span> <span data-ttu-id="232c3-107">これにより、完全にセキュリティが設定された一元的な中央集中ソースを持つユーザーに、完全にカスタマイズされたデスクトップエクスペリエンスを提供できます。</span><span class="sxs-lookup"><span data-stu-id="232c3-107">This enables a fully personalized desktop experience to users with a fully secured and compliant centralized source.</span></span>
 
<span data-ttu-id="232c3-108">仮想環境での Microsoft Teams はチャットと共同作業をサポートしており、Citrix プラットフォームでは、通話と会議機能もサポートされています。</span><span class="sxs-lookup"><span data-stu-id="232c3-108">Microsoft Teams in a virtualized environment supports chat and collaboration, and with the Citrix platform, calling and meeting functionality are also supported.</span></span>

<span data-ttu-id="232c3-109">仮想環境の Teams では、複数の構成がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="232c3-109">Teams in a virtualized environment supports multiple configurations.</span></span> <span data-ttu-id="232c3-110">これには、VDI、専用、共有、常設、非永続的モードが含まれます。</span><span class="sxs-lookup"><span data-stu-id="232c3-110">These include VDI, dedicated, shared, persistent and non-persistent modes.</span></span> <span data-ttu-id="232c3-111">機能は継続的な開発中であり、定期的に追加されており、今後数ヶ月にわたって機能が拡張されます。</span><span class="sxs-lookup"><span data-stu-id="232c3-111">Features are in continuous development and are added on a regular basis, and functionality will expand in the coming months and years.</span></span>
 
<span data-ttu-id="232c3-112">仮想環境で Teams を使用する場合は、仮想化されていない環境での Teams の使用とは多少異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="232c3-112">Using Teams in a virtualized environment may be somewhat different from using Teams in a non-virtualized environment.</span></span> <span data-ttu-id="232c3-113">たとえば、一部の高度な機能は仮想化された環境では使用できず、ビデオ解像度が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="232c3-113">For example, some advanced features may not be available in a virtualized environment and video resolution may differ.</span></span> <span data-ttu-id="232c3-114">最適なユーザーエクスペリエンスを実現するには、この記事のガイダンスに従ってください。</span><span class="sxs-lookup"><span data-stu-id="232c3-114">To ensure an optimal user experience, follow the guidance in this article.</span></span>

## <a name="teams-on-vdi-components"></a><span data-ttu-id="232c3-115">VDI コンポーネントの Teams</span><span class="sxs-lookup"><span data-stu-id="232c3-115">Teams on VDI components</span></span>

<span data-ttu-id="232c3-116">仮想環境で Teams を使用するには、次のコンポーネントが必要です。</span><span class="sxs-lookup"><span data-stu-id="232c3-116">Using Teams in a virtualized environment requires the following components.</span></span>

- <span data-ttu-id="232c3-117">**仮想ブローカー**: Azure などの仮想化プロバイダーへのリソースと接続マネージャー</span><span class="sxs-lookup"><span data-stu-id="232c3-117">**Virtualization broker**: The resource and connection manager to the virtualization provider, such as Azure</span></span>
- <span data-ttu-id="232c3-118">**仮想デスクトップ**: Microsoft Teams を実行する仮想マシン (VM) スタック</span><span class="sxs-lookup"><span data-stu-id="232c3-118">**Virtual desktop**: The Virtual Machine (VM) stack that runs Microsoft Teams</span></span>
- <span data-ttu-id="232c3-119">**シンクライアント**: ユーザーが物理的にインターフェイスを使用するエンドポイント</span><span class="sxs-lookup"><span data-stu-id="232c3-119">**Thin client**: The endpoint that the user physically interfaces with</span></span>
- <span data-ttu-id="232c3-120">**Teams デスクトップアプリ**: これは teams デスクトップクライアントアプリです</span><span class="sxs-lookup"><span data-stu-id="232c3-120">**Teams desktop app**: This is the Teams desktop client app</span></span>

## <a name="teams-on-vdi-requirements"></a><span data-ttu-id="232c3-121">VDI の要件に関するチーム</span><span class="sxs-lookup"><span data-stu-id="232c3-121">Teams on VDI requirements</span></span>

### <a name="virtualization-provider-requirements"></a><span data-ttu-id="232c3-122">仮想化プロバイダーの要件</span><span class="sxs-lookup"><span data-stu-id="232c3-122">Virtualization provider requirements</span></span>

<span data-ttu-id="232c3-123">Teams デスクトップアプリは、主要な仮想化ソリューションプロバイダーと共に検証されました。</span><span class="sxs-lookup"><span data-stu-id="232c3-123">The Teams desktop app was validated with leading virtualization solution providers.</span></span> <span data-ttu-id="232c3-124">市場プロバイダーが複数ある場合は、最小要件が満たされるように仮想化ソリューションプロバイダーに問い合わせることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="232c3-124">With multiple market providers, we recommend that you consult your virtualization solution provider to ensure minimum requirements are met.</span></span>
  
<span data-ttu-id="232c3-125">現時点では、音声/ビデオ (AV) 最適化による VDI 上の Teams は、Citrix で認定されています。</span><span class="sxs-lookup"><span data-stu-id="232c3-125">Currently, Teams on VDI with audio/video (AV) optimization is certified with Citrix.</span></span> <span data-ttu-id="232c3-126">このセクションの情報を確認して、Citrix と Teams の両方の要件が適切に機能するようになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="232c3-126">Review the information in this section to ensure both Citrix and Teams requirements are met for proper functionality.</span></span>

### <a name="partners-certified-for-teams"></a><span data-ttu-id="232c3-127">チームの認定パートナー</span><span class="sxs-lookup"><span data-stu-id="232c3-127">Partners certified for Teams</span></span>

<span data-ttu-id="232c3-128">次のパートナーには、Teams の仮想デスクトップインフラストラクチャソリューションがあります。</span><span class="sxs-lookup"><span data-stu-id="232c3-128">The following partners have virtual desktop infrastructure solutions for Teams.</span></span>

|<span data-ttu-id="232c3-129">パートナー</span><span class="sxs-lookup"><span data-stu-id="232c3-129">Partner</span></span>|<span data-ttu-id="232c3-130">パートナー ソリューション</span><span class="sxs-lookup"><span data-stu-id="232c3-130">Partner solution</span></span>|
|----|---|
|![Citrix を表すロゴ](media/citrix.png)| <span data-ttu-id="232c3-132"><a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix の仮想アプリとデスクトップ</a></span><span class="sxs-lookup"><span data-stu-id="232c3-132"><a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix Virtual Apps and Desktops</a></span></span> |

### <a name="citrix-virtual-apps-and-desktops-requirements"></a><span data-ttu-id="232c3-133">Citrix の仮想アプリとデスクトップの要件</span><span class="sxs-lookup"><span data-stu-id="232c3-133">Citrix Virtual Apps and Desktops requirements</span></span>

<span data-ttu-id="232c3-134">Citrix の仮想アプリとデスクトップ (以前は XenApp と XenDesktop) は、VDI 上の Teams で AV の最適化を実現します。</span><span class="sxs-lookup"><span data-stu-id="232c3-134">Citrix Virtual Apps and Desktops (formerly known as XenApp and XenDesktop) provides AV optimization for Teams on VDI.</span></span> <span data-ttu-id="232c3-135">Citrix の仮想アプリとデスクトップを使用すると、VDI 上の Teams では、チャットや共同作業に加えて、通話と会議機能がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="232c3-135">With Citrix Virtual Apps and Desktops, Teams on VDI supports calling and meeting functionality in addition to chat and collaboration.</span></span>

<span data-ttu-id="232c3-136">[このページで](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/)は、Citrix の仮想アプリとデスクトップの最新バージョンをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="232c3-136">You can download the latest version of Citrix Virtual Apps and Desktops [here](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/).</span></span> <span data-ttu-id="232c3-137">(最初にサインインする必要があります。)必要なコンポーネントは、既定で[Citrix Workspace アプリ (CWA)](https://www.citrix.com/downloads/workspace-app/)と仮想配信エージェント (VDA) にまとめられています。</span><span class="sxs-lookup"><span data-stu-id="232c3-137">(You'll need to sign in first.) The necessary components are bundled into the [Citrix Workspace app (CWA)](https://www.citrix.com/downloads/workspace-app/) and Virtual Delivery Agent (VDA) by default.</span></span> <span data-ttu-id="232c3-138">CWA または VDA に追加のコンポーネントまたはプラグインをインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="232c3-138">You don't need to install any additional components or plugins on CWA or the VDA.</span></span>

<span data-ttu-id="232c3-139">最新のサーバーとクライアントの要件については、[この Citrix の web サイト](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="232c3-139">For the latest server and client requirements, see [this Citrix website](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html).</span></span>

## <a name="install-or-update-the-teams-desktop-app-on-vdi"></a><span data-ttu-id="232c3-140">VDI で Teams デスクトップアプリをインストールまたは更新する</span><span class="sxs-lookup"><span data-stu-id="232c3-140">Install or update the Teams desktop app on VDI</span></span>

<span data-ttu-id="232c3-141">MSI パッケージを使用してコンピューターごとのインストールまたはユーザーごとのインストールを使用して、VDI 用の Teams デスクトップアプリを展開することができます。</span><span class="sxs-lookup"><span data-stu-id="232c3-141">You can deploy the Teams desktop app for VDI using a per-machine installation or per-user installation using the MSI package.</span></span> <span data-ttu-id="232c3-142">使用する方法を決定するのは、永続的なセットアップと非永続的な設定のどちらを使用するか、または組織に関連する機能のニーズによって異なります。</span><span class="sxs-lookup"><span data-stu-id="232c3-142">Deciding on which approach to use depends on whether you use a persistent or non-persistent setup and the associated functionality needs of your organization.</span></span>
<span data-ttu-id="232c3-143">専用の永続的なセットアップの場合、どちらのアプローチも機能します。</span><span class="sxs-lookup"><span data-stu-id="232c3-143">For a dedicated persistent setup, either approach would work.</span></span>  <span data-ttu-id="232c3-144">ただし、非永続的なセットアップでは、チームが効率的に作業するために、コンピューターごとにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="232c3-144">However, for a non-persistent setup, per-machine installation is required for Teams to work efficiently.</span></span> <span data-ttu-id="232c3-145">「[非永続的なセットアップ](#non-persistent-setup)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="232c3-145">See the [Non-persistent setup](#non-persistent-setup) section.</span></span>

<span data-ttu-id="232c3-146">コンピューター単位のインストールでは、自動更新が無効になっています。</span><span class="sxs-lookup"><span data-stu-id="232c3-146">With per-machine installation, automatic updates is disabled.</span></span> <span data-ttu-id="232c3-147">つまり、Teams アプリを更新するには、現在のバージョンをアンインストールして、新しいバージョンに更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="232c3-147">This means that to update the Teams app, you must uninstall the current version to update to a newer version.</span></span> <span data-ttu-id="232c3-148">ユーザーごとのインストールでは、自動更新が有効になっています。</span><span class="sxs-lookup"><span data-stu-id="232c3-148">With per-user installation, automatic updates is enabled.</span></span> <span data-ttu-id="232c3-149">ほとんどの VDI の展開では、コンピューターごとのインストールを使用してチームを展開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="232c3-149">For most VDI deployments, we recommend you deploy Teams using per-machine installation.</span></span>

<span data-ttu-id="232c3-150">最新のチームバージョンに更新するには、まずアンインストール手順を実行し、次に最新のチームバージョン展開を実行します。</span><span class="sxs-lookup"><span data-stu-id="232c3-150">To update to the latest Teams version, start with the uninstall procedure followed by latest Teams version deployment.</span></span>

<span data-ttu-id="232c3-151">VDI 環境での Teams の AV 最適化を適切に機能させるには、シンクライアントエンドポイントがインターネットにアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="232c3-151">For Teams AV optimization in VDI environments to work properly, the thin client endpoint must have access to the internet.</span></span> <span data-ttu-id="232c3-152">インターネットアクセスがシンクライアントエンドポイントで利用できない場合、最適化の起動は成功しません。</span><span class="sxs-lookup"><span data-stu-id="232c3-152">If internet access isn't available at the thin client endpoint, optimization startup won't be successful.</span></span> <span data-ttu-id="232c3-153">これは、ユーザーが最適化されていないメディアの状態であることを意味します。</span><span class="sxs-lookup"><span data-stu-id="232c3-153">This means that the user is in a non-optimized media state.</span></span>

#### <a name="dedicated-persistent-setup"></a><span data-ttu-id="232c3-154">専用の永続的なセットアップ</span><span class="sxs-lookup"><span data-stu-id="232c3-154">Dedicated persistent setup</span></span>

<span data-ttu-id="232c3-155">専用の永続的なセットアップでは、ユーザーのローカルオペレーティングシステムに対する変更は、ユーザーがログオフした後も保持されます。</span><span class="sxs-lookup"><span data-stu-id="232c3-155">In a dedicated persistent setup, users' local operating system changes are retained after users log off.</span></span>  <span data-ttu-id="232c3-156">永続的なセットアップの場合、Teams はユーザーごととコンピューターごとの両方のインストールをサポートします。</span><span class="sxs-lookup"><span data-stu-id="232c3-156">For persistent setup, Teams support both per-user and per-machine installation.</span></span>

<span data-ttu-id="232c3-157">推奨される最小の VM 構成は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="232c3-157">The following is the recommended minimum VM configuration.</span></span>

|<span data-ttu-id="232c3-158">パラメーター</span><span class="sxs-lookup"><span data-stu-id="232c3-158">Parameter</span></span>  |<span data-ttu-id="232c3-159">ワークステーションオペレーティングシステム</span><span class="sxs-lookup"><span data-stu-id="232c3-159">Workstation operating system</span></span>  |<span data-ttu-id="232c3-160">サーバー操作システム</span><span class="sxs-lookup"><span data-stu-id="232c3-160">Server operation system</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="232c3-161">vCPU</span><span class="sxs-lookup"><span data-stu-id="232c3-161">vCPU</span></span>   |    <span data-ttu-id="232c3-162">2コア</span><span class="sxs-lookup"><span data-stu-id="232c3-162">2 cores</span></span>     |  <span data-ttu-id="232c3-163">4、6、または8</span><span class="sxs-lookup"><span data-stu-id="232c3-163">4,6, or 8</span></span><br><span data-ttu-id="232c3-164">基になる non-uniform memory access (NUMA) 構成を理解し、それに応じて Vm を構成することが重要です。</span><span class="sxs-lookup"><span data-stu-id="232c3-164">It's important to understand the underlying non-uniform memory access (NUMA) configuration and configure your VMs accordingly.</span></span>     |
|<span data-ttu-id="232c3-165">RAM</span><span class="sxs-lookup"><span data-stu-id="232c3-165">RAM</span></span>     |   <span data-ttu-id="232c3-166">4 GB</span><span class="sxs-lookup"><span data-stu-id="232c3-166">4 GB</span></span>      | <span data-ttu-id="232c3-167">512 ~ 1024 MB (ユーザーあたり)</span><span class="sxs-lookup"><span data-stu-id="232c3-167">512 to 1024 MB per user</span></span>        |
|<span data-ttu-id="232c3-168">ストレージ</span><span class="sxs-lookup"><span data-stu-id="232c3-168">Storage</span></span>    | <span data-ttu-id="232c3-169">8 GB</span><span class="sxs-lookup"><span data-stu-id="232c3-169">8 GB</span></span>        | <span data-ttu-id="232c3-170">40 ~ 60 GB</span><span class="sxs-lookup"><span data-stu-id="232c3-170">40 to 60 GB</span></span>        |

#### <a name="non-persistent-setup"></a><span data-ttu-id="232c3-171">非永続的なセットアップ</span><span class="sxs-lookup"><span data-stu-id="232c3-171">Non-persistent setup</span></span>

<span data-ttu-id="232c3-172">非永続的なセットアップでは、ユーザーのローカルオペレーティングシステムによる変更は、ユーザーがログオフした後も保持されません。</span><span class="sxs-lookup"><span data-stu-id="232c3-172">In a non-persistent setup, users' local operating system changes are not retained after users log off.</span></span> <span data-ttu-id="232c3-173">このようなセットアップは、一般的に共有されているマルチユーザーセッションです。</span><span class="sxs-lookup"><span data-stu-id="232c3-173">Such setups are commonly shared multi-user sessions.</span></span> <span data-ttu-id="232c3-174">VM 構成は、ユーザー数と利用可能な物理ボックスリソースによって異なります。</span><span class="sxs-lookup"><span data-stu-id="232c3-174">VM configuration varies based on the number of users and available physical box resources.</span></span>

<span data-ttu-id="232c3-175">非永続的なセットアップの場合、Teams デスクトップアプリはコンピューターごとにゴールデンイメージにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="232c3-175">For a non-persistent setup, the Teams desktop app must be installed per-machine to the golden image.</span></span> <span data-ttu-id="232c3-176">詳細については、「 [VDI 上の Teams デスクトップアプリをインストールまたは更新](#install-or-update-the-teams-desktop-app-on-vdi)する」を参照してください。これにより、ユーザーセッション中に Teams アプリを効率的に起動することができます。</span><span class="sxs-lookup"><span data-stu-id="232c3-176">(To learn more, see the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.) This ensures an efficient launch of the Teams app during a user session.</span></span> <span data-ttu-id="232c3-177">非永続的なセットアップで Teams を使用する場合も、効率的な Teams のランタイムデータ同期のためのプロファイルキャッシュマネージャーが必要です。これにより、適切なユーザー固有の情報 (ユーザーデータ、プロファイル、設定など) がユーザーセッション中にキャッシュされます。</span><span class="sxs-lookup"><span data-stu-id="232c3-177">Using Teams with a non-persistent setup also requires a profile caching manager for efficient Teams runtime data sync. This ensures that the appropriate user-specific information (for example, user data, profile, and settings) are cached during the user session.</span></span>  <span data-ttu-id="232c3-178">さまざまなキャッシュマネージャーソリューションが用意されています。</span><span class="sxs-lookup"><span data-stu-id="232c3-178">There are a variety of caching manager solutions available.</span></span> <span data-ttu-id="232c3-179">たとえば、 [Fslogix](https://docs.microsoft.com/fslogix/overview)となります。</span><span class="sxs-lookup"><span data-stu-id="232c3-179">For example, [FSLogix](https://docs.microsoft.com/fslogix/overview).</span></span> <span data-ttu-id="232c3-180">特定の構成手順については、キャッシュマネージャープロバイダーにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="232c3-180">Consult your caching manager provider for specific configuration instructions.</span></span>

##### <a name="teams-cached-content-exclusion-list-for-non-persistent-setup"></a><span data-ttu-id="232c3-181">非永続的なセットアップ用の Teams キャッシュされたコンテンツ除外リスト</span><span class="sxs-lookup"><span data-stu-id="232c3-181">Teams cached content exclusion list for non-persistent setup</span></span>

<span data-ttu-id="232c3-182">[Teams のキャッシュ] フォルダーから次のものを除外します。% appdata%/チーム/teams</span><span class="sxs-lookup"><span data-stu-id="232c3-182">Exclude the following from the Teams caching folder, %appdata%/Microsoft/Teams.</span></span>  <span data-ttu-id="232c3-183">これらのヘルプを除外すると、ユーザーのキャッシュサイズが小さくなり、非永続的なセットアップがさらに最適化されます。</span><span class="sxs-lookup"><span data-stu-id="232c3-183">Excluding these help reduce the user caching size to further optimize your non-persistent setup.</span></span>

- <span data-ttu-id="232c3-184">.txt ファイル</span><span class="sxs-lookup"><span data-stu-id="232c3-184">.txt files</span></span>
- <span data-ttu-id="232c3-185">メディアスタックフォルダー</span><span class="sxs-lookup"><span data-stu-id="232c3-185">Media-stack folder</span></span>

### <a name="office-365-proplus-considerations"></a><span data-ttu-id="232c3-186">Office 365 ProPlus の考慮事項</span><span class="sxs-lookup"><span data-stu-id="232c3-186">Office 365 ProPlus considerations</span></span>

<span data-ttu-id="232c3-187">Office 365 ProPlus で VDI に Teams を展開する場合は、次の点を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="232c3-187">Consider the following when you deploy Teams with Office 365 ProPlus on VDI.</span></span>

#### <a name="new-deployments-of-teams-through-office-365-proplus"></a><span data-ttu-id="232c3-188">Office 365 ProPlus を通じた Teams の新しい展開</span><span class="sxs-lookup"><span data-stu-id="232c3-188">New deployments of Teams through Office 365 ProPlus</span></span>

<span data-ttu-id="232c3-189">Office 365 ProPlus を通じてチームを展開する前に、コンピューターごとのインストールを使用して展開された既存の Teams アプリをアンインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="232c3-189">Before you deploy Teams through Office 365 ProPlus, you must first uninstall any pre-existing Teams apps if they were deployed using per-machine installation.</span></span>

<span data-ttu-id="232c3-190">Office 365 ProPlus を通じた Teams は、ユーザーごとにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="232c3-190">Teams through Office 365 ProPlus is installed per-user.</span></span> <span data-ttu-id="232c3-191">詳細については、「 [VDI 上の Teams デスクトップアプリをインストールまたは更新](#install-or-update-the-teams-desktop-app-on-vdi)する」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="232c3-191">To learn more, see the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.</span></span>

#### <a name="teams-deployments-through-office-365-proplus-updates"></a><span data-ttu-id="232c3-192">Office 365 ProPlus の更新プログラムを通じた Teams の展開</span><span class="sxs-lookup"><span data-stu-id="232c3-192">Teams deployments through Office 365 ProPlus updates</span></span>

<span data-ttu-id="232c3-193">Teams は、Office 365 ProPlus の既存のインストールにも追加されています。</span><span class="sxs-lookup"><span data-stu-id="232c3-193">Teams is also being added to existing installations of Office 365 ProPlus.</span></span> <span data-ttu-id="232c3-194">Office 365 ProPlus はユーザーごとにチームをインストールするため、「 [VDI 上の teams デスクトップアプリをインストールまたは更新](#install-or-update-the-teams-desktop-app-on-vdi)する」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="232c3-194">Since Office 365 ProPlus installs Teams per-user only, see the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.</span></span>

#### <a name="using-teams-with-per-machine-installation-and-office-365-proplus"></a><span data-ttu-id="232c3-195">コンピューターごとのインストールと Office 365 ProPlus で Teams を使用する</span><span class="sxs-lookup"><span data-stu-id="232c3-195">Using Teams with per-machine installation and Office 365 ProPlus</span></span>

<span data-ttu-id="232c3-196">Office 365 ProPlus では、各コンピューターの Teams のインストールをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="232c3-196">Office 365 ProPlus doesn't support per-machine installations of Teams.</span></span> <span data-ttu-id="232c3-197">コンピューターごとのインストールを使用するには、Office 365 ProPlus から Teams を除外する必要があります。</span><span class="sxs-lookup"><span data-stu-id="232c3-197">To use per-machine installation, you must exclude Teams from Office 365 ProPlus.</span></span> <span data-ttu-id="232c3-198">「 [Teams デスクトップアプリを VM に展開](#deploy-the-teams-desktop-app-to-the-vm)する」と「 [Office 365 ProPlus セクションを通じてチームの展開を除外する方法](#how-to-exclude-teams-deployment-through-office-365-proplus)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="232c3-198">See the [Deploy the Teams desktop app to the VM](#deploy-the-teams-desktop-app-to-the-vm) and [How to exclude Teams deployment through Office 365 ProPlus](#how-to-exclude-teams-deployment-through-office-365-proplus) sections.</span></span>

#### <a name="how-to-exclude-teams-deployment-through-office-365-proplus"></a><span data-ttu-id="232c3-199">Office 365 ProPlus を通じてチームの展開を除外する方法</span><span class="sxs-lookup"><span data-stu-id="232c3-199">How to exclude Teams deployment through Office 365 ProPlus</span></span>

<span data-ttu-id="232c3-200">Teams と Office 365 ProPlus の詳細については、「 [office 365 ProPlus の新しいインストールからチームを除外する](https://docs.microsoft.com/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-office-365-proplus)」および「[グループポリシーを使って teams のインストールを制御](https://docs.microsoft.com/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="232c3-200">To learn more about Teams and Office 365 ProPlus, see [How to exclude Teams from new installations of Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-office-365-proplus) and [Use Group Policy to control the installation of Teams](https://docs.microsoft.com/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams).</span></span>

### <a name="deploy-the-teams-desktop-app-to-the-vm"></a><span data-ttu-id="232c3-201">Teams デスクトップアプリを VM に展開する</span><span class="sxs-lookup"><span data-stu-id="232c3-201">Deploy the Teams desktop app to the VM</span></span>

1. <span data-ttu-id="232c3-202">次のリンクのいずれかを使用して、VDI VM オペレーティングシステムと一致する Teams MSI パッケージをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="232c3-202">Download the Teams MSI package that matches your VDI VM operating system using one of the following links:</span></span>

    - [<span data-ttu-id="232c3-203">32ビット版</span><span class="sxs-lookup"><span data-stu-id="232c3-203">32-bit version</span></span>](https://statics.teams.cdn.office.net/production-windows/1.2.00.32462/Teams_windows.msi)
    - [<span data-ttu-id="232c3-204">64ビット版</span><span class="sxs-lookup"><span data-stu-id="232c3-204">64-bit version</span></span>](https://statics.teams.cdn.office.net/production-windows-x64/1.2.00.32462/Teams_windows_x64.msi)

    <span data-ttu-id="232c3-205">必要な Teams デスクトップアプリの最小バージョンはバージョン1.2.00.31357 です。</span><span class="sxs-lookup"><span data-stu-id="232c3-205">The minimum version of the Teams desktop app that's required is version 1.2.00.31357.</span></span> <span data-ttu-id="232c3-206">(PSTN 保留は以前のバージョンではサポートされていません)。</span><span class="sxs-lookup"><span data-stu-id="232c3-206">(PSTN hold is not supported in earlier versions.)</span></span>

2. <span data-ttu-id="232c3-207">次のいずれかのコマンドを実行して、MSI を VDI VM にインストールします。</span><span class="sxs-lookup"><span data-stu-id="232c3-207">Install the MSI to the VDI VM by running one of the following commands:</span></span>

    - <span data-ttu-id="232c3-208">ユーザーごとのインストール (既定)</span><span class="sxs-lookup"><span data-stu-id="232c3-208">Per-user installation  (default)</span></span>
  
        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name>
        ```
    
        <span data-ttu-id="232c3-209">これは既定のインストールです。チームは、% AppData% ユーザーフォルダーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="232c3-209">This is the default installation, which installs Teams to the %AppData% user folder.</span></span> <span data-ttu-id="232c3-210">この時点で、ゴールデンイメージのセットアップが完了しています。</span><span class="sxs-lookup"><span data-stu-id="232c3-210">At this point, the golden image setup is complete.</span></span> <span data-ttu-id="232c3-211">ユーザー単位のインストールでは、非永続的なセットアップでは、チームは適切に動作しません。</span><span class="sxs-lookup"><span data-stu-id="232c3-211">Teams will not work properly with per-user installation on a non-persistent setup.</span></span>
    
    - <span data-ttu-id="232c3-212">マシン単位のインストール</span><span class="sxs-lookup"><span data-stu-id="232c3-212">Per-machine installation</span></span>

        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1
        ```

        <span data-ttu-id="232c3-213">これにより、チームは64ビットオペレーティングシステムの Program Files (x86) フォルダーと、32ビットオペレーティングシステムの Program Files フォルダーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="232c3-213">This installs Teams to the Program Files (x86) folder on a 64-bit operating system and to the Program Files folder on a 32-bit operating system.</span></span> <span data-ttu-id="232c3-214">この時点で、ゴールデンイメージのセットアップが完了しています。</span><span class="sxs-lookup"><span data-stu-id="232c3-214">At this point, the golden image setup is complete.</span></span> <span data-ttu-id="232c3-215">非永続的なセットアップでは、コンピューターごとにチームをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="232c3-215">Installing Teams per-machine is required for non-persistent setups.</span></span>
 
        <span data-ttu-id="232c3-216">次の対話型ログオンセッションでは、チームが起動し、資格情報を求められます。</span><span class="sxs-lookup"><span data-stu-id="232c3-216">The next interactive logon session starts Teams and asks for credentials.</span></span>

3. <span data-ttu-id="232c3-217">VDI VM から MSI をアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="232c3-217">Uninstall the MSI from the VDI VM.</span></span> 

    <span data-ttu-id="232c3-218">Teams をアンインストールするには、次の2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="232c3-218">There are two ways to uninstall Teams:</span></span>  
  
    - <span data-ttu-id="232c3-219">PowerShell スクリプト (推奨)</span><span class="sxs-lookup"><span data-stu-id="232c3-219">PowerShell script (recommended)</span></span>
    
    - <span data-ttu-id="232c3-220">コマンドライン: この方法ではチームが削除されますが、Teams の再インストールはできません。</span><span class="sxs-lookup"><span data-stu-id="232c3-220">Command line: This approach removes Teams, yet prevents re-installation of Teams.</span></span> <span data-ttu-id="232c3-221">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="232c3-221">Run the following command:</span></span>
  
      ```console
      msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>
      ```
      <span data-ttu-id="232c3-222">これにより、オペレーティングシステムの環境に応じて、Program Files (x86) フォルダーまたは Program Files フォルダーから Teams がアンインストールされます。</span><span class="sxs-lookup"><span data-stu-id="232c3-222">This uninstalls Teams from the Program Files (x86) folder or Program Files folder, depending on the operating system environment.</span></span>

## <a name="teams-on-vdi-performance-considerations"></a><span data-ttu-id="232c3-223">VDI のパフォーマンスに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="232c3-223">Teams on VDI performance considerations</span></span>

<span data-ttu-id="232c3-224">さまざまな仮想化設定構成があり、それぞれが最適化のために異なるフォーカスが設定されています。</span><span class="sxs-lookup"><span data-stu-id="232c3-224">There are variety of virtualized setup configurations, each with a different focus for optimization.</span></span> <span data-ttu-id="232c3-225">たとえば、ユーザーの密度。</span><span class="sxs-lookup"><span data-stu-id="232c3-225">For example, user density.</span></span> <span data-ttu-id="232c3-226">計画するときは、組織の作業負荷のニーズに合わせて、次の点を考慮してセットアップを最適化します。</span><span class="sxs-lookup"><span data-stu-id="232c3-226">When planning, consider the following to help optimize your setup based on the workload needs of your organization:</span></span>

- <span data-ttu-id="232c3-227">最小要件: 一部のワークロードでは、最小要件を超えるリソースを使用してセットアップを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="232c3-227">Minimum requirement: Some workloads may require a setup using resources that are above the minimum requirements.</span></span> <span data-ttu-id="232c3-228">たとえば、より多くのコンピューティングリソースを必要とするアプリケーションを使用している開発者向けのワークロード。</span><span class="sxs-lookup"><span data-stu-id="232c3-228">For example, workloads for developers who use applications that demand more computing resources.</span></span>
- <span data-ttu-id="232c3-229">依存関係: チームデスクトップアプリ以外のインフラストラクチャ、作業負荷、その他の環境配慮への依存関係が含まれます。</span><span class="sxs-lookup"><span data-stu-id="232c3-229">Dependencies: These include dependencies on infrastructure, workload, and other environmental considerations outside the Teams desktop app.</span></span>
- <span data-ttu-id="232c3-230">VDI で無効になっている機能: Teams では、VDI による負荷の高い機能を無効にします。これにより、一時的な CPU 使用率の向上に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="232c3-230">Disabled features on VDI: Teams disables GPU-intensive features for VDI, which can help improve transient CPU utilization.</span></span> <span data-ttu-id="232c3-231">次の機能は無効になります。</span><span class="sxs-lookup"><span data-stu-id="232c3-231">The following features are disabled:</span></span>
    - <span data-ttu-id="232c3-232">Teams CSS アニメーション</span><span class="sxs-lookup"><span data-stu-id="232c3-232">Teams CSS animation</span></span>
    - <span data-ttu-id="232c3-233">Giphy 自動開始</span><span class="sxs-lookup"><span data-stu-id="232c3-233">Giphy auto-start</span></span>

## <a name="teams-on-vdi-with-calling-and-meetings"></a><span data-ttu-id="232c3-234">通話と会議を使った VDI 上の Teams</span><span class="sxs-lookup"><span data-stu-id="232c3-234">Teams on VDI with calling and meetings</span></span>

<span data-ttu-id="232c3-235">チャットと共同作業に加えて、通話と会議のサポートを備えた VDI の Teams は、Citrix ベースのプラットフォームで利用できます。</span><span class="sxs-lookup"><span data-stu-id="232c3-235">In addition to chat and collaboration, Teams on VDI with calling and meeting support is available with Citrix-based platforms.</span></span> <span data-ttu-id="232c3-236">サポートされている機能は、WebRTC メディアスタックと Citrix 固有の実装に基づいています。</span><span class="sxs-lookup"><span data-stu-id="232c3-236">Supported features are based on the WebRTC media stack and Citrix-specific implementation.</span></span> <span data-ttu-id="232c3-237">次の図は、アーキテクチャの概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="232c3-237">The following diagram provides an overview of the architecture.</span></span>

![VDI アーキテクチャ上の Teams を示す図](media/teams-on-vdi-architecture.png)

<span data-ttu-id="232c3-239">以下の通話および会議機能はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="232c3-239">These calling and meeting features are not supported:</span></span>

- <span data-ttu-id="232c3-240">緊急電話サービスの強化</span><span class="sxs-lookup"><span data-stu-id="232c3-240">Enhanced emergency services</span></span>
- <span data-ttu-id="232c3-241">Teams アプリとデバイス間の HID ボタンと LED コントロール</span><span class="sxs-lookup"><span data-stu-id="232c3-241">HID buttons and LED controls between the Teams app and devices</span></span>
- <span data-ttu-id="232c3-242">背景のぼかしと効果</span><span class="sxs-lookup"><span data-stu-id="232c3-242">Background blur and effects</span></span>
- <span data-ttu-id="232c3-243">ブロードキャスト/ライブイベント</span><span class="sxs-lookup"><span data-stu-id="232c3-243">Broadcast/live events</span></span>
- <span data-ttu-id="232c3-244">位置情報に基づくルーティング (LBR)</span><span class="sxs-lookup"><span data-stu-id="232c3-244">Location-Based Routing (LBR)</span></span>
- <span data-ttu-id="232c3-245">コール パーク</span><span class="sxs-lookup"><span data-stu-id="232c3-245">Call park</span></span>
- <span data-ttu-id="232c3-246">通話キュー</span><span class="sxs-lookup"><span data-stu-id="232c3-246">Call queue</span></span>

> [!IMPORTANT]
> <span data-ttu-id="232c3-247">現在、AV を最適化せずに team を VDI で実行していて、最適化のためにまだサポートされていない機能を使用している場合 (アプリの共有時に制御を許可する場合など)、[Teams] ポリシーを設定して Teams のリダイレクションを無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="232c3-247">If you currently run Teams without AV optimization in VDI and you use features that are not supported yet for optimization (such as Give and take control when app sharing), you have to set Citrix policies to turn off Teams redirection.</span></span> <span data-ttu-id="232c3-248">これは、Teams メディアセッションが最適化されないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="232c3-248">This means that Teams media sessions won’t be optimized.</span></span> <span data-ttu-id="232c3-249">Teams のリダイレクションを無効にするポリシーを設定する手順については、この[Citrix の web サイト](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/policies/reference/ica-policy-settings/multimedia-policy-settings.html)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="232c3-249">For steps on how to set policies to turn off Teams redirection, see this [Citrix website](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/policies/reference/ica-policy-settings/multimedia-policy-settings.html).</span></span>

<span data-ttu-id="232c3-250">現時点では、VDI 以外の環境でのみ利用可能な通話と会議機能の追加に取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="232c3-250">We're working on adding calling and meeting features that are currently only available in non-VDI environments.</span></span> <span data-ttu-id="232c3-251">これには、品質、追加の画面共有シナリオ、チームに最近追加された高度な機能など、より多くの管理者の制御が含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="232c3-251">These may include more admin control over quality, additional screen sharing scenarios, and advanced features recently added to Teams.</span></span> <span data-ttu-id="232c3-252">今後の機能の詳細については、チームの担当者にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="232c3-252">Contact your Teams representative to learn more about upcoming features.</span></span>

### <a name="network-requirements"></a><span data-ttu-id="232c3-253">ネットワーク要件</span><span class="sxs-lookup"><span data-stu-id="232c3-253">Network requirements</span></span>

<span data-ttu-id="232c3-254">クラウドの全体的な音声とビデオの展開に影響を与える可能性のあるリスクと要件を特定するために、環境を評価することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="232c3-254">We recommend that you evaluate your environment to identify any risks and requirements that can influence your overall cloud voice and video deployment.</span></span> <span data-ttu-id="232c3-255">[Skype For Business ネットワーク評価ツール](https://www.microsoft.com/download/details.aspx?id=53885)を使用して、自分のネットワークが Teams に対応しているかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="232c3-255">Use the [Skype for Business Network Assessment Tool](https://www.microsoft.com/download/details.aspx?id=53885) to test whether your network is ready for Teams.</span></span>

<span data-ttu-id="232c3-256">Teams のネットワークを準備する方法について詳しくは、「 [teams 用に組織のネットワークを準備](prepare-network.md)する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="232c3-256">To learn more about how to prepare your network for Teams, see [Prepare your organization's network for  Teams](prepare-network.md).</span></span>

### <a name="migrate-from-skype-for-business-on-vdi-to-teams-on-vdi"></a><span data-ttu-id="232c3-257">Vdi での Skype for Business から VDI 上の Teams への移行</span><span class="sxs-lookup"><span data-stu-id="232c3-257">Migrate from Skype for Business on VDI to Teams on VDI</span></span>

<span data-ttu-id="232c3-258">Vdi での Skype for Business から VDI 上の Teams への移行を行っている場合、2つのアプリケーションの違いに加えて、VDI も実装するといくつかの違いがあります。</span><span class="sxs-lookup"><span data-stu-id="232c3-258">If you're migrating from Skype for Business on VDI to Teams on VDI, besides the differences between the two applications, there are some differences when VDI is also implemented.</span></span> <span data-ttu-id="232c3-259">Skype for Business VDI で現在サポートされていない Teams VDI の機能には、次のような機能があります。</span><span class="sxs-lookup"><span data-stu-id="232c3-259">Some capabilities that aren’t currently supported in Teams VDI that are in Skype for Business VDI are as follows:</span></span>

- <span data-ttu-id="232c3-260">メディアのビットレートを制限するためのポリシーを使った VDI 通話エクスペリエンスの制御</span><span class="sxs-lookup"><span data-stu-id="232c3-260">Control of VDI calling experiences with policies for limiting media bitrate</span></span>
- <span data-ttu-id="232c3-261">VDI の一部の AV 機能を無効にするプラットフォームごとのポリシー</span><span class="sxs-lookup"><span data-stu-id="232c3-261">Per-platform policy to disable some AV features in VDI</span></span>
- <span data-ttu-id="232c3-262">アプリ共有を行うときの制御</span><span class="sxs-lookup"><span data-stu-id="232c3-262">Give and take control when app sharing</span></span>
- <span data-ttu-id="232c3-263">音声なしのチャットからの画面共有</span><span class="sxs-lookup"><span data-stu-id="232c3-263">Screen share from chat without audio</span></span>
- <span data-ttu-id="232c3-264">同時にビデオと画面共有の送受信を行うことができる</span><span class="sxs-lookup"><span data-stu-id="232c3-264">Simultaneous video and screen sharing send and receive</span></span>

### <a name="teams-on-chrome-browser-versus-teams-desktop-app-for-vdi"></a><span data-ttu-id="232c3-265">Chrome ブラウザーと VDI 用 Teams デスクトップアプリのチーム</span><span class="sxs-lookup"><span data-stu-id="232c3-265">Teams on Chrome browser versus Teams desktop app for VDI</span></span>

<span data-ttu-id="232c3-266">Chrome ブラウザーの teams では、AV の最適化を備えた VDI 用の Teams デスクトップアプリに代わる機能は提供されていません。</span><span class="sxs-lookup"><span data-stu-id="232c3-266">Teams on Chrome browser doesn't provide a replacement for the Teams desktop app for VDI with AV optimization.</span></span> <span data-ttu-id="232c3-267">チャットと共同作業のエクスペリエンスは期待どおりに動作します。</span><span class="sxs-lookup"><span data-stu-id="232c3-267">The chat and collaboration experience works as expected.</span></span> <span data-ttu-id="232c3-268">メディアが必要な場合は、Chrome ブラウザーでユーザーの期待を満たせない場合があります。</span><span class="sxs-lookup"><span data-stu-id="232c3-268">When media is needed, there are some experiences that may not meet user expectations on the Chrome browser:</span></span>

- <span data-ttu-id="232c3-269">オーディオとビデオのストリーミングのエクスペリエンスが最適でないことがあります。</span><span class="sxs-lookup"><span data-stu-id="232c3-269">The audio and video streaming experience may not be optimal.</span></span> <span data-ttu-id="232c3-270">ユーザーには、遅延または品質の低下が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="232c3-270">Users may experiences delays or reduced quality.</span></span>
- <span data-ttu-id="232c3-271">[デバイスの設定] は [ブラウザーの設定] では利用できません。</span><span class="sxs-lookup"><span data-stu-id="232c3-271">Device settings aren't available in browser settings.</span></span>
- <span data-ttu-id="232c3-272">デバイス管理はブラウザーで処理され、ブラウザーの [サイトの設定] では複数の設定が必要です。</span><span class="sxs-lookup"><span data-stu-id="232c3-272">Device management is handled through the browser and requires multiple settings in browser site settings.</span></span>
- <span data-ttu-id="232c3-273">デバイスの設定は、Windows デバイス管理でも設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="232c3-273">Device settings may also need to be set in Windows device management.</span></span>

## <a name="teams-on-vdi-with-chat-and-collaboration"></a><span data-ttu-id="232c3-274">チャットと共同作業による VDI on Teams</span><span class="sxs-lookup"><span data-stu-id="232c3-274">Teams on VDI with chat and collaboration</span></span>

<span data-ttu-id="232c3-275">組織で Teams のチャット機能と共同作業機能のみを使用する場合は、ユーザーレベルのポリシーを設定して、Teams の呼び出しと会議の機能を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="232c3-275">If your organization wants to only use chat and collaboration features in Teams, you can set user-level policies to turn off calling and meeting functionality in Teams.</span></span> <span data-ttu-id="232c3-276">この機能レベルでは、Citrix 仮想アプリとデスクトップは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="232c3-276">This feature level doesn't require Citrix Virtual Apps and Desktops.</span></span>

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a><span data-ttu-id="232c3-277">通話と会議の機能を無効にするポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="232c3-277">Set policies to turn off calling and meeting functionality</span></span>

<span data-ttu-id="232c3-278">ポリシーを設定するには、Microsoft Teams 管理センターまたは PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="232c3-278">You can set policies by using the Microsoft Teams admin center or PowerShell.</span></span> <span data-ttu-id="232c3-279">ポリシーの変更が反映されるまでには、多少時間がかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="232c3-279">It can take some time (a few hours) for the policy changes to propagate.</span></span> <span data-ttu-id="232c3-280">特定のアカウントの変更がすぐに表示されない場合は、数時間後にもう一度お試しください。</span><span class="sxs-lookup"><span data-stu-id="232c3-280">If you don’t see changes for a given account immediately, try again in a few hours.</span></span>

<span data-ttu-id="232c3-281">[**通話ポリシー**](teams-calling-policy.md): Teams には組み込みの DisallowCalling 通話ポリシーが含まれており、すべての通話機能がオフになっています。</span><span class="sxs-lookup"><span data-stu-id="232c3-281">[**Calling polices**](teams-calling-policy.md): Teams includes the built-in DisallowCalling calling policy, in which all calling features are turned off.</span></span> <span data-ttu-id="232c3-282">仮想化された環境で Teams を使用する組織内のすべてのユーザーに DisallowCalling ポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="232c3-282">Assign the DisallowCalling policy to all users in your organization who use Teams in a virtualized environment.</span></span>

<span data-ttu-id="232c3-283">[**会議ポリシー**](meeting-policies-in-teams.md): Teams には、すべての会議機能がオフになっている組み込みの "いいね!" の会議ポリシーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="232c3-283">[**Meeting policies**](meeting-policies-in-teams.md): Teams includes the built-in AllOff meeting policy, in which all meeting features are turned off.</span></span> <span data-ttu-id="232c3-284">仮想化された環境で Teams を使用する組織内のすべてのユーザーに対して、割り当てられた Ff ポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="232c3-284">Assign the AllOff policy to all users in your organization who use Teams in a virtualized environment.</span></span>

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a><span data-ttu-id="232c3-285">Microsoft Teams 管理センターを使用してポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="232c3-285">Assign policies using the Microsoft Teams admin center</span></span>

<span data-ttu-id="232c3-286">DisallowCalling の通話ポリシーと、割り当てられているユーザーに割り当てることができる会議ポリシーを割り当てるには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="232c3-286">To assign the DisallowCalling calling policy and the AllOff meeting policy to users, follow these steps:</span></span>

1. <span data-ttu-id="232c3-287">Microsoft Teams 管理センターの左のナビゲーションで、[**ユーザー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="232c3-287">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="232c3-288">ユーザー名の左側をクリックしてユーザーを選択し、[**編集を設定する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="232c3-288">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="232c3-289">次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="232c3-289">Do the following:</span></span>
    1.  <span data-ttu-id="232c3-290">[**通話ポリシー**] で [ **DisallowCalling**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="232c3-290">Under **Calling policy**, click **DisallowCalling**.</span></span>
    2.  <span data-ttu-id="232c3-291">[**会議のポリシー**] で、[割り当てる]**をクリックし**ます。</span><span class="sxs-lookup"><span data-stu-id="232c3-291">Under **Meeting policy**, click **AllOff**.</span></span>
4. <span data-ttu-id="232c3-292">[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="232c3-292">Click **Apply**.</span></span>

<span data-ttu-id="232c3-293">一度に複数のユーザーにポリシーを割り当てる方法については、「[一括でTeams のユーザー設定を編集する](edit-user-settings-in-bulk.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="232c3-293">To assign a policy to multiple users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="232c3-294">または、次の操作も実行できます。</span><span class="sxs-lookup"><span data-stu-id="232c3-294">Or, you can also do the following:</span></span>

1. <span data-ttu-id="232c3-295">Microsoft Teams 管理センターの左のナビゲーションで、割り当てるポリシーに移動します。</span><span class="sxs-lookup"><span data-stu-id="232c3-295">In the left navigation of the Microsoft Teams admin center, go to the policy you want to assign.</span></span> <span data-ttu-id="232c3-296">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="232c3-296">For example:</span></span>
    - <span data-ttu-id="232c3-297">[**音声** > **通話のポリシー**] に移動し、[ **DisallowCalling**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="232c3-297">Go to **Voice** > **Calling policies**, and then click **DisallowCalling**.</span></span>
    - <span data-ttu-id="232c3-298">[**会議** > の**ポリシー**] に移動して、[割り当てる**ff**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="232c3-298">Go to **Meetings** > **Meeting policies**, and then click **AllOff**.</span></span>
3. <span data-ttu-id="232c3-299">[**ユーザーを管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="232c3-299">Select **Manage users**.</span></span>
4. <span data-ttu-id="232c3-300">[**ユーザーの管理**] ウィンドウで、[表示名] または [ユーザー名] でユーザーを検索し、名前を選択して [**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="232c3-300">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="232c3-301">追加するユーザーごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="232c3-301">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="232c3-302">ユーザーの追加が完了したら、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="232c3-302">When you're finished adding users, click **Save**.</span></span>

#### <a name="assign-policies-using-powershell"></a><span data-ttu-id="232c3-303">PowerShell を使用してポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="232c3-303">Assign policies using PowerShell</span></span>

<span data-ttu-id="232c3-304">次の例は、 [Grant-CsteamDisallowCalling のポリシー](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy)を使って、ユーザーにの呼び出しポリシーを割り当てる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="232c3-304">The following example shows how to use the [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) to assign the DisallowCalling calling policy to a user.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity “user email id”
```

<span data-ttu-id="232c3-305">PowerShell を使用して通話ポリシーを管理する方法の詳細については、「 [Set-Csteam拡張性のポリシー](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="232c3-305">To learn more about using PowerShell to manage calling policies, see [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).</span></span>

<span data-ttu-id="232c3-306">次の例は、CsTeamsMeetingPolicy を使用して、[グラント](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy)ff 会議ポリシーをユーザーに割り当てる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="232c3-306">The following example shows how to use the [Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) to assign the AllOff meeting policy to a user.</span></span>

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity “user email id”
```

<span data-ttu-id="232c3-307">PowerShell を使用して会議のポリシーを管理する方法の詳細については、「 [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="232c3-307">To learn more about using PowerShell to manage meeting policies, see [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>

## <a name="migrate-teams-on-vdi-with-chat-and-collaboration-to-citrix-with-calling-and-meetings"></a><span data-ttu-id="232c3-308">通話と会議を使って、VDI 上のチームをチャットとコラボレーションで Citrix に移行する</span><span class="sxs-lookup"><span data-stu-id="232c3-308">Migrate Teams on VDI with chat and collaboration to Citrix with calling and meetings</span></span>

<span data-ttu-id="232c3-309">ユーザーレベルのポリシーを設定して、通話と会議機能を無効にしている場合に、チャットと共同作業を行っている VDI 上の Teams の既存の実装がある場合、AV 最適化を有効にして Citrix に移行するには、ポリシーを設定する必要があります。VDI ユーザー向けのチームの会議機能。</span><span class="sxs-lookup"><span data-stu-id="232c3-309">If you have an existing implementation of Teams on VDI with chat and collaboration in which you had set user-level policies to turn off calling and meeting functionality, and you're migrating to Citrix with AV optimization, you must set policies to turn on calling and meeting functionality for those Teams on VDI users.</span></span>

### <a name="set-policies-to-turn-on-calling-and-meeting-functionality"></a><span data-ttu-id="232c3-310">通話と会議の機能を有効にするポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="232c3-310">Set policies to turn on calling and meeting functionality</span></span>

<span data-ttu-id="232c3-311">Microsoft Teams 管理センターまたは PowerShell を使用して、通話と会議のポリシーを設定し、ユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="232c3-311">You can use the Microsoft Teams admin center or PowerShell to set and assign calling and meeting policies to your users.</span></span> <span data-ttu-id="232c3-312">ポリシーの変更が反映されるまでには、多少時間がかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="232c3-312">It can take some time (a few hours) for policy changes to propagate.</span></span> <span data-ttu-id="232c3-313">特定のアカウントの変更がすぐに表示されない場合は、数時間後にもう一度お試しください。</span><span class="sxs-lookup"><span data-stu-id="232c3-313">If you don’t see changes for a given account immediately, try again after a few hours.</span></span>

<span data-ttu-id="232c3-314">[**通話**](teams-calling-policy.md)ポリシー: Teams の通話ポリシーは、ユーザーが使用できる通話機能を制御します。</span><span class="sxs-lookup"><span data-stu-id="232c3-314">[**Calling polices**](teams-calling-policy.md): Calling policies in Teams control which calling features are available to users.</span></span> <span data-ttu-id="232c3-315">Teams には、組み込みの AllowCalling 通話ポリシーが含まれており、すべての通話機能が有効になっています。</span><span class="sxs-lookup"><span data-stu-id="232c3-315">Teams includes the built-in AllowCalling calling policy, in which all calling features are turned on.</span></span> <span data-ttu-id="232c3-316">すべての通話機能を有効にするには、AllowCalling ポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="232c3-316">To turn on all calling features, assign the AllowCalling policy.</span></span> <span data-ttu-id="232c3-317">または、カスタム通話ポリシーを作成して、必要な通話機能を有効にし、ユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="232c3-317">Or, create a custom calling policy to turn on the calling features that you want and assign it to users.</span></span> 

<span data-ttu-id="232c3-318">[**会議ポリシー**](meeting-policies-in-teams.md): Teams の会議ポリシーは、ユーザーが作成できる会議の種類と、組織内のユーザーによってスケジュールされている会議の参加者が使用できる機能を制御します。</span><span class="sxs-lookup"><span data-stu-id="232c3-318">[**Meeting policies**](meeting-policies-in-teams.md): Meeting policies in Teams control the types of meetings that users can create and the features that are available to meeting participants that are scheduled by users in your organization.</span></span> <span data-ttu-id="232c3-319">Teams には、すべての会議機能が有効になっている組み込みのすべての会議のポリシーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="232c3-319">Teams includes the built-in AllOn meeting policy, in which all meeting features are turned on.</span></span> <span data-ttu-id="232c3-320">すべての会議機能を有効にするには、[すべて] のポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="232c3-320">To turn on all meeting features, assign the AllOn policy.</span></span> <span data-ttu-id="232c3-321">または、カスタム会議ポリシーを作成して、必要な会議機能を有効にし、ユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="232c3-321">Or, create a custom meeting policy to turn on the meeting features that you want and assign it users.</span></span>

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a><span data-ttu-id="232c3-322">Microsoft Teams 管理センターを使用してポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="232c3-322">Assign policies using the Microsoft Teams admin center</span></span>

<span data-ttu-id="232c3-323">AllowCalling の通話ポリシーと [すべての会議] ポリシーをユーザーに割り当てるには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="232c3-323">To assign the AllowCalling calling policy and the AllOn meeting policy to users, follow these steps:</span></span>

1. <span data-ttu-id="232c3-324">Microsoft Teams 管理センターの左のナビゲーションで、[**ユーザー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="232c3-324">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="232c3-325">ユーザー名の左側をクリックしてユーザーを選択し、[**編集を設定する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="232c3-325">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="232c3-326">次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="232c3-326">Do the following:</span></span>
    1.  <span data-ttu-id="232c3-327">[**通話ポリシー**] で [ **allowcalling**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="232c3-327">Under **Calling policy**, click **AllowCalling**.</span></span>
    2.  <span data-ttu-id="232c3-328">[**会議のポリシー**] で [**すべて**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="232c3-328">Under **Meeting policy**, click **AllOn**.</span></span>
4. <span data-ttu-id="232c3-329">[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="232c3-329">Click **Apply**.</span></span>

<span data-ttu-id="232c3-330">一度に複数のユーザーにポリシーを割り当てる方法については、「[一括でTeams のユーザー設定を編集する](edit-user-settings-in-bulk.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="232c3-330">To assign a policy to multiple users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="232c3-331">または、次の操作も実行できます。</span><span class="sxs-lookup"><span data-stu-id="232c3-331">Or, you can also do the following:</span></span>

1. <span data-ttu-id="232c3-332">Microsoft Teams 管理センターの左のナビゲーションで、割り当てるポリシーに移動します。</span><span class="sxs-lookup"><span data-stu-id="232c3-332">In the left navigation of the Microsoft Teams admin center, go to the policy you want to assign.</span></span> <span data-ttu-id="232c3-333">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="232c3-333">For example:</span></span>
    - <span data-ttu-id="232c3-334">[**音声** > **通話のポリシー**] に移動し、[ **allowcalling**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="232c3-334">Go to **Voice** > **Calling policies**, and then click **AllowCalling**.</span></span>
    - <span data-ttu-id="232c3-335">[**会議** > の**ポリシー**] に移動し、[**すべて**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="232c3-335">Go to **Meetings** > **Meeting policies**, and then click **AllOn**.</span></span>
3. <span data-ttu-id="232c3-336">[**ユーザーを管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="232c3-336">Select **Manage users**.</span></span>
4. <span data-ttu-id="232c3-337">[**ユーザーの管理**] ウィンドウで、[表示名] または [ユーザー名] でユーザーを検索し、名前を選択して [**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="232c3-337">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="232c3-338">追加するユーザーごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="232c3-338">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="232c3-339">ユーザーの追加が完了したら、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="232c3-339">When you're finished adding users, click **Save**.</span></span>

#### <a name="assign-policies-using-powershell"></a><span data-ttu-id="232c3-340">PowerShell を使用してポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="232c3-340">Assign policies using PowerShell</span></span>

<span data-ttu-id="232c3-341">次の例は、 [Grant-Csteam分解のポリシー](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy)を使って、allowcalling 呼び出しポリシーをユーザーに割り当てる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="232c3-341">The following example shows how to use the [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) to assign the AllowCalling calling policy to a user.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName AllowCalling -Identity “user email id”
```

<span data-ttu-id="232c3-342">PowerShell を使用して通話ポリシーを管理する方法の詳細については、「 [Set-Csteam拡張性のポリシー](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="232c3-342">To learn more about using PowerShell to manage calling policies, see [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).</span></span>

<span data-ttu-id="232c3-343">次の例は、 [CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy)を使用して、すべての会議ポリシーをユーザーに割り当てる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="232c3-343">The following example shows how to use the [Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) to assign the AllOn meeting policy to a user.</span></span>

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOn -Identity “user email id”
```

<span data-ttu-id="232c3-344">PowerShell を使用して会議のポリシーを管理する方法の詳細については、「 [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="232c3-344">To learn more about using PowerShell to manage meeting policies, see [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>

## <a name="known-issues-and-limitations"></a><span data-ttu-id="232c3-345">既知の問題と制限事項</span><span class="sxs-lookup"><span data-stu-id="232c3-345">Known issues and limitations</span></span>

### <a name="client-deployment-installation-and-setup"></a><span data-ttu-id="232c3-346">クライアントの展開、インストール、セットアップ</span><span class="sxs-lookup"><span data-stu-id="232c3-346">Client deployment, installation, and setup</span></span>

- <span data-ttu-id="232c3-347">コンピューターごとにインストールする場合、vdi の Teams は非 VDI Teams クライアントとして自動的に更新されることはありません。</span><span class="sxs-lookup"><span data-stu-id="232c3-347">With per-machine installation, Teams on VDI isn't automatically updated in the way that non-VDI Teams clients are.</span></span> <span data-ttu-id="232c3-348">「 [VDI 上の Teams デスクトップアプリをインストールまたは更新](#install-or-update-the-teams-desktop-app-on-vdi)する」セクションで説明されているように、新しい MSI をインストールして VM イメージを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="232c3-348">You have to update the VM image by installing a new MSI as described in the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.</span></span> <span data-ttu-id="232c3-349">最新バージョンに更新するには、現在のバージョンをアンインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="232c3-349">You must uninstall the current version to update to a newer version.</span></span>
- <span data-ttu-id="232c3-350">チームは、ユーザーごとまたはコンピューターごとに展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="232c3-350">Teams should be deployed either per user or per machine.</span></span> <span data-ttu-id="232c3-351">同時ユーザー数とコンピューター単位のチームの展開はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="232c3-351">Deployment of Teams for concurrent per user and per machine is not supported.</span></span>  <span data-ttu-id="232c3-352">コンピューターごとまたはユーザーごとに、これらのモードのいずれかに移行するには、アンインストール手順に従い、どちらかのモードに再展開します。</span><span class="sxs-lookup"><span data-stu-id="232c3-352">To migrate from either per machine or per user to one of these modes, follow the uninstall procedure and redeploy to either mode.</span></span>
- <span data-ttu-id="232c3-353">現時点では、MacOs および Linux ベースのクライアントは Citrix でサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="232c3-353">MacOs and Linux-based clients are not supported by Citrix at this time.</span></span>
- <span data-ttu-id="232c3-354">Citrix は、エンドポイントで定義された明示的な HTTP プロキシの使用をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="232c3-354">Citrix doesn't support the use of explicit HTTP proxies defined on an endpoint.</span></span> 

### <a name="calling-and-meetings"></a><span data-ttu-id="232c3-355">通話と会議</span><span class="sxs-lookup"><span data-stu-id="232c3-355">Calling and meetings</span></span>

- <span data-ttu-id="232c3-356">Skype for Business の相互運用性は音声通話に限定され、ビデオ表示には使用できません。</span><span class="sxs-lookup"><span data-stu-id="232c3-356">Interoperability with Skype for Business is limited to audio calls, no video modality.</span></span>
- <span data-ttu-id="232c3-357">デュアルトーンマルチ周波数 (DTMF) テレフォニーシステムとの相互操作は、現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="232c3-357">Dual Tone Multi Frequency (DTMF) interaction with telephony systems  is currently not supported.</span></span>
- <span data-ttu-id="232c3-358">匿名ユーザーとして Teams 会議に参加することは、AV-最適化されていません。</span><span class="sxs-lookup"><span data-stu-id="232c3-358">Joining Teams meetings as an anonymous user isn't AV-optimized.</span></span> <span data-ttu-id="232c3-359">ユーザーは会議に参加し、最適化されていない操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="232c3-359">The user can join the meeting and have a non-optimized experience.</span></span>
- <span data-ttu-id="232c3-360">会議またはグループ通話でサポートされているビデオストリームは1つだけです。</span><span class="sxs-lookup"><span data-stu-id="232c3-360">Only a single incoming video stream is supported in meetings or group calls.</span></span> <span data-ttu-id="232c3-361">複数のユーザーがビデオを送信する場合、常に表示されている主要なスピーカーのビデオのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="232c3-361">When multiple people send video, only the dominant speaker's video is shown at any given time.</span></span>  
- <span data-ttu-id="232c3-362">着信と発信のビデオストリームの解像度は720p の解像度に制限されています。</span><span class="sxs-lookup"><span data-stu-id="232c3-362">Incoming and outgoing video stream resolution is limited to 720p resolution.</span></span> <span data-ttu-id="232c3-363">これは WebRTC の制限です。</span><span class="sxs-lookup"><span data-stu-id="232c3-363">This is a WebRTC limitation.</span></span>
- <span data-ttu-id="232c3-364">着信カメラまたは画面共有ストリームのビデオストリームは1つだけです。</span><span class="sxs-lookup"><span data-stu-id="232c3-364">Only one video stream from an incoming camera or screen share stream is supported.</span></span> <span data-ttu-id="232c3-365">受信画面共有が表示されている場合は、その画面共有が、優先スピーカーのビデオではなく、画面上に表示されます。</span><span class="sxs-lookup"><span data-stu-id="232c3-365">When there's an incoming screen share, that screen share is shown it instead of the video of the dominant speaker.</span></span>
- <span data-ttu-id="232c3-366">送信画面の共有:</span><span class="sxs-lookup"><span data-stu-id="232c3-366">Outgoing screen sharing:</span></span>
    - <span data-ttu-id="232c3-367">アプリケーション共有はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="232c3-367">Application sharing is not supported.</span></span>
- <span data-ttu-id="232c3-368">コントロールを用意して制御します。</span><span class="sxs-lookup"><span data-stu-id="232c3-368">Give control and take control:</span></span>  
    - <span data-ttu-id="232c3-369">画面共有またはアプリケーション共有セッション中はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="232c3-369">Not supported during a screen sharing or application sharing session.</span></span>
    - <span data-ttu-id="232c3-370">PowerPoint 共有セッション中にサポートされます。</span><span class="sxs-lookup"><span data-stu-id="232c3-370">Supported during a PowerPoint sharing session.</span></span>
- <span data-ttu-id="232c3-371">マルチモニターのセットアップで画面共有を行う場合、メインモニターのみが共有されます。</span><span class="sxs-lookup"><span data-stu-id="232c3-371">When screen sharing in a multi-monitor setup, only the main monitor is shared.</span></span>
- <span data-ttu-id="232c3-372">CWA での高 DPI スケーリングはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="232c3-372">High DPI scaling on CWA is not supported.</span></span>

<span data-ttu-id="232c3-373">VDI に関連していない Teams の既知の問題については、「 [teams の既知の問題](Known-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="232c3-373">For Teams known issues that aren’t related to VDI, see [Known issues for Teams](Known-issues.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="232c3-374">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="232c3-374">Troubleshooting</span></span>

#### <a name="troubleshoot-citrix-components"></a><span data-ttu-id="232c3-375">Citrix コンポーネントのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="232c3-375">Troubleshoot Citrix components</span></span>

<span data-ttu-id="232c3-376">VDA と CWA の問題を解決する方法については、[この Citrix の web サイト](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="232c3-376">For information on how to troubleshoot VDA and CWA issues, see [this Citrix website](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html).</span></span>

## <a name="related-topics"></a><span data-ttu-id="232c3-377">関連項目</span><span class="sxs-lookup"><span data-stu-id="232c3-377">Related topics</span></span>

- [<span data-ttu-id="232c3-378">MSI を使用して Microsoft Teams をインストールする</span><span class="sxs-lookup"><span data-stu-id="232c3-378">Install Microsoft Teams using MSI</span></span>](msi-deployment.md)
- [<span data-ttu-id="232c3-379">Teams での PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="232c3-379">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
