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
ms.openlocfilehash: 53eed34584cb3a8167367e29f036cb21d741bd83
ms.sourcegitcommit: 9b1c138b39fd87e239a7b1c5051f30c633e7d813
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "44944010"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a><span data-ttu-id="6b114-103">仮想デスクトップ インフラストラクチャ用の Teams</span><span class="sxs-lookup"><span data-stu-id="6b114-103">Teams for Virtualized Desktop Infrastructure</span></span>

<span data-ttu-id="6b114-104">この記事では、仮想化環境で Microsoft Teams を使用する場合の要件と制限について説明します。</span><span class="sxs-lookup"><span data-stu-id="6b114-104">This article describes the requirements and limitations for using Microsoft Teams in a virtualized environment.</span></span>

## <a name="what-is-vdi"></a><span data-ttu-id="6b114-105">VDI とは何ですか ?</span><span class="sxs-lookup"><span data-stu-id="6b114-105">What is VDI?</span></span>

<span data-ttu-id="6b114-106">仮想デスクトップ インフラストラクチャ (VDI) は、データセンターの集中サーバーでデスクトップ オペレーティング システムとアプリケーションをホストする仮想化テクノロジです。</span><span class="sxs-lookup"><span data-stu-id="6b114-106">Virtual Desktop Infrastructure (VDI) is virtualization technology that hosts a desktop operating system and applications on a centralized server in a data center.</span></span> <span data-ttu-id="6b114-107">これにより、完全に保護され、準拠し一元化されたソースとともに、ユーザーに完全に個人用に設定されたデスクトップ エクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="6b114-107">This enables a fully personalized desktop experience to users with a fully secured and compliant centralized source.</span></span>
 
<span data-ttu-id="6b114-108">仮想環境での Microsoft Teams では、チャットとコラボレーションがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="6b114-108">Microsoft Teams in a virtualized environment supports chat and collaboration.</span></span> <span data-ttu-id="6b114-109">また、Citrix プラットフォームでは、通話と会議機能もサポートされています。</span><span class="sxs-lookup"><span data-stu-id="6b114-109">And with the Citrix platform, calling and meeting functionality also are supported.</span></span>

<span data-ttu-id="6b114-110">仮想化環境の Teams は、複数の構成をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="6b114-110">Teams in a virtualized environment supports multiple configurations.</span></span> <span data-ttu-id="6b114-111">これには、VDI、専用、共有、永続的、非永続的モードが含まれます。</span><span class="sxs-lookup"><span data-stu-id="6b114-111">These include VDI, dedicated, shared, persistent, and non-persistent modes.</span></span> <span data-ttu-id="6b114-112">機能は継続的に開発され、定期的に追加されます。機能は今後数か月または数年で拡張されます。</span><span class="sxs-lookup"><span data-stu-id="6b114-112">Features are in continuous development and are added on a regular basis, and functionality will expand in the coming months and years.</span></span>
 
<span data-ttu-id="6b114-113">仮想環境で Teams を使用することは、仮想化されていない環境での Teams の使用とは多少異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="6b114-113">Using Teams in a virtualized environment might be somewhat different from using Teams in a non-virtualized environment.</span></span> <span data-ttu-id="6b114-114">たとえば、一部の高度な機能は仮想化された環境では使用できない場合があり、ビデオの解像度が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="6b114-114">For example, some advanced features might not be available in a virtualized environment, and video resolution might differ.</span></span> 

<span data-ttu-id="6b114-115">最適なユーザー エクスペリエンスを確保するには、この記事のガイダンスに従ってください。</span><span class="sxs-lookup"><span data-stu-id="6b114-115">To ensure an optimal user experience, follow the guidance in this article.</span></span>

## <a name="teams-on-vdi-components"></a><span data-ttu-id="6b114-116">VDI 上の Teams のコンポーネント</span><span class="sxs-lookup"><span data-stu-id="6b114-116">Teams on VDI components</span></span>

<span data-ttu-id="6b114-117">仮想化環境で Teams を使用するには、次のコンポーネントが必要です。</span><span class="sxs-lookup"><span data-stu-id="6b114-117">Using Teams in a virtualized environment requires the following components.</span></span>

- <span data-ttu-id="6b114-118">**仮想化ブローカー**: Azure などの仮想化プロバイダーへのリソースおよび接続マネージャー</span><span class="sxs-lookup"><span data-stu-id="6b114-118">**Virtualization broker**: The resource and connection manager to the virtualization provider, such as Azure</span></span>
- <span data-ttu-id="6b114-119">**仮想デスクトップ**: Microsoft Teams を実行する仮想マシン (VM) スタック</span><span class="sxs-lookup"><span data-stu-id="6b114-119">**Virtual desktop**: The Virtual Machine (VM) stack that runs Microsoft Teams</span></span>
- <span data-ttu-id="6b114-120">**シン クライアント**: ユーザーが物理的にやり取りするエンドポイント</span><span class="sxs-lookup"><span data-stu-id="6b114-120">**Thin client**: The endpoint that the user physically interfaces with</span></span>
- <span data-ttu-id="6b114-121">**Teams デスクトップアプリ**: teams デスクトップクライアントアプリ</span><span class="sxs-lookup"><span data-stu-id="6b114-121">**Teams desktop app**: The Teams desktop client app</span></span>

## <a name="teams-on-vdi-requirements"></a><span data-ttu-id="6b114-122">VDI 上の Teams の要件</span><span class="sxs-lookup"><span data-stu-id="6b114-122">Teams on VDI requirements</span></span>

### <a name="virtualization-provider-requirements"></a><span data-ttu-id="6b114-123">仮想化プロバイダーの要件</span><span class="sxs-lookup"><span data-stu-id="6b114-123">Virtualization provider requirements</span></span>

<span data-ttu-id="6b114-124">Teams デスクトップ アプリは、主要な仮想化ソリューション プロバイダーで検証済みです。</span><span class="sxs-lookup"><span data-stu-id="6b114-124">The Teams desktop app was validated with leading virtualization solution providers.</span></span> <span data-ttu-id="6b114-125">市場プロバイダーが複数ある場合は、最小要件を満たしていることを確認するために、仮想化ソリューションプロバイダーに問い合わせることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6b114-125">With multiple market providers, we recommend that you consult your virtualization solution provider to ensure that you meet the minimum requirements.</span></span>
  
<span data-ttu-id="6b114-126">現在、オーディオ/ビデオ (AV) 最適化を備えた VDI 上の Teams は、Citrix で認定されています。</span><span class="sxs-lookup"><span data-stu-id="6b114-126">Currently, Teams on VDI with audio/video (AV) optimization is certified with Citrix.</span></span> <span data-ttu-id="6b114-127">このセクションの情報を確認して、Citrix と Teams の両方の要件が適切に機能することを確認します。</span><span class="sxs-lookup"><span data-stu-id="6b114-127">Review the information in this section to ensure that you meet both Citrix and Teams requirements for proper functionality.</span></span>

### <a name="partners-certified-for-teams"></a><span data-ttu-id="6b114-128">Teams 認定パートナー</span><span class="sxs-lookup"><span data-stu-id="6b114-128">Partners certified for Teams</span></span>

<span data-ttu-id="6b114-129">次のパートナーには、Teams 用の仮想デスクトップ インフラストラクチャ ソリューションがあります。</span><span class="sxs-lookup"><span data-stu-id="6b114-129">The following partners have virtual desktop infrastructure solutions for Teams.</span></span>

|<span data-ttu-id="6b114-130">パートナー</span><span class="sxs-lookup"><span data-stu-id="6b114-130">Partner</span></span>|<span data-ttu-id="6b114-131">パートナー ソリューション</span><span class="sxs-lookup"><span data-stu-id="6b114-131">Partner solution</span></span>|
|----|---|
|![Citrix を表すロゴ](media/citrix.png)| <span data-ttu-id="6b114-133"><a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix Virtual Apps and Desktops</a></span><span class="sxs-lookup"><span data-stu-id="6b114-133"><a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix Virtual Apps and Desktops</a></span></span> |

### <a name="citrix-virtual-apps-and-desktops-requirements"></a><span data-ttu-id="6b114-134">Citrix Virtual Apps and Desktops の要件</span><span class="sxs-lookup"><span data-stu-id="6b114-134">Citrix Virtual Apps and Desktops requirements</span></span>

<span data-ttu-id="6b114-135">Citrix Virtual Apps and Desktops (以前の XenApp および XenDesktop) は、VDI 上の Teams に AV 最適化を提供します。</span><span class="sxs-lookup"><span data-stu-id="6b114-135">Citrix Virtual Apps and Desktops (formerly known as XenApp and XenDesktop) provides AV optimization for Teams on VDI.</span></span> <span data-ttu-id="6b114-136">Citrix Virtual Apps and Desktops を使用すると、VDI 上の Teams はチャットと共同作業に加えて、通話および会議機能をサポートします。</span><span class="sxs-lookup"><span data-stu-id="6b114-136">With Citrix Virtual Apps and Desktops, Teams on VDI supports calling and meeting functionality in addition to chat and collaboration.</span></span>

<span data-ttu-id="6b114-137">Citrix の[ダウンロードサイト](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/)で、Citrix の仮想アプリとデスクトップの最新バージョンをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="6b114-137">You can download the latest version of Citrix Virtual Apps and Desktops at [the Citrix downloads site](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/).</span></span> <span data-ttu-id="6b114-138">(最初にサインインする必要があります。) 必要なコンポーネントは、デフォルトで [Citrix Workspace アプリ (CWA)](https://www.citrix.com/downloads/workspace-app/) および Virtual Delivery Agent (VDA) にバンドルされています。</span><span class="sxs-lookup"><span data-stu-id="6b114-138">(You'll need to sign in first.) The necessary components are bundled into the [Citrix Workspace app (CWA)](https://www.citrix.com/downloads/workspace-app/) and Virtual Delivery Agent (VDA) by default.</span></span> <span data-ttu-id="6b114-139">CWA や VDA に追加のコンポーネントやプラグインをインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6b114-139">You don't need to install any additional components or plugins on CWA or the VDA.</span></span>

<span data-ttu-id="6b114-140">サーバーおよびクライアントの最新の要件については、[この Citrix Web サイト](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b114-140">For the latest server and client requirements, see [this Citrix website](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html).</span></span>

## <a name="install-or-update-the-teams-desktop-app-on-vdi"></a><span data-ttu-id="6b114-141">VDI で Teams デスクトップ アプリをインストールまたは更新する</span><span class="sxs-lookup"><span data-stu-id="6b114-141">Install or update the Teams desktop app on VDI</span></span>

<span data-ttu-id="6b114-142">MSI パッケージを使用したマシンごとのインストールまたはユーザーごとのインストールを用いて、VDI 用の Teams デスクトップ アプリを展開できます。</span><span class="sxs-lookup"><span data-stu-id="6b114-142">You can deploy the Teams desktop app for VDI using a per-machine installation or per-user installation using the MSI package.</span></span> <span data-ttu-id="6b114-143">どのアプローチを使用するかについては、永続的なセットアップを使用するか、または非永続的なセットアップを使用するか、および組織の関連機能のニーズに応じて決定します。</span><span class="sxs-lookup"><span data-stu-id="6b114-143">Deciding on which approach to use depends on whether you use a persistent or non-persistent setup and the associated functionality needs of your organization.</span></span>

<span data-ttu-id="6b114-144">専用の永続的なセットアップの場合、どちらのアプローチでも機能します。</span><span class="sxs-lookup"><span data-stu-id="6b114-144">For a dedicated persistent setup, either approach would work.</span></span> <span data-ttu-id="6b114-145">ただし、非永続的なセットアップの場合、チームは効率的に作業するために、コンピューターごとにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b114-145">However, for a non-persistent setup, Teams requires a per-machine installation in order to work efficiently.</span></span> <span data-ttu-id="6b114-146">[非永続のセットアップ](#non-persistent-setup)のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b114-146">See the [Non-persistent setup](#non-persistent-setup) section.</span></span>

<span data-ttu-id="6b114-147">マシンごとのインストールでは、自動更新は無効になっています。</span><span class="sxs-lookup"><span data-stu-id="6b114-147">With per-machine installation, automatic updates is disabled.</span></span> <span data-ttu-id="6b114-148">つまり、Teams アプリを更新するには、現在のバージョンをアンインストールして新しいバージョンに更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b114-148">This means that to update the Teams app, you must uninstall the current version to update to a newer version.</span></span> <span data-ttu-id="6b114-149">ユーザーごとのインストールでは、自動更新は有効になっています。</span><span class="sxs-lookup"><span data-stu-id="6b114-149">With per-user installation, automatic updates is enabled.</span></span> <span data-ttu-id="6b114-150">ほとんどの VDI の展開について、マシンごとのインストールを使用して Teams を展開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6b114-150">For most VDI deployments, we recommend you deploy Teams using per-machine installation.</span></span>

<span data-ttu-id="6b114-151">最新の Teams バージョンに更新するには、アンインストール手順から始めて、次に最新の Teams バージョンを展開します。</span><span class="sxs-lookup"><span data-stu-id="6b114-151">To update to the latest Teams version, start with the uninstall procedure followed by latest Teams version deployment.</span></span>

<span data-ttu-id="6b114-152">VDI 環境での Teams AV の最適化が適切に機能するには、シン クライアント エンドポイントがインターネットにアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b114-152">For Teams AV optimization in VDI environments to work properly, the thin client endpoint must have access to the internet.</span></span> <span data-ttu-id="6b114-153">シン クライアント エンドポイントでインターネット アクセスが利用できない場合、最適化のスタートアップは成功しません。</span><span class="sxs-lookup"><span data-stu-id="6b114-153">If internet access isn't available at the thin client endpoint, optimization startup won't be successful.</span></span> <span data-ttu-id="6b114-154">これは、ユーザーが最適化されていないメディア状態にあることを意味します。</span><span class="sxs-lookup"><span data-stu-id="6b114-154">This means that the user is in a non-optimized media state.</span></span>

#### <a name="dedicated-persistent-setup"></a><span data-ttu-id="6b114-155">専用の永続的なセットアップ</span><span class="sxs-lookup"><span data-stu-id="6b114-155">Dedicated persistent setup</span></span>

<span data-ttu-id="6b114-156">専用の永続的なセットアップでは、ユーザーのローカル オペレーティング システムの変更は、ユーザーがログオフした後も保持されます。</span><span class="sxs-lookup"><span data-stu-id="6b114-156">In a dedicated persistent setup, users' local operating system changes are retained after users log off.</span></span> <span data-ttu-id="6b114-157">永続的なセットアップでは、チームはユーザーごととコンピューターごとの両方のインストールをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="6b114-157">For persistent setup, Teams supports both per-user and per-machine installation.</span></span>

<span data-ttu-id="6b114-158">推奨される最低限の VM 構成は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6b114-158">The following is the recommended minimum VM configuration.</span></span>

|<span data-ttu-id="6b114-159">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6b114-159">Parameter</span></span>  |<span data-ttu-id="6b114-160">ワークステーションのオペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="6b114-160">Workstation operating system</span></span>  |<span data-ttu-id="6b114-161">サーバーオペレーティングシステム</span><span class="sxs-lookup"><span data-stu-id="6b114-161">Server operating system</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="6b114-162">vCPU</span><span class="sxs-lookup"><span data-stu-id="6b114-162">vCPU</span></span>   |    <span data-ttu-id="6b114-163">2 コア</span><span class="sxs-lookup"><span data-stu-id="6b114-163">2 cores</span></span>     |  <span data-ttu-id="6b114-164">4、6、または 8。</span><span class="sxs-lookup"><span data-stu-id="6b114-164">4,6, or 8</span></span><br><span data-ttu-id="6b114-165">基礎となる Non-Uniform Memory Access (NUMA) 構成を理解し、それに応じて VM を構成することが重要です。</span><span class="sxs-lookup"><span data-stu-id="6b114-165">It's important to understand the underlying non-uniform memory access (NUMA) configuration and configure your VMs accordingly.</span></span>     |
|<span data-ttu-id="6b114-166">RAM</span><span class="sxs-lookup"><span data-stu-id="6b114-166">RAM</span></span>     |   <span data-ttu-id="6b114-167">4 GB</span><span class="sxs-lookup"><span data-stu-id="6b114-167">4 GB</span></span>      | <span data-ttu-id="6b114-168">ユーザー 1 人あたり 512 から 1024 MB</span><span class="sxs-lookup"><span data-stu-id="6b114-168">512 to 1024 MB per user</span></span>        |
|<span data-ttu-id="6b114-169">ストレージ</span><span class="sxs-lookup"><span data-stu-id="6b114-169">Storage</span></span>    | <span data-ttu-id="6b114-170">8 GB</span><span class="sxs-lookup"><span data-stu-id="6b114-170">8 GB</span></span>        | <span data-ttu-id="6b114-171">40 から 60 GB</span><span class="sxs-lookup"><span data-stu-id="6b114-171">40 to 60 GB</span></span>        |

#### <a name="non-persistent-setup"></a><span data-ttu-id="6b114-172">非永続的なセットアップ</span><span class="sxs-lookup"><span data-stu-id="6b114-172">Non-persistent setup</span></span>

<span data-ttu-id="6b114-173">非永続的なセットアップでは、ユーザーのローカル オペレーティング システムの変更は、ユーザーがログオフした後は保持されません。</span><span class="sxs-lookup"><span data-stu-id="6b114-173">In a non-persistent setup, users' local operating system changes are not retained after users log off.</span></span> <span data-ttu-id="6b114-174">このようなセットアップは、一般的に共有マルチユーザー セッションです。</span><span class="sxs-lookup"><span data-stu-id="6b114-174">Such setups are commonly shared multi-user sessions.</span></span> <span data-ttu-id="6b114-175">VM 構成は、ユーザー数と使用可能な物理ボックス リソースによって異なります。</span><span class="sxs-lookup"><span data-stu-id="6b114-175">VM configuration varies based on the number of users and available physical box resources.</span></span>

<span data-ttu-id="6b114-176">非永続的なセットアップの場合、Teams デスクトップ アプリは、ゴールデン イメージに対してマシンごとにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b114-176">For a non-persistent setup, the Teams desktop app must be installed per-machine to the golden image.</span></span> <span data-ttu-id="6b114-177">(詳細に関しては、[VDI での Teams デスクトップ アプリのインストールまたは更新](#install-or-update-the-teams-desktop-app-on-vdi)セクションを参照してください) これにより、Teams アプリがユーザー セッション中でも効率的に起動できるようになります。</span><span class="sxs-lookup"><span data-stu-id="6b114-177">(To learn more, see the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.) This ensures an efficient launch of the Teams app during a user session.</span></span> 

<span data-ttu-id="6b114-178">非永続的なセットアップで Teams を使用する場合も、効率的な Teams のランタイムデータ同期のためのプロファイルキャッシュマネージャーが必要です。これにより、適切なユーザー固有の情報 (ユーザーデータ、プロファイル、設定など) がユーザーセッション中にキャッシュされます。</span><span class="sxs-lookup"><span data-stu-id="6b114-178">Using Teams with a non-persistent setup also requires a profile caching manager for efficient Teams runtime data sync. This ensures that the appropriate user-specific information (for example, user data, profile, and settings) is cached during the user session.</span></span> <span data-ttu-id="6b114-179">この2つのフォルダー内のデータが同期されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6b114-179">Make sure data in these two folders are synced.</span></span>  

- <span data-ttu-id="6b114-180">C:\Users\username\AppData\Local\Microsoft\IdentityCache (%localAppdata%\Microsoft\IdentityCache)</span><span class="sxs-lookup"><span data-stu-id="6b114-180">C:\Users\username\AppData\Local\Microsoft\IdentityCache (%localAppdata%\Microsoft\IdentityCache)</span></span>
- <span data-ttu-id="6b114-181">C:\Users\username\AppData\Roaming\Microsoft\Teams(%appdata%\Microsoft\Teams)</span><span class="sxs-lookup"><span data-stu-id="6b114-181">C:\Users\username\AppData\Roaming\Microsoft\Teams(%appdata%\Microsoft\Teams)</span></span>

<span data-ttu-id="6b114-182">さまざまなキャッシュ マネージャー ソリューションが利用可能です。</span><span class="sxs-lookup"><span data-stu-id="6b114-182">There are a variety of caching manager solutions available.</span></span> <span data-ttu-id="6b114-183">たとえば、[FSLogix](https://docs.microsoft.com/fslogix/overview) があります。</span><span class="sxs-lookup"><span data-stu-id="6b114-183">For example, [FSLogix](https://docs.microsoft.com/fslogix/overview).</span></span> <span data-ttu-id="6b114-184">具体的な構成手順については、キャッシュ マネージャー プロバイダーに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="6b114-184">Consult your caching manager provider for specific configuration instructions.</span></span>

##### <a name="teams-cached-content-exclusion-list-for-non-persistent-setup"></a><span data-ttu-id="6b114-185">Teams は、非永続的なセットアップ用のコンテンツ除外リストをキャッシュしました</span><span class="sxs-lookup"><span data-stu-id="6b114-185">Teams cached content exclusion list for non-persistent setup</span></span>

<span data-ttu-id="6b114-186">Teams キャッシュ フォルダー %appdata%/Microsoft/Teams から以下を除外します。</span><span class="sxs-lookup"><span data-stu-id="6b114-186">Exclude the following from the Teams caching folder, %appdata%/Microsoft/Teams.</span></span> <span data-ttu-id="6b114-187">これらの項目を除外すると、非永続的なセットアップをさらに最適化するために、ユーザーのキャッシュサイズを小さくすることができます。</span><span class="sxs-lookup"><span data-stu-id="6b114-187">Excluding these items helps reduce the user caching size to further optimize your non-persistent setup.</span></span>

- <span data-ttu-id="6b114-188">.txt ファイル</span><span class="sxs-lookup"><span data-stu-id="6b114-188">.txt files</span></span>
- <span data-ttu-id="6b114-189">メディアスタック フォルダー</span><span class="sxs-lookup"><span data-stu-id="6b114-189">Media-stack folder</span></span>
- <span data-ttu-id="6b114-190">meeting-addin\Cache (%appdata%\Microsoft\Teams\meeting-addin\Cache)</span><span class="sxs-lookup"><span data-stu-id="6b114-190">meeting-addin\Cache (%appdata%\Microsoft\Teams\meeting-addin\Cache)</span></span>

### <a name="microsoft-365-apps-for-enterprise-considerations"></a><span data-ttu-id="6b114-191">企業向けの Microsoft 365 アプリの考慮事項</span><span class="sxs-lookup"><span data-stu-id="6b114-191">Microsoft 365 Apps for enterprise considerations</span></span>

<span data-ttu-id="6b114-192">VDI で企業向けの Microsoft 365 アプリを使用して Teams を展開する場合は、次の点を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="6b114-192">Consider the following when you deploy Teams with Microsoft 365 Apps for enterprise on VDI.</span></span>

#### <a name="new-deployments-of-teams-through-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="6b114-193">Microsoft 365 アプリを使用した、エンタープライズ向けの新しいチーム展開</span><span class="sxs-lookup"><span data-stu-id="6b114-193">New deployments of Teams through Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="6b114-194">企業向けの Microsoft 365 アプリを使用してチームを展開する前に、コンピューターごとのインストールを使用して展開された既存の Teams アプリをアンインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b114-194">Before you deploy Teams through Microsoft 365 Apps for enterprise, you must first uninstall any pre-existing Teams apps if they were deployed using per-machine installation.</span></span>

<span data-ttu-id="6b114-195">企業向けの Microsoft 365 アプリを使用した Teams は、ユーザーごとにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="6b114-195">Teams through Microsoft 365 Apps for enterprise is installed per-user.</span></span> <span data-ttu-id="6b114-196">詳細については、[VDI で Teams デスクトップ アプリをインストールまたは更新する](#install-or-update-the-teams-desktop-app-on-vdi)セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b114-196">To learn more, see the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.</span></span>

#### <a name="teams-deployments-through-microsoft-365-apps-for-enterprise-updates"></a><span data-ttu-id="6b114-197">Microsoft 365 アプリを使用した、エンタープライズアップデート向けの Teams の展開</span><span class="sxs-lookup"><span data-stu-id="6b114-197">Teams deployments through Microsoft 365 Apps for enterprise updates</span></span>

<span data-ttu-id="6b114-198">Teams は、エンタープライズ向けの Microsoft 365 アプリの既存のインストールにも追加されています。</span><span class="sxs-lookup"><span data-stu-id="6b114-198">Teams is also being added to existing installations of Microsoft 365 Apps for enterprise.</span></span> <span data-ttu-id="6b114-199">エンタープライズ用の Microsoft 365 アプリでは、ユーザーごとにチームをインストールするため、「 [VDI 上の teams デスクトップアプリをインストールまたは更新](#install-or-update-the-teams-desktop-app-on-vdi)する」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b114-199">Since Microsoft 365 Apps for enterprise installs Teams per-user only, see the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.</span></span>

#### <a name="using-teams-with-per-machine-installation-and-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="6b114-200">コンピューターごとのインストールと Microsoft 365 アプリでの Teams の使用 (エンタープライズ向け)</span><span class="sxs-lookup"><span data-stu-id="6b114-200">Using Teams with per-machine installation and Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="6b114-201">エンタープライズ向けの Microsoft 365 アプリでは、各コンピューターの Teams インストールをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="6b114-201">Microsoft 365 Apps for enterprise doesn't support per-machine installations of Teams.</span></span> <span data-ttu-id="6b114-202">コンピューターごとのインストールを使用するには、enterprise 用の Microsoft 365 アプリから Teams を除外する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b114-202">To use per-machine installation, you must exclude Teams from Microsoft 365 Apps for enterprise.</span></span> <span data-ttu-id="6b114-203">「 [Teams デスクトップアプリを VM に展開](#deploy-the-teams-desktop-app-to-the-vm)する」および「[エンタープライズ向けの Microsoft 365 アプリを通じてチームの展開を除外する方法](#how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b114-203">See the [Deploy the Teams desktop app to the VM](#deploy-the-teams-desktop-app-to-the-vm) and [How to exclude Teams deployment through Microsoft 365 Apps for enterprise](#how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise) sections.</span></span>

#### <a name="how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="6b114-204">企業向けの Microsoft 365 アプリからチームの展開を除外する方法</span><span class="sxs-lookup"><span data-stu-id="6b114-204">How to exclude Teams deployment through Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="6b114-205">企業向けのチームおよび Microsoft 365 アプリの詳細については、「 [enterprise 用の microsoft 365 アプリの新しいインストールからチームを除外する](https://docs.microsoft.com/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-office-365-proplus)」および「[グループポリシーを使用して teams のインストールを制御](https://docs.microsoft.com/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams)する方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b114-205">To learn more about Teams and Microsoft 365 Apps for enterprise, see [How to exclude Teams from new installations of Microsoft 365 Apps for enterprise](https://docs.microsoft.com/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-office-365-proplus) and [Use Group Policy to control the installation of Teams](https://docs.microsoft.com/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams).</span></span>

### <a name="deploy-the-teams-desktop-app-to-the-vm"></a><span data-ttu-id="6b114-206">Teams デスクトップ アプリを VM に展開する</span><span class="sxs-lookup"><span data-stu-id="6b114-206">Deploy the Teams desktop app to the VM</span></span>

1. <span data-ttu-id="6b114-207">次のリンクのいずれかを使用して、VDI VM オペレーティング システムに一致する Teams MSI パッケージをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="6b114-207">Download the Teams MSI package that matches your VDI VM operating system using one of the following links:</span></span>


    - [<span data-ttu-id="6b114-208">32 ビット版</span><span class="sxs-lookup"><span data-stu-id="6b114-208">32-bit version</span></span>](https://statics.teams.cdn.office.net/production-windows/1.3.00.13565/Teams_windows.msi)
    - [<span data-ttu-id="6b114-209">64 ビット版</span><span class="sxs-lookup"><span data-stu-id="6b114-209">64-bit version</span></span>](https://statics.teams.cdn.office.net/production-windows-x64/1.3.00.13565/Teams_windows_x64.msi)


    <span data-ttu-id="6b114-210">必要な Teams デスクトップアプリの最小バージョンはバージョン1.3.00.4461 です。</span><span class="sxs-lookup"><span data-stu-id="6b114-210">The minimum version of the Teams desktop app that's required is version 1.3.00.4461.</span></span> <span data-ttu-id="6b114-211">(以前のバージョンでは、PSTN 保留はサポートされていません)。</span><span class="sxs-lookup"><span data-stu-id="6b114-211">(PSTN hold isn't supported in earlier versions.)</span></span>

2. <span data-ttu-id="6b114-212">次のコマンドのいずれかを実行して、MSI を VDI VM にインストールします。</span><span class="sxs-lookup"><span data-stu-id="6b114-212">Install the MSI to the VDI VM by running one of the following commands:</span></span>

    - <span data-ttu-id="6b114-213">ユーザーごとのインストール (既定)</span><span class="sxs-lookup"><span data-stu-id="6b114-213">Per-user installation (default)</span></span>
  
        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSERS=1
        ```

        <span data-ttu-id="6b114-214">このプロセスは既定のインストールであり、Teams を% AppData% ユーザーフォルダーにインストールします。</span><span class="sxs-lookup"><span data-stu-id="6b114-214">This process is the default installation, which installs Teams to the %AppData% user folder.</span></span> <span data-ttu-id="6b114-215">この時点で、ゴールデン イメージのセットアップは完了です。</span><span class="sxs-lookup"><span data-stu-id="6b114-215">At this point, the golden image setup is complete.</span></span> <span data-ttu-id="6b114-216">ユーザーごとのインストールで永続的なセットアップ以外の環境では、チームは適切に動作しません。</span><span class="sxs-lookup"><span data-stu-id="6b114-216">Teams won't work properly with per-user installation on a non-persistent setup.</span></span>

    - <span data-ttu-id="6b114-217">マシンごとのインストール</span><span class="sxs-lookup"><span data-stu-id="6b114-217">Per-machine installation</span></span>

        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1 ALLUSERS=1
        ```

        <span data-ttu-id="6b114-218">このプロセスでは、64ビットオペレーティングシステムの Program Files (x86) フォルダーと、32ビットオペレーティングシステムの Program Files フォルダーに Teams をインストールします。</span><span class="sxs-lookup"><span data-stu-id="6b114-218">This process installs Teams to the Program Files (x86) folder on a 64-bit operating system and to the Program Files folder on a 32-bit operating system.</span></span> <span data-ttu-id="6b114-219">この時点で、ゴールデン イメージのセットアップは完了です。</span><span class="sxs-lookup"><span data-stu-id="6b114-219">At this point, the golden image setup is complete.</span></span> <span data-ttu-id="6b114-220">非永続的なセットアップについては、マシンごとに Teams をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b114-220">Installing Teams per-machine is required for non-persistent setups.</span></span>

        <span data-ttu-id="6b114-221">次の対話型ログオン セッションは、Teams を開始し、資格情報を要求します。</span><span class="sxs-lookup"><span data-stu-id="6b114-221">The next interactive logon session starts Teams and asks for credentials.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6b114-222">これらの例では、 **ALLUSERS = 1**パラメーターも使用します。</span><span class="sxs-lookup"><span data-stu-id="6b114-222">These examples also use the **ALLUSERS=1** parameter.</span></span> <span data-ttu-id="6b114-223">このパラメーターを設定すると、チームのコンピューター全体のインストーラーがコントロールパネルの [プログラムと機能] に表示され、[アプリ] では、コンピューターのすべてのユーザーの Windows 設定の & 機能が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6b114-223">When you set this parameter, Teams Machine-Wide Installer appears in Programs and Features in Control Panel and in Apps & features in Windows Settings for all users of the computer.</span></span> <span data-ttu-id="6b114-224">すべてのユーザーが管理者の資格情報を持っている場合は、チームをアンインストールできます。</span><span class="sxs-lookup"><span data-stu-id="6b114-224">All users can then uninstall Teams if they have admin credentials.</span></span>
    <span data-ttu-id="6b114-225">**ALLUSERS = 1**と**alluser = 1**の違いを理解しておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="6b114-225">It's important to understand the difference between **ALLUSERS=1** and **ALLUSER=1**.</span></span> <span data-ttu-id="6b114-226">**ALLUSERS = 1**パラメーターは非 VDI および vdi 環境で使うことができますが、 **alluser = 1**パラメーターは vdi 環境でのみ使用され、コンピューター単位のインストールを指定します。</span><span class="sxs-lookup"><span data-stu-id="6b114-226">The **ALLUSERS=1** parameter can be used in non-VDI and VDI environments, while the **ALLUSER=1** parameter is used only in VDI environments to specify a per-machine installation.</span></span>

3. <span data-ttu-id="6b114-227">VDI VM から MSI をアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="6b114-227">Uninstall the MSI from the VDI VM.</span></span>
  
      ```console
      msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>
      ```
      <span data-ttu-id="6b114-228">このプロセスでは、オペレーティングシステムの環境に応じて、Program Files (x86) フォルダーまたは Program Files フォルダーから Teams がアンインストールされます。</span><span class="sxs-lookup"><span data-stu-id="6b114-228">This process uninstalls Teams from the Program Files (x86) folder or Program Files folder, depending on the operating system environment.</span></span>

## <a name="teams-on-vdi-performance-considerations"></a><span data-ttu-id="6b114-229">VDI 上の Teams のパフォーマンスに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="6b114-229">Teams on VDI performance considerations</span></span>

<span data-ttu-id="6b114-230">さまざまな仮想化設定が用意されており、それぞれが最適化のために異なるフォーカスが設定されています。</span><span class="sxs-lookup"><span data-stu-id="6b114-230">There are a variety of virtualized setup configurations, each with a different focus for optimization.</span></span> <span data-ttu-id="6b114-231">たとえば、構成ではユーザーの密度に重点を置いている場合があります。</span><span class="sxs-lookup"><span data-stu-id="6b114-231">For example, a configuration might focus on user density.</span></span> <span data-ttu-id="6b114-232">計画するときは、組織の作業負荷のニーズに合わせて、次の点を考慮してセットアップを最適化してください。</span><span class="sxs-lookup"><span data-stu-id="6b114-232">When planning, consider the following to help optimize your setup based on your organization's workload needs.</span></span>

- <span data-ttu-id="6b114-233">最小要件: 一部のワークロードでは、最小要件を超えるリソースを使用してセットアップを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b114-233">Minimum requirement: Some workloads might require a setup using resources that are above the minimum requirements.</span></span> <span data-ttu-id="6b114-234">たとえば、より多くのコンピューティング リソースを必要とするアプリケーションを使用する開発者向けのワークロード。</span><span class="sxs-lookup"><span data-stu-id="6b114-234">For example, workloads for developers who use applications that demand more computing resources.</span></span>
- <span data-ttu-id="6b114-235">依存関係: インフラストラクチャ、ワークロード、および Teams デスクトップ アプリ以外の環境に関するその他の考慮事項への依存関係が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6b114-235">Dependencies: These include dependencies on infrastructure, workload, and other environmental considerations outside the Teams desktop app.</span></span>
- <span data-ttu-id="6b114-236">VDI の無効な機能: Teams は、VDI の GPU 負荷集中型機能を無効にします。これは、一時的な CPU 使用率の改善に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="6b114-236">Disabled features on VDI: Teams disables GPU-intensive features for VDI, which can help improve transient CPU utilization.</span></span> <span data-ttu-id="6b114-237">以下の機能は無効です。</span><span class="sxs-lookup"><span data-stu-id="6b114-237">The following features are disabled:</span></span>
    - <span data-ttu-id="6b114-238">Teams CSS アニメーション</span><span class="sxs-lookup"><span data-stu-id="6b114-238">Teams CSS animation</span></span>
    - <span data-ttu-id="6b114-239">Giphy の自動起動</span><span class="sxs-lookup"><span data-stu-id="6b114-239">Giphy auto-start</span></span>

## <a name="teams-on-vdi-with-calling-and-meetings"></a><span data-ttu-id="6b114-240">通話と会議を含む VDI 上の Teams</span><span class="sxs-lookup"><span data-stu-id="6b114-240">Teams on VDI with calling and meetings</span></span>

<span data-ttu-id="6b114-241">チャットと共同作業に加えて、通話と会議のサポートを備えた VDI 上の Teams は、Citrix ベースのプラットフォームで利用できます。</span><span class="sxs-lookup"><span data-stu-id="6b114-241">In addition to chat and collaboration, Teams on VDI with calling and meeting support is available with Citrix-based platforms.</span></span> <span data-ttu-id="6b114-242">サポートされる機能は、WebRTC メディア スタックおよび Citrix 固有の実装に基づいています。</span><span class="sxs-lookup"><span data-stu-id="6b114-242">Supported features are based on the WebRTC media stack and Citrix-specific implementation.</span></span> <span data-ttu-id="6b114-243">次の図では、このアーキテクチャの概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="6b114-243">The following diagram provides an overview of the architecture.</span></span>

![VDI アーキテクチャ上の Teams を示す図](media/teams-on-vdi-architecture.png)

<span data-ttu-id="6b114-245">次の通話および会議機能はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="6b114-245">These calling and meeting features are not supported:</span></span>

- <span data-ttu-id="6b114-246">拡張緊急サービス</span><span class="sxs-lookup"><span data-stu-id="6b114-246">Enhanced emergency services</span></span>
- <span data-ttu-id="6b114-247">Teams アプリとデバイス間の HID ボタンと LED コントロール</span><span class="sxs-lookup"><span data-stu-id="6b114-247">HID buttons and LED controls between the Teams app and devices</span></span>
- <span data-ttu-id="6b114-248">背景のぼかしと効果</span><span class="sxs-lookup"><span data-stu-id="6b114-248">Background blur and effects</span></span>
- <span data-ttu-id="6b114-249">ブロードキャスト/ライブ イベント</span><span class="sxs-lookup"><span data-stu-id="6b114-249">Broadcast/live events</span></span>
- <span data-ttu-id="6b114-250">場所に基づくルーティング (LBR)</span><span class="sxs-lookup"><span data-stu-id="6b114-250">Location-Based Routing (LBR)</span></span>
- <span data-ttu-id="6b114-251">コール パーク</span><span class="sxs-lookup"><span data-stu-id="6b114-251">Call park</span></span>
- <span data-ttu-id="6b114-252">コール キュー</span><span class="sxs-lookup"><span data-stu-id="6b114-252">Call queue</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6b114-253">現在、VDI で AV 最適化なしで Teams を実行しており、最適化でまだサポートされていない機能 (アプリ共有時の制御の受け渡しなど) を使用する場合、Citrix ポリシーを設定して Teams のリダイレクトを無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b114-253">If you currently run Teams without AV optimization in VDI and you use features that are not supported yet for optimization (such as Give and take control when app sharing), you have to set Citrix policies to turn off Teams redirection.</span></span> <span data-ttu-id="6b114-254">つまり、Teams のメディア セッションは最適化されません。</span><span class="sxs-lookup"><span data-stu-id="6b114-254">This means that Teams media sessions won't be optimized.</span></span> <span data-ttu-id="6b114-255">Teams のリダイレクトを無効にするポリシーを設定する方法の手順については、この [Citrix Web サイト](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/policies/reference/ica-policy-settings/multimedia-policy-settings.html)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b114-255">For steps on how to set policies to turn off Teams redirection, see this [Citrix website](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/policies/reference/ica-policy-settings/multimedia-policy-settings.html).</span></span>

<span data-ttu-id="6b114-256">現在は非 VDI 環境でのみ利用可能な通話および会議機能の追加に取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="6b114-256">We're working on adding calling and meeting features that are currently only available in non-VDI environments.</span></span> <span data-ttu-id="6b114-257">これには、品質、追加の画面共有シナリオ、チームに最近追加された高度な機能など、より多くの管理者の制御が含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="6b114-257">These might include more admin control over quality, additional screen sharing scenarios, and advanced features recently added to Teams.</span></span> <span data-ttu-id="6b114-258">今後の機能の詳細については、Teams の担当者にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="6b114-258">Contact your Teams representative to learn more about upcoming features.</span></span>

### <a name="network-requirements"></a><span data-ttu-id="6b114-259">ネットワーク要件</span><span class="sxs-lookup"><span data-stu-id="6b114-259">Network requirements</span></span>

<span data-ttu-id="6b114-260">環境を評価して、クラウド全体での音声とビデオの展開に影響を与える可能性のあるリスクおよび要件を特定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6b114-260">We recommend that you evaluate your environment to identify any risks and requirements that can influence your overall cloud voice and video deployment.</span></span> <span data-ttu-id="6b114-261">[Skype for Business ネットワーク評価ツール](https://www.microsoft.com/download/details.aspx?id=53885)を使用して、ネットワークが Teams に対応しているかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="6b114-261">Use the [Skype for Business Network Assessment Tool](https://www.microsoft.com/download/details.aspx?id=53885) to test whether your network is ready for Teams.</span></span>

<span data-ttu-id="6b114-262">Teams のネットワークを準備する方法について詳しくは、「 [teams 用に組織のネットワークを準備](prepare-network.md)する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6b114-262">To learn more about how to prepare your network for Teams, see [Prepare your organization's network for Teams](prepare-network.md).</span></span>

### <a name="migrate-from-skype-for-business-on-vdi-to-teams-on-vdi"></a><span data-ttu-id="6b114-263">VDI上の Skype for Business から VDI 上の Teams に移行する</span><span class="sxs-lookup"><span data-stu-id="6b114-263">Migrate from Skype for Business on VDI to Teams on VDI</span></span>

<span data-ttu-id="6b114-264">VDI 上の Skype for Business から VDI 上の Teams に移行する場合、2 つのアプリケーションの違いに加えて、VDI も実装されている場合にはいくつかの違いがあります。</span><span class="sxs-lookup"><span data-stu-id="6b114-264">If you're migrating from Skype for Business on VDI to Teams on VDI, besides the differences between the two applications, there are some differences when VDI is also implemented.</span></span> <span data-ttu-id="6b114-265">Skype for Business VDI ではサポートされていて、Teams VDI では現在サポートされていない機能は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6b114-265">Some capabilities that aren't currently supported in Teams VDI that are in Skype for Business VDI are as follows:</span></span>

- <span data-ttu-id="6b114-266">メディアのビットレートを制限するポリシーを使用した VDI 通話エクスペリエンスの制御</span><span class="sxs-lookup"><span data-stu-id="6b114-266">Control of VDI calling experiences with policies for limiting media bitrate</span></span>
- <span data-ttu-id="6b114-267">VDI の一部の AV 機能を無効にするプラットフォームごとのポリシー</span><span class="sxs-lookup"><span data-stu-id="6b114-267">Per-platform policy to disable some AV features in VDI</span></span>
- <span data-ttu-id="6b114-268">アプリ共有時の制御の受け渡し</span><span class="sxs-lookup"><span data-stu-id="6b114-268">Give and take control when app sharing</span></span>
- <span data-ttu-id="6b114-269">音声なしのチャットからの画面共有</span><span class="sxs-lookup"><span data-stu-id="6b114-269">Screen share from chat without audio</span></span>
- <span data-ttu-id="6b114-270">ビデオと画面の共有の同時送受信</span><span class="sxs-lookup"><span data-stu-id="6b114-270">Simultaneous video and screen sharing send and receive</span></span>

### <a name="teams-on-chrome-browser-versus-teams-desktop-app-for-vdi"></a><span data-ttu-id="6b114-271">Chrome ブラウザーの Teams と VDI の Teams デスクトップ アプリの比較</span><span class="sxs-lookup"><span data-stu-id="6b114-271">Teams on Chrome browser versus Teams desktop app for VDI</span></span>

<span data-ttu-id="6b114-272">Chrome ブラウザーの Teams は、AV 最適化を備えた VDI 用の Teams デスクトップ アプリに代わるものを提供しません。</span><span class="sxs-lookup"><span data-stu-id="6b114-272">Teams on Chrome browser doesn't provide a replacement for the Teams desktop app for VDI with AV optimization.</span></span> <span data-ttu-id="6b114-273">チャットと共同作業のエクスペリエンスは期待どおりに機能します。</span><span class="sxs-lookup"><span data-stu-id="6b114-273">The chat and collaboration experience works as expected.</span></span> <span data-ttu-id="6b114-274">メディアが必要な場合は、Chrome ブラウザーでユーザーの期待を満たせない場合があります。</span><span class="sxs-lookup"><span data-stu-id="6b114-274">When media is needed, there are some experiences that might not meet user expectations on the Chrome browser:</span></span>

- <span data-ttu-id="6b114-275">オーディオとビデオのストリーミングのエクスペリエンスが最適でないことがあります。</span><span class="sxs-lookup"><span data-stu-id="6b114-275">The audio and video streaming experience might not be optimal.</span></span> <span data-ttu-id="6b114-276">ユーザーには、遅延または品質の低下が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6b114-276">Users might experiences delays or reduced quality.</span></span>
- <span data-ttu-id="6b114-277">デバイス設定は、ブラウザーの設定では使用できません。</span><span class="sxs-lookup"><span data-stu-id="6b114-277">Device settings aren't available in browser settings.</span></span>
- <span data-ttu-id="6b114-278">デバイス管理はブラウザーを介して処理され、ブラウザー サイト設定で複数の設定が必要です。</span><span class="sxs-lookup"><span data-stu-id="6b114-278">Device management is handled through the browser and requires multiple settings in browser site settings.</span></span>
- <span data-ttu-id="6b114-279">デバイス設定は、Windows デバイス管理でも設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b114-279">Device settings might also need to be set in Windows device management.</span></span>

## <a name="teams-on-vdi-with-chat-and-collaboration"></a><span data-ttu-id="6b114-280">チャットと共同作業を備えた VDI 上の Teams</span><span class="sxs-lookup"><span data-stu-id="6b114-280">Teams on VDI with chat and collaboration</span></span>

<span data-ttu-id="6b114-281">組織で Teams のチャットおよび共同作業機能のみを使用する場合は、ユーザーレベル ポリシーを設定して、Teams の通話および会議機能を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="6b114-281">If your organization wants to only use chat and collaboration features in Teams, you can set user-level policies to turn off calling and meeting functionality in Teams.</span></span> <span data-ttu-id="6b114-282">この機能レベルには、Citrix Virtual Apps and Desktops は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="6b114-282">This feature level doesn't require Citrix Virtual Apps and Desktops.</span></span>

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a><span data-ttu-id="6b114-283">通話および会議機能を無効にするポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="6b114-283">Set policies to turn off calling and meeting functionality</span></span>

<span data-ttu-id="6b114-284">Microsoft Teams 管理センターまたは PowerShell を使用してポリシーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="6b114-284">You can set policies by using the Microsoft Teams admin center or PowerShell.</span></span> <span data-ttu-id="6b114-285">ポリシーの変更が反映されるまでには、多少時間がかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="6b114-285">It might take some time (a few hours) for the policy changes to propagate.</span></span> <span data-ttu-id="6b114-286">指定したアカウントの変更がすぐに表示されない場合は、数時間後にもう一度お試しください。</span><span class="sxs-lookup"><span data-stu-id="6b114-286">If you don't see changes for a given account immediately, try again in a few hours.</span></span>

<span data-ttu-id="6b114-287">[**通話ポリシー**](teams-calling-policy.md): Teams には、すべての通話機能が無効になっている組み込みの DisallowCalling 通話ポリシーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6b114-287">[**Calling polices**](teams-calling-policy.md): Teams includes the built-in DisallowCalling calling policy, in which all calling features are turned off.</span></span> <span data-ttu-id="6b114-288">DisallowCalling ポリシーを、仮想化環境で Teams を使用する組織内のすべてのユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="6b114-288">Assign the DisallowCalling policy to all users in your organization who use Teams in a virtualized environment.</span></span>

<span data-ttu-id="6b114-289">[**会議ポリシー**](meeting-policies-in-teams.md): Teams には、すべての会議機能が無効になっている組み込みの AllOff 会議ポリシーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6b114-289">[**Meeting policies**](meeting-policies-in-teams.md): Teams includes the built-in AllOff meeting policy, in which all meeting features are turned off.</span></span> <span data-ttu-id="6b114-290">AllOff ポリシーを、仮想化環境で Teams を使用する組織内のすべてのユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="6b114-290">Assign the AllOff policy to all users in your organization who use Teams in a virtualized environment.</span></span>

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a><span data-ttu-id="6b114-291">Microsoft Teams 管理センターを使用してポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="6b114-291">Assign policies using the Microsoft Teams admin center</span></span>

<span data-ttu-id="6b114-292">DisallowCalling の通話ポリシーと割り当てをユーザーに割り当てるには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="6b114-292">To assign the DisallowCalling calling policy and the AllOff meeting policy to a user:</span></span>

1. <span data-ttu-id="6b114-293">Microsoft Teams 管理センターの左側のナビゲーションで、[**ユーザー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="6b114-293">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="6b114-294">ユーザー名の左側をクリックしてユーザーを選択し、[**編集を設定する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6b114-294">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="6b114-295">以下の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="6b114-295">Do the following:</span></span>
    1.  <span data-ttu-id="6b114-296">[**通話ポリシー**] で、[**DisallowCalling**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6b114-296">Under **Calling policy**, click **DisallowCalling**.</span></span>
    2.  <span data-ttu-id="6b114-297">[**会議ポリシー**] で、[**AllOff**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6b114-297">Under **Meeting policy**, click **AllOff**.</span></span>
4. <span data-ttu-id="6b114-298">[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6b114-298">Click **Apply**.</span></span>

<span data-ttu-id="6b114-299">複数のユーザーに同時にポリシーを割り当てるには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="6b114-299">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="6b114-300">Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動し、ユーザーを検索するか、表示にフィルターを適用してユーザーを表示します。</span><span class="sxs-lookup"><span data-stu-id="6b114-300">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="6b114-301">[**&#x2713;** (チェックマーク)] の列からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="6b114-301">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="6b114-302">すべてのユーザーを選択するには、表の上部にある [&#x2713; (チェックマーク)] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6b114-302">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="6b114-303">[**設定の編集**] をクリックし、必要な変更を行い、[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6b114-303">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>

<span data-ttu-id="6b114-304">または、次の操作も実行できます。</span><span class="sxs-lookup"><span data-stu-id="6b114-304">Or, you can also do the following:</span></span>

1. <span data-ttu-id="6b114-305">Microsoft Teams 管理センターの左側のナビゲーションで、割り当てるポリシーに移動します。</span><span class="sxs-lookup"><span data-stu-id="6b114-305">In the left navigation of the Microsoft Teams admin center, go to the policy you want to assign.</span></span> <span data-ttu-id="6b114-306">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="6b114-306">For example:</span></span>
    - <span data-ttu-id="6b114-307">[**音声**]  >  [**通話ポリシー**] の順に移動し、[**DisallowCalling**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6b114-307">Go to **Voice** > **Calling policies**, and then click **DisallowCalling**.</span></span>
    - <span data-ttu-id="6b114-308">[**会議**]  >  [**会議ポリシー**] の順に移動し、[**AllOff**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6b114-308">Go to **Meetings** > **Meeting policies**, and then click **AllOff**.</span></span>
3. <span data-ttu-id="6b114-309">**[ユーザーを管理する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6b114-309">Select **Manage users**.</span></span>
4. <span data-ttu-id="6b114-310">[**ユーザーを管理する**] ウィンドウで、表示名またはユーザー名でユーザーを検索し、名前を選択して [**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6b114-310">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="6b114-311">追加するユーザーごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="6b114-311">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="6b114-312">ユーザーの追加が完了したら、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6b114-312">When you're finished adding users, click **Save**.</span></span>

#### <a name="assign-policies-using-powershell"></a><span data-ttu-id="6b114-313">PowerShell を使用してポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="6b114-313">Assign policies using PowerShell</span></span>

<span data-ttu-id="6b114-314">次の例は、[Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) を使用して、DisallowCalling 通話ポリシーをユーザーに割り当てる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="6b114-314">The following example shows how to use the [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) to assign the DisallowCalling calling policy to a user.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

<span data-ttu-id="6b114-315">PowerShell を使用して通話ポリシーを管理する方法の詳細については、「[Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b114-315">To learn more about using PowerShell to manage calling policies, see [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).</span></span>

<span data-ttu-id="6b114-316">次の例は、[Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) を使用して、AllOff 会議ポリシーをユーザーに割り当てる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="6b114-316">The following example shows how to use the [Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) to assign the AllOff meeting policy to a user.</span></span>

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

<span data-ttu-id="6b114-317">PowerShell を使用して会議ポリシーを管理する方法の詳細については、「[Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b114-317">To learn more about using PowerShell to manage meeting policies, see [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>

## <a name="migrate-teams-on-vdi-with-chat-and-collaboration-to-citrix-with-calling-and-meetings"></a><span data-ttu-id="6b114-318">チャットとコラボレーションを使用する VDI 上の Teams を、通話と会議を使用する Citrix に移行します。</span><span class="sxs-lookup"><span data-stu-id="6b114-318">Migrate Teams on VDI with chat and collaboration to Citrix with calling and meetings</span></span>

<span data-ttu-id="6b114-319">ユーザーレベル ポリシーを設定して通話および会議機能を無効にしたチャットとコラボレーションを使用する VDI 上の Teams の既存の実装があり、AV 最適化を備えた Citrix に移行する場合、VDI 上の Teams のユーザーに通話および会議機能を有効にするポリシーを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b114-319">If you have an existing implementation of Teams on VDI with chat and collaboration in which you had set user-level policies to turn off calling and meeting functionality, and you're migrating to Citrix with AV optimization, you must set policies to turn on calling and meeting functionality for those Teams on VDI users.</span></span>

### <a name="set-policies-to-turn-on-calling-and-meeting-functionality"></a><span data-ttu-id="6b114-320">通話および会議機能を有効にするポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="6b114-320">Set policies to turn on calling and meeting functionality</span></span>

<span data-ttu-id="6b114-321">Microsoft Teams 管理センターまたは PowerShell を使用して、通話および会議ポリシーを設定し、ユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="6b114-321">You can use the Microsoft Teams admin center or PowerShell to set and assign calling and meeting policies to your users.</span></span> <span data-ttu-id="6b114-322">ポリシーの変更が反映されるまでに時間がかかる場合があります (数時間)。</span><span class="sxs-lookup"><span data-stu-id="6b114-322">It can take some time (a few hours) for policy changes to propagate.</span></span> <span data-ttu-id="6b114-323">指定したアカウントの変更がすぐに表示されない場合は、数時間が経過した後にもう一度お試しください。</span><span class="sxs-lookup"><span data-stu-id="6b114-323">If you don't see changes for a given account immediately, try again after a few hours.</span></span>

<span data-ttu-id="6b114-324">[**通話ポリシー**](teams-calling-policy.md): Teams の通話ポリシーは、ユーザーが使用できる通話機能を制御します。</span><span class="sxs-lookup"><span data-stu-id="6b114-324">[**Calling polices**](teams-calling-policy.md): Calling policies in Teams control which calling features are available to users.</span></span> <span data-ttu-id="6b114-325">Teams には、すべての通話機能が有効になっている組み込みの AallowCalling 通話ポリシーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6b114-325">Teams includes the built-in AllowCalling calling policy, in which all calling features are turned on.</span></span> <span data-ttu-id="6b114-326">すべての通話機能を有効にするには、AllowCalling ポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="6b114-326">To turn on all calling features, assign the AllowCalling policy.</span></span> <span data-ttu-id="6b114-327">または、カスタム通話ポリシーを作成して、必要な通話機能を有効にし、ユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="6b114-327">Or, create a custom calling policy to turn on the calling features that you want and assign it to users.</span></span> 

<span data-ttu-id="6b114-328">[**会議ポリシー**](meeting-policies-in-teams.md): Teams の会議ポリシーは、ユーザーが作成できる会議の種類と、組織内のユーザーによってスケジュールされた会議参加者が利用できる機能を制御します。</span><span class="sxs-lookup"><span data-stu-id="6b114-328">[**Meeting policies**](meeting-policies-in-teams.md): Meeting policies in Teams control the types of meetings that users can create and the features that are available to meeting participants that are scheduled by users in your organization.</span></span> <span data-ttu-id="6b114-329">Teams には、すべての会議機能が有効になっている組み込みの AllOn 会議ポリシーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6b114-329">Teams includes the built-in AllOn meeting policy, in which all meeting features are turned on.</span></span> <span data-ttu-id="6b114-330">すべての会議機能を有効にするには、AllOn ポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="6b114-330">To turn on all meeting features, assign the AllOn policy.</span></span> <span data-ttu-id="6b114-331">または、カスタム会議ポリシーを作成して、必要な会議機能を有効にし、ユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="6b114-331">Or, create a custom meeting policy to turn on the meeting features that you want and assign it users.</span></span>

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a><span data-ttu-id="6b114-332">Microsoft Teams 管理センターを使用してポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="6b114-332">Assign policies using the Microsoft Teams admin center</span></span>

<span data-ttu-id="6b114-333">AllowCalling の通話ポリシーと、すべての会議ポリシーをユーザーに割り当てるには:</span><span class="sxs-lookup"><span data-stu-id="6b114-333">To assign the AllowCalling calling policy and the AllOn meeting policy to a user:</span></span>

1. <span data-ttu-id="6b114-334">Microsoft Teams 管理センターの左側のナビゲーションで、[**ユーザー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="6b114-334">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="6b114-335">ユーザー名の左側をクリックしてユーザーを選択し、[**編集を設定する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6b114-335">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="6b114-336">以下の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="6b114-336">Do the following:</span></span>
    1.  <span data-ttu-id="6b114-337">[**通話ポリシー**] で、[**AllowCalling**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6b114-337">Under **Calling policy**, click **AllowCalling**.</span></span>
    2.  <span data-ttu-id="6b114-338">[**会議ポリシー**] で、[**AllOn**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6b114-338">Under **Meeting policy**, click **AllOn**.</span></span>
4. <span data-ttu-id="6b114-339">[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6b114-339">Click **Apply**.</span></span>

<span data-ttu-id="6b114-340">複数のユーザーに同時にポリシーを割り当てるには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="6b114-340">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="6b114-341">Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動し、ユーザーを検索するか、表示にフィルターを適用してユーザーを表示します。</span><span class="sxs-lookup"><span data-stu-id="6b114-341">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="6b114-342">[**&#x2713;** (チェックマーク)] の列からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="6b114-342">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="6b114-343">すべてのユーザーを選択するには、テーブルの上部にある **&#x2713;** (チェックマーク) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6b114-343">To select all users, click the **&#x2713;** (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="6b114-344">[**設定の編集**] をクリックし、必要な変更を行い、[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6b114-344">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>

<span data-ttu-id="6b114-345">または、次の操作も実行できます。</span><span class="sxs-lookup"><span data-stu-id="6b114-345">Or, you can also do the following:</span></span>

1. <span data-ttu-id="6b114-346">Microsoft Teams 管理センターの左側のナビゲーションで、割り当てるポリシーに移動します。</span><span class="sxs-lookup"><span data-stu-id="6b114-346">In the left navigation of the Microsoft Teams admin center, go to the policy you want to assign.</span></span> <span data-ttu-id="6b114-347">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="6b114-347">For example:</span></span>
    - <span data-ttu-id="6b114-348">[**音声**]  >  [**通話ポリシー**] の順に移動し、[**AllowCalling**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6b114-348">Go to **Voice** > **Calling policies**, and then click **AllowCalling**.</span></span>
    - <span data-ttu-id="6b114-349">[**会議**]  >  [**会議ポリシー**] の順に移動し、[**AllOn**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6b114-349">Go to **Meetings** > **Meeting policies**, and then click **AllOn**.</span></span>
3. <span data-ttu-id="6b114-350">[**ユーザーを管理する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6b114-350">Select **Manage users**.</span></span>
4. <span data-ttu-id="6b114-351">[**ユーザーを管理する**] ウィンドウで、表示名またはユーザー名でユーザーを検索し、名前を選択して [**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6b114-351">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="6b114-352">追加するユーザーごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="6b114-352">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="6b114-353">ユーザーの追加が完了したら、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6b114-353">When you're finished adding users, click **Save**.</span></span>

#### <a name="assign-policies-using-powershell"></a><span data-ttu-id="6b114-354">PowerShell を使用してポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="6b114-354">Assign policies using PowerShell</span></span>

<span data-ttu-id="6b114-355">次の例は、[Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) を使用して、AllowCalling 通話ポリシーをユーザーに割り当てる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="6b114-355">The following example shows how to use the [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) to assign the AllowCalling calling policy to a user.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName AllowCalling -Identity "user email id"
```

<span data-ttu-id="6b114-356">PowerShell を使用して通話ポリシーを管理する方法の詳細については、「[Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b114-356">To learn more about using PowerShell to manage calling policies, see [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).</span></span>

<span data-ttu-id="6b114-357">次の例は、[Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) を使用して、AllOn 会議ポリシーをユーザーに割り当てる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="6b114-357">The following example shows how to use the [Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) to assign the AllOn meeting policy to a user.</span></span>

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOn -Identity "user email id"
```

<span data-ttu-id="6b114-358">PowerShell を使用して会議ポリシーを管理する方法の詳細については、「[Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b114-358">To learn more about using PowerShell to manage meeting policies, see [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>

## <a name="known-issues-and-limitations"></a><span data-ttu-id="6b114-359">既知の問題と制限事項</span><span class="sxs-lookup"><span data-stu-id="6b114-359">Known issues and limitations</span></span>

### <a name="client-deployment-installation-and-setup"></a><span data-ttu-id="6b114-360">クライアントの展開、インストール、およびセットアップ</span><span class="sxs-lookup"><span data-stu-id="6b114-360">Client deployment, installation, and setup</span></span>

- <span data-ttu-id="6b114-361">マシンごとのインストールでは、VDI 上の Teams は、非 VDI Teams のクライアントと同様に自動的に更新されません。</span><span class="sxs-lookup"><span data-stu-id="6b114-361">With per-machine installation, Teams on VDI isn't automatically updated in the way that non-VDI Teams clients are.</span></span> <span data-ttu-id="6b114-362">[VDI で Teams デスクトップ アプリをインストールまたは更新する](#install-or-update-the-teams-desktop-app-on-vdi)セクションの説明に従って新しい MSI をインストールし、VM イメージを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b114-362">You have to update the VM image by installing a new MSI as described in the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.</span></span> <span data-ttu-id="6b114-363">現在のバージョンをアンインストールして新しいバージョンに更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b114-363">You must uninstall the current version to update to a newer version.</span></span>
- <span data-ttu-id="6b114-364">Teams は、ユーザーごとまたはマシンごとに展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b114-364">Teams should be deployed either per user or per machine.</span></span> <span data-ttu-id="6b114-365">Teams のユーザーごとおよびマシンごとの同時展開はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="6b114-365">Deployment of Teams for concurrent per user and per machine is not supported.</span></span> <span data-ttu-id="6b114-366">マシンごとまたはユーザーごとからこれらのモードのいずれかに移行するには、アンインストール手順に従っていずれかのモードに再展開します。</span><span class="sxs-lookup"><span data-stu-id="6b114-366">To migrate from either per machine or per user to one of these modes, follow the uninstall procedure and redeploy to either mode.</span></span>
- <span data-ttu-id="6b114-367">現時点では、Citrix は MacOs と Linux ベースのクライアントをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="6b114-367">Citrix doesn't support MacOs and Linux-based clients at this time.</span></span>
- <span data-ttu-id="6b114-368">Citrix は、エンドポイントに定義された明示的な HTTP プロキシの使用をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="6b114-368">Citrix doesn't support the use of explicit HTTP proxies defined on an endpoint.</span></span>

### <a name="calling-and-meetings"></a><span data-ttu-id="6b114-369">通話と会議</span><span class="sxs-lookup"><span data-stu-id="6b114-369">Calling and meetings</span></span>

- <span data-ttu-id="6b114-370">Skype for Business の相互運用性は音声通話に限定されます。ビデオのモダリティはありません。</span><span class="sxs-lookup"><span data-stu-id="6b114-370">Interoperability with Skype for Business is limited to audio calls; there is no video modality.</span></span>
- <span data-ttu-id="6b114-371">デュアルトーンマルチ周波数 (DTMF) テレフォニーシステムとの相互操作は、現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="6b114-371">Dual Tone Multi Frequency (DTMF) interaction with telephony systems is currently not supported.</span></span>
- <span data-ttu-id="6b114-372">匿名ユーザーとしての Teams 会議への参加については、AV 最適化されていません。</span><span class="sxs-lookup"><span data-stu-id="6b114-372">Joining Teams meetings as an anonymous user isn't AV-optimized.</span></span> <span data-ttu-id="6b114-373">ユーザーは会議に参加でき、最適化されていないエクスペリエンスを経験します。</span><span class="sxs-lookup"><span data-stu-id="6b114-373">The user can join the meeting and have a non-optimized experience.</span></span>
- <span data-ttu-id="6b114-374">会議またはグループ通話では、単一の着信ビデオ ストリームのみがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="6b114-374">Only a single incoming video stream is supported in meetings or group calls.</span></span> <span data-ttu-id="6b114-375">複数のユーザーがビデオを送信する場合、常に主要な発表者のビデオのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6b114-375">When multiple people send video, only the dominant speaker's video is shown at any given time.</span></span>
- <span data-ttu-id="6b114-376">受信および送信ビデオ ストリームの解像度は、720p に制限されています。</span><span class="sxs-lookup"><span data-stu-id="6b114-376">Incoming and outgoing video stream resolution is limited to 720p resolution.</span></span> <span data-ttu-id="6b114-377">これは WebRTC の制限です。</span><span class="sxs-lookup"><span data-stu-id="6b114-377">This is a WebRTC limitation.</span></span>
- <span data-ttu-id="6b114-378">受信カメラまたは画面共有ストリームからの 1 つのビデオ ストリームのみがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="6b114-378">Only one video stream from an incoming camera or screen share stream is supported.</span></span> <span data-ttu-id="6b114-379">着信画面が表示されている場合は、その画面共有が、主要なスピーカーのビデオではなく、表示されます。</span><span class="sxs-lookup"><span data-stu-id="6b114-379">When there's an incoming screen share, that screen share is shown, instead of the video of the dominant speaker.</span></span>
- <span data-ttu-id="6b114-380">送信画面の共有:</span><span class="sxs-lookup"><span data-stu-id="6b114-380">Outgoing screen sharing:</span></span>
    - <span data-ttu-id="6b114-381">チャットからの画面共有はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="6b114-381">Screen sharing from chat is not supported.</span></span>
    - <span data-ttu-id="6b114-382">アプリケーションの共有はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="6b114-382">Application sharing is not supported.</span></span>
- <span data-ttu-id="6b114-383">制御の受け渡し:</span><span class="sxs-lookup"><span data-stu-id="6b114-383">Give control and take control:</span></span>
    - <span data-ttu-id="6b114-384">画面共有またはアプリケーション共有セッション中はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="6b114-384">Not supported during a screen sharing or application sharing session.</span></span>
    - <span data-ttu-id="6b114-385">PowerPoint 共有セッション中はサポートされます。</span><span class="sxs-lookup"><span data-stu-id="6b114-385">Supported during a PowerPoint sharing session.</span></span>
- <span data-ttu-id="6b114-386">マルチモニター設定での画面共有の場合、メイン モニターのみ共有されます。</span><span class="sxs-lookup"><span data-stu-id="6b114-386">When screen sharing in a multi-monitor setup, only the main monitor is shared.</span></span>
- <span data-ttu-id="6b114-387">CWA での高 DPI スケーリングはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="6b114-387">High DPI scaling on CWA is not supported.</span></span>

<span data-ttu-id="6b114-388">VDI に関連していない Teams の既知の問題については、「[組織のサポートチーム](Known-issues.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6b114-388">For Teams known issues that aren't related to VDI, see [Support Teams in your organization](Known-issues.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="6b114-389">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="6b114-389">Troubleshooting</span></span>

#### <a name="troubleshoot-citrix-components"></a><span data-ttu-id="6b114-390">Citrix コンポーネントのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="6b114-390">Troubleshoot Citrix components</span></span>

<span data-ttu-id="6b114-391">VDA および CWA の問題のトラブルシューティング方法については、[このCitrix Web サイト](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b114-391">For information on how to troubleshoot VDA and CWA issues, see [this Citrix website](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html).</span></span>

## <a name="related-topics"></a><span data-ttu-id="6b114-392">関連項目</span><span class="sxs-lookup"><span data-stu-id="6b114-392">Related topics</span></span>

- [<span data-ttu-id="6b114-393">MSI を使用して Microsoft Teams をインストールする</span><span class="sxs-lookup"><span data-stu-id="6b114-393">Install Microsoft Teams using MSI</span></span>](msi-deployment.md)
- [<span data-ttu-id="6b114-394">Teams での PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="6b114-394">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="6b114-395">Windows 仮想デスクトップで Microsoft Teams を使用する</span><span class="sxs-lookup"><span data-stu-id="6b114-395">Use Microsoft Teams on Windows Virtual desktop</span></span>](https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd)
