---
title: System Center Configuration Manager を使用して Microsoft Teams ルームを展開する
author: lanachin
ms.author: v-lanac
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
ms.collection:
- M365-collaboration
description: このトピックでは、大規模な展開での Microsoft Teams のルームの展開について説明します。
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
ms.openlocfilehash: fe6ea140f15c5234117aabe6612e0190e47ddc4d
ms.sourcegitcommit: 9bead87a7f4c4e71f19f8980e9dce2b979735055
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2020
ms.locfileid: "41269101"
---
# <a name="deploy-microsoft-teams-rooms-by-using-system-center-configuration-manager"></a><span data-ttu-id="c11d9-103">System Center Configuration Manager を使用して Microsoft Teams ルームを展開する</span><span class="sxs-lookup"><span data-stu-id="c11d9-103">Deploy Microsoft Teams Rooms by using System Center Configuration Manager</span></span>

<span data-ttu-id="c11d9-104">この記事では、System Center Configuration Manager を使用して Microsoft Teams 室の展開を作成するために必要なすべての情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-104">This article gives you all the necessary information to create your Microsoft Teams Rooms deployments by using System Center Configuration Manager.</span></span>

<span data-ttu-id="c11d9-105">System Center Configuration Manager によって提供される使いやすいメソッドを使用して、オペレーティングシステムとその他のアプリケーションを複数のターゲットデバイスに展開できます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-105">With the easy-to-use methods provided by System Center Configuration Manager, you can deploy the operating system and other applications to multiple target devices.</span></span>

<span data-ttu-id="c11d9-106">次の手順を使用して、構成マネージャーの構成について説明し、このガイダンス全体で組織に必要なサンプルパッケージとスクリプトをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="c11d9-106">Use the approach illustrated below to guide you through your Configuration Manager configuration, and customize the sample packages and scripts provided throughout this guidance as needed for your organization.</span></span>

![Microsoft Teams 室展開プロセス (Configuration Manager を使用)](../media/room-systems-scale-image1.png)

> [!IMPORTANT]
> <span data-ttu-id="c11d9-108">このソリューションは、Surface Pro ベースの展開でのみテストされています。</span><span class="sxs-lookup"><span data-stu-id="c11d9-108">This solution has only been tested with Surface Pro–based deployments.</span></span> <span data-ttu-id="c11d9-109">Surface Pro に基づかない構成については、製造元のガイドラインに従ってください。</span><span class="sxs-lookup"><span data-stu-id="c11d9-109">Follow the manufacturer’s guidelines for configurations that aren’t based on Surface Pro.</span></span>

## <a name="validate-prerequisites"></a><span data-ttu-id="c11d9-110">前提条件の検証</span><span class="sxs-lookup"><span data-stu-id="c11d9-110">Validate prerequisites</span></span>

<span data-ttu-id="c11d9-111">Configuration Manager を使用して Microsoft Teams のルームを展開するには、次の前提条件と要件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-111">To deploy Microsoft Teams Rooms with Configuration Manager, ensure that you meet the following prerequisites and requirements.</span></span>

### <a name="system-center-configuration-manager-requirements"></a><span data-ttu-id="c11d9-112">System Center Configuration Manager の要件</span><span class="sxs-lookup"><span data-stu-id="c11d9-112">System Center Configuration Manager requirements</span></span>

-   <span data-ttu-id="c11d9-113">System Center Configuration Manager のバージョンは、1706以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="c11d9-113">System Center Configuration Manager version must be at least 1706 or above.</span></span> <span data-ttu-id="c11d9-114">1710以降の使用をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c11d9-114">We recommend using 1710 or later.</span></span> <span data-ttu-id="c11d9-115">Configuration Manager でサポートされている Windows 10 のバージョンについては、「 [System Center Configuration manager での windows 10 のサポート」](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c11d9-115">Check out [Support for Windows 10 in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) to learn about the Windows 10 versions that Configuration Manager supports.</span></span>

-   <span data-ttu-id="c11d9-116">Windows 10 でサポートされているバージョンの Windows アセスメント & デプロイメントキット (ADK) がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c11d9-116">A supported version of Windows Assessment and Deployment Kit (ADK) for Windows 10 must be installed.</span></span> <span data-ttu-id="c11d9-117">さまざまなバージョンの Configuration Manager で使用できる[Windows 10 ADK](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-adk)のバージョンを確認し、展開に適切なバージョンが含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-117">See the versions of the [Windows 10 ADK](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-adk) that you can use with different versions of Configuration Manager, and ensure that your deployment includes the correct version.</span></span>

-   <span data-ttu-id="c11d9-118">サイトシステムサーバーには、配布ポイントの役割が割り当てられている必要があります。また、ネットワークで開始された展開を有効にするために、ブートイメージを[プレブート実行環境 (PXE) のサポート](https://docs.microsoft.com/sccm/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network)に対して有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c11d9-118">The site system servers must have been assigned the distribution point role, and the boot images should be enabled for [preboot execution environment (PXE) support](https://docs.microsoft.com/sccm/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) to enable network-initiated deployments.</span></span> <span data-ttu-id="c11d9-119">PXE のサポートが有効になっていない場合は、展開用に[起動可能なメディア](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network)を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-119">If PXE support isn’t enabled, you can use [bootable media](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) for your deployments.</span></span>

-   <span data-ttu-id="c11d9-120">ネットワークアクセスアカウントは、新しいコンピューター (ベアメタル) の展開シナリオをサポートするように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c11d9-120">A network access account must be configured to support new computer (bare metal) deployment scenarios.</span></span> <span data-ttu-id="c11d9-121">ネットワークアクセスアカウントの構成の詳細については、「 [System Center Configuration Manager でコンテンツにアクセスするためにアカウントを管理](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c11d9-121">To learn more about the configuration of a network access account, see [Manage accounts to access content in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span></span>

-   <span data-ttu-id="c11d9-122">同じ Microsoft Teams のルームイメージを複数のユニットに同時に展開する可能性がある場合は、[マルチキャストサポート](https://docs.microsoft.com/sccm/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network)を有効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c11d9-122">We recommend that you enable [multicast support](https://docs.microsoft.com/sccm/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network), if you’re likely to deploy the same Microsoft Teams Rooms image to multiple units at the same time.</span></span>

### <a name="networking-requirements"></a><span data-ttu-id="c11d9-123">ネットワーク要件</span><span class="sxs-lookup"><span data-stu-id="c11d9-123">Networking requirements</span></span>

-   <span data-ttu-id="c11d9-124">ネットワークには、Microsoft Teams のルームユニットが展開されるサブネットへの IP アドレスの自動配布用に構成された動的ホスト構成プロトコル (DHCP) サーバーが必要です。</span><span class="sxs-lookup"><span data-stu-id="c11d9-124">Your network should have a Dynamic Host Configuration Protocol (DHCP) server, configured for automatic IP address distribution to the subnets where Microsoft Teams Rooms units will be deployed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c11d9-125">DHCP リース期間は、イメージの展開期間よりも長い値に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c11d9-125">DHCP lease duration must be set to a value longer than the image deployment duration.</span></span> <span data-ttu-id="c11d9-126">そうしないと、展開が失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c11d9-126">Otherwise, the deployment might fail.</span></span>

-   <span data-ttu-id="c11d9-127">スイッチや仮想 Lan (Vlan) などのネットワークは、PXE をサポートするように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c11d9-127">Your network, including switches and virtual LANs (VLANs), should be configured to support PXE.</span></span> <span data-ttu-id="c11d9-128">IP ヘルパーと PXE 構成の詳細については、ネットワークベンダーにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="c11d9-128">Refer to your network vendor for more information about IP Helper and PXE configuration.</span></span> <span data-ttu-id="c11d9-129">または、PXE のサポートが有効になっていない場合は、展開用に[起動可能なメディア](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network)を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-129">Alternatively, you can use [bootable media](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) for your deployments, if PXE support isn’t enabled.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c11d9-130">Surface Pro デバイスでは、ネットワークからの起動 (PXE ブート) は、Microsoft のイーサネットアダプターまたはドッキングステーションを使っている場合にのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-130">For Surface Pro devices, booting from the network (PXE boot) is only supported when you use an Ethernet adapter or docking station from Microsoft.</span></span> <span data-ttu-id="c11d9-131">サードパーティのイーサネットアダプターは Surface Pro による PXE ブートをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="c11d9-131">Third-party Ethernet adapters don’t support PXE boot with Surface Pro.</span></span> <span data-ttu-id="c11d9-132">詳細については[、「イーサネットアダプターとサーフェスの展開](https://docs.microsoft.com/surface/ethernet-adapters-and-surface-device-deployment)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c11d9-132">See [Ethernet adapters and Surface deployment](https://docs.microsoft.com/surface/ethernet-adapters-and-surface-device-deployment) for more information.</span></span>

## <a name="configure-system-center-configuration-manager-for-operating-system-deployment"></a><span data-ttu-id="c11d9-133">オペレーティングシステムの展開用に System Center Configuration Manager を構成する</span><span class="sxs-lookup"><span data-stu-id="c11d9-133">Configure System Center Configuration Manager for operating system deployment</span></span>

<span data-ttu-id="c11d9-134">この記事では、システムセンター構成マネージャーの展開が正常に完了していることを前提としており、構成マネージャーを最初から展開して構成するために必要なすべての手順については詳しく説明しません。</span><span class="sxs-lookup"><span data-stu-id="c11d9-134">This article assumes you already have a healthy System Center Configuration Manager deployment, and doesn’t detail all the steps required to deploy and configure Configuration Manager from scratch.</span></span> <span data-ttu-id="c11d9-135">System Center Configuration Manager の[ドキュメントと構成ガイダンス](https://docs.microsoft.com/sccm/)は、優れたリソースです。まだ構成マネージャーを展開していない場合は、これらのリソースから始めることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c11d9-135">The [documentation and the configuration guidance](https://docs.microsoft.com/sccm/) on the System Center Configuration Manager is a great resource; we recommend you start with these resources if you haven’t yet deployed Configuration Manager.</span></span>

<span data-ttu-id="c11d9-136">オペレーティングシステムの展開 (OSD) 機能が正しく構成されていることを確認するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-136">Use the following instructions to verify that the operating system deployment (OSD) features are configured properly.</span></span>

### <a name="validate-and-upgrade-configuration-manager"></a><span data-ttu-id="c11d9-137">構成マネージャーの検証とアップグレード</span><span class="sxs-lookup"><span data-stu-id="c11d9-137">Validate and upgrade Configuration Manager</span></span>

1.  <span data-ttu-id="c11d9-138">Configuration Manager コンソールで、[**管理** \> **更新とサービス**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-138">In the Configuration Manager console, go to **Administration** \> **Updates and Servicing**.</span></span>

2.  <span data-ttu-id="c11d9-139">インストールされているビルドと、まだインストールされていない更新プログラムを確認します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-139">Check the installed build and applicable updates that haven’t been installed yet.</span></span>

3.  <span data-ttu-id="c11d9-140">[System Center Configuration Manager での Windows 10 のサポートを](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client)確認します。展開をアップグレードする必要がある場合は、インストールする更新プログラムを選び、[**ダウンロード**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-140">Review [Support for Windows 10 in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client); if you need to upgrade your deployment, select the update you want to install, and then select **Download**.</span></span>

4.  <span data-ttu-id="c11d9-141">ダウンロードが完了したら、更新プログラムを選択して、[**更新プログラムパックのインストール**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-141">After the download is complete, select the update, and then select **Install Update Pack**.</span></span>

### <a name="configure-distribution-points-to-support-pxe-and-multicast"></a><span data-ttu-id="c11d9-142">PXE とマルチキャストをサポートするように配布ポイントを構成する</span><span class="sxs-lookup"><span data-stu-id="c11d9-142">Configure distribution points to support PXE and multicast</span></span>

1.  <span data-ttu-id="c11d9-143">Configuration Manager コンソールで、[**管理** \> ]**配布ポイント**に移動します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-143">In the Configuration Manager console, go to **Administration** \> **Distribution Points**.</span></span>

2.  <span data-ttu-id="c11d9-144">Microsoft Teams ルームの展開を実行する配布ポイントサーバーを選択し、[**プロパティ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-144">Select the distribution point server that will serve the Microsoft Teams Rooms deployment, and then select **Properties**.</span></span>

3.  <span data-ttu-id="c11d9-145">[ **PXE** ] タブを選択し、次の設定が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-145">Select the **PXE** tab, and ensure that the following settings are enabled:</span></span>
    -   <span data-ttu-id="c11d9-146">クライアントに対して PXE のサポートを有効にする</span><span class="sxs-lookup"><span data-stu-id="c11d9-146">Enable PXE support for clients</span></span>
    -   <span data-ttu-id="c11d9-147">この配布ポイントから受信 PXE 要求への応答を許可する</span><span class="sxs-lookup"><span data-stu-id="c11d9-147">Allow this distribution point to respond to incoming PXE requests</span></span>
    -   <span data-ttu-id="c11d9-148">不明なコンピューターのサポートを有効にする</span><span class="sxs-lookup"><span data-stu-id="c11d9-148">Enable unknown computer support</span></span>

4.  <span data-ttu-id="c11d9-149">*オプション:* マルチキャストのサポートを有効にするには、[**マルチキャスト**] タブを選択し、次の設定が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-149">*Optional:* To enable multicast support, select the **Multicast** tab, and ensure that the following settings are enabled:</span></span>
    -   <span data-ttu-id="c11d9-150">マルチキャストで複数のクライアントにデータを同時に送信できるようにする</span><span class="sxs-lookup"><span data-stu-id="c11d9-150">Enable multicast to simultaneously send data to multiple clients</span></span>
    -   <span data-ttu-id="c11d9-151">ネットワークチームの推奨事項に従って UDP ポート範囲を構成する</span><span class="sxs-lookup"><span data-stu-id="c11d9-151">Configure the UDP port range as per your network team’s recommendation</span></span>

### <a name="configure-the-network-access-account"></a><span data-ttu-id="c11d9-152">ネットワークアクセスアカウントを構成する</span><span class="sxs-lookup"><span data-stu-id="c11d9-152">Configure the Network Access Account</span></span>

1.  <span data-ttu-id="c11d9-153">Configuration Manager コンソールで、[**管理** \> **サイトの構成** \> **サイト**] に移動し、サイトを選びます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-153">In the Configuration Manager console, go to **Administration** \> **Site Configuration** \> **Sites**, and then select the site.</span></span>

2.  <span data-ttu-id="c11d9-154">[**設定**] グループで、[**サイトコンポーネント** \> **ソフトウェア配布**の構成] を選びます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-154">In the **Settings** group, select **Configure Site Components** \> **Software Distribution**.</span></span>

3.  <span data-ttu-id="c11d9-155">[**ネットワークアクセスアカウント**] タブを選びます。1つまたは複数のアカウントをセットアップし、[ **OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-155">Select the **Network Access Account** tab. Set up one or more accounts, and then select **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="c11d9-156">アカウントには特別な権限は必要ありません。ただし、配布ポイントサーバーの [**ネットワーク経由でコンピューターにアクセス**する] 権限は使用できません。</span><span class="sxs-lookup"><span data-stu-id="c11d9-156">The accounts don’t need any special rights, except for the **Access this computer from the network** right on the distribution point server.</span></span> <span data-ttu-id="c11d9-157">一般的なドメインユーザーアカウントが適切です。</span><span class="sxs-lookup"><span data-stu-id="c11d9-157">A generic domain user account will be appropriate.</span></span> <span data-ttu-id="c11d9-158">詳細については、「 [System Center Configuration Manager でコンテンツにアクセスするためにアカウントを管理する](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c11d9-158">For more information, see [Manage accounts to access content in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span></span>

### <a name="configure-a-boot-image"></a><span data-ttu-id="c11d9-159">ブートイメージを構成する</span><span class="sxs-lookup"><span data-stu-id="c11d9-159">Configure a boot image</span></span>

1.  <span data-ttu-id="c11d9-160">Configuration Manager コンソールで、[**ソフトウェアライブラリ** \> **オペレーティングシステム** \> **ブートイメージ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-160">In the Configuration Manager console, go to **Software Library** \> **Operating System** \> **Boot Images**.</span></span>

2.  <span data-ttu-id="c11d9-161">[**ブートイメージ (x64)**] を選択し、[**プロパティ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-161">Select **Boot image (x64)**, and then select **Properties**.</span></span>

3.  <span data-ttu-id="c11d9-162">[**データソース**] タブを選択し、[ **PXE 対応の配布ポイントからこのブートイメージを展開**する] を有効にします。</span><span class="sxs-lookup"><span data-stu-id="c11d9-162">Select the **Data Source** tab, and enable **Deploy this boot image from the PXE-enabled distribution point**.</span></span>

4.  <span data-ttu-id="c11d9-163">[**オプションコンポーネント**] タブを選択して、必要なコンポーネントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="c11d9-163">Select the **Optional Components** tab to install required components:</span></span>

    1.  <span data-ttu-id="c11d9-164">星アイコンを選択し、HTML を検索する **(WinPE-HTA)**</span><span class="sxs-lookup"><span data-stu-id="c11d9-164">Select the star icon, and search for **HTML (WinPE-HTA)**</span></span>

    2.  <span data-ttu-id="c11d9-165">[ **OK]** を選択して、HTML アプリケーションのサポートをブートイメージに追加します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-165">Select **OK** to add HTML application support in to the boot image.</span></span>

5.  <span data-ttu-id="c11d9-166">*オプション:* 展開エクスペリエンスをカスタマイズするには、[**カスタマイズ**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-166">*Optional:* To customize the deployment experience, select the **Customization** tab.</span></span>
    -   <span data-ttu-id="c11d9-167">展開時にコマンドプロンプトにアクセスする必要がある場合は、**コマンドのサポート (テスト専用)** を有効にします。</span><span class="sxs-lookup"><span data-stu-id="c11d9-167">Enable **command support (testing only)** if you want to have access to a command prompt during the deployment.</span></span> <span data-ttu-id="c11d9-168">この機能が有効になっている場合は、展開中に**F8**を選択してコマンドプロンプトを開始できます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-168">When this is enabled, you can start a command prompt by selecting **F8** at any time during the deployment.</span></span>
    -   <span data-ttu-id="c11d9-169">また、展開中に表示されるカスタムの背景画像を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-169">You can also specify a custom background image to be displayed during the deployment.</span></span> <span data-ttu-id="c11d9-170">画像を設定するには、**カスタムの背景画像ファイル (UNC パスを指定**し、背景を選択します) を有効にします。</span><span class="sxs-lookup"><span data-stu-id="c11d9-170">To set an image, enable **Specify the custom background image file (UNC path** and select your background.</span></span>

6.  <span data-ttu-id="c11d9-171">メッセージが表示されたら、[**はい**] を選択し、更新されたブートイメージを配布ポイントに配布します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-171">When asked, select **Yes** and distribute the updated boot image to your distribution points.</span></span>

<span data-ttu-id="c11d9-172">詳細については、「 [System Center Configuration Manager を使用してブートイメージを管理](https://docs.microsoft.com/sccm/osd/get-started/manage-boot-images)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c11d9-172">For more information, see [Manage boot images with System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-boot-images).</span></span>

> [!NOTE]
> <span data-ttu-id="c11d9-173">ブート可能な USB メディアを作成して、PXE をサポートしていない環境の構成マネージャーのタスクシーケンスベースの展開を開始することができます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-173">You can create a bootable USB media to initiate Configuration Manager task sequence–based deployments for environments that have no PXE support.</span></span> <span data-ttu-id="c11d9-174">起動可能なメディアには、ブートイメージ、オプションの起動コマンドと必要なファイル、および構成マネージャーのバイナリが含まれます。これには、Windows PE の起動と、展開プロセスの残りの部分に対して Configuration Manager への接続がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-174">The bootable media contains only the boot image, optional prestart commands and their required files, and Configuration Manager binaries to support booting into Windows PE and connecting to Configuration Manager for the rest of the deployment process.</span></span> <span data-ttu-id="c11d9-175">詳細については、「[起動可能なメディアを作成する方法](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c11d9-175">For more information, see [How to Create Bootable Media](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia).</span></span>

## <a name="create-configuration-manager-packages"></a><span data-ttu-id="c11d9-176">Configuration Manager パッケージを作成する</span><span class="sxs-lookup"><span data-stu-id="c11d9-176">Create Configuration Manager packages</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c11d9-177">各 SRS インストーラーバージョンに必要なオペレーティングシステムのバージョンが、MSI のすべてのリリースで変更されています。</span><span class="sxs-lookup"><span data-stu-id="c11d9-177">The required operating system version for each SRS installer version changes with every MSI release.</span></span> <span data-ttu-id="c11d9-178">特定の MSI で最適なオペレーティングシステムバージョンを判断するには、コンソールセットアップスクリプトを1回実行します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-178">To determine the best operating system version for a given MSI, run the console setup script once.</span></span> <span data-ttu-id="c11d9-179">詳細については、「 [System Center Configuration Manager を使用して Microsoft Teams ルームを展開](rooms-scale.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c11d9-179">To learn more, see [Deploy Microsoft Teams Rooms by using System Center Configuration Manager](rooms-scale.md).</span></span>

<span data-ttu-id="c11d9-180">Configuration Manager では、Microsoft Teams のルームユニットを展開して構成するために、多数のパッケージが必要です。</span><span class="sxs-lookup"><span data-stu-id="c11d9-180">Configuration Manager requires a number of packages to deploy and configure the Microsoft Teams Rooms units.</span></span>

<span data-ttu-id="c11d9-181">次のパッケージを作成して構成し、配布ポイントサーバーの役割が割り当てられている Configuration Manager サイトシステムに配布する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c11d9-181">You need to create and configure the following packages, and then distribute them to the Configuration Manager site systems that have been assigned the distribution point server role.</span></span>

| <span data-ttu-id="c11d9-182">**パッケージ名**</span><span class="sxs-lookup"><span data-stu-id="c11d9-182">**Package name**</span></span>                     | <span data-ttu-id="c11d9-183">**種類**</span><span class="sxs-lookup"><span data-stu-id="c11d9-183">**Type**</span></span>               | <span data-ttu-id="c11d9-184">**説明**</span><span class="sxs-lookup"><span data-stu-id="c11d9-184">**Description**</span></span>                                                                           |
|--------------------------------------|------------------------|-------------------------------------------------------------------------------------------|
| <span data-ttu-id="c11d9-185">SRS v2-SRS アプリケーションパッケージ</span><span class="sxs-lookup"><span data-stu-id="c11d9-185">SRS v2 - SRS Application Package</span></span>     | <span data-ttu-id="c11d9-186">ソフトウェアパッケージ</span><span class="sxs-lookup"><span data-stu-id="c11d9-186">Software package</span></span>       | <span data-ttu-id="c11d9-187">Microsoft Teams 室展開キット用パッケージ</span><span class="sxs-lookup"><span data-stu-id="c11d9-187">Package for the Microsoft Teams Rooms deployment kit</span></span>                                      |
| <span data-ttu-id="c11d9-188">SRS v2-Sysprep パッケージ</span><span class="sxs-lookup"><span data-stu-id="c11d9-188">SRS v2 - Sysprep Package</span></span>             | <span data-ttu-id="c11d9-189">ソフトウェアパッケージ</span><span class="sxs-lookup"><span data-stu-id="c11d9-189">Software package</span></span>       | <span data-ttu-id="c11d9-190">Microsoft Teams のルームユニットを構成するためのカスタムの unattend.xml パッケージ</span><span class="sxs-lookup"><span data-stu-id="c11d9-190">Package for the custom Unattended.xml to configure Microsoft Teams Rooms units</span></span>            |
| <span data-ttu-id="c11d9-191">SRS v2-セットアップ-SRSComputerName パッケージ</span><span class="sxs-lookup"><span data-stu-id="c11d9-191">SRS v2 - Set-SRSComputerName Package</span></span> | <span data-ttu-id="c11d9-192">ソフトウェアパッケージ</span><span class="sxs-lookup"><span data-stu-id="c11d9-192">Software package</span></span>       | <span data-ttu-id="c11d9-193">展開時にコンピューター名を割り当てる HTML アプリケーション (HTA) のパッケージ</span><span class="sxs-lookup"><span data-stu-id="c11d9-193">Package for the HTML application (HTA) to assign a computer name during the deployment</span></span>    |
| <span data-ttu-id="c11d9-194">SRS v2-SRS の設定を構成する</span><span class="sxs-lookup"><span data-stu-id="c11d9-194">SRS v2 - Configure SRS Setup</span></span>         | <span data-ttu-id="c11d9-195">ソフトウェアパッケージ</span><span class="sxs-lookup"><span data-stu-id="c11d9-195">Software package</span></span>       | <span data-ttu-id="c11d9-196">Microsoft Teams の会議アプリの展開を構成するパッケージ</span><span class="sxs-lookup"><span data-stu-id="c11d9-196">Package to configure deployment of the Microsoft Teams Rooms app</span></span>                          |
| <span data-ttu-id="c11d9-197">SRS v2-OS 更新プログラムパッケージ</span><span class="sxs-lookup"><span data-stu-id="c11d9-197">SRS v2 - OS Updates Package</span></span>          | <span data-ttu-id="c11d9-198">ソフトウェアパッケージ</span><span class="sxs-lookup"><span data-stu-id="c11d9-198">Software package</span></span>       | <span data-ttu-id="c11d9-199">必須のオペレーティングシステム更新プログラムを展開するパッケージ</span><span class="sxs-lookup"><span data-stu-id="c11d9-199">Package to deploy mandatory operating system updates</span></span>                                      |
| <span data-ttu-id="c11d9-200">SRS v2-ルート証明書パッケージ</span><span class="sxs-lookup"><span data-stu-id="c11d9-200">SRS v2 - Root Certificate Package</span></span>    | <span data-ttu-id="c11d9-201">ソフトウェアパッケージ</span><span class="sxs-lookup"><span data-stu-id="c11d9-201">Software package</span></span>       | <span data-ttu-id="c11d9-202">オプション-ルート証明書を展開するパッケージ (ドメインに参加しているユニットには必要ありません)</span><span class="sxs-lookup"><span data-stu-id="c11d9-202">Optional - Package to deploy the root certificate (not required for domain-joined units)</span></span>  |
| <span data-ttu-id="c11d9-203">SRS v2-Microsoft Monitoring Agent パッケージ</span><span class="sxs-lookup"><span data-stu-id="c11d9-203">SRS v2 - Microsoft Monitoring Agent Package</span></span> | <span data-ttu-id="c11d9-204">ソフトウェアパッケージ</span><span class="sxs-lookup"><span data-stu-id="c11d9-204">Software package</span></span>       | <span data-ttu-id="c11d9-205">オプション-Microsoft Operations Management Suite エージェントの展開と構成を行うパッケージ</span><span class="sxs-lookup"><span data-stu-id="c11d9-205">Optional - Package to deploy and configure the Microsoft Operations Management Suite agent</span></span>|
| <span data-ttu-id="c11d9-206">SRS v2-WinPE バックグラウンドパッケージ</span><span class="sxs-lookup"><span data-stu-id="c11d9-206">SRS v2 - WinPE Background Package</span></span>    | <span data-ttu-id="c11d9-207">ソフトウェアパッケージ</span><span class="sxs-lookup"><span data-stu-id="c11d9-207">Software package</span></span>       | <span data-ttu-id="c11d9-208">ブートイメージと共に使用するカスタムの背景イメージのパッケージ</span><span class="sxs-lookup"><span data-stu-id="c11d9-208">Package for the custom background image to use with boot images</span></span>                           |
| <span data-ttu-id="c11d9-209">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="c11d9-209">Windows 10 Enterprise</span></span>                | <span data-ttu-id="c11d9-210">オペレーティングシステムのイメージ</span><span class="sxs-lookup"><span data-stu-id="c11d9-210">Operating system image</span></span> | <span data-ttu-id="c11d9-211">オペレーティングシステムインストールファイル (.wim) のパッケージ</span><span class="sxs-lookup"><span data-stu-id="c11d9-211">Package for the operating system installation file (install.wim)</span></span>                          |
| <span data-ttu-id="c11d9-212">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="c11d9-212">Surface Pro</span></span>                          | <span data-ttu-id="c11d9-213">ドライバーパッケージ</span><span class="sxs-lookup"><span data-stu-id="c11d9-213">Driver package</span></span>         | <span data-ttu-id="c11d9-214">Microsoft Surface Pro のデバイスドライバーとファームウェアのパッケージ</span><span class="sxs-lookup"><span data-stu-id="c11d9-214">Package for the device drivers and firmware for Microsoft Surface Pro</span></span>                     |
| <span data-ttu-id="c11d9-215">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="c11d9-215">Surface Pro 4</span></span>                        | <span data-ttu-id="c11d9-216">ドライバーパッケージ</span><span class="sxs-lookup"><span data-stu-id="c11d9-216">Driver package</span></span>         | <span data-ttu-id="c11d9-217">Microsoft Surface Pro 4 のデバイスドライバーとファームウェアのパッケージ</span><span class="sxs-lookup"><span data-stu-id="c11d9-217">Package for the device drivers and firmware for Microsoft Surface Pro 4</span></span>                   |

<span data-ttu-id="c11d9-218">詳細については、「 [System Center Configuration Manager のパッケージとプログラム](https://docs.microsoft.com/sccm/apps/deploy-use/packages-and-programs)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c11d9-218">For more information, see [Packages and programs in System Center Configuration Manager](https://docs.microsoft.com/sccm/apps/deploy-use/packages-and-programs).</span></span>

### <a name="create-folders-for-the-package-source-files"></a><span data-ttu-id="c11d9-219">パッケージソースファイルのフォルダーを作成する</span><span class="sxs-lookup"><span data-stu-id="c11d9-219">Create folders for the package source files</span></span>

<span data-ttu-id="c11d9-220">Configuration Manager では、最初に作成され、更新されるときに、パッケージソースファイルを特定のフォルダー構造で整理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c11d9-220">Configuration Manager requires package source files to be organized in a specific folder structure when they’re first created and when they’re updated.</span></span>

<span data-ttu-id="c11d9-221">System Center Configuration Manager のサーバーの全体管理サイトまたはプライマリサイト、またはパッケージソースファイルのホストとして使用しているサーバー共有で、次のフォルダー構造を作成します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-221">Create the following folder structure on the System Center Configuration Manager central administration site or primary site, or on a server share you’re using to host package source files:</span></span>

-   <span data-ttu-id="c11d9-222">SRS v2-Microsoft Monitoring Agent パッケージ</span><span class="sxs-lookup"><span data-stu-id="c11d9-222">SRS v2 - Microsoft Monitoring Agent Package</span></span>
-   <span data-ttu-id="c11d9-223">SRS v2-OS 更新プログラムパッケージ</span><span class="sxs-lookup"><span data-stu-id="c11d9-223">SRS v2 - OS Updates Package</span></span>
-   <span data-ttu-id="c11d9-224">SRS v2-ルート証明書パッケージ</span><span class="sxs-lookup"><span data-stu-id="c11d9-224">SRS v2 - Root Certificate Package</span></span>
-   <span data-ttu-id="c11d9-225">SRS v2-セットアップ-SRSComputerName パッケージ</span><span class="sxs-lookup"><span data-stu-id="c11d9-225">SRS v2 - Set-SRSComputerName Package</span></span>
-   <span data-ttu-id="c11d9-226">SRS v2-SRS アプリケーションパッケージ</span><span class="sxs-lookup"><span data-stu-id="c11d9-226">SRS v2 - SRS Application Package</span></span>
-   <span data-ttu-id="c11d9-227">SRS v2-SRS の設定を構成する</span><span class="sxs-lookup"><span data-stu-id="c11d9-227">SRS v2 - Configure SRS Setup</span></span>
-   <span data-ttu-id="c11d9-228">SRS v2-Sysprep パッケージ</span><span class="sxs-lookup"><span data-stu-id="c11d9-228">SRS v2 - Sysprep Package</span></span>
-   <span data-ttu-id="c11d9-229">デバイス</span><span class="sxs-lookup"><span data-stu-id="c11d9-229">Drivers</span></span>
    -   <span data-ttu-id="c11d9-230">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="c11d9-230">Surface Pro</span></span>
    -   <span data-ttu-id="c11d9-231">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="c11d9-231">Surface Pro 4</span></span>
-   <span data-ttu-id="c11d9-232">オペレーティングシステム</span><span class="sxs-lookup"><span data-stu-id="c11d9-232">Operating Systems</span></span>
    -   <span data-ttu-id="c11d9-233">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="c11d9-233">Windows 10 Enterprise</span></span>

> [!TIP]
> <span data-ttu-id="c11d9-234">また、インポートする必要があるパッケージ、使用する必要があるスクリプト、およびタスクシーケンステンプレートのフォルダー構造を含む zip ファイルを[ダウンロード](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)して使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-234">You may also [download](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) and use the zip file that includes the folder structure for the packages, the scripts that you need to use, and the task sequence template, that you need to import.</span></span>

### <a name="create-the-monitoring-agent-package"></a><span data-ttu-id="c11d9-235">監視エージェントパッケージを作成する</span><span class="sxs-lookup"><span data-stu-id="c11d9-235">Create the Monitoring agent package</span></span>

1. <span data-ttu-id="c11d9-236">から<https://go.microsoft.com/fwlink/?LinkId=828603>監視エージェントをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="c11d9-236">Download the Monitoring agent from <https://go.microsoft.com/fwlink/?LinkId=828603>.</span></span>

2. <span data-ttu-id="c11d9-237">コマンドプロンプトウィンドウを開いて、コマンドプロンプトに**MMASetup-AMD64/c**を入力して、 **SRS V2-Microsoft Monitoring Agent パッケージ**フォルダーにパッケージを抽出します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-237">Extract the package into the **SRS v2 - Microsoft Monitoring Agent Package** folder by opening a Command Prompt window and entering **MMASetup-AMD64.exe /C:**     at the command prompt.</span></span>

3. <span data-ttu-id="c11d9-238">Configuration Manager コンソールで、[**ソフトウェアライブラリ** \> **アプリケーション管理** \> **パッケージ**] に移動し、[**パッケージの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-238">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4. <span data-ttu-id="c11d9-239">パッケージを作成するには、次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-239">Enter the following information to create the package:</span></span>

   - <span data-ttu-id="c11d9-240">名前<strong>: SRS v2-Microsoft Monitoring Agent パッケージ</strong></span><span class="sxs-lookup"><span data-stu-id="c11d9-240">Name<strong>: SRS v2 - Microsoft Monitoring Agent Package</strong></span></span>

   - <span data-ttu-id="c11d9-241">製造元<strong>: Microsoft Corporation</strong></span><span class="sxs-lookup"><span data-stu-id="c11d9-241">Manufacturer<strong>: Microsoft Corporation</strong></span></span>

   - <span data-ttu-id="c11d9-242">バージョン<strong>: 8.1.11081.0</strong> (ダウンロードしたインストールファイルのバージョンを入力します)</span><span class="sxs-lookup"><span data-stu-id="c11d9-242">Version<strong>: 8.1.11081.0</strong> (enter the version of the downloaded installation file)</span></span>

   - <span data-ttu-id="c11d9-243">[**このパッケージはソースファイルを含む**] チェックボックスをオンにして、 **SRS V2-Microsoft Monitoring Agent パッケージ**フォルダーへのパスを入力し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-243">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Microsoft Monitoring Agent Package** folder, and then select **Next**.</span></span>

5. <span data-ttu-id="c11d9-244">[**プログラムを作成しない**] を選び、[**次へ**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-244">Select **Do not create a program**, and then select **Next**.</span></span>

6. <span data-ttu-id="c11d9-245">[**設定の確認**] ページを確認して、[**次へ**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-245">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7. <span data-ttu-id="c11d9-246">[**閉じる**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-246">Select **Close**.</span></span>

### <a name="create-the-operating-system-updates-package"></a><span data-ttu-id="c11d9-247">オペレーティングシステムの更新パッケージを作成する</span><span class="sxs-lookup"><span data-stu-id="c11d9-247">Create the operating system updates package</span></span>

1. <span data-ttu-id="c11d9-248">**SRS v2-OS 更新パッケージ**フォルダーで、 **Install-SRSv2-OS-Updates**という名前の新しい PowerShell スクリプトを作成します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-248">In the **SRS v2 - OS Updates Package** folder, create a new PowerShell script named **Install-SRSv2-OS-Updates.ps1**.</span></span>

2. <span data-ttu-id="c11d9-249">次のスクリプトを**Install-SRSv2-OS-Updates**スクリプトにコピーします。</span><span class="sxs-lookup"><span data-stu-id="c11d9-249">Copy the script below into the **Install-SRSv2-OS-Updates.ps1** script.</span></span> <span data-ttu-id="c11d9-250">または、[ここ](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)から Install-SRSv2-OS-Updates スクリプトをダウンロードすることもできます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-250">Alternatively, you can download the Install-SRSv2-OS-Updates.ps1 script from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
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
3. <span data-ttu-id="c11d9-251">同じフォルダーに、必須の Windows 更新プログラムパッケージをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="c11d9-251">Download the mandatory Windows Update packages into the same folder.</span></span>
   > [!NOTE]
   > <span data-ttu-id="c11d9-252">この記事が公開された時点では、 [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu)のみが必要でした。</span><span class="sxs-lookup"><span data-stu-id="c11d9-252">At the time this article was published, only [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) was required.</span></span> <span data-ttu-id="c11d9-253">他の更新プログラムが必要かどうかを確認するには、 [Microsoft Teams のルームコンソールの構成](console.md)を確認します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-253">Check [Configure a Microsoft Teams Rooms console](console.md), to see whether any other updates are required.</span></span>

4. <span data-ttu-id="c11d9-254">Configuration Manager コンソールで、[**ソフトウェアライブラリ** \> **アプリケーション管理** \> **パッケージ**] に移動し、[**パッケージの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-254">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

5. <span data-ttu-id="c11d9-255">パッケージを作成するには、次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-255">Enter the following information to create the package:</span></span>
   -   <span data-ttu-id="c11d9-256">名前: **SRS v2 – OS 更新プログラムパッケージ**</span><span class="sxs-lookup"><span data-stu-id="c11d9-256">Name: **SRS v2 – OS Updates Package**</span></span>
   -   <span data-ttu-id="c11d9-257">製造元: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="c11d9-257">Manufacturer: **Microsoft Corporation**</span></span>
   -   <span data-ttu-id="c11d9-258">バージョン: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="c11d9-258">Version: **1.0.0**</span></span>
   -   <span data-ttu-id="c11d9-259">[**このパッケージはソースファイルを含む**] チェックボックスをオンにして、 **SRS V2-OS 更新パッケージ**フォルダーへのパスを入力し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-259">Select the **This package contains source files** check box, enter the path to the **SRS v2 - OS Updates Package** folder, and then select **Next**.</span></span>

6. <span data-ttu-id="c11d9-260">[**プログラムを作成しない**] を選び、[**次へ**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-260">Select **Do not create a program**, and then select **Next**.</span></span>

7. <span data-ttu-id="c11d9-261">[**設定の確認**] ページを確認して、[**次へ**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-261">Review the **Confirm the settings** page, and then select **Next**.</span></span>

8. <span data-ttu-id="c11d9-262">[**閉じる**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-262">Select **Close**.</span></span>

### <a name="create-the-root-certificate-package-optional"></a><span data-ttu-id="c11d9-263">ルート証明書パッケージを作成する (省略可能)</span><span class="sxs-lookup"><span data-stu-id="c11d9-263">Create the root certificate package (optional)</span></span>

<span data-ttu-id="c11d9-264">このパッケージを作成して、Active Directory ドメインに参加しないデバイスのルート証明書を配布します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-264">You create this package to distribute the root certificate for devices that won’t be joined to an Active Directory domain.</span></span> <span data-ttu-id="c11d9-265">このパッケージを作成するのは、次の両方の条件が当てはまる場合のみです。</span><span class="sxs-lookup"><span data-stu-id="c11d9-265">Create this package only if both the following conditions apply:</span></span>
-   <span data-ttu-id="c11d9-266">展開には、オンプレミスの Lync または Skype for Business Server が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-266">Your deployment includes on-premises Lync or Skype for Business Server.</span></span>
-   <span data-ttu-id="c11d9-267">Microsoft Teams のルームユニットは、ドメインメンバーではなくワークグループで機能するように構成されています。</span><span class="sxs-lookup"><span data-stu-id="c11d9-267">Microsoft Teams Rooms units are configured to work in a workgroup instead of a domain member.</span></span>

1.  <span data-ttu-id="c11d9-268">ルート証明書を**SRS v2 –ルート証明書パッケージ**フォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="c11d9-268">Copy the root certificate into the **SRS v2 – Root Certificate Package** folder.</span></span>

2.  <span data-ttu-id="c11d9-269">Configuration Manager コンソールで、[**ソフトウェアライブラリ** \> **アプリケーション管理** \> **パッケージ**] に移動し、[**パッケージの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-269">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

3.  <span data-ttu-id="c11d9-270">パッケージを作成するには、次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-270">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="c11d9-271">名前: **SRS v2 –ルート証明書パッケージ**</span><span class="sxs-lookup"><span data-stu-id="c11d9-271">Name: **SRS v2 – Root Certificate Package**</span></span>
    -   <span data-ttu-id="c11d9-272">製造元:*組織の名前*</span><span class="sxs-lookup"><span data-stu-id="c11d9-272">Manufacturer: *Your organization’s name*</span></span>
    -   <span data-ttu-id="c11d9-273">バージョン: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="c11d9-273">Version: **1.0.0**</span></span>
    -   <span data-ttu-id="c11d9-274">[**このパッケージはソースファイルを含む**] チェックボックスをオンにして、 **SRS V2 –ルート証明書パッケージ**フォルダーへのパスを入力し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-274">Select the **This package contains source files** check box, enter the path to the **SRS v2 – Root Certificate Package** folder, and then select **Next**.</span></span>

4.  <span data-ttu-id="c11d9-275">[**プログラムを作成しない**] を選び、[**次へ**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-275">Select **Do not create a program**, and then select **Next**.</span></span>

5.  <span data-ttu-id="c11d9-276">[**設定の確認**] ページを確認して、[**次へ**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-276">Review the **Confirm the settings** page, and then select **Next**.</span></span>

6.  <span data-ttu-id="c11d9-277">[**閉じる**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-277">Select **Close**.</span></span>

### <a name="create-the-microsoft-teams-rooms-deployment-kit-package"></a><span data-ttu-id="c11d9-278">Microsoft Teams のルーム展開キットパッケージを作成する</span><span class="sxs-lookup"><span data-stu-id="c11d9-278">Create the Microsoft Teams Rooms deployment kit package</span></span>

1.  <span data-ttu-id="c11d9-279">から<https://go.microsoft.com/fwlink/?linkid=851168>最新バージョンの**Microsoft Teams ルーム展開キット**をダウンロードして、ワークステーションにインストールします。</span><span class="sxs-lookup"><span data-stu-id="c11d9-279">Download the latest version of the **Microsoft Teams Rooms deployment kit** from <https://go.microsoft.com/fwlink/?linkid=851168>, and install it to a workstation.</span></span>

2.  <span data-ttu-id="c11d9-280">**C:\\Program Files (x86)\\Skype Room System Deployment Kit**から、 **srs v2-srs アプリケーションパッケージ**フォルダーにコンテンツをコピーします。</span><span class="sxs-lookup"><span data-stu-id="c11d9-280">Copy the content from **C:\\Program Files (x86)\\Skype Room System Deployment Kit** to the **SRS v2 - SRS Application Package** folder.</span></span>

3.  <span data-ttu-id="c11d9-281">Configuration Manager コンソールで、[**ソフトウェアライブラリ** \> **アプリケーション管理** \> **パッケージ**] に移動し、[**パッケージの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-281">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="c11d9-282">パッケージを作成するには、次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-282">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="c11d9-283">名前: **srs v2 – Srs アプリケーションパッケージ**</span><span class="sxs-lookup"><span data-stu-id="c11d9-283">Name: **SRS v2 – SRS Application Package**</span></span>
    -   <span data-ttu-id="c11d9-284">製造元: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="c11d9-284">Manufacturer: **Microsoft Corporation**</span></span>
    -   <span data-ttu-id="c11d9-285">バージョン: **3.1.104.0** (ダウンロードしたインストールファイルのバージョンを入力します)</span><span class="sxs-lookup"><span data-stu-id="c11d9-285">Version: **3.1.104.0** (enter the version of the downloaded installation file)</span></span>
    -   <span data-ttu-id="c11d9-286">[**このパッケージはソースファイルを含む**] チェックボックスをオンにして、 **SRS V2 – srs アプリケーションパッケージ**フォルダーへのパスを入力し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-286">Select the **This package contains source files** check box, enter the path to the **SRS v2 – SRS Application Package** folder, and then select **Next**.</span></span>
5.  <span data-ttu-id="c11d9-287">[**プログラムを作成しない**] を選び、[**次へ**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-287">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="c11d9-288">[**設定の確認**] ページを確認して、[**次へ**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-288">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="c11d9-289">[**閉じる**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-289">Select **Close**.</span></span>

### <a name="create-the-computer-name-assignment-package"></a><span data-ttu-id="c11d9-290">コンピューター名割り当てパッケージを作成する</span><span class="sxs-lookup"><span data-stu-id="c11d9-290">Create the computer name assignment package</span></span>

1.  <span data-ttu-id="c11d9-291">[ **SRS v2-セットアップ-SRSComputerName パッケージ**] フォルダーで、 **Set-SRSComputerName**という名前の新しい HTML アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-291">In the **SRS v2 - Set-SRSComputerName Package** folder, create a new HTML application named **Set-SRSComputerName.hta** .</span></span>

2.  <span data-ttu-id="c11d9-292">次のスクリプトを**Set-SRSComputerName**ファイルにコピーします。</span><span class="sxs-lookup"><span data-stu-id="c11d9-292">Copy the following script into the **Set-SRSComputerName.hta** file.</span></span> <span data-ttu-id="c11d9-293">または、[ここ](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)から Set-SRSComputerName ファイルをダウンロードすることもできます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-293">Alternatively, you can download the Set-SRSComputerName.hta file from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
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
3.  <span data-ttu-id="c11d9-294">Configuration Manager コンソールで、[**ソフトウェアライブラリ** \> **アプリケーション管理** \> **パッケージ**] に移動し、[**パッケージの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-294">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="c11d9-295">パッケージを作成するには、次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-295">Enter the following information to create the package:</span></span>

    -   <span data-ttu-id="c11d9-296">名前: **SRS v2-セットアップ-SRSComputerName パッケージ**</span><span class="sxs-lookup"><span data-stu-id="c11d9-296">Name: **SRS v2 - Set-SRSComputerName Package**</span></span>

    -   <span data-ttu-id="c11d9-297">製造元: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="c11d9-297">Manufacturer: **Microsoft Corporation**</span></span>

    -   <span data-ttu-id="c11d9-298">バージョン: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="c11d9-298">Version: **1.0.0**</span></span>

    -   <span data-ttu-id="c11d9-299">[**このパッケージはソースファイルを含む**] チェックボックスをオンにして、 **SRS v2-セットアップ-Srscomputername パッケージ**フォルダーへのパスを入力し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-299">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Set-SRSComputerName Package** folder, and then select **Next**.</span></span>

5.  <span data-ttu-id="c11d9-300">[**プログラムを作成しない**] を選び、[**次へ**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-300">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="c11d9-301">[**設定の確認**] ページを確認して、[**次へ**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-301">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="c11d9-302">[**閉じる**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-302">Select **Close**.</span></span>

### <a name="create-the-sysprep-package"></a><span data-ttu-id="c11d9-303">Sysprep パッケージを作成する</span><span class="sxs-lookup"><span data-stu-id="c11d9-303">Create the Sysprep package</span></span>

1. <span data-ttu-id="c11d9-304">[ **SRS v2 – Sysprep パッケージ]** フォルダーで、 **unattend.xml**という名前の新しい xml ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-304">In the **SRS v2 – Sysprep Package** folder, create a new XML file named **Unattend.xml** .</span></span>

2. <span data-ttu-id="c11d9-305">次のテキストを**unattend.xml**ファイルにコピーします。</span><span class="sxs-lookup"><span data-stu-id="c11d9-305">Copy the following text into the **Unattend.xml** file.</span></span> <span data-ttu-id="c11d9-306">または、[ここ](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)から unattend.xml ファイルをダウンロードすることもできます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-306">Alternatively, you can download the Unattend.xml file from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
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
3. <span data-ttu-id="c11d9-307">Configuration Manager コンソールで、[**ソフトウェアライブラリ** \> **アプリケーション管理** \> **パッケージ**] に移動し、[**パッケージの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-307">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4. <span data-ttu-id="c11d9-308">パッケージを作成するには、次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-308">Enter the following information to create the package:</span></span>
   -   <span data-ttu-id="c11d9-309">名前: **SRS v2-Sysprep パッケージ**</span><span class="sxs-lookup"><span data-stu-id="c11d9-309">Name: **SRS v2 - Sysprep Package**</span></span>
   -   <span data-ttu-id="c11d9-310">製造元: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="c11d9-310">Manufacturer: **Microsoft Corporation**</span></span>
   -   <span data-ttu-id="c11d9-311">バージョン: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="c11d9-311">Version: **1.0.0**</span></span>
   -   <span data-ttu-id="c11d9-312">[**このパッケージはソースファイルを含む**] チェックボックスをオンにし、[ **SRS V2 – Sysprep パッケージ**] フォルダーへのパスを入力して、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-312">Select the **This package contains source files** check box, enter the path to the **SRS v2 – Sysprep Package** folder, and then select **Next**.</span></span>
5. <span data-ttu-id="c11d9-313">[**プログラムを作成しない**] を選び、[**次へ**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-313">Select **Do not create a program**, and then select **Next**.</span></span>

6. <span data-ttu-id="c11d9-314">[**設定の確認**] ページを確認して、[**次へ**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-314">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7. <span data-ttu-id="c11d9-315">[**閉じる**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-315">Select **Close**.</span></span>

### <a name="create-the-windows-10-enterprise-package"></a><span data-ttu-id="c11d9-316">Windows 10 Enterprise パッケージを作成する</span><span class="sxs-lookup"><span data-stu-id="c11d9-316">Create the Windows 10 Enterprise package</span></span>

1.  <span data-ttu-id="c11d9-317">Windows 10 Enterprise x64 メディアを取得し、**インストール .wim**ファイルを**オペレーティングシステム\\の Windows 10 enterprise**フォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="c11d9-317">Obtain a Windows 10 Enterprise x64 media, and copy the **install.wim** file to the **Operating Systems\\Windows 10 Enterprise** folder.</span></span>

2.  <span data-ttu-id="c11d9-318">Configuration Manager コンソールで、[**ソフトウェアライブラリ** \> **オペレーティング** \>システムの**オペレーティングシステムイメージ**] に移動し、[**オペレーティングシステムイメージの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-318">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Operating System Images**, and then select **Add Operating System Image**.</span></span>

3.  <span data-ttu-id="c11d9-319">コピーした**インストール .wim**ファイルへのパスを指定し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-319">Specify the path to the **install.wim** file you just copied, and then select **Next**.</span></span>

4.  <span data-ttu-id="c11d9-320">[**バージョン**] フィールドを更新して、Windows 10 Enterprise のイメージのビルド番号と一致するようにし、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-320">Update the **Version** field to match the build number of the Windows 10 Enterprise image, and then select **Next**.</span></span>

5.  <span data-ttu-id="c11d9-321">[**詳細**] ページを確認し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-321">Review the **Details** page, and then select **Next**.</span></span>

6.  <span data-ttu-id="c11d9-322">[**閉じる**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-322">Select **Close**.</span></span>

<span data-ttu-id="c11d9-323">詳細については、「 [System Center Configuration Manager を使用してオペレーティングシステムのイメージを管理](https://docs.microsoft.com/sccm/osd/get-started/manage-operating-system-images)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c11d9-323">For more information, see [Manage operating system images with System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-operating-system-images).</span></span>

### <a name="create-surface-pro-device-driver-packages"></a><span data-ttu-id="c11d9-324">Surface Pro デバイスドライバーパッケージを作成する</span><span class="sxs-lookup"><span data-stu-id="c11d9-324">Create Surface Pro device driver packages</span></span>

<span data-ttu-id="c11d9-325">Microsoft Teams のルームは Surface Pro と Surface Pro 4 の両方でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="c11d9-325">Microsoft Teams Rooms is supported for both Surface Pro and Surface Pro 4.</span></span> <span data-ttu-id="c11d9-326">環境内にある Surface Pro モデルごとにドライバーパッケージを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c11d9-326">You need to create a driver package for each Surface Pro model you have in your environment.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c11d9-327">ドライバーは、Windows 10 Enterprise ビルドおよび Microsoft Teams 室展開キットのバージョンと互換性がある必要があります。</span><span class="sxs-lookup"><span data-stu-id="c11d9-327">The drivers must be compatible with the Windows 10 Enterprise build and the Microsoft Teams Rooms deployment kit version.</span></span> <span data-ttu-id="c11d9-328">詳細については、「 [Surface デバイス用の最新のファームウェアとドライバーをダウンロード](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices)して[本体を構成する](console.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c11d9-328">For more information, see [Download the latest firmware and drivers for Surface devices](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) and [Configure a console](console.md).</span></span>

1.  <span data-ttu-id="c11d9-329">最新のドライバーとファームウェアをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="c11d9-329">Download the latest drivers and firmware.</span></span>
    -   <span data-ttu-id="c11d9-330">Surface Pro の場合:<https://www.microsoft.com/download/details.aspx?id=55484></span><span class="sxs-lookup"><span data-stu-id="c11d9-330">For Surface Pro: <https://www.microsoft.com/download/details.aspx?id=55484></span></span>
    -   <span data-ttu-id="c11d9-331">Surface Pro 4 の場合:<https://www.microsoft.com/download/details.aspx?id=49498></span><span class="sxs-lookup"><span data-stu-id="c11d9-331">For Surface Pro 4: <https://www.microsoft.com/download/details.aspx?id=49498></span></span>

2.  <span data-ttu-id="c11d9-332">ダウンロードしたドライバーとファームウェアを抽出します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-332">Extract the downloaded driver and firmware.</span></span> <span data-ttu-id="c11d9-333">コマンドプロンプトウィンドウを開き、コマンドプロンプトで次のいずれかのコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-333">Open a Command Prompt window and at the command prompt, enter one of the following commands:</span></span>
    -   `msiexec /a C:\SurfacePro_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro"`
    -   `msiexec /a C:\SurfacePro4_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro 4"`

3.  <span data-ttu-id="c11d9-334">Configuration Manager コンソールで、[**ソフトウェアライブラリ** \> **オペレーティングシステム** \> **ドライバー**] に移動し、[**ドライバーのインポート**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-334">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Drivers**, and then select **Import Driver**.</span></span>

4.  <span data-ttu-id="c11d9-335">[**次のネットワークパス (UNC) のすべてのドライバーをインポートする**] を選択し、ソースフォルダー (\\たとえば\\、\\C: _Sources Drivers Surface Pro) を選び、[**次へ**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-335">Select **Import all drivers in the following network path (UNC)**, select the source folder (for example, C:\\_Sources\\Drivers\\Surface Pro), and then select **Next**.</span></span>

5.  <span data-ttu-id="c11d9-336">[**インポートしたドライバーの詳細を指定**してください] ページで、一覧表示されているすべてのドライバーを選び、[これらのドライバーを有効にする] を選択して、[**コンピューターにインストールを許可する**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-336">On the **Specify the details for the imported drivers** page, select all the listed drivers, and then select **Enable these drivers and allow computers to install them**.</span></span>

6.  <span data-ttu-id="c11d9-337">[**カテゴリ**] を選択し、Surface モデルに一致する新しいカテゴリを作成して、[ **OK**] を選択し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-337">Select **Categories**, create a new category that matches the Surface model, select **OK**, and then select **Next**.</span></span>

7.  <span data-ttu-id="c11d9-338">[**新しいパッケージ**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-338">Select **New Package**.</span></span>

8.  <span data-ttu-id="c11d9-339">Surface Pro モデルと一致するパッケージ名を指定し、ドライバーパッケージファイルを保存するフォルダーパスを入力して、[ **OK**] を選択し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-339">Specify the package name that matches the Surface Pro model, enter a folder path to store the driver package files in, select **OK**, and then select **Next**.</span></span>

9.  <span data-ttu-id="c11d9-340">[**ブートイメージ**] ページで、[ブートイメージ] が選択されていないことを確認し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-340">On the **boot images** page, ensure that no boot images are selected, and then select **Next**.</span></span>

10. <span data-ttu-id="c11d9-341">[**閉じる**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-341">Select **Close**.</span></span>

11. <span data-ttu-id="c11d9-342">[ **Software Library** \> **オペレーティングシステム** \> **ドライバー**] に移動し、[フォルダーの\*\* \>作成] フォルダー\*\*を選択し、ドライバーをインポートした Surface Pro モデルと一致するフォルダー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-342">Go to **Software Library** \> **Operating Systems** \> **Drivers**, select **Folder \> Create Folder**, and enter a folder name that matches the Surface Pro model that you just imported the drivers for.</span></span>

12. <span data-ttu-id="c11d9-343">新しく作成したフォルダーに、インポートされたすべてのドライバーを移動して、移動や操作が簡単にできるようにします。</span><span class="sxs-lookup"><span data-stu-id="c11d9-343">Move all the imported drivers to the newly created folder for easier navigation and operation.</span></span>

> [!NOTE]
> <span data-ttu-id="c11d9-344">他の Surface Pro モデルにも同じ手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-344">Repeat the same steps for other Surface Pro models you might have.</span></span> <span data-ttu-id="c11d9-345">詳細については、「 [System Center Configuration Manager でドライバーを管理](https://docs.microsoft.com/sccm/osd/get-started/manage-drivers)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c11d9-345">For more information, see [Manage drivers in System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-drivers).</span></span>

### <a name="create-microsoft-teams-rooms-configuration-package"></a><span data-ttu-id="c11d9-346">Microsoft Teams 会議室構成パッケージを作成する</span><span class="sxs-lookup"><span data-stu-id="c11d9-346">Create Microsoft Teams Rooms Configuration Package</span></span>

1.  <span data-ttu-id="c11d9-347">Configuration Manager コンソールで、[**ソフトウェアライブラリ** \> **アプリケーション管理** \> **パッケージ**] に移動し、[**パッケージの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-347">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

2.  <span data-ttu-id="c11d9-348">パッケージを作成するには、次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-348">Enter the following information to create the package:</span></span>

    -   <span data-ttu-id="c11d9-349">名前: **srs v2-Srs セットアップパッケージを構成する**</span><span class="sxs-lookup"><span data-stu-id="c11d9-349">Name: **SRS v2 - Configure SRS Setup Package**</span></span>

    -   <span data-ttu-id="c11d9-350">製造元: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="c11d9-350">Manufacturer: **Microsoft Corporation**</span></span>

    -   <span data-ttu-id="c11d9-351">バージョン: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="c11d9-351">Version: **1.0.0**</span></span>

    -   <span data-ttu-id="c11d9-352">[**このパッケージはソースファイルを含む**] チェックボックスをオンにし、[ **SRS V2-srs セットアップ**] フォルダーへのパスを入力して、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-352">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Configure SRS Setup** folder, and then select **Next**.</span></span>

3.  <span data-ttu-id="c11d9-353">[**プログラムを作成しない**] を選び、[**次へ**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-353">Select **Do not create a program**, and then select **Next**.</span></span>

4.  <span data-ttu-id="c11d9-354">[**設定の確認**] ページを確認して、[**次へ**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-354">Review the **Confirm the settings** page, and then select **Next**.</span></span>

5.  <span data-ttu-id="c11d9-355">[**閉じる**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-355">Select **Close**.</span></span>



## <a name="distribute-configuration-manager-packages"></a><span data-ttu-id="c11d9-356">Configuration Manager パッケージを配布する</span><span class="sxs-lookup"><span data-stu-id="c11d9-356">Distribute Configuration Manager packages</span></span>

<span data-ttu-id="c11d9-357">すべてのパッケージは、構成マネージャー階層で配布ポイントの役割が割り当てられているサーバーに配布する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c11d9-357">All the packages must be distributed to the servers that have been assigned the distribution point role in the Configuration Manager hierarchy.</span></span> <span data-ttu-id="c11d9-358">パッケージの配布を開始するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="c11d9-358">Follow the instructions below to initiate package distribution.</span></span>

1.  <span data-ttu-id="c11d9-359">ソフトウェアパッケージを配布します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-359">Distribute software packages.</span></span>

    1.  <span data-ttu-id="c11d9-360">Configuration Manager コンソールで、[**ソフトウェアライブラリ** \> **アプリケーション管理** \> **パッケージ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-360">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**.</span></span> <span data-ttu-id="c11d9-361">配布するすべてのソフトウェアパッケージを選択し、[コンテンツの**配布**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-361">Select all the software packages you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="c11d9-362">パッケージの一覧を確認し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-362">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="c11d9-363">すべての配布ポイントサーバー (構成マネージャーの階層に応じて配布ポイントグループ) を一覧に追加し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-363">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="c11d9-364">[**次へ**] を選択し、[**閉じる**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-364">Select **Next**, and then select **Close**.</span></span>

2.  <span data-ttu-id="c11d9-365">ドライバーパッケージを配布します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-365">Distribute driver packages.</span></span>

    1.  <span data-ttu-id="c11d9-366">Configuration Manager コンソールで、[**ソフトウェアライブラリ** \> **オペレーティングシステム** \> **ドライバーパッケージ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-366">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Driver Packages**.</span></span> <span data-ttu-id="c11d9-367">配布するドライバーパッケージをすべて選択し、[**コンテンツの配布**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-367">Select all the driver packages you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="c11d9-368">パッケージの一覧を確認し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-368">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="c11d9-369">すべての配布ポイントサーバー (構成マネージャーの階層に応じて配布ポイントグループ) を一覧に追加し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-369">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="c11d9-370">[**次へ**] を選択し、[**閉じる**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-370">Select **Next**, and then select **Close**.</span></span>

3.  <span data-ttu-id="c11d9-371">オペレーティングシステムパッケージを配布します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-371">Distribute operating system packages.</span></span>

    1.  <span data-ttu-id="c11d9-372">Configuration Manager コンソールで、[**ソフトウェアライブラリ** \> **オペレーティング** \>システムの**オペレーティングシステムイメージ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-372">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Operating System Images**.</span></span> <span data-ttu-id="c11d9-373">配布するすべてのオペレーティングシステムイメージを選択し、[コンテンツの**配布**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-373">Select all the operating system images you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="c11d9-374">パッケージの一覧を確認し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-374">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="c11d9-375">すべての配布ポイントサーバー (構成マネージャーの階層に応じて配布ポイントグループ) を一覧に追加し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-375">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="c11d9-376">[**次へ**] を選択し、[**閉じる**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-376">Select **Next**, and then select **Close**.</span></span>

> [!NOTE]
> <span data-ttu-id="c11d9-377">パッケージの配布には、パッケージサイズ、構成マネージャー階層、配布ポイントサーバーの数、ネットワークで利用可能な帯域幅に応じて、時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c11d9-377">Package distribution might take some time, depending on the package size, Configuration Manager hierarchy, number of distribution point servers, and the bandwidth available in your network.</span></span>
> 
> <span data-ttu-id="c11d9-378">Microsoft Teams のルームユニットの展開を開始する前に、すべてのパッケージを配布する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c11d9-378">All the packages must be distributed before you can start deploying a Microsoft Teams Rooms unit.</span></span>
> 
> <span data-ttu-id="c11d9-379">Configuration Manager コンソールでパッケージ配布の状態を確認するには、「**配布ステータス** \> **コンテンツの状態**を**監視** \>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c11d9-379">You can review the status of your package distribution in the Configuration Manager console by going to **Monitoring** \> **Distribution Status** \> **Content Status**.</span></span>

## <a name="configuration-manager-task-sequences"></a><span data-ttu-id="c11d9-380">構成マネージャーのタスクシーケンス</span><span class="sxs-lookup"><span data-stu-id="c11d9-380">Configuration Manager task sequences</span></span>

<span data-ttu-id="c11d9-381">タスクシーケンスは System Center Configuration Manager と共に使用して、オペレーティングシステムイメージを送信先コンピューターに展開するための手順を自動化します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-381">You use task sequences with System Center Configuration Manager to automate the steps for deploying an operating system image to a destination computer.</span></span> <span data-ttu-id="c11d9-382">自動的な方法で Microsoft Teams ルームユニットを展開するには、展開先の Microsoft Teams 室のコンピューター、インストールする Windows 10 Enterprise オペレーティングシステムのイメージを開始するために使用されるブートイメージを参照するタスクシーケンスを作成します。その他のアプリケーションやソフトウェア更新プログラムなどのその他のコンテンツ。</span><span class="sxs-lookup"><span data-stu-id="c11d9-382">To deploy a Microsoft Teams Rooms unit in an automated fashion, you create a task sequence that references the boot image used to start the destination Microsoft Teams Rooms computer, the Windows 10 Enterprise operating system image that you want to install, and any other additional content, such as other applications or software updates.</span></span>

### <a name="import-the-sample-task-sequence"></a><span data-ttu-id="c11d9-383">サンプルのタスクシーケンスをインポートする</span><span class="sxs-lookup"><span data-stu-id="c11d9-383">Import the sample task sequence</span></span>

<span data-ttu-id="c11d9-384">サンプルのタスクシーケンスをダウンロードして簡単にインポートし、ニーズに合わせてカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-384">You can download and easily import a sample task sequence and customize it to meet your needs.</span></span>

1.  <span data-ttu-id="c11d9-385">サンプルタスクシーケンスを[**ダウンロード**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)して、ダウンロードした zip ファイルを共有の場所にコピーします。</span><span class="sxs-lookup"><span data-stu-id="c11d9-385">[**Download**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) the sample task sequence, and copy the downloaded zip file to a shared location.</span></span>
2.  <span data-ttu-id="c11d9-386">Configuration Manager コンソールで、[**ソフトウェアライブラリ** \>の**オペレーティングシステム** \>の**タスクシーケンス**] に移動し、[**タスクシーケンスのインポート**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-386">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Task Sequences**, and then select **Import Task Sequence**.</span></span>

3.  <span data-ttu-id="c11d9-387">[**参照**] を選択し、手順1で使用した共有フォルダーの場所に移動し、 **Microsoft Teams のルーム展開 (en-us)** ファイルを選択して、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-387">Select **Browse**, go to the shared folder location you used in step 1, select the **Microsoft Teams Rooms Deployment (EN-US).zip** file, and then select **Next**.</span></span>

4.  <span data-ttu-id="c11d9-388">[**新規作成**]**アクション**を設定して、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-388">Set **Action** to **Create New**, and then select **Next**.</span></span>

5.  <span data-ttu-id="c11d9-389">設定を確認し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-389">Confirm the settings, and then select **Next**.</span></span>

6.  <span data-ttu-id="c11d9-390">[**閉じる**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-390">Select **Close**.</span></span>

### <a name="validate-that-the-reference-packages-are-correctly-linked-to-each-task-sequence-step"></a><span data-ttu-id="c11d9-391">参照パッケージが各タスクシーケンスの手順に正しくリンクされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-391">Validate that the reference packages are correctly linked to each task sequence step.</span></span>

1. <span data-ttu-id="c11d9-392">インポートしたタスクシーケンスを選択し、[**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-392">Select the imported task sequence, and then select **Edit**.</span></span>

    <span data-ttu-id="c11d9-393">タスクシーケンスエディターが開き、Microsoft Teams のルームユニットを展開して構成するために必要な一連の手順が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-393">The Task Sequence Editor opens and displays each sequential step that you need to deploy and configure a Microsoft Teams Rooms unit.</span></span>

2. <span data-ttu-id="c11d9-394">各手順を順番に実行し、推奨される更新プログラムを完了します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-394">Walk through each step and complete the recommended updates:</span></span>

   1. <span data-ttu-id="c11d9-395">**WINDOWS PE で再起動**します。この手順では、コンピューターが再起動し、windows PXE が起動されます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-395">**Restart in Windows PE**: This step restarts and then boots the computer into Windows PXE.</span></span> <span data-ttu-id="c11d9-396">この手順で変更を加える必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c11d9-396">No changes are required for this step.</span></span>

   2. <span data-ttu-id="c11d9-397">**パーティションディスク0– UEFI**: この手順を実行すると、ディスク構成が消去され、構成された設定に基づいてパーティションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-397">**Partition Disk 0 – UEFI**: This step wipes the disk configuration and creates partitions based on the configured settings.</span></span> <span data-ttu-id="c11d9-398">この手順には変更を加えないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c11d9-398">We recommend that you not make any changes to this step.</span></span>

   3. <span data-ttu-id="c11d9-399">**SRS コンピューター名を設定**する: この手順には、展開時に Microsoft Teams のルームユニットのコンピューター名を設定するための UI を提供する HTML アプリケーションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c11d9-399">**Set SRS Computer Name**: This step includes an HTML application to provide a UI to set a computer name for the Microsoft Teams Rooms unit during the deployment.</span></span>
      -  <span data-ttu-id="c11d9-400">これは省略可能な手順ですが、別のプロセスでコンピューターの名前付けを管理する場合にのみ無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-400">This is an optional step, but it can only be disabled if you want to manage computer naming through an alternate process.</span></span>
      -  <span data-ttu-id="c11d9-401">**SRS v2-セットアップ-SRSComputerName**パッケージが選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-401">Verify that the **SRS v2 - Set-SRSComputerName** package is selected.</span></span> <span data-ttu-id="c11d9-402">表示されていない場合は、パッケージを参照して選択します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-402">If it isn’t, browse to the package and select it.</span></span>

   4. <span data-ttu-id="c11d9-403">**オペレーティングシステムの適用**: この手順では、展開するオペレーティングシステムイメージと、使用する無人 Sysprep 応答ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-403">**Apply Operating System**: This step specifies the operating system image to be deployed and the unattended Sysprep answer file to use.</span></span>
      -  <span data-ttu-id="c11d9-404">正しい Windows 10 Enterprise オペレーティングシステムイメージファイルが選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-404">Verify that the correct Windows 10 Enterprise operating system image file is selected.</span></span>
      -  <span data-ttu-id="c11d9-405">**カスタムインストールに無人または sysprep の応答ファイルを使用**する機能が有効になっていることを確認し、[ **SRS V2-sysprep パッケージ**] が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-405">Verify that **Use an unattended or Sysprep answer file for a custom installation** is enabled, and the **SRS v2 - Sysprep Package** is selected.</span></span> <span data-ttu-id="c11d9-406">また、**ファイル名**が**unattend.xml**に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-406">Also ensure that **File Name** is set to **unattend.xml**.</span></span>

   5. <span data-ttu-id="c11d9-407">**Windows の設定を適用**する: この手順では、windows インストールに関する情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-407">**Apply Windows Settings**: This step gathers information about the Windows installation.</span></span>
      -  <span data-ttu-id="c11d9-408">プロダクトキー、ローカル管理者アカウントのパスワード、タイムゾーン (必要に応じて) を含む、ライセンスおよび登録情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-408">Provide licensing and registration information including the product key, local administrator account password, and time zone (depending on your needs).</span></span>

   6. <span data-ttu-id="c11d9-409">**ネットワーク設定を適用**する: この手順では、ワークグループまたは Active Directory ドメイン名と組織単位を指定できます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-409">**Apply Network Settings**: This step allows you to specify a workgroup or Active Directory domain name and organizational unit.</span></span>
      > [!NOTE]
      > <span data-ttu-id="c11d9-410">「 [Skype Room System domain](domain-joining-considerations.md) 」をご覧ください。推奨される操作については、「Microsoft Teams ルームユニットを Actve ディレクトリドメインのメンバーとして展開する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c11d9-410">See [Skype Room System domain joining considerations](domain-joining-considerations.md) for recommended actions you need to take in deploying Microsoft Teams Rooms units as members of an Actve Directory domain.</span></span>
   7. <span data-ttu-id="c11d9-411">**ドライバーを適用します。** この手順とサブステップを使って、使用している Surface Pro モデルに基づいて、該当するデバイスドライバーとファームウェアを展開します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-411">**Apply Drivers:** This step and its sub-steps are used to deploy applicable device drivers and firmware based on the Surface Pro model you have.</span></span> <span data-ttu-id="c11d9-412">各手順を更新して、この展開に関連する関連するドライバーパッケージを指定します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-412">Update each step to specify the relevant driver package associated with this deployment.</span></span>
      -   <span data-ttu-id="c11d9-413">各ドライバパッケージは、Windows Management Instrumentation (WMI) フィルターを活用して Surface Pro の作成とモデルに基づいて関連するドライバーとファームウェアを展開するように構成されています。</span><span class="sxs-lookup"><span data-stu-id="c11d9-413">Each driver package is configured to leverage Windows Management Instrumentation (WMI) filters to deploy relevant drivers and firmware based on the Surface Pro make and model.</span></span>
      -   <span data-ttu-id="c11d9-414">これらのドライバーの構成を変更しないようにすることを強くお勧めします。そうしないと、展開が失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c11d9-414">We highly recommend that you not alter the configuration of these drivers, otherwise deployment might fail.</span></span>

   8. <span data-ttu-id="c11d9-415">**Windows と構成マネージャーのセットアップ**: この手順では、configuration manager クライアントを展開して構成します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-415">**Set up Windows and Configuration Manager**: This step deploys and configures the Configuration Manager client.</span></span> <span data-ttu-id="c11d9-416">この手順を更新して、組み込みの Configuration Manager クライアントパッケージを指定します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-416">Update this step to specify the built-in Configuration Manager Client Package.</span></span>

   9. <span data-ttu-id="c11d9-417">[**ルート証明書のインストール**]: この手順では、ドメインに参加していないデバイスのルート証明書を配布します。そのため、既定ではオプションで無効になります。</span><span class="sxs-lookup"><span data-stu-id="c11d9-417">**Install Root Certificate**: This step distributes the root certificate for non–domain-joined devices, and therefore is optional and disabled by default.</span></span>
      -   <span data-ttu-id="c11d9-418">Microsoft Teams のルームユニットにルート証明書を展開する必要がある場合は、この手順を有効にします。</span><span class="sxs-lookup"><span data-stu-id="c11d9-418">Enable this step if you need to deploy a root certificate to the Microsoft Teams Rooms units.</span></span>
      -   <span data-ttu-id="c11d9-419">この手順を実行する必要がある場合は、 **SRS v2 –ルート証明書パッケージ**と**64 ビットファイルシステムリダイレクション**が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-419">If you do need to perform this step, verify that the **SRS v2 – Root Certificate Package** and **Disable 64-bit file system redirection** are selected.</span></span>

   10. <span data-ttu-id="c11d9-420">**Monitoring Agent のインストールと構成**: この手順では、64ビットバージョンの Microsoft Azure Monitor エージェントをインストールし、ログ分析ワークスペースに接続するようにエージェントを構成します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-420">**Install and Configure Monitoring Agent**: This step installs the 64-bit version of the Microsoft Azure Monitor agent and configures the agent to connect to your Log Analytics workspace.</span></span>
       -   <span data-ttu-id="c11d9-421">この手順は、既定では無効になっています。</span><span class="sxs-lookup"><span data-stu-id="c11d9-421">This step is disabled by default.</span></span> <span data-ttu-id="c11d9-422">この手順を有効にするのは、監視エージェントを使用して Microsoft Teams のルームの正常性を監視する場合のみです。</span><span class="sxs-lookup"><span data-stu-id="c11d9-422">Enable this step only if you’re going to use the Monitoring Agent to monitor the health of your Microsoft Teams Rooms units.</span></span>
       -   <span data-ttu-id="c11d9-423">この手順を編集し、コマンドラインパラメーターを更新して、**ワークスペース ID**と**ワークスペースキー**を指定します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-423">Edit this step and update the command-line parameters to specify your **Workspace ID** and **Workspace Key**.</span></span>
       -   <span data-ttu-id="c11d9-424">Operations Management Suite のワークスペース ID と主キーの入手方法の詳細については、「 [Azure Monitoring のテストデバイスを構成する](azure-monitor-deploy.md#configure-test-devices-for-azure-monitoring)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c11d9-424">See [Configure test devices for Azure Monitoring](azure-monitor-deploy.md#configure-test-devices-for-azure-monitoring) for more information about obtaining the Operations Management Suite Workspace ID and the primary key.</span></span>
       -   <span data-ttu-id="c11d9-425">**SRS v2 – Microsoft Monitoring Agent パッケージ**と**64 ビットファイルシステムリダイレクション**が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-425">Verify that the **SRS v2 – Microsoft Monitoring Agent Package** and **Disable 64-bit file system redirection** are selected.</span></span>
       -   <span data-ttu-id="c11d9-426">Microsoft Teams 室の展開の正常性を監視する方法の詳細については、「 [Azure monitor を使用した microsoft Teams 会議室管理の計画](azure-monitor-plan.md)」を参照してください。 azure monitor で microsoft [teams の](azure-monitor-deploy.md)ルーム管理を展開し、 [Azure monitor で microsoft Teams 室のデバイスを管理](azure-monitor-manage.md)します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-426">For more information about monitoring the health of your Microsoft Teams Rooms deployment, see [Plan Microsoft Teams Rooms management with Azure Monitor](azure-monitor-plan.md), [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor-deploy.md) and [Manage Microsoft Teams Rooms devices with Azure Monitor](azure-monitor-manage.md).</span></span>

   11. <span data-ttu-id="c11d9-427">**SRS V2 構成ファイルをコピー**する: この手順では、必要なセットアップファイルと構成ファイルを Microsoft Teams のルーム展開キットからローカルのハードドライブにコピーします。</span><span class="sxs-lookup"><span data-stu-id="c11d9-427">**Copy SRS v2 Configuration Files**: This step copies the required setup and configuration files from the Microsoft Teams Rooms deployment kit to the local hard drive.</span></span> <span data-ttu-id="c11d9-428">この手順をカスタマイズする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c11d9-428">No customization is required for this step.</span></span>
       -   <span data-ttu-id="c11d9-429">**Srs v2 – Srs アプリケーションパッケージ**と**64 ビットファイルシステムリダイレクション**が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-429">Verify that the **SRS v2 – SRS Application Package** and **Disable 64-bit file system redirection** are selected.</span></span>

   12. <span data-ttu-id="c11d9-430">**SRSv2-OS-更新プログラム**: この手順では、Microsoft Teams ルームの展開に必要なオペレーティングシステムの必須更新プログラムが展開されます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-430">**Install-SRSv2-OS-Updates**: This step deploys any mandatory operating system updates required with the Microsoft Teams Rooms deployment.</span></span> <span data-ttu-id="c11d9-431">次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-431">Do the following:</span></span>
       -   <span data-ttu-id="c11d9-432">必要な更新プログラムを確認するには[、Microsoft Teams 室コンソールを構成](console.md)することを確認します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-432">Check [Configure a Microsoft Teams Rooms console](console.md) to see which updates are required.</span></span>
       -   <span data-ttu-id="c11d9-433">**SRS v2 – OS 更新パッケージ**に必要な更新プログラムがすべて含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-433">Verify that your **SRS v2 – OS Updates Package** includes all the required updates.</span></span>
       -   <span data-ttu-id="c11d9-434">[ **SRS v2 – OS 更新プログラムパッケージ]** が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-434">Verify that the **SRS v2 – OS Updates Package** is selected.</span></span>
       -   <span data-ttu-id="c11d9-435">PowerShell 実行ポリシーが**バイパス**されるように設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-435">Verify that the PowerShell execution policy is set to **Bypass**.</span></span>

   13. <span data-ttu-id="c11d9-436">**コンピューターの再起動**: この手順は、オペレーティングシステムの必須更新プログラムがインストールされた後にコンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-436">**Restart Computer**: This step reboots the computer after the mandatory operating system updates are installed.</span></span> <span data-ttu-id="c11d9-437">この手順をカスタマイズする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c11d9-437">No customization is required for this step.</span></span>

   14. <span data-ttu-id="c11d9-438">**Windows コンポーネントの構成**: この手順では、必要な windows 機能を構成します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-438">**Configure Windows Components**: This step configures the required Windows features.</span></span> <span data-ttu-id="c11d9-439">この手順をカスタマイズする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c11d9-439">No customization is required for this step.</span></span>

   15. <span data-ttu-id="c11d9-440">**コンピューターを再起動**する: この手順は、Windows の機能が構成された後にコンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-440">**Restart Computer**: This step reboots the computer after the Windows features are configured.</span></span> <span data-ttu-id="c11d9-441">この手順をカスタマイズする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c11d9-441">No customization is required for this step.</span></span>

   16. <span data-ttu-id="c11d9-442">**ローカル Skype ユーザの追加**: この手順では、Windows に自動的にサインインするために使用されるローカルの skype アカウントを作成して、Microsoft Teams のルームアプリケーションを起動します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-442">**Add Local Skype User**: This step creates the local Skype account used to automatically sign in to Windows and start the Microsoft Teams Rooms application.</span></span> <span data-ttu-id="c11d9-443">この手順には、関連付けられたソフトウェアパッケージはありません。また、そのためのカスタマイズは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="c11d9-443">This step doesn’t have any software package associated with it, and no customization is required for it.</span></span>

   17. <span data-ttu-id="c11d9-444">**SRS アプリケーションをセットアップして構成する**: この手順では、オペレーティングシステムを次に起動するために Microsoft Teams 室のアプリケーションインストールが構成されます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-444">**Set up and configure SRS application**: This step configures the Microsoft Teams Rooms application installation for the next boot of the operating system.</span></span>
       -   <span data-ttu-id="c11d9-445">**Srs v2 – Srs セットアップパッケージを構成**し、 **64 ビットファイルシステムリダイレクション**が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-445">Verify that the **SRS v2 – Configure SRS Setup Package** and **Disable 64-bit file system redirection** are selected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c11d9-446">タスクシーケンスの手順は、指定された順序で行う必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c11d9-446">It is very important that the task sequence steps must be in the provided order.</span></span> <span data-ttu-id="c11d9-447">手順の順序を変更したり、追加の手順を構成したりすると、展開が壊れることがあります。</span><span class="sxs-lookup"><span data-stu-id="c11d9-447">Modifying the order of steps, or configuring additional steps might break the deployment.</span></span>
>
> <span data-ttu-id="c11d9-448">**SRS アプリケーションのセットアップと構成**は、タスクシーケンスの最後の手順として行う必要があります。そうしないと、展開が失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c11d9-448">**Set up and configure SRS application** step must be the last step in the task sequence, otherwise the deployment might fail.</span></span>

### <a name="create-deployment-for-the-task-sequence"></a><span data-ttu-id="c11d9-449">タスクシーケンスの展開を作成する</span><span class="sxs-lookup"><span data-stu-id="c11d9-449">Create deployment for the task sequence</span></span>

1. <span data-ttu-id="c11d9-450">タスクシーケンスを選択し、[**展開**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-450">Select the task sequence, and then select **Deploy**.</span></span>

2. <span data-ttu-id="c11d9-451">[**参照**] を選択して展開用のターゲットコレクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-451">Select **Browse** to select target collection for deployment.</span></span>

3. <span data-ttu-id="c11d9-452">[**すべての不明なコンピューター** ] を選択し、[ **OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-452">Select **All Unknown Computers** and then select **OK**.</span></span>

4. <span data-ttu-id="c11d9-453">[**次へ**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-453">Select **Next**.</span></span>

5. <span data-ttu-id="c11d9-454">[**目的**] ドロップダウンリストで [**利用可能**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-454">Select **Available** on the **Purpose** drop down list.</span></span>

6. <span data-ttu-id="c11d9-455">[**以下のものを利用可能にする**] ボックスの一覧で [**メディアと PXE のみ**] を選び、[**次**へ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-455">Select **Only Media and PXE** in the **Make available to the following** list, and then select **Next**.</span></span>
   > [!WARNING]
   > <span data-ttu-id="c11d9-456">**目的**を**利用できる**ように設定することは非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="c11d9-456">It is very important that **Purpose** is set to **Available**.</span></span> <span data-ttu-id="c11d9-457">**目的**が [**必須**」に設定されて**いない**ことを確認します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-457">Make sure that the **Purpose** is **NOT** set to **Required**.</span></span> <span data-ttu-id="c11d9-458">また、**次の [利用可能にする**] で [**メディアと PXE] のみ**を選択してください。</span><span class="sxs-lookup"><span data-stu-id="c11d9-458">Also make sure that you select **Only Media and PXE** in the **Make available to the following**.</span></span>
   >
   > <span data-ttu-id="c11d9-459">これらの値を別の値に設定すると、すべてのコンピューターで、起動時に Microsoft Teams のルームの展開イメージが取得されることがあります。</span><span class="sxs-lookup"><span data-stu-id="c11d9-459">Setting these values to something else might cause all computers to get the Microsoft Teams Rooms deployment image when booted.</span></span>
7. <span data-ttu-id="c11d9-460">スケジュールを指定せずに、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-460">Do not specify any schedule and select **Next**.</span></span>

8. <span data-ttu-id="c11d9-461">[**ユーザーエクスペリエンス**] セクション内の何も変更せず、[**次へ**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-461">Do not change anything within the **User Experience** section and select **Next**.</span></span>

9. <span data-ttu-id="c11d9-462">[**通知**] セクション内の何も変更せず、[**次へ**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-462">Do not change anything within the **Alerts** section and select **Next**.</span></span>

10. <span data-ttu-id="c11d9-463">[**配布ポイント**] セクション内の何も変更せず、[**次へ**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-463">Do not change anything within the **Distribution Points** section and select **Next**.</span></span>

11. <span data-ttu-id="c11d9-464">設定を確認し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-464">Confirm the settings and then select **Next**.</span></span>

12. <span data-ttu-id="c11d9-465">[**閉じる**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-465">Select **Close**.</span></span>

<a name="validate-and-troubleshoot-the-solution"></a><span data-ttu-id="c11d9-466">ソリューションの検証とトラブルシューティングを行う</span><span class="sxs-lookup"><span data-stu-id="c11d9-466">Validate and troubleshoot the solution</span></span>
--------------------------------------

<span data-ttu-id="c11d9-467">System Center Configuration Manager のタスクシーケンスが完了したら、タスクシーケンスで Microsoft Teams のルームユニットを展開して構成できることを確認するために、テスト実行を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c11d9-467">After you’ve completed the System Center Configuration Manager task sequences, you’ll need to perform a test run to validate that the task sequence can deploy and configure Microsoft Teams Rooms units.</span></span>

1.  <span data-ttu-id="c11d9-468">サポートされているイーサネットアダプターのいずれかを使用するか、Surface dock を使用して、テストデバイスを有線ネットワークに接続します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-468">Connect the test device to the wired network by using one of the supported Ethernet adapters or using the Surface dock.</span></span> <span data-ttu-id="c11d9-469">使用している環境に対して PXE ブート機能が構成されていない場合は、[前に作成](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media)した usb フラッシュドライブのブートイメージを使用して、usb から起動し、構成マネージャーに接続できます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-469">If PXE boot functionality hasn’t been configured for your environment, you can use the boot image on the USB flash drive [that you created earlier](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media) to boot from USB and connect to Configuration Manager.</span></span>

2.  <span data-ttu-id="c11d9-470">ファームウェアにアクセスし、PXE ブートを開始します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-470">Access the firmware and initiate PXE boot:</span></span>

    1.  <span data-ttu-id="c11d9-471">Surface デバイスの電源がオフになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-471">Ensure the Surface device is powered off.</span></span>

    2.  <span data-ttu-id="c11d9-472">[**音量を上げる**] ボタンを押したままにします。</span><span class="sxs-lookup"><span data-stu-id="c11d9-472">Press and hold the **Volume Up** button.</span></span>

    3.  <span data-ttu-id="c11d9-473">**電源**ボタンを押してから離します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-473">Press and release the **Power** button.</span></span>

    4.  <span data-ttu-id="c11d9-474">デバイスの起動が開始されたら、[**音量を上げる**] ボタンを放します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-474">After the device begins to boot, release the **Volume Up** button.</span></span>

    5.  <span data-ttu-id="c11d9-475">[**ブート構成**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-475">Select **Boot configuration**.</span></span>

    6.  <span data-ttu-id="c11d9-476">次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-476">Do one of the following:</span></span>

        -   <span data-ttu-id="c11d9-477">[ **PXE ブート**] を選択し、一覧の一番上にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="c11d9-477">Select **PXE boot**, and drag it to the top of the list.</span></span> <span data-ttu-id="c11d9-478">または、ネットワークアダプターを左にスワイプして、すぐにデバイスを起動することもできます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-478">Alternatively, you can swipe left on the network adapter to boot to the device immediately.</span></span> <span data-ttu-id="c11d9-479">これにより、起動順序は変わりません。</span><span class="sxs-lookup"><span data-stu-id="c11d9-479">This won’t affect the boot order.</span></span>
        -   <span data-ttu-id="c11d9-480">ブートメディアを含む USB フラッシュドライブを選択します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-480">Select the USB flash drive that holds the boot media.</span></span>

3.  <span data-ttu-id="c11d9-481">[**終了**] を選択し、[**今すぐ再起動**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-481">Select **Exit**, and then select **Restart Now**.</span></span>

4.  <span data-ttu-id="c11d9-482">メッセージが表示されたら、[ネットワークブートサービスの**入力**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-482">When prompted, select **Enter** for network boot service.</span></span>

5.  <span data-ttu-id="c11d9-483">Windows PE はメモリに読み込まれ、タスクシーケンスウィザードが開始されます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-483">Windows PE will load into memory, and the Task Sequence Wizard will start.</span></span> <span data-ttu-id="c11d9-484">[**次へ**] を選択して続行します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-484">Select **Next** to continue.</span></span>

6.  <span data-ttu-id="c11d9-485">前にインポートしたタスクシーケンスを選択し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-485">Select the task sequence that you imported earlier, and then select **Next**.</span></span>

7.  <span data-ttu-id="c11d9-486">ディスク構成が適用されると、デバイスのコンピューター名を指定するように求められます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-486">After the disk configuration is applied, you’ll be prompted to specify a computer name for the device.</span></span> <span data-ttu-id="c11d9-487">ユーザーインターフェイスには、Surface Pro デバイスのシリアル番号に基づく推奨コンピューター名が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-487">The user interface will display a recommended computer name based on the serial number of the Surface Pro device.</span></span> <span data-ttu-id="c11d9-488">提案された名前を受け入れるか、新しい名前を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-488">You can either accept the proposed name or specify a new one.</span></span> <span data-ttu-id="c11d9-489">[コンピューター名の割り当て] 画面の指示に従います。</span><span class="sxs-lookup"><span data-stu-id="c11d9-489">Follow the instructions on the computer name assignment screen.</span></span> <span data-ttu-id="c11d9-490">[**承諾**] を選択すると、展開が開始されます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-490">When you select **Accept**, the deployment begins.</span></span>

8.  <span data-ttu-id="c11d9-491">展開プロセスの残りの部分は自動であり、ユーザーにより多くの入力を求められることはありません。</span><span class="sxs-lookup"><span data-stu-id="c11d9-491">The rest of the deployment process is automatic and doesn’t ask for any more user input.</span></span>

9.  <span data-ttu-id="c11d9-492">展開タスクシーケンスによるデバイスの構成が完了すると、Microsoft Teams の会議の設定を構成するように求められる次の構成画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-492">After the deployment task sequence finishes configuring the device, you’ll see the following configuration screen that asks you to configure the Microsoft Teams Rooms application settings.</span></span>

    ![Microsoft Teams 室アプリケーションの最初のセットアップ画面](../media/room-systems-scale-image2.png)

10.  <span data-ttu-id="c11d9-494">Surface Pro を Microsoft Teams 室コンソールに接続し、アプリケーション設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-494">Plug the Surface Pro into the Microsoft Teams Rooms console, and configure the application settings.</span></span>

11.  <span data-ttu-id="c11d9-495">[Microsoft Teams のルーム](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)に記載されている機能が、展開されたデバイスで機能していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-495">Validate that the capabilities listed in [Microsoft Teams Rooms help](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) are working on the deployed device.</span></span>


<span data-ttu-id="c11d9-496">インストールに失敗した場合のトラブルシューティングを行うには、 **Smsts .log**ファイルを確認します。これは、構成マネージャーのタスクシーケンスで実行されたすべてのステップをログに記録します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-496">To troubleshoot a failed installation, check the **SMSTS.log** file, which logs all the steps executed in a Configuration Manager task sequence.</span></span>

<span data-ttu-id="c11d9-497">SMSTS ファイルは、ビルドプロセスの段階に応じて、多数のパスのいずれかに保存されます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-497">The SMSTS.log file is stored on one of a number of paths, depending on the stage of the build process.</span></span> <span data-ttu-id="c11d9-498">次の表を参照して SMSTS .log ファイルへのパスを確認します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-498">Check the following table to identify the path to the SMSTS.log file.</span></span>


| <span data-ttu-id="c11d9-499">**展開フェーズ**</span><span class="sxs-lookup"><span data-stu-id="c11d9-499">**Deployment phase**</span></span>                                                            | <span data-ttu-id="c11d9-500">**タスクシーケンスのログパス**</span><span class="sxs-lookup"><span data-stu-id="c11d9-500">**Task sequence log path**</span></span>                         |
|---------------------------------------------------------------------------------|----------------------------------------------------|
| <span data-ttu-id="c11d9-501">WinPE (HDD 形式の前)</span><span class="sxs-lookup"><span data-stu-id="c11d9-501">WinPE, before HDD format</span></span>                                                        | <span data-ttu-id="c11d9-502">X:\\Windows\\Temp\\smstslog\\smsts .log</span><span class="sxs-lookup"><span data-stu-id="c11d9-502">X:\\Windows\\Temp\\smstslog\\smsts.log</span></span>             |
| <span data-ttu-id="c11d9-503">WinPE (HDD 形式の後)</span><span class="sxs-lookup"><span data-stu-id="c11d9-503">WinPE, after HDD format</span></span>                                                         | <span data-ttu-id="c11d9-504">C:\\_SMSTaskSequence\\Smstslog\\\\smsts .log をログに記録します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-504">C:\\_SMSTaskSequence\\Logs\\Smstslog\\smsts.log</span></span>    |
| <span data-ttu-id="c11d9-505">Configuration Manager エージェントをインストールする前に、オペレーティングシステムが展開されました</span><span class="sxs-lookup"><span data-stu-id="c11d9-505">Operating system deployed, before the Configuration Manager agent was installed</span></span> | <span data-ttu-id="c11d9-506">c:\\_SMSTaskSequence\\Smstslog\\\\smsts .log をログに記録します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-506">c:\\_SMSTaskSequence\\Logs\\Smstslog\\smsts.log</span></span>    |
| <span data-ttu-id="c11d9-507">オペレーティングシステムと Configuration Manager エージェントが展開されている</span><span class="sxs-lookup"><span data-stu-id="c11d9-507">Operating system and the Configuration Manager agent deployed</span></span>                   | <span data-ttu-id="c11d9-508">% windir%\\System32\\ccm\\ログ\\Smstslog\\smsts .log</span><span class="sxs-lookup"><span data-stu-id="c11d9-508">%windir%\\System32\\ccm\\logs\\Smstslog\\smsts.log</span></span> |
| <span data-ttu-id="c11d9-509">タスクシーケンスの実行が完了しました</span><span class="sxs-lookup"><span data-stu-id="c11d9-509">Task sequence execution complete</span></span>                                                | <span data-ttu-id="c11d9-510">% windir%\\System32\\ccm\\は\\smsts .log をログに記録します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-510">%windir%\\System32\\ccm\\logs\\smsts.log</span></span>           |

> [!TIP]
> <span data-ttu-id="c11d9-511">タスクシーケンス中に**F8**を選択してコマンドコンソールを開き、smsts .log ファイルにアクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="c11d9-511">You can select **F8** at any time during the task sequence to open a command console, and then get access to the SMSTS.log file.</span></span>

<span data-ttu-id="c11d9-512">PXE ブートの問題のトラブルシューティングを行うには、PXE の操作に固有の、Configuration Manager サーバー上の2つのログファイルを確認します。</span><span class="sxs-lookup"><span data-stu-id="c11d9-512">To troubleshoot PXE boot issues, check the two log files on the Configuration Manager server that are specific to PXE actions:</span></span>

-   <span data-ttu-id="c11d9-513">**Pxecontrol。** Configuration Manager のインストールログディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="c11d9-513">**Pxecontrol.log**, located in the Configuration Manager installation logs directory</span></span>

-   <span data-ttu-id="c11d9-514">**Smspxe**(Configuration Manager 管理ポイント (MP) logs ディレクトリにあります)</span><span class="sxs-lookup"><span data-stu-id="c11d9-514">**Smspxe.log**, located in Configuration Manager Management Point (MP) logs directory</span></span>

<span data-ttu-id="c11d9-515">構成マネージャーのインストールをさらにトラブルシューティングするために使用できるログファイルの完全な一覧については、「 [System Center Configuration manager でファイルをログに記録](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/log-files)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c11d9-515">For a complete list of the log files that you can use to further troubleshoot your Configuration Manager installation, see [Log files in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/log-files).</span></span>
