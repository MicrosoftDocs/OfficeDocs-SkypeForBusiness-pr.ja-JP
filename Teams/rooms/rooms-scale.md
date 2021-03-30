---
title: Microsoft Endpoint Configuration Manager を使用して Microsoft Teams Rooms を展開する
author: dstrome
ms.author: dstrome
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom:
- Strat_SB_Admin
- seo-marvel-apr2020
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
ms.collection:
- M365-collaboration
description: Microsoft Endpoint Configuration Manager を使用した、大規模な Microsoft Teams Rooms の展開の方法について説明します。
no-loc:
- Microsoft
- Microsoft Corporation
- Microsoft Teams Rooms
- Microsoft Teams Room
- System Center
- Configuration Manager
- Windows
- Surface
- Surface Pro
- Windows PE
- Windows 10
- Windows 10 Enterprise
- Azure
- Azure Monitor
- Log Analytics
- Operations Management Suite
ms.openlocfilehash: 2348d0f3e9d94aed80494155fbaab8288ddd97a6
ms.sourcegitcommit: 95386369e2256ba382b4d6e34adb7473de050b26
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2021
ms.locfileid: "51410113"
---
# <a name="deploy-microsoft-teams-rooms-by-using-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="dbbc3-103">Microsoft Endpoint Configuration Manager を使用して Microsoft Teams Rooms を展開する</span><span class="sxs-lookup"><span data-stu-id="dbbc3-103">Deploy Microsoft Teams Rooms by using Microsoft Endpoint Configuration Manager</span></span>

<span data-ttu-id="dbbc3-104">この記事では、Microsoft Endpoint Configuration Manager を使用して、Microsoft Teams Rooms の展開をするために必要なすべての情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-104">This article gives you all the necessary information to create your Microsoft Teams Rooms deployments by using Microsoft Endpoint Configuration Manager.</span></span>

<span data-ttu-id="dbbc3-105">構成マネージャーが提供する簡単な方法では、複数のターゲット デバイスにオペレーティング システムとその他のアプリケーションを展開することができます。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-105">With the easy-to-use methods provided by Configuration Manager, you can deploy the operating system and other applications to multiple target devices.</span></span>

<span data-ttu-id="dbbc3-106">次に示すアプローチを使用して、構成マネージャーの構成を行い、組織のニーズに応じて、このガイド全体のサンプル パッケージとスクリプトをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-106">Use the approach illustrated below to guide you through your Configuration Manager configuration, and customize the sample packages and scripts provided throughout this guidance as needed for your organization.</span></span>

![構成マネージャーを使用した Microsoft Teams Rooms の展開プロセス](../media/room-systems-scale-image1.png)

> [!IMPORTANT]
> <span data-ttu-id="dbbc3-108">この解決方法は、Surface Pro ベースの展開でのみテストされています。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-108">This solution has only been tested with Surface Pro–based deployments.</span></span> <span data-ttu-id="dbbc3-109">Surface Pro をベースにしていない構成については、メーカーのガイドラインに従ってください。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-109">Follow the manufacturer's guidelines for configurations that aren't based on Surface Pro.</span></span>

## <a name="validate-prerequisites"></a><span data-ttu-id="dbbc3-110">前提条件の検証</span><span class="sxs-lookup"><span data-stu-id="dbbc3-110">Validate prerequisites</span></span>

<span data-ttu-id="dbbc3-111">Microsoft Teams Rooms を構成マネージャーで展開するにあたり、次の前提条件と要件を満たしていることをご確認ください。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-111">To deploy Microsoft Teams Rooms with Configuration Manager, ensure that you meet the following prerequisites and requirements.</span></span>

### <a name="microsoft-endpoint-configuration-manager-requirements"></a><span data-ttu-id="dbbc3-112">Microsoft Endpoint Configuration Manager の要件</span><span class="sxs-lookup"><span data-stu-id="dbbc3-112">Microsoft Endpoint Configuration Manager requirements</span></span>

-   <span data-ttu-id="dbbc3-113">Microsoft Endpoint Configuration Manager のバージョンは、少なくとも 1706 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-113">Microsoft Endpoint Configuration Manager version must be at least 1706 or above.</span></span> <span data-ttu-id="dbbc3-114">1710 以降を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-114">We recommend using 1710 or later.</span></span> <span data-ttu-id="dbbc3-115">[構成マネージャー内の Windows 10 のサポート](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client)を確認し、構成マネージャーでサポートされている Windows 10 のバージョンを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-115">Check out [Support for Windows 10 in Configuration Manager](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) to learn about the Windows 10 versions that Configuration Manager supports.</span></span>

-   <span data-ttu-id="dbbc3-116">Windows 10 用の Windows アセスメント & デプロイメント キット (ADK) のサポートされているバージョンがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-116">A supported version of Windows Assessment and Deployment Kit (ADK) for Windows 10 must be installed.</span></span> <span data-ttu-id="dbbc3-117">異なるバージョンの構成マネージャーで使用できる [Windows 10 ADK](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-adk) のバージョンを参照して、展開に正しいバージョンが含まれていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-117">See the versions of the [Windows 10 ADK](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-adk) that you can use with different versions of Configuration Manager, and ensure that your deployment includes the correct version.</span></span>

-   <span data-ttu-id="dbbc3-118">サイト システム サーバーには配布ポイントの役割が割り当てられている必要があります。また、ネットワークを利用した展開を有効にするには、ブート イメージの[プレブート実行環境 (PXE) のサポート](/configmgr/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network)を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-118">The site system servers must have been assigned the distribution point role, and the boot images should be enabled for [preboot execution environment (PXE) support](/configmgr/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) to enable network-initiated deployments.</span></span> <span data-ttu-id="dbbc3-119">PXE のサポートが有効になっていない場合は、[起動可能なメディア](/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network)を展開に使用できます。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-119">If PXE support isn't enabled, you can use [bootable media](/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) for your deployments.</span></span>

-   <span data-ttu-id="dbbc3-120">新しいコンピューター (ベア メタル) の展開シナリオをサポートするには、ネットワーク アクセス アカウントを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-120">A network access account must be configured to support new computer (bare metal) deployment scenarios.</span></span> <span data-ttu-id="dbbc3-121">ネットワーク アクセス アカウントの構成の詳細については、[「構成マネージャーで使用するアカウント」](/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-121">To learn more about the configuration of a network access account, see [Accounts used in Configuration Manager](/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span></span>

-   <span data-ttu-id="dbbc3-122">同じ Microsoft Teams Rooms のイメージを、複数のユニットに同時に展開した場合は、[マルチキャスト サポート](/configmgr/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network)を有効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-122">We recommend that you enable [multicast support](/configmgr/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network), if you're likely to deploy the same Microsoft Teams Rooms image to multiple units at the same time.</span></span>

### <a name="networking-requirements"></a><span data-ttu-id="dbbc3-123">ネットワークの要件</span><span class="sxs-lookup"><span data-stu-id="dbbc3-123">Networking requirements</span></span>

-   <span data-ttu-id="dbbc3-124">使用しているネットワークには、Microsoft Teams Rooms ユニットが展開されるサブネットに対して、IP アドレスを自動的に配布するように構成された動的ホスト構成プロトコル (DHCP) サーバーが必要です。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-124">Your network should have a Dynamic Host Configuration Protocol (DHCP) server, configured for automatic IP address distribution to the subnets where Microsoft Teams Rooms units will be deployed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="dbbc3-125">DHCP リース期間は、イメージの展開期間よりも長い値を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-125">DHCP lease duration must be set to a value longer than the image deployment duration.</span></span> <span data-ttu-id="dbbc3-126">それ以外の場合、展開に失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-126">Otherwise, the deployment might fail.</span></span>

-   <span data-ttu-id="dbbc3-127">スイッチと仮想 LAN (VLAN) を含むネットワークは、PXE をサポートするように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-127">Your network, including switches and virtual LANs (VLANs), should be configured to support PXE.</span></span> <span data-ttu-id="dbbc3-128">IP Helper および PXE 構成の詳細については、ネットワーク ベンダーにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-128">Refer to your network vendor for more information about IP Helper and PXE configuration.</span></span> <span data-ttu-id="dbbc3-129">また、PXE サポートが有効になっていない場合は、[起動可能なメディア](/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network)を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-129">Alternatively, you can use [bootable media](/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) for your deployments, if PXE support isn't enabled.</span></span>

    > [!NOTE]
    > <span data-ttu-id="dbbc3-130">Surface Pro デバイスの場合、ネットワークからの起動 (PXE ブート) は、Microsoft の Ethernet アダプター、またはドッキング ステーションを使用している場合にのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-130">For Surface Pro devices, booting from the network (PXE boot) is only supported when you use an Ethernet adapter or docking station from Microsoft.</span></span> <span data-ttu-id="dbbc3-131">サードパーティ製のイーサネット アダプターは Surface Pro による PXE ブートをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-131">Third-party Ethernet adapters don't support PXE boot with Surface Pro.</span></span> <span data-ttu-id="dbbc3-132">詳細については、[「イーサネット アダプターと Surface の展開」](/surface/ethernet-adapters-and-surface-device-deployment)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-132">See [Ethernet adapters and Surface deployment](/surface/ethernet-adapters-and-surface-device-deployment) for more information.</span></span>

## <a name="configure-microsoft-endpoint-configuration-manager-for-operating-system-deployment"></a><span data-ttu-id="dbbc3-133">オペレーティング システムの展開用に Microsoft Endpoint Configuration Manager を構成する</span><span class="sxs-lookup"><span data-stu-id="dbbc3-133">Configure Microsoft Endpoint Configuration Manager for operating system deployment</span></span>

<span data-ttu-id="dbbc3-134">この記事では、構成マネージャーが正常に展開されていることを前提としているため、構成マネージャーを一から展開して構成するために必要なすべての手順については説明していません。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-134">This article assumes you already have a healthy Configuration Manager deployment, and doesn't detail all the steps required to deploy and configure Configuration Manager from scratch.</span></span> <span data-ttu-id="dbbc3-135">Microsoft Endpoint Configuration Manager の [ドキュメントと構成のガイダンス](/configmgr/)は、優れたリソースです。構成マネージャーをまだ展開していない場合は、これらのリソースから始めることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-135">The [documentation and the configuration guidance](/configmgr/) on the Microsoft Endpoint Configuration Manager is a great resource; we recommend you start with these resources if you haven't yet deployed Configuration Manager.</span></span>

<span data-ttu-id="dbbc3-136">オペレーティング システムの展開 (OSD) 機能が正しく構成されていることを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-136">Use the following instructions to verify that the operating system deployment (OSD) features are configured properly.</span></span>

### <a name="validate-and-upgrade-configuration-manager"></a><span data-ttu-id="dbbc3-137">構成マネージャーの検証とアップグレード</span><span class="sxs-lookup"><span data-stu-id="dbbc3-137">Validate and upgrade Configuration Manager</span></span>

1.  <span data-ttu-id="dbbc3-138">構成マネージャー コンソールで、[**管理**] \> [**更新とサービス**]に移動します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-138">In the Configuration Manager console, go to **Administration** \> **Updates and Servicing**.</span></span>

2.  <span data-ttu-id="dbbc3-139">インストールされているビルドおよびインストールされていない更新プログラムを確認します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-139">Check the installed build and applicable updates that haven't been installed yet.</span></span>

3.  <span data-ttu-id="dbbc3-140">[構成マネージャーでの Windows 10 のサポート](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client)を確認します。展開をアップグレードする必要がある場合は、インストールする更新プログラムを選択し、[**ダウンロード**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-140">Review [Support for Windows 10 in Configuration Manager](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client); if you need to upgrade your deployment, select the update you want to install, and then select **Download**.</span></span>

4.  <span data-ttu-id="dbbc3-141">ダウンロードが完了したら、更新プログラムを選択し、[**更新プログラム パックをインストール**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-141">After the download is complete, select the update, and then select **Install Update Pack**.</span></span>

### <a name="configure-distribution-points-to-support-pxe-and-multicast"></a><span data-ttu-id="dbbc3-142">PXE とマルチキャストをサポートするように配布ポイントを構成する</span><span class="sxs-lookup"><span data-stu-id="dbbc3-142">Configure distribution points to support PXE and multicast</span></span>

1.  <span data-ttu-id="dbbc3-143">構成マネージャー コンソールで、[**管理**] \> [**配布ポイント**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-143">In the Configuration Manager console, go to **Administration** \> **Distribution Points**.</span></span>

2.  <span data-ttu-id="dbbc3-144">Microsoft Teams Rooms の展開に使用する配布ポイント サーバーを選択し、[**プロパティ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-144">Select the distribution point server that will serve the Microsoft Teams Rooms deployment, and then select **Properties**.</span></span>

3.  <span data-ttu-id="dbbc3-145">[**PXE**] タブを選択し、次の設定が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-145">Select the **PXE** tab, and ensure that the following settings are enabled:</span></span>
    -   <span data-ttu-id="dbbc3-146">クライアントの PXE サポートの有効化</span><span class="sxs-lookup"><span data-stu-id="dbbc3-146">Enable PXE support for clients</span></span>
    -   <span data-ttu-id="dbbc3-147">この配布ポイントに受信 PXE 要求に応答することを許可する</span><span class="sxs-lookup"><span data-stu-id="dbbc3-147">Allow this distribution point to respond to incoming PXE requests</span></span>
    -   <span data-ttu-id="dbbc3-148">不明なコンピューターのサポートを有効にする</span><span class="sxs-lookup"><span data-stu-id="dbbc3-148">Enable unknown computer support</span></span>

4.  <span data-ttu-id="dbbc3-149">*省略可能:* マルチキャストのサポートを有効にするには、[**マルチキャスト**] タブを選択し、次の設定が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-149">*Optional:* To enable multicast support, select the **Multicast** tab, and ensure that the following settings are enabled:</span></span>
    -   <span data-ttu-id="dbbc3-150">マルチキャストで、複数のクライアントに同時にデータを送信できるようにする</span><span class="sxs-lookup"><span data-stu-id="dbbc3-150">Enable multicast to simultaneously send data to multiple clients</span></span>
    -   <span data-ttu-id="dbbc3-151">ネットワーク チームの推奨事項に応じて、UDP ポートの範囲を構成します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-151">Configure the UDP port range as per your network team's recommendation</span></span>

### <a name="configure-the-network-access-account"></a><span data-ttu-id="dbbc3-152">ネットワーク アクセス アカウントを構成する</span><span class="sxs-lookup"><span data-stu-id="dbbc3-152">Configure the Network Access Account</span></span>

1.  <span data-ttu-id="dbbc3-153">構成マネージャー コンソールで、[**管理**] \> [**サイト構成**] \> [**サイト**] に移動して、サイトを選びます。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-153">In the Configuration Manager console, go to **Administration** \> **Site Configuration** \> **Sites**, and then select the site.</span></span>

2.  <span data-ttu-id="dbbc3-154">[**設定**] グループで、[**サイト コンポーネントの構成**] \> [**ソフトウェア配布**]を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-154">In the **Settings** group, select **Configure Site Components** \> **Software Distribution**.</span></span>

3.  <span data-ttu-id="dbbc3-155">[**ネットワーク アクセス アカウント**] タブを選択します。1 つまたは複数のアカウントを設定し、[**OK**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-155">Select the **Network Access Account** tab. Set up one or more accounts, and then select **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="dbbc3-156">アカウントには特別な権限は必要ありません。ただし、配布ポイント サーバー上の [**ネットワークからこのコンピューターにアクセスする権限**] を除きます。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-156">The accounts don't need any special rights, except for the **Access this computer from the network** right on the distribution point server.</span></span> <span data-ttu-id="dbbc3-157">汎用ドメイン ユーザー アカウントが適しています。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-157">A generic domain user account will be appropriate.</span></span> <span data-ttu-id="dbbc3-158">詳細については、[「構成マネージャーで使用されているアカウント」](/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-158">For more information, see [Accounts used in Configuration Manager](/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span></span>

### <a name="configure-a-boot-image"></a><span data-ttu-id="dbbc3-159">ブート イメージを構成する</span><span class="sxs-lookup"><span data-stu-id="dbbc3-159">Configure a boot image</span></span>

1.  <span data-ttu-id="dbbc3-160">構成マネージャー コンソールで、[**ソフトウェアライブラリ**] \> [**オペレーティングシステム**] \> [**ブートイメージ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-160">In the Configuration Manager console, go to **Software Library** \> **Operating System** \> **Boot Images**.</span></span>

2.  <span data-ttu-id="dbbc3-161">**ブート イメージ (x64)** を選択し、[**プロパティ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-161">Select **Boot image (x64)**, and then select **Properties**.</span></span>

3.  <span data-ttu-id="dbbc3-162">[**データ ソース**] タブを選択し、[**PXE 対応の配布ポイントからこのブート イメージを展開する**] を有効にします。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-162">Select the **Data Source** tab, and enable **Deploy this boot image from the PXE-enabled distribution point**.</span></span>

4.  <span data-ttu-id="dbbc3-163">必要なコンポーネントをインストールするには、[**オプションコンポーネント**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-163">Select the **Optional Components** tab to install required components:</span></span>

    1.  <span data-ttu-id="dbbc3-164">星型のアイコンを選び、**HTML (WinPE) を検索します**</span><span class="sxs-lookup"><span data-stu-id="dbbc3-164">Select the star icon, and search for **HTML (WinPE-HTA)**</span></span>

    2.  <span data-ttu-id="dbbc3-165">[**OK**] を選択して、HTML アプリケーション サポートをブート イメージに追加します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-165">Select **OK** to add HTML application support in to the boot image.</span></span>

5.  <span data-ttu-id="dbbc3-166">*省略可能:* 展開エクスペリエンスをカスタマイズするには、[**カスタマイズ**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-166">*Optional:* To customize the deployment experience, select the **Customization** tab.</span></span>
    -   <span data-ttu-id="dbbc3-167">展開中にコマンド プロンプトにアクセスできるようにするには、[**コマンドのサポート (テストのみ)**] を有効にします。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-167">Enable **command support (testing only)** if you want to have access to a command prompt during the deployment.</span></span> <span data-ttu-id="dbbc3-168">この設定を有効にすると、展開中にいつでも [**F8**] を選択して、コマンド プロンプトを起動できます。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-168">When this is enabled, you can start a command prompt by selecting **F8** at any time during the deployment.</span></span>
    -   <span data-ttu-id="dbbc3-169">展開中に表示されるカスタム背景画像を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-169">You can also specify a custom background image to be displayed during the deployment.</span></span> <span data-ttu-id="dbbc3-170">画像を設定するには、[**カスタム背景画像ファイル （UNCパス) の指定**] を有効にして、背景を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-170">To set an image, enable **Specify the custom background image file (UNC path** and select your background.</span></span>

6.  <span data-ttu-id="dbbc3-171">メッセージが表示されたら、[**はい**] を選択し、更新されたブート イメージを配布ポイントに配布します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-171">When asked, select **Yes** and distribute the updated boot image to your distribution points.</span></span>

<span data-ttu-id="dbbc3-172">詳細については、[「構成マネージャーを使用してブートイメージを管理する」](/configmgr/osd/get-started/manage-boot-images)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-172">For more information, see [Manage boot images with Configuration Manager](/configmgr/osd/get-started/manage-boot-images).</span></span>

> [!NOTE]
> <span data-ttu-id="dbbc3-173">PXE がサポートされていない環境向けに、構成マネージャーのタスク シーケンス ベースの展開を開始するために、起動可能な USB メディアを作成できます。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-173">You can create a bootable USB media to initiate Configuration Manager task sequence–based deployments for environments that have no PXE support.</span></span> <span data-ttu-id="dbbc3-174">ブート可能なメディアには、ブート イメージ、オプションの実行可能コマンド、必須ファイル、および Windows PE へのブートとデプロイメントプロセスの残りの部分の構成マネージャーへの接続をサポートする、構成マネージャー バイナリのみが含まれています。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-174">The bootable media contains only the boot image, optional prestart commands and their required files, and Configuration Manager binaries to support booting into Windows PE and connecting to Configuration Manager for the rest of the deployment process.</span></span> <span data-ttu-id="dbbc3-175">詳細については、「[ブート可能なメディアの作成](/configmgr/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-175">For more information, see [Create bootable media](/configmgr/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia).</span></span>

## <a name="create-configuration-manager-packages"></a><span data-ttu-id="dbbc3-176">構成マネージャー パッケージを作成する</span><span class="sxs-lookup"><span data-stu-id="dbbc3-176">Create Configuration Manager packages</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dbbc3-177">各 SRS インストーラー バージョンに要求されるオペレーティング システムのバージョンは、MSI リリースごとに変わります。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-177">The required operating system version for each SRS installer version changes with every MSI release.</span></span> <span data-ttu-id="dbbc3-178">特定の MSI に最適なオペレーティング システム バージョンを決定するには、コンソール セットアップ スクリプトを一度実行します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-178">To determine the best operating system version for a given MSI, run the console setup script once.</span></span> <span data-ttu-id="dbbc3-179">詳細については、「[Microsoft Endpoint Configuration Manager を使用して Microsoft Teams Rooms を展開する](rooms-scale.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-179">To learn more, see [Deploy Microsoft Teams Rooms by using Microsoft Endpoint Configuration Manager](rooms-scale.md).</span></span>

<span data-ttu-id="dbbc3-180">構成マネージャーでは、Microsoft Teams Rooms ユニットの展開と構成を行うため、いくつかのパッケージが必要になります。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-180">Configuration Manager requires a number of packages to deploy and configure the Microsoft Teams Rooms units.</span></span>

<span data-ttu-id="dbbc3-181">次のパッケージを作成して構成し、配布ポイント サーバーの役割が割り当てられた 構成マネージャー サイト システムに配布する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-181">You need to create and configure the following packages, and then distribute them to the Configuration Manager site systems that have been assigned the distribution point server role.</span></span>

| <span data-ttu-id="dbbc3-182">**パッケージ名**</span><span class="sxs-lookup"><span data-stu-id="dbbc3-182">**Package name**</span></span>                     | <span data-ttu-id="dbbc3-183">**Type**</span><span class="sxs-lookup"><span data-stu-id="dbbc3-183">**Type**</span></span>               | <span data-ttu-id="dbbc3-184">**説明**</span><span class="sxs-lookup"><span data-stu-id="dbbc3-184">**Description**</span></span>                                                                           |
|--------------------------------------|------------------------|-------------------------------------------------------------------------------------------|
| <span data-ttu-id="dbbc3-185">SRS v2-SRS アプリケーション パッケージ</span><span class="sxs-lookup"><span data-stu-id="dbbc3-185">SRS v2 - SRS Application Package</span></span>     | <span data-ttu-id="dbbc3-186">ソフトウェアパッケージ</span><span class="sxs-lookup"><span data-stu-id="dbbc3-186">Software package</span></span>       | <span data-ttu-id="dbbc3-187">Microsoft Teams Rooms 展開キット用のパッケージ</span><span class="sxs-lookup"><span data-stu-id="dbbc3-187">Package for the Microsoft Teams Rooms deployment kit</span></span>                                      |
| <span data-ttu-id="dbbc3-188">SRS v2-Sysprep パッケージ</span><span class="sxs-lookup"><span data-stu-id="dbbc3-188">SRS v2 - Sysprep Package</span></span>             | <span data-ttu-id="dbbc3-189">ソフトウェア パッケージ</span><span class="sxs-lookup"><span data-stu-id="dbbc3-189">Software package</span></span>       | <span data-ttu-id="dbbc3-190">Microsoft Teams Rooms ユニットを構成するための、カスタム Unattended.xml 用のパッケージ</span><span class="sxs-lookup"><span data-stu-id="dbbc3-190">Package for the custom Unattended.xml to configure Microsoft Teams Rooms units</span></span>            |
| <span data-ttu-id="dbbc3-191">SRS v2 - Set-SRSComputerName パッケージ</span><span class="sxs-lookup"><span data-stu-id="dbbc3-191">SRS v2 - Set-SRSComputerName Package</span></span> | <span data-ttu-id="dbbc3-192">ソフトウェア パッケージ</span><span class="sxs-lookup"><span data-stu-id="dbbc3-192">Software package</span></span>       | <span data-ttu-id="dbbc3-193">展開中にコンピューター名を割り当てる HTML アプリケーション (HTA) 用のパッケージ</span><span class="sxs-lookup"><span data-stu-id="dbbc3-193">Package for the HTML application (HTA) to assign a computer name during the deployment</span></span>    |
| <span data-ttu-id="dbbc3-194">SRS v2 - SRS のセットアップを構成する</span><span class="sxs-lookup"><span data-stu-id="dbbc3-194">SRS v2 - Configure SRS Setup</span></span>         | <span data-ttu-id="dbbc3-195">ソフトウェア パッケージ</span><span class="sxs-lookup"><span data-stu-id="dbbc3-195">Software package</span></span>       | <span data-ttu-id="dbbc3-196">Microsoft Teams Rooms アプリの展開を構成するためのパッケージ</span><span class="sxs-lookup"><span data-stu-id="dbbc3-196">Package to configure deployment of the Microsoft Teams Rooms app</span></span>                          |
| <span data-ttu-id="dbbc3-197">SRS v2 - OS アップデート パッケージ</span><span class="sxs-lookup"><span data-stu-id="dbbc3-197">SRS v2 - OS Updates Package</span></span>          | <span data-ttu-id="dbbc3-198">ソフトウェア パッケージ</span><span class="sxs-lookup"><span data-stu-id="dbbc3-198">Software package</span></span>       | <span data-ttu-id="dbbc3-199">必須のオペレーティング システム更新プログラムを展開するためのパッケージ</span><span class="sxs-lookup"><span data-stu-id="dbbc3-199">Package to deploy mandatory operating system updates</span></span>                                      |
| <span data-ttu-id="dbbc3-200">SRS v2 - ルート証明書パッケージ</span><span class="sxs-lookup"><span data-stu-id="dbbc3-200">SRS v2 - Root Certificate Package</span></span>    | <span data-ttu-id="dbbc3-201">ソフトウェア パッケージ</span><span class="sxs-lookup"><span data-stu-id="dbbc3-201">Software package</span></span>       | <span data-ttu-id="dbbc3-202">省略可能 -ルート証明書を展開するためのパッケージ (ドメインに参加しているユニットには必要ありません)</span><span class="sxs-lookup"><span data-stu-id="dbbc3-202">Optional - Package to deploy the root certificate (not required for domain-joined units)</span></span>  |
| <span data-ttu-id="dbbc3-203">SRS v2 - Microsoft Monitoring Agent パッケージ</span><span class="sxs-lookup"><span data-stu-id="dbbc3-203">SRS v2 - Microsoft Monitoring Agent Package</span></span> | <span data-ttu-id="dbbc3-204">ソフトウェア パッケージ</span><span class="sxs-lookup"><span data-stu-id="dbbc3-204">Software package</span></span>       | <span data-ttu-id="dbbc3-205">省略可能 - Microsoft Operations Management Suite エージェントを展開および構成するためのパッケージ</span><span class="sxs-lookup"><span data-stu-id="dbbc3-205">Optional - Package to deploy and configure the Microsoft Operations Management Suite agent</span></span>|
| <span data-ttu-id="dbbc3-206">SRS v2 - WinPE 背景パッケージ</span><span class="sxs-lookup"><span data-stu-id="dbbc3-206">SRS v2 - WinPE Background Package</span></span>    | <span data-ttu-id="dbbc3-207">ソフトウェア パッケージ</span><span class="sxs-lookup"><span data-stu-id="dbbc3-207">Software package</span></span>       | <span data-ttu-id="dbbc3-208">カスタム背景画像を使用して、ブート イメージに使用するためのパッケージ</span><span class="sxs-lookup"><span data-stu-id="dbbc3-208">Package for the custom background image to use with boot images</span></span>                           |
| <span data-ttu-id="dbbc3-209">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="dbbc3-209">Windows 10 Enterprise</span></span>                | <span data-ttu-id="dbbc3-210">オペレーティング システム イメージ</span><span class="sxs-lookup"><span data-stu-id="dbbc3-210">Operating system image</span></span> | <span data-ttu-id="dbbc3-211">オペレーティング システムのインストール ファイル用のパッケージ (install.wim)</span><span class="sxs-lookup"><span data-stu-id="dbbc3-211">Package for the operating system installation file (install.wim)</span></span>                          |
| <span data-ttu-id="dbbc3-212">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="dbbc3-212">Surface Pro</span></span>                          | <span data-ttu-id="dbbc3-213">ドライバー パッケージ</span><span class="sxs-lookup"><span data-stu-id="dbbc3-213">Driver package</span></span>         | <span data-ttu-id="dbbc3-214">Microsoft Surface Pro のデバイス ドライバーおよびファームウェア用のパッケージ</span><span class="sxs-lookup"><span data-stu-id="dbbc3-214">Package for the device drivers and firmware for Microsoft Surface Pro</span></span>                     |
| <span data-ttu-id="dbbc3-215">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="dbbc3-215">Surface Pro 4</span></span>                        | <span data-ttu-id="dbbc3-216">ドライバー パッケージ</span><span class="sxs-lookup"><span data-stu-id="dbbc3-216">Driver package</span></span>         | <span data-ttu-id="dbbc3-217">Microsoft Surface Pro 4 のデバイス ドライバーおよびファームウェア用のパッケージ</span><span class="sxs-lookup"><span data-stu-id="dbbc3-217">Package for the device drivers and firmware for Microsoft Surface Pro 4</span></span>                   |

<span data-ttu-id="dbbc3-218">詳細については、「[構成マネージャー内のパッケージとプログラム](/configmgr/apps/deploy-use/packages-and-programs)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-218">For more information, see [Packages and programs in Configuration Manager](/configmgr/apps/deploy-use/packages-and-programs).</span></span>

### <a name="create-folders-for-the-package-source-files"></a><span data-ttu-id="dbbc3-219">パッケージ ソース ファイル用のフォルダーを作成する</span><span class="sxs-lookup"><span data-stu-id="dbbc3-219">Create folders for the package source files</span></span>

<span data-ttu-id="dbbc3-220">構成マネージャーでは、最初に作成されたとき、および更新されたときに、パッケージのソース ファイルを特定のフォルダー構造に整理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-220">Configuration Manager requires package source files to be organized in a specific folder structure when they're first created and when they're updated.</span></span>

<span data-ttu-id="dbbc3-221">Microsoft Endpoint Configuration Manager のサーバーの全体管理サイトまたはプライマリ サイト、あるいはパッケージ ソース ファイルのホストに使用しているサーバー共有上で、次のフォルダー構造を作成します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-221">Create the following folder structure on the Microsoft Endpoint Configuration Manager central administration site or primary site, or on a server share you're using to host package source files:</span></span>

-   <span data-ttu-id="dbbc3-222">SRS v2 - Microsoft Monitoring Agent パッケージ</span><span class="sxs-lookup"><span data-stu-id="dbbc3-222">SRS v2 - Microsoft Monitoring Agent Package</span></span>
-   <span data-ttu-id="dbbc3-223">SRS v2 - OS アップデート パッケージ</span><span class="sxs-lookup"><span data-stu-id="dbbc3-223">SRS v2 - OS Updates Package</span></span>
-   <span data-ttu-id="dbbc3-224">SRS v2 - ルート証明書パッケージ</span><span class="sxs-lookup"><span data-stu-id="dbbc3-224">SRS v2 - Root Certificate Package</span></span>
-   <span data-ttu-id="dbbc3-225">SRS v2 - Set-SRSComputerName パッケージ</span><span class="sxs-lookup"><span data-stu-id="dbbc3-225">SRS v2 - Set-SRSComputerName Package</span></span>
-   <span data-ttu-id="dbbc3-226">SRS v2-SRS アプリケーション パッケージ</span><span class="sxs-lookup"><span data-stu-id="dbbc3-226">SRS v2 - SRS Application Package</span></span>
-   <span data-ttu-id="dbbc3-227">SRS v2 - SRS のセットアップを構成する</span><span class="sxs-lookup"><span data-stu-id="dbbc3-227">SRS v2 - Configure SRS Setup</span></span>
-   <span data-ttu-id="dbbc3-228">SRS v2-Sysprep パッケージ</span><span class="sxs-lookup"><span data-stu-id="dbbc3-228">SRS v2 - Sysprep Package</span></span>
-   <span data-ttu-id="dbbc3-229">ドライバー</span><span class="sxs-lookup"><span data-stu-id="dbbc3-229">Drivers</span></span>
    -   <span data-ttu-id="dbbc3-230">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="dbbc3-230">Surface Pro</span></span>
    -   <span data-ttu-id="dbbc3-231">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="dbbc3-231">Surface Pro 4</span></span>
-   <span data-ttu-id="dbbc3-232">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="dbbc3-232">Operating Systems</span></span>
    -   <span data-ttu-id="dbbc3-233">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="dbbc3-233">Windows 10 Enterprise</span></span>

> [!TIP]
> <span data-ttu-id="dbbc3-234">パッケージのフォルダー構造、使用する必要のあるスクリプト、インポートする必要のあるタスク シーケンス テンプレートを含む zip ファイルを、[ダウンロード](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)して使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-234">You may also [download](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) and use the zip file that includes the folder structure for the packages, the scripts that you need to use, and the task sequence template, that you need to import.</span></span>

### <a name="create-the-monitoring-agent-package"></a><span data-ttu-id="dbbc3-235">監視エージェント パッケージを作成する</span><span class="sxs-lookup"><span data-stu-id="dbbc3-235">Create the Monitoring agent package</span></span>

1. <span data-ttu-id="dbbc3-236"><https://go.microsoft.com/fwlink/?LinkId=828603> から監視エージェントをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-236">Download the Monitoring agent from <https://go.microsoft.com/fwlink/?LinkId=828603>.</span></span>

2. <span data-ttu-id="dbbc3-237">コマンド プロンプト ウィンドウを開き、コマンド プロンプトで **MMASetup-AMD64.exe /C:** と入力し、パッケージを **SRS v2 - Microsoft Monitoring Agent パッケージ** フォルダーに展開します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-237">Extract the package into the **SRS v2 - Microsoft Monitoring Agent Package** folder by opening a Command Prompt window and entering **MMASetup-AMD64.exe /C:**     at the command prompt.</span></span>

3. <span data-ttu-id="dbbc3-238">構成マネージャー コンソールから、[**ソフトウェアライブラリ**] \> [**アプリケーションの管理**] \> [**パッケージ**] に移動し、[**パッケージの作成**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-238">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4. <span data-ttu-id="dbbc3-239">パッケージを作成するには、次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-239">Enter the following information to create the package:</span></span>

   - <span data-ttu-id="dbbc3-240">名前<strong>: SRS v2 - Microsoft Monitoring Agent パッケージ</strong></span><span class="sxs-lookup"><span data-stu-id="dbbc3-240">Name<strong>: SRS v2 - Microsoft Monitoring Agent Package</strong></span></span>

   - <span data-ttu-id="dbbc3-241">製造元<strong>: Microsoft Corporation</strong></span><span class="sxs-lookup"><span data-stu-id="dbbc3-241">Manufacturer<strong>: Microsoft Corporation</strong></span></span>

   - <span data-ttu-id="dbbc3-242">バージョン<strong>: 8.1.11081.0</strong> (ダウンロードしたインストール ファイルのバージョンを入力してください)</span><span class="sxs-lookup"><span data-stu-id="dbbc3-242">Version<strong>: 8.1.11081.0</strong> (enter the version of the downloaded installation file)</span></span>

   - <span data-ttu-id="dbbc3-243">[**このパッケージには、ソース ファイルが含まれています**] のチェック ボックスを選択し、**SRS v2 - Microsoft Monitoring Agent パッケージ** フォルダーのパスを入力し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-243">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Microsoft Monitoring Agent Package** folder, and then select **Next**.</span></span>

5. <span data-ttu-id="dbbc3-244">[**プログラムを作成しない**] を選択し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-244">Select **Do not create a program**, and then select **Next**.</span></span>

6. <span data-ttu-id="dbbc3-245">[**設定の確認**] を確認して、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-245">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7. <span data-ttu-id="dbbc3-246">**[閉じる]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-246">Select **Close**.</span></span>

### <a name="create-the-operating-system-updates-package"></a><span data-ttu-id="dbbc3-247">オペレーティング システムの更新プログラム パッケージを作成する</span><span class="sxs-lookup"><span data-stu-id="dbbc3-247">Create the operating system updates package</span></span>

1. <span data-ttu-id="dbbc3-248">[**SRS v2 - OS 更新プログラムパッケージ**] フォルダーで、**Install-SRSv2-OS-Updates.ps1** という名前の新しい PowerShell スクリプトを作成します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-248">In the **SRS v2 - OS Updates Package** folder, create a new PowerShell script named **Install-SRSv2-OS-Updates.ps1**.</span></span>

2. <span data-ttu-id="dbbc3-249">次のスクリプトを **Install-SRSv2-OS-Updates.ps1** スクリプトにコピーします。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-249">Copy the script below into the **Install-SRSv2-OS-Updates.ps1** script.</span></span> <span data-ttu-id="dbbc3-250">または、[ここ](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)から Install-SRSv2-OS-Updates.ps1 スクリプトをダウンロードすることもできます。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-250">Alternatively, you can download the Install-SRSv2-OS-Updates.ps1 script from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
   ```
   # Install-SRSv2-OS-Updates.ps1
   $strPath = split-path -parent $MyInvocation.MyCommand.Definition
   $total = gci $strPath *.msu | measure | Select-Object -expand Count
   $i = 0
   gci $strPath *.msu | ForEach-Object {
     $i++
     WUSA ""$_.FullName /quiet /norestart""
     Write-Progress -activity "Applying Mandatory Updates" -status "Installing
     $_ .. $i of $total" -percentComplete (($i / $total) * 100)
     Wait-Process -name wusa
   }
   ```
3. <span data-ttu-id="dbbc3-251">必須の Windows Update パッケージを、同じフォルダーにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-251">Download the mandatory Windows Update packages into the same folder.</span></span>
   > [!NOTE]
   > <span data-ttu-id="dbbc3-252">この記事が公開された時点では、 [の KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) のみが必要でした。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-252">At the time this article was published, only [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) was required.</span></span> <span data-ttu-id="dbbc3-253">[[Microsoft Teams Rooms コンソールを構成する](console.md)] を確認し、他の更新プログラムが必要かどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-253">Check [Configure a Microsoft Teams Rooms console](console.md), to see whether any other updates are required.</span></span>

4. <span data-ttu-id="dbbc3-254">構成マネージャー コンソールから、[**ソフトウェアライブラリ**] \> [**アプリケーションの管理**] \> [**パッケージ**] に移動し、[**パッケージの作成**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-254">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

5. <span data-ttu-id="dbbc3-255">パッケージを作成するには、次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-255">Enter the following information to create the package:</span></span>
   -   <span data-ttu-id="dbbc3-256">名前: **SRS v2 – OS 更新プログラムパッケージ**</span><span class="sxs-lookup"><span data-stu-id="dbbc3-256">Name: **SRS v2 – OS Updates Package**</span></span>
   -   <span data-ttu-id="dbbc3-257">製造元: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="dbbc3-257">Manufacturer: **Microsoft Corporation**</span></span>
   -   <span data-ttu-id="dbbc3-258">バージョン: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="dbbc3-258">Version: **1.0.0**</span></span>
   -   <span data-ttu-id="dbbc3-259">[**このパッケージには、ソース ファイルが含まれています**] のチェック ボックスを選択し、**SRS v2 - OS 更新プログラム パッケージ** フォルダーのパスを入力し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-259">Select the **This package contains source files** check box, enter the path to the **SRS v2 - OS Updates Package** folder, and then select **Next**.</span></span>

6. <span data-ttu-id="dbbc3-260">[**プログラムを作成しない**] を選択し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-260">Select **Do not create a program**, and then select **Next**.</span></span>

7. <span data-ttu-id="dbbc3-261">[**設定の確認**] を確認して、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-261">Review the **Confirm the settings** page, and then select **Next**.</span></span>

8. <span data-ttu-id="dbbc3-262">**[閉じる]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-262">Select **Close**.</span></span>

### <a name="create-the-root-certificate-package-optional"></a><span data-ttu-id="dbbc3-263">ルート証明書パッケージを作成する (省略可能)</span><span class="sxs-lookup"><span data-stu-id="dbbc3-263">Create the root certificate package (optional)</span></span>

<span data-ttu-id="dbbc3-264">このパッケージを作成して、Active Directory ドメインに参加しないデバイスのルート証明書を配布します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-264">You create this package to distribute the root certificate for devices that won't be joined to an Active Directory domain.</span></span> <span data-ttu-id="dbbc3-265">次の両方の条件が該当する場合にのみ、このパッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-265">Create this package only if both the following conditions apply:</span></span>
-   <span data-ttu-id="dbbc3-266">展開には、オンプレミスの Lync または Skype for Business サーバーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-266">Your deployment includes on-premises Lync or Skype for Business Server.</span></span>
-   <span data-ttu-id="dbbc3-267">Microsoft Teams Rooms ユニットは、ドメイン メンバーの代わりにワーク グループで動作するように構成されています。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-267">Microsoft Teams Rooms units are configured to work in a workgroup instead of a domain member.</span></span>

1.  <span data-ttu-id="dbbc3-268">ルート証明書を **SRS v2 –ルート証明書パッケージ** フォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-268">Copy the root certificate into the **SRS v2 – Root Certificate Package** folder.</span></span>

2.  <span data-ttu-id="dbbc3-269">構成マネージャー コンソールから、[**ソフトウェアライブラリ**] \> [**アプリケーションの管理**] \> [**パッケージ**] に移動し、[**パッケージの作成**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-269">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

3.  <span data-ttu-id="dbbc3-270">パッケージを作成するには、次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-270">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="dbbc3-271">名前: **SRS v2 –ルート証明書パッケージ**</span><span class="sxs-lookup"><span data-stu-id="dbbc3-271">Name: **SRS v2 – Root Certificate Package**</span></span>
    -   <span data-ttu-id="dbbc3-272">製造元: *組織の名前*</span><span class="sxs-lookup"><span data-stu-id="dbbc3-272">Manufacturer: *Your organization's name*</span></span>
    -   <span data-ttu-id="dbbc3-273">バージョン: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="dbbc3-273">Version: **1.0.0**</span></span>
    -   <span data-ttu-id="dbbc3-274">[**このパッケージには、ソース ファイルが含まれています**] のチェック ボックスを選択し、**SRS v2 - ルート証明書パッケージ** フォルダーのパスを入力し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-274">Select the **This package contains source files** check box, enter the path to the **SRS v2 – Root Certificate Package** folder, and then select **Next**.</span></span>

4.  <span data-ttu-id="dbbc3-275">[**プログラムを作成しない**] を選択し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-275">Select **Do not create a program**, and then select **Next**.</span></span>

5.  <span data-ttu-id="dbbc3-276">[**設定の確認**] を確認して、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-276">Review the **Confirm the settings** page, and then select **Next**.</span></span>

6.  <span data-ttu-id="dbbc3-277">**[閉じる]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-277">Select **Close**.</span></span>

### <a name="create-the-microsoft-teams-rooms-deployment-kit-package"></a><span data-ttu-id="dbbc3-278">Microsoft Teams Rooms 展開キット パッケージの作成</span><span class="sxs-lookup"><span data-stu-id="dbbc3-278">Create the Microsoft Teams Rooms deployment kit package</span></span>

1.  <span data-ttu-id="dbbc3-279"><https://go.microsoft.com/fwlink/?linkid=851168>から最新バージョンの **Microsoft Teams Rooms 展開キット** をダウンロードし、ワークステーションにインストールします。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-279">Download the latest version of the **Microsoft Teams Rooms deployment kit** from <https://go.microsoft.com/fwlink/?linkid=851168>, and install it to a workstation.</span></span>

2.  <span data-ttu-id="dbbc3-280">**C:\\Program Files (x86)\\ Skype ミーティング システム展開キット** の内容を、**SRS v2 - SRS アプリケーション パッケージ** フォルダにコピーします。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-280">Copy the content from **C:\\Program Files (x86)\\Skype Room System Deployment Kit** to the **SRS v2 - SRS Application Package** folder.</span></span>

3.  <span data-ttu-id="dbbc3-281">構成マネージャー コンソールから、[**ソフトウェアライブラリ**] \> [**アプリケーションの管理**] \> [**パッケージ**] に移動し、[**パッケージの作成**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-281">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="dbbc3-282">パッケージを作成するには、次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-282">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="dbbc3-283">名前: **SRS v2 – SRS アプリケーション パッケージ**</span><span class="sxs-lookup"><span data-stu-id="dbbc3-283">Name: **SRS v2 – SRS Application Package**</span></span>
    -   <span data-ttu-id="dbbc3-284">製造元: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="dbbc3-284">Manufacturer: **Microsoft Corporation**</span></span>
    -   <span data-ttu-id="dbbc3-285">バージョン: **3.1.104.0** (ダウンロードしたインストールファイルのバージョンを入力してください)</span><span class="sxs-lookup"><span data-stu-id="dbbc3-285">Version: **3.1.104.0** (enter the version of the downloaded installation file)</span></span>
    -   <span data-ttu-id="dbbc3-286">[**このパッケージには、ソース ファイルが含まれています**] のチェック ボックスを選択し、**SRS v2 - SRS アプリケーション パッケージ** フォルダーのパスを入力し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-286">Select the **This package contains source files** check box, enter the path to the **SRS v2 – SRS Application Package** folder, and then select **Next**.</span></span>
5.  <span data-ttu-id="dbbc3-287">[**プログラムを作成しない**] を選択し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-287">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="dbbc3-288">[**設定の確認**] を確認して、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-288">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="dbbc3-289">**[閉じる]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-289">Select **Close**.</span></span>

### <a name="create-the-computer-name-assignment-package"></a><span data-ttu-id="dbbc3-290">コンピューター名の割り当てパッケージを作成する</span><span class="sxs-lookup"><span data-stu-id="dbbc3-290">Create the computer name assignment package</span></span>

1.  <span data-ttu-id="dbbc3-291">**SRS v2 - Set-SRSComputerName パッケージ** フォルダーで **Set-SRSComputerName.hta** という名前の新しい HTML アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-291">In the **SRS v2 - Set-SRSComputerName Package** folder, create a new HTML application named **Set-SRSComputerName.hta** .</span></span>

2.  <span data-ttu-id="dbbc3-292">**Set-SRSComputerName.hta** ファイルに次のスクリプトをコピーします。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-292">Copy the following script into the **Set-SRSComputerName.hta** file.</span></span> <span data-ttu-id="dbbc3-293">または、[ここ](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)から Set-SRSComputerName.hta ファイルをダウンロードすることもできます。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-293">Alternatively, you can download the Set-SRSComputerName.hta file from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
    ```HTML
    <!DOCTYPE HTML>
    <html>
    <head>
    <title>Set SRS Computer Name</title>
    <HTA:APPLICATION
      APPLICATIONNAME="Set SRS Computer Name"
      ID="SetSRSComputerName"
      VERSION="1.0"
      SCROLL="no"
      SINGLEINSTANCE="yes"
      WINDOWSTATE="maximize"
      MaximizeButton="no"
      MinimizeButton="no"
      SysMenu="no"
      ShowInTaskbar="no"
      Caption="no"
      />
    <style type="text/css">
    body {
        background-color: #fdfeff;
        color: darkblue;
        font-family: Calibri;
        font-size: 12pt;
        margin: 4em 3em;
    }
    </style>
    </head>
    <script language="VBScript">
    Public strNewComputerName
    Sub GenerateComputerName()
        strComputer = "."
        Set objWMIService = GetObject("winmgmts:\\" & strComputer & "\root\cimv2")
        Set colItems = objWMIService.ExecQuery("Select * from Win32_BIOS",,48)
        For Each objItem in colItems
            strSerialNumber = objItem.SerialNumber
        Next
        strNewComputerName = "SRS-"  & right(replace(strSerialNumber, "-","") ,10)
        TextArea1.innerHTML = "The serial number of the device: " & strSerialNumber
        strHTMLText = strHTMLText & "<br> Computer name to be assigned: <font color = red>" & strNewComputerName & "</font>"
        strHTMLText = strHTMLText & "<br><br> Click Accept to use this as the computer name and continue deployment, or Change to set a new name."
        strHTMLText = strHTMLText & "<p><input type=""button"" value=""Accept"" name = ""Accept_Button"" onclick=""SetComputerName"" />"
        strHTMLText = strHTMLText & " <input type=""button"" value=""Change"" name = ""Change_Button"" onclick=""ChangeComputerName"" />"
        TextArea2.innerHTML = strHTMLText
    End Sub

    Sub SetComputerName()
        dim result
        result = MsgBox("Computer Name to be assigned: " & strNewComputerName &vbcrlf & "Are you sure you want to continue?", 36)
        If (result = vbYes) then
            SET env = CreateObject("Microsoft.SMS.TSEnvironment")
            env("OSDComputerName") = strNewComputerName
            self.close
        elseif (result = vbNo) then
            Window_OnLoad
        End If
    End Sub

    Sub UpdateComputerName()
        strNewComputerName = newcomputername.value
        if len(trim(strNewComputerName)) = 0 then
            MsgBox "Computer name cannot be empty." &vbcrlf & "Update and try again.",16
            exit sub
        end if
        SetComputerName
    End Sub

    Sub ChangeComputerName()
        TextArea2.innerHTML = "<p>Type the new computer name and click Accept:  <input type=""text"" name=""newcomputername"" value =" & strNewComputerName & " />"
        TextArea2.innerHTML = TextArea2.innerHTML & "<br><input type=""button"" value=""Update"" name = ""Update_Button"" onclick=""UpdateComputerName"" />"
    End Sub

    Sub Window_OnLoad
        Set oTSProgressUI = CreateObject("Microsoft.SMS.TsProgressUI")
        oTSProgressUI.CloseProgressDialog
        GenerateComputerName
    End Sub
    </script>

    <body>
    <span id = "TextArea1"></span>
    <span id = "TextArea2">
    </span>
    </body>
    </html>

    ```
3.  <span data-ttu-id="dbbc3-294">構成マネージャー コンソールから、[**ソフトウェアライブラリ**] \> [**アプリケーションの管理**] \> [**パッケージ**] に移動し、[**パッケージの作成**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-294">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="dbbc3-295">パッケージを作成するには、次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-295">Enter the following information to create the package:</span></span>

    -   <span data-ttu-id="dbbc3-296">名前: **SRS v2 - Set-SRSComputerName パッケージ**</span><span class="sxs-lookup"><span data-stu-id="dbbc3-296">Name: **SRS v2 - Set-SRSComputerName Package**</span></span>

    -   <span data-ttu-id="dbbc3-297">製造元: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="dbbc3-297">Manufacturer: **Microsoft Corporation**</span></span>

    -   <span data-ttu-id="dbbc3-298">バージョン: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="dbbc3-298">Version: **1.0.0**</span></span>

    -   <span data-ttu-id="dbbc3-299">[**このパッケージには、ソース ファイルが含まれています**] のチェック ボックスを選択し、**SRS v2 - Set-SRSComputerName パッケージ** フォルダーのパスを入力し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-299">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Set-SRSComputerName Package** folder, and then select **Next**.</span></span>

5.  <span data-ttu-id="dbbc3-300">[**プログラムを作成しない**] を選択し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-300">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="dbbc3-301">[**設定の確認**] を確認して、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-301">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="dbbc3-302">**[閉じる]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-302">Select **Close**.</span></span>

### <a name="create-the-sysprep-package"></a><span data-ttu-id="dbbc3-303">Sysprep パッケージを作成する</span><span class="sxs-lookup"><span data-stu-id="dbbc3-303">Create the Sysprep package</span></span>

1. <span data-ttu-id="dbbc3-304">**SRS v2 – Sysprep パッケージ** フォルダーで、**Unattend.xml** という名前の新しい XML ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-304">In the **SRS v2 – Sysprep Package** folder, create a new XML file named **Unattend.xml** .</span></span>

2. <span data-ttu-id="dbbc3-305">**Unattend.xml** ファイルに次のテキストをコピーします。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-305">Copy the following text into the **Unattend.xml** file.</span></span> <span data-ttu-id="dbbc3-306">または、[ここ](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)から Unattend.xml ファイルをダウンロードすることもできます。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-306">Alternatively, you can download the Unattend.xml file from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
   ```XML
   <?xml version="1.0" encoding="utf-8"?>
   <unattend xmlns="urn:schemas-microsoft-com:unattend">
   <settings pass="specialize">
       <component name="Microsoft-Windows-Embedded-BootExp" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="NonSxS" xmlns:wcm="https://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
           <DisableBootMenu>1</DisableBootMenu>
           <DisplayDisabled>1</DisplayDisabled>
       </component>
       <component name="Microsoft-Windows-powercpl" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="https://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
           <PreferredPlan>8c5e7fda-e8bf-4a96-9a85-a6e23a8c635c</PreferredPlan>
       </component>
   </settings>
   <settings pass="oobeSystem">
       <component name="Microsoft-Windows-Shell-Setup" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="https://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
           <OOBE>
               <HideEULAPage>true</HideEULAPage>
               <HideLocalAccountScreen>true</HideLocalAccountScreen>
               <HideOEMRegistrationScreen>true</HideOEMRegistrationScreen>
               <HideOnlineAccountScreens>true</HideOnlineAccountScreens>
               <HideWirelessSetupInOOBE>true</HideWirelessSetupInOOBE>
               <SkipMachineOOBE>true</SkipMachineOOBE>
               <SkipUserOOBE>true</SkipUserOOBE>
               <ProtectYourPC>1</ProtectYourPC>
           </OOBE>
           <AutoLogon>
               <Enabled>true</Enabled>
               <Username>Skype</Username>
               <Password>
                   <Value>UABhAHMAcwB3AG8AcgBkAA==</Value>
                   <PlainText>false</PlainText>
               </Password>
           </AutoLogon>
           <UserAccounts>
               <LocalAccounts>
                   <LocalAccount wcm:action="add">
                       <Password>
                           <Value>cwBmAGIAUABhAHMAcwB3AG8AcgBkAA==</Value>
                           <PlainText>false</PlainText>
                       </Password>
                       <Name>Admin</Name>
                       <Group>Administrators</Group>
                       <DisplayName>Administrator</DisplayName>
                       <Description>Administrator</Description>
                   </LocalAccount>
               </LocalAccounts>
           </UserAccounts>
       </component>
   </settings>
   <cpi:offlineImage cpi:source="wim:h:/install.wim#Windows 10 Enterprise" xmlns:cpi="urn:schemas-microsoft-com:cpi" />
   </unattend>
   ```
3. <span data-ttu-id="dbbc3-307">構成マネージャー コンソールから、[**ソフトウェアライブラリ**] \> [**アプリケーションの管理**] \> [**パッケージ**] に移動し、[**パッケージの作成**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-307">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4. <span data-ttu-id="dbbc3-308">パッケージを作成するには、次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-308">Enter the following information to create the package:</span></span>
   -   <span data-ttu-id="dbbc3-309">名前: **SRS v2-Sysprep パッケージ**</span><span class="sxs-lookup"><span data-stu-id="dbbc3-309">Name: **SRS v2 - Sysprep Package**</span></span>
   -   <span data-ttu-id="dbbc3-310">製造元: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="dbbc3-310">Manufacturer: **Microsoft Corporation**</span></span>
   -   <span data-ttu-id="dbbc3-311">バージョン: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="dbbc3-311">Version: **1.0.0**</span></span>
   -   <span data-ttu-id="dbbc3-312">[**このパッケージには、ソース ファイルが含まれています**] のチェック ボックスを選択し、**SRS v2 - Sysprep パッケージ** フォルダーのパスを入力し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-312">Select the **This package contains source files** check box, enter the path to the **SRS v2 – Sysprep Package** folder, and then select **Next**.</span></span>
5. <span data-ttu-id="dbbc3-313">[**プログラムを作成しない**] を選択し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-313">Select **Do not create a program**, and then select **Next**.</span></span>

6. <span data-ttu-id="dbbc3-314">[**設定の確認**] を確認して、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-314">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7. <span data-ttu-id="dbbc3-315">**[閉じる]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-315">Select **Close**.</span></span>

### <a name="create-the-windows-10-enterprise-package"></a><span data-ttu-id="dbbc3-316">Windows 10 Enterprise パッケージを作成する</span><span class="sxs-lookup"><span data-stu-id="dbbc3-316">Create the Windows 10 Enterprise package</span></span>

1.  <span data-ttu-id="dbbc3-317">Windows 10 Enterprise x64 メディアを取得して、**install.wim** ファイルを **オペレーティング システム \\Windows 10 Enterprise** フォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-317">Obtain a Windows 10 Enterprise x64 media, and copy the **install.wim** file to the **Operating Systems\\Windows 10 Enterprise** folder.</span></span>

2.  <span data-ttu-id="dbbc3-318">構成マネージャー コンソールから、[**ソフトウェア ライブラリ**] \> [**オペレーティングシステム**] \> [**オペレーティング システム イメージ**] に移動し、[**オペレーティング システム イメージを追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-318">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Operating System Images**, and then select **Add Operating System Image**.</span></span>

3.  <span data-ttu-id="dbbc3-319">コピーした **install.wim** ファイルのパスを指定し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-319">Specify the path to the **install.wim** file you just copied, and then select **Next**.</span></span>

4.  <span data-ttu-id="dbbc3-320">[**バージョン**] フィールドを更新して、Windows 10 Enterprise のビルド番号と一致するようにし、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-320">Update the **Version** field to match the build number of the Windows 10 Enterprise image, and then select **Next**.</span></span>

5.  <span data-ttu-id="dbbc3-321">[**詳細**] ページを確認し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-321">Review the **Details** page, and then select **Next**.</span></span>

6.  <span data-ttu-id="dbbc3-322">**[閉じる]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-322">Select **Close**.</span></span>

<span data-ttu-id="dbbc3-323">詳細については、[「構成マネージャーを使用して OS イメージを管理する」](/configmgr/osd/get-started/manage-operating-system-images)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-323">For more information, see [Manage OS images with Configuration Manager](/configmgr/osd/get-started/manage-operating-system-images).</span></span>

### <a name="create-surface-pro-device-driver-packages"></a><span data-ttu-id="dbbc3-324">Surface Pro デバイス ドライバー パッケージの作成</span><span class="sxs-lookup"><span data-stu-id="dbbc3-324">Create Surface Pro device driver packages</span></span>

<span data-ttu-id="dbbc3-325">Microsoft Teams Rooms は Surface Pro と Surface Pro 4 の両方でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-325">Microsoft Teams Rooms is supported for both Surface Pro and Surface Pro 4.</span></span> <span data-ttu-id="dbbc3-326">環境内にある Surface Pro のモデルごとに、ドライバー パッケージを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-326">You need to create a driver package for each Surface Pro model you have in your environment.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dbbc3-327">ドライバーは、Windows 10 Enterprise ビルドおよび Microsoft Teams Rooms 展開キットのバージョンと互換性がある必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-327">The drivers must be compatible with the Windows 10 Enterprise build and the Microsoft Teams Rooms deployment kit version.</span></span> <span data-ttu-id="dbbc3-328">詳細については、[「Surface デバイス用の最新のファームウェアとドライバーをダウンロードする」](/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) および [「コンソールを構成する」](console.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-328">For more information, see [Download the latest firmware and drivers for Surface devices](/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) and [Configure a console](console.md).</span></span>

1.  <span data-ttu-id="dbbc3-329">最新のドライバーとファームウェアをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-329">Download the latest drivers and firmware.</span></span>
    -   <span data-ttu-id="dbbc3-330">Surface Pro 用: <https://www.microsoft.com/download/details.aspx?id=55484></span><span class="sxs-lookup"><span data-stu-id="dbbc3-330">For Surface Pro: <https://www.microsoft.com/download/details.aspx?id=55484></span></span>
    -   <span data-ttu-id="dbbc3-331">Surface Pro 4 用: <https://www.microsoft.com/download/details.aspx?id=49498></span><span class="sxs-lookup"><span data-stu-id="dbbc3-331">For Surface Pro 4: <https://www.microsoft.com/download/details.aspx?id=49498></span></span>

2.  <span data-ttu-id="dbbc3-332">ダウンロードしたドライバーおよびファームウェアを抽出します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-332">Extract the downloaded driver and firmware.</span></span> <span data-ttu-id="dbbc3-333">コマンド プロンプト ウインドウを開き、コマンド プロンプトで次のいずれかのコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-333">Open a Command Prompt window and at the command prompt, enter one of the following commands:</span></span>
    -   `msiexec /a C:\SurfacePro_Win10.msi /passive TARGETDIR="C:\_Sources\Drivers\Surface Pro"`
    -   `msiexec /a C:\SurfacePro4_Win10.msi /passive TARGETDIR="C:\_Sources\Drivers\Surface Pro 4"`

3.  <span data-ttu-id="dbbc3-334">構成マネージャー コンソールで、[**ソフトウェアライブラリ**] \> [**オペレーティングシステム**] \> [**ドライバー**] に移動し、[**ドライバーのインポート**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-334">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Drivers**, and then select **Import Driver**.</span></span>

4.  <span data-ttu-id="dbbc3-335">[**次のネットワーク パス (UNC) にあるすべてのドライバーをインポート**] を選択し、ソース フォルダーを選択します (例: C:\\_Sources\\ドライバー\\Surface Pro)。そして [ **次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-335">Select **Import all drivers in the following network path (UNC)**, select the source folder (for example, C:\\_Sources\\Drivers\\Surface Pro), and then select **Next**.</span></span>

5.  <span data-ttu-id="dbbc3-336">[**インポートされたドライバーの詳細を指定する**] のページで、一覧表示されているすべてのドライバーを選択し、[**これらのドライバーを有効にして、コンピューターにインストールできるようにする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-336">On the **Specify the details for the imported drivers** page, select all the listed drivers, and then select **Enable these drivers and allow computers to install them**.</span></span>

6.  <span data-ttu-id="dbbc3-337">[**カテゴリ**] を選択し、Surface のモデルと一致する新しいカテゴリを作成し、[**OK**] を選択し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-337">Select **Categories**, create a new category that matches the Surface model, select **OK**, and then select **Next**.</span></span>

7.  <span data-ttu-id="dbbc3-338">**[新しいパッケージ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-338">Select **New Package**.</span></span>

8.  <span data-ttu-id="dbbc3-339">Surface Pro のモデルと一致するパッケージ名を指定し、ドライバー パッケージ ファイルを格納するフォルダーのパスを入力して、[**OK**] を選択し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-339">Specify the package name that matches the Surface Pro model, enter a folder path to store the driver package files in, select **OK**, and then select **Next**.</span></span>

9.  <span data-ttu-id="dbbc3-340">[**ブート イメージ**] のページで、ブート イメージが選択されていないことを確認してから、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-340">On the **boot images** page, ensure that no boot images are selected, and then select **Next**.</span></span>

10. <span data-ttu-id="dbbc3-341">**[閉じる]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-341">Select **Close**.</span></span>

11. <span data-ttu-id="dbbc3-342">[**ソフトウェア ライブラリ**] \> [**オペレーティング システム**] \> [**ドライバー**] フォルダーに移動し、[**フォルダー \> フォルダーの作成**] を選択し、ドライバーをインポートした Surface Pro のモデルと一致するフォルダー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-342">Go to **Software Library** \> **Operating Systems** \> **Drivers**, select **Folder \> Create Folder**, and enter a folder name that matches the Surface Pro model that you just imported the drivers for.</span></span>

12. <span data-ttu-id="dbbc3-343">インポートされたすべてのドライバーを新たに作成したフォルダーに移動すると、操作が簡単になります。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-343">Move all the imported drivers to the newly created folder for easier navigation and operation.</span></span>

> [!NOTE]
> <span data-ttu-id="dbbc3-344">他の Surface Pro のモデルにも同じ手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-344">Repeat the same steps for other Surface Pro models you might have.</span></span> <span data-ttu-id="dbbc3-345">詳細については、[「構成マネージャーでドライバーを管理する」](/configmgr/osd/get-started/manage-drivers) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-345">For more information, see [Manage drivers in Configuration Manager](/configmgr/osd/get-started/manage-drivers).</span></span>

### <a name="create-microsoft-teams-rooms-configuration-package"></a><span data-ttu-id="dbbc3-346">Microsoft Teams Rooms 構成パッケージの作成</span><span class="sxs-lookup"><span data-stu-id="dbbc3-346">Create Microsoft Teams Rooms Configuration Package</span></span>

1.  <span data-ttu-id="dbbc3-347">構成マネージャー コンソールから、[**ソフトウェアライブラリ**] \> [**アプリケーションの管理**] \> [**パッケージ**] に移動し、[**パッケージの作成**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-347">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

2.  <span data-ttu-id="dbbc3-348">パッケージを作成するには、次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-348">Enter the following information to create the package:</span></span>

    -   <span data-ttu-id="dbbc3-349">名前: **SRS v2 - SRS セットアップパッケージを構成する**</span><span class="sxs-lookup"><span data-stu-id="dbbc3-349">Name: **SRS v2 - Configure SRS Setup Package**</span></span>

    -   <span data-ttu-id="dbbc3-350">製造元: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="dbbc3-350">Manufacturer: **Microsoft Corporation**</span></span>

    -   <span data-ttu-id="dbbc3-351">バージョン: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="dbbc3-351">Version: **1.0.0**</span></span>

    -   <span data-ttu-id="dbbc3-352">[**このパッケージには、ソース ファイルが含まれています**] のチェック ボックスを選択し、**SRS v2 - SRS セットアップの構成** フォルダーのパスを入力し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-352">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Configure SRS Setup** folder, and then select **Next**.</span></span>

3.  <span data-ttu-id="dbbc3-353">[**プログラムを作成しない**] を選択し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-353">Select **Do not create a program**, and then select **Next**.</span></span>

4.  <span data-ttu-id="dbbc3-354">[**設定の確認**] を確認して、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-354">Review the **Confirm the settings** page, and then select **Next**.</span></span>

5.  <span data-ttu-id="dbbc3-355">**[閉じる]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-355">Select **Close**.</span></span>



## <a name="distribute-configuration-manager-packages"></a><span data-ttu-id="dbbc3-356">構成マネージャー パッケージの配布</span><span class="sxs-lookup"><span data-stu-id="dbbc3-356">Distribute Configuration Manager packages</span></span>

<span data-ttu-id="dbbc3-357">すべてのパッケージを、構成マネージャーの階層の配布ポイントの役割が割り当てられているサーバーに配布する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-357">All the packages must be distributed to the servers that have been assigned the distribution point role in the Configuration Manager hierarchy.</span></span> <span data-ttu-id="dbbc3-358">パッケージの配布を開始するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-358">Follow the instructions below to initiate package distribution.</span></span>

1.  <span data-ttu-id="dbbc3-359">ソフトウェアパッケージを配布します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-359">Distribute software packages.</span></span>

    1.  <span data-ttu-id="dbbc3-360">構成マネージャー コンソールで、 [**ソフトウェアライブラリ**] \> [**アプリケーション管理**] \> [**パッケージ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-360">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**.</span></span> <span data-ttu-id="dbbc3-361">配布するソフトウェアパッケージをすべて選択し、[**コンテンツの配布**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-361">Select all the software packages you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="dbbc3-362">パッケージのリストを確認し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-362">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="dbbc3-363">すべての配布ポイントサーバー (または、構成マネージャーの階層によっては、配布ポイントグループ) を一覧に追加し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-363">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="dbbc3-364">[**OK**] を選択し、[**閉じる**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-364">Select **Next**, and then select **Close**.</span></span>

2.  <span data-ttu-id="dbbc3-365">ドライバー パッケージを配布します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-365">Distribute driver packages.</span></span>

    1.  <span data-ttu-id="dbbc3-366">構成マネージャー コンソールで、[**ソフトウェア ライブラリ**] \> [**オペレーティング システム**] \> [**ドライバー パッケージ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-366">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Driver Packages**.</span></span> <span data-ttu-id="dbbc3-367">配布したいすべてのドライバーパッケージを選択し、[**コンテンツの配布**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-367">Select all the driver packages you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="dbbc3-368">パッケージのリストを確認し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-368">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="dbbc3-369">すべての配布ポイントサーバー (または、構成マネージャーの階層によっては、配布ポイントグループ) を一覧に追加し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-369">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="dbbc3-370">[**OK**] を選択し、[**閉じる**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-370">Select **Next**, and then select **Close**.</span></span>

3.  <span data-ttu-id="dbbc3-371">オペレーティング システム パッケージを配布します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-371">Distribute operating system packages.</span></span>

    1.  <span data-ttu-id="dbbc3-372">構成マネージャー コンソールで、[**ソフトウェア ライブラリ**] \> [**オペレーティングシステム**] \> [**オペレーティング システム イメージ**] に移動します。。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-372">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Operating System Images**.</span></span> <span data-ttu-id="dbbc3-373">配布したいすべてのオペレーティング システム イメージを選択し、[**コンテンツの配布**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-373">Select all the operating system images you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="dbbc3-374">パッケージのリストを確認し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-374">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="dbbc3-375">すべての配布ポイントサーバー (または、構成マネージャーの階層によっては、配布ポイントグループ) を一覧に追加し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-375">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="dbbc3-376">[**OK**] を選択し、[**閉じる**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-376">Select **Next**, and then select **Close**.</span></span>

> [!NOTE]
> <span data-ttu-id="dbbc3-377">パッケージの配布には、パッケージサイズ、構成マネージャーの階層、配布ポイント サーバーの数、およびネットワークで使用可能な帯域幅によって、時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-377">Package distribution might take some time, depending on the package size, Configuration Manager hierarchy, number of distribution point servers, and the bandwidth available in your network.</span></span>
> 
> <span data-ttu-id="dbbc3-378">Microsoft Teams Rooms の展開を開始する前に、すべてのパッケージを配布する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-378">All the packages must be distributed before you can start deploying a Microsoft Teams Rooms unit.</span></span>
> 
> <span data-ttu-id="dbbc3-379">構成マネージャー コンソールでパッケージ配布の状態を確認するには、 [**監視**] \> [**配布状態**] \> [**コンテンツの状態**] に進みます。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-379">You can review the status of your package distribution in the Configuration Manager console by going to **Monitoring** \> **Distribution Status** \> **Content Status**.</span></span>

## <a name="configuration-manager-task-sequences"></a><span data-ttu-id="dbbc3-380">構成マネージャーのタスク シーケンス</span><span class="sxs-lookup"><span data-stu-id="dbbc3-380">Configuration Manager task sequences</span></span>

<span data-ttu-id="dbbc3-381">構成マネージャーでタスク シーケンスを使用して、オペレーティング システム イメージを対象のコンピューターに展開する手順を自動化します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-381">You use task sequences with Configuration Manager to automate the steps for deploying an operating system image to a destination computer.</span></span> <span data-ttu-id="dbbc3-382">Microsoft Teams Rooms ユニットを自動で展開するには、対象の Microsoft Teams Rooms コンピューターの起動に使用したブート イメージ、インストールする Windows 10 Enterprise オペレーティング システム イメージ、およびその他のアプリケーションやソフトウェアアップデートなどの追加コンテンツを参照するタスク シーケンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-382">To deploy a Microsoft Teams Rooms unit in an automated fashion, you create a task sequence that references the boot image used to start the destination Microsoft Teams Rooms computer, the Windows 10 Enterprise operating system image that you want to install, and any other additional content, such as other applications or software updates.</span></span>

### <a name="import-the-sample-task-sequence"></a><span data-ttu-id="dbbc3-383">サンプル タスク シーケンスをインポートする</span><span class="sxs-lookup"><span data-stu-id="dbbc3-383">Import the sample task sequence</span></span>

<span data-ttu-id="dbbc3-384">サンプル タスク シーケンスをダウンロードして簡単にインポートし、必要に応じてカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-384">You can download and easily import a sample task sequence and customize it to meet your needs.</span></span>

1.  <span data-ttu-id="dbbc3-385">サンプル タスク シーケンスを [**ダウンロード**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)し、共有の場所にダウンロードした zip ファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-385">[**Download**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) the sample task sequence, and copy the downloaded zip file to a shared location.</span></span>
2.  <span data-ttu-id="dbbc3-386">構成マネージャー コンソールで、 [**ソフトウェア ライブラリ**] \> [**オペレーティングシステム**] \> [**タスクシーケンス**] に移動し、[**インポート タスク シーケンス**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-386">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Task Sequences**, and then select **Import Task Sequence**.</span></span>

3.  <span data-ttu-id="dbbc3-387">[**参照**] を選択して、手順 1 で使用した共有フォルダーの場所に移動し、**Microsoft Teams Rooms の展開 (EN-US).zip** ファイルを選択し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-387">Select **Browse**, go to the shared folder location you used in step 1, select the **Microsoft Teams Rooms Deployment (EN-US).zip** file, and then select **Next**.</span></span>

4.  <span data-ttu-id="dbbc3-388">[**アクション**] を [**新規作成**] に設定し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-388">Set **Action** to **Create New**, and then select **Next**.</span></span>

5.  <span data-ttu-id="dbbc3-389">設定を確認して、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-389">Confirm the settings, and then select **Next**.</span></span>

6.  <span data-ttu-id="dbbc3-390">**[閉じる]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-390">Select **Close**.</span></span>

### <a name="validate-that-the-reference-packages-are-correctly-linked-to-each-task-sequence-step"></a><span data-ttu-id="dbbc3-391">参照パッケージが各タスク シーケンスの手順に正しくリンクされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-391">Validate that the reference packages are correctly linked to each task sequence step.</span></span>

1. <span data-ttu-id="dbbc3-392">インポートされたタスク シーケンスを選択し、[ **編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-392">Select the imported task sequence, and then select **Edit**.</span></span>

    <span data-ttu-id="dbbc3-393">タスク シーケンス エディターが開き、Microsoft Teams Rooms ユニットを展開して構成するために必要な一連の手順が表示されます。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-393">The Task Sequence Editor opens and displays each sequential step that you need to deploy and configure a Microsoft Teams Rooms unit.</span></span>

2. <span data-ttu-id="dbbc3-394">各手順に従って、推奨される更新プログラムを完了します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-394">Walk through each step and complete the recommended updates:</span></span>

   1. <span data-ttu-id="dbbc3-395">**Windows PE での再起動**: この手順では、コンピューターを再起動し、Windows PXE に起動します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-395">**Restart in Windows PE**: This step restarts and then boots the computer into Windows PXE.</span></span> <span data-ttu-id="dbbc3-396">この手順では、変更は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-396">No changes are required for this step.</span></span>

   2. <span data-ttu-id="dbbc3-397">**パーティションディスク 0 – UEFI**: この手順では、ディスク構成を消去し、構成された設定に基づいてパーティションを作成します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-397">**Partition Disk 0 – UEFI**: This step wipes the disk configuration and creates partitions based on the configured settings.</span></span> <span data-ttu-id="dbbc3-398">このステップは変更しないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-398">We recommend that you not make any changes to this step.</span></span>

   3. <span data-ttu-id="dbbc3-399">**SRS コンピューター名を設定する**: この手順には、展開時に Microsoft Teams Rooms ユニットのコンピュータ名を設定するための UI を提供する HTML アプリケーションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-399">**Set SRS Computer Name**: This step includes an HTML application to provide a UI to set a computer name for the Microsoft Teams Rooms unit during the deployment.</span></span>
      -  <span data-ttu-id="dbbc3-400">これは省略可能な手順ですが、代替プロセスを使用してコンピューター名を管理する場合にのみ無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-400">This is an optional step, but it can only be disabled if you want to manage computer naming through an alternate process.</span></span>
      -  <span data-ttu-id="dbbc3-401">**SRS v2 - Set-SRSComputerName** パッケージが選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-401">Verify that the **SRS v2 - Set-SRSComputerName** package is selected.</span></span> <span data-ttu-id="dbbc3-402">表示されない場合は、パッケージを参照して選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-402">If it isn't, browse to the package and select it.</span></span>

   4. <span data-ttu-id="dbbc3-403">**オペレーティングシステムの適用**: この手順では、展開するオペレーティング システム イメージと、使用する無人 Sysprep 応答ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-403">**Apply Operating System**: This step specifies the operating system image to be deployed and the unattended Sysprep answer file to use.</span></span>
      -  <span data-ttu-id="dbbc3-404">正しい Windows 10 Enterprise オペレーティング システム イメージ ファイルが選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-404">Verify that the correct Windows 10 Enterprise operating system image file is selected.</span></span>
      -  <span data-ttu-id="dbbc3-405">[**カスタム インストールに無人または Sysprep 応答ファイルを使用する**] が有効になっており、[**SRS v2 - Sysprep パッケージ**] が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-405">Verify that **Use an unattended or Sysprep answer file for a custom installation** is enabled, and the **SRS v2 - Sysprep Package** is selected.</span></span> <span data-ttu-id="dbbc3-406">また、 **ファイル名** が **unattend.xml** に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-406">Also ensure that **File Name** is set to **unattend.xml**.</span></span>

   5. <span data-ttu-id="dbbc3-407">**Windows の設定を適用する**: この手順では、Windows のインストールに関する情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-407">**Apply Windows Settings**: This step gathers information about the Windows installation.</span></span>
      -  <span data-ttu-id="dbbc3-408">プロダクト キー、ローカル管理者アカウントのパスワード、タイムゾーン (必要に応じて) を含むライセンスと登録情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-408">Provide licensing and registration information including the product key, local administrator account password, and time zone (depending on your needs).</span></span>

   6. <span data-ttu-id="dbbc3-409">**ネットワークの設定を適用する**: この手順では、ワークグループまたは Active Directory ドメイン名と組織ユニットを指定できます。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-409">**Apply Network Settings**: This step allows you to specify a workgroup or Active Directory domain name and organizational unit.</span></span>
      > [!NOTE]
      > <span data-ttu-id="dbbc3-410">Microsoft Teams Rooms ユニットをActve Directory ドメインのメンバーとして展開する際に必要な推奨されるアクションについては、[「Skype ミーティング システム ドメイン結合の際に考慮する事項」](domain-joining-considerations.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-410">See [Skype Room System domain joining considerations](domain-joining-considerations.md) for recommended actions you need to take in deploying Microsoft Teams Rooms units as members of an Actve Directory domain.</span></span>
   7. <span data-ttu-id="dbbc3-411">**ドライバーの適用:** この手順は、お使いの Surface Pro のモデルに基づいた、適用可能なデバイスドライバとファームウェアを展開するために使用します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-411">**Apply Drivers:** This step and its sub-steps are used to deploy applicable device drivers and firmware based on the Surface Pro model you have.</span></span> <span data-ttu-id="dbbc3-412">各手順を更新して、この展開に関連付けられている関連するドライバー パッケージを指定します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-412">Update each step to specify the relevant driver package associated with this deployment.</span></span>
      -   <span data-ttu-id="dbbc3-413">各ドライバーパッケージでは、Windows Management Instrumentation (WMI) フィルターを使用し、 Surface Pro のモデルに基づいて関連性の高いドライバーやファームウェアを展開します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-413">Each driver package is configured to leverage Windows Management Instrumentation (WMI) filters to deploy relevant drivers and firmware based on the Surface Pro make and model.</span></span>
      -   <span data-ttu-id="dbbc3-414">展開が失敗するおそれがありますので、これらのドライバーの構成を変更しないことを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-414">We highly recommend that you not alter the configuration of these drivers, otherwise deployment might fail.</span></span>

   8. <span data-ttu-id="dbbc3-415">**Windows と構成マネージャーをセットアップする**: この手順では、構成マネージャー クライアントを展開し、構成します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-415">**Set up Windows and Configuration Manager**: This step deploys and configures the Configuration Manager client.</span></span> <span data-ttu-id="dbbc3-416">組み込みの構成マネージャー クライアント パッケージを指定するには、この手順を更新します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-416">Update this step to specify the built-in Configuration Manager Client Package.</span></span>

   9. <span data-ttu-id="dbbc3-417">**ルート証明書をインストールする**: この手順では、ドメインに参加していないデバイスのルート証明書を配布します。そのため、既定では無効となっており省略可能です。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-417">**Install Root Certificate**: This step distributes the root certificate for non–domain-joined devices, and therefore is optional and disabled by default.</span></span>
      -   <span data-ttu-id="dbbc3-418">Microsoft Teams Rooms ユニットにルート証明書を展開する必要がある場合は、この手順を有効にします。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-418">Enable this step if you need to deploy a root certificate to the Microsoft Teams Rooms units.</span></span>
      -   <span data-ttu-id="dbbc3-419">この手順を実行する必要がある場合は、**「SRS v2 – ルート証明書パッケージ」** と「**64 ビット ファイル システム リダイレクトを無効にする**」 が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-419">If you do need to perform this step, verify that the **SRS v2 – Root Certificate Package** and **Disable 64-bit file system redirection** are selected.</span></span>

   10. <span data-ttu-id="dbbc3-420">**監視エージェントをインストールして構成する**: この手順では、64 ビット版の Microsoft Azure Monitor エージェントをインストールし、ログ分析ワークスペースに接続するようにエージェントを構成します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-420">**Install and Configure Monitoring Agent**: This step installs the 64-bit version of the Microsoft Azure Monitor agent and configures the agent to connect to your Log Analytics workspace.</span></span>
       -   <span data-ttu-id="dbbc3-421">この手順は既定では無効になっています。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-421">This step is disabled by default.</span></span> <span data-ttu-id="dbbc3-422">監視エージェントを使用して Microsoft Teams Rooms の状態を監視する場合にのみ、この手順を有効にします。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-422">Enable this step only if you're going to use the Monitoring Agent to monitor the health of your Microsoft Teams Rooms units.</span></span>
       -   <span data-ttu-id="dbbc3-423">この手順を編集して、コマンドライン パラメーターを更新し、**ワークスペース ID** と **ワークスペース キー** を指定します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-423">Edit this step and update the command-line parameters to specify your **Workspace ID** and **Workspace Key**.</span></span>
       -   <span data-ttu-id="dbbc3-424">運用管理スイートのワークスペース ID と主キーを取得に関する詳細については、「[Azure の監視用にテストデバイスを構成する](azure-monitor-deploy.md#configure-test-devices-for-azure-monitoring)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-424">See [Configure test devices for Azure Monitoring](azure-monitor-deploy.md#configure-test-devices-for-azure-monitoring) for more information about obtaining the Operations Management Suite Workspace ID and the primary key.</span></span>
       -   <span data-ttu-id="dbbc3-425">「**SRS v2 – Microsoft Monitoring Agent パッケージ**」 と 「**64 ビット ファイル システム リダイレクトを無効にする**」 が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-425">Verify that the **SRS v2 – Microsoft Monitoring Agent Package** and **Disable 64-bit file system redirection** are selected.</span></span>
       -   <span data-ttu-id="dbbc3-426">Microsoft Teams Rooms の展開の状態を監視する方法の詳細については、「[Azure Monitor を使った Microsoft Teams Rooms 管理の計画](azure-monitor-plan.md)」、「[Azure Monitor を使った Microsoft Teams Rooms 管理の展開](azure-monitor-deploy.md)」、「[Azure Monitor を使った Microsoft Teams Rooms デバイスの管理](azure-monitor-manage.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-426">For more information about monitoring the health of your Microsoft Teams Rooms deployment, see [Plan Microsoft Teams Rooms management with Azure Monitor](azure-monitor-plan.md), [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor-deploy.md) and [Manage Microsoft Teams Rooms devices with Azure Monitor](azure-monitor-manage.md).</span></span>

   11. <span data-ttu-id="dbbc3-427">**SRS v2 構成ファイルのコピー**: この手順では、Microsoft Teams Rooms の展開キットから、ローカル ハード ドライブに必要なセットアップファイルと構成ファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-427">**Copy SRS v2 Configuration Files**: This step copies the required setup and configuration files from the Microsoft Teams Rooms deployment kit to the local hard drive.</span></span> <span data-ttu-id="dbbc3-428">この手順では、カスタマイズは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-428">No customization is required for this step.</span></span>
       -   <span data-ttu-id="dbbc3-429">「**SRS v2 – SRS アプリケーション パッケージ**」 と「**64 ビットファイルシステムのリダイレクトを無効にする**」 が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-429">Verify that the **SRS v2 – SRS Application Package** and **Disable 64-bit file system redirection** are selected.</span></span>

   12. <span data-ttu-id="dbbc3-430">**Install-SRSv2-OS-Updates**: この手順では、Microsoft Teams Rooms の展開に必要なオペレーティング システムの更新プログラムを展開します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-430">**Install-SRSv2-OS-Updates**: This step deploys any mandatory operating system updates required with the Microsoft Teams Rooms deployment.</span></span> <span data-ttu-id="dbbc3-431">以下の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-431">Do the following:</span></span>
       -   <span data-ttu-id="dbbc3-432">「[Microsoft Teams Rooms コンソールを構成する](console.md)」 をチェックして、必要な更新プログラムを確認します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-432">Check [Configure a Microsoft Teams Rooms console](console.md) to see which updates are required.</span></span>
       -   <span data-ttu-id="dbbc3-433">**SRS v2 – OS 更新プログラム** パッケージに、必要な更新プログラムがすべて含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-433">Verify that your **SRS v2 – OS Updates Package** includes all the required updates.</span></span>
       -   <span data-ttu-id="dbbc3-434">**SRS v2 – OS 更新プログラム パッケージ** が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-434">Verify that the **SRS v2 – OS Updates Package** is selected.</span></span>
       -   <span data-ttu-id="dbbc3-435">PowerShell の実行ポリシーが **バイパス** に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-435">Verify that the PowerShell execution policy is set to **Bypass**.</span></span>

   13. <span data-ttu-id="dbbc3-436">**コンピューターを再起動する**: この手順では、オペレーティング システムの必要な更新プログラムのインストール後にコンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-436">**Restart Computer**: This step reboots the computer after the mandatory operating system updates are installed.</span></span> <span data-ttu-id="dbbc3-437">この手順では、カスタマイズは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-437">No customization is required for this step.</span></span>

   14. <span data-ttu-id="dbbc3-438">**Windows コンポーネントを構成する**: この手順では、必要な Windows の機能を構成します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-438">**Configure Windows Components**: This step configures the required Windows features.</span></span> <span data-ttu-id="dbbc3-439">この手順では、カスタマイズは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-439">No customization is required for this step.</span></span>

   15. <span data-ttu-id="dbbc3-440">**コンピューターを再起動する**: この手順では、Windows の機能を構成した後にコンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-440">**Restart Computer**: This step reboots the computer after the Windows features are configured.</span></span> <span data-ttu-id="dbbc3-441">この手順では、カスタマイズは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-441">No customization is required for this step.</span></span>

   16. <span data-ttu-id="dbbc3-442">**ローカル Skype ユーザーの追加**: この手順では、Windows に自動サインインして Microsoft Teams Rooms アプリケーションを起動するために使用するローカル Skype アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-442">**Add Local Skype User**: This step creates the local Skype account used to automatically sign in to Windows and start the Microsoft Teams Rooms application.</span></span> <span data-ttu-id="dbbc3-443">この手順には関連付けられているソフトウェアパッケージはありません。カスタマイズする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-443">This step doesn't have any software package associated with it, and no customization is required for it.</span></span>

   17. <span data-ttu-id="dbbc3-444">**SRS アプリケーションをセットアップして構成する**: この手順では、オペレーティング システムの次の起動用に Microsoft Teams Rooms アプリケーションをインストールします。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-444">**Set up and configure SRS application**: This step configures the Microsoft Teams Rooms application installation for the next boot of the operating system.</span></span>
       -   <span data-ttu-id="dbbc3-445">「**SRS v2 – SRS セットアップ パッケージの構成**」 と 「**64 ビット ファイル システムのリダイレクトを無効にする**」 が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-445">Verify that the **SRS v2 – Configure SRS Setup Package** and **Disable 64-bit file system redirection** are selected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dbbc3-446">タスク シーケンスのステップは、指定された順序である必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-446">It is very important that the task sequence steps must be in the provided order.</span></span> <span data-ttu-id="dbbc3-447">ステップの順序を変更したり、追加の手順を構成したりすると、展開が破損する場合があります。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-447">Modifying the order of steps, or configuring additional steps might break the deployment.</span></span>
>
> <span data-ttu-id="dbbc3-448">**SRS アプリケーションのセットアップと構成** のステップは、タスク シーケンスの最後の手順である必要があります。それ以外の場合は、展開が失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-448">**Set up and configure SRS application** step must be the last step in the task sequence, otherwise the deployment might fail.</span></span>

### <a name="create-deployment-for-the-task-sequence"></a><span data-ttu-id="dbbc3-449">タスク シーケンスの展開を作成する</span><span class="sxs-lookup"><span data-stu-id="dbbc3-449">Create deployment for the task sequence</span></span>

1. <span data-ttu-id="dbbc3-450">タスク シーケンスを選択し、[**展開**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-450">Select the task sequence, and then select **Deploy**.</span></span>

2. <span data-ttu-id="dbbc3-451">[**参照**] を選択して、展開用のターゲット コレクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-451">Select **Browse** to select target collection for deployment.</span></span>

3. <span data-ttu-id="dbbc3-452">[**すべての不明なコンピューター**] を選択し、[**OK**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-452">Select **All Unknown Computers** and then select **OK**.</span></span>

4. <span data-ttu-id="dbbc3-453">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-453">Select **Next**.</span></span>

5. <span data-ttu-id="dbbc3-454">**「目的」** のドロップ ダウン リストから、[**使用可能**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-454">Select **Available** on the **Purpose** drop down list.</span></span>

6. <span data-ttu-id="dbbc3-455">**「次のリストで利用可能にする」** で[**メディアと PXE のみ**] を選択し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-455">Select **Only Media and PXE** in the **Make available to the following** list, and then select **Next**.</span></span>
   > [!WARNING]
   > <span data-ttu-id="dbbc3-456">[**目的**] は、[**使用可能**] に設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-456">It is very important that **Purpose** is set to **Available**.</span></span> <span data-ttu-id="dbbc3-457">[**目的**] が、 [**必須**]に設定されて **いない** ことを確認します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-457">Make sure that the **Purpose** is **NOT** set to **Required**.</span></span> <span data-ttu-id="dbbc3-458">また、**「次に利用可能にする」** で、[**メディアとPXEのみ**] を選択していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-458">Also make sure that you select **Only Media and PXE** in the **Make available to the following**.</span></span>
   >
   > <span data-ttu-id="dbbc3-459">これらの値を別の値に設定すると、起動したときに、すべてのコンピューターで Microsoft Teams Rooms の展開イメージが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-459">Setting these values to something else might cause all computers to get the Microsoft Teams Rooms deployment image when booted.</span></span>
7. <span data-ttu-id="dbbc3-460">スケジュールを指定せずに、 [**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-460">Do not specify any schedule and select **Next**.</span></span>

8. <span data-ttu-id="dbbc3-461">[**ユーザーエクスペリエンス**] セクション内の内容を変更せずに、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-461">Do not change anything within the **User Experience** section and select **Next**.</span></span>

9. <span data-ttu-id="dbbc3-462">[**アラート**] セクション内の内容を変更せずに、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-462">Do not change anything within the **Alerts** section and select **Next**.</span></span>

10. <span data-ttu-id="dbbc3-463">[**配布ポイント**] セクション内の内容を変更せずに、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-463">Do not change anything within the **Distribution Points** section and select **Next**.</span></span>

11. <span data-ttu-id="dbbc3-464">設定を確認して、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-464">Confirm the settings and then select **Next**.</span></span>

12. <span data-ttu-id="dbbc3-465">**[閉じる]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-465">Select **Close**.</span></span>

<a name="validate-and-troubleshoot-the-solution"></a><span data-ttu-id="dbbc3-466">ソリューションの検証およびトラブルシューティングを行う</span><span class="sxs-lookup"><span data-stu-id="dbbc3-466">Validate and troubleshoot the solution</span></span>
--------------------------------------

<span data-ttu-id="dbbc3-467">Microsoft Endpoint Configuration Manager のタスク シーケンスを完了したら、タスク シーケンスが Microsoft Teams Rooms ユニットを展開し構成できることを検証するため、テスト実行を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-467">After you've completed the Microsoft Endpoint Configuration Manager task sequences, you'll need to perform a test run to validate that the task sequence can deploy and configure Microsoft Teams Rooms units.</span></span>

1.  <span data-ttu-id="dbbc3-468">サポートされているイーサネット アダプターのいずれかを使用するか、Surface dock を使用して、テスト デバイスをケーブル ネットワークに接続します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-468">Connect the test device to the wired network by using one of the supported Ethernet adapters or using the Surface dock.</span></span> <span data-ttu-id="dbbc3-469">使用している環境に PXE ブート機能が構成されていない場合は、[以前に作成した](/configmgr/osd/deploy-use/create-bootable-media) USB フラッシュ ドライブのブート イメージを使用して USB から起動し、構成マネージャーに接続することができます。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-469">If PXE boot functionality hasn't been configured for your environment, you can use the boot image on the USB flash drive [that you created earlier](/configmgr/osd/deploy-use/create-bootable-media) to boot from USB and connect to Configuration Manager.</span></span>

2.  <span data-ttu-id="dbbc3-470">ファームウェアにアクセスし、PXE ブートを開始します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-470">Access the firmware and initiate PXE boot:</span></span>

    1.  <span data-ttu-id="dbbc3-471">Surface デバイスの電源が切れていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-471">Ensure the Surface device is powered off.</span></span>

    2.  <span data-ttu-id="dbbc3-472">**「音量を上げる」** ボタンを長押しします。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-472">Press and hold the **Volume Up** button.</span></span>

    3.  <span data-ttu-id="dbbc3-473">**電源ボタン** を押して、離します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-473">Press and release the **Power** button.</span></span>

    4.  <span data-ttu-id="dbbc3-474">デバイスが起動したら、 **「音量を上げる」** ボタンを放します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-474">After the device begins to boot, release the **Volume Up** button.</span></span>

    5.  <span data-ttu-id="dbbc3-475">**「ブート構成」** を選びます。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-475">Select **Boot configuration**.</span></span>

    6.  <span data-ttu-id="dbbc3-476">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-476">Do one of the following:</span></span>

        -   <span data-ttu-id="dbbc3-477">[**PXE ブート**] を選択し、リストの先頭にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-477">Select **PXE boot**, and drag it to the top of the list.</span></span> <span data-ttu-id="dbbc3-478">または、ネットワーク アダプターを左にスワイプして、デバイスからすぐに起動することもできます。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-478">Alternatively, you can swipe left on the network adapter to boot to the device immediately.</span></span> <span data-ttu-id="dbbc3-479">これは、ブート順序には影響しません。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-479">This won't affect the boot order.</span></span>
        -   <span data-ttu-id="dbbc3-480">ブート メディアを含む USB フラッシュドライブを選びます。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-480">Select the USB flash drive that holds the boot media.</span></span>

3.  <span data-ttu-id="dbbc3-481">[**終了**] を選択し、[**今すぐ再起動**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-481">Select **Exit**, and then select **Restart Now**.</span></span>

4.  <span data-ttu-id="dbbc3-482">メッセージが表示されたら、ネットワーク ブート サービスの [**実行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-482">When prompted, select **Enter** for network boot service.</span></span>

5.  <span data-ttu-id="dbbc3-483">Windows PE がメモリに読み込まれ、タスク シーケンス ウィザードが起動します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-483">Windows PE will load into memory, and the Task Sequence Wizard will start.</span></span> <span data-ttu-id="dbbc3-484">[**次へ**] を選んで続行します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-484">Select **Next** to continue.</span></span>

6.  <span data-ttu-id="dbbc3-485">以前にインポートしたタスク シーケンスを選択し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-485">Select the task sequence that you imported earlier, and then select **Next**.</span></span>

7.  <span data-ttu-id="dbbc3-486">ディスク構成が適用されると、デバイスのコンピューター名を指定するように求められます。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-486">After the disk configuration is applied, you'll be prompted to specify a computer name for the device.</span></span> <span data-ttu-id="dbbc3-487">ユーザー インターフェイスには、Surface Pro デバイスのシリアル番号に基づいて推奨されるコンピューター名が表示されます。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-487">The user interface will display a recommended computer name based on the serial number of the Surface Pro device.</span></span> <span data-ttu-id="dbbc3-488">提案された名前を受け入れるか、新しい名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-488">You can either accept the proposed name or specify a new one.</span></span> <span data-ttu-id="dbbc3-489">コンピューター名の割り当て画面の指示に従います。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-489">Follow the instructions on the computer name assignment screen.</span></span> <span data-ttu-id="dbbc3-490">[**承諾**] を選択すると、展開が始まります。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-490">When you select **Accept**, the deployment begins.</span></span>

8.  <span data-ttu-id="dbbc3-491">展開プロセスの残りの部分は自動的に行われ、ユーザーからの入力を求めることはありません。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-491">The rest of the deployment process is automatic and doesn't ask for any more user input.</span></span>

9.  <span data-ttu-id="dbbc3-492">展開タスクのシーケンスでデバイスの構成が完了すると、Microsoft Teams Rooms のアプリケーション設定を構成するように求める次の構成画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-492">After the deployment task sequence finishes configuring the device, you'll see the following configuration screen that asks you to configure the Microsoft Teams Rooms application settings.</span></span>

    ![Microsoft Teams Rooms アプリケーションの初期セットアップ画面](../media/room-systems-scale-image2.png)

10.  <span data-ttu-id="dbbc3-494">Surface Pro を Microsoft Teams Rooms コンソールに接続し、アプリケーション設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-494">Plug the Surface Pro into the Microsoft Teams Rooms console, and configure the application settings.</span></span>

11.  <span data-ttu-id="dbbc3-495">[Microsoft Teams Rooms ヘルプ](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)に記載されている機能が、展開されたデバイスで機能していることを検証します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-495">Validate that the capabilities listed in [Microsoft Teams Rooms help](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) are working on the deployed device.</span></span>


<span data-ttu-id="dbbc3-496">インストールの失敗をトラブルシューティングするには、**SMSTS.log** ファイルを確認します。このファイルは、構成マネージャー タスク シーケンスで実行されたすべてのステップを記録します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-496">To troubleshoot a failed installation, check the **SMSTS.log** file, which logs all the steps executed in a Configuration Manager task sequence.</span></span>

<span data-ttu-id="dbbc3-497">SMSTS.log ファイルは、ビルド プロセスのステージに応じて、多くのパスの内のいずれかに格納されます。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-497">The SMSTS.log file is stored on one of a number of paths, depending on the stage of the build process.</span></span> <span data-ttu-id="dbbc3-498">次の表を確認し、SMSTS.log ファイルへのパスを確認します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-498">Check the following table to identify the path to the SMSTS.log file.</span></span>


| <span data-ttu-id="dbbc3-499">**展開フェーズ**</span><span class="sxs-lookup"><span data-stu-id="dbbc3-499">**Deployment phase**</span></span>                                                            | <span data-ttu-id="dbbc3-500">**タスク シーケンスのログのパス**</span><span class="sxs-lookup"><span data-stu-id="dbbc3-500">**Task sequence log path**</span></span>                         |
|---------------------------------------------------------------------------------|----------------------------------------------------|
| <span data-ttu-id="dbbc3-501">WinPE (HDD フォーマット以前)</span><span class="sxs-lookup"><span data-stu-id="dbbc3-501">WinPE, before HDD format</span></span>                                                        | <span data-ttu-id="dbbc3-502">X:\\Windows\\Temp\\smstslog\\smsts.log</span><span class="sxs-lookup"><span data-stu-id="dbbc3-502">X:\\Windows\\Temp\\smstslog\\smsts.log</span></span>             |
| <span data-ttu-id="dbbc3-503">WinPE (ハードフォーマット以降)</span><span class="sxs-lookup"><span data-stu-id="dbbc3-503">WinPE, after HDD format</span></span>                                                         | <span data-ttu-id="dbbc3-504">C:\\_SMSTaskSequence\\Logs\\Smstslog\\smsts.log</span><span class="sxs-lookup"><span data-stu-id="dbbc3-504">C:\\_SMSTaskSequence\\Logs\\Smstslog\\smsts.log</span></span>    |
| <span data-ttu-id="dbbc3-505">構成マネージャー エージェントをインストールする前に、オペレーティング システムが展開された</span><span class="sxs-lookup"><span data-stu-id="dbbc3-505">Operating system deployed, before the Configuration Manager agent was installed</span></span> | <span data-ttu-id="dbbc3-506">c:\\_SMSTaskSequence\\Logs\\Smstslog\\smsts.log</span><span class="sxs-lookup"><span data-stu-id="dbbc3-506">c:\\_SMSTaskSequence\\Logs\\Smstslog\\smsts.log</span></span>    |
| <span data-ttu-id="dbbc3-507">オペレーティングシステムと構成マネージャー エージェントが展開されている</span><span class="sxs-lookup"><span data-stu-id="dbbc3-507">Operating system and the Configuration Manager agent deployed</span></span>                   | <span data-ttu-id="dbbc3-508">% windir%\\System32\\ccm\\logs\\Smstslog\\smsts.log</span><span class="sxs-lookup"><span data-stu-id="dbbc3-508">%windir%\\System32\\ccm\\logs\\Smstslog\\smsts.log</span></span> |
| <span data-ttu-id="dbbc3-509">タスク シーケンスの実行が完了しました</span><span class="sxs-lookup"><span data-stu-id="dbbc3-509">Task sequence execution complete</span></span>                                                | <span data-ttu-id="dbbc3-510">%windir%\\System32\\ccm\\logs\\smsts.log</span><span class="sxs-lookup"><span data-stu-id="dbbc3-510">%windir%\\System32\\ccm\\logs\\smsts.log</span></span>           |

> [!TIP]
> <span data-ttu-id="dbbc3-511">タスクシーケンスの実行中に、いつでも **F8** を選択してコマンド コンソールを開くことができ、 SMSTS.log ファイルにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-511">You can select **F8** at any time during the task sequence to open a command console, and then get access to the SMSTS.log file.</span></span>

<span data-ttu-id="dbbc3-512">PXE ブートの問題のトラブルシューティングを行うには、PXE のアクション固有の、構成マネージャー サーバー上の 2 つのログファイルを確認します。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-512">To troubleshoot PXE boot issues, check the two log files on the Configuration Manager server that are specific to PXE actions:</span></span>

-   <span data-ttu-id="dbbc3-513">構成マネージャー インストール ログ ディレクトリにある **Pxecontrol.log**</span><span class="sxs-lookup"><span data-stu-id="dbbc3-513">**Pxecontrol.log**, located in the Configuration Manager installation logs directory</span></span>

-   <span data-ttu-id="dbbc3-514">構成マネージャー 管理ポイント (MP) logs ディレクトリにある **Smspxe.log**</span><span class="sxs-lookup"><span data-stu-id="dbbc3-514">**Smspxe.log**, located in Configuration Manager Management Point (MP) logs directory</span></span>

<span data-ttu-id="dbbc3-515">構成マネージャーのインストールの詳細なトラブルシューティングに使用できるログファイルの完全なリストについては、「Microsoft Endpoint Configuration Manager [ログファイルの参照](/configmgr/core/plan-design/hierarchy/log-files)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dbbc3-515">For a complete list of the log files that you can use to further troubleshoot your Configuration Manager installation, see the Microsoft Endpoint Configuration Manager [Log file reference](/configmgr/core/plan-design/hierarchy/log-files).</span></span>
