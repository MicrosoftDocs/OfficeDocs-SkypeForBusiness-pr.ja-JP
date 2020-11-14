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
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: f8670b7a1a2ba8393f6afddb9546cd01c276808f
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031263"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a><span data-ttu-id="b55d2-103">仮想デスクトップ インフラストラクチャ用の Teams</span><span class="sxs-lookup"><span data-stu-id="b55d2-103">Teams for Virtualized Desktop Infrastructure</span></span>

<span data-ttu-id="b55d2-104">この記事では、仮想化環境で Microsoft Teams を使用する場合の要件と制限について説明します。</span><span class="sxs-lookup"><span data-stu-id="b55d2-104">This article describes the requirements and limitations for using Microsoft Teams in a virtualized environment.</span></span>

## <a name="what-is-vdi"></a><span data-ttu-id="b55d2-105">VDI とは何ですか ?</span><span class="sxs-lookup"><span data-stu-id="b55d2-105">What is VDI?</span></span>

<span data-ttu-id="b55d2-106">仮想デスクトップ インフラストラクチャ (VDI) は、データセンターの集中サーバーでデスクトップ オペレーティング システムとアプリケーションをホストする仮想化テクノロジです。</span><span class="sxs-lookup"><span data-stu-id="b55d2-106">Virtual Desktop Infrastructure (VDI) is virtualization technology that hosts a desktop operating system and applications on a centralized server in a data center.</span></span> <span data-ttu-id="b55d2-107">これにより、完全に保護され、準拠し一元化されたソースとともに、ユーザーに完全に個人用に設定されたデスクトップ エクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="b55d2-107">This enables a fully personalized desktop experience to users with a fully secured and compliant centralized source.</span></span>

<span data-ttu-id="b55d2-108">仮想環境での Microsoft Teams では、チャットとコラボレーションがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="b55d2-108">Microsoft Teams in a virtualized environment supports chat and collaboration.</span></span> <span data-ttu-id="b55d2-109">また、Windows 仮想デスクトップ、Citrix、VMware の各プラットフォームでは、通話と会議機能もサポートされています。</span><span class="sxs-lookup"><span data-stu-id="b55d2-109">And with the Windows Virtual Desktop, Citrix, and VMware platforms, calling and meeting functionality is also supported.</span></span>

<span data-ttu-id="b55d2-110">仮想化環境の Teams は、複数の構成をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="b55d2-110">Teams in a virtualized environment supports multiple configurations.</span></span> <span data-ttu-id="b55d2-111">これには、VDI、専用、共有、永続的、非永続的モードが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b55d2-111">These include VDI, dedicated, shared, persistent, and non-persistent modes.</span></span> <span data-ttu-id="b55d2-112">機能は継続的に開発され、定期的に追加されます。機能は今後数か月または数年で拡張されます。</span><span class="sxs-lookup"><span data-stu-id="b55d2-112">Features are in continuous development and are added on a regular basis, and functionality will expand in the coming months and years.</span></span>

<span data-ttu-id="b55d2-113">仮想環境で Teams を使用することは、仮想化されていない環境での Teams の使用とは多少異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b55d2-113">Using Teams in a virtualized environment might be somewhat different from using Teams in a non-virtualized environment.</span></span> <span data-ttu-id="b55d2-114">たとえば、一部の高度な機能は仮想化された環境では使用できない場合があり、ビデオの解像度が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b55d2-114">For example, some advanced features might not be available in a virtualized environment, and video resolution might differ.</span></span>

<span data-ttu-id="b55d2-115">最適なユーザー エクスペリエンスを確保するには、この記事のガイダンスに従ってください。</span><span class="sxs-lookup"><span data-stu-id="b55d2-115">To ensure an optimal user experience, follow the guidance in this article.</span></span>

 > [!Note]
> <span data-ttu-id="b55d2-116">さまざまなプラットフォームの Teams VDI の詳細については、「 [プラットフォームごとの teams の機能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b55d2-116">For details about Teams VDI on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

## <a name="teams-on-vdi-components"></a><span data-ttu-id="b55d2-117">VDI 上の Teams のコンポーネント</span><span class="sxs-lookup"><span data-stu-id="b55d2-117">Teams on VDI components</span></span>

<span data-ttu-id="b55d2-118">仮想化環境で Teams を使用するには、次のコンポーネントが必要です。</span><span class="sxs-lookup"><span data-stu-id="b55d2-118">Using Teams in a virtualized environment requires the following components.</span></span>

- <span data-ttu-id="b55d2-119">**仮想化ブローカー** : Azure などの仮想化プロバイダーへのリソースおよび接続マネージャー</span><span class="sxs-lookup"><span data-stu-id="b55d2-119">**Virtualization broker** : The resource and connection manager to the virtualization provider, such as Azure</span></span>
- <span data-ttu-id="b55d2-120">**仮想デスクトップ** : Microsoft Teams を実行する仮想マシン (VM) スタック</span><span class="sxs-lookup"><span data-stu-id="b55d2-120">**Virtual desktop** : The Virtual Machine (VM) stack that runs Microsoft Teams</span></span>
- <span data-ttu-id="b55d2-121">**シン クライアント** : ユーザーが物理的にやり取りするエンドポイント</span><span class="sxs-lookup"><span data-stu-id="b55d2-121">**Thin client** : The endpoint that the user physically interfaces with</span></span>
- <span data-ttu-id="b55d2-122">**Teams デスクトップアプリ** : teams デスクトップクライアントアプリ</span><span class="sxs-lookup"><span data-stu-id="b55d2-122">**Teams desktop app** : The Teams desktop client app</span></span>

## <a name="teams-on-vdi-requirements"></a><span data-ttu-id="b55d2-123">VDI 上の Teams の要件</span><span class="sxs-lookup"><span data-stu-id="b55d2-123">Teams on VDI requirements</span></span>

### <a name="virtualization-provider-requirements"></a><span data-ttu-id="b55d2-124">仮想化プロバイダーの要件</span><span class="sxs-lookup"><span data-stu-id="b55d2-124">Virtualization provider requirements</span></span>

<span data-ttu-id="b55d2-125">Teams デスクトップ アプリは、主要な仮想化ソリューション プロバイダーで検証済みです。</span><span class="sxs-lookup"><span data-stu-id="b55d2-125">The Teams desktop app was validated with leading virtualization solution providers.</span></span> <span data-ttu-id="b55d2-126">市場プロバイダーが複数ある場合は、最小要件を満たしていることを確認するために、仮想化ソリューションプロバイダーに問い合わせることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b55d2-126">With multiple market providers, we recommend that you consult your virtualization solution provider to ensure that you meet the minimum requirements.</span></span>
  
<span data-ttu-id="b55d2-127">現時点では、音声/ビデオ (AV) 最適化による VDI 上の Teams は、Windows 仮想デスクトップ、Citrix、および VMware で認定されています。</span><span class="sxs-lookup"><span data-stu-id="b55d2-127">Currently, Teams on VDI with audio/video (AV) optimization is certified with Windows Virtual Desktop, Citrix, and VMware.</span></span> <span data-ttu-id="b55d2-128">このセクションの情報を確認して、適切な機能の要件をすべて満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b55d2-128">Review the information in this section to ensure that you meet all requirements for proper functionality.</span></span>

### <a name="platforms-certified-for-teams"></a><span data-ttu-id="b55d2-129">Teams で認定したプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="b55d2-129">Platforms certified for Teams</span></span>

<span data-ttu-id="b55d2-130">次のプラットフォームには、Teams 向けの仮想デスクトップインフラストラクチャソリューションがあります。</span><span class="sxs-lookup"><span data-stu-id="b55d2-130">The following platforms have virtual desktop infrastructure solutions for Teams.</span></span>

|<span data-ttu-id="b55d2-131">プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="b55d2-131">Platform</span></span>|<span data-ttu-id="b55d2-132">ソリューション</span><span class="sxs-lookup"><span data-stu-id="b55d2-132">Solution</span></span>|
|----|---|
|![Microsoft を表すロゴ](media/microsoft-logo.png)| <span data-ttu-id="b55d2-134"><a href="https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd" target="_blank">Windows 仮想デスクトップ</a></span><span class="sxs-lookup"><span data-stu-id="b55d2-134"><a href="https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd" target="_blank">Windows Virtual Desktop</a></span></span> |
|![Citrix を表すロゴ](media/citrix-logo.png)| <span data-ttu-id="b55d2-136"><a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix Virtual Apps and Desktops</a></span><span class="sxs-lookup"><span data-stu-id="b55d2-136"><a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix Virtual Apps and Desktops</a></span></span> |
|![VMware を表すロゴ](media/vmware-logo.png)| <span data-ttu-id="b55d2-138"><a href="https://www.vmware.com/products/horizon.html" target="_blank">ヴイエムウェアホライズン</a></span><span class="sxs-lookup"><span data-stu-id="b55d2-138"><a href="https://www.vmware.com/products/horizon.html" target="_blank">VMware Horizon</a></span></span> |

### <a name="windows-virtual-desktop"></a><span data-ttu-id="b55d2-139">Windows 仮想デスクトップ</span><span class="sxs-lookup"><span data-stu-id="b55d2-139">Windows Virtual Desktop</span></span>

<span data-ttu-id="b55d2-140">Windows 仮想デスクトップでは、VDI 上の Teams に AV の最適化が提供されています。</span><span class="sxs-lookup"><span data-stu-id="b55d2-140">Windows Virtual Desktop provides AV optimization for Teams on VDI.</span></span> <span data-ttu-id="b55d2-141">詳細と要件とインストールの詳細については、「 [Windows 仮想デスクトップで Teams を使用](https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b55d2-141">To learn more and requirements and installation, see [Use Teams on Windows Virtual Desktop](https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd).</span></span>

### <a name="citrix-virtual-apps-and-desktops-requirements"></a><span data-ttu-id="b55d2-142">Citrix Virtual Apps and Desktops の要件</span><span class="sxs-lookup"><span data-stu-id="b55d2-142">Citrix Virtual Apps and Desktops requirements</span></span>

<span data-ttu-id="b55d2-143">Citrix Virtual Apps and Desktops (以前の XenApp および XenDesktop) は、VDI 上の Teams に AV 最適化を提供します。</span><span class="sxs-lookup"><span data-stu-id="b55d2-143">Citrix Virtual Apps and Desktops (formerly known as XenApp and XenDesktop) provides AV optimization for Teams on VDI.</span></span> <span data-ttu-id="b55d2-144">Citrix Virtual Apps and Desktops を使用すると、VDI 上の Teams はチャットと共同作業に加えて、通話および会議機能をサポートします。</span><span class="sxs-lookup"><span data-stu-id="b55d2-144">With Citrix Virtual Apps and Desktops, Teams on VDI supports calling and meeting functionality in addition to chat and collaboration.</span></span>

<span data-ttu-id="b55d2-145">Citrix の [ダウンロードサイト](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/)で、Citrix の仮想アプリとデスクトップの最新バージョンをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="b55d2-145">You can download the latest version of Citrix Virtual Apps and Desktops at [the Citrix downloads site](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/).</span></span> <span data-ttu-id="b55d2-146">(最初にサインインする必要があります。) 必要なコンポーネントは、デフォルトで [Citrix Workspace アプリ (CWA)](https://www.citrix.com/downloads/workspace-app/) および Virtual Delivery Agent (VDA) にバンドルされています。</span><span class="sxs-lookup"><span data-stu-id="b55d2-146">(You'll need to sign in first.) The necessary components are bundled into the [Citrix Workspace app (CWA)](https://www.citrix.com/downloads/workspace-app/) and Virtual Delivery Agent (VDA) by default.</span></span> <span data-ttu-id="b55d2-147">CWA や VDA に追加のコンポーネントやプラグインをインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b55d2-147">You don't need to install any additional components or plugins on CWA or the VDA.</span></span>

<span data-ttu-id="b55d2-148">サーバーおよびクライアントの最新の要件については、[この Citrix Web サイト](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b55d2-148">For the latest server and client requirements, see [this Citrix website](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html).</span></span>

### <a name="vmware-horizon-workspace-and-desktop-requirements"></a><span data-ttu-id="b55d2-149">VMware ホライズンワークスペースとデスクトップの要件</span><span class="sxs-lookup"><span data-stu-id="b55d2-149">VMware Horizon Workspace and Desktop requirements</span></span>

<span data-ttu-id="b55d2-150">VMware ホライズンは、ハイブリッドクラウドで仮想デスクトップとアプリを安全に配信するための先進プラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="b55d2-150">VMware Horizon is a modern platform for secure delivery of virtual desktops and apps across the hybrid cloud.</span></span> <span data-ttu-id="b55d2-151">ヴイエムウェアホライズンは、優れたエンドユーザーエクスペリエンスを提供するために、Teams のメディア最適化を提供します。</span><span class="sxs-lookup"><span data-stu-id="b55d2-151">To offer a great end-user experience, VMware Horizon provides media optimization for Teams.</span></span> <span data-ttu-id="b55d2-152">この最適化によって、仮想デスクトップとアプリ全体の生産性が向上し、Teams を使用した通話と会議のユーザーエクスペリエンスが強化されます。</span><span class="sxs-lookup"><span data-stu-id="b55d2-152">This optimization improves overall productivity across virtual desktops and apps, and enhances user experience when calling and meeting using Teams.</span></span>

<span data-ttu-id="b55d2-153">最新バージョンの VMware ホライズンは、 [ヴイエムウェアのダウンロード](https://my.vmware.com/web/vmware/downloads/#all_products) ページからダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="b55d2-153">You can download the latest version of VMware Horizon from the [VMware Downloads](https://my.vmware.com/web/vmware/downloads/#all_products) page.</span></span> <span data-ttu-id="b55d2-154">必要なメディア最適化コンポーネントは、既定ではホライズンエージェントとホライズンクライアントに含まれており、Teams の最適化機能を使用するために追加のプラグインをインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b55d2-154">The required media optimization components are part of the Horizon Agent and Horizon Client by default and there's no need to install any additional plug-in to use the optimization feature for Teams.</span></span>

<span data-ttu-id="b55d2-155">Teams でメディア最適化を構成する方法についての最新の要件と手順については、「 [この VMware の web サイト](https://docs.vmware.com/en/VMware-Horizon/2006/horizon-remote-desktop-features/GUID-F68FA7BB-B08F-4EFF-9BB1-1F9FC71F8214.html)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b55d2-155">To get the latest requirements and instructions on how to configure media optimization for Teams, see [this VMware website](https://docs.vmware.com/en/VMware-Horizon/2006/horizon-remote-desktop-features/GUID-F68FA7BB-B08F-4EFF-9BB1-1F9FC71F8214.html).</span></span>

## <a name="install-or-update-the-teams-desktop-app-on-vdi"></a><span data-ttu-id="b55d2-156">VDI で Teams デスクトップ アプリをインストールまたは更新する</span><span class="sxs-lookup"><span data-stu-id="b55d2-156">Install or update the Teams desktop app on VDI</span></span>

<span data-ttu-id="b55d2-157">MSI パッケージを使用したマシンごとのインストールまたはユーザーごとのインストールを用いて、VDI 用の Teams デスクトップ アプリを展開できます。</span><span class="sxs-lookup"><span data-stu-id="b55d2-157">You can deploy the Teams desktop app for VDI using a per-machine installation or per-user installation using the MSI package.</span></span> <span data-ttu-id="b55d2-158">どのアプローチを使用するかについては、永続的なセットアップを使用するか、または非永続的なセットアップを使用するか、および組織の関連機能のニーズに応じて決定します。</span><span class="sxs-lookup"><span data-stu-id="b55d2-158">Deciding on which approach to use depends on whether you use a persistent or non-persistent setup and the associated functionality needs of your organization.</span></span>

<span data-ttu-id="b55d2-159">専用の永続的なセットアップの場合、どちらのアプローチでも機能します。</span><span class="sxs-lookup"><span data-stu-id="b55d2-159">For a dedicated persistent setup, either approach would work.</span></span> <span data-ttu-id="b55d2-160">ただし、非永続的なセットアップの場合、チームは効率的に作業するために、コンピューターごとにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b55d2-160">However, for a non-persistent setup, Teams requires a per-machine installation in order to work efficiently.</span></span> <span data-ttu-id="b55d2-161">[非永続のセットアップ](#non-persistent-setup)のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b55d2-161">See the [Non-persistent setup](#non-persistent-setup) section.</span></span>

<span data-ttu-id="b55d2-162">マシンごとのインストールでは、自動更新は無効になっています。</span><span class="sxs-lookup"><span data-stu-id="b55d2-162">With per-machine installation, automatic updates is disabled.</span></span> <span data-ttu-id="b55d2-163">つまり、Teams アプリを更新するには、現在のバージョンをアンインストールして新しいバージョンに更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b55d2-163">This means that to update the Teams app, you must uninstall the current version to update to a newer version.</span></span> <span data-ttu-id="b55d2-164">ユーザーごとのインストールでは、自動更新は有効になっています。</span><span class="sxs-lookup"><span data-stu-id="b55d2-164">With per-user installation, automatic updates is enabled.</span></span> <span data-ttu-id="b55d2-165">ほとんどの VDI の展開について、マシンごとのインストールを使用して Teams を展開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b55d2-165">For most VDI deployments, we recommend you deploy Teams using per-machine installation.</span></span>

<span data-ttu-id="b55d2-166">最新の Teams バージョンに更新するには、アンインストール手順から始めて、次に最新の Teams バージョンを展開します。</span><span class="sxs-lookup"><span data-stu-id="b55d2-166">To update to the latest Teams version, start with the uninstall procedure followed by latest Teams version deployment.</span></span>

<span data-ttu-id="b55d2-167">VDI 環境での Teams AV の最適化が適切に機能するには、シン クライアント エンドポイントがインターネットにアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="b55d2-167">For Teams AV optimization in VDI environments to work properly, the thin client endpoint must have access to the internet.</span></span> <span data-ttu-id="b55d2-168">シン クライアント エンドポイントでインターネット アクセスが利用できない場合、最適化のスタートアップは成功しません。</span><span class="sxs-lookup"><span data-stu-id="b55d2-168">If internet access isn't available at the thin client endpoint, optimization startup won't be successful.</span></span> <span data-ttu-id="b55d2-169">これは、ユーザーが最適化されていないメディア状態にあることを意味します。</span><span class="sxs-lookup"><span data-stu-id="b55d2-169">This means that the user is in a non-optimized media state.</span></span>

#### <a name="dedicated-persistent-setup"></a><span data-ttu-id="b55d2-170">専用の永続的なセットアップ</span><span class="sxs-lookup"><span data-stu-id="b55d2-170">Dedicated persistent setup</span></span>

<span data-ttu-id="b55d2-171">専用の永続的なセットアップでは、ユーザーのローカル オペレーティング システムの変更は、ユーザーがログオフした後も保持されます。</span><span class="sxs-lookup"><span data-stu-id="b55d2-171">In a dedicated persistent setup, users' local operating system changes are retained after users log off.</span></span> <span data-ttu-id="b55d2-172">永続的なセットアップでは、チームはユーザーごととコンピューターごとの両方のインストールをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="b55d2-172">For persistent setup, Teams supports both per-user and per-machine installation.</span></span>

<span data-ttu-id="b55d2-173">推奨される最低限の VM 構成は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b55d2-173">The following is the recommended minimum VM configuration.</span></span>

|<span data-ttu-id="b55d2-174">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b55d2-174">Parameter</span></span>  |<span data-ttu-id="b55d2-175">ワークステーションのオペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="b55d2-175">Workstation operating system</span></span>  |<span data-ttu-id="b55d2-176">サーバーオペレーティングシステム</span><span class="sxs-lookup"><span data-stu-id="b55d2-176">Server operating system</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="b55d2-177">vCPU</span><span class="sxs-lookup"><span data-stu-id="b55d2-177">vCPU</span></span>   |    <span data-ttu-id="b55d2-178">2 コア</span><span class="sxs-lookup"><span data-stu-id="b55d2-178">2 cores</span></span>     |  <span data-ttu-id="b55d2-179">4、6、または 8。</span><span class="sxs-lookup"><span data-stu-id="b55d2-179">4,6, or 8</span></span><br><span data-ttu-id="b55d2-180">基礎となる Non-Uniform Memory Access (NUMA) 構成を理解し、それに応じて VM を構成することが重要です。</span><span class="sxs-lookup"><span data-stu-id="b55d2-180">It's important to understand the underlying non-uniform memory access (NUMA) configuration and configure your VMs accordingly.</span></span>     |
|<span data-ttu-id="b55d2-181">RAM</span><span class="sxs-lookup"><span data-stu-id="b55d2-181">RAM</span></span>     |   <span data-ttu-id="b55d2-182">4 GB</span><span class="sxs-lookup"><span data-stu-id="b55d2-182">4 GB</span></span>      | <span data-ttu-id="b55d2-183">ユーザー 1 人あたり 512 から 1024 MB</span><span class="sxs-lookup"><span data-stu-id="b55d2-183">512 to 1024 MB per user</span></span>        |
|<span data-ttu-id="b55d2-184">ストレージ</span><span class="sxs-lookup"><span data-stu-id="b55d2-184">Storage</span></span>    | <span data-ttu-id="b55d2-185">8 GB</span><span class="sxs-lookup"><span data-stu-id="b55d2-185">8 GB</span></span>        | <span data-ttu-id="b55d2-186">40 から 60 GB</span><span class="sxs-lookup"><span data-stu-id="b55d2-186">40 to 60 GB</span></span>        |

#### <a name="non-persistent-setup"></a><span data-ttu-id="b55d2-187">非永続的なセットアップ</span><span class="sxs-lookup"><span data-stu-id="b55d2-187">Non-persistent setup</span></span>

<span data-ttu-id="b55d2-188">非永続的なセットアップでは、ユーザーのローカル オペレーティング システムの変更は、ユーザーがログオフした後は保持されません。</span><span class="sxs-lookup"><span data-stu-id="b55d2-188">In a non-persistent setup, users' local operating system changes are not retained after users log off.</span></span> <span data-ttu-id="b55d2-189">このようなセットアップは、一般的に共有マルチユーザー セッションです。</span><span class="sxs-lookup"><span data-stu-id="b55d2-189">Such setups are commonly shared multi-user sessions.</span></span> <span data-ttu-id="b55d2-190">VM 構成は、ユーザー数と使用可能な物理ボックス リソースによって異なります。</span><span class="sxs-lookup"><span data-stu-id="b55d2-190">VM configuration varies based on the number of users and available physical box resources.</span></span>

<span data-ttu-id="b55d2-191">非永続的なセットアップの場合、Teams デスクトップ アプリは、ゴールデン イメージに対してマシンごとにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b55d2-191">For a non-persistent setup, the Teams desktop app must be installed per-machine to the golden image.</span></span> <span data-ttu-id="b55d2-192">(詳細に関しては、[VDI での Teams デスクトップ アプリのインストールまたは更新](#install-or-update-the-teams-desktop-app-on-vdi)セクションを参照してください) これにより、Teams アプリがユーザー セッション中でも効率的に起動できるようになります。</span><span class="sxs-lookup"><span data-stu-id="b55d2-192">(To learn more, see the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.) This ensures an efficient launch of the Teams app during a user session.</span></span>

<span data-ttu-id="b55d2-193">非永続的なセットアップで Teams を使用する場合も、効率的な Teams のランタイムデータ同期のためのプロファイルキャッシュマネージャーが必要です。これにより、適切なユーザー固有の情報 (ユーザーデータ、プロファイル、設定など) がユーザーセッション中にキャッシュされます。</span><span class="sxs-lookup"><span data-stu-id="b55d2-193">Using Teams with a non-persistent setup also requires a profile caching manager for efficient Teams runtime data sync. This ensures that the appropriate user-specific information (for example, user data, profile, and settings) is cached during the user session.</span></span> <span data-ttu-id="b55d2-194">この2つのフォルダー内のデータが同期されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b55d2-194">Make sure data in these two folders are synced.</span></span>  

- <span data-ttu-id="b55d2-195">C:\Users\username\AppData\Local\Microsoft\IdentityCache (%localAppdata%\Microsoft\IdentityCache)</span><span class="sxs-lookup"><span data-stu-id="b55d2-195">C:\Users\username\AppData\Local\Microsoft\IdentityCache (%localAppdata%\Microsoft\IdentityCache)</span></span>
- <span data-ttu-id="b55d2-196">C:\Users\username\AppData\Roaming\Microsoft\Teams (%appdata%\Microsoft\Teams)</span><span class="sxs-lookup"><span data-stu-id="b55d2-196">C:\Users\username\AppData\Roaming\Microsoft\Teams (%appdata%\Microsoft\Teams)</span></span>

<span data-ttu-id="b55d2-197">さまざまなキャッシュ マネージャー ソリューションが利用可能です。</span><span class="sxs-lookup"><span data-stu-id="b55d2-197">There are a variety of caching manager solutions available.</span></span> <span data-ttu-id="b55d2-198">たとえば、[FSLogix](https://docs.microsoft.com/fslogix/overview) があります。</span><span class="sxs-lookup"><span data-stu-id="b55d2-198">For example, [FSLogix](https://docs.microsoft.com/fslogix/overview).</span></span> <span data-ttu-id="b55d2-199">具体的な構成手順については、キャッシュ マネージャー プロバイダーに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="b55d2-199">Consult your caching manager provider for specific configuration instructions.</span></span>

##### <a name="teams-cached-content-exclusion-list-for-non-persistent-setup"></a><span data-ttu-id="b55d2-200">Teams は、非永続的なセットアップ用のコンテンツ除外リストをキャッシュしました</span><span class="sxs-lookup"><span data-stu-id="b55d2-200">Teams cached content exclusion list for non-persistent setup</span></span>

<span data-ttu-id="b55d2-201">Teams キャッシュ フォルダー %appdata%/Microsoft/Teams から以下を除外します。</span><span class="sxs-lookup"><span data-stu-id="b55d2-201">Exclude the following from the Teams caching folder, %appdata%/Microsoft/Teams.</span></span> <span data-ttu-id="b55d2-202">これらの項目を除外すると、非永続的なセットアップをさらに最適化するために、ユーザーのキャッシュサイズを小さくすることができます。</span><span class="sxs-lookup"><span data-stu-id="b55d2-202">Excluding these items helps reduce the user caching size to further optimize your non-persistent setup.</span></span>

- <span data-ttu-id="b55d2-203">.txt ファイル</span><span class="sxs-lookup"><span data-stu-id="b55d2-203">.txt files</span></span>
- <span data-ttu-id="b55d2-204">メディアスタック フォルダー</span><span class="sxs-lookup"><span data-stu-id="b55d2-204">Media-stack folder</span></span>
- <span data-ttu-id="b55d2-205">meeting-addin\Cache (%appdata%\Microsoft\Teams\meeting-addin\Cache)</span><span class="sxs-lookup"><span data-stu-id="b55d2-205">meeting-addin\Cache (%appdata%\Microsoft\Teams\meeting-addin\Cache)</span></span>

### <a name="microsoft-365-apps-for-enterprise-considerations"></a><span data-ttu-id="b55d2-206">企業向けの Microsoft 365 アプリの考慮事項</span><span class="sxs-lookup"><span data-stu-id="b55d2-206">Microsoft 365 Apps for enterprise considerations</span></span>

<span data-ttu-id="b55d2-207">VDI で企業向けの Microsoft 365 アプリを使用して Teams を展開する場合は、次の点を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="b55d2-207">Consider the following when you deploy Teams with Microsoft 365 Apps for enterprise on VDI.</span></span>

#### <a name="new-deployments-of-teams-through-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="b55d2-208">Microsoft 365 アプリを使用した、エンタープライズ向けの新しいチーム展開</span><span class="sxs-lookup"><span data-stu-id="b55d2-208">New deployments of Teams through Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="b55d2-209">企業向けの Microsoft 365 アプリを使用してチームを展開する前に、コンピューターごとのインストールを使用して展開された既存の Teams アプリをアンインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b55d2-209">Before you deploy Teams through Microsoft 365 Apps for enterprise, you must first uninstall any pre-existing Teams apps if they were deployed using per-machine installation.</span></span>

<span data-ttu-id="b55d2-210">企業向けの Microsoft 365 アプリを使用した Teams は、ユーザーごとにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="b55d2-210">Teams through Microsoft 365 Apps for enterprise is installed per-user.</span></span> <span data-ttu-id="b55d2-211">詳細については、[VDI で Teams デスクトップ アプリをインストールまたは更新する](#install-or-update-the-teams-desktop-app-on-vdi)セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b55d2-211">To learn more, see the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.</span></span>

#### <a name="teams-deployments-through-microsoft-365-apps-for-enterprise-updates"></a><span data-ttu-id="b55d2-212">Microsoft 365 アプリを使用した、エンタープライズアップデート向けの Teams の展開</span><span class="sxs-lookup"><span data-stu-id="b55d2-212">Teams deployments through Microsoft 365 Apps for enterprise updates</span></span>

<span data-ttu-id="b55d2-213">Teams は、エンタープライズ向けの Microsoft 365 アプリの既存のインストールにも追加されています。</span><span class="sxs-lookup"><span data-stu-id="b55d2-213">Teams is also being added to existing installations of Microsoft 365 Apps for enterprise.</span></span> <span data-ttu-id="b55d2-214">エンタープライズ用の Microsoft 365 アプリでは、ユーザーごとにチームをインストールするため、「 [VDI 上の teams デスクトップアプリをインストールまたは更新](#install-or-update-the-teams-desktop-app-on-vdi) する」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b55d2-214">Since Microsoft 365 Apps for enterprise installs Teams per-user only, see the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.</span></span>

#### <a name="using-teams-with-per-machine-installation-and-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="b55d2-215">コンピューターごとのインストールと Microsoft 365 アプリでの Teams の使用 (エンタープライズ向け)</span><span class="sxs-lookup"><span data-stu-id="b55d2-215">Using Teams with per-machine installation and Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="b55d2-216">エンタープライズ向けの Microsoft 365 アプリでは、各コンピューターの Teams インストールをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="b55d2-216">Microsoft 365 Apps for enterprise doesn't support per-machine installations of Teams.</span></span> <span data-ttu-id="b55d2-217">コンピューターごとのインストールを使用するには、enterprise 用の Microsoft 365 アプリから Teams を除外する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b55d2-217">To use per-machine installation, you must exclude Teams from Microsoft 365 Apps for enterprise.</span></span> <span data-ttu-id="b55d2-218">「 [Teams デスクトップアプリを VM に展開](#deploy-the-teams-desktop-app-to-the-vm) する」および「 [エンタープライズ向けの Microsoft 365 アプリを通じてチームの展開を除外する方法](#how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b55d2-218">See the [Deploy the Teams desktop app to the VM](#deploy-the-teams-desktop-app-to-the-vm) and [How to exclude Teams deployment through Microsoft 365 Apps for enterprise](#how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise) sections.</span></span>

#### <a name="how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="b55d2-219">企業向けの Microsoft 365 アプリからチームの展開を除外する方法</span><span class="sxs-lookup"><span data-stu-id="b55d2-219">How to exclude Teams deployment through Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="b55d2-220">企業向けのチームおよび Microsoft 365 アプリの詳細については、「 [enterprise 用の microsoft 365 アプリの新しいインストールからチームを除外する](https://docs.microsoft.com/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-office-365-proplus) 」および「 [グループポリシーを使用して teams のインストールを制御](https://docs.microsoft.com/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams)する方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b55d2-220">To learn more about Teams and Microsoft 365 Apps for enterprise, see [How to exclude Teams from new installations of Microsoft 365 Apps for enterprise](https://docs.microsoft.com/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-office-365-proplus) and [Use Group Policy to control the installation of Teams](https://docs.microsoft.com/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams).</span></span>

### <a name="deploy-the-teams-desktop-app-to-the-vm"></a><span data-ttu-id="b55d2-221">Teams デスクトップ アプリを VM に展開する</span><span class="sxs-lookup"><span data-stu-id="b55d2-221">Deploy the Teams desktop app to the VM</span></span>

1. <span data-ttu-id="b55d2-222">次のリンクのいずれかを使用して、VDI VM オペレーティング システムに一致する Teams MSI パッケージをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="b55d2-222">Download the Teams MSI package that matches your VDI VM operating system using one of the following links:</span></span>

    - [<span data-ttu-id="b55d2-223">32 ビット版</span><span class="sxs-lookup"><span data-stu-id="b55d2-223">32-bit version</span></span>](https://statics.teams.cdn.office.net/production-windows/1.3.00.21759/Teams_windows.msi)
    - [<span data-ttu-id="b55d2-224">64 ビット版</span><span class="sxs-lookup"><span data-stu-id="b55d2-224">64-bit version</span></span>](https://statics.teams.cdn.office.net/production-windows-x64/1.3.00.21759/Teams_windows_x64.msi)

    <span data-ttu-id="b55d2-225">必要な Teams デスクトップアプリの最小バージョンはバージョン1.3.00.4461 です。</span><span class="sxs-lookup"><span data-stu-id="b55d2-225">The minimum version of the Teams desktop app that's required is version 1.3.00.4461.</span></span> <span data-ttu-id="b55d2-226">(以前のバージョンでは、PSTN 保留はサポートされていません)。</span><span class="sxs-lookup"><span data-stu-id="b55d2-226">(PSTN hold isn't supported in earlier versions.)</span></span>

2. <span data-ttu-id="b55d2-227">次のコマンドのいずれかを実行して、MSI を VDI VM にインストールします。</span><span class="sxs-lookup"><span data-stu-id="b55d2-227">Install the MSI to the VDI VM by running one of the following commands:</span></span>

    - <span data-ttu-id="b55d2-228">ユーザーごとのインストール (既定)</span><span class="sxs-lookup"><span data-stu-id="b55d2-228">Per-user installation (default)</span></span>
  
        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSERS=1
        ```

        <span data-ttu-id="b55d2-229">このプロセスは既定のインストールであり、Teams を% AppData% ユーザーフォルダーにインストールします。</span><span class="sxs-lookup"><span data-stu-id="b55d2-229">This process is the default installation, which installs Teams to the %AppData% user folder.</span></span> <span data-ttu-id="b55d2-230">この時点で、ゴールデン イメージのセットアップは完了です。</span><span class="sxs-lookup"><span data-stu-id="b55d2-230">At this point, the golden image setup is complete.</span></span> <span data-ttu-id="b55d2-231">ユーザーごとのインストールで永続的なセットアップ以外の環境では、チームは適切に動作しません。</span><span class="sxs-lookup"><span data-stu-id="b55d2-231">Teams won't work properly with per-user installation on a non-persistent setup.</span></span>

    - <span data-ttu-id="b55d2-232">マシンごとのインストール</span><span class="sxs-lookup"><span data-stu-id="b55d2-232">Per-machine installation</span></span>

        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1 ALLUSERS=1
        ```

        <span data-ttu-id="b55d2-233">このプロセスでは、64ビットオペレーティングシステムの Program Files (x86) フォルダーと、32ビットオペレーティングシステムの Program Files フォルダーに Teams をインストールします。</span><span class="sxs-lookup"><span data-stu-id="b55d2-233">This process installs Teams to the Program Files (x86) folder on a 64-bit operating system and to the Program Files folder on a 32-bit operating system.</span></span> <span data-ttu-id="b55d2-234">この時点で、ゴールデン イメージのセットアップは完了です。</span><span class="sxs-lookup"><span data-stu-id="b55d2-234">At this point, the golden image setup is complete.</span></span> <span data-ttu-id="b55d2-235">非永続的なセットアップについては、マシンごとに Teams をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b55d2-235">Installing Teams per-machine is required for non-persistent setups.</span></span>

        <span data-ttu-id="b55d2-236">次の対話型ログオン セッションは、Teams を開始し、資格情報を要求します。</span><span class="sxs-lookup"><span data-stu-id="b55d2-236">The next interactive logon session starts Teams and asks for credentials.</span></span>

        > [!NOTE]
        > <span data-ttu-id="b55d2-237">これらの例では、 **ALLUSERS = 1** パラメーターも使用します。</span><span class="sxs-lookup"><span data-stu-id="b55d2-237">These examples also use the **ALLUSERS=1** parameter.</span></span> <span data-ttu-id="b55d2-238">このパラメーターを設定すると、コントロールパネルの [プログラムと機能] と、コンピューターのすべてのユーザーに対して [Windows 設定] の [アプリ &] の各機能に Teams Machine-Wide Installer が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b55d2-238">When you set this parameter, Teams Machine-Wide Installer appears in Programs and Features in Control Panel and in Apps & features in Windows Settings for all users of the computer.</span></span> <span data-ttu-id="b55d2-239">すべてのユーザーが管理者の資格情報を持っている場合は、チームをアンインストールできます。</span><span class="sxs-lookup"><span data-stu-id="b55d2-239">All users can then uninstall Teams if they have admin credentials.</span></span>
        <span data-ttu-id="b55d2-240">**ALLUSERS = 1** と **alluser = 1** の違いを理解しておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="b55d2-240">It's important to understand the difference between **ALLUSERS=1** and **ALLUSER=1**.</span></span> <span data-ttu-id="b55d2-241">**ALLUSERS = 1** パラメーターは非 VDI および vdi 環境で使うことができますが、 **alluser = 1** パラメーターは vdi 環境でのみ使用され、コンピューター単位のインストールを指定します。</span><span class="sxs-lookup"><span data-stu-id="b55d2-241">The **ALLUSERS=1** parameter can be used in non-VDI and VDI environments, while the **ALLUSER=1** parameter is used only in VDI environments to specify a per-machine installation.</span></span>

3. <span data-ttu-id="b55d2-242">VDI VM から MSI をアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="b55d2-242">Uninstall the MSI from the VDI VM.</span></span> <span data-ttu-id="b55d2-243">Teams をアンインストールするには、2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="b55d2-243">There are two ways to uninstall Teams.</span></span>

    - <span data-ttu-id="b55d2-244">PowerShell スクリプト: [この PowerShell スクリプト](scripts/powershell-script-deployment-cleanup.md) を使用して teams をアンインストールし、ユーザーの teams フォルダーを削除できます。</span><span class="sxs-lookup"><span data-stu-id="b55d2-244">PowerShell script: You can use [this PowerShell script](scripts/powershell-script-deployment-cleanup.md) to uninstall Teams and remove the Teams folder for a user.</span></span> <span data-ttu-id="b55d2-245">コンピューターに Teams がインストールされている各ユーザープロファイル用のスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="b55d2-245">Run the script for each user profile in which Teams was installed on the computer.</span></span>
    - <span data-ttu-id="b55d2-246">コマンドライン: 次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b55d2-246">Command line: Run the following command.</span></span>
  
      ```console
      msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>
      ```

      <span data-ttu-id="b55d2-247">このプロセスでは、オペレーティングシステムの環境に応じて、Program Files (x86) フォルダーまたは Program Files フォルダーから Teams がアンインストールされます。</span><span class="sxs-lookup"><span data-stu-id="b55d2-247">This process uninstalls Teams from the Program Files (x86) folder or Program Files folder, depending on the operating system environment.</span></span>

## <a name="teams-on-vdi-performance-considerations"></a><span data-ttu-id="b55d2-248">VDI 上の Teams のパフォーマンスに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="b55d2-248">Teams on VDI performance considerations</span></span>

<span data-ttu-id="b55d2-249">さまざまな仮想化設定が用意されており、それぞれが最適化のために異なるフォーカスが設定されています。</span><span class="sxs-lookup"><span data-stu-id="b55d2-249">There are a variety of virtualized setup configurations, each with a different focus for optimization.</span></span> <span data-ttu-id="b55d2-250">たとえば、構成ではユーザーの密度に重点を置いている場合があります。</span><span class="sxs-lookup"><span data-stu-id="b55d2-250">For example, a configuration might focus on user density.</span></span> <span data-ttu-id="b55d2-251">計画するときは、組織の作業負荷のニーズに合わせて、次の点を考慮してセットアップを最適化してください。</span><span class="sxs-lookup"><span data-stu-id="b55d2-251">When planning, consider the following to help optimize your setup based on your organization's workload needs.</span></span>

- <span data-ttu-id="b55d2-252">最小要件: 一部のワークロードでは、最小要件を超えるリソースを使用してセットアップを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="b55d2-252">Minimum requirement: Some workloads might require a setup using resources that are above the minimum requirements.</span></span> <span data-ttu-id="b55d2-253">たとえば、より多くのコンピューティング リソースを必要とするアプリケーションを使用する開発者向けのワークロード。</span><span class="sxs-lookup"><span data-stu-id="b55d2-253">For example, workloads for developers who use applications that demand more computing resources.</span></span>
- <span data-ttu-id="b55d2-254">依存関係: インフラストラクチャ、ワークロード、および Teams デスクトップ アプリ以外の環境に関するその他の考慮事項への依存関係が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b55d2-254">Dependencies: These include dependencies on infrastructure, workload, and other environmental considerations outside the Teams desktop app.</span></span>
- <span data-ttu-id="b55d2-255">VDI の無効な機能: Teams は、VDI の GPU 負荷集中型機能を無効にします。これは、一時的な CPU 使用率の改善に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b55d2-255">Disabled features on VDI: Teams disables GPU-intensive features for VDI, which can help improve transient CPU utilization.</span></span> <span data-ttu-id="b55d2-256">以下の機能は無効です。</span><span class="sxs-lookup"><span data-stu-id="b55d2-256">The following features are disabled:</span></span>
    - <span data-ttu-id="b55d2-257">Teams CSS アニメーション</span><span class="sxs-lookup"><span data-stu-id="b55d2-257">Teams CSS animation</span></span>
    - <span data-ttu-id="b55d2-258">Giphy の自動起動</span><span class="sxs-lookup"><span data-stu-id="b55d2-258">Giphy auto-start</span></span>

## <a name="teams-on-vdi-with-calling-and-meetings"></a><span data-ttu-id="b55d2-259">通話と会議を含む VDI 上の Teams</span><span class="sxs-lookup"><span data-stu-id="b55d2-259">Teams on VDI with calling and meetings</span></span>

<span data-ttu-id="b55d2-260">チャットと共同作業に加えて、通話と会議に関する VDI の Teams は、サポートされている仮想化プロバイダープラットフォームで利用できます。</span><span class="sxs-lookup"><span data-stu-id="b55d2-260">In addition to chat and collaboration, Teams on VDI with calling and meetings is available with supported virtualization provider platforms.</span></span> <span data-ttu-id="b55d2-261">サポートされている機能は、WebRTC メディアスタックと仮想化プロバイダーの実装に基づいています。</span><span class="sxs-lookup"><span data-stu-id="b55d2-261">Supported features are based on the WebRTC media stack and virtualization provider implementation.</span></span> <span data-ttu-id="b55d2-262">次の図では、このアーキテクチャの概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="b55d2-262">The following diagram provides an overview of the architecture.</span></span>

![VDI アーキテクチャ上の Teams を示す図](media/teams-on-vdi-architecture.png)

> [!IMPORTANT]
> <span data-ttu-id="b55d2-264">現時点では、AV の最適化を行わずに team を実行していて、最適化のためにまだサポートされていない機能を使用している場合 (アプリの共有時に制御を行う場合など)、[仮想化プロバイダー] ポリシーを設定して、Teams のリダイレクションを無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b55d2-264">If you currently run Teams without AV optimization in VDI and you use features that are not supported yet for optimization (such as Give and take control when app sharing), you have to set virtualization provider policies to turn off Teams redirection.</span></span> <span data-ttu-id="b55d2-265">つまり、Teams のメディア セッションは最適化されません。</span><span class="sxs-lookup"><span data-stu-id="b55d2-265">This means that Teams media sessions won't be optimized.</span></span> <span data-ttu-id="b55d2-266">Teams のリダイレクションを無効にするポリシーを設定する手順については、仮想化プロバイダーにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="b55d2-266">For steps on how to set policies to turn off Teams redirection, contact your virtualization provider.</span></span>

### <a name="network-requirements"></a><span data-ttu-id="b55d2-267">ネットワーク要件</span><span class="sxs-lookup"><span data-stu-id="b55d2-267">Network requirements</span></span>

<span data-ttu-id="b55d2-268">環境を評価して、クラウド全体での音声とビデオの展開に影響を与える可能性のあるリスクおよび要件を特定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b55d2-268">We recommend that you evaluate your environment to identify any risks and requirements that can influence your overall cloud voice and video deployment.</span></span> <span data-ttu-id="b55d2-269">[Skype for Business ネットワーク評価ツール](https://www.microsoft.com/download/details.aspx?id=53885)を使用して、ネットワークが Teams に対応しているかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="b55d2-269">Use the [Skype for Business Network Assessment Tool](https://www.microsoft.com/download/details.aspx?id=53885) to test whether your network is ready for Teams.</span></span>

<span data-ttu-id="b55d2-270">Teams のネットワークを準備する方法について詳しくは、「 [teams 用に組織のネットワークを準備](prepare-network.md)する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b55d2-270">To learn more about how to prepare your network for Teams, see [Prepare your organization's network for Teams](prepare-network.md).</span></span>

### <a name="migrate-from-skype-for-business-on-vdi-to-teams-on-vdi"></a><span data-ttu-id="b55d2-271">VDI上の Skype for Business から VDI 上の Teams に移行する</span><span class="sxs-lookup"><span data-stu-id="b55d2-271">Migrate from Skype for Business on VDI to Teams on VDI</span></span>

<span data-ttu-id="b55d2-272">VDI 上の Skype for Business から VDI 上の Teams に移行する場合、2 つのアプリケーションの違いに加えて、VDI も実装されている場合にはいくつかの違いがあります。</span><span class="sxs-lookup"><span data-stu-id="b55d2-272">If you're migrating from Skype for Business on VDI to Teams on VDI, besides the differences between the two applications, there are some differences when VDI is also implemented.</span></span> <span data-ttu-id="b55d2-273">Skype for Business VDI ではサポートされていて、Teams VDI では現在サポートされていない機能は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b55d2-273">Some capabilities that aren't currently supported in Teams VDI that are in Skype for Business VDI are as follows:</span></span>

- <span data-ttu-id="b55d2-274">VDI の一部の AV 機能を無効にするプラットフォームごとのポリシー</span><span class="sxs-lookup"><span data-stu-id="b55d2-274">Per-platform policy to disable some AV features in VDI</span></span>
- <span data-ttu-id="b55d2-275">アプリ共有時の制御の受け渡し</span><span class="sxs-lookup"><span data-stu-id="b55d2-275">Give and take control when app sharing</span></span>
- <span data-ttu-id="b55d2-276">音声なしのチャットからの画面共有</span><span class="sxs-lookup"><span data-stu-id="b55d2-276">Screen share from chat without audio</span></span>
- <span data-ttu-id="b55d2-277">ビデオと画面の共有の同時送受信</span><span class="sxs-lookup"><span data-stu-id="b55d2-277">Simultaneous video and screen sharing send and receive</span></span>

### <a name="teams-on-chrome-browser-versus-teams-desktop-app-for-vdi"></a><span data-ttu-id="b55d2-278">Chrome ブラウザーの Teams と VDI の Teams デスクトップ アプリの比較</span><span class="sxs-lookup"><span data-stu-id="b55d2-278">Teams on Chrome browser versus Teams desktop app for VDI</span></span>

<span data-ttu-id="b55d2-279">Chrome ブラウザーの Teams は、AV 最適化を備えた VDI 用の Teams デスクトップ アプリに代わるものを提供しません。</span><span class="sxs-lookup"><span data-stu-id="b55d2-279">Teams on Chrome browser doesn't provide a replacement for the Teams desktop app for VDI with AV optimization.</span></span> <span data-ttu-id="b55d2-280">チャットと共同作業のエクスペリエンスは期待どおりに機能します。</span><span class="sxs-lookup"><span data-stu-id="b55d2-280">The chat and collaboration experience works as expected.</span></span> <span data-ttu-id="b55d2-281">メディアが必要な場合は、Chrome ブラウザーでユーザーの期待を満たせない場合があります。</span><span class="sxs-lookup"><span data-stu-id="b55d2-281">When media is needed, there are some experiences that might not meet user expectations on the Chrome browser:</span></span>

- <span data-ttu-id="b55d2-282">オーディオとビデオのストリーミングのエクスペリエンスが最適でないことがあります。</span><span class="sxs-lookup"><span data-stu-id="b55d2-282">The audio and video streaming experience might not be optimal.</span></span> <span data-ttu-id="b55d2-283">ユーザーには、遅延または品質の低下が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b55d2-283">Users might experiences delays or reduced quality.</span></span>
- <span data-ttu-id="b55d2-284">デバイス設定は、ブラウザーの設定では使用できません。</span><span class="sxs-lookup"><span data-stu-id="b55d2-284">Device settings aren't available in browser settings.</span></span>
- <span data-ttu-id="b55d2-285">デバイス管理はブラウザーを介して処理され、ブラウザー サイト設定で複数の設定が必要です。</span><span class="sxs-lookup"><span data-stu-id="b55d2-285">Device management is handled through the browser and requires multiple settings in browser site settings.</span></span>
- <span data-ttu-id="b55d2-286">デバイス設定は、Windows デバイス管理でも設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b55d2-286">Device settings might also need to be set in Windows device management.</span></span>

## <a name="teams-on-vdi-with-chat-and-collaboration"></a><span data-ttu-id="b55d2-287">チャットと共同作業を備えた VDI 上の Teams</span><span class="sxs-lookup"><span data-stu-id="b55d2-287">Teams on VDI with chat and collaboration</span></span>

<span data-ttu-id="b55d2-288">組織で Teams のチャットおよび共同作業機能のみを使用する場合は、ユーザーレベル ポリシーを設定して、Teams の通話および会議機能を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="b55d2-288">If your organization wants to only use chat and collaboration features in Teams, you can set user-level policies to turn off calling and meeting functionality in Teams.</span></span> 

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a><span data-ttu-id="b55d2-289">通話および会議機能を無効にするポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="b55d2-289">Set policies to turn off calling and meeting functionality</span></span>

<span data-ttu-id="b55d2-290">Microsoft Teams 管理センターまたは PowerShell を使用してポリシーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="b55d2-290">You can set policies by using the Microsoft Teams admin center or PowerShell.</span></span> <span data-ttu-id="b55d2-291">ポリシーの変更が反映されるまでには、多少時間がかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="b55d2-291">It might take some time (a few hours) for the policy changes to propagate.</span></span> <span data-ttu-id="b55d2-292">指定したアカウントの変更がすぐに表示されない場合は、数時間後にもう一度お試しください。</span><span class="sxs-lookup"><span data-stu-id="b55d2-292">If you don't see changes for a given account immediately, try again in a few hours.</span></span>

<span data-ttu-id="b55d2-293">[**通話ポリシー**](teams-calling-policy.md): Teams には、すべての通話機能が無効になっている組み込みの DisallowCalling 通話ポリシーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b55d2-293">[**Calling polices**](teams-calling-policy.md): Teams includes the built-in DisallowCalling calling policy, in which all calling features are turned off.</span></span> <span data-ttu-id="b55d2-294">DisallowCalling ポリシーを、仮想化環境で Teams を使用する組織内のすべてのユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b55d2-294">Assign the DisallowCalling policy to all users in your organization who use Teams in a virtualized environment.</span></span>

<span data-ttu-id="b55d2-295">[**会議ポリシー**](meeting-policies-in-teams.md): Teams には、すべての会議機能が無効になっている組み込みの AllOff 会議ポリシーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b55d2-295">[**Meeting policies**](meeting-policies-in-teams.md): Teams includes the built-in AllOff meeting policy, in which all meeting features are turned off.</span></span> <span data-ttu-id="b55d2-296">AllOff ポリシーを、仮想化環境で Teams を使用する組織内のすべてのユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b55d2-296">Assign the AllOff policy to all users in your organization who use Teams in a virtualized environment.</span></span>

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a><span data-ttu-id="b55d2-297">Microsoft Teams 管理センターを使用してポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="b55d2-297">Assign policies using the Microsoft Teams admin center</span></span>

<span data-ttu-id="b55d2-298">DisallowCalling の通話ポリシーと割り当てをユーザーに割り当てるには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b55d2-298">To assign the DisallowCalling calling policy and the AllOff meeting policy to a user:</span></span>

1. <span data-ttu-id="b55d2-299">Microsoft Teams 管理センターの左側のナビゲーションで、[ **ユーザー** ] に移動します。</span><span class="sxs-lookup"><span data-stu-id="b55d2-299">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="b55d2-300">ユーザー名の左側をクリックしてユーザーを選択し、[ **編集を設定する** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b55d2-300">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="b55d2-301">以下の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b55d2-301">Do the following:</span></span>
    1.  <span data-ttu-id="b55d2-302">[ **通話ポリシー** ] で、[ **DisallowCalling** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b55d2-302">Under **Calling policy** , click **DisallowCalling**.</span></span>
    2.  <span data-ttu-id="b55d2-303">[ **会議ポリシー** ] で、[ **AllOff** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b55d2-303">Under **Meeting policy** , click **AllOff**.</span></span>
4. <span data-ttu-id="b55d2-304">[ **適用** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b55d2-304">Click **Apply**.</span></span>

<span data-ttu-id="b55d2-305">複数のユーザーに同時にポリシーを割り当てるには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b55d2-305">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="b55d2-306">Microsoft Teams 管理センターの左側のナビゲーションで、 **[ユーザー]** に移動し、ユーザーを検索するか、表示にフィルターを適用してユーザーを表示します。</span><span class="sxs-lookup"><span data-stu-id="b55d2-306">In the left navigation of the Microsoft Teams admin center, go to **Users** , and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="b55d2-307">[ **&#x2713;** (チェックマーク)] の列からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="b55d2-307">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="b55d2-308">すべてのユーザーを選択するには、表の上部にある [&#x2713; (チェックマーク)] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b55d2-308">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="b55d2-309">[ **設定の編集** ] をクリックし、必要な変更を行い、[ **適用** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b55d2-309">Click **Edit settings** , make the changes that you want, and then click **Apply**.</span></span>

<span data-ttu-id="b55d2-310">または、次の操作も実行できます。</span><span class="sxs-lookup"><span data-stu-id="b55d2-310">Or, you can also do the following:</span></span>

1. <span data-ttu-id="b55d2-311">Microsoft Teams 管理センターの左側のナビゲーションで、割り当てるポリシーに移動します。</span><span class="sxs-lookup"><span data-stu-id="b55d2-311">In the left navigation of the Microsoft Teams admin center, go to the policy you want to assign.</span></span> <span data-ttu-id="b55d2-312">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b55d2-312">For example:</span></span>
    - <span data-ttu-id="b55d2-313">[ **音声** ]  >  [ **通話ポリシー** ] の順に移動し、[ **DisallowCalling** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b55d2-313">Go to **Voice** > **Calling policies** , and then click **DisallowCalling**.</span></span>
    - <span data-ttu-id="b55d2-314">[ **会議** ]  >  [ **会議ポリシー** ] の順に移動し、[ **AllOff** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b55d2-314">Go to **Meetings** > **Meeting policies** , and then click **AllOff**.</span></span>
2. <span data-ttu-id="b55d2-315">[ **ユーザーを管理する** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b55d2-315">Select **Manage users**.</span></span>
3. <span data-ttu-id="b55d2-316">[ **ユーザーを管理する** ] ウィンドウで、表示名またはユーザー名でユーザーを検索し、名前を選択して [ **追加** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b55d2-316">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="b55d2-317">追加するユーザーごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="b55d2-317">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="b55d2-318">ユーザーの追加が完了したら、[ **保存** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b55d2-318">When you're finished adding users, click **Save**.</span></span>

#### <a name="assign-policies-using-powershell"></a><span data-ttu-id="b55d2-319">PowerShell を使用してポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="b55d2-319">Assign policies using PowerShell</span></span>

<span data-ttu-id="b55d2-320">次の例は、[Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) を使用して、DisallowCalling 通話ポリシーをユーザーに割り当てる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="b55d2-320">The following example shows how to use the [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) to assign the DisallowCalling calling policy to a user.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

<span data-ttu-id="b55d2-321">PowerShell を使用して通話ポリシーを管理する方法の詳細については、「[Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b55d2-321">To learn more about using PowerShell to manage calling policies, see [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).</span></span>

<span data-ttu-id="b55d2-322">次の例は、[Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) を使用して、AllOff 会議ポリシーをユーザーに割り当てる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="b55d2-322">The following example shows how to use the [Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) to assign the AllOff meeting policy to a user.</span></span>

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

<span data-ttu-id="b55d2-323">PowerShell を使用して会議ポリシーを管理する方法の詳細については、「[Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b55d2-323">To learn more about using PowerShell to manage meeting policies, see [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>

## <a name="migrate-teams-on-vdi-with-chat-and-collaboration-to-optimize-teams-with-calling-and-meetings"></a><span data-ttu-id="b55d2-324">チャットとコラボレーションを使用して VDI 上のチームを移行して、チームの通話と会議を最適化する</span><span class="sxs-lookup"><span data-stu-id="b55d2-324">Migrate Teams on VDI with chat and collaboration to optimize Teams with calling and meetings</span></span>

<span data-ttu-id="b55d2-325">ユーザーレベルのポリシーを設定して、通話と会議機能を無効にしている場合、また、AV 最適化を使用してチームに移行している場合は、VDI でのチームの既存の実装がある場合は、VDI ユーザーのチームの呼び出しと会議機能を有効にするようにポリシーを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b55d2-325">If you have an existing implementation of Teams on VDI with chat and collaboration in which you had set user-level policies to turn off calling and meeting functionality, and you're migrating to Teams with AV optimization, you must set policies to turn on calling and meeting functionality for those Teams on VDI users.</span></span>

### <a name="set-policies-to-turn-on-calling-and-meeting-functionality"></a><span data-ttu-id="b55d2-326">通話および会議機能を有効にするポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="b55d2-326">Set policies to turn on calling and meeting functionality</span></span>

<span data-ttu-id="b55d2-327">Microsoft Teams 管理センターまたは PowerShell を使用して、通話および会議ポリシーを設定し、ユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="b55d2-327">You can use the Microsoft Teams admin center or PowerShell to set and assign calling and meeting policies to your users.</span></span> <span data-ttu-id="b55d2-328">ポリシーの変更が反映されるまでに時間がかかる場合があります (数時間)。</span><span class="sxs-lookup"><span data-stu-id="b55d2-328">It can take some time (a few hours) for policy changes to propagate.</span></span> <span data-ttu-id="b55d2-329">指定したアカウントの変更がすぐに表示されない場合は、数時間が経過した後にもう一度お試しください。</span><span class="sxs-lookup"><span data-stu-id="b55d2-329">If you don't see changes for a given account immediately, try again after a few hours.</span></span>

<span data-ttu-id="b55d2-330">[**通話ポリシー**](teams-calling-policy.md): Teams の通話ポリシーは、ユーザーが使用できる通話機能を制御します。</span><span class="sxs-lookup"><span data-stu-id="b55d2-330">[**Calling polices**](teams-calling-policy.md): Calling policies in Teams control which calling features are available to users.</span></span> <span data-ttu-id="b55d2-331">Teams には、すべての通話機能が有効になっている組み込みの AallowCalling 通話ポリシーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b55d2-331">Teams includes the built-in AllowCalling calling policy, in which all calling features are turned on.</span></span> <span data-ttu-id="b55d2-332">すべての通話機能を有効にするには、AllowCalling ポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b55d2-332">To turn on all calling features, assign the AllowCalling policy.</span></span> <span data-ttu-id="b55d2-333">または、カスタム通話ポリシーを作成して、必要な通話機能を有効にし、ユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b55d2-333">Or, create a custom calling policy to turn on the calling features that you want and assign it to users.</span></span> 

<span data-ttu-id="b55d2-334">[**会議ポリシー**](meeting-policies-in-teams.md): Teams の会議ポリシーは、ユーザーが作成できる会議の種類と、組織内のユーザーによってスケジュールされた会議参加者が利用できる機能を制御します。</span><span class="sxs-lookup"><span data-stu-id="b55d2-334">[**Meeting policies**](meeting-policies-in-teams.md): Meeting policies in Teams control the types of meetings that users can create and the features that are available to meeting participants that are scheduled by users in your organization.</span></span> <span data-ttu-id="b55d2-335">Teams には、すべての会議機能が有効になっている組み込みの AllOn 会議ポリシーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b55d2-335">Teams includes the built-in AllOn meeting policy, in which all meeting features are turned on.</span></span> <span data-ttu-id="b55d2-336">すべての会議機能を有効にするには、AllOn ポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b55d2-336">To turn on all meeting features, assign the AllOn policy.</span></span> <span data-ttu-id="b55d2-337">または、カスタム会議ポリシーを作成して、必要な会議機能を有効にし、ユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b55d2-337">Or, create a custom meeting policy to turn on the meeting features that you want and assign it users.</span></span>

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a><span data-ttu-id="b55d2-338">Microsoft Teams 管理センターを使用してポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="b55d2-338">Assign policies using the Microsoft Teams admin center</span></span>

<span data-ttu-id="b55d2-339">AllowCalling の通話ポリシーと、すべての会議ポリシーをユーザーに割り当てるには:</span><span class="sxs-lookup"><span data-stu-id="b55d2-339">To assign the AllowCalling calling policy and the AllOn meeting policy to a user:</span></span>

1. <span data-ttu-id="b55d2-340">Microsoft Teams 管理センターの左側のナビゲーションで、[ **ユーザー** ] に移動します。</span><span class="sxs-lookup"><span data-stu-id="b55d2-340">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="b55d2-341">ユーザー名の左側をクリックしてユーザーを選択し、[ **編集を設定する** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b55d2-341">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="b55d2-342">以下の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b55d2-342">Do the following:</span></span>
    1.  <span data-ttu-id="b55d2-343">[ **通話ポリシー** ] で、[ **AllowCalling** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b55d2-343">Under **Calling policy** , click **AllowCalling**.</span></span>
    2.  <span data-ttu-id="b55d2-344">[ **会議ポリシー** ] で、[ **AllOn** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b55d2-344">Under **Meeting policy** , click **AllOn**.</span></span>
4. <span data-ttu-id="b55d2-345">[ **適用** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b55d2-345">Click **Apply**.</span></span>

<span data-ttu-id="b55d2-346">複数のユーザーに同時にポリシーを割り当てるには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b55d2-346">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="b55d2-347">Microsoft Teams 管理センターの左側のナビゲーションで、 **[ユーザー]** に移動し、ユーザーを検索するか、表示にフィルターを適用してユーザーを表示します。</span><span class="sxs-lookup"><span data-stu-id="b55d2-347">In the left navigation of the Microsoft Teams admin center, go to **Users** , and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="b55d2-348">[ **&#x2713;** (チェックマーク)] の列からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="b55d2-348">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="b55d2-349">すべてのユーザーを選択するには、テーブルの上部にある **&#x2713;** (チェックマーク) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b55d2-349">To select all users, click the **&#x2713;** (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="b55d2-350">[ **設定の編集** ] をクリックし、必要な変更を行い、[ **適用** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b55d2-350">Click **Edit settings** , make the changes that you want, and then click **Apply**.</span></span>

<span data-ttu-id="b55d2-351">または、次の操作も実行できます。</span><span class="sxs-lookup"><span data-stu-id="b55d2-351">Or, you can also do the following:</span></span>

1. <span data-ttu-id="b55d2-352">Microsoft Teams 管理センターの左側のナビゲーションで、割り当てるポリシーに移動します。</span><span class="sxs-lookup"><span data-stu-id="b55d2-352">In the left navigation of the Microsoft Teams admin center, go to the policy you want to assign.</span></span> <span data-ttu-id="b55d2-353">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b55d2-353">For example:</span></span>
    - <span data-ttu-id="b55d2-354">[ **音声** ]  >  [ **通話ポリシー** ] の順に移動し、[ **AllowCalling** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b55d2-354">Go to **Voice** > **Calling policies** , and then click **AllowCalling**.</span></span>
    - <span data-ttu-id="b55d2-355">[ **会議** ]  >  [ **会議ポリシー** ] の順に移動し、[ **AllOn** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b55d2-355">Go to **Meetings** > **Meeting policies** , and then click **AllOn**.</span></span>
2. <span data-ttu-id="b55d2-356">[ **ユーザーを管理する** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b55d2-356">Select **Manage users**.</span></span>
3. <span data-ttu-id="b55d2-357">[ **ユーザーを管理する** ] ウィンドウで、表示名またはユーザー名でユーザーを検索し、名前を選択して [ **追加** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b55d2-357">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="b55d2-358">追加するユーザーごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="b55d2-358">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="b55d2-359">ユーザーの追加が完了したら、[ **保存** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b55d2-359">When you're finished adding users, click **Save**.</span></span>

#### <a name="assign-policies-using-powershell"></a><span data-ttu-id="b55d2-360">PowerShell を使用してポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="b55d2-360">Assign policies using PowerShell</span></span>

<span data-ttu-id="b55d2-361">次の例は、[Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) を使用して、AllowCalling 通話ポリシーをユーザーに割り当てる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="b55d2-361">The following example shows how to use the [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) to assign the AllowCalling calling policy to a user.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName AllowCalling -Identity "user email id"
```

<span data-ttu-id="b55d2-362">PowerShell を使用して通話ポリシーを管理する方法の詳細については、「[Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b55d2-362">To learn more about using PowerShell to manage calling policies, see [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).</span></span>

<span data-ttu-id="b55d2-363">次の例は、[Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) を使用して、AllOn 会議ポリシーをユーザーに割り当てる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="b55d2-363">The following example shows how to use the [Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) to assign the AllOn meeting policy to a user.</span></span>

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOn -Identity "user email id"
```

<span data-ttu-id="b55d2-364">PowerShell を使用して会議ポリシーを管理する方法の詳細については、「[Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b55d2-364">To learn more about using PowerShell to manage meeting policies, see [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>

## <a name="control-fallback-mode-in-teams"></a><span data-ttu-id="b55d2-365">Teams でのフォールバックモードの制御</span><span class="sxs-lookup"><span data-stu-id="b55d2-365">Control fallback mode in Teams</span></span>

<span data-ttu-id="b55d2-366">ユーザーがサポートされていないエンドポイントから接続している場合、ユーザーはフォールバックモードになっており、AV が最適化されていません。</span><span class="sxs-lookup"><span data-stu-id="b55d2-366">When users connect from an unsupported endpoint, the users are in fallback mode, in which AV isn't optimized.</span></span> <span data-ttu-id="b55d2-367">次のレジストリ DWORD 値のいずれかを設定することによって、フォールバックモードを無効または有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="b55d2-367">You can disable or enable fallback mode by setting one of the following registry DWORD values:</span></span>

- <span data-ttu-id="b55d2-368">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Teams\DisableFallback</span><span class="sxs-lookup"><span data-stu-id="b55d2-368">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Teams\DisableFallback</span></span>
- <span data-ttu-id="b55d2-369">HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\Teams\DisableFallback</span><span class="sxs-lookup"><span data-stu-id="b55d2-369">HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\Teams\DisableFallback</span></span>

<span data-ttu-id="b55d2-370">フォールバックモードを無効にするには、値を **1** に設定します。</span><span class="sxs-lookup"><span data-stu-id="b55d2-370">To disable fallback mode, set the value to **1**.</span></span> <span data-ttu-id="b55d2-371">オーディオのみを有効にするには、値を **2** に設定します。</span><span class="sxs-lookup"><span data-stu-id="b55d2-371">To enable audio only, set the value to **2**.</span></span> <span data-ttu-id="b55d2-372">値が存在しない場合、または **0** (ゼロ) に設定されている場合は、フォールバックモードが有効になります。</span><span class="sxs-lookup"><span data-stu-id="b55d2-372">If the value isn't present or is set to **0** (zero), fallback mode is enabled.</span></span>

<span data-ttu-id="b55d2-373">この機能は、Teams バージョン1.3.00.13565 以降で利用できます。</span><span class="sxs-lookup"><span data-stu-id="b55d2-373">This feature is available in Teams version 1.3.00.13565 and later.</span></span>

## <a name="known-issues-and-limitations"></a><span data-ttu-id="b55d2-374">既知の問題と制限事項</span><span class="sxs-lookup"><span data-stu-id="b55d2-374">Known issues and limitations</span></span>

### <a name="client-deployment-installation-and-setup"></a><span data-ttu-id="b55d2-375">クライアントの展開、インストール、およびセットアップ</span><span class="sxs-lookup"><span data-stu-id="b55d2-375">Client deployment, installation, and setup</span></span>

- <span data-ttu-id="b55d2-376">マシンごとのインストールでは、VDI 上の Teams は、非 VDI Teams のクライアントと同様に自動的に更新されません。</span><span class="sxs-lookup"><span data-stu-id="b55d2-376">With per-machine installation, Teams on VDI isn't automatically updated in the way that non-VDI Teams clients are.</span></span> <span data-ttu-id="b55d2-377">[VDI で Teams デスクトップ アプリをインストールまたは更新する](#install-or-update-the-teams-desktop-app-on-vdi)セクションの説明に従って新しい MSI をインストールし、VM イメージを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b55d2-377">You have to update the VM image by installing a new MSI as described in the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.</span></span> <span data-ttu-id="b55d2-378">現在のバージョンをアンインストールして新しいバージョンに更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b55d2-378">You must uninstall the current version to update to a newer version.</span></span>
- <span data-ttu-id="b55d2-379">Teams は、ユーザーごとまたはマシンごとに展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b55d2-379">Teams should be deployed either per user or per machine.</span></span> <span data-ttu-id="b55d2-380">Teams のユーザーごとおよびマシンごとの同時展開はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="b55d2-380">Deployment of Teams for concurrent per user and per machine is not supported.</span></span> <span data-ttu-id="b55d2-381">マシンごとまたはユーザーごとからこれらのモードのいずれかに移行するには、アンインストール手順に従っていずれかのモードに再展開します。</span><span class="sxs-lookup"><span data-stu-id="b55d2-381">To migrate from either per machine or per user to one of these modes, follow the uninstall procedure and redeploy to either mode.</span></span>
- <span data-ttu-id="b55d2-382">現時点では、Windows 仮想デスクトップと VMware は MacOS と Linux ベースのクライアントをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="b55d2-382">Windows Virtual Desktop and VMware don't support MacOS and Linux-based clients at this time.</span></span>
- <span data-ttu-id="b55d2-383">現時点では、Citrix は MacOs クライアントをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="b55d2-383">Citrix doesn't support MacOs clients at this time.</span></span>
- <span data-ttu-id="b55d2-384">Citrix は、エンドポイントに定義された明示的な HTTP プロキシの使用をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="b55d2-384">Citrix doesn't support the use of explicit HTTP proxies defined on an endpoint.</span></span>

### <a name="calling-and-meetings"></a><span data-ttu-id="b55d2-385">通話と会議</span><span class="sxs-lookup"><span data-stu-id="b55d2-385">Calling and meetings</span></span>

<span data-ttu-id="b55d2-386">次の通話と会議の機能はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="b55d2-386">The following calling and meeting features are not supported:</span></span>

- <span data-ttu-id="b55d2-387">拡張緊急サービス</span><span class="sxs-lookup"><span data-stu-id="b55d2-387">Enhanced emergency services</span></span>
- <span data-ttu-id="b55d2-388">Teams アプリとデバイス間の HID ボタンと LED コントロール</span><span class="sxs-lookup"><span data-stu-id="b55d2-388">HID buttons and LED controls between the Teams app and devices</span></span>
- <span data-ttu-id="b55d2-389">背景のぼかしと効果</span><span class="sxs-lookup"><span data-stu-id="b55d2-389">Background blur and effects</span></span>
- <span data-ttu-id="b55d2-390">ブロードキャストおよびライブイベントプロデューサーと発表者の役割</span><span class="sxs-lookup"><span data-stu-id="b55d2-390">Broadcast and live event producer and presenter roles</span></span>
- <span data-ttu-id="b55d2-391">場所に基づくルーティング (LBR)</span><span class="sxs-lookup"><span data-stu-id="b55d2-391">Location-Based Routing (LBR)</span></span>
- <span data-ttu-id="b55d2-392">コール パーク</span><span class="sxs-lookup"><span data-stu-id="b55d2-392">Call park</span></span>
- <span data-ttu-id="b55d2-393">コール キュー</span><span class="sxs-lookup"><span data-stu-id="b55d2-393">Call queue</span></span>
- <span data-ttu-id="b55d2-394">共有システムオーディオ/コンピューターのサウンド</span><span class="sxs-lookup"><span data-stu-id="b55d2-394">Shared system audio/computer sound</span></span>
- <span data-ttu-id="b55d2-395">ダイレクト ルーティングのメディア バイパス</span><span class="sxs-lookup"><span data-stu-id="b55d2-395">Media bypass for Direct Routing</span></span>

> [!NOTE]
> <span data-ttu-id="b55d2-396">現在は非 VDI 環境でのみ利用可能な通話および会議機能の追加に取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="b55d2-396">We're working on adding calling and meeting features that are currently only available in non-VDI environments.</span></span> <span data-ttu-id="b55d2-397">これには、品質、追加の画面共有シナリオ、チームに最近追加された高度な機能など、より多くの管理者の制御が含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b55d2-397">These might include more admin control over quality, additional screen sharing scenarios, and advanced features recently added to Teams.</span></span> <span data-ttu-id="b55d2-398">今後の機能の詳細については、Teams の担当者にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="b55d2-398">Contact your Teams representative to learn more about upcoming features.</span></span>

<span data-ttu-id="b55d2-399">次に、既知の問題と通話と会議の制限事項を示します。</span><span class="sxs-lookup"><span data-stu-id="b55d2-399">The following are known issues and limitations for calling and meetings:</span></span>

- <span data-ttu-id="b55d2-400">Skype for Business の相互運用性は音声通話に限定されます。ビデオのモダリティはありません。</span><span class="sxs-lookup"><span data-stu-id="b55d2-400">Interoperability with Skype for Business is limited to audio calls; there is no video modality.</span></span>
- <span data-ttu-id="b55d2-401">会議またはグループ通話では、単一の着信ビデオ ストリームのみがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="b55d2-401">Only a single incoming video stream is supported in meetings or group calls.</span></span> <span data-ttu-id="b55d2-402">複数のユーザーがビデオを送信する場合、常に主要な発表者のビデオのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b55d2-402">When multiple people send video, only the dominant speaker's video is shown at any given time.</span></span>
- <span data-ttu-id="b55d2-403">受信および送信ビデオ ストリームの解像度は、720p に制限されています。</span><span class="sxs-lookup"><span data-stu-id="b55d2-403">Incoming and outgoing video stream resolution is limited to 720p resolution.</span></span> <span data-ttu-id="b55d2-404">これは WebRTC の制限です。</span><span class="sxs-lookup"><span data-stu-id="b55d2-404">This is a WebRTC limitation.</span></span>
- <span data-ttu-id="b55d2-405">受信カメラまたは画面共有ストリームからの 1 つのビデオ ストリームのみがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="b55d2-405">Only one video stream from an incoming camera or screen share stream is supported.</span></span> <span data-ttu-id="b55d2-406">着信画面が表示されている場合は、その画面共有が、主要なスピーカーのビデオではなく、表示されます。</span><span class="sxs-lookup"><span data-stu-id="b55d2-406">When there's an incoming screen share, that screen share is shown, instead of the video of the dominant speaker.</span></span>
- <span data-ttu-id="b55d2-407">送信画面の共有:</span><span class="sxs-lookup"><span data-stu-id="b55d2-407">Outgoing screen sharing:</span></span>
    - <span data-ttu-id="b55d2-408">アプリケーションの共有はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="b55d2-408">Application sharing is not supported.</span></span>
- <span data-ttu-id="b55d2-409">制御の受け渡し:</span><span class="sxs-lookup"><span data-stu-id="b55d2-409">Give control and take control:</span></span>
    - <span data-ttu-id="b55d2-410">画面共有またはアプリケーション共有セッション中はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="b55d2-410">Not supported during a screen sharing or application sharing session.</span></span>
    - <span data-ttu-id="b55d2-411">PowerPoint 共有セッション中はサポートされます。</span><span class="sxs-lookup"><span data-stu-id="b55d2-411">Supported during a PowerPoint sharing session.</span></span>
- <span data-ttu-id="b55d2-412">Citrix のみの制限</span><span class="sxs-lookup"><span data-stu-id="b55d2-412">Citrix-only limitations</span></span>
    - <span data-ttu-id="b55d2-413">マルチモニター設定での画面共有の場合、メイン モニターのみ共有されます。</span><span class="sxs-lookup"><span data-stu-id="b55d2-413">When screen sharing in a multi-monitor setup, only the main monitor is shared.</span></span>
    - <span data-ttu-id="b55d2-414">CWA での高 DPI スケーリングはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="b55d2-414">High DPI scaling on CWA is not supported.</span></span>

<span data-ttu-id="b55d2-415">VDI に関連していない Teams の既知の問題については、「 [組織のサポートチーム](Known-issues.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b55d2-415">For Teams known issues that aren't related to VDI, see [Support Teams in your organization](Known-issues.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="b55d2-416">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="b55d2-416">Troubleshooting</span></span>

### <a name="troubleshoot-citrix-components"></a><span data-ttu-id="b55d2-417">Citrix コンポーネントのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="b55d2-417">Troubleshoot Citrix components</span></span>

#### <a name="teams-crashes-or-the-teams-sign-in-screen-is-blank"></a><span data-ttu-id="b55d2-418">チームがクラッシュするか、Teams のサインイン画面が空白になる</span><span class="sxs-lookup"><span data-stu-id="b55d2-418">Teams crashes or the Teams sign in screen is blank</span></span>

<span data-ttu-id="b55d2-419">これは、Citrix VDA バージョン1906と1909の既知の問題です。</span><span class="sxs-lookup"><span data-stu-id="b55d2-419">This is a known issue with Citrix VDA versions 1906 and 1909.</span></span> <span data-ttu-id="b55d2-420">この問題を回避するには、次のレジストリ DWORD 値を追加し、それを 204 (16 進数) に設定します。</span><span class="sxs-lookup"><span data-stu-id="b55d2-420">To work around this issue, add the following registry DWORD value, and set it to 204 (hexadecimal).</span></span>

<span data-ttu-id="b55d2-421">HKEY_LOCAL_MACHINE\SOFTWARE\Citrix\CtxHook\AppInit_Dlls\SfrHook\Teams.exe</span><span class="sxs-lookup"><span data-stu-id="b55d2-421">HKEY_LOCAL_MACHINE\SOFTWARE\Citrix\CtxHook\AppInit_Dlls\SfrHook\Teams.exe</span></span>

<span data-ttu-id="b55d2-422">次に、VDA を再起動します。</span><span class="sxs-lookup"><span data-stu-id="b55d2-422">Then, restart VDA.</span></span> <span data-ttu-id="b55d2-423">詳細については、「Citrix のサポート記事、 [Teams の HDX の最適化に関するトラブルシューティング](https://support.citrix.com/article/CTX253754)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b55d2-423">To learn more, see this Citrix support article, [Troubleshooting HDX optimization for Teams](https://support.citrix.com/article/CTX253754).</span></span>

## <a name="related-topics"></a><span data-ttu-id="b55d2-424">関連項目</span><span class="sxs-lookup"><span data-stu-id="b55d2-424">Related topics</span></span>

- [<span data-ttu-id="b55d2-425">MSI を使用して Microsoft Teams をインストールする</span><span class="sxs-lookup"><span data-stu-id="b55d2-425">Install Microsoft Teams using MSI</span></span>](msi-deployment.md)
- [<span data-ttu-id="b55d2-426">Teams での PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="b55d2-426">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="b55d2-427">Windows 仮想デスクトップで Microsoft Teams を使用する</span><span class="sxs-lookup"><span data-stu-id="b55d2-427">Use Microsoft Teams on Windows Virtual desktop</span></span>](https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd)
