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
ms.openlocfilehash: e286611823ddfd12b43abd3a8ff385885fd02a38
ms.sourcegitcommit: bd13aecbb25c14e17d1b64343df6d80c90b2aa45
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2020
ms.locfileid: "46803996"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a><span data-ttu-id="4cc35-103">仮想デスクトップ インフラストラクチャ用の Teams</span><span class="sxs-lookup"><span data-stu-id="4cc35-103">Teams for Virtualized Desktop Infrastructure</span></span>

<span data-ttu-id="4cc35-104">この記事では、仮想化環境で Microsoft Teams を使用する場合の要件と制限について説明します。</span><span class="sxs-lookup"><span data-stu-id="4cc35-104">This article describes the requirements and limitations for using Microsoft Teams in a virtualized environment.</span></span>

## <a name="what-is-vdi"></a><span data-ttu-id="4cc35-105">VDI とは何ですか ?</span><span class="sxs-lookup"><span data-stu-id="4cc35-105">What is VDI?</span></span>

<span data-ttu-id="4cc35-106">仮想デスクトップ インフラストラクチャ (VDI) は、データセンターの集中サーバーでデスクトップ オペレーティング システムとアプリケーションをホストする仮想化テクノロジです。</span><span class="sxs-lookup"><span data-stu-id="4cc35-106">Virtual Desktop Infrastructure (VDI) is virtualization technology that hosts a desktop operating system and applications on a centralized server in a data center.</span></span> <span data-ttu-id="4cc35-107">これにより、完全に保護され、準拠し一元化されたソースとともに、ユーザーに完全に個人用に設定されたデスクトップ エクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="4cc35-107">This enables a fully personalized desktop experience to users with a fully secured and compliant centralized source.</span></span>

<span data-ttu-id="4cc35-108">仮想環境での Microsoft Teams では、チャットとコラボレーションがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="4cc35-108">Microsoft Teams in a virtualized environment supports chat and collaboration.</span></span> <span data-ttu-id="4cc35-109">また、Windows 仮想デスクトップ、Citrix、VMware の各プラットフォームでは、通話と会議機能もサポートされています。</span><span class="sxs-lookup"><span data-stu-id="4cc35-109">And with the Windows Virtual Desktop, Citrix, and VMware platforms, calling and meeting functionality is also supported.</span></span>

<span data-ttu-id="4cc35-110">仮想化環境の Teams は、複数の構成をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="4cc35-110">Teams in a virtualized environment supports multiple configurations.</span></span> <span data-ttu-id="4cc35-111">これには、VDI、専用、共有、永続的、非永続的モードが含まれます。</span><span class="sxs-lookup"><span data-stu-id="4cc35-111">These include VDI, dedicated, shared, persistent, and non-persistent modes.</span></span> <span data-ttu-id="4cc35-112">機能は継続的に開発され、定期的に追加されます。機能は今後数か月または数年で拡張されます。</span><span class="sxs-lookup"><span data-stu-id="4cc35-112">Features are in continuous development and are added on a regular basis, and functionality will expand in the coming months and years.</span></span>

<span data-ttu-id="4cc35-113">仮想環境で Teams を使用することは、仮想化されていない環境での Teams の使用とは多少異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="4cc35-113">Using Teams in a virtualized environment might be somewhat different from using Teams in a non-virtualized environment.</span></span> <span data-ttu-id="4cc35-114">たとえば、一部の高度な機能は仮想化された環境では使用できない場合があり、ビデオの解像度が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="4cc35-114">For example, some advanced features might not be available in a virtualized environment, and video resolution might differ.</span></span>

<span data-ttu-id="4cc35-115">最適なユーザー エクスペリエンスを確保するには、この記事のガイダンスに従ってください。</span><span class="sxs-lookup"><span data-stu-id="4cc35-115">To ensure an optimal user experience, follow the guidance in this article.</span></span>

## <a name="teams-on-vdi-components"></a><span data-ttu-id="4cc35-116">VDI 上の Teams のコンポーネント</span><span class="sxs-lookup"><span data-stu-id="4cc35-116">Teams on VDI components</span></span>

<span data-ttu-id="4cc35-117">仮想化環境で Teams を使用するには、次のコンポーネントが必要です。</span><span class="sxs-lookup"><span data-stu-id="4cc35-117">Using Teams in a virtualized environment requires the following components.</span></span>

- <span data-ttu-id="4cc35-118">**仮想化ブローカー**: Azure などの仮想化プロバイダーへのリソースおよび接続マネージャー</span><span class="sxs-lookup"><span data-stu-id="4cc35-118">**Virtualization broker**: The resource and connection manager to the virtualization provider, such as Azure</span></span>
- <span data-ttu-id="4cc35-119">**仮想デスクトップ**: Microsoft Teams を実行する仮想マシン (VM) スタック</span><span class="sxs-lookup"><span data-stu-id="4cc35-119">**Virtual desktop**: The Virtual Machine (VM) stack that runs Microsoft Teams</span></span>
- <span data-ttu-id="4cc35-120">**シン クライアント**: ユーザーが物理的にやり取りするエンドポイント</span><span class="sxs-lookup"><span data-stu-id="4cc35-120">**Thin client**: The endpoint that the user physically interfaces with</span></span>
- <span data-ttu-id="4cc35-121">**Teams デスクトップアプリ**: teams デスクトップクライアントアプリ</span><span class="sxs-lookup"><span data-stu-id="4cc35-121">**Teams desktop app**: The Teams desktop client app</span></span>

## <a name="teams-on-vdi-requirements"></a><span data-ttu-id="4cc35-122">VDI 上の Teams の要件</span><span class="sxs-lookup"><span data-stu-id="4cc35-122">Teams on VDI requirements</span></span>

### <a name="virtualization-provider-requirements"></a><span data-ttu-id="4cc35-123">仮想化プロバイダーの要件</span><span class="sxs-lookup"><span data-stu-id="4cc35-123">Virtualization provider requirements</span></span>

<span data-ttu-id="4cc35-124">Teams デスクトップ アプリは、主要な仮想化ソリューション プロバイダーで検証済みです。</span><span class="sxs-lookup"><span data-stu-id="4cc35-124">The Teams desktop app was validated with leading virtualization solution providers.</span></span> <span data-ttu-id="4cc35-125">市場プロバイダーが複数ある場合は、最小要件を満たしていることを確認するために、仮想化ソリューションプロバイダーに問い合わせることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4cc35-125">With multiple market providers, we recommend that you consult your virtualization solution provider to ensure that you meet the minimum requirements.</span></span>
  
<span data-ttu-id="4cc35-126">現時点では、音声/ビデオ (AV) 最適化による VDI 上の Teams は、Windows 仮想デスクトップ、Citrix、および VMware で認定されています。</span><span class="sxs-lookup"><span data-stu-id="4cc35-126">Currently, Teams on VDI with audio/video (AV) optimization is certified with Windows Virtual Desktop, Citrix, and VMware.</span></span> <span data-ttu-id="4cc35-127">このセクションの情報を確認して、適切な機能の要件をすべて満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4cc35-127">Review the information in this section to ensure that you meet all requirements for proper functionality.</span></span>

### <a name="platforms-certified-for-teams"></a><span data-ttu-id="4cc35-128">Teams で認定したプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="4cc35-128">Platforms certified for Teams</span></span>

<span data-ttu-id="4cc35-129">次のプラットフォームには、Teams 向けの仮想デスクトップインフラストラクチャソリューションがあります。</span><span class="sxs-lookup"><span data-stu-id="4cc35-129">The following platforms have virtual desktop infrastructure solutions for Teams.</span></span>

|<span data-ttu-id="4cc35-130">プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="4cc35-130">Platform</span></span>|<span data-ttu-id="4cc35-131">ソリューション</span><span class="sxs-lookup"><span data-stu-id="4cc35-131">Solution</span></span>|
|----|---|
|![Microsoft を表すロゴ](media/microsoft-logo.png)| <span data-ttu-id="4cc35-133"><a href="https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd" target="_blank">Windows 仮想デスクトップ</a></span><span class="sxs-lookup"><span data-stu-id="4cc35-133"><a href="https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd" target="_blank">Windows Virtual Desktop</a></span></span> |
|![Citrix を表すロゴ](media/citrix-logo.png)| <span data-ttu-id="4cc35-135"><a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix Virtual Apps and Desktops</a></span><span class="sxs-lookup"><span data-stu-id="4cc35-135"><a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix Virtual Apps and Desktops</a></span></span> |
|![VMware を表すロゴ](media/vmware-logo.png)| <span data-ttu-id="4cc35-137"><a href="https://www.vmware.com/products/horizon.html" target="_blank">ヴイエムウェアホライズン</a></span><span class="sxs-lookup"><span data-stu-id="4cc35-137"><a href="https://www.vmware.com/products/horizon.html" target="_blank">VMware Horizon</a></span></span> |

### <a name="windows-virtual-desktop"></a><span data-ttu-id="4cc35-138">Windows 仮想デスクトップ</span><span class="sxs-lookup"><span data-stu-id="4cc35-138">Windows Virtual Desktop</span></span>

<span data-ttu-id="4cc35-139">Windows 仮想デスクトップでは、VDI 上の Teams に AV の最適化が提供されています。</span><span class="sxs-lookup"><span data-stu-id="4cc35-139">Windows Virtual Desktop provides AV optimization for Teams on VDI.</span></span> <span data-ttu-id="4cc35-140">詳細と要件とインストールの詳細については、「 [Windows 仮想デスクトップで Teams を使用](https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4cc35-140">To learn more and requirements and installation, see [Use Teams on Windows Virtual Desktop](https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd).</span></span>

### <a name="citrix-virtual-apps-and-desktops-requirements"></a><span data-ttu-id="4cc35-141">Citrix Virtual Apps and Desktops の要件</span><span class="sxs-lookup"><span data-stu-id="4cc35-141">Citrix Virtual Apps and Desktops requirements</span></span>

<span data-ttu-id="4cc35-142">Citrix Virtual Apps and Desktops (以前の XenApp および XenDesktop) は、VDI 上の Teams に AV 最適化を提供します。</span><span class="sxs-lookup"><span data-stu-id="4cc35-142">Citrix Virtual Apps and Desktops (formerly known as XenApp and XenDesktop) provides AV optimization for Teams on VDI.</span></span> <span data-ttu-id="4cc35-143">Citrix Virtual Apps and Desktops を使用すると、VDI 上の Teams はチャットと共同作業に加えて、通話および会議機能をサポートします。</span><span class="sxs-lookup"><span data-stu-id="4cc35-143">With Citrix Virtual Apps and Desktops, Teams on VDI supports calling and meeting functionality in addition to chat and collaboration.</span></span>

<span data-ttu-id="4cc35-144">Citrix の [ダウンロードサイト](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/)で、Citrix の仮想アプリとデスクトップの最新バージョンをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="4cc35-144">You can download the latest version of Citrix Virtual Apps and Desktops at [the Citrix downloads site](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/).</span></span> <span data-ttu-id="4cc35-145">(最初にサインインする必要があります。) 必要なコンポーネントは、デフォルトで [Citrix Workspace アプリ (CWA)](https://www.citrix.com/downloads/workspace-app/) および Virtual Delivery Agent (VDA) にバンドルされています。</span><span class="sxs-lookup"><span data-stu-id="4cc35-145">(You'll need to sign in first.) The necessary components are bundled into the [Citrix Workspace app (CWA)](https://www.citrix.com/downloads/workspace-app/) and Virtual Delivery Agent (VDA) by default.</span></span> <span data-ttu-id="4cc35-146">CWA や VDA に追加のコンポーネントやプラグインをインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4cc35-146">You don't need to install any additional components or plugins on CWA or the VDA.</span></span>

<span data-ttu-id="4cc35-147">サーバーおよびクライアントの最新の要件については、[この Citrix Web サイト](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4cc35-147">For the latest server and client requirements, see [this Citrix website](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html).</span></span>

### <a name="vmware-horizon-workspace-and-desktop-requirements"></a><span data-ttu-id="4cc35-148">VMware ホライズンワークスペースとデスクトップの要件</span><span class="sxs-lookup"><span data-stu-id="4cc35-148">VMware Horizon Workspace and Desktop requirements</span></span>

<span data-ttu-id="4cc35-149">ヴイエムウェアホライズンは、VDI での Teams のサポートを最適化し、仮想デスクトップ全体の生産性を向上させます。</span><span class="sxs-lookup"><span data-stu-id="4cc35-149">VMware Horizon provides optimized AV support for Teams on VDI for improved productivity across virtual desktops.</span></span> <span data-ttu-id="4cc35-150">最新バージョンの VMware ホライズンは、 [ヴイエムウェアのダウンロード](https://my.vmware.com/web/vmware/downloads/#all_products) ページからダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="4cc35-150">You can download the latest version of VMware Horizon from the [VMware Downloads](https://my.vmware.com/web/vmware/downloads/#all_products) page.</span></span>

## <a name="install-or-update-the-teams-desktop-app-on-vdi"></a><span data-ttu-id="4cc35-151">VDI で Teams デスクトップ アプリをインストールまたは更新する</span><span class="sxs-lookup"><span data-stu-id="4cc35-151">Install or update the Teams desktop app on VDI</span></span>

<span data-ttu-id="4cc35-152">MSI パッケージを使用したマシンごとのインストールまたはユーザーごとのインストールを用いて、VDI 用の Teams デスクトップ アプリを展開できます。</span><span class="sxs-lookup"><span data-stu-id="4cc35-152">You can deploy the Teams desktop app for VDI using a per-machine installation or per-user installation using the MSI package.</span></span> <span data-ttu-id="4cc35-153">どのアプローチを使用するかについては、永続的なセットアップを使用するか、または非永続的なセットアップを使用するか、および組織の関連機能のニーズに応じて決定します。</span><span class="sxs-lookup"><span data-stu-id="4cc35-153">Deciding on which approach to use depends on whether you use a persistent or non-persistent setup and the associated functionality needs of your organization.</span></span>

<span data-ttu-id="4cc35-154">専用の永続的なセットアップの場合、どちらのアプローチでも機能します。</span><span class="sxs-lookup"><span data-stu-id="4cc35-154">For a dedicated persistent setup, either approach would work.</span></span> <span data-ttu-id="4cc35-155">ただし、非永続的なセットアップの場合、チームは効率的に作業するために、コンピューターごとにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4cc35-155">However, for a non-persistent setup, Teams requires a per-machine installation in order to work efficiently.</span></span> <span data-ttu-id="4cc35-156">[非永続のセットアップ](#non-persistent-setup)のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4cc35-156">See the [Non-persistent setup](#non-persistent-setup) section.</span></span>

<span data-ttu-id="4cc35-157">マシンごとのインストールでは、自動更新は無効になっています。</span><span class="sxs-lookup"><span data-stu-id="4cc35-157">With per-machine installation, automatic updates is disabled.</span></span> <span data-ttu-id="4cc35-158">つまり、Teams アプリを更新するには、現在のバージョンをアンインストールして新しいバージョンに更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4cc35-158">This means that to update the Teams app, you must uninstall the current version to update to a newer version.</span></span> <span data-ttu-id="4cc35-159">ユーザーごとのインストールでは、自動更新は有効になっています。</span><span class="sxs-lookup"><span data-stu-id="4cc35-159">With per-user installation, automatic updates is enabled.</span></span> <span data-ttu-id="4cc35-160">ほとんどの VDI の展開について、マシンごとのインストールを使用して Teams を展開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4cc35-160">For most VDI deployments, we recommend you deploy Teams using per-machine installation.</span></span>

<span data-ttu-id="4cc35-161">最新の Teams バージョンに更新するには、アンインストール手順から始めて、次に最新の Teams バージョンを展開します。</span><span class="sxs-lookup"><span data-stu-id="4cc35-161">To update to the latest Teams version, start with the uninstall procedure followed by latest Teams version deployment.</span></span>

<span data-ttu-id="4cc35-162">VDI 環境での Teams AV の最適化が適切に機能するには、シン クライアント エンドポイントがインターネットにアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="4cc35-162">For Teams AV optimization in VDI environments to work properly, the thin client endpoint must have access to the internet.</span></span> <span data-ttu-id="4cc35-163">シン クライアント エンドポイントでインターネット アクセスが利用できない場合、最適化のスタートアップは成功しません。</span><span class="sxs-lookup"><span data-stu-id="4cc35-163">If internet access isn't available at the thin client endpoint, optimization startup won't be successful.</span></span> <span data-ttu-id="4cc35-164">これは、ユーザーが最適化されていないメディア状態にあることを意味します。</span><span class="sxs-lookup"><span data-stu-id="4cc35-164">This means that the user is in a non-optimized media state.</span></span>

#### <a name="dedicated-persistent-setup"></a><span data-ttu-id="4cc35-165">専用の永続的なセットアップ</span><span class="sxs-lookup"><span data-stu-id="4cc35-165">Dedicated persistent setup</span></span>

<span data-ttu-id="4cc35-166">専用の永続的なセットアップでは、ユーザーのローカル オペレーティング システムの変更は、ユーザーがログオフした後も保持されます。</span><span class="sxs-lookup"><span data-stu-id="4cc35-166">In a dedicated persistent setup, users' local operating system changes are retained after users log off.</span></span> <span data-ttu-id="4cc35-167">永続的なセットアップでは、チームはユーザーごととコンピューターごとの両方のインストールをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="4cc35-167">For persistent setup, Teams supports both per-user and per-machine installation.</span></span>

<span data-ttu-id="4cc35-168">推奨される最低限の VM 構成は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4cc35-168">The following is the recommended minimum VM configuration.</span></span>

|<span data-ttu-id="4cc35-169">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4cc35-169">Parameter</span></span>  |<span data-ttu-id="4cc35-170">ワークステーションのオペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="4cc35-170">Workstation operating system</span></span>  |<span data-ttu-id="4cc35-171">サーバーオペレーティングシステム</span><span class="sxs-lookup"><span data-stu-id="4cc35-171">Server operating system</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="4cc35-172">vCPU</span><span class="sxs-lookup"><span data-stu-id="4cc35-172">vCPU</span></span>   |    <span data-ttu-id="4cc35-173">2 コア</span><span class="sxs-lookup"><span data-stu-id="4cc35-173">2 cores</span></span>     |  <span data-ttu-id="4cc35-174">4、6、または 8。</span><span class="sxs-lookup"><span data-stu-id="4cc35-174">4,6, or 8</span></span><br><span data-ttu-id="4cc35-175">基礎となる Non-Uniform Memory Access (NUMA) 構成を理解し、それに応じて VM を構成することが重要です。</span><span class="sxs-lookup"><span data-stu-id="4cc35-175">It's important to understand the underlying non-uniform memory access (NUMA) configuration and configure your VMs accordingly.</span></span>     |
|<span data-ttu-id="4cc35-176">RAM</span><span class="sxs-lookup"><span data-stu-id="4cc35-176">RAM</span></span>     |   <span data-ttu-id="4cc35-177">4 GB</span><span class="sxs-lookup"><span data-stu-id="4cc35-177">4 GB</span></span>      | <span data-ttu-id="4cc35-178">ユーザー 1 人あたり 512 から 1024 MB</span><span class="sxs-lookup"><span data-stu-id="4cc35-178">512 to 1024 MB per user</span></span>        |
|<span data-ttu-id="4cc35-179">ストレージ</span><span class="sxs-lookup"><span data-stu-id="4cc35-179">Storage</span></span>    | <span data-ttu-id="4cc35-180">8 GB</span><span class="sxs-lookup"><span data-stu-id="4cc35-180">8 GB</span></span>        | <span data-ttu-id="4cc35-181">40 から 60 GB</span><span class="sxs-lookup"><span data-stu-id="4cc35-181">40 to 60 GB</span></span>        |

#### <a name="non-persistent-setup"></a><span data-ttu-id="4cc35-182">非永続的なセットアップ</span><span class="sxs-lookup"><span data-stu-id="4cc35-182">Non-persistent setup</span></span>

<span data-ttu-id="4cc35-183">非永続的なセットアップでは、ユーザーのローカル オペレーティング システムの変更は、ユーザーがログオフした後は保持されません。</span><span class="sxs-lookup"><span data-stu-id="4cc35-183">In a non-persistent setup, users' local operating system changes are not retained after users log off.</span></span> <span data-ttu-id="4cc35-184">このようなセットアップは、一般的に共有マルチユーザー セッションです。</span><span class="sxs-lookup"><span data-stu-id="4cc35-184">Such setups are commonly shared multi-user sessions.</span></span> <span data-ttu-id="4cc35-185">VM 構成は、ユーザー数と使用可能な物理ボックス リソースによって異なります。</span><span class="sxs-lookup"><span data-stu-id="4cc35-185">VM configuration varies based on the number of users and available physical box resources.</span></span>

<span data-ttu-id="4cc35-186">非永続的なセットアップの場合、Teams デスクトップ アプリは、ゴールデン イメージに対してマシンごとにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4cc35-186">For a non-persistent setup, the Teams desktop app must be installed per-machine to the golden image.</span></span> <span data-ttu-id="4cc35-187">(詳細に関しては、[VDI での Teams デスクトップ アプリのインストールまたは更新](#install-or-update-the-teams-desktop-app-on-vdi)セクションを参照してください) これにより、Teams アプリがユーザー セッション中でも効率的に起動できるようになります。</span><span class="sxs-lookup"><span data-stu-id="4cc35-187">(To learn more, see the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.) This ensures an efficient launch of the Teams app during a user session.</span></span>

<span data-ttu-id="4cc35-188">非永続的なセットアップで Teams を使用する場合も、効率的な Teams のランタイムデータ同期のためのプロファイルキャッシュマネージャーが必要です。これにより、適切なユーザー固有の情報 (ユーザーデータ、プロファイル、設定など) がユーザーセッション中にキャッシュされます。</span><span class="sxs-lookup"><span data-stu-id="4cc35-188">Using Teams with a non-persistent setup also requires a profile caching manager for efficient Teams runtime data sync. This ensures that the appropriate user-specific information (for example, user data, profile, and settings) is cached during the user session.</span></span> <span data-ttu-id="4cc35-189">この2つのフォルダー内のデータが同期されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4cc35-189">Make sure data in these two folders are synced.</span></span>  

- <span data-ttu-id="4cc35-190">C:\Users\username\AppData\Local\Microsoft\IdentityCache (%localAppdata%\Microsoft\IdentityCache)</span><span class="sxs-lookup"><span data-stu-id="4cc35-190">C:\Users\username\AppData\Local\Microsoft\IdentityCache (%localAppdata%\Microsoft\IdentityCache)</span></span>
- <span data-ttu-id="4cc35-191">C:\Users\username\AppData\Roaming\Microsoft\Teams (%appdata%\Microsoft\Teams)</span><span class="sxs-lookup"><span data-stu-id="4cc35-191">C:\Users\username\AppData\Roaming\Microsoft\Teams (%appdata%\Microsoft\Teams)</span></span>

<span data-ttu-id="4cc35-192">さまざまなキャッシュ マネージャー ソリューションが利用可能です。</span><span class="sxs-lookup"><span data-stu-id="4cc35-192">There are a variety of caching manager solutions available.</span></span> <span data-ttu-id="4cc35-193">たとえば、[FSLogix](https://docs.microsoft.com/fslogix/overview) があります。</span><span class="sxs-lookup"><span data-stu-id="4cc35-193">For example, [FSLogix](https://docs.microsoft.com/fslogix/overview).</span></span> <span data-ttu-id="4cc35-194">具体的な構成手順については、キャッシュ マネージャー プロバイダーに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="4cc35-194">Consult your caching manager provider for specific configuration instructions.</span></span>

##### <a name="teams-cached-content-exclusion-list-for-non-persistent-setup"></a><span data-ttu-id="4cc35-195">Teams は、非永続的なセットアップ用のコンテンツ除外リストをキャッシュしました</span><span class="sxs-lookup"><span data-stu-id="4cc35-195">Teams cached content exclusion list for non-persistent setup</span></span>

<span data-ttu-id="4cc35-196">Teams キャッシュ フォルダー %appdata%/Microsoft/Teams から以下を除外します。</span><span class="sxs-lookup"><span data-stu-id="4cc35-196">Exclude the following from the Teams caching folder, %appdata%/Microsoft/Teams.</span></span> <span data-ttu-id="4cc35-197">これらの項目を除外すると、非永続的なセットアップをさらに最適化するために、ユーザーのキャッシュサイズを小さくすることができます。</span><span class="sxs-lookup"><span data-stu-id="4cc35-197">Excluding these items helps reduce the user caching size to further optimize your non-persistent setup.</span></span>

- <span data-ttu-id="4cc35-198">.txt ファイル</span><span class="sxs-lookup"><span data-stu-id="4cc35-198">.txt files</span></span>
- <span data-ttu-id="4cc35-199">メディアスタック フォルダー</span><span class="sxs-lookup"><span data-stu-id="4cc35-199">Media-stack folder</span></span>
- <span data-ttu-id="4cc35-200">meeting-addin\Cache (%appdata%\Microsoft\Teams\meeting-addin\Cache)</span><span class="sxs-lookup"><span data-stu-id="4cc35-200">meeting-addin\Cache (%appdata%\Microsoft\Teams\meeting-addin\Cache)</span></span>

### <a name="microsoft-365-apps-for-enterprise-considerations"></a><span data-ttu-id="4cc35-201">企業向けの Microsoft 365 アプリの考慮事項</span><span class="sxs-lookup"><span data-stu-id="4cc35-201">Microsoft 365 Apps for enterprise considerations</span></span>

<span data-ttu-id="4cc35-202">VDI で企業向けの Microsoft 365 アプリを使用して Teams を展開する場合は、次の点を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="4cc35-202">Consider the following when you deploy Teams with Microsoft 365 Apps for enterprise on VDI.</span></span>

#### <a name="new-deployments-of-teams-through-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="4cc35-203">Microsoft 365 アプリを使用した、エンタープライズ向けの新しいチーム展開</span><span class="sxs-lookup"><span data-stu-id="4cc35-203">New deployments of Teams through Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="4cc35-204">企業向けの Microsoft 365 アプリを使用してチームを展開する前に、コンピューターごとのインストールを使用して展開された既存の Teams アプリをアンインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4cc35-204">Before you deploy Teams through Microsoft 365 Apps for enterprise, you must first uninstall any pre-existing Teams apps if they were deployed using per-machine installation.</span></span>

<span data-ttu-id="4cc35-205">企業向けの Microsoft 365 アプリを使用した Teams は、ユーザーごとにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="4cc35-205">Teams through Microsoft 365 Apps for enterprise is installed per-user.</span></span> <span data-ttu-id="4cc35-206">詳細については、[VDI で Teams デスクトップ アプリをインストールまたは更新する](#install-or-update-the-teams-desktop-app-on-vdi)セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4cc35-206">To learn more, see the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.</span></span>

#### <a name="teams-deployments-through-microsoft-365-apps-for-enterprise-updates"></a><span data-ttu-id="4cc35-207">Microsoft 365 アプリを使用した、エンタープライズアップデート向けの Teams の展開</span><span class="sxs-lookup"><span data-stu-id="4cc35-207">Teams deployments through Microsoft 365 Apps for enterprise updates</span></span>

<span data-ttu-id="4cc35-208">Teams は、エンタープライズ向けの Microsoft 365 アプリの既存のインストールにも追加されています。</span><span class="sxs-lookup"><span data-stu-id="4cc35-208">Teams is also being added to existing installations of Microsoft 365 Apps for enterprise.</span></span> <span data-ttu-id="4cc35-209">エンタープライズ用の Microsoft 365 アプリでは、ユーザーごとにチームをインストールするため、「 [VDI 上の teams デスクトップアプリをインストールまたは更新](#install-or-update-the-teams-desktop-app-on-vdi) する」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4cc35-209">Since Microsoft 365 Apps for enterprise installs Teams per-user only, see the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.</span></span>

#### <a name="using-teams-with-per-machine-installation-and-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="4cc35-210">コンピューターごとのインストールと Microsoft 365 アプリでの Teams の使用 (エンタープライズ向け)</span><span class="sxs-lookup"><span data-stu-id="4cc35-210">Using Teams with per-machine installation and Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="4cc35-211">エンタープライズ向けの Microsoft 365 アプリでは、各コンピューターの Teams インストールをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="4cc35-211">Microsoft 365 Apps for enterprise doesn't support per-machine installations of Teams.</span></span> <span data-ttu-id="4cc35-212">コンピューターごとのインストールを使用するには、enterprise 用の Microsoft 365 アプリから Teams を除外する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4cc35-212">To use per-machine installation, you must exclude Teams from Microsoft 365 Apps for enterprise.</span></span> <span data-ttu-id="4cc35-213">「 [Teams デスクトップアプリを VM に展開](#deploy-the-teams-desktop-app-to-the-vm) する」および「 [エンタープライズ向けの Microsoft 365 アプリを通じてチームの展開を除外する方法](#how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4cc35-213">See the [Deploy the Teams desktop app to the VM](#deploy-the-teams-desktop-app-to-the-vm) and [How to exclude Teams deployment through Microsoft 365 Apps for enterprise](#how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise) sections.</span></span>

#### <a name="how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="4cc35-214">企業向けの Microsoft 365 アプリからチームの展開を除外する方法</span><span class="sxs-lookup"><span data-stu-id="4cc35-214">How to exclude Teams deployment through Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="4cc35-215">企業向けのチームおよび Microsoft 365 アプリの詳細については、「 [enterprise 用の microsoft 365 アプリの新しいインストールからチームを除外する](https://docs.microsoft.com/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-office-365-proplus) 」および「 [グループポリシーを使用して teams のインストールを制御](https://docs.microsoft.com/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams)する方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4cc35-215">To learn more about Teams and Microsoft 365 Apps for enterprise, see [How to exclude Teams from new installations of Microsoft 365 Apps for enterprise](https://docs.microsoft.com/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-office-365-proplus) and [Use Group Policy to control the installation of Teams](https://docs.microsoft.com/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams).</span></span>

### <a name="deploy-the-teams-desktop-app-to-the-vm"></a><span data-ttu-id="4cc35-216">Teams デスクトップ アプリを VM に展開する</span><span class="sxs-lookup"><span data-stu-id="4cc35-216">Deploy the Teams desktop app to the VM</span></span>

1. <span data-ttu-id="4cc35-217">次のリンクのいずれかを使用して、VDI VM オペレーティング システムに一致する Teams MSI パッケージをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="4cc35-217">Download the Teams MSI package that matches your VDI VM operating system using one of the following links:</span></span>

    - [<span data-ttu-id="4cc35-218">32 ビット版</span><span class="sxs-lookup"><span data-stu-id="4cc35-218">32-bit version</span></span>](https://statics.teams.cdn.office.net/production-windows/1.3.00.21759/Teams_windows.msi)
    - [<span data-ttu-id="4cc35-219">64 ビット版</span><span class="sxs-lookup"><span data-stu-id="4cc35-219">64-bit version</span></span>](https://statics.teams.cdn.office.net/production-windows-x64/1.3.00.21759/Teams_windows_x64.msi)

    <span data-ttu-id="4cc35-220">必要な Teams デスクトップアプリの最小バージョンはバージョン1.3.00.4461 です。</span><span class="sxs-lookup"><span data-stu-id="4cc35-220">The minimum version of the Teams desktop app that's required is version 1.3.00.4461.</span></span> <span data-ttu-id="4cc35-221">(以前のバージョンでは、PSTN 保留はサポートされていません)。</span><span class="sxs-lookup"><span data-stu-id="4cc35-221">(PSTN hold isn't supported in earlier versions.)</span></span>

2. <span data-ttu-id="4cc35-222">次のコマンドのいずれかを実行して、MSI を VDI VM にインストールします。</span><span class="sxs-lookup"><span data-stu-id="4cc35-222">Install the MSI to the VDI VM by running one of the following commands:</span></span>

    - <span data-ttu-id="4cc35-223">ユーザーごとのインストール (既定)</span><span class="sxs-lookup"><span data-stu-id="4cc35-223">Per-user installation (default)</span></span>
  
        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSERS=1
        ```

        <span data-ttu-id="4cc35-224">このプロセスは既定のインストールであり、Teams を% AppData% ユーザーフォルダーにインストールします。</span><span class="sxs-lookup"><span data-stu-id="4cc35-224">This process is the default installation, which installs Teams to the %AppData% user folder.</span></span> <span data-ttu-id="4cc35-225">この時点で、ゴールデン イメージのセットアップは完了です。</span><span class="sxs-lookup"><span data-stu-id="4cc35-225">At this point, the golden image setup is complete.</span></span> <span data-ttu-id="4cc35-226">ユーザーごとのインストールで永続的なセットアップ以外の環境では、チームは適切に動作しません。</span><span class="sxs-lookup"><span data-stu-id="4cc35-226">Teams won't work properly with per-user installation on a non-persistent setup.</span></span>

    - <span data-ttu-id="4cc35-227">マシンごとのインストール</span><span class="sxs-lookup"><span data-stu-id="4cc35-227">Per-machine installation</span></span>

        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1 ALLUSERS=1
        ```

        <span data-ttu-id="4cc35-228">このプロセスでは、64ビットオペレーティングシステムの Program Files (x86) フォルダーと、32ビットオペレーティングシステムの Program Files フォルダーに Teams をインストールします。</span><span class="sxs-lookup"><span data-stu-id="4cc35-228">This process installs Teams to the Program Files (x86) folder on a 64-bit operating system and to the Program Files folder on a 32-bit operating system.</span></span> <span data-ttu-id="4cc35-229">この時点で、ゴールデン イメージのセットアップは完了です。</span><span class="sxs-lookup"><span data-stu-id="4cc35-229">At this point, the golden image setup is complete.</span></span> <span data-ttu-id="4cc35-230">非永続的なセットアップについては、マシンごとに Teams をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4cc35-230">Installing Teams per-machine is required for non-persistent setups.</span></span>

        <span data-ttu-id="4cc35-231">次の対話型ログオン セッションは、Teams を開始し、資格情報を要求します。</span><span class="sxs-lookup"><span data-stu-id="4cc35-231">The next interactive logon session starts Teams and asks for credentials.</span></span>

        > [!NOTE]
        > <span data-ttu-id="4cc35-232">これらの例では、 **ALLUSERS = 1** パラメーターも使用します。</span><span class="sxs-lookup"><span data-stu-id="4cc35-232">These examples also use the **ALLUSERS=1** parameter.</span></span> <span data-ttu-id="4cc35-233">このパラメーターを設定すると、チームのコンピューター全体のインストーラーがコントロールパネルの [プログラムと機能] に表示され、[アプリ] では、コンピューターのすべてのユーザーの Windows 設定の & 機能が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4cc35-233">When you set this parameter, Teams Machine-Wide Installer appears in Programs and Features in Control Panel and in Apps & features in Windows Settings for all users of the computer.</span></span> <span data-ttu-id="4cc35-234">すべてのユーザーが管理者の資格情報を持っている場合は、チームをアンインストールできます。</span><span class="sxs-lookup"><span data-stu-id="4cc35-234">All users can then uninstall Teams if they have admin credentials.</span></span>
        <span data-ttu-id="4cc35-235">**ALLUSERS = 1**と**alluser = 1**の違いを理解しておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="4cc35-235">It's important to understand the difference between **ALLUSERS=1** and **ALLUSER=1**.</span></span> <span data-ttu-id="4cc35-236">**ALLUSERS = 1**パラメーターは非 VDI および vdi 環境で使うことができますが、 **alluser = 1**パラメーターは vdi 環境でのみ使用され、コンピューター単位のインストールを指定します。</span><span class="sxs-lookup"><span data-stu-id="4cc35-236">The **ALLUSERS=1** parameter can be used in non-VDI and VDI environments, while the **ALLUSER=1** parameter is used only in VDI environments to specify a per-machine installation.</span></span>

3. <span data-ttu-id="4cc35-237">VDI VM から MSI をアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="4cc35-237">Uninstall the MSI from the VDI VM.</span></span>
  
      ```console
      msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>
      ```

      <span data-ttu-id="4cc35-238">このプロセスでは、オペレーティングシステムの環境に応じて、Program Files (x86) フォルダーまたは Program Files フォルダーから Teams がアンインストールされます。</span><span class="sxs-lookup"><span data-stu-id="4cc35-238">This process uninstalls Teams from the Program Files (x86) folder or Program Files folder, depending on the operating system environment.</span></span>

## <a name="teams-on-vdi-performance-considerations"></a><span data-ttu-id="4cc35-239">VDI 上の Teams のパフォーマンスに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="4cc35-239">Teams on VDI performance considerations</span></span>

<span data-ttu-id="4cc35-240">さまざまな仮想化設定が用意されており、それぞれが最適化のために異なるフォーカスが設定されています。</span><span class="sxs-lookup"><span data-stu-id="4cc35-240">There are a variety of virtualized setup configurations, each with a different focus for optimization.</span></span> <span data-ttu-id="4cc35-241">たとえば、構成ではユーザーの密度に重点を置いている場合があります。</span><span class="sxs-lookup"><span data-stu-id="4cc35-241">For example, a configuration might focus on user density.</span></span> <span data-ttu-id="4cc35-242">計画するときは、組織の作業負荷のニーズに合わせて、次の点を考慮してセットアップを最適化してください。</span><span class="sxs-lookup"><span data-stu-id="4cc35-242">When planning, consider the following to help optimize your setup based on your organization's workload needs.</span></span>

- <span data-ttu-id="4cc35-243">最小要件: 一部のワークロードでは、最小要件を超えるリソースを使用してセットアップを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="4cc35-243">Minimum requirement: Some workloads might require a setup using resources that are above the minimum requirements.</span></span> <span data-ttu-id="4cc35-244">たとえば、より多くのコンピューティング リソースを必要とするアプリケーションを使用する開発者向けのワークロード。</span><span class="sxs-lookup"><span data-stu-id="4cc35-244">For example, workloads for developers who use applications that demand more computing resources.</span></span>
- <span data-ttu-id="4cc35-245">依存関係: インフラストラクチャ、ワークロード、および Teams デスクトップ アプリ以外の環境に関するその他の考慮事項への依存関係が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4cc35-245">Dependencies: These include dependencies on infrastructure, workload, and other environmental considerations outside the Teams desktop app.</span></span>
- <span data-ttu-id="4cc35-246">VDI の無効な機能: Teams は、VDI の GPU 負荷集中型機能を無効にします。これは、一時的な CPU 使用率の改善に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4cc35-246">Disabled features on VDI: Teams disables GPU-intensive features for VDI, which can help improve transient CPU utilization.</span></span> <span data-ttu-id="4cc35-247">以下の機能は無効です。</span><span class="sxs-lookup"><span data-stu-id="4cc35-247">The following features are disabled:</span></span>
    - <span data-ttu-id="4cc35-248">Teams CSS アニメーション</span><span class="sxs-lookup"><span data-stu-id="4cc35-248">Teams CSS animation</span></span>
    - <span data-ttu-id="4cc35-249">Giphy の自動起動</span><span class="sxs-lookup"><span data-stu-id="4cc35-249">Giphy auto-start</span></span>

## <a name="teams-on-vdi-with-calling-and-meetings"></a><span data-ttu-id="4cc35-250">通話と会議を含む VDI 上の Teams</span><span class="sxs-lookup"><span data-stu-id="4cc35-250">Teams on VDI with calling and meetings</span></span>

<span data-ttu-id="4cc35-251">チャットと共同作業に加えて、通話と会議に関する VDI の Teams は、サポートされている仮想化プロバイダープラットフォームで利用できます。</span><span class="sxs-lookup"><span data-stu-id="4cc35-251">In addition to chat and collaboration, Teams on VDI with calling and meetings is available with supported virtualization provider platforms.</span></span> <span data-ttu-id="4cc35-252">サポートされている機能は、WebRTC メディアスタックと仮想化プロバイダーの実装に基づいています。</span><span class="sxs-lookup"><span data-stu-id="4cc35-252">Supported features are based on the WebRTC media stack and virtualization provider implementation.</span></span> <span data-ttu-id="4cc35-253">次の図では、このアーキテクチャの概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="4cc35-253">The following diagram provides an overview of the architecture.</span></span>

![VDI アーキテクチャ上の Teams を示す図](media/teams-on-vdi-architecture.png)

> [!IMPORTANT]
> <span data-ttu-id="4cc35-255">現時点では、AV の最適化を行わずに team を実行していて、最適化のためにまだサポートされていない機能を使用している場合 (アプリの共有時に制御を行う場合など)、[仮想化プロバイダー] ポリシーを設定して、Teams のリダイレクションを無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4cc35-255">If you currently run Teams without AV optimization in VDI and you use features that are not supported yet for optimization (such as Give and take control when app sharing), you have to set virtualization provider policies to turn off Teams redirection.</span></span> <span data-ttu-id="4cc35-256">つまり、Teams のメディア セッションは最適化されません。</span><span class="sxs-lookup"><span data-stu-id="4cc35-256">This means that Teams media sessions won't be optimized.</span></span> <span data-ttu-id="4cc35-257">Teams のリダイレクションを無効にするポリシーを設定する手順については、仮想化プロバイダーにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="4cc35-257">For steps on how to set policies to turn off Teams redirection, contact your virtualization provider.</span></span>

### <a name="network-requirements"></a><span data-ttu-id="4cc35-258">ネットワーク要件</span><span class="sxs-lookup"><span data-stu-id="4cc35-258">Network requirements</span></span>

<span data-ttu-id="4cc35-259">環境を評価して、クラウド全体での音声とビデオの展開に影響を与える可能性のあるリスクおよび要件を特定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4cc35-259">We recommend that you evaluate your environment to identify any risks and requirements that can influence your overall cloud voice and video deployment.</span></span> <span data-ttu-id="4cc35-260">[Skype for Business ネットワーク評価ツール](https://www.microsoft.com/download/details.aspx?id=53885)を使用して、ネットワークが Teams に対応しているかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="4cc35-260">Use the [Skype for Business Network Assessment Tool](https://www.microsoft.com/download/details.aspx?id=53885) to test whether your network is ready for Teams.</span></span>

<span data-ttu-id="4cc35-261">Teams のネットワークを準備する方法について詳しくは、「 [teams 用に組織のネットワークを準備](prepare-network.md)する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4cc35-261">To learn more about how to prepare your network for Teams, see [Prepare your organization's network for Teams](prepare-network.md).</span></span>

### <a name="migrate-from-skype-for-business-on-vdi-to-teams-on-vdi"></a><span data-ttu-id="4cc35-262">VDI上の Skype for Business から VDI 上の Teams に移行する</span><span class="sxs-lookup"><span data-stu-id="4cc35-262">Migrate from Skype for Business on VDI to Teams on VDI</span></span>

<span data-ttu-id="4cc35-263">VDI 上の Skype for Business から VDI 上の Teams に移行する場合、2 つのアプリケーションの違いに加えて、VDI も実装されている場合にはいくつかの違いがあります。</span><span class="sxs-lookup"><span data-stu-id="4cc35-263">If you're migrating from Skype for Business on VDI to Teams on VDI, besides the differences between the two applications, there are some differences when VDI is also implemented.</span></span> <span data-ttu-id="4cc35-264">Skype for Business VDI ではサポートされていて、Teams VDI では現在サポートされていない機能は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4cc35-264">Some capabilities that aren't currently supported in Teams VDI that are in Skype for Business VDI are as follows:</span></span>

- <span data-ttu-id="4cc35-265">メディアのビットレートを制限するポリシーを使用した VDI 通話エクスペリエンスの制御</span><span class="sxs-lookup"><span data-stu-id="4cc35-265">Control of VDI calling experiences with policies for limiting media bitrate</span></span>
- <span data-ttu-id="4cc35-266">VDI の一部の AV 機能を無効にするプラットフォームごとのポリシー</span><span class="sxs-lookup"><span data-stu-id="4cc35-266">Per-platform policy to disable some AV features in VDI</span></span>
- <span data-ttu-id="4cc35-267">アプリ共有時の制御の受け渡し</span><span class="sxs-lookup"><span data-stu-id="4cc35-267">Give and take control when app sharing</span></span>
- <span data-ttu-id="4cc35-268">音声なしのチャットからの画面共有</span><span class="sxs-lookup"><span data-stu-id="4cc35-268">Screen share from chat without audio</span></span>
- <span data-ttu-id="4cc35-269">ビデオと画面の共有の同時送受信</span><span class="sxs-lookup"><span data-stu-id="4cc35-269">Simultaneous video and screen sharing send and receive</span></span>

### <a name="teams-on-chrome-browser-versus-teams-desktop-app-for-vdi"></a><span data-ttu-id="4cc35-270">Chrome ブラウザーの Teams と VDI の Teams デスクトップ アプリの比較</span><span class="sxs-lookup"><span data-stu-id="4cc35-270">Teams on Chrome browser versus Teams desktop app for VDI</span></span>

<span data-ttu-id="4cc35-271">Chrome ブラウザーの Teams は、AV 最適化を備えた VDI 用の Teams デスクトップ アプリに代わるものを提供しません。</span><span class="sxs-lookup"><span data-stu-id="4cc35-271">Teams on Chrome browser doesn't provide a replacement for the Teams desktop app for VDI with AV optimization.</span></span> <span data-ttu-id="4cc35-272">チャットと共同作業のエクスペリエンスは期待どおりに機能します。</span><span class="sxs-lookup"><span data-stu-id="4cc35-272">The chat and collaboration experience works as expected.</span></span> <span data-ttu-id="4cc35-273">メディアが必要な場合は、Chrome ブラウザーでユーザーの期待を満たせない場合があります。</span><span class="sxs-lookup"><span data-stu-id="4cc35-273">When media is needed, there are some experiences that might not meet user expectations on the Chrome browser:</span></span>

- <span data-ttu-id="4cc35-274">オーディオとビデオのストリーミングのエクスペリエンスが最適でないことがあります。</span><span class="sxs-lookup"><span data-stu-id="4cc35-274">The audio and video streaming experience might not be optimal.</span></span> <span data-ttu-id="4cc35-275">ユーザーには、遅延または品質の低下が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4cc35-275">Users might experiences delays or reduced quality.</span></span>
- <span data-ttu-id="4cc35-276">デバイス設定は、ブラウザーの設定では使用できません。</span><span class="sxs-lookup"><span data-stu-id="4cc35-276">Device settings aren't available in browser settings.</span></span>
- <span data-ttu-id="4cc35-277">デバイス管理はブラウザーを介して処理され、ブラウザー サイト設定で複数の設定が必要です。</span><span class="sxs-lookup"><span data-stu-id="4cc35-277">Device management is handled through the browser and requires multiple settings in browser site settings.</span></span>
- <span data-ttu-id="4cc35-278">デバイス設定は、Windows デバイス管理でも設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4cc35-278">Device settings might also need to be set in Windows device management.</span></span>

## <a name="teams-on-vdi-with-chat-and-collaboration"></a><span data-ttu-id="4cc35-279">チャットと共同作業を備えた VDI 上の Teams</span><span class="sxs-lookup"><span data-stu-id="4cc35-279">Teams on VDI with chat and collaboration</span></span>

<span data-ttu-id="4cc35-280">組織で Teams のチャットおよび共同作業機能のみを使用する場合は、ユーザーレベル ポリシーを設定して、Teams の通話および会議機能を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="4cc35-280">If your organization wants to only use chat and collaboration features in Teams, you can set user-level policies to turn off calling and meeting functionality in Teams.</span></span> 

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a><span data-ttu-id="4cc35-281">通話および会議機能を無効にするポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="4cc35-281">Set policies to turn off calling and meeting functionality</span></span>

<span data-ttu-id="4cc35-282">Microsoft Teams 管理センターまたは PowerShell を使用してポリシーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="4cc35-282">You can set policies by using the Microsoft Teams admin center or PowerShell.</span></span> <span data-ttu-id="4cc35-283">ポリシーの変更が反映されるまでには、多少時間がかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="4cc35-283">It might take some time (a few hours) for the policy changes to propagate.</span></span> <span data-ttu-id="4cc35-284">指定したアカウントの変更がすぐに表示されない場合は、数時間後にもう一度お試しください。</span><span class="sxs-lookup"><span data-stu-id="4cc35-284">If you don't see changes for a given account immediately, try again in a few hours.</span></span>

<span data-ttu-id="4cc35-285">[**通話ポリシー**](teams-calling-policy.md): Teams には、すべての通話機能が無効になっている組み込みの DisallowCalling 通話ポリシーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4cc35-285">[**Calling polices**](teams-calling-policy.md): Teams includes the built-in DisallowCalling calling policy, in which all calling features are turned off.</span></span> <span data-ttu-id="4cc35-286">DisallowCalling ポリシーを、仮想化環境で Teams を使用する組織内のすべてのユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="4cc35-286">Assign the DisallowCalling policy to all users in your organization who use Teams in a virtualized environment.</span></span>

<span data-ttu-id="4cc35-287">[**会議ポリシー**](meeting-policies-in-teams.md): Teams には、すべての会議機能が無効になっている組み込みの AllOff 会議ポリシーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4cc35-287">[**Meeting policies**](meeting-policies-in-teams.md): Teams includes the built-in AllOff meeting policy, in which all meeting features are turned off.</span></span> <span data-ttu-id="4cc35-288">AllOff ポリシーを、仮想化環境で Teams を使用する組織内のすべてのユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="4cc35-288">Assign the AllOff policy to all users in your organization who use Teams in a virtualized environment.</span></span>

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a><span data-ttu-id="4cc35-289">Microsoft Teams 管理センターを使用してポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="4cc35-289">Assign policies using the Microsoft Teams admin center</span></span>

<span data-ttu-id="4cc35-290">DisallowCalling の通話ポリシーと割り当てをユーザーに割り当てるには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="4cc35-290">To assign the DisallowCalling calling policy and the AllOff meeting policy to a user:</span></span>

1. <span data-ttu-id="4cc35-291">Microsoft Teams 管理センターの左側のナビゲーションで、[**ユーザー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="4cc35-291">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="4cc35-292">ユーザー名の左側をクリックしてユーザーを選択し、[**編集を設定する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4cc35-292">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="4cc35-293">以下の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="4cc35-293">Do the following:</span></span>
    1.  <span data-ttu-id="4cc35-294">[**通話ポリシー**] で、[**DisallowCalling**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4cc35-294">Under **Calling policy**, click **DisallowCalling**.</span></span>
    2.  <span data-ttu-id="4cc35-295">[**会議ポリシー**] で、[**AllOff**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4cc35-295">Under **Meeting policy**, click **AllOff**.</span></span>
4. <span data-ttu-id="4cc35-296">[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4cc35-296">Click **Apply**.</span></span>

<span data-ttu-id="4cc35-297">複数のユーザーに同時にポリシーを割り当てるには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="4cc35-297">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="4cc35-298">Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動し、ユーザーを検索するか、表示にフィルターを適用してユーザーを表示します。</span><span class="sxs-lookup"><span data-stu-id="4cc35-298">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="4cc35-299">[**&#x2713;** (チェックマーク)] の列からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="4cc35-299">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="4cc35-300">すべてのユーザーを選択するには、表の上部にある [&#x2713; (チェックマーク)] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4cc35-300">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="4cc35-301">[**設定の編集**] をクリックし、必要な変更を行い、[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4cc35-301">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>

<span data-ttu-id="4cc35-302">または、次の操作も実行できます。</span><span class="sxs-lookup"><span data-stu-id="4cc35-302">Or, you can also do the following:</span></span>

1. <span data-ttu-id="4cc35-303">Microsoft Teams 管理センターの左側のナビゲーションで、割り当てるポリシーに移動します。</span><span class="sxs-lookup"><span data-stu-id="4cc35-303">In the left navigation of the Microsoft Teams admin center, go to the policy you want to assign.</span></span> <span data-ttu-id="4cc35-304">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="4cc35-304">For example:</span></span>
    - <span data-ttu-id="4cc35-305">[**音声**]  >  [**通話ポリシー**] の順に移動し、[**DisallowCalling**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4cc35-305">Go to **Voice** > **Calling policies**, and then click **DisallowCalling**.</span></span>
    - <span data-ttu-id="4cc35-306">[**会議**]  >  [**会議ポリシー**] の順に移動し、[**AllOff**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4cc35-306">Go to **Meetings** > **Meeting policies**, and then click **AllOff**.</span></span>
2. <span data-ttu-id="4cc35-307">[**ユーザーを管理する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4cc35-307">Select **Manage users**.</span></span>
3. <span data-ttu-id="4cc35-308">[**ユーザーを管理する**] ウィンドウで、表示名またはユーザー名でユーザーを検索し、名前を選択して [**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4cc35-308">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="4cc35-309">追加するユーザーごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="4cc35-309">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="4cc35-310">ユーザーの追加が完了したら、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4cc35-310">When you're finished adding users, click **Save**.</span></span>

#### <a name="assign-policies-using-powershell"></a><span data-ttu-id="4cc35-311">PowerShell を使用してポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="4cc35-311">Assign policies using PowerShell</span></span>

<span data-ttu-id="4cc35-312">次の例は、[Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) を使用して、DisallowCalling 通話ポリシーをユーザーに割り当てる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="4cc35-312">The following example shows how to use the [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) to assign the DisallowCalling calling policy to a user.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

<span data-ttu-id="4cc35-313">PowerShell を使用して通話ポリシーを管理する方法の詳細については、「[Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4cc35-313">To learn more about using PowerShell to manage calling policies, see [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).</span></span>

<span data-ttu-id="4cc35-314">次の例は、[Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) を使用して、AllOff 会議ポリシーをユーザーに割り当てる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="4cc35-314">The following example shows how to use the [Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) to assign the AllOff meeting policy to a user.</span></span>

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

<span data-ttu-id="4cc35-315">PowerShell を使用して会議ポリシーを管理する方法の詳細については、「[Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4cc35-315">To learn more about using PowerShell to manage meeting policies, see [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>

## <a name="migrate-teams-on-vdi-with-chat-and-collaboration-to-optimize-teams-with-calling-and-meetings"></a><span data-ttu-id="4cc35-316">チャットとコラボレーションを使用して VDI 上のチームを移行して、チームの通話と会議を最適化する</span><span class="sxs-lookup"><span data-stu-id="4cc35-316">Migrate Teams on VDI with chat and collaboration to optimize Teams with calling and meetings</span></span>

<span data-ttu-id="4cc35-317">ユーザーレベルのポリシーを設定して、通話と会議機能を無効にしている場合、また、AV 最適化を使用してチームに移行している場合は、VDI でのチームの既存の実装がある場合は、VDI ユーザーのチームの呼び出しと会議機能を有効にするようにポリシーを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4cc35-317">If you have an existing implementation of Teams on VDI with chat and collaboration in which you had set user-level policies to turn off calling and meeting functionality, and you're migrating to Teams with AV optimization, you must set policies to turn on calling and meeting functionality for those Teams on VDI users.</span></span>

### <a name="set-policies-to-turn-on-calling-and-meeting-functionality"></a><span data-ttu-id="4cc35-318">通話および会議機能を有効にするポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="4cc35-318">Set policies to turn on calling and meeting functionality</span></span>

<span data-ttu-id="4cc35-319">Microsoft Teams 管理センターまたは PowerShell を使用して、通話および会議ポリシーを設定し、ユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="4cc35-319">You can use the Microsoft Teams admin center or PowerShell to set and assign calling and meeting policies to your users.</span></span> <span data-ttu-id="4cc35-320">ポリシーの変更が反映されるまでに時間がかかる場合があります (数時間)。</span><span class="sxs-lookup"><span data-stu-id="4cc35-320">It can take some time (a few hours) for policy changes to propagate.</span></span> <span data-ttu-id="4cc35-321">指定したアカウントの変更がすぐに表示されない場合は、数時間が経過した後にもう一度お試しください。</span><span class="sxs-lookup"><span data-stu-id="4cc35-321">If you don't see changes for a given account immediately, try again after a few hours.</span></span>

<span data-ttu-id="4cc35-322">[**通話ポリシー**](teams-calling-policy.md): Teams の通話ポリシーは、ユーザーが使用できる通話機能を制御します。</span><span class="sxs-lookup"><span data-stu-id="4cc35-322">[**Calling polices**](teams-calling-policy.md): Calling policies in Teams control which calling features are available to users.</span></span> <span data-ttu-id="4cc35-323">Teams には、すべての通話機能が有効になっている組み込みの AallowCalling 通話ポリシーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4cc35-323">Teams includes the built-in AllowCalling calling policy, in which all calling features are turned on.</span></span> <span data-ttu-id="4cc35-324">すべての通話機能を有効にするには、AllowCalling ポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="4cc35-324">To turn on all calling features, assign the AllowCalling policy.</span></span> <span data-ttu-id="4cc35-325">または、カスタム通話ポリシーを作成して、必要な通話機能を有効にし、ユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="4cc35-325">Or, create a custom calling policy to turn on the calling features that you want and assign it to users.</span></span> 

<span data-ttu-id="4cc35-326">[**会議ポリシー**](meeting-policies-in-teams.md): Teams の会議ポリシーは、ユーザーが作成できる会議の種類と、組織内のユーザーによってスケジュールされた会議参加者が利用できる機能を制御します。</span><span class="sxs-lookup"><span data-stu-id="4cc35-326">[**Meeting policies**](meeting-policies-in-teams.md): Meeting policies in Teams control the types of meetings that users can create and the features that are available to meeting participants that are scheduled by users in your organization.</span></span> <span data-ttu-id="4cc35-327">Teams には、すべての会議機能が有効になっている組み込みの AllOn 会議ポリシーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4cc35-327">Teams includes the built-in AllOn meeting policy, in which all meeting features are turned on.</span></span> <span data-ttu-id="4cc35-328">すべての会議機能を有効にするには、AllOn ポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="4cc35-328">To turn on all meeting features, assign the AllOn policy.</span></span> <span data-ttu-id="4cc35-329">または、カスタム会議ポリシーを作成して、必要な会議機能を有効にし、ユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="4cc35-329">Or, create a custom meeting policy to turn on the meeting features that you want and assign it users.</span></span>

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a><span data-ttu-id="4cc35-330">Microsoft Teams 管理センターを使用してポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="4cc35-330">Assign policies using the Microsoft Teams admin center</span></span>

<span data-ttu-id="4cc35-331">AllowCalling の通話ポリシーと、すべての会議ポリシーをユーザーに割り当てるには:</span><span class="sxs-lookup"><span data-stu-id="4cc35-331">To assign the AllowCalling calling policy and the AllOn meeting policy to a user:</span></span>

1. <span data-ttu-id="4cc35-332">Microsoft Teams 管理センターの左側のナビゲーションで、[**ユーザー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="4cc35-332">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="4cc35-333">ユーザー名の左側をクリックしてユーザーを選択し、[**編集を設定する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4cc35-333">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="4cc35-334">以下の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="4cc35-334">Do the following:</span></span>
    1.  <span data-ttu-id="4cc35-335">[**通話ポリシー**] で、[**AllowCalling**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4cc35-335">Under **Calling policy**, click **AllowCalling**.</span></span>
    2.  <span data-ttu-id="4cc35-336">[**会議ポリシー**] で、[**AllOn**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4cc35-336">Under **Meeting policy**, click **AllOn**.</span></span>
4. <span data-ttu-id="4cc35-337">[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4cc35-337">Click **Apply**.</span></span>

<span data-ttu-id="4cc35-338">複数のユーザーに同時にポリシーを割り当てるには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="4cc35-338">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="4cc35-339">Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動し、ユーザーを検索するか、表示にフィルターを適用してユーザーを表示します。</span><span class="sxs-lookup"><span data-stu-id="4cc35-339">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="4cc35-340">[**&#x2713;** (チェックマーク)] の列からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="4cc35-340">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="4cc35-341">すべてのユーザーを選択するには、テーブルの上部にある **&#x2713;** (チェックマーク) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4cc35-341">To select all users, click the **&#x2713;** (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="4cc35-342">[**設定の編集**] をクリックし、必要な変更を行い、[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4cc35-342">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>

<span data-ttu-id="4cc35-343">または、次の操作も実行できます。</span><span class="sxs-lookup"><span data-stu-id="4cc35-343">Or, you can also do the following:</span></span>

1. <span data-ttu-id="4cc35-344">Microsoft Teams 管理センターの左側のナビゲーションで、割り当てるポリシーに移動します。</span><span class="sxs-lookup"><span data-stu-id="4cc35-344">In the left navigation of the Microsoft Teams admin center, go to the policy you want to assign.</span></span> <span data-ttu-id="4cc35-345">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="4cc35-345">For example:</span></span>
    - <span data-ttu-id="4cc35-346">[**音声**]  >  [**通話ポリシー**] の順に移動し、[**AllowCalling**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4cc35-346">Go to **Voice** > **Calling policies**, and then click **AllowCalling**.</span></span>
    - <span data-ttu-id="4cc35-347">[**会議**]  >  [**会議ポリシー**] の順に移動し、[**AllOn**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4cc35-347">Go to **Meetings** > **Meeting policies**, and then click **AllOn**.</span></span>
2. <span data-ttu-id="4cc35-348">[**ユーザーを管理する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4cc35-348">Select **Manage users**.</span></span>
3. <span data-ttu-id="4cc35-349">[**ユーザーを管理する**] ウィンドウで、表示名またはユーザー名でユーザーを検索し、名前を選択して [**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4cc35-349">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="4cc35-350">追加するユーザーごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="4cc35-350">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="4cc35-351">ユーザーの追加が完了したら、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4cc35-351">When you're finished adding users, click **Save**.</span></span>

#### <a name="assign-policies-using-powershell"></a><span data-ttu-id="4cc35-352">PowerShell を使用してポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="4cc35-352">Assign policies using PowerShell</span></span>

<span data-ttu-id="4cc35-353">次の例は、[Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) を使用して、AllowCalling 通話ポリシーをユーザーに割り当てる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="4cc35-353">The following example shows how to use the [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) to assign the AllowCalling calling policy to a user.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName AllowCalling -Identity "user email id"
```

<span data-ttu-id="4cc35-354">PowerShell を使用して通話ポリシーを管理する方法の詳細については、「[Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4cc35-354">To learn more about using PowerShell to manage calling policies, see [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).</span></span>

<span data-ttu-id="4cc35-355">次の例は、[Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) を使用して、AllOn 会議ポリシーをユーザーに割り当てる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="4cc35-355">The following example shows how to use the [Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) to assign the AllOn meeting policy to a user.</span></span>

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOn -Identity "user email id"
```

<span data-ttu-id="4cc35-356">PowerShell を使用して会議ポリシーを管理する方法の詳細については、「[Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4cc35-356">To learn more about using PowerShell to manage meeting policies, see [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>

## <a name="control-fallback-mode-in-teams"></a><span data-ttu-id="4cc35-357">Teams でのフォールバックモードの制御</span><span class="sxs-lookup"><span data-stu-id="4cc35-357">Control fallback mode in Teams</span></span>

<span data-ttu-id="4cc35-358">ユーザーがサポートされていないエンドポイントから接続している場合、ユーザーはフォールバックモードになっており、AV が最適化されていません。</span><span class="sxs-lookup"><span data-stu-id="4cc35-358">When users connect from an unsupported endpoint, the users are in fallback mode, in which AV isn't optimized.</span></span> <span data-ttu-id="4cc35-359">次のレジストリ DWORD 値のいずれかを設定することによって、フォールバックモードを無効または有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="4cc35-359">You can disable or enable fallback mode by setting one of the following registry DWORD values:</span></span>

- <span data-ttu-id="4cc35-360">HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\Teams\DisableFallback</span><span class="sxs-lookup"><span data-stu-id="4cc35-360">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Teams\DisableFallback</span></span>
- <span data-ttu-id="4cc35-361">HKEY_CURRENT_USER \SOFTWARE\Microsoft\Office\Teams\DisableFallback</span><span class="sxs-lookup"><span data-stu-id="4cc35-361">HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\Teams\DisableFallback</span></span>

<span data-ttu-id="4cc35-362">フォールバックモードを無効にするには、値を **1**に設定します。</span><span class="sxs-lookup"><span data-stu-id="4cc35-362">To disable fallback mode, set the value to **1**.</span></span> <span data-ttu-id="4cc35-363">オーディオのみを有効にするには、値を **2**に設定します。</span><span class="sxs-lookup"><span data-stu-id="4cc35-363">To enable audio only, set the value to **2**.</span></span> <span data-ttu-id="4cc35-364">値が存在しない場合、または **0** (ゼロ) に設定されている場合は、フォールバックモードが有効になります。</span><span class="sxs-lookup"><span data-stu-id="4cc35-364">If the value isn't present or is set to **0** (zero), fallback mode is enabled.</span></span>

<span data-ttu-id="4cc35-365">この機能は、Teams バージョン1.3.00.13565 以降で利用できます。</span><span class="sxs-lookup"><span data-stu-id="4cc35-365">This feature is available in Teams version 1.3.00.13565 and later.</span></span>

## <a name="known-issues-and-limitations"></a><span data-ttu-id="4cc35-366">既知の問題と制限事項</span><span class="sxs-lookup"><span data-stu-id="4cc35-366">Known issues and limitations</span></span>

### <a name="client-deployment-installation-and-setup"></a><span data-ttu-id="4cc35-367">クライアントの展開、インストール、およびセットアップ</span><span class="sxs-lookup"><span data-stu-id="4cc35-367">Client deployment, installation, and setup</span></span>

- <span data-ttu-id="4cc35-368">マシンごとのインストールでは、VDI 上の Teams は、非 VDI Teams のクライアントと同様に自動的に更新されません。</span><span class="sxs-lookup"><span data-stu-id="4cc35-368">With per-machine installation, Teams on VDI isn't automatically updated in the way that non-VDI Teams clients are.</span></span> <span data-ttu-id="4cc35-369">[VDI で Teams デスクトップ アプリをインストールまたは更新する](#install-or-update-the-teams-desktop-app-on-vdi)セクションの説明に従って新しい MSI をインストールし、VM イメージを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4cc35-369">You have to update the VM image by installing a new MSI as described in the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.</span></span> <span data-ttu-id="4cc35-370">現在のバージョンをアンインストールして新しいバージョンに更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4cc35-370">You must uninstall the current version to update to a newer version.</span></span>
- <span data-ttu-id="4cc35-371">Teams は、ユーザーごとまたはマシンごとに展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4cc35-371">Teams should be deployed either per user or per machine.</span></span> <span data-ttu-id="4cc35-372">Teams のユーザーごとおよびマシンごとの同時展開はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="4cc35-372">Deployment of Teams for concurrent per user and per machine is not supported.</span></span> <span data-ttu-id="4cc35-373">マシンごとまたはユーザーごとからこれらのモードのいずれかに移行するには、アンインストール手順に従っていずれかのモードに再展開します。</span><span class="sxs-lookup"><span data-stu-id="4cc35-373">To migrate from either per machine or per user to one of these modes, follow the uninstall procedure and redeploy to either mode.</span></span>
- <span data-ttu-id="4cc35-374">現時点では、Windows 仮想デスクトップと VMware は MacOS と Linux ベースのクライアントをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="4cc35-374">Windows Virtual Desktop and VMware don't support MacOS and Linux-based clients at this time.</span></span>
- <span data-ttu-id="4cc35-375">現時点では、Citrix は MacOs クライアントをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="4cc35-375">Citrix doesn't support MacOs clients at this time.</span></span>
- <span data-ttu-id="4cc35-376">Citrix は、エンドポイントに定義された明示的な HTTP プロキシの使用をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="4cc35-376">Citrix doesn't support the use of explicit HTTP proxies defined on an endpoint.</span></span>

### <a name="calling-and-meetings"></a><span data-ttu-id="4cc35-377">通話と会議</span><span class="sxs-lookup"><span data-stu-id="4cc35-377">Calling and meetings</span></span>

<span data-ttu-id="4cc35-378">次の通話と会議の機能はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="4cc35-378">The following calling and meeting features are not supported:</span></span>

- <span data-ttu-id="4cc35-379">拡張緊急サービス</span><span class="sxs-lookup"><span data-stu-id="4cc35-379">Enhanced emergency services</span></span>
- <span data-ttu-id="4cc35-380">Teams アプリとデバイス間の HID ボタンと LED コントロール</span><span class="sxs-lookup"><span data-stu-id="4cc35-380">HID buttons and LED controls between the Teams app and devices</span></span>
- <span data-ttu-id="4cc35-381">背景のぼかしと効果</span><span class="sxs-lookup"><span data-stu-id="4cc35-381">Background blur and effects</span></span>
- <span data-ttu-id="4cc35-382">ブロードキャスト/ライブ イベント</span><span class="sxs-lookup"><span data-stu-id="4cc35-382">Broadcast/live events</span></span>
- <span data-ttu-id="4cc35-383">場所に基づくルーティング (LBR)</span><span class="sxs-lookup"><span data-stu-id="4cc35-383">Location-Based Routing (LBR)</span></span>
- <span data-ttu-id="4cc35-384">コール パーク</span><span class="sxs-lookup"><span data-stu-id="4cc35-384">Call park</span></span>
- <span data-ttu-id="4cc35-385">コール キュー</span><span class="sxs-lookup"><span data-stu-id="4cc35-385">Call queue</span></span>

> [!NOTE]
> <span data-ttu-id="4cc35-386">現在は非 VDI 環境でのみ利用可能な通話および会議機能の追加に取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="4cc35-386">We're working on adding calling and meeting features that are currently only available in non-VDI environments.</span></span> <span data-ttu-id="4cc35-387">これには、品質、追加の画面共有シナリオ、チームに最近追加された高度な機能など、より多くの管理者の制御が含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="4cc35-387">These might include more admin control over quality, additional screen sharing scenarios, and advanced features recently added to Teams.</span></span> <span data-ttu-id="4cc35-388">今後の機能の詳細については、Teams の担当者にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="4cc35-388">Contact your Teams representative to learn more about upcoming features.</span></span>

<span data-ttu-id="4cc35-389">次に、既知の問題と通話と会議の制限事項を示します。</span><span class="sxs-lookup"><span data-stu-id="4cc35-389">The following are known issues and limitations for calling and meetings:</span></span>

- <span data-ttu-id="4cc35-390">Skype for Business の相互運用性は音声通話に限定されます。ビデオのモダリティはありません。</span><span class="sxs-lookup"><span data-stu-id="4cc35-390">Interoperability with Skype for Business is limited to audio calls; there is no video modality.</span></span>
- <span data-ttu-id="4cc35-391">会議またはグループ通話では、単一の着信ビデオ ストリームのみがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="4cc35-391">Only a single incoming video stream is supported in meetings or group calls.</span></span> <span data-ttu-id="4cc35-392">複数のユーザーがビデオを送信する場合、常に主要な発表者のビデオのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4cc35-392">When multiple people send video, only the dominant speaker's video is shown at any given time.</span></span>
- <span data-ttu-id="4cc35-393">受信および送信ビデオ ストリームの解像度は、720p に制限されています。</span><span class="sxs-lookup"><span data-stu-id="4cc35-393">Incoming and outgoing video stream resolution is limited to 720p resolution.</span></span> <span data-ttu-id="4cc35-394">これは WebRTC の制限です。</span><span class="sxs-lookup"><span data-stu-id="4cc35-394">This is a WebRTC limitation.</span></span>
- <span data-ttu-id="4cc35-395">受信カメラまたは画面共有ストリームからの 1 つのビデオ ストリームのみがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="4cc35-395">Only one video stream from an incoming camera or screen share stream is supported.</span></span> <span data-ttu-id="4cc35-396">着信画面が表示されている場合は、その画面共有が、主要なスピーカーのビデオではなく、表示されます。</span><span class="sxs-lookup"><span data-stu-id="4cc35-396">When there's an incoming screen share, that screen share is shown, instead of the video of the dominant speaker.</span></span>
- <span data-ttu-id="4cc35-397">送信画面の共有:</span><span class="sxs-lookup"><span data-stu-id="4cc35-397">Outgoing screen sharing:</span></span>
    - <span data-ttu-id="4cc35-398">アプリケーションの共有はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="4cc35-398">Application sharing is not supported.</span></span>
- <span data-ttu-id="4cc35-399">制御の受け渡し:</span><span class="sxs-lookup"><span data-stu-id="4cc35-399">Give control and take control:</span></span>
    - <span data-ttu-id="4cc35-400">画面共有またはアプリケーション共有セッション中はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="4cc35-400">Not supported during a screen sharing or application sharing session.</span></span>
    - <span data-ttu-id="4cc35-401">PowerPoint 共有セッション中はサポートされます。</span><span class="sxs-lookup"><span data-stu-id="4cc35-401">Supported during a PowerPoint sharing session.</span></span>
- <span data-ttu-id="4cc35-402">Citrix のみの制限</span><span class="sxs-lookup"><span data-stu-id="4cc35-402">Citrix-only limitations</span></span>
    - <span data-ttu-id="4cc35-403">デュアルトーンマルチ周波数 (DTMF) テレフォニーシステムとの相互操作は、現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="4cc35-403">Dual Tone Multi Frequency (DTMF) interaction with telephony systems is currently not supported.</span></span>
    - <span data-ttu-id="4cc35-404">マルチモニター設定での画面共有の場合、メイン モニターのみ共有されます。</span><span class="sxs-lookup"><span data-stu-id="4cc35-404">When screen sharing in a multi-monitor setup, only the main monitor is shared.</span></span>
    - <span data-ttu-id="4cc35-405">CWA での高 DPI スケーリングはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="4cc35-405">High DPI scaling on CWA is not supported.</span></span>

<span data-ttu-id="4cc35-406">VDI に関連していない Teams の既知の問題については、「 [組織のサポートチーム](Known-issues.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4cc35-406">For Teams known issues that aren't related to VDI, see [Support Teams in your organization](Known-issues.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="4cc35-407">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="4cc35-407">Troubleshooting</span></span>

### <a name="troubleshoot-citrix-components"></a><span data-ttu-id="4cc35-408">Citrix コンポーネントのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="4cc35-408">Troubleshoot Citrix components</span></span>

<span data-ttu-id="4cc35-409">VDA および CWA の問題のトラブルシューティング方法については、[このCitrix Web サイト](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4cc35-409">For information on how to troubleshoot VDA and CWA issues, see [this Citrix website](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html).</span></span>

## <a name="related-topics"></a><span data-ttu-id="4cc35-410">関連項目</span><span class="sxs-lookup"><span data-stu-id="4cc35-410">Related topics</span></span>

- [<span data-ttu-id="4cc35-411">MSI を使用して Microsoft Teams をインストールする</span><span class="sxs-lookup"><span data-stu-id="4cc35-411">Install Microsoft Teams using MSI</span></span>](msi-deployment.md)
- [<span data-ttu-id="4cc35-412">Teams での PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="4cc35-412">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="4cc35-413">Windows 仮想デスクトップで Microsoft Teams を使用する</span><span class="sxs-lookup"><span data-stu-id="4cc35-413">Use Microsoft Teams on Windows Virtual desktop</span></span>](https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd)
