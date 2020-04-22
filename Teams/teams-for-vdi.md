---
title: 仮想デスクトップ インフラストラクチャ用の Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi, jmorrow
audience: admin
description: 仮想デスクトップ インフラストラクチャ (VDI) 環境で Microsoft Teams を実行する方法について説明します。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 43adfb71c287677a6390d371a05bd1aea35ceda3
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779986"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a><span data-ttu-id="63748-103">仮想デスクトップ インフラストラクチャ用の Teams</span><span class="sxs-lookup"><span data-stu-id="63748-103">Teams for Virtualized Desktop Infrastructure</span></span>

<span data-ttu-id="63748-104">この記事では、仮想化環境で Microsoft Teams を使用する場合の要件と制限について説明します。</span><span class="sxs-lookup"><span data-stu-id="63748-104">This article describes the requirements and limitations for using Microsoft Teams in a virtualized environment.</span></span>

## <a name="what-is-vdi"></a><span data-ttu-id="63748-105">VDI とは何ですか ?</span><span class="sxs-lookup"><span data-stu-id="63748-105">What is VDI?</span></span>

<span data-ttu-id="63748-106">仮想デスクトップ インフラストラクチャ (VDI) は、データセンターの集中サーバーでデスクトップ オペレーティング システムとアプリケーションをホストする仮想化テクノロジです。</span><span class="sxs-lookup"><span data-stu-id="63748-106">Virtual Desktop Infrastructure (VDI) is virtualization technology that hosts a desktop operating system and applications on a centralized server in a data center.</span></span> <span data-ttu-id="63748-107">これにより、完全に保護され、準拠し一元化されたソースとともに、ユーザーに完全に個人用に設定されたデスクトップ エクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="63748-107">This enables a fully personalized desktop experience to users with a fully secured and compliant centralized source.</span></span>
 
<span data-ttu-id="63748-108">仮想化環境の Microsoft Teams はチャットと共同作業をサポートし、Citrix プラットフォームを使用すれば、通話および会議機能もサポートされています。</span><span class="sxs-lookup"><span data-stu-id="63748-108">Microsoft Teams in a virtualized environment supports chat and collaboration, and with the Citrix platform, calling and meeting functionality are also supported.</span></span>

<span data-ttu-id="63748-109">仮想化環境の Teams は、複数の構成をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="63748-109">Teams in a virtualized environment supports multiple configurations.</span></span> <span data-ttu-id="63748-110">これらには、VDI、専用モード、共有モード、永続モード、非永続モードが含まれます。</span><span class="sxs-lookup"><span data-stu-id="63748-110">These include VDI, dedicated, shared, persistent and non-persistent modes.</span></span> <span data-ttu-id="63748-111">機能は継続的に開発され、定期的に追加されます。機能は今後数か月または数年で拡張されます。</span><span class="sxs-lookup"><span data-stu-id="63748-111">Features are in continuous development and are added on a regular basis, and functionality will expand in the coming months and years.</span></span>
 
<span data-ttu-id="63748-112">仮想化環境での Teams の使用は、非仮想化環境での Teams の使用とは多少異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="63748-112">Using Teams in a virtualized environment may be somewhat different from using Teams in a non-virtualized environment.</span></span> <span data-ttu-id="63748-113">たとえば、仮想化環境では一部の高度な機能が利用できず、ビデオ解像度が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="63748-113">For example, some advanced features may not be available in a virtualized environment and video resolution may differ.</span></span> <span data-ttu-id="63748-114">最適なユーザー エクスペリエンスを確保するには、この記事のガイダンスに従ってください。</span><span class="sxs-lookup"><span data-stu-id="63748-114">To ensure an optimal user experience, follow the guidance in this article.</span></span>

## <a name="teams-on-vdi-components"></a><span data-ttu-id="63748-115">VDI 上の Teams のコンポーネント</span><span class="sxs-lookup"><span data-stu-id="63748-115">Teams on VDI components</span></span>

<span data-ttu-id="63748-116">仮想化環境で Teams を使用するには、次のコンポーネントが必要です。</span><span class="sxs-lookup"><span data-stu-id="63748-116">Using Teams in a virtualized environment requires the following components.</span></span>

- <span data-ttu-id="63748-117">**仮想化ブローカー**: Azure などの仮想化プロバイダーへのリソースおよび接続マネージャー</span><span class="sxs-lookup"><span data-stu-id="63748-117">**Virtualization broker**: The resource and connection manager to the virtualization provider, such as Azure</span></span>
- <span data-ttu-id="63748-118">**仮想デスクトップ**: Microsoft Teams を実行する仮想マシン (VM) スタック</span><span class="sxs-lookup"><span data-stu-id="63748-118">**Virtual desktop**: The Virtual Machine (VM) stack that runs Microsoft Teams</span></span>
- <span data-ttu-id="63748-119">**シン クライアント**: ユーザーが物理的にやり取りするエンドポイント</span><span class="sxs-lookup"><span data-stu-id="63748-119">**Thin client**: The endpoint that the user physically interfaces with</span></span>
- <span data-ttu-id="63748-120">**Teams デスクトップ アプリ**: これは Teams デスクトップ クライアント アプリです</span><span class="sxs-lookup"><span data-stu-id="63748-120">**Teams desktop app**: This is the Teams desktop client app</span></span>

## <a name="teams-on-vdi-requirements"></a><span data-ttu-id="63748-121">VDI 上の Teams の要件</span><span class="sxs-lookup"><span data-stu-id="63748-121">Teams on VDI requirements</span></span>

### <a name="virtualization-provider-requirements"></a><span data-ttu-id="63748-122">仮想化プロバイダーの要件</span><span class="sxs-lookup"><span data-stu-id="63748-122">Virtualization provider requirements</span></span>

<span data-ttu-id="63748-123">Teams デスクトップ アプリは、主要な仮想化ソリューション プロバイダーで検証済みです。</span><span class="sxs-lookup"><span data-stu-id="63748-123">The Teams desktop app was validated with leading virtualization solution providers.</span></span> <span data-ttu-id="63748-124">複数の市場プロバイダーを使用している場合は、仮想化ソリューション プロバイダーに相談し、最低限の要件が満たされていることの確認をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="63748-124">With multiple market providers, we recommend that you consult your virtualization solution provider to ensure minimum requirements are met.</span></span>
  
<span data-ttu-id="63748-125">現在、オーディオ/ビデオ (AV) 最適化を備えた VDI 上の Teams は、Citrix で認定されています。</span><span class="sxs-lookup"><span data-stu-id="63748-125">Currently, Teams on VDI with audio/video (AV) optimization is certified with Citrix.</span></span> <span data-ttu-id="63748-126">このセクションの情報を確認して、Citrix と Teams の両方の要件が適切に満たされていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="63748-126">Review the information in this section to ensure both Citrix and Teams requirements are met for proper functionality.</span></span>

### <a name="partners-certified-for-teams"></a><span data-ttu-id="63748-127">Teams 認定パートナー</span><span class="sxs-lookup"><span data-stu-id="63748-127">Partners certified for Teams</span></span>

<span data-ttu-id="63748-128">次のパートナーには、Teams 用の仮想デスクトップ インフラストラクチャ ソリューションがあります。</span><span class="sxs-lookup"><span data-stu-id="63748-128">The following partners have virtual desktop infrastructure solutions for Teams.</span></span>

|<span data-ttu-id="63748-129">パートナー</span><span class="sxs-lookup"><span data-stu-id="63748-129">Partner</span></span>|<span data-ttu-id="63748-130">パートナー ソリューション</span><span class="sxs-lookup"><span data-stu-id="63748-130">Partner solution</span></span>|
|----|---|
|![Citrix を表すロゴ](media/citrix.png)| <span data-ttu-id="63748-132"><a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix Virtual Apps and Desktops</a></span><span class="sxs-lookup"><span data-stu-id="63748-132"><a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix Virtual Apps and Desktops</a></span></span> |

### <a name="citrix-virtual-apps-and-desktops-requirements"></a><span data-ttu-id="63748-133">Citrix Virtual Apps and Desktops の要件</span><span class="sxs-lookup"><span data-stu-id="63748-133">Citrix Virtual Apps and Desktops requirements</span></span>

<span data-ttu-id="63748-134">Citrix Virtual Apps and Desktops (以前の XenApp および XenDesktop) は、VDI 上の Teams に AV 最適化を提供します。</span><span class="sxs-lookup"><span data-stu-id="63748-134">Citrix Virtual Apps and Desktops (formerly known as XenApp and XenDesktop) provides AV optimization for Teams on VDI.</span></span> <span data-ttu-id="63748-135">Citrix Virtual Apps and Desktops を使用すると、VDI 上の Teams はチャットと共同作業に加えて、通話および会議機能をサポートします。</span><span class="sxs-lookup"><span data-stu-id="63748-135">With Citrix Virtual Apps and Desktops, Teams on VDI supports calling and meeting functionality in addition to chat and collaboration.</span></span>

<span data-ttu-id="63748-136">Citrix Virtual Apps and Desktops の最新バージョンは、[こちら](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/)からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="63748-136">You can download the latest version of Citrix Virtual Apps and Desktops [here](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/).</span></span> <span data-ttu-id="63748-137">(最初にサインインする必要があります。) 必要なコンポーネントは、デフォルトで [Citrix Workspace アプリ (CWA)](https://www.citrix.com/downloads/workspace-app/) および Virtual Delivery Agent (VDA) にバンドルされています。</span><span class="sxs-lookup"><span data-stu-id="63748-137">(You'll need to sign in first.) The necessary components are bundled into the [Citrix Workspace app (CWA)](https://www.citrix.com/downloads/workspace-app/) and Virtual Delivery Agent (VDA) by default.</span></span> <span data-ttu-id="63748-138">CWA や VDA に追加のコンポーネントやプラグインをインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="63748-138">You don't need to install any additional components or plugins on CWA or the VDA.</span></span>

<span data-ttu-id="63748-139">サーバーおよびクライアントの最新の要件については、[この Citrix Web サイト](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63748-139">For the latest server and client requirements, see [this Citrix website](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html).</span></span>

## <a name="install-or-update-the-teams-desktop-app-on-vdi"></a><span data-ttu-id="63748-140">VDI で Teams デスクトップ アプリをインストールまたは更新する</span><span class="sxs-lookup"><span data-stu-id="63748-140">Install or update the Teams desktop app on VDI</span></span>

<span data-ttu-id="63748-141">MSI パッケージを使用したマシンごとのインストールまたはユーザーごとのインストールを用いて、VDI 用の Teams デスクトップ アプリを展開できます。</span><span class="sxs-lookup"><span data-stu-id="63748-141">You can deploy the Teams desktop app for VDI using a per-machine installation or per-user installation using the MSI package.</span></span> <span data-ttu-id="63748-142">どのアプローチを使用するかについては、永続的なセットアップを使用するか、または非永続的なセットアップを使用するか、および組織の関連機能のニーズに応じて決定します。</span><span class="sxs-lookup"><span data-stu-id="63748-142">Deciding on which approach to use depends on whether you use a persistent or non-persistent setup and the associated functionality needs of your organization.</span></span>
<span data-ttu-id="63748-143">専用の永続的なセットアップの場合、どちらのアプローチでも機能します。</span><span class="sxs-lookup"><span data-stu-id="63748-143">For a dedicated persistent setup, either approach would work.</span></span>  <span data-ttu-id="63748-144">ただし、非永続的なセットアップの場合、Teams が効率的に機能するにはマシンごとのインストールが必要です。</span><span class="sxs-lookup"><span data-stu-id="63748-144">However, for a non-persistent setup, per-machine installation is required for Teams to work efficiently.</span></span> <span data-ttu-id="63748-145">[非永続のセットアップ](#non-persistent-setup)のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="63748-145">See the [Non-persistent setup](#non-persistent-setup) section.</span></span>

<span data-ttu-id="63748-146">マシンごとのインストールでは、自動更新は無効になっています。</span><span class="sxs-lookup"><span data-stu-id="63748-146">With per-machine installation, automatic updates is disabled.</span></span> <span data-ttu-id="63748-147">つまり、Teams アプリを更新するには、現在のバージョンをアンインストールして新しいバージョンに更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="63748-147">This means that to update the Teams app, you must uninstall the current version to update to a newer version.</span></span> <span data-ttu-id="63748-148">ユーザーごとのインストールでは、自動更新は有効になっています。</span><span class="sxs-lookup"><span data-stu-id="63748-148">With per-user installation, automatic updates is enabled.</span></span> <span data-ttu-id="63748-149">ほとんどの VDI の展開について、マシンごとのインストールを使用して Teams を展開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="63748-149">For most VDI deployments, we recommend you deploy Teams using per-machine installation.</span></span>

<span data-ttu-id="63748-150">最新の Teams バージョンに更新するには、アンインストール手順から始めて、次に最新の Teams バージョンを展開します。</span><span class="sxs-lookup"><span data-stu-id="63748-150">To update to the latest Teams version, start with the uninstall procedure followed by latest Teams version deployment.</span></span>

<span data-ttu-id="63748-151">VDI 環境での Teams AV の最適化が適切に機能するには、シン クライアント エンドポイントがインターネットにアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="63748-151">For Teams AV optimization in VDI environments to work properly, the thin client endpoint must have access to the internet.</span></span> <span data-ttu-id="63748-152">シン クライアント エンドポイントでインターネット アクセスが利用できない場合、最適化のスタートアップは成功しません。</span><span class="sxs-lookup"><span data-stu-id="63748-152">If internet access isn't available at the thin client endpoint, optimization startup won't be successful.</span></span> <span data-ttu-id="63748-153">これは、ユーザーが最適化されていないメディア状態にあることを意味します。</span><span class="sxs-lookup"><span data-stu-id="63748-153">This means that the user is in a non-optimized media state.</span></span>

#### <a name="dedicated-persistent-setup"></a><span data-ttu-id="63748-154">専用の永続的なセットアップ</span><span class="sxs-lookup"><span data-stu-id="63748-154">Dedicated persistent setup</span></span>

<span data-ttu-id="63748-155">専用の永続的なセットアップでは、ユーザーのローカル オペレーティング システムの変更は、ユーザーがログオフした後も保持されます。</span><span class="sxs-lookup"><span data-stu-id="63748-155">In a dedicated persistent setup, users' local operating system changes are retained after users log off.</span></span>  <span data-ttu-id="63748-156">永続的なセットアップの場合、Teams はユーザーごとのインストールとマシンごとのインストールの両方をサポートします。</span><span class="sxs-lookup"><span data-stu-id="63748-156">For persistent setup, Teams support both per-user and per-machine installation.</span></span>

<span data-ttu-id="63748-157">推奨される最低限の VM 構成は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="63748-157">The following is the recommended minimum VM configuration.</span></span>

|<span data-ttu-id="63748-158">パラメーター</span><span class="sxs-lookup"><span data-stu-id="63748-158">Parameter</span></span>  |<span data-ttu-id="63748-159">ワークステーションのオペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="63748-159">Workstation operating system</span></span>  |<span data-ttu-id="63748-160">サーバーのオペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="63748-160">Server operation system</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="63748-161">vCPU</span><span class="sxs-lookup"><span data-stu-id="63748-161">vCPU</span></span>   |    <span data-ttu-id="63748-162">2 コア</span><span class="sxs-lookup"><span data-stu-id="63748-162">2 cores</span></span>     |  <span data-ttu-id="63748-163">4、6、または 8。</span><span class="sxs-lookup"><span data-stu-id="63748-163">4,6, or 8</span></span><br><span data-ttu-id="63748-164">基礎となる Non-Uniform Memory Access (NUMA) 構成を理解し、それに応じて VM を構成することが重要です。</span><span class="sxs-lookup"><span data-stu-id="63748-164">It's important to understand the underlying non-uniform memory access (NUMA) configuration and configure your VMs accordingly.</span></span>     |
|<span data-ttu-id="63748-165">RAM</span><span class="sxs-lookup"><span data-stu-id="63748-165">RAM</span></span>     |   <span data-ttu-id="63748-166">4 GB</span><span class="sxs-lookup"><span data-stu-id="63748-166">4 GB</span></span>      | <span data-ttu-id="63748-167">ユーザー 1 人あたり 512 から 1024 MB</span><span class="sxs-lookup"><span data-stu-id="63748-167">512 to 1024 MB per user</span></span>        |
|<span data-ttu-id="63748-168">ストレージ</span><span class="sxs-lookup"><span data-stu-id="63748-168">Storage</span></span>    | <span data-ttu-id="63748-169">8 GB</span><span class="sxs-lookup"><span data-stu-id="63748-169">8 GB</span></span>        | <span data-ttu-id="63748-170">40 から 60 GB</span><span class="sxs-lookup"><span data-stu-id="63748-170">40 to 60 GB</span></span>        |

#### <a name="non-persistent-setup"></a><span data-ttu-id="63748-171">非永続的なセットアップ</span><span class="sxs-lookup"><span data-stu-id="63748-171">Non-persistent setup</span></span>

<span data-ttu-id="63748-172">非永続的なセットアップでは、ユーザーのローカル オペレーティング システムの変更は、ユーザーがログオフした後は保持されません。</span><span class="sxs-lookup"><span data-stu-id="63748-172">In a non-persistent setup, users' local operating system changes are not retained after users log off.</span></span> <span data-ttu-id="63748-173">このようなセットアップは、一般的に共有マルチユーザー セッションです。</span><span class="sxs-lookup"><span data-stu-id="63748-173">Such setups are commonly shared multi-user sessions.</span></span> <span data-ttu-id="63748-174">VM 構成は、ユーザー数と使用可能な物理ボックス リソースによって異なります。</span><span class="sxs-lookup"><span data-stu-id="63748-174">VM configuration varies based on the number of users and available physical box resources.</span></span>

<span data-ttu-id="63748-175">非永続的なセットアップの場合、Teams デスクトップ アプリは、ゴールデン イメージに対してマシンごとにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="63748-175">For a non-persistent setup, the Teams desktop app must be installed per-machine to the golden image.</span></span> <span data-ttu-id="63748-176">(詳細に関しては、[VDI での Teams デスクトップ アプリのインストールまたは更新](#install-or-update-the-teams-desktop-app-on-vdi)セクションを参照してください) これにより、Teams アプリがユーザー セッション中でも効率的に起動できるようになります。</span><span class="sxs-lookup"><span data-stu-id="63748-176">(To learn more, see the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.) This ensures an efficient launch of the Teams app during a user session.</span></span> <span data-ttu-id="63748-177">非永続的なセットアップで Teams を使用するには、効率的な Teams ランタイム データ同期のためにプロファイル キャッシュ マネージャーも必要です。これにより、ユーザー セッション中に適切なユーザー固有の情報 (たとえば、ユーザー データ、プロファイル、設定) が確実にキャッシュされます。</span><span class="sxs-lookup"><span data-stu-id="63748-177">Using Teams with a non-persistent setup also requires a profile caching manager for efficient Teams runtime data sync. This ensures that the appropriate user-specific information (for example, user data, profile, and settings) are cached during the user session.</span></span>  <span data-ttu-id="63748-178">さまざまなキャッシュ マネージャー ソリューションが利用可能です。</span><span class="sxs-lookup"><span data-stu-id="63748-178">There are a variety of caching manager solutions available.</span></span> <span data-ttu-id="63748-179">たとえば、[FSLogix](https://docs.microsoft.com/fslogix/overview) があります。</span><span class="sxs-lookup"><span data-stu-id="63748-179">For example, [FSLogix](https://docs.microsoft.com/fslogix/overview).</span></span> <span data-ttu-id="63748-180">具体的な構成手順については、キャッシュ マネージャー プロバイダーに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="63748-180">Consult your caching manager provider for specific configuration instructions.</span></span>

##### <a name="teams-cached-content-exclusion-list-for-non-persistent-setup"></a><span data-ttu-id="63748-181">Teams は、非永続的なセットアップ用のコンテンツ除外リストをキャッシュしました</span><span class="sxs-lookup"><span data-stu-id="63748-181">Teams cached content exclusion list for non-persistent setup</span></span>

<span data-ttu-id="63748-182">Teams キャッシュ フォルダー %appdata%/Microsoft/Teams から以下を除外します。</span><span class="sxs-lookup"><span data-stu-id="63748-182">Exclude the following from the Teams caching folder, %appdata%/Microsoft/Teams.</span></span>  <span data-ttu-id="63748-183">これらを除外すると、ユーザーのキャッシュ サイズが小さくなり、非永続的なセットアップがさらに最適化されます。</span><span class="sxs-lookup"><span data-stu-id="63748-183">Excluding these help reduce the user caching size to further optimize your non-persistent setup.</span></span>

- <span data-ttu-id="63748-184">.txt ファイル</span><span class="sxs-lookup"><span data-stu-id="63748-184">.txt files</span></span>
- <span data-ttu-id="63748-185">メディアスタック フォルダー</span><span class="sxs-lookup"><span data-stu-id="63748-185">Media-stack folder</span></span>

### <a name="microsoft-365-apps-for-enterprise-considerations"></a><span data-ttu-id="63748-186">企業向けの Microsoft 365 アプリの考慮事項</span><span class="sxs-lookup"><span data-stu-id="63748-186">Microsoft 365 Apps for enterprise considerations</span></span>

<span data-ttu-id="63748-187">VDI で企業向けの Microsoft 365 アプリを使用して Teams を展開する場合は、次の点を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="63748-187">Consider the following when you deploy Teams with Microsoft 365 Apps for enterprise on VDI.</span></span>

#### <a name="new-deployments-of-teams-through-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="63748-188">Microsoft 365 アプリを使用した、エンタープライズ向けの新しいチーム展開</span><span class="sxs-lookup"><span data-stu-id="63748-188">New deployments of Teams through Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="63748-189">企業向けの Microsoft 365 アプリを使用してチームを展開する前に、コンピューターごとのインストールを使用して展開された既存の Teams アプリをアンインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="63748-189">Before you deploy Teams through Microsoft 365 Apps for enterprise, you must first uninstall any pre-existing Teams apps if they were deployed using per-machine installation.</span></span>

<span data-ttu-id="63748-190">企業向けの Microsoft 365 アプリを使用した Teams は、ユーザーごとにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="63748-190">Teams through Microsoft 365 Apps for enterprise is installed per-user.</span></span> <span data-ttu-id="63748-191">詳細については、[VDI で Teams デスクトップ アプリをインストールまたは更新する](#install-or-update-the-teams-desktop-app-on-vdi)セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="63748-191">To learn more, see the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.</span></span>

#### <a name="teams-deployments-through-microsoft-365-apps-for-enterprise-updates"></a><span data-ttu-id="63748-192">Microsoft 365 アプリを使用した、エンタープライズアップデート向けの Teams の展開</span><span class="sxs-lookup"><span data-stu-id="63748-192">Teams deployments through Microsoft 365 Apps for enterprise updates</span></span>

<span data-ttu-id="63748-193">Teams は、エンタープライズ向けの Microsoft 365 アプリの既存のインストールにも追加されています。</span><span class="sxs-lookup"><span data-stu-id="63748-193">Teams is also being added to existing installations of Microsoft 365 Apps for enterprise.</span></span> <span data-ttu-id="63748-194">エンタープライズ用の Microsoft 365 アプリでは、ユーザーごとにチームをインストールするため、「 [VDI 上の teams デスクトップアプリをインストールまたは更新](#install-or-update-the-teams-desktop-app-on-vdi)する」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="63748-194">Since Microsoft 365 Apps for enterprise installs Teams per-user only, see the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.</span></span>

#### <a name="using-teams-with-per-machine-installation-and-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="63748-195">コンピューターごとのインストールと Microsoft 365 アプリでの Teams の使用 (エンタープライズ向け)</span><span class="sxs-lookup"><span data-stu-id="63748-195">Using Teams with per-machine installation and Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="63748-196">エンタープライズ向けの Microsoft 365 アプリでは、各コンピューターの Teams インストールをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="63748-196">Microsoft 365 Apps for enterprise doesn't support per-machine installations of Teams.</span></span> <span data-ttu-id="63748-197">コンピューターごとのインストールを使用するには、enterprise 用の Microsoft 365 アプリから Teams を除外する必要があります。</span><span class="sxs-lookup"><span data-stu-id="63748-197">To use per-machine installation, you must exclude Teams from Microsoft 365 Apps for enterprise.</span></span> <span data-ttu-id="63748-198">「 [Teams デスクトップアプリを VM に展開](#deploy-the-teams-desktop-app-to-the-vm)する」および「[エンタープライズ向けの Microsoft 365 アプリを通じてチームの展開を除外する方法](#how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63748-198">See the [Deploy the Teams desktop app to the VM](#deploy-the-teams-desktop-app-to-the-vm) and [How to exclude Teams deployment through Microsoft 365 Apps for enterprise](#how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise) sections.</span></span>

#### <a name="how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="63748-199">企業向けの Microsoft 365 アプリからチームの展開を除外する方法</span><span class="sxs-lookup"><span data-stu-id="63748-199">How to exclude Teams deployment through Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="63748-200">企業向けのチームおよび Microsoft 365 アプリの詳細については、「 [enterprise 用の microsoft 365 アプリの新しいインストールからチームを除外する](https://docs.microsoft.com/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-office-365-proplus)」および「[グループポリシーを使用して teams のインストールを制御](https://docs.microsoft.com/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams)する方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63748-200">To learn more about Teams and Microsoft 365 Apps for enterprise, see [How to exclude Teams from new installations of Microsoft 365 Apps for enterprise](https://docs.microsoft.com/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-office-365-proplus) and [Use Group Policy to control the installation of Teams](https://docs.microsoft.com/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams).</span></span>

### <a name="deploy-the-teams-desktop-app-to-the-vm"></a><span data-ttu-id="63748-201">Teams デスクトップ アプリを VM に展開する</span><span class="sxs-lookup"><span data-stu-id="63748-201">Deploy the Teams desktop app to the VM</span></span>

1. <span data-ttu-id="63748-202">次のリンクのいずれかを使用して、VDI VM オペレーティング システムに一致する Teams MSI パッケージをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="63748-202">Download the Teams MSI package that matches your VDI VM operating system using one of the following links:</span></span>

    - [<span data-ttu-id="63748-203">32 ビット版</span><span class="sxs-lookup"><span data-stu-id="63748-203">32-bit version</span></span>](https://statics.teams.cdn.office.net/production-windows/1.3.00.4461/Teams_windows.msi)
    - [<span data-ttu-id="63748-204">64 ビット版</span><span class="sxs-lookup"><span data-stu-id="63748-204">64-bit version</span></span>](https://statics.teams.cdn.office.net/production-windows-x64/1.3.00.4461/Teams_windows_x64.msi)

    <span data-ttu-id="63748-205">必要な Teams デスクトップアプリの最小バージョンはバージョン1.3.00.4461 です。</span><span class="sxs-lookup"><span data-stu-id="63748-205">The minimum version of the Teams desktop app that's required is version 1.3.00.4461.</span></span> <span data-ttu-id="63748-206">(PSTN ホールドは以前のバージョンではサポートされていません。)</span><span class="sxs-lookup"><span data-stu-id="63748-206">(PSTN hold is not supported in earlier versions.)</span></span>

2. <span data-ttu-id="63748-207">次のコマンドのいずれかを実行して、MSI を VDI VM にインストールします。</span><span class="sxs-lookup"><span data-stu-id="63748-207">Install the MSI to the VDI VM by running one of the following commands:</span></span>

    - <span data-ttu-id="63748-208">ユーザーごとのインストール (既定)</span><span class="sxs-lookup"><span data-stu-id="63748-208">Per-user installation  (default)</span></span>
  
        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSERS=1
        ```

        <span data-ttu-id="63748-209">これは、Teams を %AppData% ユーザー フォルダーにインストールする既定のインストールです。</span><span class="sxs-lookup"><span data-stu-id="63748-209">This is the default installation, which installs Teams to the %AppData% user folder.</span></span> <span data-ttu-id="63748-210">この時点で、ゴールデン イメージのセットアップは完了です。</span><span class="sxs-lookup"><span data-stu-id="63748-210">At this point, the golden image setup is complete.</span></span> <span data-ttu-id="63748-211">Teams は、非永続的なセットアップでのユーザーごとのインストールでは適切に動作しません。</span><span class="sxs-lookup"><span data-stu-id="63748-211">Teams will not work properly with per-user installation on a non-persistent setup.</span></span>

    - <span data-ttu-id="63748-212">マシンごとのインストール</span><span class="sxs-lookup"><span data-stu-id="63748-212">Per-machine installation</span></span>

        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1 ALLUSERS=1
        ```

        <span data-ttu-id="63748-213">これにより、64ビット オペレーティング システムの Program Files (x86) フォルダーおよび 32 ビット オペレーティング システム の Program Files フォルダーに Teams がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="63748-213">This installs Teams to the Program Files (x86) folder on a 64-bit operating system and to the Program Files folder on a 32-bit operating system.</span></span> <span data-ttu-id="63748-214">この時点で、ゴールデン イメージのセットアップは完了です。</span><span class="sxs-lookup"><span data-stu-id="63748-214">At this point, the golden image setup is complete.</span></span> <span data-ttu-id="63748-215">非永続的なセットアップについては、マシンごとに Teams をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="63748-215">Installing Teams per-machine is required for non-persistent setups.</span></span>

        <span data-ttu-id="63748-216">次の対話型ログオン セッションは、Teams を開始し、資格情報を要求します。</span><span class="sxs-lookup"><span data-stu-id="63748-216">The next interactive logon session starts Teams and asks for credentials.</span></span>

    > [!NOTE]
    > <span data-ttu-id="63748-217">これらの例では、 **ALLUSERS = 1**パラメーターも使用します。</span><span class="sxs-lookup"><span data-stu-id="63748-217">These examples also use the **ALLUSERS=1** parameter.</span></span> <span data-ttu-id="63748-218">このパラメーターを設定すると、チームのコンピューター全体のインストーラーがコントロールパネルの [プログラムと機能] に表示され、[アプリ] では、コンピューターのすべてのユーザーの Windows 設定の & 機能が表示されます。</span><span class="sxs-lookup"><span data-stu-id="63748-218">When you set this parameter, Teams Machine-Wide Installer appears in Programs and Features in Control Panel and in Apps & features in Windows Settings for all users of the computer.</span></span> <span data-ttu-id="63748-219">すべてのユーザーが管理者の資格情報を持っている場合は、チームをアンインストールできます。</span><span class="sxs-lookup"><span data-stu-id="63748-219">All users can then uninstall Teams if they have admin credentials.</span></span> <span data-ttu-id="63748-220">**ALLUSERS = 1**と**alluser = 1**の違いを理解しておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="63748-220">It's important to understand the difference between **ALLUSERS=1** and **ALLUSER=1**.</span></span> <span data-ttu-id="63748-221">**ALLUSERS = 1**パラメーターは、非 VDI および vdi 環境で使うことができ、 **alluser = 1**パラメーターは vdi 環境でのみ使用され、コンピューター単位のインストールを指定します。</span><span class="sxs-lookup"><span data-stu-id="63748-221">The **ALLUSERS=1** parameter can be used in non-VDI and VDI environments and the **ALLUSER=1** parameter is used only in VDI environments to specify a per-machine installation.</span></span>

3. <span data-ttu-id="63748-222">VDI VM から MSI をアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="63748-222">Uninstall the MSI from the VDI VM.</span></span>

    <span data-ttu-id="63748-223">Teams をアンインストールする方法は 2 つあります。</span><span class="sxs-lookup"><span data-stu-id="63748-223">There are two ways to uninstall Teams:</span></span>  
  
    - <span data-ttu-id="63748-224">PowerShell スクリプト (推奨)</span><span class="sxs-lookup"><span data-stu-id="63748-224">PowerShell script (recommended)</span></span>

    - <span data-ttu-id="63748-225">コマンドライン:</span><span class="sxs-lookup"><span data-stu-id="63748-225">Command line:</span></span>
  
      ```console
      msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>
      ```
      <span data-ttu-id="63748-226">これにより、オペレーティング システムの環境に応じて、Program Files (x86) フォルダーまたは Program Files フォルダーから Teams がアンインストールされます。</span><span class="sxs-lookup"><span data-stu-id="63748-226">This uninstalls Teams from the Program Files (x86) folder or Program Files folder, depending on the operating system environment.</span></span>

## <a name="teams-on-vdi-performance-considerations"></a><span data-ttu-id="63748-227">VDI 上の Teams のパフォーマンスに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="63748-227">Teams on VDI performance considerations</span></span>

<span data-ttu-id="63748-228">さまざまな仮想化セットアップ構成があり、それぞれ最適化の焦点が異なります。</span><span class="sxs-lookup"><span data-stu-id="63748-228">There are variety of virtualized setup configurations, each with a different focus for optimization.</span></span> <span data-ttu-id="63748-229">たとえば、ユーザーの密度です。</span><span class="sxs-lookup"><span data-stu-id="63748-229">For example, user density.</span></span> <span data-ttu-id="63748-230">計画するときは、組織のワークロードのニーズに基づいてセットアップを最適化するために、以下を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="63748-230">When planning, consider the following to help optimize your setup based on the workload needs of your organization:</span></span>

- <span data-ttu-id="63748-231">最小要件: 一部のワークロードでは、最小要件を超えるリソースを使用したセットアップが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="63748-231">Minimum requirement: Some workloads may require a setup using resources that are above the minimum requirements.</span></span> <span data-ttu-id="63748-232">たとえば、より多くのコンピューティング リソースを必要とするアプリケーションを使用する開発者向けのワークロード。</span><span class="sxs-lookup"><span data-stu-id="63748-232">For example, workloads for developers who use applications that demand more computing resources.</span></span>
- <span data-ttu-id="63748-233">依存関係: インフラストラクチャ、ワークロード、および Teams デスクトップ アプリ以外の環境に関するその他の考慮事項への依存関係が含まれます。</span><span class="sxs-lookup"><span data-stu-id="63748-233">Dependencies: These include dependencies on infrastructure, workload, and other environmental considerations outside the Teams desktop app.</span></span>
- <span data-ttu-id="63748-234">VDI の無効な機能: Teams は、VDI の GPU 負荷集中型機能を無効にします。これは、一時的な CPU 使用率の改善に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="63748-234">Disabled features on VDI: Teams disables GPU-intensive features for VDI, which can help improve transient CPU utilization.</span></span> <span data-ttu-id="63748-235">以下の機能は無効です。</span><span class="sxs-lookup"><span data-stu-id="63748-235">The following features are disabled:</span></span>
    - <span data-ttu-id="63748-236">Teams CSS アニメーション</span><span class="sxs-lookup"><span data-stu-id="63748-236">Teams CSS animation</span></span>
    - <span data-ttu-id="63748-237">Giphy の自動起動</span><span class="sxs-lookup"><span data-stu-id="63748-237">Giphy auto-start</span></span>

## <a name="teams-on-vdi-with-calling-and-meetings"></a><span data-ttu-id="63748-238">通話と会議を含む VDI 上の Teams</span><span class="sxs-lookup"><span data-stu-id="63748-238">Teams on VDI with calling and meetings</span></span>

<span data-ttu-id="63748-239">チャットと共同作業に加えて、通話と会議のサポートを備えた VDI 上の Teams は、Citrix ベースのプラットフォームで利用できます。</span><span class="sxs-lookup"><span data-stu-id="63748-239">In addition to chat and collaboration, Teams on VDI with calling and meeting support is available with Citrix-based platforms.</span></span> <span data-ttu-id="63748-240">サポートされる機能は、WebRTC メディア スタックおよび Citrix 固有の実装に基づいています。</span><span class="sxs-lookup"><span data-stu-id="63748-240">Supported features are based on the WebRTC media stack and Citrix-specific implementation.</span></span> <span data-ttu-id="63748-241">次の図では、このアーキテクチャの概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="63748-241">The following diagram provides an overview of the architecture.</span></span>

![VDI アーキテクチャ上の Teams を示す図](media/teams-on-vdi-architecture.png)

<span data-ttu-id="63748-243">次の通話および会議機能はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="63748-243">These calling and meeting features are not supported:</span></span>

- <span data-ttu-id="63748-244">拡張緊急サービス</span><span class="sxs-lookup"><span data-stu-id="63748-244">Enhanced emergency services</span></span>
- <span data-ttu-id="63748-245">Teams アプリとデバイス間の HID ボタンと LED コントロール</span><span class="sxs-lookup"><span data-stu-id="63748-245">HID buttons and LED controls between the Teams app and devices</span></span>
- <span data-ttu-id="63748-246">背景のぼかしと効果</span><span class="sxs-lookup"><span data-stu-id="63748-246">Background blur and effects</span></span>
- <span data-ttu-id="63748-247">ブロードキャスト/ライブ イベント</span><span class="sxs-lookup"><span data-stu-id="63748-247">Broadcast/live events</span></span>
- <span data-ttu-id="63748-248">場所に基づくルーティング (LBR)</span><span class="sxs-lookup"><span data-stu-id="63748-248">Location-Based Routing (LBR)</span></span>
- <span data-ttu-id="63748-249">コール パーク</span><span class="sxs-lookup"><span data-stu-id="63748-249">Call park</span></span>
- <span data-ttu-id="63748-250">コール キュー</span><span class="sxs-lookup"><span data-stu-id="63748-250">Call queue</span></span>

> [!IMPORTANT]
> <span data-ttu-id="63748-251">現在、VDI で AV 最適化なしで Teams を実行しており、最適化でまだサポートされていない機能 (アプリ共有時の制御の受け渡しなど) を使用する場合、Citrix ポリシーを設定して Teams のリダイレクトを無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="63748-251">If you currently run Teams without AV optimization in VDI and you use features that are not supported yet for optimization (such as Give and take control when app sharing), you have to set Citrix policies to turn off Teams redirection.</span></span> <span data-ttu-id="63748-252">つまり、Teams のメディア セッションは最適化されません。</span><span class="sxs-lookup"><span data-stu-id="63748-252">This means that Teams media sessions won't be optimized.</span></span> <span data-ttu-id="63748-253">Teams のリダイレクトを無効にするポリシーを設定する方法の手順については、この [Citrix Web サイト](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/policies/reference/ica-policy-settings/multimedia-policy-settings.html)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63748-253">For steps on how to set policies to turn off Teams redirection, see this [Citrix website](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/policies/reference/ica-policy-settings/multimedia-policy-settings.html).</span></span>

<span data-ttu-id="63748-254">現在は非 VDI 環境でのみ利用可能な通話および会議機能の追加に取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="63748-254">We're working on adding calling and meeting features that are currently only available in non-VDI environments.</span></span> <span data-ttu-id="63748-255">これらには、品質についての管理者制御の強化、画面共有シナリオの追加、および最近 Teams に追加された高度な機能が含まれる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="63748-255">These may include more admin control over quality, additional screen sharing scenarios, and advanced features recently added to Teams.</span></span> <span data-ttu-id="63748-256">今後の機能の詳細については、Teams の担当者にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="63748-256">Contact your Teams representative to learn more about upcoming features.</span></span>

### <a name="network-requirements"></a><span data-ttu-id="63748-257">ネットワーク要件</span><span class="sxs-lookup"><span data-stu-id="63748-257">Network requirements</span></span>

<span data-ttu-id="63748-258">環境を評価して、クラウド全体での音声とビデオの展開に影響を与える可能性のあるリスクおよび要件を特定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="63748-258">We recommend that you evaluate your environment to identify any risks and requirements that can influence your overall cloud voice and video deployment.</span></span> <span data-ttu-id="63748-259">[Skype for Business ネットワーク評価ツール](https://www.microsoft.com/download/details.aspx?id=53885)を使用して、ネットワークが Teams に対応しているかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="63748-259">Use the [Skype for Business Network Assessment Tool](https://www.microsoft.com/download/details.aspx?id=53885) to test whether your network is ready for Teams.</span></span>

<span data-ttu-id="63748-260">Teams 用にネットワークを準備する方法の詳細については、「[Teams 用に組織のネットワークを準備する](prepare-network.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63748-260">To learn more about how to prepare your network for Teams, see [Prepare your organization's network for  Teams](prepare-network.md).</span></span>

### <a name="migrate-from-skype-for-business-on-vdi-to-teams-on-vdi"></a><span data-ttu-id="63748-261">VDI上の Skype for Business から VDI 上の Teams に移行する</span><span class="sxs-lookup"><span data-stu-id="63748-261">Migrate from Skype for Business on VDI to Teams on VDI</span></span>

<span data-ttu-id="63748-262">VDI 上の Skype for Business から VDI 上の Teams に移行する場合、2 つのアプリケーションの違いに加えて、VDI も実装されている場合にはいくつかの違いがあります。</span><span class="sxs-lookup"><span data-stu-id="63748-262">If you're migrating from Skype for Business on VDI to Teams on VDI, besides the differences between the two applications, there are some differences when VDI is also implemented.</span></span> <span data-ttu-id="63748-263">Skype for Business VDI ではサポートされていて、Teams VDI では現在サポートされていない機能は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="63748-263">Some capabilities that aren't currently supported in Teams VDI that are in Skype for Business VDI are as follows:</span></span>

- <span data-ttu-id="63748-264">メディアのビットレートを制限するポリシーを使用した VDI 通話エクスペリエンスの制御</span><span class="sxs-lookup"><span data-stu-id="63748-264">Control of VDI calling experiences with policies for limiting media bitrate</span></span>
- <span data-ttu-id="63748-265">VDI の一部の AV 機能を無効にするプラットフォームごとのポリシー</span><span class="sxs-lookup"><span data-stu-id="63748-265">Per-platform policy to disable some AV features in VDI</span></span>
- <span data-ttu-id="63748-266">アプリ共有時の制御の受け渡し</span><span class="sxs-lookup"><span data-stu-id="63748-266">Give and take control when app sharing</span></span>
- <span data-ttu-id="63748-267">音声なしのチャットからの画面共有</span><span class="sxs-lookup"><span data-stu-id="63748-267">Screen share from chat without audio</span></span>
- <span data-ttu-id="63748-268">ビデオと画面の共有の同時送受信</span><span class="sxs-lookup"><span data-stu-id="63748-268">Simultaneous video and screen sharing send and receive</span></span>

### <a name="teams-on-chrome-browser-versus-teams-desktop-app-for-vdi"></a><span data-ttu-id="63748-269">Chrome ブラウザーの Teams と VDI の Teams デスクトップ アプリの比較</span><span class="sxs-lookup"><span data-stu-id="63748-269">Teams on Chrome browser versus Teams desktop app for VDI</span></span>

<span data-ttu-id="63748-270">Chrome ブラウザーの Teams は、AV 最適化を備えた VDI 用の Teams デスクトップ アプリに代わるものを提供しません。</span><span class="sxs-lookup"><span data-stu-id="63748-270">Teams on Chrome browser doesn't provide a replacement for the Teams desktop app for VDI with AV optimization.</span></span> <span data-ttu-id="63748-271">チャットと共同作業のエクスペリエンスは期待どおりに機能します。</span><span class="sxs-lookup"><span data-stu-id="63748-271">The chat and collaboration experience works as expected.</span></span> <span data-ttu-id="63748-272">メディアが必要な場合、Chrome ブラウザーでのユーザーの期待に合わないエクスペリエンスがいくつか提供される場合があります。</span><span class="sxs-lookup"><span data-stu-id="63748-272">When media is needed, there are some experiences that may not meet user expectations on the Chrome browser:</span></span>

- <span data-ttu-id="63748-273">オーディオとビデオのストリーミング エクスペリエンスが最適でない場合があります。</span><span class="sxs-lookup"><span data-stu-id="63748-273">The audio and video streaming experience may not be optimal.</span></span> <span data-ttu-id="63748-274">ユーザーには遅延や品質低下が発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="63748-274">Users may experiences delays or reduced quality.</span></span>
- <span data-ttu-id="63748-275">デバイス設定は、ブラウザーの設定では使用できません。</span><span class="sxs-lookup"><span data-stu-id="63748-275">Device settings aren't available in browser settings.</span></span>
- <span data-ttu-id="63748-276">デバイス管理はブラウザーを介して処理され、ブラウザー サイト設定で複数の設定が必要です。</span><span class="sxs-lookup"><span data-stu-id="63748-276">Device management is handled through the browser and requires multiple settings in browser site settings.</span></span>
- <span data-ttu-id="63748-277">デバイス設定は、Windows デバイス管理でも設定する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="63748-277">Device settings may also need to be set in Windows device management.</span></span>

## <a name="teams-on-vdi-with-chat-and-collaboration"></a><span data-ttu-id="63748-278">チャットと共同作業を備えた VDI 上の Teams</span><span class="sxs-lookup"><span data-stu-id="63748-278">Teams on VDI with chat and collaboration</span></span>

<span data-ttu-id="63748-279">組織で Teams のチャットおよび共同作業機能のみを使用する場合は、ユーザーレベル ポリシーを設定して、Teams の通話および会議機能を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="63748-279">If your organization wants to only use chat and collaboration features in Teams, you can set user-level policies to turn off calling and meeting functionality in Teams.</span></span> <span data-ttu-id="63748-280">この機能レベルには、Citrix Virtual Apps and Desktops は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="63748-280">This feature level doesn't require Citrix Virtual Apps and Desktops.</span></span>

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a><span data-ttu-id="63748-281">通話および会議機能を無効にするポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="63748-281">Set policies to turn off calling and meeting functionality</span></span>

<span data-ttu-id="63748-282">Microsoft Teams 管理センターまたは PowerShell を使用してポリシーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="63748-282">You can set policies by using the Microsoft Teams admin center or PowerShell.</span></span> <span data-ttu-id="63748-283">ポリシーの変更が反映されるまでに時間がかかる場合があります (数時間)。</span><span class="sxs-lookup"><span data-stu-id="63748-283">It can take some time (a few hours) for the policy changes to propagate.</span></span> <span data-ttu-id="63748-284">指定したアカウントの変更がすぐに表示されない場合は、数時間後にもう一度お試しください。</span><span class="sxs-lookup"><span data-stu-id="63748-284">If you don't see changes for a given account immediately, try again in a few hours.</span></span>

<span data-ttu-id="63748-285">[**通話ポリシー**](teams-calling-policy.md): Teams には、すべての通話機能が無効になっている組み込みの DisallowCalling 通話ポリシーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="63748-285">[**Calling polices**](teams-calling-policy.md): Teams includes the built-in DisallowCalling calling policy, in which all calling features are turned off.</span></span> <span data-ttu-id="63748-286">DisallowCalling ポリシーを、仮想化環境で Teams を使用する組織内のすべてのユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="63748-286">Assign the DisallowCalling policy to all users in your organization who use Teams in a virtualized environment.</span></span>

<span data-ttu-id="63748-287">[**会議ポリシー**](meeting-policies-in-teams.md): Teams には、すべての会議機能が無効になっている組み込みの AllOff 会議ポリシーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="63748-287">[**Meeting policies**](meeting-policies-in-teams.md): Teams includes the built-in AllOff meeting policy, in which all meeting features are turned off.</span></span> <span data-ttu-id="63748-288">AllOff ポリシーを、仮想化環境で Teams を使用する組織内のすべてのユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="63748-288">Assign the AllOff policy to all users in your organization who use Teams in a virtualized environment.</span></span>

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a><span data-ttu-id="63748-289">Microsoft Teams 管理センターを使用してポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="63748-289">Assign policies using the Microsoft Teams admin center</span></span>

<span data-ttu-id="63748-290">DisallowCalling 通話ポリシーおよび AllOff 会議ポリシーをユーザーに割り当てるには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="63748-290">To assign the DisallowCalling calling policy and the AllOff meeting policy to users, follow these steps:</span></span>

1. <span data-ttu-id="63748-291">Microsoft Teams 管理センターの左側のナビゲーションで、[**ユーザー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="63748-291">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="63748-292">ユーザー名の左側をクリックしてユーザーを選択し、[**編集を設定する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63748-292">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="63748-293">以下の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="63748-293">Do the following:</span></span>
    1.  <span data-ttu-id="63748-294">[**通話ポリシー**] で、[**DisallowCalling**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63748-294">Under **Calling policy**, click **DisallowCalling**.</span></span>
    2.  <span data-ttu-id="63748-295">[**会議ポリシー**] で、[**AllOff**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63748-295">Under **Meeting policy**, click **AllOff**.</span></span>
4. <span data-ttu-id="63748-296">[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63748-296">Click **Apply**.</span></span>

<span data-ttu-id="63748-297">一度に複数のユーザーにポリシーを割り当てる方法については、「[一括でTeams のユーザー設定を編集する](edit-user-settings-in-bulk.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63748-297">To assign a policy to multiple users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="63748-298">または、次の操作も実行できます。</span><span class="sxs-lookup"><span data-stu-id="63748-298">Or, you can also do the following:</span></span>

1. <span data-ttu-id="63748-299">Microsoft Teams 管理センターの左側のナビゲーションで、割り当てるポリシーに移動します。</span><span class="sxs-lookup"><span data-stu-id="63748-299">In the left navigation of the Microsoft Teams admin center, go to the policy you want to assign.</span></span> <span data-ttu-id="63748-300">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="63748-300">For example:</span></span>
    - <span data-ttu-id="63748-301">[**音声**]  >  [**通話ポリシー**] の順に移動し、[**DisallowCalling**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63748-301">Go to **Voice** > **Calling policies**, and then click **DisallowCalling**.</span></span>
    - <span data-ttu-id="63748-302">[**会議**]  >  [**会議ポリシー**] の順に移動し、[**AllOff**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63748-302">Go to **Meetings** > **Meeting policies**, and then click **AllOff**.</span></span>
3. <span data-ttu-id="63748-303">**[ユーザーを管理する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="63748-303">Select **Manage users**.</span></span>
4. <span data-ttu-id="63748-304">[**ユーザーを管理する**] ウィンドウで、表示名またはユーザー名でユーザーを検索し、名前を選択して [**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63748-304">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="63748-305">追加するユーザーごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="63748-305">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="63748-306">ユーザーの追加が完了したら、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63748-306">When you're finished adding users, click **Save**.</span></span>

#### <a name="assign-policies-using-powershell"></a><span data-ttu-id="63748-307">PowerShell を使用してポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="63748-307">Assign policies using PowerShell</span></span>

<span data-ttu-id="63748-308">次の例は、[Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) を使用して、DisallowCalling 通話ポリシーをユーザーに割り当てる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="63748-308">The following example shows how to use the [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) to assign the DisallowCalling calling policy to a user.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

<span data-ttu-id="63748-309">PowerShell を使用して通話ポリシーを管理する方法の詳細については、「[Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63748-309">To learn more about using PowerShell to manage calling policies, see [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).</span></span>

<span data-ttu-id="63748-310">次の例は、[Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) を使用して、AllOff 会議ポリシーをユーザーに割り当てる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="63748-310">The following example shows how to use the [Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) to assign the AllOff meeting policy to a user.</span></span>

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

<span data-ttu-id="63748-311">PowerShell を使用して会議ポリシーを管理する方法の詳細については、「[Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63748-311">To learn more about using PowerShell to manage meeting policies, see [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>

## <a name="migrate-teams-on-vdi-with-chat-and-collaboration-to-citrix-with-calling-and-meetings"></a><span data-ttu-id="63748-312">チャットとコラボレーションを使用する VDI 上の Teams を、通話と会議を使用する Citrix に移行します。</span><span class="sxs-lookup"><span data-stu-id="63748-312">Migrate Teams on VDI with chat and collaboration to Citrix with calling and meetings</span></span>

<span data-ttu-id="63748-313">ユーザーレベル ポリシーを設定して通話および会議機能を無効にしたチャットとコラボレーションを使用する VDI 上の Teams の既存の実装があり、AV 最適化を備えた Citrix に移行する場合、VDI 上の Teams のユーザーに通話および会議機能を有効にするポリシーを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="63748-313">If you have an existing implementation of Teams on VDI with chat and collaboration in which you had set user-level policies to turn off calling and meeting functionality, and you're migrating to Citrix with AV optimization, you must set policies to turn on calling and meeting functionality for those Teams on VDI users.</span></span>

### <a name="set-policies-to-turn-on-calling-and-meeting-functionality"></a><span data-ttu-id="63748-314">通話および会議機能を有効にするポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="63748-314">Set policies to turn on calling and meeting functionality</span></span>

<span data-ttu-id="63748-315">Microsoft Teams 管理センターまたは PowerShell を使用して、通話および会議ポリシーを設定し、ユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="63748-315">You can use the Microsoft Teams admin center or PowerShell to set and assign calling and meeting policies to your users.</span></span> <span data-ttu-id="63748-316">ポリシーの変更が反映されるまでに時間がかかる場合があります (数時間)。</span><span class="sxs-lookup"><span data-stu-id="63748-316">It can take some time (a few hours) for policy changes to propagate.</span></span> <span data-ttu-id="63748-317">指定したアカウントの変更がすぐに表示されない場合は、数時間が経過した後にもう一度お試しください。</span><span class="sxs-lookup"><span data-stu-id="63748-317">If you don't see changes for a given account immediately, try again after a few hours.</span></span>

<span data-ttu-id="63748-318">[**通話ポリシー**](teams-calling-policy.md): Teams の通話ポリシーは、ユーザーが使用できる通話機能を制御します。</span><span class="sxs-lookup"><span data-stu-id="63748-318">[**Calling polices**](teams-calling-policy.md): Calling policies in Teams control which calling features are available to users.</span></span> <span data-ttu-id="63748-319">Teams には、すべての通話機能が有効になっている組み込みの AallowCalling 通話ポリシーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="63748-319">Teams includes the built-in AllowCalling calling policy, in which all calling features are turned on.</span></span> <span data-ttu-id="63748-320">すべての通話機能を有効にするには、AllowCalling ポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="63748-320">To turn on all calling features, assign the AllowCalling policy.</span></span> <span data-ttu-id="63748-321">または、カスタム通話ポリシーを作成して、必要な通話機能を有効にし、ユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="63748-321">Or, create a custom calling policy to turn on the calling features that you want and assign it to users.</span></span> 

<span data-ttu-id="63748-322">[**会議ポリシー**](meeting-policies-in-teams.md): Teams の会議ポリシーは、ユーザーが作成できる会議の種類と、組織内のユーザーによってスケジュールされた会議参加者が利用できる機能を制御します。</span><span class="sxs-lookup"><span data-stu-id="63748-322">[**Meeting policies**](meeting-policies-in-teams.md): Meeting policies in Teams control the types of meetings that users can create and the features that are available to meeting participants that are scheduled by users in your organization.</span></span> <span data-ttu-id="63748-323">Teams には、すべての会議機能が有効になっている組み込みの AllOn 会議ポリシーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="63748-323">Teams includes the built-in AllOn meeting policy, in which all meeting features are turned on.</span></span> <span data-ttu-id="63748-324">すべての会議機能を有効にするには、AllOn ポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="63748-324">To turn on all meeting features, assign the AllOn policy.</span></span> <span data-ttu-id="63748-325">または、カスタム会議ポリシーを作成して、必要な会議機能を有効にし、ユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="63748-325">Or, create a custom meeting policy to turn on the meeting features that you want and assign it users.</span></span>

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a><span data-ttu-id="63748-326">Microsoft Teams 管理センターを使用してポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="63748-326">Assign policies using the Microsoft Teams admin center</span></span>

<span data-ttu-id="63748-327">AllowCalling 通話ポリシーおよび AllOn 会議ポリシーをユーザーに割り当てるには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="63748-327">To assign the AllowCalling calling policy and the AllOn meeting policy to users, follow these steps:</span></span>

1. <span data-ttu-id="63748-328">Microsoft Teams 管理センターの左側のナビゲーションで、[**ユーザー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="63748-328">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="63748-329">ユーザー名の左側をクリックしてユーザーを選択し、[**編集を設定する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63748-329">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="63748-330">以下の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="63748-330">Do the following:</span></span>
    1.  <span data-ttu-id="63748-331">[**通話ポリシー**] で、[**AllowCalling**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63748-331">Under **Calling policy**, click **AllowCalling**.</span></span>
    2.  <span data-ttu-id="63748-332">[**会議ポリシー**] で、[**AllOn**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63748-332">Under **Meeting policy**, click **AllOn**.</span></span>
4. <span data-ttu-id="63748-333">[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63748-333">Click **Apply**.</span></span>

<span data-ttu-id="63748-334">一度に複数のユーザーにポリシーを割り当てる方法については、「[一括でTeams のユーザー設定を編集する](edit-user-settings-in-bulk.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63748-334">To assign a policy to multiple users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="63748-335">または、次の操作も実行できます。</span><span class="sxs-lookup"><span data-stu-id="63748-335">Or, you can also do the following:</span></span>

1. <span data-ttu-id="63748-336">Microsoft Teams 管理センターの左側のナビゲーションで、割り当てるポリシーに移動します。</span><span class="sxs-lookup"><span data-stu-id="63748-336">In the left navigation of the Microsoft Teams admin center, go to the policy you want to assign.</span></span> <span data-ttu-id="63748-337">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="63748-337">For example:</span></span>
    - <span data-ttu-id="63748-338">[**音声**]  >  [**通話ポリシー**] の順に移動し、[**AllowCalling**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63748-338">Go to **Voice** > **Calling policies**, and then click **AllowCalling**.</span></span>
    - <span data-ttu-id="63748-339">[**会議**]  >  [**会議ポリシー**] の順に移動し、[**AllOn**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63748-339">Go to **Meetings** > **Meeting policies**, and then click **AllOn**.</span></span>
3. <span data-ttu-id="63748-340">[**ユーザーを管理する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="63748-340">Select **Manage users**.</span></span>
4. <span data-ttu-id="63748-341">[**ユーザーを管理する**] ウィンドウで、表示名またはユーザー名でユーザーを検索し、名前を選択して [**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63748-341">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="63748-342">追加するユーザーごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="63748-342">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="63748-343">ユーザーの追加が完了したら、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63748-343">When you're finished adding users, click **Save**.</span></span>

#### <a name="assign-policies-using-powershell"></a><span data-ttu-id="63748-344">PowerShell を使用してポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="63748-344">Assign policies using PowerShell</span></span>

<span data-ttu-id="63748-345">次の例は、[Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) を使用して、AllowCalling 通話ポリシーをユーザーに割り当てる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="63748-345">The following example shows how to use the [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) to assign the AllowCalling calling policy to a user.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName AllowCalling -Identity "user email id"
```

<span data-ttu-id="63748-346">PowerShell を使用して通話ポリシーを管理する方法の詳細については、「[Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63748-346">To learn more about using PowerShell to manage calling policies, see [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).</span></span>

<span data-ttu-id="63748-347">次の例は、[Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) を使用して、AllOn 会議ポリシーをユーザーに割り当てる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="63748-347">The following example shows how to use the [Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) to assign the AllOn meeting policy to a user.</span></span>

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOn -Identity "user email id"
```

<span data-ttu-id="63748-348">PowerShell を使用して会議ポリシーを管理する方法の詳細については、「[Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63748-348">To learn more about using PowerShell to manage meeting policies, see [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>

## <a name="known-issues-and-limitations"></a><span data-ttu-id="63748-349">既知の問題と制限事項</span><span class="sxs-lookup"><span data-stu-id="63748-349">Known issues and limitations</span></span>

### <a name="client-deployment-installation-and-setup"></a><span data-ttu-id="63748-350">クライアントの展開、インストール、およびセットアップ</span><span class="sxs-lookup"><span data-stu-id="63748-350">Client deployment, installation, and setup</span></span>

- <span data-ttu-id="63748-351">マシンごとのインストールでは、VDI 上の Teams は、非 VDI Teams のクライアントと同様に自動的に更新されません。</span><span class="sxs-lookup"><span data-stu-id="63748-351">With per-machine installation, Teams on VDI isn't automatically updated in the way that non-VDI Teams clients are.</span></span> <span data-ttu-id="63748-352">[VDI で Teams デスクトップ アプリをインストールまたは更新する](#install-or-update-the-teams-desktop-app-on-vdi)セクションの説明に従って新しい MSI をインストールし、VM イメージを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="63748-352">You have to update the VM image by installing a new MSI as described in the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.</span></span> <span data-ttu-id="63748-353">現在のバージョンをアンインストールして新しいバージョンに更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="63748-353">You must uninstall the current version to update to a newer version.</span></span>
- <span data-ttu-id="63748-354">Teams は、ユーザーごとまたはマシンごとに展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="63748-354">Teams should be deployed either per user or per machine.</span></span> <span data-ttu-id="63748-355">Teams のユーザーごとおよびマシンごとの同時展開はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="63748-355">Deployment of Teams for concurrent per user and per machine is not supported.</span></span>  <span data-ttu-id="63748-356">マシンごとまたはユーザーごとからこれらのモードのいずれかに移行するには、アンインストール手順に従っていずれかのモードに再展開します。</span><span class="sxs-lookup"><span data-stu-id="63748-356">To migrate from either per machine or per user to one of these modes, follow the uninstall procedure and redeploy to either mode.</span></span>
- <span data-ttu-id="63748-357">Mac OS および Linux ベースのクライアントは、現時点では Citrix によってサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="63748-357">MacOs and Linux-based clients are not supported by Citrix at this time.</span></span>
- <span data-ttu-id="63748-358">Citrix は、エンドポイントに定義された明示的な HTTP プロキシの使用をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="63748-358">Citrix doesn't support the use of explicit HTTP proxies defined on an endpoint.</span></span> 

### <a name="calling-and-meetings"></a><span data-ttu-id="63748-359">通話と会議</span><span class="sxs-lookup"><span data-stu-id="63748-359">Calling and meetings</span></span>

- <span data-ttu-id="63748-360">Skype for Business との相互運用性は、音声通話に限定され、ビデオ モダリティにはありません。</span><span class="sxs-lookup"><span data-stu-id="63748-360">Interoperability with Skype for Business is limited to audio calls, no video modality.</span></span>
- <span data-ttu-id="63748-361">テレフォニー システムとのデュアル トーン多重周波数 (DTMF) の相互作用は現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="63748-361">Dual Tone Multi Frequency (DTMF) interaction with telephony systems  is currently not supported.</span></span>
- <span data-ttu-id="63748-362">匿名ユーザーとしての Teams 会議への参加については、AV 最適化されていません。</span><span class="sxs-lookup"><span data-stu-id="63748-362">Joining Teams meetings as an anonymous user isn't AV-optimized.</span></span> <span data-ttu-id="63748-363">ユーザーは会議に参加でき、最適化されていないエクスペリエンスを経験します。</span><span class="sxs-lookup"><span data-stu-id="63748-363">The user can join the meeting and have a non-optimized experience.</span></span>
- <span data-ttu-id="63748-364">会議またはグループ通話では、単一の着信ビデオ ストリームのみがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="63748-364">Only a single incoming video stream is supported in meetings or group calls.</span></span> <span data-ttu-id="63748-365">複数のユーザーがビデオを送信する場合、常に主要な発表者のビデオのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="63748-365">When multiple people send video, only the dominant speaker's video is shown at any given time.</span></span>  
- <span data-ttu-id="63748-366">受信および送信ビデオ ストリームの解像度は、720p に制限されています。</span><span class="sxs-lookup"><span data-stu-id="63748-366">Incoming and outgoing video stream resolution is limited to 720p resolution.</span></span> <span data-ttu-id="63748-367">これは WebRTC の制限です。</span><span class="sxs-lookup"><span data-stu-id="63748-367">This is a WebRTC limitation.</span></span>
- <span data-ttu-id="63748-368">受信カメラまたは画面共有ストリームからの 1 つのビデオ ストリームのみがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="63748-368">Only one video stream from an incoming camera or screen share stream is supported.</span></span> <span data-ttu-id="63748-369">受信画面共有がある場合、主要な発表者のビデオではなく、その画面共有が表示されます。</span><span class="sxs-lookup"><span data-stu-id="63748-369">When there's an incoming screen share, that screen share is shown it instead of the video of the dominant speaker.</span></span>
- <span data-ttu-id="63748-370">送信画面の共有:</span><span class="sxs-lookup"><span data-stu-id="63748-370">Outgoing screen sharing:</span></span>
    - <span data-ttu-id="63748-371">アプリケーションの共有はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="63748-371">Application sharing is not supported.</span></span>
- <span data-ttu-id="63748-372">制御の受け渡し:</span><span class="sxs-lookup"><span data-stu-id="63748-372">Give control and take control:</span></span>  
    - <span data-ttu-id="63748-373">画面共有またはアプリケーション共有セッション中はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="63748-373">Not supported during a screen sharing or application sharing session.</span></span>
    - <span data-ttu-id="63748-374">PowerPoint 共有セッション中はサポートされます。</span><span class="sxs-lookup"><span data-stu-id="63748-374">Supported during a PowerPoint sharing session.</span></span>
- <span data-ttu-id="63748-375">マルチモニター設定での画面共有の場合、メイン モニターのみ共有されます。</span><span class="sxs-lookup"><span data-stu-id="63748-375">When screen sharing in a multi-monitor setup, only the main monitor is shared.</span></span>
- <span data-ttu-id="63748-376">CWA での高 DPI スケーリングはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="63748-376">High DPI scaling on CWA is not supported.</span></span>

<span data-ttu-id="63748-377">VDI に関連しない Teams の既知の問題については、「[Teams の既知の問題](Known-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63748-377">For Teams known issues that aren't related to VDI, see [Known issues for Teams](Known-issues.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="63748-378">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="63748-378">Troubleshooting</span></span>

#### <a name="troubleshoot-citrix-components"></a><span data-ttu-id="63748-379">Citrix コンポーネントのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="63748-379">Troubleshoot Citrix components</span></span>

<span data-ttu-id="63748-380">VDA および CWA の問題のトラブルシューティング方法については、[このCitrix Web サイト](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63748-380">For information on how to troubleshoot VDA and CWA issues, see [this Citrix website](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html).</span></span>

## <a name="related-topics"></a><span data-ttu-id="63748-381">関連項目</span><span class="sxs-lookup"><span data-stu-id="63748-381">Related topics</span></span>

- [<span data-ttu-id="63748-382">MSI を使用して Microsoft Teams をインストールする</span><span class="sxs-lookup"><span data-stu-id="63748-382">Install Microsoft Teams using MSI</span></span>](msi-deployment.md)
- [<span data-ttu-id="63748-383">Teams での PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="63748-383">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
