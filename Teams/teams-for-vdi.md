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
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4c63195f4732931083a12a455b79d77d9c1e6b01
ms.sourcegitcommit: dc240b123efb03d5ab0545d650a973bf60d04506
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2019
ms.locfileid: "40069348"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a><span data-ttu-id="01d7d-103">仮想デスクトップ インフラストラクチャ用の Teams</span><span class="sxs-lookup"><span data-stu-id="01d7d-103">Teams for Virtualized Desktop Infrastructure</span></span>

<span data-ttu-id="01d7d-104">この記事では、仮想化された環境で Microsoft Teams を使用する場合の要件と制限について説明します。</span><span class="sxs-lookup"><span data-stu-id="01d7d-104">This article describes the requirements and limitations for using Microsoft Teams in a virtualized environment.</span></span>

## <a name="what-is-vdi"></a><span data-ttu-id="01d7d-105">VDI とは</span><span class="sxs-lookup"><span data-stu-id="01d7d-105">What is VDI?</span></span>

<span data-ttu-id="01d7d-106">仮想デスクトップインフラストラクチャ (VDI) は、デスクトップオペレーティングシステムと、データセンターの中央サーバー上のアプリケーションをホストする仮想化テクノロジです。</span><span class="sxs-lookup"><span data-stu-id="01d7d-106">Virtual Desktop Infrastructure (VDI) is virtualization technology that hosts a desktop operating system and applications on a centralized server in a data center.</span></span> <span data-ttu-id="01d7d-107">これにより、完全にセキュリティが設定された一元的な中央集中ソースを持つユーザーに、完全にカスタマイズされたデスクトップエクスペリエンスを提供できます。</span><span class="sxs-lookup"><span data-stu-id="01d7d-107">This enables a fully personalized desktop experience to users with a fully secured and compliant centralized source.</span></span>
 
<span data-ttu-id="01d7d-108">仮想環境での Microsoft Teams はチャットと共同作業をサポートしており、Citrix プラットフォームでは、通話と会議機能もサポートされています。</span><span class="sxs-lookup"><span data-stu-id="01d7d-108">Microsoft Teams in a virtualized environment supports chat and collaboration, and with the Citrix platform, calling and meeting functionality are also supported.</span></span>

<span data-ttu-id="01d7d-109">仮想環境の Teams では、複数の構成がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="01d7d-109">Teams in a virtualized environment supports multiple configurations.</span></span> <span data-ttu-id="01d7d-110">これには、VDI、専用、共有、常設、非永続的モードが含まれます。</span><span class="sxs-lookup"><span data-stu-id="01d7d-110">These include VDI, dedicated, shared, persistent and non-persistent modes.</span></span> <span data-ttu-id="01d7d-111">機能は継続的な開発中であり、定期的に追加されており、今後数ヶ月にわたって機能が拡張されます。</span><span class="sxs-lookup"><span data-stu-id="01d7d-111">Features are in continuous development and are added on a regular basis, and functionality will expand in the coming months and years.</span></span>
 
<span data-ttu-id="01d7d-112">仮想環境で Teams を使用する場合は、仮想化されていない環境での Teams の使用とは多少異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="01d7d-112">Using Teams in a virtualized environment may be somewhat different from using Teams in a non-virtualized environment.</span></span> <span data-ttu-id="01d7d-113">たとえば、一部の高度な機能は仮想化された環境では使用できず、ビデオ解像度が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="01d7d-113">For example, some advanced features may not be available in a virtualized environment and video resolution may differ.</span></span> <span data-ttu-id="01d7d-114">最適なユーザーエクスペリエンスを実現するには、この記事のガイダンスに従ってください。</span><span class="sxs-lookup"><span data-stu-id="01d7d-114">To ensure an optimal user experience, follow the guidance in this article.</span></span>

## <a name="teams-on-vdi-components"></a><span data-ttu-id="01d7d-115">VDI コンポーネントの Teams</span><span class="sxs-lookup"><span data-stu-id="01d7d-115">Teams on VDI components</span></span>

<span data-ttu-id="01d7d-116">仮想環境で Teams を使用するには、次のコンポーネントが必要です。</span><span class="sxs-lookup"><span data-stu-id="01d7d-116">Using Teams in a virtualized environment requires the following components.</span></span>

- <span data-ttu-id="01d7d-117">**仮想ブローカー**: Azure などの仮想化プロバイダーへのリソースと接続マネージャー</span><span class="sxs-lookup"><span data-stu-id="01d7d-117">**Virtualization broker**: The resource and connection manager to the virtualization provider, such as Azure</span></span>
- <span data-ttu-id="01d7d-118">**仮想デスクトップ**: Microsoft Teams を実行する仮想マシン (VM) スタック</span><span class="sxs-lookup"><span data-stu-id="01d7d-118">**Virtual desktop**: The Virtual Machine (VM) stack that runs Microsoft Teams</span></span>
- <span data-ttu-id="01d7d-119">**シンクライアント**: ユーザーが物理的にインターフェイスを使用するエンドポイント</span><span class="sxs-lookup"><span data-stu-id="01d7d-119">**Thin client**: The endpoint that the user physically interfaces with</span></span>
- <span data-ttu-id="01d7d-120">**Teams デスクトップアプリ**: これは teams デスクトップクライアントアプリです</span><span class="sxs-lookup"><span data-stu-id="01d7d-120">**Teams desktop app**: This is the Teams desktop client app</span></span>

## <a name="teams-on-vdi-requirements"></a><span data-ttu-id="01d7d-121">VDI の要件に関するチーム</span><span class="sxs-lookup"><span data-stu-id="01d7d-121">Teams on VDI requirements</span></span>

### <a name="virtualization-provider-requirements"></a><span data-ttu-id="01d7d-122">仮想化プロバイダーの要件</span><span class="sxs-lookup"><span data-stu-id="01d7d-122">Virtualization provider requirements</span></span>

<span data-ttu-id="01d7d-123">Teams デスクトップアプリは、主要な仮想化ソリューションプロバイダーと共に検証されました。</span><span class="sxs-lookup"><span data-stu-id="01d7d-123">The Teams desktop app was validated with leading virtualization solution providers.</span></span> <span data-ttu-id="01d7d-124">市場プロバイダーが複数ある場合は、最小要件が満たされるように仮想化ソリューションプロバイダーに問い合わせることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="01d7d-124">With multiple market providers, we recommend that you consult your virtualization solution provider to ensure minimum requirements are met.</span></span>
  
<span data-ttu-id="01d7d-125">現時点では、音声/ビデオ (AV) 最適化による VDI 上の Teams は、Citrix で認定されています。</span><span class="sxs-lookup"><span data-stu-id="01d7d-125">Currently, Teams on VDI with audio/video (AV) optimization is certified with Citrix.</span></span> <span data-ttu-id="01d7d-126">このセクションの情報を確認して、Citrix と Teams の両方の要件が適切に機能するようになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="01d7d-126">Review the information in this section to ensure both Citrix and Teams requirements are met for proper functionality.</span></span>

### <a name="partners-certified-for-teams"></a><span data-ttu-id="01d7d-127">チームの認定パートナー</span><span class="sxs-lookup"><span data-stu-id="01d7d-127">Partners certified for Teams</span></span>

<span data-ttu-id="01d7d-128">次のパートナーには、Teams の仮想デスクトップインフラストラクチャソリューションがあります。</span><span class="sxs-lookup"><span data-stu-id="01d7d-128">The following partners have virtual desktop infrastructure solutions for Teams.</span></span>

|<span data-ttu-id="01d7d-129">パートナー</span><span class="sxs-lookup"><span data-stu-id="01d7d-129">Partner</span></span>|<span data-ttu-id="01d7d-130">パートナーソリューション</span><span class="sxs-lookup"><span data-stu-id="01d7d-130">Partner solution</span></span>|
|----|---|
|![Citrix を表すロゴ](media/citrix.png)| <span data-ttu-id="01d7d-132"><a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix の仮想アプリとデスクトップ</a></span><span class="sxs-lookup"><span data-stu-id="01d7d-132"><a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix Virtual Apps and Desktops</a></span></span> |

### <a name="citrix-virtual-apps-and-desktops-requirements"></a><span data-ttu-id="01d7d-133">Citrix の仮想アプリとデスクトップの要件</span><span class="sxs-lookup"><span data-stu-id="01d7d-133">Citrix Virtual Apps and Desktops requirements</span></span>

<span data-ttu-id="01d7d-134">Citrix の仮想アプリとデスクトップ (以前は XenApp と XenDesktop) は、VDI 上の Teams で AV の最適化を実現します。</span><span class="sxs-lookup"><span data-stu-id="01d7d-134">Citrix Virtual Apps and Desktops (formerly known as XenApp and XenDesktop) provides AV optimization for Teams on VDI.</span></span> <span data-ttu-id="01d7d-135">Citrix の仮想アプリとデスクトップを使用すると、VDI 上の Teams では、チャットや共同作業に加えて、通話と会議機能がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="01d7d-135">With Citrix Virtual Apps and Desktops, Teams on VDI supports calling and meeting functionality in addition to chat and collaboration.</span></span>

<span data-ttu-id="01d7d-136">[このページで](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/)は、Citrix の仮想アプリとデスクトップの最新バージョンをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="01d7d-136">You can download the latest version of Citrix Virtual Apps and Desktops [here](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/).</span></span> <span data-ttu-id="01d7d-137">(最初にサインインする必要があります。)必要なコンポーネントは、既定で[Citrix Workspace アプリ (CWA)](https://www.citrix.com/downloads/workspace-app/)と仮想配信エージェント (VDA) にまとめられています。</span><span class="sxs-lookup"><span data-stu-id="01d7d-137">(You'll need to sign in first.) The necessary components are bundled into the [Citrix Workspace app (CWA)](https://www.citrix.com/downloads/workspace-app/) and Virtual Delivery Agent (VDA) by default.</span></span> <span data-ttu-id="01d7d-138">CWA または VDA に追加のコンポーネントまたはプラグインをインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="01d7d-138">You don't need to install any additional components or plugins on CWA or the VDA.</span></span>

<span data-ttu-id="01d7d-139">最新のサーバーとクライアントの要件については、[この Citrix の web サイト](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01d7d-139">For the latest server and client requirements, see [this Citrix website](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html).</span></span>

## <a name="install-or-update-the-teams-desktop-app-on-vdi"></a><span data-ttu-id="01d7d-140">VDI で Teams デスクトップアプリをインストールまたは更新する</span><span class="sxs-lookup"><span data-stu-id="01d7d-140">Install or update the Teams desktop app on VDI</span></span>

<span data-ttu-id="01d7d-141">MSI パッケージを使用してコンピューターごとのインストールまたはユーザーごとのインストールを使用して、VDI 用の Teams デスクトップアプリを展開することができます。</span><span class="sxs-lookup"><span data-stu-id="01d7d-141">You can deploy the Teams desktop app for VDI using a per-machine installation or per-user installation using the MSI package.</span></span> <span data-ttu-id="01d7d-142">使用する方法を決定するのは、永続的なセットアップと非永続的な設定のどちらを使用するか、または組織に関連する機能のニーズによって異なります。</span><span class="sxs-lookup"><span data-stu-id="01d7d-142">Deciding on which approach to use depends on whether you use a persistent or non-persistent setup and the associated functionality needs of your organization.</span></span>
<span data-ttu-id="01d7d-143">専用の永続的なセットアップの場合、どちらのアプローチも機能します。</span><span class="sxs-lookup"><span data-stu-id="01d7d-143">For a dedicated persistent setup, either approach would work.</span></span>  <span data-ttu-id="01d7d-144">ただし、非永続的なセットアップでは、チームが効率的に作業するために、コンピューターごとにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="01d7d-144">However, for a non-persistent setup, per-machine installation is required for Teams to work efficiently.</span></span> <span data-ttu-id="01d7d-145">「[非永続的なセットアップ](#non-persistent-setup)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="01d7d-145">See the [Non-persistent setup](#non-persistent-setup) section.</span></span>

<span data-ttu-id="01d7d-146">コンピューター単位のインストールでは、自動更新が無効になっています。</span><span class="sxs-lookup"><span data-stu-id="01d7d-146">With per-machine installation, automatic updates is disabled.</span></span> <span data-ttu-id="01d7d-147">つまり、Teams アプリを更新するには、現在のバージョンをアンインストールして、新しいバージョンに更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="01d7d-147">This means that to update the Teams app, you must uninstall the current version to update to a newer version.</span></span> <span data-ttu-id="01d7d-148">ユーザーごとのインストールでは、自動更新が有効になっています。</span><span class="sxs-lookup"><span data-stu-id="01d7d-148">With per-user installation, automatic updates is enabled.</span></span> <span data-ttu-id="01d7d-149">ほとんどの VDI の展開では、コンピューターごとのインストールを使用してチームを展開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="01d7d-149">For most VDI deployments, we recommend you deploy Teams using per-machine installation.</span></span>

<span data-ttu-id="01d7d-150">最新のチームバージョンに更新するには、まずアンインストール手順を実行し、次に最新のチームバージョン展開を実行します。</span><span class="sxs-lookup"><span data-stu-id="01d7d-150">To update to the latest Teams version, start with the uninstall procedure followed by latest Teams version deployment.</span></span>

<span data-ttu-id="01d7d-151">VDI 環境での Teams の AV 最適化を適切に機能させるには、シンクライアントエンドポイントがインターネットにアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="01d7d-151">For Teams AV optimization in VDI environments to work properly, the thin client endpoint must have access to the internet.</span></span> <span data-ttu-id="01d7d-152">インターネットアクセスがシンクライアントエンドポイントで利用できない場合、最適化の起動は成功しません。</span><span class="sxs-lookup"><span data-stu-id="01d7d-152">If internet access isn't available at the thin client endpoint, optimization startup won't be successful.</span></span> <span data-ttu-id="01d7d-153">これは、ユーザーが最適化されていないメディアの状態であることを意味します。</span><span class="sxs-lookup"><span data-stu-id="01d7d-153">This means that the user is in a non-optimized media state.</span></span>

#### <a name="dedicated-persistent-setup"></a><span data-ttu-id="01d7d-154">専用の永続的なセットアップ</span><span class="sxs-lookup"><span data-stu-id="01d7d-154">Dedicated persistent setup</span></span>

<span data-ttu-id="01d7d-155">専用の永続的なセットアップでは、ユーザーのローカルオペレーティングシステムに対する変更は、ユーザーがログオフした後も保持されます。</span><span class="sxs-lookup"><span data-stu-id="01d7d-155">In a dedicated persistent setup, users' local operating system changes are retained after users log off.</span></span>  <span data-ttu-id="01d7d-156">永続的なセットアップの場合、Teams はユーザーごととコンピューターごとの両方のインストールをサポートします。</span><span class="sxs-lookup"><span data-stu-id="01d7d-156">For persistent setup, Teams support both per-user and per-machine installation.</span></span>

<span data-ttu-id="01d7d-157">推奨される最小の VM 構成は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="01d7d-157">The following is the recommended minimum VM configuration.</span></span>

|<span data-ttu-id="01d7d-158">パラメーター</span><span class="sxs-lookup"><span data-stu-id="01d7d-158">Parameter</span></span>  |<span data-ttu-id="01d7d-159">ワークステーションオペレーティングシステム</span><span class="sxs-lookup"><span data-stu-id="01d7d-159">Workstation operating system</span></span>  |<span data-ttu-id="01d7d-160">サーバー操作システム</span><span class="sxs-lookup"><span data-stu-id="01d7d-160">Server operation system</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="01d7d-161">vCPU</span><span class="sxs-lookup"><span data-stu-id="01d7d-161">vCPU</span></span>   |    <span data-ttu-id="01d7d-162">2コア</span><span class="sxs-lookup"><span data-stu-id="01d7d-162">2 cores</span></span>     |  <span data-ttu-id="01d7d-163">4、6、または8</span><span class="sxs-lookup"><span data-stu-id="01d7d-163">4,6, or 8</span></span><br><span data-ttu-id="01d7d-164">基になる non-uniform memory access (NUMA) 構成を理解し、それに応じて Vm を構成することが重要です。</span><span class="sxs-lookup"><span data-stu-id="01d7d-164">It's important to understand the underlying non-uniform memory access (NUMA) configuration and configure your VMs accordingly.</span></span>     |
|<span data-ttu-id="01d7d-165">RAM</span><span class="sxs-lookup"><span data-stu-id="01d7d-165">RAM</span></span>     |   <span data-ttu-id="01d7d-166">4 GB</span><span class="sxs-lookup"><span data-stu-id="01d7d-166">4 GB</span></span>      | <span data-ttu-id="01d7d-167">512 ~ 1024 MB (ユーザーあたり)</span><span class="sxs-lookup"><span data-stu-id="01d7d-167">512 to 1024 MB per user</span></span>        |
|<span data-ttu-id="01d7d-168">ストレージ</span><span class="sxs-lookup"><span data-stu-id="01d7d-168">Storage</span></span>    | <span data-ttu-id="01d7d-169">8 GB</span><span class="sxs-lookup"><span data-stu-id="01d7d-169">8 GB</span></span>        | <span data-ttu-id="01d7d-170">40 ~ 60 GB</span><span class="sxs-lookup"><span data-stu-id="01d7d-170">40 to 60 GB</span></span>        |

#### <a name="non-persistent-setup"></a><span data-ttu-id="01d7d-171">非永続的なセットアップ</span><span class="sxs-lookup"><span data-stu-id="01d7d-171">Non-persistent setup</span></span>

<span data-ttu-id="01d7d-172">非永続的なセットアップでは、ユーザーのローカルオペレーティングシステムによる変更は、ユーザーがログオフした後も保持されません。</span><span class="sxs-lookup"><span data-stu-id="01d7d-172">In a non-persistent setup, users' local operating system changes are not retained after users log off.</span></span> <span data-ttu-id="01d7d-173">このようなセットアップは、一般的に共有されているマルチユーザーセッションです。</span><span class="sxs-lookup"><span data-stu-id="01d7d-173">Such setups are commonly shared multi-user sessions.</span></span> <span data-ttu-id="01d7d-174">VM 構成は、ユーザー数と利用可能な物理ボックスリソースによって異なります。</span><span class="sxs-lookup"><span data-stu-id="01d7d-174">VM configuration varies based on the number of users and available physical box resources.</span></span>

<span data-ttu-id="01d7d-175">非永続的なセットアップの場合、Teams デスクトップアプリはコンピューターごとにゴールデンイメージにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="01d7d-175">For a non-persistent setup, the Teams desktop app must be installed per-machine to the golden image.</span></span> <span data-ttu-id="01d7d-176">詳細については、「 [VDI 上の Teams デスクトップアプリをインストールまたは更新](#install-or-update-the-teams-desktop-app-on-vdi)する」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="01d7d-176">(To learn more, see the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section).</span></span> <span data-ttu-id="01d7d-177">これにより、ユーザーセッション中に Teams アプリを効率的に起動することができます。</span><span class="sxs-lookup"><span data-stu-id="01d7d-177">This ensures an efficient launch of the Teams app during a user session.</span></span> <span data-ttu-id="01d7d-178">非永続的なセットアップで Teams を使用する場合も、効率的な Teams のランタイムデータ同期のためのプロファイルキャッシュマネージャーが必要です。これにより、適切なユーザー固有の情報 (ユーザーデータ、プロファイル、設定など) がユーザーセッション中にキャッシュされます。</span><span class="sxs-lookup"><span data-stu-id="01d7d-178">Using Teams with a non-persistent setup also requires a profile caching manager for efficient Teams runtime data sync. This ensures that the appropriate user-specific information (for example, user data, profile, and settings) are cached during the user session.</span></span>  <span data-ttu-id="01d7d-179">さまざまなキャッシュマネージャーソリューションを利用できます。</span><span class="sxs-lookup"><span data-stu-id="01d7d-179">There are variety of caching manager solutions available.</span></span> <span data-ttu-id="01d7d-180">たとえば、 [Fslogix](https://docs.microsoft.com/fslogix/overview)となります。</span><span class="sxs-lookup"><span data-stu-id="01d7d-180">For example, [FSLogix](https://docs.microsoft.com/fslogix/overview).</span></span> <span data-ttu-id="01d7d-181">特定の構成手順については、キャッシュマネージャープロバイダーにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="01d7d-181">Consult your caching manager provider for specific configuration instructions.</span></span>

##### <a name="teams-cached-content-exclusion-list-for-non-persistent-setup"></a><span data-ttu-id="01d7d-182">非永続的なセットアップ用の Teams キャッシュされたコンテンツ除外リスト</span><span class="sxs-lookup"><span data-stu-id="01d7d-182">Teams cached content exclusion list for non-persistent setup</span></span>

<span data-ttu-id="01d7d-183">[Teams のキャッシュ] フォルダーから次のものを除外します。% appdata%/チーム/teams</span><span class="sxs-lookup"><span data-stu-id="01d7d-183">Exclude the following from the Teams caching folder, %appdata%/Microsoft/Teams.</span></span>  <span data-ttu-id="01d7d-184">これらのヘルプを除外すると、ユーザーのキャッシュサイズが小さくなり、非永続的なセットアップがさらに最適化されます。</span><span class="sxs-lookup"><span data-stu-id="01d7d-184">Excluding these help reduce the user caching size to further optimize your non-persistent setup.</span></span>

- <span data-ttu-id="01d7d-185">.txt ファイル</span><span class="sxs-lookup"><span data-stu-id="01d7d-185">.txt files</span></span>
- <span data-ttu-id="01d7d-186">メディアスタックフォルダー</span><span class="sxs-lookup"><span data-stu-id="01d7d-186">Media-stack folder</span></span>

### <a name="office-365-proplus-considerations"></a><span data-ttu-id="01d7d-187">Office 365 ProPlus の考慮事項</span><span class="sxs-lookup"><span data-stu-id="01d7d-187">Office 365 ProPlus considerations</span></span>

<span data-ttu-id="01d7d-188">Office 365 ProPlus で VDI に Teams を展開する場合は、次の点を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="01d7d-188">Consider the following when you deploy Teams with Office 365 ProPlus on VDI.</span></span>

#### <a name="new-deployments-of-teams-through-office-365-proplus"></a><span data-ttu-id="01d7d-189">Office 365 ProPlus を通じた Teams の新しい展開</span><span class="sxs-lookup"><span data-stu-id="01d7d-189">New deployments of Teams through Office 365 ProPlus</span></span>

<span data-ttu-id="01d7d-190">Office 365 ProPlus を通じてチームを展開する前に、コンピューターごとのインストールを使用して展開された既存の Teams アプリをアンインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="01d7d-190">Before you deploy Teams through Office 365 ProPlus, you must first uninstall any pre-existing Teams apps if they were deployed using per-machine installation.</span></span>

<span data-ttu-id="01d7d-191">Office 365 ProPlus を通じた Teams は、ユーザーごとにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="01d7d-191">Teams through Office 365 ProPlus is installed per-user.</span></span> <span data-ttu-id="01d7d-192">詳細については、「 [VDI 上の Teams デスクトップアプリをインストールまたは更新](#install-or-update-the-teams-desktop-app-on-vdi)する」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="01d7d-192">To learn more, see the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.</span></span>

#### <a name="teams-deployments-through-office-365-proplus-updates"></a><span data-ttu-id="01d7d-193">Office 365 ProPlus の更新プログラムを通じた Teams の展開</span><span class="sxs-lookup"><span data-stu-id="01d7d-193">Teams deployments through Office 365 ProPlus updates</span></span>

<span data-ttu-id="01d7d-194">Teams は、Office 365 ProPlus の既存のインストールにも追加されています。</span><span class="sxs-lookup"><span data-stu-id="01d7d-194">Teams is also being added to existing installations of Office 365 ProPlus.</span></span> <span data-ttu-id="01d7d-195">Office 365 ProPlus はユーザーごとにチームをインストールするため、「 [VDI 上の teams デスクトップアプリをインストールまたは更新](#install-or-update-the-teams-desktop-app-on-vdi)する」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="01d7d-195">Since Office 365 ProPlus installs Teams per-user only, see the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.</span></span>

#### <a name="using-teams-with-per-machine-installation-and-office-365-proplus"></a><span data-ttu-id="01d7d-196">コンピューターごとのインストールと Office 365 ProPlus で Teams を使用する</span><span class="sxs-lookup"><span data-stu-id="01d7d-196">Using Teams with per-machine installation and Office 365 ProPlus</span></span>

<span data-ttu-id="01d7d-197">Office 365 ProPlus では、各コンピューターの Teams のインストールをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="01d7d-197">Office 365 ProPlus doesn't support per-machine installations of Teams.</span></span> <span data-ttu-id="01d7d-198">コンピューターごとのインストールを使用するには、Office 365 ProPlus から Teams を除外する必要があります。</span><span class="sxs-lookup"><span data-stu-id="01d7d-198">To use per-machine installation, you must exclude Teams from Office 365 ProPlus.</span></span> <span data-ttu-id="01d7d-199">「 [Teams デスクトップアプリを VM に展開](#deploy-the-teams-desktop-app-to-the-vm)する」と「 [Office 365 ProPlus セクションを通じてチームの展開を除外する方法](#how-to-exclude-teams-deployment-through-office-365-proplus)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01d7d-199">See the [Deploy the Teams desktop app to the VM](#deploy-the-teams-desktop-app-to-the-vm) and [How to exclude Teams deployment through Office 365 ProPlus](#how-to-exclude-teams-deployment-through-office-365-proplus) sections.</span></span>

#### <a name="how-to-exclude-teams-deployment-through-office-365-proplus"></a><span data-ttu-id="01d7d-200">Office 365 ProPlus を通じてチームの展開を除外する方法</span><span class="sxs-lookup"><span data-stu-id="01d7d-200">How to exclude Teams deployment through Office 365 ProPlus</span></span>

<span data-ttu-id="01d7d-201">Teams と Office 365 ProPlus の詳細については、「 [office 365 ProPlus の新しいインストールからチームを除外する](https://docs.microsoft.com/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-office-365-proplus)」および「[グループポリシーを使って teams のインストールを制御](https://docs.microsoft.com/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01d7d-201">To learn more about Teams and Office 365 ProPlus, see [How to exclude Teams from new installations of Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-office-365-proplus) and [Use Group Policy to control the installation of Teams](https://docs.microsoft.com/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams).</span></span>

### <a name="deploy-the-teams-desktop-app-to-the-vm"></a><span data-ttu-id="01d7d-202">Teams デスクトップアプリを VM に展開する</span><span class="sxs-lookup"><span data-stu-id="01d7d-202">Deploy the Teams desktop app to the VM</span></span>

1. <span data-ttu-id="01d7d-203">次のリンクのいずれかを使用して、VDI VM オペレーティングシステムと一致する Teams MSI パッケージをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="01d7d-203">Download the Teams MSI package that matches your VDI VM operating system using one of the following links:</span></span>

    - [<span data-ttu-id="01d7d-204">32ビット版</span><span class="sxs-lookup"><span data-stu-id="01d7d-204">32-bit version</span></span>](https://statics.teams.cdn.office.net/production-windows/1.2.00.32462/Teams_windows.msi)
    - [<span data-ttu-id="01d7d-205">64ビット版</span><span class="sxs-lookup"><span data-stu-id="01d7d-205">64-bit version</span></span>](https://statics.teams.cdn.office.net/production-windows-x64/1.2.00.32462/Teams_windows_x64.msi)

    <span data-ttu-id="01d7d-206">必要な Teams デスクトップアプリの最小バージョンはバージョン1.2.00.31357 です。</span><span class="sxs-lookup"><span data-stu-id="01d7d-206">The minimum version of the Teams desktop app that's required is version 1.2.00.31357.</span></span> <span data-ttu-id="01d7d-207">(PSTN 保留は以前のバージョンではサポートされていません)。</span><span class="sxs-lookup"><span data-stu-id="01d7d-207">(PSTN hold is not supported in earlier versions.)</span></span>

2. <span data-ttu-id="01d7d-208">次のいずれかのコマンドを実行して、MSI を VDI VM にインストールします。</span><span class="sxs-lookup"><span data-stu-id="01d7d-208">Install the MSI to the VDI VM by running one of the following commands:</span></span>

    - <span data-ttu-id="01d7d-209">ユーザーごとのインストール (既定)</span><span class="sxs-lookup"><span data-stu-id="01d7d-209">Per-user installation  (default)</span></span>
  
        ```
        msiexec /i <path_to_msi> /l*v <install_logfile_name>
        ```
    
        <span data-ttu-id="01d7d-210">これは既定のインストールです。チームは、% AppData% ユーザーフォルダーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="01d7d-210">This is the default installation, which installs Teams to the %AppData% user folder.</span></span> <span data-ttu-id="01d7d-211">この時点で、ゴールデンイメージのセットアップが完了しています。</span><span class="sxs-lookup"><span data-stu-id="01d7d-211">At this point, the golden image setup is complete.</span></span> <span data-ttu-id="01d7d-212">ユーザー単位のインストールでは、非永続的なセットアップでは、チームは適切に動作しません。</span><span class="sxs-lookup"><span data-stu-id="01d7d-212">Teams will not work properly with per-user installation on a non-persistent setup.</span></span>
    
    - <span data-ttu-id="01d7d-213">マシン単位のインストール</span><span class="sxs-lookup"><span data-stu-id="01d7d-213">Per-machine installation</span></span>

        ```
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1
        ```

        <span data-ttu-id="01d7d-214">これにより、チームは64ビットオペレーティングシステムの Program Files (x86) フォルダーと、32ビットオペレーティングシステムの Program Files フォルダーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="01d7d-214">This installs Teams to the Program Files (x86) folder on a 64-bit operating system and to the Program Files folder on a 32-bit operating system.</span></span> <span data-ttu-id="01d7d-215">この時点で、ゴールデンイメージのセットアップが完了しています。</span><span class="sxs-lookup"><span data-stu-id="01d7d-215">At this point, the golden image setup is complete.</span></span> <span data-ttu-id="01d7d-216">非永続的なセットアップでは、コンピューターごとにチームをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="01d7d-216">Installing Teams per-machine is required for non-persistent setups.</span></span>
 
        <span data-ttu-id="01d7d-217">次の対話型ログオンセッションでは、チームが起動し、資格情報を求められます。</span><span class="sxs-lookup"><span data-stu-id="01d7d-217">The next interactive logon session starts Teams and asks for credentials.</span></span>

3. <span data-ttu-id="01d7d-218">VDI VM から MSI をアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="01d7d-218">Uninstall the MSI from the VDI VM.</span></span> 

    <span data-ttu-id="01d7d-219">Teams をアンインストールするには、次の2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="01d7d-219">There are two ways to uninstall Teams:</span></span>  
  
    - <span data-ttu-id="01d7d-220">PowerShell スクリプト (推奨): この[PowerShell スクリプト](scripts/powershell-script-teams-deployment-clean-up.md)を使用して、ターゲットコンピューターまたはユーザーからチームをクリーンアップできます。</span><span class="sxs-lookup"><span data-stu-id="01d7d-220">PowerShell script (recommended): You can use this [PowerShell script](scripts/powershell-script-teams-deployment-clean-up.md) to clean up Teams from target machines or users.</span></span> <span data-ttu-id="01d7d-221">ターゲットコンピューター上のすべてのユーザーに対して実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="01d7d-221">It should be executed for every user on a targeted machine.</span></span> 
    
    - <span data-ttu-id="01d7d-222">コマンドライン: この方法ではチームが削除されますが、Teams の再インストールはできません。</span><span class="sxs-lookup"><span data-stu-id="01d7d-222">Command line: This approach removes Teams, yet prevents re-installation of Teams.</span></span> <span data-ttu-id="01d7d-223">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="01d7d-223">Run the following command:</span></span>
  
      ```
      msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>
      ```
      <span data-ttu-id="01d7d-224">これにより、オペレーティングシステムの環境に応じて、Program Files (x86) フォルダーまたは Program Files フォルダーから Teams がアンインストールされます。</span><span class="sxs-lookup"><span data-stu-id="01d7d-224">This uninstalls Teams from the Program Files (x86) folder or Program Files folder, depending on the operating system environment.</span></span>

## <a name="teams-on-vdi-performance-considerations"></a><span data-ttu-id="01d7d-225">VDI のパフォーマンスに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="01d7d-225">Teams on VDI performance considerations</span></span>

<span data-ttu-id="01d7d-226">さまざまな仮想化設定構成があり、それぞれが最適化のために異なるフォーカスが設定されています。</span><span class="sxs-lookup"><span data-stu-id="01d7d-226">There are variety of virtualized setup configurations, each with a different focus for optimization.</span></span> <span data-ttu-id="01d7d-227">たとえば、ユーザーの密度。</span><span class="sxs-lookup"><span data-stu-id="01d7d-227">For example, user density.</span></span> <span data-ttu-id="01d7d-228">計画するときは、組織の作業負荷のニーズに合わせて、次の点を考慮してセットアップを最適化します。</span><span class="sxs-lookup"><span data-stu-id="01d7d-228">When planning, consider the following to help optimize your setup based on the workload needs of your organization:</span></span>

- <span data-ttu-id="01d7d-229">最小要件: 一部のワークロードでは、最小要件を超えるリソースを使用してセットアップを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="01d7d-229">Minimum requirement: Some workloads may require a setup using resources that are above the minimum requirements.</span></span> <span data-ttu-id="01d7d-230">たとえば、より多くのコンピューティングリソースを必要とするアプリケーションを使用している開発者向けのワークロード。</span><span class="sxs-lookup"><span data-stu-id="01d7d-230">For example, workloads for developers who use applications that demand more computing resources.</span></span>
- <span data-ttu-id="01d7d-231">依存関係: チームデスクトップアプリ以外のインフラストラクチャ、作業負荷、その他の環境配慮への依存関係が含まれます。</span><span class="sxs-lookup"><span data-stu-id="01d7d-231">Dependencies: These include dependencies on infrastructure, workload, and other environmental considerations outside the Teams desktop app.</span></span>
- <span data-ttu-id="01d7d-232">VDI で無効になっている機能: Teams では、VDI による負荷の高い機能を無効にします。これにより、一時的な CPU 使用率の向上に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="01d7d-232">Disabled features on VDI: Teams disables GPU-intensive features for VDI, which can help improve transient CPU utilization.</span></span> <span data-ttu-id="01d7d-233">次の機能は無効になります。</span><span class="sxs-lookup"><span data-stu-id="01d7d-233">The following features are disabled:</span></span>
    - <span data-ttu-id="01d7d-234">Teams CSS アニメーション</span><span class="sxs-lookup"><span data-stu-id="01d7d-234">Teams CSS animation</span></span>
    - <span data-ttu-id="01d7d-235">Giphy 自動開始</span><span class="sxs-lookup"><span data-stu-id="01d7d-235">Giphy auto-start</span></span>

## <a name="teams-on-vdi-with-calling-and-meetings"></a><span data-ttu-id="01d7d-236">通話と会議を使った VDI 上の Teams</span><span class="sxs-lookup"><span data-stu-id="01d7d-236">Teams on VDI with calling and meetings</span></span>

<span data-ttu-id="01d7d-237">チャットと共同作業に加えて、通話と会議のサポートを備えた VDI の Teams は、Citrix ベースのプラットフォームで利用できます。</span><span class="sxs-lookup"><span data-stu-id="01d7d-237">In addition to chat and collaboration, Teams on VDI with calling and meeting support is available with Citrix-based platforms.</span></span> <span data-ttu-id="01d7d-238">サポートされている機能は、WebRTC メディアスタックと Citrix 固有の実装に基づいています。</span><span class="sxs-lookup"><span data-stu-id="01d7d-238">Supported features are based on the WebRTC media stack and Citrix-specific implementation.</span></span> <span data-ttu-id="01d7d-239">次の図は、アーキテクチャの概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="01d7d-239">The following diagram provides an overview of the architecture.</span></span>

![VDI アーキテクチャ上の Teams を示す図](media/teams-on-vdi-architecture.png)

<span data-ttu-id="01d7d-241">以下の通話および会議機能はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="01d7d-241">These calling and meeting features are not supported:</span></span>

- <span data-ttu-id="01d7d-242">緊急電話サービスの強化</span><span class="sxs-lookup"><span data-stu-id="01d7d-242">Enhanced emergency services</span></span>
- <span data-ttu-id="01d7d-243">Teams アプリとデバイス間の HID ボタンと LED コントロール</span><span class="sxs-lookup"><span data-stu-id="01d7d-243">HID buttons and LED controls between the Teams app and devices</span></span>
- <span data-ttu-id="01d7d-244">背景のぼかしと効果</span><span class="sxs-lookup"><span data-stu-id="01d7d-244">Background blur and effects</span></span>
- <span data-ttu-id="01d7d-245">ブロードキャスト/ライブイベント</span><span class="sxs-lookup"><span data-stu-id="01d7d-245">Broadcast/live events</span></span>
- <span data-ttu-id="01d7d-246">位置情報に基づくルーティング (LBR)</span><span class="sxs-lookup"><span data-stu-id="01d7d-246">Location-Based Routing (LBR)</span></span>
- <span data-ttu-id="01d7d-247">コール パーク</span><span class="sxs-lookup"><span data-stu-id="01d7d-247">Call park</span></span>
- <span data-ttu-id="01d7d-248">通話キュー</span><span class="sxs-lookup"><span data-stu-id="01d7d-248">Call queue</span></span>

> [!IMPORTANT]
> <span data-ttu-id="01d7d-249">現在、AV を最適化せずに team を VDI で実行していて、最適化のためにまだサポートされていない機能を使用している場合 (アプリの共有時に制御を許可する場合など)、[Teams] ポリシーを設定して Teams のリダイレクションを無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="01d7d-249">If you currently run Teams without AV optimization in VDI and you use features that are not supported yet for optimization (such as Give and take control when app sharing), you have to set Citrix policies to turn off Teams redirection.</span></span> <span data-ttu-id="01d7d-250">これは、Teams メディアセッションが最適化されないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="01d7d-250">This means that Teams media sessions won’t be optimized.</span></span> <span data-ttu-id="01d7d-251">Teams のリダイレクションを無効にするポリシーを設定する手順については、この[Citrix の web サイト](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/policies/reference/ica-policy-settings/multimedia-policy-settings.html)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01d7d-251">For steps on how to set policies to turn off Teams redirection, see this [Citrix website](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/policies/reference/ica-policy-settings/multimedia-policy-settings.html).</span></span>

<span data-ttu-id="01d7d-252">現時点では、VDI 以外の環境でのみ利用可能な通話と会議機能の追加に取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="01d7d-252">We're working on adding calling and meeting features that are currently only available in non-VDI environments.</span></span> <span data-ttu-id="01d7d-253">これには、品質、追加の画面共有シナリオ、チームに最近追加された高度な機能など、より多くの管理者の制御が含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="01d7d-253">These may include more admin control over quality, additional screen sharing scenarios, and advanced features recently added to Teams.</span></span> <span data-ttu-id="01d7d-254">今後の機能の詳細については、チームの担当者にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="01d7d-254">Contact your Teams representative to learn more about upcoming features.</span></span>

### <a name="network-requirements"></a><span data-ttu-id="01d7d-255">ネットワーク要件</span><span class="sxs-lookup"><span data-stu-id="01d7d-255">Network requirements</span></span>

<span data-ttu-id="01d7d-256">クラウドの全体的な音声とビデオの展開に影響を与える可能性のあるリスクと要件を特定するために、環境を評価することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="01d7d-256">We recommend that you evaluate your environment to identify any risks and requirements that can influence your overall cloud voice and video deployment.</span></span> <span data-ttu-id="01d7d-257">[Skype For Business ネットワーク評価ツール](https://www.microsoft.com/download/details.aspx?id=53885)を使用して、自分のネットワークが Teams に対応しているかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="01d7d-257">Use the [Skype for Business Network Assessment Tool](https://www.microsoft.com/download/details.aspx?id=53885) to test whether your network is ready for Teams.</span></span>

<span data-ttu-id="01d7d-258">Teams のネットワークを準備する方法について詳しくは、「 [teams 用に組織のネットワークを準備](prepare-network.md)する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="01d7d-258">To learn more about how to prepare your network for Teams, see [Prepare your organization's network for  Teams](prepare-network.md).</span></span>

### <a name="migrate-from-skype-for-business-on-vdi-to-teams-on-vdi"></a><span data-ttu-id="01d7d-259">Vdi での Skype for Business から VDI 上の Teams への移行</span><span class="sxs-lookup"><span data-stu-id="01d7d-259">Migrate from Skype for Business on VDI to Teams on VDI</span></span>

<span data-ttu-id="01d7d-260">Vdi での Skype for Business から VDI 上の Teams への移行を行っている場合、2つのアプリケーションの違いに加えて、VDI も実装するといくつかの違いがあります。</span><span class="sxs-lookup"><span data-stu-id="01d7d-260">If you're migrating from Skype for Business on VDI to Teams on VDI, besides the differences between the two applications, there are some differences when VDI is also implemented.</span></span> <span data-ttu-id="01d7d-261">Skype for Business VDI で現在サポートされていない Teams VDI の機能には、次のような機能があります。</span><span class="sxs-lookup"><span data-stu-id="01d7d-261">Some capabilities that aren’t currently supported in Teams VDI that are in Skype for Business VDI are as follows:</span></span>

- <span data-ttu-id="01d7d-262">メディアのビットレートを制限するためのポリシーを使った VDI 通話エクスペリエンスの制御</span><span class="sxs-lookup"><span data-stu-id="01d7d-262">Control of VDI calling experiences with policies for limiting media bitrate</span></span>
- <span data-ttu-id="01d7d-263">VDI の一部の AV 機能を無効にするプラットフォームごとのポリシー</span><span class="sxs-lookup"><span data-stu-id="01d7d-263">Per-platform policy to disable some AV features in VDI</span></span>
- <span data-ttu-id="01d7d-264">アプリ共有を行うときの制御</span><span class="sxs-lookup"><span data-stu-id="01d7d-264">Give and take control when app sharing</span></span>
- <span data-ttu-id="01d7d-265">音声なしのチャットからの画面共有</span><span class="sxs-lookup"><span data-stu-id="01d7d-265">Screen share from chat without audio</span></span>
- <span data-ttu-id="01d7d-266">同時にビデオと画面共有の送受信を行うことができる</span><span class="sxs-lookup"><span data-stu-id="01d7d-266">Simultaneous video and screen sharing send and receive</span></span>

### <a name="teams-on-chrome-browser-versus-teams-desktop-app-for-vdi"></a><span data-ttu-id="01d7d-267">Chrome ブラウザーと VDI 用 Teams デスクトップアプリのチーム</span><span class="sxs-lookup"><span data-stu-id="01d7d-267">Teams on Chrome browser versus Teams desktop app for VDI</span></span>

<span data-ttu-id="01d7d-268">Chrome ブラウザーの teams では、AV の最適化を備えた VDI 用の Teams デスクトップアプリに代わる機能は提供されていません。</span><span class="sxs-lookup"><span data-stu-id="01d7d-268">Teams on Chrome browser doesn't provide a replacement for the Teams desktop app for VDI with AV optimization.</span></span> <span data-ttu-id="01d7d-269">チャットと共同作業のエクスペリエンスは期待どおりに動作します。</span><span class="sxs-lookup"><span data-stu-id="01d7d-269">The chat and collaboration experience works as expected.</span></span> <span data-ttu-id="01d7d-270">メディアが必要な場合は、Chrome ブラウザーでユーザーの期待を満たせない場合があります。</span><span class="sxs-lookup"><span data-stu-id="01d7d-270">When media is needed, there are some experiences that may not meet user expectations on the Chrome browser:</span></span>

- <span data-ttu-id="01d7d-271">オーディオとビデオのストリーミングのエクスペリエンスが最適でないことがあります。</span><span class="sxs-lookup"><span data-stu-id="01d7d-271">The audio and video streaming experience may not be optimal.</span></span> <span data-ttu-id="01d7d-272">ユーザーには、遅延または品質の低下が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="01d7d-272">Users may experiences delays or reduced quality.</span></span>
- <span data-ttu-id="01d7d-273">[デバイスの設定] は [ブラウザーの設定] では利用できません。</span><span class="sxs-lookup"><span data-stu-id="01d7d-273">Device settings aren't available in browser settings.</span></span>
- <span data-ttu-id="01d7d-274">デバイス管理はブラウザーで処理され、ブラウザーの [サイトの設定] では複数の設定が必要です。</span><span class="sxs-lookup"><span data-stu-id="01d7d-274">Device management is handled through the browser and requires multiple settings in browser site settings.</span></span>
- <span data-ttu-id="01d7d-275">デバイスの設定は、Windows デバイス管理でも設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="01d7d-275">Device settings may also need to be set in Windows device management.</span></span>

## <a name="teams-on-vdi-with-chat-and-collaboration"></a><span data-ttu-id="01d7d-276">チャットと共同作業による VDI on Teams</span><span class="sxs-lookup"><span data-stu-id="01d7d-276">Teams on VDI with chat and collaboration</span></span>

<span data-ttu-id="01d7d-277">組織で Teams のチャット機能と共同作業機能のみを使用する場合は、ユーザーレベルのポリシーを設定して、Teams の呼び出しと会議の機能を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="01d7d-277">If your organization wants to only use chat and collaboration features in Teams, you can set user-level policies to turn off calling and meeting functionality in Teams.</span></span> <span data-ttu-id="01d7d-278">この機能レベルでは、Citrix 仮想アプリとデスクトップは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="01d7d-278">This feature level doesn't require Citrix Virtual Apps and Desktops.</span></span>

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a><span data-ttu-id="01d7d-279">通話と会議の機能を無効にするポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="01d7d-279">Set policies to turn off calling and meeting functionality</span></span>

<span data-ttu-id="01d7d-280">ポリシーを設定するには、Microsoft Teams 管理センターまたは PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="01d7d-280">You can set policies by using the Microsoft Teams admin center or PowerShell.</span></span> <span data-ttu-id="01d7d-281">ポリシーの変更が反映されるまでには、多少時間がかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="01d7d-281">It can take some time (a few hours) for the policy changes to propagate.</span></span> <span data-ttu-id="01d7d-282">特定のアカウントの変更がすぐに表示されない場合は、数時間後にもう一度お試しください。</span><span class="sxs-lookup"><span data-stu-id="01d7d-282">If you don’t see changes for a given account immediately, try again in a few hours.</span></span>

<span data-ttu-id="01d7d-283">[**通話ポリシー**](teams-calling-policy.md): Teams には組み込みの DisallowCalling 通話ポリシーが含まれており、すべての通話機能がオフになっています。</span><span class="sxs-lookup"><span data-stu-id="01d7d-283">[**Calling polices**](teams-calling-policy.md): Teams includes the built-in DisallowCalling calling policy, in which all calling features are turned off.</span></span> <span data-ttu-id="01d7d-284">仮想化された環境で Teams を使用する組織内のすべてのユーザーに DisallowCalling ポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="01d7d-284">Assign the DisallowCalling policy to all users in your organization who use Teams in a virtualized environment.</span></span>

<span data-ttu-id="01d7d-285">[**会議ポリシー**](meeting-policies-in-teams.md): Teams には、すべての会議機能がオフになっている組み込みの "いいね!" の会議ポリシーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="01d7d-285">[**Meeting policies**](meeting-policies-in-teams.md): Teams includes the built-in AllOff meeting policy, in which all meeting features are turned off.</span></span> <span data-ttu-id="01d7d-286">仮想化された環境で Teams を使用する組織内のすべてのユーザーに対して、割り当てられた Ff ポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="01d7d-286">Assign the AllOff policy to all users in your organization who use Teams in a virtualized environment.</span></span>

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a><span data-ttu-id="01d7d-287">Microsoft Teams 管理センターを使用してポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="01d7d-287">Assign policies using the Microsoft Teams admin center</span></span>

<span data-ttu-id="01d7d-288">DisallowCalling の通話ポリシーと、割り当てられているユーザーに割り当てることができる会議ポリシーを割り当てるには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="01d7d-288">To assign the DisallowCalling calling policy and the AllOff meeting policy to users, follow these steps:</span></span>

1. <span data-ttu-id="01d7d-289">Microsoft Teams 管理センターの左のナビゲーションで、[**ユーザー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="01d7d-289">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="01d7d-290">ユーザー名の左側をクリックしてユーザーを選び、[**設定の編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="01d7d-290">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="01d7d-291">次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="01d7d-291">Do the following:</span></span>
    1.  <span data-ttu-id="01d7d-292">[**通話ポリシー**] で [ **DisallowCalling**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="01d7d-292">Under **Calling policy**, click **DisallowCalling**.</span></span>
    2.  <span data-ttu-id="01d7d-293">[**会議のポリシー**] で、[割り当てる]**をクリックし**ます。</span><span class="sxs-lookup"><span data-stu-id="01d7d-293">Under **Meeting policy**, click **AllOff**.</span></span>
4. <span data-ttu-id="01d7d-294">[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="01d7d-294">Click **Apply**.</span></span>

<span data-ttu-id="01d7d-295">一度に複数のユーザーにポリシーを割り当てるには、「[チームのユーザー設定を一括](edit-user-settings-in-bulk.md)して編集する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01d7d-295">To assign a policy to multiple users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="01d7d-296">または、次の操作も行うことができます。</span><span class="sxs-lookup"><span data-stu-id="01d7d-296">Or, you can also do the following:</span></span>

1. <span data-ttu-id="01d7d-297">Microsoft Teams 管理センターの左のナビゲーションで、割り当てるポリシーに移動します。</span><span class="sxs-lookup"><span data-stu-id="01d7d-297">In the left navigation of the Microsoft Teams admin center, go to the policy you want to assign.</span></span> <span data-ttu-id="01d7d-298">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="01d7d-298">For example:</span></span>
    - <span data-ttu-id="01d7d-299">[**音声** > **通話のポリシー**] に移動し、[ **DisallowCalling**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="01d7d-299">Go to **Voice** > **Calling policies**, and then click **DisallowCalling**.</span></span>
    - <span data-ttu-id="01d7d-300">[**会議** > の**ポリシー**] に移動して、[割り当てる**ff**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="01d7d-300">Go to **Meetings** > **Meeting policies**, and then click **AllOff**.</span></span>
3. <span data-ttu-id="01d7d-301">[**ユーザーの管理**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="01d7d-301">Select **Manage users**.</span></span>
4. <span data-ttu-id="01d7d-302">[**ユーザーの管理**] ウィンドウで、[表示名] または [ユーザー名] でユーザーを検索し、名前を選択して [**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="01d7d-302">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="01d7d-303">追加するユーザーごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="01d7d-303">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="01d7d-304">ユーザーの追加が完了したら、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="01d7d-304">When you're finished adding users, click **Save**.</span></span>

#### <a name="assign-policies-using-powershell"></a><span data-ttu-id="01d7d-305">PowerShell を使用してポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="01d7d-305">Assign policies using PowerShell</span></span>

<span data-ttu-id="01d7d-306">次の例は、 [Grant-CsteamDisallowCalling のポリシー](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy)を使って、ユーザーにの呼び出しポリシーを割り当てる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="01d7d-306">The following example shows how to use the [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) to assign the DisallowCalling calling policy to a user.</span></span>

```
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity “user email id”
```

<span data-ttu-id="01d7d-307">PowerShell を使用して通話ポリシーを管理する方法の詳細については、「 [Set-Csteam拡張性のポリシー](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="01d7d-307">To learn more about using PowerShell to manage calling policies, see [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).</span></span>

<span data-ttu-id="01d7d-308">次の例は、CsTeamsMeetingPolicy を使用して、[グラント](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy)ff 会議ポリシーをユーザーに割り当てる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="01d7d-308">The following example shows how to use the [Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) to assign the AllOff meeting policy to a user.</span></span>

```
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity “user email id”
```

<span data-ttu-id="01d7d-309">PowerShell を使用して会議のポリシーを管理する方法の詳細については、「 [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01d7d-309">To learn more about using PowerShell to manage meeting policies, see [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>

## <a name="migrate-teams-on-vdi-with-chat-and-collaboration-to-citrix-with-calling-and-meetings"></a><span data-ttu-id="01d7d-310">通話と会議を使って、VDI 上のチームをチャットとコラボレーションで Citrix に移行する</span><span class="sxs-lookup"><span data-stu-id="01d7d-310">Migrate Teams on VDI with chat and collaboration to Citrix with calling and meetings</span></span>

<span data-ttu-id="01d7d-311">ユーザーレベルのポリシーを設定して、通話と会議機能を無効にしている場合に、チャットと共同作業を行っている VDI 上の Teams の既存の実装がある場合、AV 最適化を有効にして Citrix に移行するには、ポリシーを設定する必要があります。VDI ユーザー向けのチームの会議機能。</span><span class="sxs-lookup"><span data-stu-id="01d7d-311">If you have an existing implementation of Teams on VDI with chat and collaboration in which you had set user-level policies to turn off calling and meeting functionality, and you're migrating to Citrix with AV optimization, you must set policies to turn on calling and meeting functionality for those Teams on VDI users.</span></span>

### <a name="set-policies-to-turn-on-calling-and-meeting-functionality"></a><span data-ttu-id="01d7d-312">通話と会議の機能を有効にするポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="01d7d-312">Set policies to turn on calling and meeting functionality</span></span>

<span data-ttu-id="01d7d-313">Microsoft Teams 管理センターまたは PowerShell を使用して、通話と会議のポリシーを設定し、ユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="01d7d-313">You can use the Microsoft Teams admin center or PowerShell to set and assign calling and meeting policies to your users.</span></span> <span data-ttu-id="01d7d-314">ポリシーの変更が反映されるまでには、多少時間がかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="01d7d-314">It can take some time (a few hours) for policy changes to propagate.</span></span> <span data-ttu-id="01d7d-315">特定のアカウントの変更がすぐに表示されない場合は、数時間後にもう一度お試しください。</span><span class="sxs-lookup"><span data-stu-id="01d7d-315">If you don’t see changes for a given account immediately, try again after a few hours.</span></span>

<span data-ttu-id="01d7d-316">[**通話**](teams-calling-policy.md)ポリシー: Teams の通話ポリシーは、ユーザーが使用できる通話機能を制御します。</span><span class="sxs-lookup"><span data-stu-id="01d7d-316">[**Calling polices**](teams-calling-policy.md): Calling policies in Teams control which calling features are available to users.</span></span> <span data-ttu-id="01d7d-317">Teams には、組み込みの AllowCalling 通話ポリシーが含まれており、すべての通話機能が有効になっています。</span><span class="sxs-lookup"><span data-stu-id="01d7d-317">Teams includes the built-in AllowCalling calling policy, in which all calling features are turned on.</span></span> <span data-ttu-id="01d7d-318">すべての通話機能を有効にするには、AllowCalling ポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="01d7d-318">To turn on all calling features, assign the AllowCalling policy.</span></span> <span data-ttu-id="01d7d-319">または、カスタム通話ポリシーを作成して、必要な通話機能を有効にし、ユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="01d7d-319">Or, create a custom calling policy to turn on the calling features that you want and assign it to users.</span></span> 

<span data-ttu-id="01d7d-320">[**会議ポリシー**](meeting-policies-in-teams.md): Teams の会議ポリシーは、ユーザーが作成できる会議の種類と、組織内のユーザーによってスケジュールされている会議の参加者が使用できる機能を制御します。</span><span class="sxs-lookup"><span data-stu-id="01d7d-320">[**Meeting policies**](meeting-policies-in-teams.md): Meeting policies in Teams control the types of meetings that users can create and the features that are available to meeting participants that are scheduled by users in your organization.</span></span> <span data-ttu-id="01d7d-321">Teams には、すべての会議機能が有効になっている組み込みのすべての会議のポリシーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="01d7d-321">Teams includes the built-in AllOn meeting policy, in which all meeting features are turned on.</span></span> <span data-ttu-id="01d7d-322">すべての会議機能を有効にするには、[すべて] のポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="01d7d-322">To turn on all meeting features, assign the AllOn policy.</span></span> <span data-ttu-id="01d7d-323">または、カスタム会議ポリシーを作成して、必要な会議機能を有効にし、ユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="01d7d-323">Or, create a custom meeting policy to turn on the meeting features that you want and assign it users.</span></span>

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a><span data-ttu-id="01d7d-324">Microsoft Teams 管理センターを使用してポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="01d7d-324">Assign policies using the Microsoft Teams admin center</span></span>

<span data-ttu-id="01d7d-325">AllowCalling の通話ポリシーと [すべての会議] ポリシーをユーザーに割り当てるには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="01d7d-325">To assign the AllowCalling calling policy and the AllOn meeting policy to users, follow these steps:</span></span>

1. <span data-ttu-id="01d7d-326">Microsoft Teams 管理センターの左のナビゲーションで、[**ユーザー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="01d7d-326">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="01d7d-327">ユーザー名の左側をクリックしてユーザーを選び、[**設定の編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="01d7d-327">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="01d7d-328">次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="01d7d-328">Do the following:</span></span>
    1.  <span data-ttu-id="01d7d-329">[**通話ポリシー**] で [ **allowcalling**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="01d7d-329">Under **Calling policy**, click **AllowCalling**.</span></span>
    2.  <span data-ttu-id="01d7d-330">[**会議のポリシー**] で [**すべて**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="01d7d-330">Under **Meeting policy**, click **AllOn**.</span></span>
4. <span data-ttu-id="01d7d-331">[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="01d7d-331">Click **Apply**.</span></span>

<span data-ttu-id="01d7d-332">一度に複数のユーザーにポリシーを割り当てるには、「[チームのユーザー設定を一括](edit-user-settings-in-bulk.md)して編集する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01d7d-332">To assign a policy to multiple users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="01d7d-333">または、次の操作も行うことができます。</span><span class="sxs-lookup"><span data-stu-id="01d7d-333">Or, you can also do the following:</span></span>

1. <span data-ttu-id="01d7d-334">Microsoft Teams 管理センターの左のナビゲーションで、割り当てるポリシーに移動します。</span><span class="sxs-lookup"><span data-stu-id="01d7d-334">In the left navigation of the Microsoft Teams admin center, go to the policy you want to assign.</span></span> <span data-ttu-id="01d7d-335">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="01d7d-335">For example:</span></span>
    - <span data-ttu-id="01d7d-336">[**音声** > **通話のポリシー**] に移動し、[ **allowcalling**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="01d7d-336">Go to **Voice** > **Calling policies**, and then click **AllowCalling**.</span></span>
    - <span data-ttu-id="01d7d-337">[**会議** > の**ポリシー**] に移動し、[**すべて**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="01d7d-337">Go to **Meetings** > **Meeting policies**, and then click **AllOn**.</span></span>
3. <span data-ttu-id="01d7d-338">[**ユーザーの管理**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="01d7d-338">Select **Manage users**.</span></span>
4. <span data-ttu-id="01d7d-339">[**ユーザーの管理**] ウィンドウで、[表示名] または [ユーザー名] でユーザーを検索し、名前を選択して [**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="01d7d-339">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="01d7d-340">追加するユーザーごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="01d7d-340">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="01d7d-341">ユーザーの追加が完了したら、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="01d7d-341">When you're finished adding users, click **Save**.</span></span>

#### <a name="assign-policies-using-powershell"></a><span data-ttu-id="01d7d-342">PowerShell を使用してポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="01d7d-342">Assign policies using PowerShell</span></span>

<span data-ttu-id="01d7d-343">次の例は、 [Grant-Csteam分解のポリシー](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy)を使って、allowcalling 呼び出しポリシーをユーザーに割り当てる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="01d7d-343">The following example shows how to use the [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) to assign the AllowCalling calling policy to a user.</span></span>

```
Grant-CsTeamsCallingPolicy -PolicyName AllowCalling -Identity “user email id”
```

<span data-ttu-id="01d7d-344">PowerShell を使用して通話ポリシーを管理する方法の詳細については、「 [Set-Csteam拡張性のポリシー](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="01d7d-344">To learn more about using PowerShell to manage calling policies, see [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).</span></span>

<span data-ttu-id="01d7d-345">次の例は、 [CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy)を使用して、すべての会議ポリシーをユーザーに割り当てる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="01d7d-345">The following example shows how to use the [Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) to assign the AllOn meeting policy to a user.</span></span>

```
Grant-CsTeamsMeetingPolicy -PolicyName AllOn -Identity “user email id”
```

<span data-ttu-id="01d7d-346">PowerShell を使用して会議のポリシーを管理する方法の詳細については、「 [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01d7d-346">To learn more about using PowerShell to manage meeting policies, see [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>

## <a name="known-issues-and-limitations"></a><span data-ttu-id="01d7d-347">既知の問題と制限事項</span><span class="sxs-lookup"><span data-stu-id="01d7d-347">Known issues and limitations</span></span>

### <a name="client-deployment-installation-and-setup"></a><span data-ttu-id="01d7d-348">クライアントの展開、インストール、セットアップ</span><span class="sxs-lookup"><span data-stu-id="01d7d-348">Client deployment, installation, and setup</span></span>

- <span data-ttu-id="01d7d-349">コンピューターごとにインストールする場合、vdi の Teams は非 VDI Teams クライアントとして自動的に更新されることはありません。</span><span class="sxs-lookup"><span data-stu-id="01d7d-349">With per-machine installation, Teams on VDI isn't automatically updated in the way that non-VDI Teams clients are.</span></span> <span data-ttu-id="01d7d-350">「 [VDI 上の Teams デスクトップアプリをインストールまたは更新](#install-or-update-the-teams-desktop-app-on-vdi)する」セクションで説明されているように、新しい MSI をインストールして VM イメージを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="01d7d-350">You have to update the VM image by installing a new MSI as described in the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.</span></span> <span data-ttu-id="01d7d-351">最新バージョンに更新するには、現在のバージョンをアンインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="01d7d-351">You must uninstall the current version to update to a newer version.</span></span>
- <span data-ttu-id="01d7d-352">チームは、ユーザーごとまたはコンピューターごとに展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="01d7d-352">Teams should be deployed either per user or per machine.</span></span> <span data-ttu-id="01d7d-353">同時ユーザー数とコンピューター単位のチームの展開はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="01d7d-353">Deployment of Teams for concurrent per user and per machine is not supported.</span></span>  <span data-ttu-id="01d7d-354">コンピューターごとまたはユーザーごとに、これらのモードのいずれかに移行するには、アンインストール手順に従い、どちらかのモードに再展開します。</span><span class="sxs-lookup"><span data-stu-id="01d7d-354">To migrate from either per machine or per user to one of these modes, follow the uninstall procedure and redeploy to either mode.</span></span>
- <span data-ttu-id="01d7d-355">現時点では、MacOs および Linux ベースのクライアントは Citrix でサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="01d7d-355">MacOs and Linux-based clients are not supported by Citrix at this time.</span></span>
- <span data-ttu-id="01d7d-356">Citrix は、エンドポイントで定義された明示的な HTTP プロキシの使用をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="01d7d-356">Citrix doesn't support the use of explicit HTTP proxies defined on an endpoint.</span></span> 

### <a name="calling-and-meetings"></a><span data-ttu-id="01d7d-357">通話と会議</span><span class="sxs-lookup"><span data-stu-id="01d7d-357">Calling and meetings</span></span>

- <span data-ttu-id="01d7d-358">Skype for Business の相互運用性は音声通話に限定され、ビデオ表示には使用できません。</span><span class="sxs-lookup"><span data-stu-id="01d7d-358">Interoperability with Skype for Business is limited to audio calls, no video modality.</span></span>
- <span data-ttu-id="01d7d-359">デュアルトーンマルチ周波数 (DTMF) テレフォニーシステムとの相互操作は、現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="01d7d-359">Dual Tone Multi Frequency (DTMF) interaction with telephony systems  is currently not supported.</span></span>
- <span data-ttu-id="01d7d-360">匿名ユーザーとして Teams 会議に参加することは、AV-最適化されていません。</span><span class="sxs-lookup"><span data-stu-id="01d7d-360">Joining Teams meetings as an anonymous user isn't AV-optimized.</span></span> <span data-ttu-id="01d7d-361">ユーザーは会議に参加し、最適化されていない操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="01d7d-361">The user can join the meeting and have a non-optimized experience.</span></span>
- <span data-ttu-id="01d7d-362">会議またはグループ通話でサポートされているビデオストリームは1つだけです。</span><span class="sxs-lookup"><span data-stu-id="01d7d-362">Only a single incoming video stream is supported in meetings or group calls.</span></span> <span data-ttu-id="01d7d-363">複数のユーザーがビデオを送信する場合、常に表示されている主要なスピーカーのビデオのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="01d7d-363">When multiple people send video, only the dominant speaker's video is shown at any given time.</span></span>  
- <span data-ttu-id="01d7d-364">着信と発信のビデオストリームの解像度は720p の解像度に制限されています。</span><span class="sxs-lookup"><span data-stu-id="01d7d-364">Incoming and outgoing video stream resolution is limited to 720p resolution.</span></span> <span data-ttu-id="01d7d-365">これは WebRTC の制限です。</span><span class="sxs-lookup"><span data-stu-id="01d7d-365">This is a WebRTC limitation.</span></span>
- <span data-ttu-id="01d7d-366">着信カメラまたは画面共有ストリームのビデオストリームは1つだけです。</span><span class="sxs-lookup"><span data-stu-id="01d7d-366">Only one video stream from an incoming camera or screen share stream is supported.</span></span> <span data-ttu-id="01d7d-367">受信画面共有が表示されている場合は、その画面共有が、優先スピーカーのビデオではなく、画面上に表示されます。</span><span class="sxs-lookup"><span data-stu-id="01d7d-367">When there's an incoming screen share, that screen share is shown it instead of the video of the dominant speaker.</span></span>
- <span data-ttu-id="01d7d-368">送信画面の共有:</span><span class="sxs-lookup"><span data-stu-id="01d7d-368">Outgoing screen sharing:</span></span>
    - <span data-ttu-id="01d7d-369">アプリケーション共有はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="01d7d-369">Application sharing is not supported.</span></span>
- <span data-ttu-id="01d7d-370">コントロールを用意して制御します。</span><span class="sxs-lookup"><span data-stu-id="01d7d-370">Give control and take control:</span></span>  
    - <span data-ttu-id="01d7d-371">画面共有またはアプリケーション共有セッション中はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="01d7d-371">Not supported during a screen sharing or application sharing session.</span></span>
    - <span data-ttu-id="01d7d-372">PowerPoint 共有セッション中にサポートされます。</span><span class="sxs-lookup"><span data-stu-id="01d7d-372">Supported during a PowerPoint sharing session.</span></span>  
- <span data-ttu-id="01d7d-373">CWA での高 DPI スケーリングはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="01d7d-373">High DPI scaling on CWA is not supported.</span></span>

<span data-ttu-id="01d7d-374">VDI に関連していない Teams の既知の問題については、「 [teams の既知の問題](Known-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01d7d-374">For Teams known issues that aren’t related to VDI, see [Known issues for Teams](Known-issues.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="01d7d-375">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="01d7d-375">Troubleshooting</span></span>

#### <a name="troubleshoot-citrix-components"></a><span data-ttu-id="01d7d-376">Citrix コンポーネントのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="01d7d-376">Troubleshoot Citrix components</span></span>

<span data-ttu-id="01d7d-377">VDA と CWA の問題を解決する方法については、[この Citrix の web サイト](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01d7d-377">For information on how to troubleshoot VDA and CWA issues, see [this Citrix website](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html).</span></span>

## <a name="related-topics"></a><span data-ttu-id="01d7d-378">関連項目</span><span class="sxs-lookup"><span data-stu-id="01d7d-378">Related topics</span></span>

- [<span data-ttu-id="01d7d-379">MSI を使用して Microsoft Teams をインストールする</span><span class="sxs-lookup"><span data-stu-id="01d7d-379">Install Microsoft Teams using MSI</span></span>](msi-deployment.md)
- [<span data-ttu-id="01d7d-380">Teams での PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="01d7d-380">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
