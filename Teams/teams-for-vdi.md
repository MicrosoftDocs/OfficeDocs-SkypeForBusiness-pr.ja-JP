---
title: 仮想デスクトップ インフラストラクチャ用の Teams
author: msdmaguire
ms.author: dmaguire
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
ms.openlocfilehash: a6eba4f1da849a2cf8e355454fd1ba794a3496db
ms.sourcegitcommit: cae94cd5761baafde51aea1137e6d164722eead9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2021
ms.locfileid: "53075390"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a><span data-ttu-id="df3b9-103">仮想デスクトップ インフラストラクチャ用の Teams</span><span class="sxs-lookup"><span data-stu-id="df3b9-103">Teams for Virtualized Desktop Infrastructure</span></span>

<span data-ttu-id="df3b9-104">この記事では、仮想化環境で Microsoft Teams を使用する場合の要件と制限について説明します。</span><span class="sxs-lookup"><span data-stu-id="df3b9-104">This article describes the requirements and limitations for using Microsoft Teams in a virtualized environment.</span></span>

## <a name="what-is-vdi"></a><span data-ttu-id="df3b9-105">VDI とは何ですか ?</span><span class="sxs-lookup"><span data-stu-id="df3b9-105">What is VDI?</span></span>

<span data-ttu-id="df3b9-106">仮想デスクトップ インフラストラクチャ (VDI) は、データセンターの集中サーバーでデスクトップ オペレーティング システムとアプリケーションをホストする仮想化テクノロジです。</span><span class="sxs-lookup"><span data-stu-id="df3b9-106">Virtual Desktop Infrastructure (VDI) is virtualization technology that hosts a desktop operating system and applications on a centralized server in a data center.</span></span> <span data-ttu-id="df3b9-107">これにより、完全に保護され、準拠し一元化されたソースとともに、ユーザーに完全に個人用に設定されたデスクトップ エクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="df3b9-107">This enables a fully personalized desktop experience to users with a fully secured and compliant centralized source.</span></span>

<span data-ttu-id="df3b9-108">仮想化環境の Microsoft Teams はチャットと共同作業をサポートします。</span><span class="sxs-lookup"><span data-stu-id="df3b9-108">Microsoft Teams in a virtualized environment supports chat and collaboration.</span></span> <span data-ttu-id="df3b9-109">また、Citrix、VMware プラットフォームを使用すれば、通話および会議機能もサポートされます。</span><span class="sxs-lookup"><span data-stu-id="df3b9-109">And with the Windows Virtual Desktop, Citrix, and VMware platforms, calling and meeting functionality is also supported.</span></span>

<span data-ttu-id="df3b9-110">仮想化環境の Teams は、複数の構成をサポートします。</span><span class="sxs-lookup"><span data-stu-id="df3b9-110">Teams in a virtualized environment supports multiple configurations.</span></span> <span data-ttu-id="df3b9-111">これらには、VDI、専用、共有、永続、非永続のモードが含まれます。</span><span class="sxs-lookup"><span data-stu-id="df3b9-111">These include VDI, dedicated, shared, persistent, and non-persistent modes.</span></span> <span data-ttu-id="df3b9-112">機能は継続的に開発されており、定期的に追加されます。今後数か月または数年で機能が拡張されます。</span><span class="sxs-lookup"><span data-stu-id="df3b9-112">Features are in continuous development and are added on a regular basis, and functionality will expand in the coming months and years.</span></span>

<span data-ttu-id="df3b9-113">仮想化環境での Teams の使用は、非仮想化環境での Teams の使用とは多少異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="df3b9-113">Using Teams in a virtualized environment might be somewhat different from using Teams in a non-virtualized environment.</span></span> <span data-ttu-id="df3b9-114">たとえば、仮想化環境では一部の高度な機能が利用できない可能性があり、ビデオ解像度が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="df3b9-114">For example, some advanced features might not be available in a virtualized environment, and video resolution might differ.</span></span>

<span data-ttu-id="df3b9-115">最適なユーザー エクスペリエンスを確保するには、この記事のガイダンスに従ってください。</span><span class="sxs-lookup"><span data-stu-id="df3b9-115">To ensure an optimal user experience, follow the guidance in this article.</span></span>

> [!Note]
> <span data-ttu-id="df3b9-116">別のプラットフォームでの Teams VDI に関する詳細は、「[プラットフォームごとの Teams の機能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df3b9-116">For details about Teams VDI on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

## <a name="teams-on-vdi-components"></a><span data-ttu-id="df3b9-117">VDI 上の Teams のコンポーネント</span><span class="sxs-lookup"><span data-stu-id="df3b9-117">Teams on VDI components</span></span>

<span data-ttu-id="df3b9-118">仮想化環境で Teams を使用するには、次のコンポーネントが必要です。</span><span class="sxs-lookup"><span data-stu-id="df3b9-118">Using Teams in a virtualized environment requires the following components.</span></span>

- <span data-ttu-id="df3b9-119">**仮想化ブローカー**: Azure などの仮想化プロバイダーへのリソースおよび接続マネージャー</span><span class="sxs-lookup"><span data-stu-id="df3b9-119">**Virtualization broker**: The resource and connection manager to the virtualization provider, such as Azure</span></span>
- <span data-ttu-id="df3b9-120">**仮想デスクトップ**: Microsoft Teams を実行する仮想マシン (VM) スタック</span><span class="sxs-lookup"><span data-stu-id="df3b9-120">**Virtual desktop**: The Virtual Machine (VM) stack that runs Microsoft Teams</span></span>
- <span data-ttu-id="df3b9-121">**シン クライアント**: ユーザーが物理的にやり取りするエンドポイント</span><span class="sxs-lookup"><span data-stu-id="df3b9-121">**Thin client**: The endpoint that the user physically interfaces with</span></span>
- <span data-ttu-id="df3b9-122">**Teams デスクトップ アプリ**: Teams デスクトップ クライアント アプリ</span><span class="sxs-lookup"><span data-stu-id="df3b9-122">**Teams desktop app**: The Teams desktop client app</span></span>

## <a name="teams-on-vdi-requirements"></a><span data-ttu-id="df3b9-123">VDI 上の Teams の要件</span><span class="sxs-lookup"><span data-stu-id="df3b9-123">Teams on VDI requirements</span></span>

### <a name="virtualization-provider-requirements"></a><span data-ttu-id="df3b9-124">仮想化プロバイダーの要件</span><span class="sxs-lookup"><span data-stu-id="df3b9-124">Virtualization provider requirements</span></span>

<span data-ttu-id="df3b9-125">Teams デスクトップ アプリは、主要な仮想化ソリューション プロバイダーで検証済みです。</span><span class="sxs-lookup"><span data-stu-id="df3b9-125">The Teams desktop app was validated with leading virtualization solution providers.</span></span> <span data-ttu-id="df3b9-126">複数の市場プロバイダーを使用している場合は、仮想化ソリューション プロバイダーに相談して、最小要件が満たされていることを確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="df3b9-126">With multiple market providers, we recommend that you consult your virtualization solution provider to ensure that you meet the minimum requirements.</span></span>
  
<span data-ttu-id="df3b9-127">現在、音声/ビデオ (AV) 最適化を備えた VDI 上の Teams は、Windows Virtual Desktop、Citrix、VMware で認定されています。</span><span class="sxs-lookup"><span data-stu-id="df3b9-127">Currently, Teams on VDI with audio/video (AV) optimization is certified with Windows Virtual Desktop, Citrix, and VMware.</span></span> <span data-ttu-id="df3b9-128">このセクションの情報を確認して、適切に機能するためのすべての要件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="df3b9-128">Review the information in this section to ensure that you meet all requirements for proper functionality.</span></span>

### <a name="platforms-certified-for-teams"></a><span data-ttu-id="df3b9-129">Teams 認定プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="df3b9-129">Platforms certified for Teams</span></span>

<span data-ttu-id="df3b9-130">次のプラットフォームには、Teams 用の仮想デスクトップ インフラストラクチャ ソリューションがあります。</span><span class="sxs-lookup"><span data-stu-id="df3b9-130">The following platforms have virtual desktop infrastructure solutions for Teams.</span></span>

|<span data-ttu-id="df3b9-131">プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="df3b9-131">Platform</span></span>|<span data-ttu-id="df3b9-132">ソリューション</span><span class="sxs-lookup"><span data-stu-id="df3b9-132">Solution</span></span>|
|----|---|
|![Microsoft を表すロゴ](media/microsoft-logo.png)| <span data-ttu-id="df3b9-134"><a href="/azure/virtual-desktop/teams-on-wvd" target="_blank">Windows Virtual Desktop</a></span><span class="sxs-lookup"><span data-stu-id="df3b9-134"><a href="/azure/virtual-desktop/teams-on-wvd" target="_blank">Windows Virtual Desktop</a></span></span> |
|![Citrix を表すロゴ](media/citrix-logo.png)| <span data-ttu-id="df3b9-136"><a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix Virtual Apps and Desktops</a></span><span class="sxs-lookup"><span data-stu-id="df3b9-136"><a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix Virtual Apps and Desktops</a></span></span> |
|![VMware を表すロゴ](media/vmware-logo.png)| <span data-ttu-id="df3b9-138"><a href="https://www.vmware.com/products/horizon.html" target="_blank">VMware Horizon</a></span><span class="sxs-lookup"><span data-stu-id="df3b9-138"><a href="https://www.vmware.com/products/horizon.html" target="_blank">VMware Horizon</a></span></span> |

### <a name="windows-virtual-desktop"></a><span data-ttu-id="df3b9-139">Windows Virtual Desktop</span><span class="sxs-lookup"><span data-stu-id="df3b9-139">Windows Virtual Desktop</span></span>

<span data-ttu-id="df3b9-140">Windows Virtual Desktop は、VDI 上の Teams に AV 最適化を提供します。</span><span class="sxs-lookup"><span data-stu-id="df3b9-140">Windows Virtual Desktop provides AV optimization for Teams on VDI.</span></span> <span data-ttu-id="df3b9-141">詳細、要件およびインストールについては、「[Windows Virtual Desktop で Microsoft Teams を使用する](/azure/virtual-desktop/teams-on-wvd)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df3b9-141">To learn more and requirements and installation, see [Use Teams on Windows Virtual Desktop](/azure/virtual-desktop/teams-on-wvd).</span></span>

### <a name="citrix-virtual-apps-and-desktops-requirements"></a><span data-ttu-id="df3b9-142">Citrix Virtual Apps and Desktops の要件</span><span class="sxs-lookup"><span data-stu-id="df3b9-142">Citrix Virtual Apps and Desktops requirements</span></span>

<span data-ttu-id="df3b9-143">Citrix Virtual Apps and Desktops (以前の XenApp および XenDesktop) は、VDI 上の Teams に AV 最適化を提供します。</span><span class="sxs-lookup"><span data-stu-id="df3b9-143">Citrix Virtual Apps and Desktops (formerly known as XenApp and XenDesktop) provides AV optimization for Teams on VDI.</span></span> <span data-ttu-id="df3b9-144">Citrix Virtual Apps and Desktops を使用すると、VDI 上の Teams はチャットと共同作業に加えて、通話および会議機能をサポートします。</span><span class="sxs-lookup"><span data-stu-id="df3b9-144">With Citrix Virtual Apps and Desktops, Teams on VDI supports calling and meeting functionality in addition to chat and collaboration.</span></span>

<span data-ttu-id="df3b9-145">Citrix Virtual Apps and Desktops の最新バージョンは、[Citrix ダウンロード サイト](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/)からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="df3b9-145">You can download the latest version of Citrix Virtual Apps and Desktops at [the Citrix downloads site](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/).</span></span> <span data-ttu-id="df3b9-146">(最初にサインインする必要があります。) 必要なコンポーネントは、デフォルトで [Citrix Workspace アプリ (CWA)](https://www.citrix.com/downloads/workspace-app/) および Virtual Delivery Agent (VDA) にバンドルされています。</span><span class="sxs-lookup"><span data-stu-id="df3b9-146">(You'll need to sign in first.) The necessary components are bundled into the [Citrix Workspace app (CWA)](https://www.citrix.com/downloads/workspace-app/) and Virtual Delivery Agent (VDA) by default.</span></span> <span data-ttu-id="df3b9-147">CWA や VDA に追加のコンポーネントやプラグインをインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="df3b9-147">You don't need to install any additional components or plugins on CWA or the VDA.</span></span>

<span data-ttu-id="df3b9-148">サーバーおよびクライアントの最新の要件については、[この Citrix Web サイト](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df3b9-148">For the latest server and client requirements, see [this Citrix website](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html).</span></span>

### <a name="vmware-horizon-workspace-and-desktop-requirements"></a><span data-ttu-id="df3b9-149">VMware Horizon Workspace and Desktop の要件</span><span class="sxs-lookup"><span data-stu-id="df3b9-149">VMware Horizon Workspace and Desktop requirements</span></span>

<span data-ttu-id="df3b9-150">VMware Horizon は、ハイブリッド クラウド全体に仮想デスクトップとアプリを安全に配信するためのモダン プラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="df3b9-150">VMware Horizon is a modern platform for secure delivery of virtual desktops and apps across the hybrid cloud.</span></span> <span data-ttu-id="df3b9-151">優れたエンドユーザー エクスペリエンスを提供するために、VMware Horizon は Teams のメディア最適化を提供します。</span><span class="sxs-lookup"><span data-stu-id="df3b9-151">To offer a great end-user experience, VMware Horizon provides media optimization for Teams.</span></span> <span data-ttu-id="df3b9-152">この最適化により、仮想デスクトップやアプリ全体の総体的な生産性が向上し、Teams を使用して通話や会議を行う際のユーザー エクスペリエンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="df3b9-152">This optimization improves overall productivity across virtual desktops and apps, and enhances user experience when calling and meeting using Teams.</span></span>

<span data-ttu-id="df3b9-153">VMware Horizon の最新バージョンは、[VMware ダウンロード](https://my.vmware.com/web/vmware/downloads/#all_products) ページからダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="df3b9-153">You can download the latest version of VMware Horizon from the [VMware Downloads](https://my.vmware.com/web/vmware/downloads/#all_products) page.</span></span> <span data-ttu-id="df3b9-154">既定では、必要なメディア最適化コンポーネントは Horizon Agent と Horizon Client に含まれているため、Teams の最適化機能を使用するために追加のプラグインをインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="df3b9-154">The required media optimization components are part of the Horizon Agent and Horizon Client by default and there's no need to install any additional plug-in to use the optimization feature for Teams.</span></span>

<span data-ttu-id="df3b9-155">Teams のメディア最適化を構成する方法に関する最新の要件と手順を入手するには、[こちらの VMware Web サイト](https://docs.vmware.com/en/VMware-Horizon/2006/horizon-remote-desktop-features/GUID-F68FA7BB-B08F-4EFF-9BB1-1F9FC71F8214.html)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="df3b9-155">To get the latest requirements and instructions on how to configure media optimization for Teams, see [this VMware website](https://docs.vmware.com/en/VMware-Horizon/2006/horizon-remote-desktop-features/GUID-F68FA7BB-B08F-4EFF-9BB1-1F9FC71F8214.html).</span></span>

## <a name="install-or-update-the-teams-desktop-app-on-vdi"></a><span data-ttu-id="df3b9-156">VDI で Teams デスクトップ アプリをインストールまたは更新する</span><span class="sxs-lookup"><span data-stu-id="df3b9-156">Install or update the Teams desktop app on VDI</span></span>

<span data-ttu-id="df3b9-157">MSI パッケージを使用したマシンごとのインストールまたはユーザーごとのインストールを用いて、VDI 用の Teams デスクトップ アプリを展開できます。</span><span class="sxs-lookup"><span data-stu-id="df3b9-157">You can deploy the Teams desktop app for VDI using a per-machine installation or per-user installation using the MSI package.</span></span> <span data-ttu-id="df3b9-158">どのアプローチを使用するかについては、永続的なセットアップを使用するか、または非永続的なセットアップを使用するか、および組織の関連機能のニーズに応じて決定します。</span><span class="sxs-lookup"><span data-stu-id="df3b9-158">Deciding on which approach to use depends on whether you use a persistent or non-persistent setup and the associated functionality needs of your organization.</span></span>

<span data-ttu-id="df3b9-159">専用の永続的なセットアップの場合、どちらのアプローチでも機能します。</span><span class="sxs-lookup"><span data-stu-id="df3b9-159">For a dedicated persistent setup, either approach would work.</span></span> <span data-ttu-id="df3b9-160">ただし、非永続的なセットアップの場合、Teams が効率的に機能するにはマシンごとにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="df3b9-160">However, for a non-persistent setup, Teams requires a per-machine installation in order to work efficiently.</span></span> <span data-ttu-id="df3b9-161">[非永続のセットアップ](#non-persistent-setup)のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="df3b9-161">See the [Non-persistent setup](#non-persistent-setup) section.</span></span>

<span data-ttu-id="df3b9-162">マシンごとのインストールでは、自動更新は無効になっています。</span><span class="sxs-lookup"><span data-stu-id="df3b9-162">With per-machine installation, automatic updates is disabled.</span></span> <span data-ttu-id="df3b9-163">つまり、Teams アプリを更新するには、現在のバージョンをアンインストールして新しいバージョンに更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df3b9-163">This means that to update the Teams app, you must uninstall the current version to update to a newer version.</span></span> <span data-ttu-id="df3b9-164">ユーザーごとのインストールでは、自動更新は有効になっています。</span><span class="sxs-lookup"><span data-stu-id="df3b9-164">With per-user installation, automatic updates is enabled.</span></span> <span data-ttu-id="df3b9-165">ほとんどの VDI の展開について、マシンごとのインストールを使用して Teams を展開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="df3b9-165">For most VDI deployments, we recommend you deploy Teams using per-machine installation.</span></span>

<span data-ttu-id="df3b9-166">最新の Teams バージョンに更新するには、アンインストール手順から始めて、次に最新の Teams バージョンを展開します。</span><span class="sxs-lookup"><span data-stu-id="df3b9-166">To update to the latest Teams version, start with the uninstall procedure followed by latest Teams version deployment.</span></span>

<span data-ttu-id="df3b9-167">VDI 環境での Teams AV の最適化が適切に機能するには、シン クライアント エンドポイントがインターネットにアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="df3b9-167">For Teams AV optimization in VDI environments to work properly, the thin client endpoint must have access to the internet.</span></span> <span data-ttu-id="df3b9-168">シン クライアント エンドポイントでインターネット アクセスが利用できない場合、最適化のスタートアップは成功しません。</span><span class="sxs-lookup"><span data-stu-id="df3b9-168">If internet access isn't available at the thin client endpoint, optimization startup won't be successful.</span></span> <span data-ttu-id="df3b9-169">これは、ユーザーが最適化されていないメディア状態にあることを意味します。</span><span class="sxs-lookup"><span data-stu-id="df3b9-169">This means that the user is in a non-optimized media state.</span></span>

#### <a name="dedicated-persistent-setup"></a><span data-ttu-id="df3b9-170">専用の永続的なセットアップ</span><span class="sxs-lookup"><span data-stu-id="df3b9-170">Dedicated persistent setup</span></span>

<span data-ttu-id="df3b9-171">専用の永続的なセットアップでは、ユーザーのローカル オペレーティング システムの変更は、ユーザーがログオフした後も保持されます。</span><span class="sxs-lookup"><span data-stu-id="df3b9-171">In a dedicated persistent setup, users' local operating system changes are retained after users log off.</span></span> <span data-ttu-id="df3b9-172">永続的なセットアップの場合、Teams はユーザーごとのインストールとマシンごとのインストールの両方をサポートします。</span><span class="sxs-lookup"><span data-stu-id="df3b9-172">For persistent setup, Teams supports both per-user and per-machine installation.</span></span>

<span data-ttu-id="df3b9-173">推奨される最低限の VM 構成は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="df3b9-173">The following is the recommended minimum VM configuration.</span></span>

|<span data-ttu-id="df3b9-174">パラメーター</span><span class="sxs-lookup"><span data-stu-id="df3b9-174">Parameter</span></span>  |<span data-ttu-id="df3b9-175">ワークステーションのオペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="df3b9-175">Workstation operating system</span></span>  |<span data-ttu-id="df3b9-176">サーバー オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="df3b9-176">Server operating system</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="df3b9-177">vCPU</span><span class="sxs-lookup"><span data-stu-id="df3b9-177">vCPU</span></span>   |    <span data-ttu-id="df3b9-178">2 コア</span><span class="sxs-lookup"><span data-stu-id="df3b9-178">2 cores</span></span>     |  <span data-ttu-id="df3b9-179">4、6、または 8。</span><span class="sxs-lookup"><span data-stu-id="df3b9-179">4,6, or 8</span></span><br><span data-ttu-id="df3b9-180">基礎となる Non-Uniform Memory Access (NUMA) 構成を理解し、それに応じて VM を構成することが重要です。</span><span class="sxs-lookup"><span data-stu-id="df3b9-180">It's important to understand the underlying non-uniform memory access (NUMA) configuration and configure your VMs accordingly.</span></span>     |
|<span data-ttu-id="df3b9-181">RAM</span><span class="sxs-lookup"><span data-stu-id="df3b9-181">RAM</span></span>     |   <span data-ttu-id="df3b9-182">4 GB</span><span class="sxs-lookup"><span data-stu-id="df3b9-182">4 GB</span></span>      | <span data-ttu-id="df3b9-183">ユーザー 1 人あたり 512 から 1024 MB</span><span class="sxs-lookup"><span data-stu-id="df3b9-183">512 to 1024 MB per user</span></span>        |
|<span data-ttu-id="df3b9-184">ストレージ</span><span class="sxs-lookup"><span data-stu-id="df3b9-184">Storage</span></span>    | <span data-ttu-id="df3b9-185">8 GB</span><span class="sxs-lookup"><span data-stu-id="df3b9-185">8 GB</span></span>        | <span data-ttu-id="df3b9-186">40 から 60 GB</span><span class="sxs-lookup"><span data-stu-id="df3b9-186">40 to 60 GB</span></span>        |

#### <a name="non-persistent-setup"></a><span data-ttu-id="df3b9-187">非永続的なセットアップ</span><span class="sxs-lookup"><span data-stu-id="df3b9-187">Non-persistent setup</span></span>

<span data-ttu-id="df3b9-188">非永続的なセットアップでは、ユーザーのローカル オペレーティング システムの変更は、ユーザーがログオフした後は保持されません。</span><span class="sxs-lookup"><span data-stu-id="df3b9-188">In a non-persistent setup, users' local operating system changes are not retained after users log off.</span></span> <span data-ttu-id="df3b9-189">このようなセットアップは、一般的に共有マルチユーザー セッションです。</span><span class="sxs-lookup"><span data-stu-id="df3b9-189">Such setups are commonly shared multi-user sessions.</span></span> <span data-ttu-id="df3b9-190">VM 構成は、ユーザー数と使用可能な物理ボックス リソースによって異なります。</span><span class="sxs-lookup"><span data-stu-id="df3b9-190">VM configuration varies based on the number of users and available physical box resources.</span></span>

<span data-ttu-id="df3b9-191">非永続的なセットアップの場合、Teams デスクトップ アプリは、ゴールデン イメージに対してマシンごとにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="df3b9-191">For a non-persistent setup, the Teams desktop app must be installed per-machine to the golden image.</span></span> <span data-ttu-id="df3b9-192">(詳細に関しては、[VDI での Teams デスクトップ アプリのインストールまたは更新](#install-or-update-the-teams-desktop-app-on-vdi)セクションを参照してください) これにより、Teams アプリがユーザー セッション中でも効率的に起動できるようになります。</span><span class="sxs-lookup"><span data-stu-id="df3b9-192">(To learn more, see the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.) This ensures an efficient launch of the Teams app during a user session.</span></span>

<span data-ttu-id="df3b9-193">非永続的なセットアップで Teams を使用するには、効率的なTeamsランタイムデータ同期のために、プロファイル キャッシュ マネージャーも必要です。</span><span class="sxs-lookup"><span data-stu-id="df3b9-193">Using Teams in a non-persistent setup also requires a profile-caching manager, for efficient Teams runtime data synchronization.</span></span> <span data-ttu-id="df3b9-194">効率的なデータ同期により、適切なユーザー固有の情報 (ユーザーのデータ、プロファイル、設定など) がユーザーのセッション中にキャッシュされます。</span><span class="sxs-lookup"><span data-stu-id="df3b9-194">Efficient data synchronization ensures that the appropriate user-specific information (such as a user's data, profile, or settings) is cached during the user's session.</span></span> <span data-ttu-id="df3b9-195">以下の 2 つのフォルダーのデータが同期されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="df3b9-195">Make sure data in these two folders are synched:</span></span><br>
- <span data-ttu-id="df3b9-196">C:\Users\username\AppData\Local\Microsoft\IdentityCache (%localAppdata%\Microsoft\IdentityCache)</span><span class="sxs-lookup"><span data-stu-id="df3b9-196">C:\Users\username\AppData\Local\Microsoft\IdentityCache (%localAppdata%\Microsoft\IdentityCache)</span></span>
- <span data-ttu-id="df3b9-197">C:\Users\username\AppData\Roaming\Microsoft\Teams (%appdata%\Microsoft\Teams)</span><span class="sxs-lookup"><span data-stu-id="df3b9-197">C:\Users\username\AppData\Roaming\Microsoft\Teams (%appdata%\Microsoft\Teams)</span></span>

> [!NOTE]
> <span data-ttu-id="df3b9-198">Teams アプリがアプリケーションの実行に必要なランタイム データとファイルを確実に取得するには、ローミング フォルダー (またはフォルダー リダイレクトを使用している場合はキャッシュ マネージャー) が必要です。</span><span class="sxs-lookup"><span data-stu-id="df3b9-198">A roaming folder (or, if you are using folder redirection, a caching manager) is required to ensure that the Teams app has the runtime data and files required to run the application.</span></span> <span data-ttu-id="df3b9-199">これは、ネットワーク遅延の問題やネットワークの不具合を軽減するために必要です。それを行わない場合、データやファイルが利用できないことにより、アプリケーション エラーが発生し、動作が遅くなります。</span><span class="sxs-lookup"><span data-stu-id="df3b9-199">This is necessary to mitigate network latency issues or network glitches, which would otherwise cause application errors and a slow experience due to unavailable data and files.</span></span>

<span data-ttu-id="df3b9-200">さまざまなキャッシュ マネージャー ソリューションが利用可能です。</span><span class="sxs-lookup"><span data-stu-id="df3b9-200">There are a variety of caching manager solutions available.</span></span> <span data-ttu-id="df3b9-201">たとえば、[FSLogix](/fslogix/overview) があります。</span><span class="sxs-lookup"><span data-stu-id="df3b9-201">For example, [FSLogix](/fslogix/overview).</span></span> <span data-ttu-id="df3b9-202">具体的な構成手順については、キャッシュ マネージャー プロバイダーに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="df3b9-202">Consult your caching manager provider for specific configuration instructions.</span></span>

##### <a name="teams-cached-content-exclusion-list-for-non-persistent-setup"></a><span data-ttu-id="df3b9-203">Teams は、非永続的なセットアップ用のコンテンツ除外リストをキャッシュしました</span><span class="sxs-lookup"><span data-stu-id="df3b9-203">Teams cached content exclusion list for non-persistent setup</span></span>

<span data-ttu-id="df3b9-204">Teams キャッシュ フォルダー %appdata%/Microsoft/Teams から以下を除外します。</span><span class="sxs-lookup"><span data-stu-id="df3b9-204">Exclude the following from the Teams caching folder, %appdata%/Microsoft/Teams.</span></span> <span data-ttu-id="df3b9-205">これらのアイテムを除外すると、ユーザーのキャッシュ サイズが小さくなり、非永続的なセットアップがさらに最適化されます。</span><span class="sxs-lookup"><span data-stu-id="df3b9-205">Excluding these items helps reduce the user caching size to further optimize your non-persistent setup.</span></span>

- <span data-ttu-id="df3b9-206">.txt ファイル</span><span class="sxs-lookup"><span data-stu-id="df3b9-206">.txt files</span></span>
- <span data-ttu-id="df3b9-207">メディアスタック フォルダー</span><span class="sxs-lookup"><span data-stu-id="df3b9-207">Media-stack folder</span></span>
- <span data-ttu-id="df3b9-208">meeting-addin\Cache (%appdata%\Microsoft\Teams\meeting-addin\Cache)</span><span class="sxs-lookup"><span data-stu-id="df3b9-208">meeting-addin\Cache (%appdata%\Microsoft\Teams\meeting-addin\Cache)</span></span>

### <a name="microsoft-365-apps-for-enterprise-considerations"></a><span data-ttu-id="df3b9-209">Microsoft 365 Apps for enterprise に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="df3b9-209">Microsoft 365 Apps for enterprise considerations</span></span>

<span data-ttu-id="df3b9-210">VDI で Microsoft 365 Apps for enterprise を使用して Teams を展開する場合は、次のことを考慮してください。</span><span class="sxs-lookup"><span data-stu-id="df3b9-210">Consider the following when you deploy Teams with Microsoft 365 Apps for enterprise on VDI.</span></span>

#### <a name="new-deployments-of-teams-through-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="df3b9-211">Microsoft 365 Apps for enterprise を使用した Teams の新しい展開</span><span class="sxs-lookup"><span data-stu-id="df3b9-211">New deployments of Teams through Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="df3b9-212">Microsoft 365 Apps for enterprise を介して Teams を展開する前に、まず、マシンごとのインストールを使用して展開されている既存の Teams アプリをアンインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="df3b9-212">Before you deploy Teams through Microsoft 365 Apps for enterprise, you must first uninstall any pre-existing Teams apps if they were deployed using per-machine installation.</span></span>

<span data-ttu-id="df3b9-213">Microsoft 365 Apps for enterprise を介した Teams は、ユーザーごとにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="df3b9-213">Teams through Microsoft 365 Apps for enterprise is installed per-user.</span></span> <span data-ttu-id="df3b9-214">詳細については、「[VDI で Teams デスクトップ アプリをインストールまたは更新する](#install-or-update-the-teams-desktop-app-on-vdi)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="df3b9-214">To learn more, see the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.</span></span>

#### <a name="teams-deployments-through-microsoft-365-apps-for-enterprise-updates"></a><span data-ttu-id="df3b9-215">Microsoft 365 Apps for enterprise の更新プログラムを使用した Teams の展開</span><span class="sxs-lookup"><span data-stu-id="df3b9-215">Teams deployments through Microsoft 365 Apps for enterprise updates</span></span>

<span data-ttu-id="df3b9-216">Teams は、Microsoft 365 Apps for enterprise の既存のインストールにも追加される予定です。</span><span class="sxs-lookup"><span data-stu-id="df3b9-216">Teams is also being added to existing installations of Microsoft 365 Apps for enterprise.</span></span> <span data-ttu-id="df3b9-217">Microsoft 365 Apps for enterprise では、Teams はユーザーごとにのみインストールされるため、「[VDI で Teams デスクトップ アプリをインストールまたは更新する](#install-or-update-the-teams-desktop-app-on-vdi)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="df3b9-217">Since Microsoft 365 Apps for enterprise installs Teams per-user only, see the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.</span></span>

#### <a name="using-teams-with-per-machine-installation-and-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="df3b9-218">マシンごとのインストールと Microsoft 365 Apps for enterprise での Teams の使用</span><span class="sxs-lookup"><span data-stu-id="df3b9-218">Using Teams with per-machine installation and Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="df3b9-219">Microsoft 365 Apps for enterprise は、Teams のマシンごとのインストールをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="df3b9-219">Microsoft 365 Apps for enterprise doesn't support per-machine installations of Teams.</span></span> <span data-ttu-id="df3b9-220">マシンごとのインストールを使用するには、Microsoft 365 Apps for enterprise から Teams を除外する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df3b9-220">To use per-machine installation, you must exclude Teams from Microsoft 365 Apps for enterprise.</span></span> <span data-ttu-id="df3b9-221">「[Teams デスクトップ アプリを VM に展開する](#deploy-the-teams-desktop-app-to-the-vm)」と「[Microsoft 365 Apps for enterprise を介した Teams の展開を除外する方法](#how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="df3b9-221">See the [Deploy the Teams desktop app to the VM](#deploy-the-teams-desktop-app-to-the-vm) and [How to exclude Teams deployment through Microsoft 365 Apps for enterprise](#how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise) sections.</span></span>

#### <a name="how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="df3b9-222">Microsoft 365 Apps for enterprise を介した Teams の展開を除外する方法</span><span class="sxs-lookup"><span data-stu-id="df3b9-222">How to exclude Teams deployment through Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="df3b9-223">Teams と Microsoft 365 Apps for enterprise の詳細については、「[Microsoft 365 Apps for enterprise の新規インストールから Teams を除外する方法](/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-office-365-proplus)」と「[グループ ポリシーを使用して Teams のインストールを制御する](/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df3b9-223">To learn more about Teams and Microsoft 365 Apps for enterprise, see [How to exclude Teams from new installations of Microsoft 365 Apps for enterprise](/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-office-365-proplus) and [Use Group Policy to control the installation of Teams](/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams).</span></span>

### <a name="deploy-the-teams-desktop-app-to-the-vm"></a><span data-ttu-id="df3b9-224">Teams デスクトップ アプリを VM に展開する</span><span class="sxs-lookup"><span data-stu-id="df3b9-224">Deploy the Teams desktop app to the VM</span></span>

1. <span data-ttu-id="df3b9-225">次のリンクのいずれかを使用して、VDI VM オペレーティング システムに一致する Teams MSI パッケージをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="df3b9-225">Download the Teams MSI package that matches your VDI VM operating system using one of the following links:</span></span>

    - [<span data-ttu-id="df3b9-226">32 ビット版</span><span class="sxs-lookup"><span data-stu-id="df3b9-226">32-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)
    - [<span data-ttu-id="df3b9-227">64 ビット版</span><span class="sxs-lookup"><span data-stu-id="df3b9-227">64-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)

    > [!NOTE]
    > <span data-ttu-id="df3b9-228">政府機関向けクラウドの場合、MSI ファイルのダウンロード リンクについては、「[Microsoft Endpoint Configuration Manager を使用して Microsoft Teams をインストールする](msi-deployment.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df3b9-228">For government clouds, see [Install Microsoft Teams using Microsoft Endpoint Configuration Manager](msi-deployment.md) for the download links to the MSI files.</span></span>

    <span data-ttu-id="df3b9-229">必要な Teams デスクトップ アプリの最小バージョンは、バージョン 1.3.00.4461 です。</span><span class="sxs-lookup"><span data-stu-id="df3b9-229">The minimum version of the Teams desktop app that's required is version 1.3.00.4461.</span></span> <span data-ttu-id="df3b9-230">(PSTN ホールドは以前のバージョンではサポートされていません。)</span><span class="sxs-lookup"><span data-stu-id="df3b9-230">(PSTN hold isn't supported in earlier versions.)</span></span>

2. <span data-ttu-id="df3b9-231">次のいずれかのコマンドを実行して、MSI を VDI VM にインストールします。</span><span class="sxs-lookup"><span data-stu-id="df3b9-231">Install the MSI to the VDI VM by running one of the following commands:</span></span>

    - <span data-ttu-id="df3b9-232">ユーザーごとのインストール (既定)</span><span class="sxs-lookup"><span data-stu-id="df3b9-232">Per-user installation (default)</span></span>
  
        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSERS=1
        ```

        <span data-ttu-id="df3b9-233">このプロセスは既定のインストールで、Teams は %AppData% ユーザー フォルダーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="df3b9-233">This process is the default installation, which installs Teams to the %AppData% user folder.</span></span> <span data-ttu-id="df3b9-234">この時点で、ゴールデン イメージのセットアップは完了です。</span><span class="sxs-lookup"><span data-stu-id="df3b9-234">At this point, the golden image setup is complete.</span></span> <span data-ttu-id="df3b9-235">非永続的なセットアップでのユーザーごとのインストールでは、Teams は適切に動作しません。</span><span class="sxs-lookup"><span data-stu-id="df3b9-235">Teams won't work properly with per-user installation on a non-persistent setup.</span></span>

    - <span data-ttu-id="df3b9-236">マシンごとのインストール</span><span class="sxs-lookup"><span data-stu-id="df3b9-236">Per-machine installation</span></span>

        ```console
        reg add "HKLM\SOFTWARE\Microsoft\Teams" /v IsWVDEnvironment /t REG_DWORD /d 1 /f
        ```
        <span data-ttu-id="df3b9-237">このプロセスにより、必要なレジストリ キーがマシンに追加され、Teams VDI インスタンスがマシンに表示されます。</span><span class="sxs-lookup"><span data-stu-id="df3b9-237">This process adds a required registry key to the machine that lets the Teams installer know it is a VDI instance.</span></span>  <span data-ttu-id="df3b9-238">インストールしない場合、インストーラーは次のエラーを返します。"インストールに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="df3b9-238">Without it, the installer will error out, stating: "Installation has failed.</span></span>  <span data-ttu-id="df3b9-239">VDI 環境が検出されない場合は、すべてのユーザーにインストールできません。"</span><span class="sxs-lookup"><span data-stu-id="df3b9-239">Cannot install for all users when a VDI environment is not detected."</span></span>

        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1 ALLUSERS=1
        ```

        <span data-ttu-id="df3b9-240">このプロセスでは、Teams は 64 ビット オペレーティング システムの Program Files (x86) フォルダー、および 32 ビット オペレーティング システム の Program Files フォルダーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="df3b9-240">This process installs Teams to the Program Files (x86) folder on a 64-bit operating system and to the Program Files folder on a 32-bit operating system.</span></span> <span data-ttu-id="df3b9-241">この時点で、ゴールデン イメージのセットアップは完了です。</span><span class="sxs-lookup"><span data-stu-id="df3b9-241">At this point, the golden image setup is complete.</span></span> <span data-ttu-id="df3b9-242">非永続的なセットアップについては、マシンごとに Teams をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="df3b9-242">Installing Teams per-machine is required for non-persistent setups.</span></span>

        <span data-ttu-id="df3b9-243">次の対話型ログオン セッションは、Teams を開始し、資格情報を要求します。</span><span class="sxs-lookup"><span data-stu-id="df3b9-243">The next interactive logon session starts Teams and asks for credentials.</span></span>

        > [!NOTE]
        > <span data-ttu-id="df3b9-244">これらの例でも **ALLUSERS=1** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="df3b9-244">These examples also use the **ALLUSERS=1** parameter.</span></span> <span data-ttu-id="df3b9-245">このパラメーターを設定すると、コンピューターのすべてのユーザーの [コントロール パネル] の [プログラムと機能] および [Windows の設定] の [アプリと機能] に Teams Machine-Wide Installer が表示されます。</span><span class="sxs-lookup"><span data-stu-id="df3b9-245">When you set this parameter, Teams Machine-Wide Installer appears in Programs and Features in Control Panel and in Apps & features in Windows Settings for all users of the computer.</span></span> <span data-ttu-id="df3b9-246">管理者の資格情報を持っている場合は、すべてのユーザーが Teams をアンインストールできます。</span><span class="sxs-lookup"><span data-stu-id="df3b9-246">All users can then uninstall Teams if they have admin credentials.</span></span>
        <span data-ttu-id="df3b9-247">**ALLUSERS=1** と **ALLUSER=1** の違いを理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="df3b9-247">It's important to understand the difference between **ALLUSERS=1** and **ALLUSER=1**.</span></span> <span data-ttu-id="df3b9-248">**ALLUSERS=1** パラメーターは、非 VDI 環境および VDI 環境の両方で使用できますが、**ALLUSER=1** パラメーターは、VDI 環境でのみマシンごとのインストールを指定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="df3b9-248">The **ALLUSERS=1** parameter can be used in non-VDI and VDI environments, while the **ALLUSER=1** parameter is used only in VDI environments to specify a per-machine installation.</span></span>

3. <span data-ttu-id="df3b9-249">VDI VM から MSI をアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="df3b9-249">Uninstall the MSI from the VDI VM.</span></span> <span data-ttu-id="df3b9-250">Teams をアンインストールする方法は 2 つあります。</span><span class="sxs-lookup"><span data-stu-id="df3b9-250">There are two ways to uninstall Teams.</span></span>

    - <span data-ttu-id="df3b9-251">PowerShell スクリプト: [この PowerShell スクリプト](scripts/powershell-script-deployment-cleanup.md)を使用して、Teams をアンインストールしてユーザーの Teams フォルダーを削除できます。</span><span class="sxs-lookup"><span data-stu-id="df3b9-251">PowerShell script: You can use [this PowerShell script](scripts/powershell-script-deployment-cleanup.md) to uninstall Teams and remove the Teams folder for a user.</span></span> <span data-ttu-id="df3b9-252">Teams がコンピューターにインストールされているユーザー プロファイルごとにスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="df3b9-252">Run the script for each user profile in which Teams was installed on the computer.</span></span>
    - <span data-ttu-id="df3b9-253">コマンド ライン: 次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="df3b9-253">Command line: Run the following command.</span></span>
  
      ```console
      msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>
      ```

      <span data-ttu-id="df3b9-254">このプロセスでは、オペレーティング システムの環境に応じて、Program Files (x86) フォルダーまたは Program Files フォルダーから Teams がアンインストールされます。</span><span class="sxs-lookup"><span data-stu-id="df3b9-254">This process uninstalls Teams from the Program Files (x86) folder or Program Files folder, depending on the operating system environment.</span></span>

## <a name="teams-on-vdi-performance-considerations"></a><span data-ttu-id="df3b9-255">VDI 上の Teams のパフォーマンスに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="df3b9-255">Teams on VDI performance considerations</span></span>

<span data-ttu-id="df3b9-256">さまざまな仮想化セットアップ構成があり、それぞれ最適化の焦点が異なります。</span><span class="sxs-lookup"><span data-stu-id="df3b9-256">There are a variety of virtualized setup configurations, each with a different focus for optimization.</span></span> <span data-ttu-id="df3b9-257">たとえば、ある構成ではユーザー密度に焦点が当てられます。</span><span class="sxs-lookup"><span data-stu-id="df3b9-257">For example, a configuration might focus on user density.</span></span> <span data-ttu-id="df3b9-258">計画するときは、組織のワークロードのニーズに基づいてセットアップを最適化するために、以下を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="df3b9-258">When planning, consider the following to help optimize your setup based on your organization's workload needs.</span></span>

- <span data-ttu-id="df3b9-259">最小要件: 一部のワークロードでは、最小要件を超えるリソースを使用したセットアップが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="df3b9-259">Minimum requirement: Some workloads might require a setup using resources that are above the minimum requirements.</span></span> <span data-ttu-id="df3b9-260">たとえば、より多くのコンピューティング リソースを必要とするアプリケーションを使用する開発者向けのワークロード。</span><span class="sxs-lookup"><span data-stu-id="df3b9-260">For example, workloads for developers who use applications that demand more computing resources.</span></span>
- <span data-ttu-id="df3b9-261">依存関係: インフラストラクチャ、ワークロード、および Teams デスクトップ アプリ以外の環境に関するその他の考慮事項への依存関係が含まれます。</span><span class="sxs-lookup"><span data-stu-id="df3b9-261">Dependencies: These include dependencies on infrastructure, workload, and other environmental considerations outside the Teams desktop app.</span></span>
- <span data-ttu-id="df3b9-262">VDI の無効な機能: Teams は、VDI の GPU 負荷集中型機能を無効にします。これは、一時的な CPU 使用率の改善に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="df3b9-262">Disabled features on VDI: Teams disables GPU-intensive features for VDI, which can help improve transient CPU utilization.</span></span> <span data-ttu-id="df3b9-263">以下の機能は無効です。</span><span class="sxs-lookup"><span data-stu-id="df3b9-263">The following features are disabled:</span></span>
    - <span data-ttu-id="df3b9-264">Teams CSS アニメーション</span><span class="sxs-lookup"><span data-stu-id="df3b9-264">Teams CSS animation</span></span>
    - <span data-ttu-id="df3b9-265">Giphy の自動起動</span><span class="sxs-lookup"><span data-stu-id="df3b9-265">Giphy auto-start</span></span>

## <a name="teams-on-vdi-with-calling-and-meetings"></a><span data-ttu-id="df3b9-266">通話と会議を含む VDI 上の Teams</span><span class="sxs-lookup"><span data-stu-id="df3b9-266">Teams on VDI with calling and meetings</span></span>

<span data-ttu-id="df3b9-267">チャットと共同作業に加えて、通話と会議のサポートを備えた VDI 上の Teams は、サポートされている仮想化プロバイダーのプラットフォームで利用できます。</span><span class="sxs-lookup"><span data-stu-id="df3b9-267">In addition to chat and collaboration, Teams on VDI with calling and meetings is available with supported virtualization provider platforms.</span></span> <span data-ttu-id="df3b9-268">サポートされる機能は、WebRTC メディア スタックおよび仮想化プロバイダーの実装に基づいています。</span><span class="sxs-lookup"><span data-stu-id="df3b9-268">Supported features are based on the WebRTC media stack and virtualization provider implementation.</span></span> <span data-ttu-id="df3b9-269">次の図では、このアーキテクチャの概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="df3b9-269">The following diagram provides an overview of the architecture.</span></span>

![VDI アーキテクチャ上の Teams を示す図](media/teams-on-vdi-architecture.png)

> [!IMPORTANT]
> <span data-ttu-id="df3b9-271">現在、VDI で AV 最適化なしで Teams を実行していて、最適化でまだサポートされていない機能 (アプリ共有時の制御の受け渡しなど) を使用している場合、仮想化プロバイダーのポリシーを設定して Teams のリダイレクトを無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="df3b9-271">If you currently run Teams without AV optimization in VDI and you use features that are not supported yet for optimization (such as Give and take control when app sharing), you have to set virtualization provider policies to turn off Teams redirection.</span></span> <span data-ttu-id="df3b9-272">これは、Teams のメディア セッションが最適化されないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="df3b9-272">This means that Teams media sessions won't be optimized.</span></span> <span data-ttu-id="df3b9-273">Teams のリダイレクトを無効にするようにポリシーを設定する方法の手順については、仮想化プロバイダーにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="df3b9-273">For steps on how to set policies to turn off Teams redirection, contact your virtualization provider.</span></span>

### <a name="network-requirements"></a><span data-ttu-id="df3b9-274">ネットワーク要件</span><span class="sxs-lookup"><span data-stu-id="df3b9-274">Network requirements</span></span>

<span data-ttu-id="df3b9-275">環境を評価して、クラウド全体での音声とビデオの展開に影響を与える可能性のあるリスクおよび要件を特定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="df3b9-275">We recommend that you evaluate your environment to identify any risks and requirements that can influence your overall cloud voice and video deployment.</span></span> <span data-ttu-id="df3b9-276">[Skype for Business ネットワーク評価ツール](https://www.microsoft.com/download/details.aspx?id=53885)を使用して、ネットワークが Teams に対応しているかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="df3b9-276">Use the [Skype for Business Network Assessment Tool](https://www.microsoft.com/download/details.aspx?id=53885) to test whether your network is ready for Teams.</span></span>

<span data-ttu-id="df3b9-277">Teams 用にネットワークを準備する方法の詳細については、「[Teams 用に組織のネットワークを準備する](prepare-network.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df3b9-277">To learn more about how to prepare your network for Teams, see [Prepare your organization's network for Teams](prepare-network.md).</span></span>

### <a name="migrate-from-skype-for-business-on-vdi-to-teams-on-vdi"></a><span data-ttu-id="df3b9-278">VDI上の Skype for Business から VDI 上の Teams に移行する</span><span class="sxs-lookup"><span data-stu-id="df3b9-278">Migrate from Skype for Business on VDI to Teams on VDI</span></span>

<span data-ttu-id="df3b9-279">VDI 上の Skype for Business から VDI 上の Teams に移行する場合、2 つのアプリケーションの違いに加えて、VDI も実装されている場合にはいくつかの違いがあります。</span><span class="sxs-lookup"><span data-stu-id="df3b9-279">If you're migrating from Skype for Business on VDI to Teams on VDI, besides the differences between the two applications, there are some differences when VDI is also implemented.</span></span> <span data-ttu-id="df3b9-280">Skype for Business VDI ではサポートされていて、Teams VDI では現在サポートされていない機能は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="df3b9-280">Some capabilities that aren't currently supported in Teams VDI that are in Skype for Business VDI are as follows:</span></span>

- <span data-ttu-id="df3b9-281">VDI の一部の AV 機能を無効にするプラットフォームごとのポリシー</span><span class="sxs-lookup"><span data-stu-id="df3b9-281">Per-platform policy to disable some AV features in VDI</span></span>
- <span data-ttu-id="df3b9-282">アプリ共有時の制御の受け渡し</span><span class="sxs-lookup"><span data-stu-id="df3b9-282">Give and take control when app sharing</span></span>
- <span data-ttu-id="df3b9-283">音声なしのチャットからの画面共有</span><span class="sxs-lookup"><span data-stu-id="df3b9-283">Screen share from chat without audio</span></span>
- <span data-ttu-id="df3b9-284">ビデオと画面の共有の同時送受信</span><span class="sxs-lookup"><span data-stu-id="df3b9-284">Simultaneous video and screen sharing send and receive</span></span>

### <a name="teams-on-chrome-browser-versus-teams-desktop-app-for-vdi"></a><span data-ttu-id="df3b9-285">Chrome ブラウザーの Teams と VDI の Teams デスクトップ アプリの比較</span><span class="sxs-lookup"><span data-stu-id="df3b9-285">Teams on Chrome browser versus Teams desktop app for VDI</span></span>

<span data-ttu-id="df3b9-286">Chrome ブラウザーの Teams は、AV 最適化を備えた VDI 用の Teams デスクトップ アプリに代わるものを提供しません。</span><span class="sxs-lookup"><span data-stu-id="df3b9-286">Teams on Chrome browser doesn't provide a replacement for the Teams desktop app for VDI with AV optimization.</span></span> <span data-ttu-id="df3b9-287">チャットと共同作業のエクスペリエンスは期待どおりに機能します。</span><span class="sxs-lookup"><span data-stu-id="df3b9-287">The chat and collaboration experience works as expected.</span></span> <span data-ttu-id="df3b9-288">メディアが必要な場合、一部の機能が Chrome ブラウザーでのユーザーの期待に合致しない場合があります。</span><span class="sxs-lookup"><span data-stu-id="df3b9-288">When media is needed, there are some experiences that might not meet user expectations on the Chrome browser:</span></span>

- <span data-ttu-id="df3b9-289">音声とビデオのストリーミング エクスペリエンスが最適にならない場合があります。</span><span class="sxs-lookup"><span data-stu-id="df3b9-289">The audio and video streaming experience might not be optimal.</span></span> <span data-ttu-id="df3b9-290">遅延や品質低下が発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="df3b9-290">Users might experiences delays or reduced quality.</span></span>
- <span data-ttu-id="df3b9-291">デバイス設定は、ブラウザーの設定では使用できません。</span><span class="sxs-lookup"><span data-stu-id="df3b9-291">Device settings aren't available in browser settings.</span></span>
- <span data-ttu-id="df3b9-292">デバイス管理はブラウザーを介して処理され、ブラウザー サイト設定で複数の設定が必要です。</span><span class="sxs-lookup"><span data-stu-id="df3b9-292">Device management is handled through the browser and requires multiple settings in browser site settings.</span></span>
- <span data-ttu-id="df3b9-293">デバイス設定は、Windows デバイス管理でも設定する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="df3b9-293">Device settings might also need to be set in Windows device management.</span></span>

## <a name="teams-on-vdi-with-chat-and-collaboration"></a><span data-ttu-id="df3b9-294">チャットと共同作業を備えた VDI 上の Teams</span><span class="sxs-lookup"><span data-stu-id="df3b9-294">Teams on VDI with chat and collaboration</span></span>

<span data-ttu-id="df3b9-295">組織で Teams のチャットおよび共同作業機能のみを使用する場合は、ユーザーレベル ポリシーを設定して、Teams の通話および会議機能を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="df3b9-295">If your organization wants to only use chat and collaboration features in Teams, you can set user-level policies to turn off calling and meeting functionality in Teams.</span></span> 

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a><span data-ttu-id="df3b9-296">通話および会議機能を無効にするポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="df3b9-296">Set policies to turn off calling and meeting functionality</span></span>

<span data-ttu-id="df3b9-297">Microsoft Teams 管理センターまたは PowerShell を使用してポリシーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="df3b9-297">You can set policies by using the Microsoft Teams admin center or PowerShell.</span></span> <span data-ttu-id="df3b9-298">ポリシーの変更が反映されるまでに時間がかかる場合があります (数時間)。</span><span class="sxs-lookup"><span data-stu-id="df3b9-298">It might take some time (a few hours) for the policy changes to propagate.</span></span> <span data-ttu-id="df3b9-299">指定したアカウントの変更がすぐに表示されない場合は、数時間後にもう一度お試しください。</span><span class="sxs-lookup"><span data-stu-id="df3b9-299">If you don't see changes for a given account immediately, try again in a few hours.</span></span>

<span data-ttu-id="df3b9-300">[**通話ポリシー**](teams-calling-policy.md): Teams には、すべての通話機能が無効になっている組み込みの DisallowCalling 通話ポリシーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="df3b9-300">[**Calling polices**](teams-calling-policy.md): Teams includes the built-in DisallowCalling calling policy, in which all calling features are turned off.</span></span> <span data-ttu-id="df3b9-301">DisallowCalling ポリシーを、仮想化環境で Teams を使用する組織内のすべてのユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="df3b9-301">Assign the DisallowCalling policy to all users in your organization who use Teams in a virtualized environment.</span></span>

<span data-ttu-id="df3b9-302">[**会議ポリシー**](meeting-policies-in-teams.md): Teams には、すべての会議機能が無効になっている組み込みの AllOff 会議ポリシーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="df3b9-302">[**Meeting policies**](meeting-policies-in-teams.md): Teams includes the built-in AllOff meeting policy, in which all meeting features are turned off.</span></span> <span data-ttu-id="df3b9-303">AllOff ポリシーを、仮想化環境で Teams を使用する組織内のすべてのユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="df3b9-303">Assign the AllOff policy to all users in your organization who use Teams in a virtualized environment.</span></span>

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a><span data-ttu-id="df3b9-304">Microsoft Teams 管理センターを使用してポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="df3b9-304">Assign policies using the Microsoft Teams admin center</span></span>

<span data-ttu-id="df3b9-305">DisallowCalling 通話ポリシーと AllOff 会議ポリシーをユーザーに割り当てるには、以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="df3b9-305">To assign the DisallowCalling calling policy and the AllOff meeting policy to a user:</span></span>

1. <span data-ttu-id="df3b9-306">Microsoft Teams 管理センターの左側のナビゲーションで、[**ユーザー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="df3b9-306">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="df3b9-307">ユーザー名の左側をクリックしてユーザーを選択し、[**編集を設定する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df3b9-307">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="df3b9-308">以下の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="df3b9-308">Do the following:</span></span>
    1.  <span data-ttu-id="df3b9-309">[**通話ポリシー**] で、[**DisallowCalling**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df3b9-309">Under **Calling policy**, click **DisallowCalling**.</span></span>
    2.  <span data-ttu-id="df3b9-310">[**会議ポリシー**] で、[**AllOff**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df3b9-310">Under **Meeting policy**, click **AllOff**.</span></span>
4. <span data-ttu-id="df3b9-311">[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df3b9-311">Click **Apply**.</span></span>

<span data-ttu-id="df3b9-312">複数のユーザーに同時にポリシーを割り当てるには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="df3b9-312">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="df3b9-313">Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動し、ユーザーを検索するか、表示にフィルターを適用してユーザーを表示します。</span><span class="sxs-lookup"><span data-stu-id="df3b9-313">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="df3b9-314">[**&#x2713;** (チェックマーク)] の列からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="df3b9-314">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="df3b9-315">すべてのユーザーを選択するには、表の上部にある [&#x2713; (チェックマーク)] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df3b9-315">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="df3b9-316">[**設定の編集**] をクリックし、必要な変更を行い、[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df3b9-316">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>

<span data-ttu-id="df3b9-317">または、次の操作も実行できます。</span><span class="sxs-lookup"><span data-stu-id="df3b9-317">Or, you can also do the following:</span></span>

1. <span data-ttu-id="df3b9-318">Microsoft Teams 管理センターの左側のナビゲーションで、割り当てるポリシーに移動します。</span><span class="sxs-lookup"><span data-stu-id="df3b9-318">In the left navigation of the Microsoft Teams admin center, go to the policy you want to assign.</span></span> <span data-ttu-id="df3b9-319">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="df3b9-319">For example:</span></span>
    - <span data-ttu-id="df3b9-320">[**音声**]  >  [**通話ポリシー**] の順に移動し、[**DisallowCalling**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df3b9-320">Go to **Voice** > **Calling policies**, and then click **DisallowCalling**.</span></span>
    - <span data-ttu-id="df3b9-321">[**会議**]  >  [**会議ポリシー**] の順に移動し、[**AllOff**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df3b9-321">Go to **Meetings** > **Meeting policies**, and then click **AllOff**.</span></span>
2. <span data-ttu-id="df3b9-322">[**ユーザーを管理する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="df3b9-322">Select **Manage users**.</span></span>
3. <span data-ttu-id="df3b9-323">[**ユーザーを管理する**] ウィンドウで、表示名またはユーザー名でユーザーを検索し、名前を選択して [**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df3b9-323">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="df3b9-324">追加するユーザーごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="df3b9-324">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="df3b9-325">ユーザーの追加が完了したら、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df3b9-325">When you're finished adding users, click **Save**.</span></span>

#### <a name="assign-policies-using-powershell"></a><span data-ttu-id="df3b9-326">PowerShell を使用してポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="df3b9-326">Assign policies using PowerShell</span></span>

<span data-ttu-id="df3b9-327">次の例は、[Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) を使用して、DisallowCalling 通話ポリシーをユーザーに割り当てる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="df3b9-327">The following example shows how to use the [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) to assign the DisallowCalling calling policy to a user.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

<span data-ttu-id="df3b9-328">PowerShell を使用して通話ポリシーを管理する方法の詳細については、「[Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df3b9-328">To learn more about using PowerShell to manage calling policies, see [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy).</span></span>

<span data-ttu-id="df3b9-329">次の例は、[Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) を使用して、AllOff 会議ポリシーをユーザーに割り当てる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="df3b9-329">The following example shows how to use the [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) to assign the AllOff meeting policy to a user.</span></span>

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

<span data-ttu-id="df3b9-330">PowerShell を使用して会議ポリシーを管理する方法の詳細については、「[Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df3b9-330">To learn more about using PowerShell to manage meeting policies, see [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>

## <a name="migrate-teams-on-vdi-with-chat-and-collaboration-to-optimize-teams-with-calling-and-meetings"></a><span data-ttu-id="df3b9-331">チャットと共同作業を備えた VDI 上の Teams を移行して、通話と会議を備えた Teams を最適化する</span><span class="sxs-lookup"><span data-stu-id="df3b9-331">Migrate Teams on VDI with chat and collaboration to optimize Teams with calling and meetings</span></span>

<span data-ttu-id="df3b9-332">ユーザーレベル ポリシーで通話および会議機能を無効にするように設定したチャットと共同作業を備えた VDI 上の Teams の既存の実装があり、AV 最適化を備えた Teams に移行する場合、VDI 上の Teams ユーザーのために通話および会議機能を有効にするポリシーを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df3b9-332">If you have an existing implementation of Teams on VDI with chat and collaboration in which you had set user-level policies to turn off calling and meeting functionality, and you're migrating to Teams with AV optimization, you must set policies to turn on calling and meeting functionality for those Teams on VDI users.</span></span>

### <a name="set-policies-to-turn-on-calling-and-meeting-functionality"></a><span data-ttu-id="df3b9-333">通話および会議機能を有効にするポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="df3b9-333">Set policies to turn on calling and meeting functionality</span></span>

<span data-ttu-id="df3b9-334">Microsoft Teams 管理センターまたは PowerShell を使用して、通話および会議ポリシーを設定し、ユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="df3b9-334">You can use the Microsoft Teams admin center or PowerShell to set and assign calling and meeting policies to your users.</span></span> <span data-ttu-id="df3b9-335">ポリシーの変更が反映されるまでに時間がかかる場合があります (数時間)。</span><span class="sxs-lookup"><span data-stu-id="df3b9-335">It can take some time (a few hours) for policy changes to propagate.</span></span> <span data-ttu-id="df3b9-336">指定したアカウントの変更がすぐに表示されない場合は、数時間が経過した後にもう一度お試しください。</span><span class="sxs-lookup"><span data-stu-id="df3b9-336">If you don't see changes for a given account immediately, try again after a few hours.</span></span>

<span data-ttu-id="df3b9-337">[**通話ポリシー**](teams-calling-policy.md): Teams の通話ポリシーは、ユーザーが使用できる通話機能を制御します。</span><span class="sxs-lookup"><span data-stu-id="df3b9-337">[**Calling polices**](teams-calling-policy.md): Calling policies in Teams control which calling features are available to users.</span></span> <span data-ttu-id="df3b9-338">Teams には、すべての通話機能が有効になっている組み込みの AallowCalling 通話ポリシーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="df3b9-338">Teams includes the built-in AllowCalling calling policy, in which all calling features are turned on.</span></span> <span data-ttu-id="df3b9-339">すべての通話機能を有効にするには、AllowCalling ポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="df3b9-339">To turn on all calling features, assign the AllowCalling policy.</span></span> <span data-ttu-id="df3b9-340">または、カスタム通話ポリシーを作成して、必要な通話機能を有効にし、ユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="df3b9-340">Or, create a custom calling policy to turn on the calling features that you want and assign it to users.</span></span> 

<span data-ttu-id="df3b9-341">[**会議ポリシー**](meeting-policies-in-teams.md): Teams の会議ポリシーは、ユーザーが作成できる会議の種類と、組織内のユーザーによってスケジュールされた会議参加者が利用できる機能を制御します。</span><span class="sxs-lookup"><span data-stu-id="df3b9-341">[**Meeting policies**](meeting-policies-in-teams.md): Meeting policies in Teams control the types of meetings that users can create and the features that are available to meeting participants that are scheduled by users in your organization.</span></span> <span data-ttu-id="df3b9-342">Teams には、すべての会議機能が有効になっている組み込みの AllOn 会議ポリシーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="df3b9-342">Teams includes the built-in AllOn meeting policy, in which all meeting features are turned on.</span></span> <span data-ttu-id="df3b9-343">すべての会議機能を有効にするには、AllOn ポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="df3b9-343">To turn on all meeting features, assign the AllOn policy.</span></span> <span data-ttu-id="df3b9-344">または、カスタム会議ポリシーを作成して、必要な会議機能を有効にし、ユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="df3b9-344">Or, create a custom meeting policy to turn on the meeting features that you want and assign it users.</span></span>

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a><span data-ttu-id="df3b9-345">Microsoft Teams 管理センターを使用してポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="df3b9-345">Assign policies using the Microsoft Teams admin center</span></span>

<span data-ttu-id="df3b9-346">AllowCalling 通話ポリシーと AllOn 会議ポリシーをユーザーに割り当てるには、以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="df3b9-346">To assign the AllowCalling calling policy and the AllOn meeting policy to a user:</span></span>

1. <span data-ttu-id="df3b9-347">Microsoft Teams 管理センターの左側のナビゲーションで、[**ユーザー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="df3b9-347">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="df3b9-348">ユーザー名の左側をクリックしてユーザーを選択し、[**編集を設定する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df3b9-348">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="df3b9-349">以下の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="df3b9-349">Do the following:</span></span>
    1.  <span data-ttu-id="df3b9-350">[**通話ポリシー**] で、[**AllowCalling**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df3b9-350">Under **Calling policy**, click **AllowCalling**.</span></span>
    2.  <span data-ttu-id="df3b9-351">[**会議ポリシー**] で、[**AllOn**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df3b9-351">Under **Meeting policy**, click **AllOn**.</span></span>
4. <span data-ttu-id="df3b9-352">[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df3b9-352">Click **Apply**.</span></span>

<span data-ttu-id="df3b9-353">複数のユーザーに同時にポリシーを割り当てるには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="df3b9-353">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="df3b9-354">Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動し、ユーザーを検索するか、表示にフィルターを適用してユーザーを表示します。</span><span class="sxs-lookup"><span data-stu-id="df3b9-354">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="df3b9-355">[**&#x2713;** (チェックマーク)] の列からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="df3b9-355">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="df3b9-356">すべてのユーザーを選択するには、表の上部にある [**&#x2713;** (チェックマーク)] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df3b9-356">To select all users, click the **&#x2713;** (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="df3b9-357">[**設定の編集**] をクリックし、必要な変更を加え、[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df3b9-357">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>

<span data-ttu-id="df3b9-358">または、次の操作も実行できます。</span><span class="sxs-lookup"><span data-stu-id="df3b9-358">Or, you can also do the following:</span></span>

1. <span data-ttu-id="df3b9-359">Microsoft Teams 管理センターの左側のナビゲーションで、割り当てるポリシーに移動します。</span><span class="sxs-lookup"><span data-stu-id="df3b9-359">In the left navigation of the Microsoft Teams admin center, go to the policy you want to assign.</span></span> <span data-ttu-id="df3b9-360">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="df3b9-360">For example:</span></span>
    - <span data-ttu-id="df3b9-361">[**音声**]  >  [**通話ポリシー**] の順に移動し、[**AllowCalling**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df3b9-361">Go to **Voice** > **Calling policies**, and then click **AllowCalling**.</span></span>
    - <span data-ttu-id="df3b9-362">[**会議**]  >  [**会議ポリシー**] の順に移動し、[**AllOn**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df3b9-362">Go to **Meetings** > **Meeting policies**, and then click **AllOn**.</span></span>
2. <span data-ttu-id="df3b9-363">[**ユーザーを管理する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="df3b9-363">Select **Manage users**.</span></span>
3. <span data-ttu-id="df3b9-364">[**ユーザーを管理する**] ウィンドウで、表示名またはユーザー名でユーザーを検索し、名前を選択して [**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df3b9-364">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="df3b9-365">追加するユーザーごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="df3b9-365">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="df3b9-366">ユーザーの追加が完了したら、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df3b9-366">When you're finished adding users, click **Save**.</span></span>

#### <a name="assign-policies-using-powershell"></a><span data-ttu-id="df3b9-367">PowerShell を使用してポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="df3b9-367">Assign policies using PowerShell</span></span>

<span data-ttu-id="df3b9-368">次の例は、[Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) を使用して、AllowCalling 通話ポリシーをユーザーに割り当てる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="df3b9-368">The following example shows how to use the [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) to assign the AllowCalling calling policy to a user.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName AllowCalling -Identity "user email id"
```

<span data-ttu-id="df3b9-369">PowerShell を使用して通話ポリシーを管理する方法の詳細については、「[Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df3b9-369">To learn more about using PowerShell to manage calling policies, see [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy).</span></span>

<span data-ttu-id="df3b9-370">次の例は、[Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) を使用して、AllOn 会議ポリシーをユーザーに割り当てる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="df3b9-370">The following example shows how to use the [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) to assign the AllOn meeting policy to a user.</span></span>

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOn -Identity "user email id"
```

<span data-ttu-id="df3b9-371">PowerShell を使用して会議ポリシーを管理する方法の詳細については、「[Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df3b9-371">To learn more about using PowerShell to manage meeting policies, see [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>

## <a name="control-fallback-mode-in-teams"></a><span data-ttu-id="df3b9-372">Teams でフォールバック モードを制御する</span><span class="sxs-lookup"><span data-stu-id="df3b9-372">Control fallback mode in Teams</span></span>

<span data-ttu-id="df3b9-373">ユーザーがサポートされていないエンドポイントから接続すると、ユーザーはフォールバック モードになり、AV は最適化されません。</span><span class="sxs-lookup"><span data-stu-id="df3b9-373">When users connect from an unsupported endpoint, the users are in fallback mode, in which AV isn't optimized.</span></span> <span data-ttu-id="df3b9-374">次のレジストリ DWORD 値のいずれかを設定して、フォールバック モードを無効または有効にできます。</span><span class="sxs-lookup"><span data-stu-id="df3b9-374">You can disable or enable fallback mode by setting one of the following registry DWORD values:</span></span>

- <span data-ttu-id="df3b9-375">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Teams\DisableFallback</span><span class="sxs-lookup"><span data-stu-id="df3b9-375">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Teams\DisableFallback</span></span>
- <span data-ttu-id="df3b9-376">HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\Teams\DisableFallback</span><span class="sxs-lookup"><span data-stu-id="df3b9-376">HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\Teams\DisableFallback</span></span>

<span data-ttu-id="df3b9-377">フォールバック モードを無効にするには、値を **1** に設定します。</span><span class="sxs-lookup"><span data-stu-id="df3b9-377">To disable fallback mode, set the value to **1**.</span></span> <span data-ttu-id="df3b9-378">音声のみを有効にするには、値を **2** に設定します。</span><span class="sxs-lookup"><span data-stu-id="df3b9-378">To enable audio only, set the value to **2**.</span></span> <span data-ttu-id="df3b9-379">値が存在しない場合、または **0** (ゼロ) に設定されている場合は、フォールバック モードが有効になります。</span><span class="sxs-lookup"><span data-stu-id="df3b9-379">If the value isn't present or is set to **0** (zero), fallback mode is enabled.</span></span>

<span data-ttu-id="df3b9-380">この機能は、バージョン 1.3.00.13565 以降の Teams で使用できます。</span><span class="sxs-lookup"><span data-stu-id="df3b9-380">This feature is available in Teams version 1.3.00.13565 and later.</span></span>

## <a name="known-issues-and-limitations"></a><span data-ttu-id="df3b9-381">既知の問題と制限事項</span><span class="sxs-lookup"><span data-stu-id="df3b9-381">Known issues and limitations</span></span>

### <a name="client-deployment-installation-and-setup"></a><span data-ttu-id="df3b9-382">クライアントの展開、インストール、およびセットアップ</span><span class="sxs-lookup"><span data-stu-id="df3b9-382">Client deployment, installation, and setup</span></span>

- <span data-ttu-id="df3b9-383">マシンごとのインストールでは、VDI 上の Teams は、非 VDI Teams のクライアントと同様に自動的に更新されません。</span><span class="sxs-lookup"><span data-stu-id="df3b9-383">With per-machine installation, Teams on VDI isn't automatically updated in the way that non-VDI Teams clients are.</span></span> <span data-ttu-id="df3b9-384">[VDI で Teams デスクトップ アプリをインストールまたは更新する](#install-or-update-the-teams-desktop-app-on-vdi)セクションの説明に従って新しい MSI をインストールし、VM イメージを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df3b9-384">You have to update the VM image by installing a new MSI as described in the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.</span></span> <span data-ttu-id="df3b9-385">現在のバージョンをアンインストールして新しいバージョンに更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df3b9-385">You must uninstall the current version to update to a newer version.</span></span>
- <span data-ttu-id="df3b9-386">Citrix 環境では、Teams の実行中にユーザーが仮想マシンから切断された場合、Teams の更新により、再接続時にユーザーが AV 用に最適化されていない状態になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="df3b9-386">In Citrix environments, if the user disconnects from the Virtual Machine while Teams is running, Teams updates can result in the user to be in a non-optimized state for AV when they reconnect.</span></span> <span data-ttu-id="df3b9-387">ユーザーは、このシナリオを回避Teams Citrix 仮想マシンから切断する前に、アプリケーションを終了することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="df3b9-387">We recommend that users quit Teams before they disconnect from Citrix Virtual Machine to avoid this scenario.</span></span>
- <span data-ttu-id="df3b9-388">Teams は、ユーザーごとまたはマシンごとに展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df3b9-388">Teams should be deployed either per user or per machine.</span></span> <span data-ttu-id="df3b9-389">Teams のユーザーごとおよびマシンごとの同時展開はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="df3b9-389">Deployment of Teams for concurrent per user and per machine is not supported.</span></span> <span data-ttu-id="df3b9-390">マシンごとまたはユーザーごとからこれらのモードのいずれかに移行するには、アンインストール手順に従っていずれかのモードに再展開します。</span><span class="sxs-lookup"><span data-stu-id="df3b9-390">To migrate from either per machine or per user to one of these modes, follow the uninstall procedure and redeploy to either mode.</span></span>
- <span data-ttu-id="df3b9-391">Windows現時点では、Virtual Desktop は macOS および Linux ベースのクライアントをサポートしません。</span><span class="sxs-lookup"><span data-stu-id="df3b9-391">Windows Virtual Desktop doesn't support macOS and Linux-based clients at this time.</span></span>

### <a name="calling-and-meetings"></a><span data-ttu-id="df3b9-392">通話と会議</span><span class="sxs-lookup"><span data-stu-id="df3b9-392">Calling and meetings</span></span>

<span data-ttu-id="df3b9-393">次の通話および会議機能はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="df3b9-393">The following calling and meeting features are not supported:</span></span>

- <span data-ttu-id="df3b9-394">新しい会議エクスペリエンスなどのマルチウィンドウ機能、または新しい会議エクスペリエンスに付属する機能</span><span class="sxs-lookup"><span data-stu-id="df3b9-394">Any multi-window functionality like the new meeting experiences or any functionality that comes with the new meeting experience</span></span>
- <span data-ttu-id="df3b9-395">拡張緊急サービス</span><span class="sxs-lookup"><span data-stu-id="df3b9-395">Enhanced emergency services</span></span>
- <span data-ttu-id="df3b9-396">Teams アプリとデバイス間の HID ボタンと LED コントロール</span><span class="sxs-lookup"><span data-stu-id="df3b9-396">HID buttons and LED controls between the Teams app and devices</span></span>
- <span data-ttu-id="df3b9-397">背景のぼかしと効果</span><span class="sxs-lookup"><span data-stu-id="df3b9-397">Background blur and effects</span></span>
- <span data-ttu-id="df3b9-398">ブロードキャストとライブ イベントのプロデューサーと発表者の役割</span><span class="sxs-lookup"><span data-stu-id="df3b9-398">Broadcast and live event producer and presenter roles</span></span>
- <span data-ttu-id="df3b9-399">場所に基づくルーティング (LBR)</span><span class="sxs-lookup"><span data-stu-id="df3b9-399">Location-Based Routing (LBR)</span></span>
- <span data-ttu-id="df3b9-400">PSTN 通話呼び出しの呼び出し音</span><span class="sxs-lookup"><span data-stu-id="df3b9-400">PSTN call ringback tone</span></span>
- <span data-ttu-id="df3b9-401">共有システムのオーディオ/コンピューターのサウンド</span><span class="sxs-lookup"><span data-stu-id="df3b9-401">Shared system audio/computer sound</span></span>
- <span data-ttu-id="df3b9-402">ダイレクト ルーティングのメディア バイパス</span><span class="sxs-lookup"><span data-stu-id="df3b9-402">Media bypass for Direct Routing</span></span>
- <span data-ttu-id="df3b9-403">コール パーク</span><span class="sxs-lookup"><span data-stu-id="df3b9-403">Call park</span></span>
- <span data-ttu-id="df3b9-404">ズーム コントロール</span><span class="sxs-lookup"><span data-stu-id="df3b9-404">Zoom control</span></span> 

> [!NOTE]
> <span data-ttu-id="df3b9-405">現在は非 VDI 環境でのみ利用可能な通話および会議機能の追加に取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="df3b9-405">We're working on adding calling and meeting features that are currently only available in non-VDI environments.</span></span> <span data-ttu-id="df3b9-406">これらには、品質についての管理者制御の強化、画面共有シナリオの追加、および最近 Teams に追加された高度な機能が含まれる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="df3b9-406">These might include more admin control over quality, additional screen sharing scenarios, and advanced features recently added to Teams.</span></span> <span data-ttu-id="df3b9-407">今後の機能の詳細については、Teams の担当者にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="df3b9-407">Contact your Teams representative to learn more about upcoming features.</span></span>

<span data-ttu-id="df3b9-408">通話と会議に関する既知の問題と制限事項を次に示します。</span><span class="sxs-lookup"><span data-stu-id="df3b9-408">The following are known issues and limitations for calling and meetings:</span></span>

- <span data-ttu-id="df3b9-409">Skype for Business との相互運用性は、音声通話に限定されます。ビデオ モダリティはありません。</span><span class="sxs-lookup"><span data-stu-id="df3b9-409">Interoperability with Skype for Business is limited to audio calls; there is no video modality.</span></span>
- <span data-ttu-id="df3b9-410">受信および送信ビデオ ストリームの解像度は、720p に制限されています。</span><span class="sxs-lookup"><span data-stu-id="df3b9-410">Incoming and outgoing video stream resolution is limited to 720p resolution.</span></span>
- <span data-ttu-id="df3b9-411">受信カメラまたは画面共有ストリームからの 1 つのビデオ ストリームのみがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="df3b9-411">Only one video stream from an incoming camera or screen share stream is supported.</span></span> <span data-ttu-id="df3b9-412">受信画面共有がある場合、主要な発表者のビデオではなく、その画面共有が表示されます。</span><span class="sxs-lookup"><span data-stu-id="df3b9-412">When there's an incoming screen share, that screen share is shown, instead of the video of the dominant speaker.</span></span>
- <span data-ttu-id="df3b9-413">デバイスが切断されて再接続された場合、ユーザーが最後に選択したオーディオ デバイスが使用されるように切り替えられません。</span><span class="sxs-lookup"><span data-stu-id="df3b9-413">Teams doesn't switch to use the last audio device that a user selected, if the device is disconnected, and then reconnected.</span></span>
- <span data-ttu-id="df3b9-414">送信画面の共有:</span><span class="sxs-lookup"><span data-stu-id="df3b9-414">Outgoing screen sharing:</span></span>
    - <span data-ttu-id="df3b9-415">アプリケーションの共有はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="df3b9-415">Application sharing is not supported.</span></span>
- <span data-ttu-id="df3b9-416">制御の受け渡し:</span><span class="sxs-lookup"><span data-stu-id="df3b9-416">Give control and take control:</span></span>
    - <span data-ttu-id="df3b9-417">画面共有またはアプリケーション共有セッション中はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="df3b9-417">Not supported during a screen sharing or application sharing session.</span></span>
    - <span data-ttu-id="df3b9-418">PowerPoint 共有セッション中はサポートされます。</span><span class="sxs-lookup"><span data-stu-id="df3b9-418">Supported during a PowerPoint sharing session.</span></span>
- <span data-ttu-id="df3b9-419">Citrix 限定の制限事項</span><span class="sxs-lookup"><span data-stu-id="df3b9-419">Citrix-only limitations</span></span>
    - <span data-ttu-id="df3b9-420">マルチモニター設定での画面共有の場合、メイン モニターのみ共有されます。</span><span class="sxs-lookup"><span data-stu-id="df3b9-420">When screen sharing in a multi-monitor setup, only the main monitor is shared.</span></span>
    - <span data-ttu-id="df3b9-421">CWA での高 DPI スケーリングはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="df3b9-421">High DPI scaling on CWA is not supported.</span></span>

<span data-ttu-id="df3b9-422">VDI に関連しない Teams の既知の問題については、「[組織で Teams をサポートする](/MicrosoftTeams/troubleshoot/teams-welcome)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df3b9-422">For Teams known issues that aren't related to VDI, see [Support Teams in your organization](/MicrosoftTeams/troubleshoot/teams-welcome).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="df3b9-423">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="df3b9-423">Troubleshooting</span></span>

### <a name="troubleshoot-citrix-components"></a><span data-ttu-id="df3b9-424">Citrix コンポーネントのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="df3b9-424">Troubleshoot Citrix components</span></span>

#### <a name="teams-crashes-or-the-teams-sign-in-screen-is-blank"></a><span data-ttu-id="df3b9-425">Teams がクラッシュする、または Teams のサインイン画面が空白になる</span><span class="sxs-lookup"><span data-stu-id="df3b9-425">Teams crashes or the Teams sign in screen is blank</span></span>

<span data-ttu-id="df3b9-426">これは、Citrix VDA バージョン 1906 および 1909 の既知の問題です。</span><span class="sxs-lookup"><span data-stu-id="df3b9-426">This is a known issue with Citrix VDA versions 1906 and 1909.</span></span> <span data-ttu-id="df3b9-427">この問題を回避するには、次のレジストリ DWORD 値を追加し、204 (16 進数) に設定します。</span><span class="sxs-lookup"><span data-stu-id="df3b9-427">To work around this issue, add the following registry DWORD value, and set it to 204 (hexadecimal).</span></span>

<span data-ttu-id="df3b9-428">HKEY_LOCAL_MACHINE\SOFTWARE\Citrix\CtxHook\AppInit_Dlls\SfrHook\Teams.exe</span><span class="sxs-lookup"><span data-stu-id="df3b9-428">HKEY_LOCAL_MACHINE\SOFTWARE\Citrix\CtxHook\AppInit_Dlls\SfrHook\Teams.exe</span></span>

<span data-ttu-id="df3b9-429">次に、VDA を再起動します。</span><span class="sxs-lookup"><span data-stu-id="df3b9-429">Then, restart VDA.</span></span> <span data-ttu-id="df3b9-430">詳細については、この Citrix サポート記事「[Teams の HDX 最適化のトラブルシューティング](https://support.citrix.com/article/CTX253754)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df3b9-430">To learn more, see this Citrix support article, [Troubleshooting HDX optimization for Teams](https://support.citrix.com/article/CTX253754).</span></span>

## <a name="related-topics"></a><span data-ttu-id="df3b9-431">関連項目</span><span class="sxs-lookup"><span data-stu-id="df3b9-431">Related topics</span></span>

- [<span data-ttu-id="df3b9-432">MSI を使用して Microsoft Teams をインストールする</span><span class="sxs-lookup"><span data-stu-id="df3b9-432">Install Microsoft Teams using MSI</span></span>](msi-deployment.md)
- [<span data-ttu-id="df3b9-433">Teams での PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="df3b9-433">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="df3b9-434">Windows Virtual Desktop で Microsoft Teams を使用する</span><span class="sxs-lookup"><span data-stu-id="df3b9-434">Use Microsoft Teams on Windows Virtual desktop</span></span>](/azure/virtual-desktop/teams-on-wvd)
