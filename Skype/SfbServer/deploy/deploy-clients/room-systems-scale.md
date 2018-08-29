---
title: システム センター構成マネージャーを使用して、Skype の部屋のシステムを導入します。
ms.author: jambirk
author: Turgayo
manager: serdars
ms.date: 5/10/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: 大規模な展開で Skype ルーム システム v2 を展開する方法については、このトピックを参照してください。
ms.openlocfilehash: 3b34d584bf98326257964e30431f622a0be6dee2
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2018
ms.locfileid: "23247458"
---
# <a name="deploy-skype-room-systems-v2-by-using-system-center-configuration-manager"></a><span data-ttu-id="2fc7e-103">システム センター構成マネージャーを使用して Skype ルーム システム v2 を展開します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-103">Deploy Skype Room Systems v2 by using System Center Configuration Manager</span></span>

<span data-ttu-id="2fc7e-104">この記事では、システム センター構成マネージャーを使用して、Skype ルーム システム v2 の展開を作成するために必要なすべての情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-104">This article gives you all the necessary information to create your Skype Room Systems v2 deployments by using System Center Configuration Manager.</span></span>

<span data-ttu-id="2fc7e-105">システム センター構成マネージャーで提供される使用する方法、オペレーティング システムと複数のターゲット ・ デバイスには、他のアプリケーションを導入できます。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-105">With the easy-to-use methods provided by System Center Configuration Manager, you can deploy the operating system and other applications to multiple target devices.</span></span>

<span data-ttu-id="2fc7e-106">指示に従って、構成マネージャーの構成を以下に示す方法を使用し、サンプル パッケージと、組織の必要に応じて、このガイドで提供されているスクリプトをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-106">Use the approach illustrated below to guide you through your Configuration Manager configuration, and customize the sample packages and scripts provided throughout this guidance as needed for your organization.</span></span>

![構成マネージャーを使用して Skype ルーム システム v2 の展開プロセス](../../media/room-systems-scale-image1.png)

> [!IMPORTANT]
> <span data-ttu-id="2fc7e-108">このソリューションは、Surface Pro ベースの環境でのみテストされています。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-108">This solution has only been tested with Surface Pro–based deployments.</span></span> <span data-ttu-id="2fc7e-109">Surface Pro に基づかない場合、製造元のガイドラインに従います。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-109">Follow the manufacturer’s guidelines for configurations that aren’t based on Surface Pro.</span></span>

## <a name="validate-prerequisites"></a><span data-ttu-id="2fc7e-110">前提条件を検証します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-110">Validate prerequisites</span></span>

<span data-ttu-id="2fc7e-111">Skype ルーム システム v2 が構成マネージャーを展開するには、次の前提条件と要件を満たすことを確認します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-111">To deploy Skype Room Systems v2 with Configuration Manager, ensure that you meet the following prerequisites and requirements.</span></span>

### <a name="system-center-configuration-manager-requirements"></a><span data-ttu-id="2fc7e-112">システム センター構成マネージャーの要件</span><span class="sxs-lookup"><span data-stu-id="2fc7e-112">System Center Configuration Manager requirements</span></span>

-   <span data-ttu-id="2fc7e-113">システム センター構成マネージャーのバージョンは、少なくとも 1706 をする必要がありますまたはそれ以上です。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-113">System Center Configuration Manager version must be at least 1706 or above.</span></span> <span data-ttu-id="2fc7e-114">1710 またはそれ以降を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-114">We recommend using 1710 or later.</span></span> <span data-ttu-id="2fc7e-115">[サポートの Windows 10 ですシステム センター構成マネージャーで](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client)の構成マネージャーをサポートしている 10 の Windows のバージョンに関する詳細をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-115">Check out [Support for Windows 10 in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) to learn about the Windows 10 versions that Configuration Manager supports.</span></span>

-   <span data-ttu-id="2fc7e-116">Windows の評価と 10 の Windows の展開キット (ADK) のサポートされているバージョンをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-116">A supported version of Windows Assessment and Deployment Kit (ADK) for Windows 10 must be installed.</span></span> <span data-ttu-id="2fc7e-117">さまざまなバージョンの構成マネージャーを使用して、展開に適切なバージョンが含まれていることを確認する[10 ADK の Windows](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-adk)のバージョンを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-117">See the versions of the [Windows 10 ADK](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-adk) that you can use with different versions of Configuration Manager, and ensure that your deployment includes the correct version.</span></span>

-   <span data-ttu-id="2fc7e-118">サイト システム サーバーする必要があります割り当てられている配布ポイントの役割とのネットワークによる展開を有効にするのには、[プレブート実行環境 (PXE) のサポート](https://docs.microsoft.com/sccm/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network)を有効にするブート イメージです。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-118">The site system servers must have been assigned the distribution point role, and the boot images should be enabled for [preboot execution environment (PXE) support](https://docs.microsoft.com/sccm/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) to enable network-initiated deployments.</span></span> <span data-ttu-id="2fc7e-119">Pxe ブートのサポートが有効でない場合は、展開では、[ブータブル メディア](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network)を使用できます。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-119">If PXE support isn’t enabled, you can use [bootable media](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) for your deployments.</span></span>

-   <span data-ttu-id="2fc7e-120">コンピューター (ベア メタル) の新しい展開シナリオをサポートするためには、ネットワーク アクセス アカウントを構成しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-120">A network access account must be configured to support new computer (bare metal) deployment scenarios.</span></span> <span data-ttu-id="2fc7e-121">ネットワーク アクセス アカウントの構成に関する詳細については、[システム センター構成マネージャーでのコンテンツにアクセスするアカウントの管理](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-121">To learn more about the configuration of a network access account, see [Manage accounts to access content in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span></span>

-   <span data-ttu-id="2fc7e-122">同時に複数のユニットに同じ Skype ルーム システム v2 のイメージを展開する場合、[マルチキャスト サポート](https://docs.microsoft.com/sccm/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network)を有効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-122">We recommend that you enable [multicast support](https://docs.microsoft.com/sccm/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network), if you’re likely to deploy the same Skype Room Systems v2 image to multiple units at the same time.</span></span>

### <a name="networking-requirements"></a><span data-ttu-id="2fc7e-123">ネットワーク要件</span><span class="sxs-lookup"><span data-stu-id="2fc7e-123">Networking requirements</span></span>

-   <span data-ttu-id="2fc7e-124">ネットワークには、動的ホスト構成プロトコル (DHCP) サーバーは、Skype ルーム システム v2 のユニットを配置する場所のサブネットに IP アドレスの配分を自動で構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-124">Your network should have a Dynamic Host Configuration Protocol (DHCP) server, configured for automatic IP address distribution to the subnets where Skype Room Systems v2 units will be deployed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2fc7e-125">DHCP のリース期間は、イメージの展開期間よりも長い値に設定しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-125">DHCP lease duration must be set to a value longer than the image deployment duration.</span></span> <span data-ttu-id="2fc7e-126">それ以外の場合、展開が失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-126">Otherwise, the deployment might fail.</span></span>

-   <span data-ttu-id="2fc7e-127">PXE をサポートするためにスイッチ、仮想 Lan (Vlan) など、ネットワークを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-127">Your network, including switches and virtual LANs (VLANs), should be configured to support PXE.</span></span> <span data-ttu-id="2fc7e-128">IP ヘルパーと PXE の構成の詳細については、ネットワークの製造元を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-128">Refer to your network vendor for more information about IP Helper and PXE configuration.</span></span> <span data-ttu-id="2fc7e-129">または、pxe ブートのサポートが有効になっていない場合は、展開の場合、[起動可能なメディア](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network)を使用できます。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-129">Alternatively, you can use [bootable media](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) for your deployments, if PXE support isn’t enabled.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2fc7e-130">Surface Pro のイーサネット アダプターまたはマイクロソフトからのドッキング ステーションを使用する場合のみ、デバイス、ネットワーク (PXE ブート) からの起動がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-130">For Surface Pro devices, booting from the network (PXE boot) is only supported when you use an Ethernet adapter or docking station from Microsoft.</span></span> <span data-ttu-id="2fc7e-131">Surface Pro で PXE ブートをサポートしていないサードパーティ製のイーサネット アダプターです。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-131">Third-party Ethernet adapters don’t support PXE boot with Surface Pro.</span></span> <span data-ttu-id="2fc7e-132">詳細については、[イーサネット アダプターとサーフェスの配置](https://docs.microsoft.com/surface/ethernet-adapters-and-surface-device-deployment)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-132">See [Ethernet adapters and Surface deployment](https://docs.microsoft.com/surface/ethernet-adapters-and-surface-device-deployment) for more information.</span></span>

## <a name="configure-system-center-configuration-manager-for-operating-system-deployment"></a><span data-ttu-id="2fc7e-133">システム センター構成マネージャーをオペレーティング システムの展開の構成します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-133">Configure System Center Configuration Manager for operating system deployment</span></span>

<span data-ttu-id="2fc7e-134">この資料では、既に正常なシステム センター構成マネージャーの展開があり、詳細を展開し、最初から構成マネージャーを構成するために必要なすべての手順を実行しないと仮定します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-134">This article assumes you already have a healthy System Center Configuration Manager deployment, and doesn’t detail all the steps required to deploy and configure Configuration Manager from scratch.</span></span> <span data-ttu-id="2fc7e-135">[ドキュメントおよび構成ガイド](https://docs.microsoft.com/sccm/)、システム センター構成マネージャーでは、優れたリソースです。構成マネージャーをまだ展開していない場合、これらのリソースを開始することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-135">The [documentation and the configuration guidance](https://docs.microsoft.com/sccm/) on the System Center Configuration Manager is a great resource; we recommend you start with these resources if you haven’t yet deployed Configuration Manager.</span></span>

<span data-ttu-id="2fc7e-136">オペレーティング システムの展開 (OSD) 機能が正しく構成されていることを確認するのにには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-136">Use the following instructions to verify that the operating system deployment (OSD) features are configured properly.</span></span>

### <a name="validate-and-upgrade-configuration-manager"></a><span data-ttu-id="2fc7e-137">検証し、構成マネージャーのアップグレード</span><span class="sxs-lookup"><span data-stu-id="2fc7e-137">Validate and upgrade Configuration Manager</span></span>

1.  <span data-ttu-id="2fc7e-138">構成マネージャー コンソールで、**管理**ページに移動\>**の更新プログラムおよびサービス**です。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-138">In the Configuration Manager console, go to **Administration** \> **Updates and Servicing**.</span></span>

2.  <span data-ttu-id="2fc7e-139">まだインストールされていない適用可能な更新プログラム、インストールされているビルドを確認します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-139">Check the installed build and applicable updates that haven’t been installed yet.</span></span>

3.  <span data-ttu-id="2fc7e-140">[10 System Center 構成マネージャーでの Windows のサポート](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client)を確認します。配置をアップグレードする場合をインストールする更新プログラムを選択し、**ダウンロード**します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-140">Review [Support for Windows 10 in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client); if you need to upgrade your deployment, select the update you want to install, and then select **Download**.</span></span>

4.  <span data-ttu-id="2fc7e-141">ダウンロードが完了した後、更新プログラムを選択し、**更新パックをインストール**します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-141">After the download is complete, select the update, and then select **Install Update Pack**.</span></span>

### <a name="configure-distribution-points-to-support-pxe-and-multicast"></a><span data-ttu-id="2fc7e-142">PXE、マルチキャストをサポートするために配布ポイントを構成します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-142">Configure distribution points to support PXE and multicast</span></span>

1.  <span data-ttu-id="2fc7e-143">構成マネージャー コンソールで、**管理**ページに移動\>**の配布ポイント**です。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-143">In the Configuration Manager console, go to **Administration** \> **Distribution Points**.</span></span>

2.  <span data-ttu-id="2fc7e-144">Skype ルーム システム v2 の導入、サービスを提供し、**プロパティ**を選択し、配布ポイント サーバーを選択します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-144">Select the distribution point server that will serve the Skype Room Systems v2 deployment, and then select **Properties**.</span></span>

3.  <span data-ttu-id="2fc7e-145">**PXE** ] タブを選択し、次の設定が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-145">Select the **PXE** tab, and ensure that the following settings are enabled:</span></span>
    -   <span data-ttu-id="2fc7e-146">クライアントの pxe ブートのサポートを有効にします。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-146">Enable PXE support for clients</span></span>
    -   <span data-ttu-id="2fc7e-147">受信 PXE 要求に応答するには、この配布ポイントを許可します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-147">Allow this distribution point to respond to incoming PXE requests</span></span>
    -   <span data-ttu-id="2fc7e-148">不明なコンピューターのサポートを有効にします。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-148">Enable unknown computer support</span></span>

4.  <span data-ttu-id="2fc7e-149">*オプション:* マルチキャスト サポートを有効にするには、[**マルチキャスト**] タブを選択し、[次の設定が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-149">*Optional:* To enable multicast support, select the **Multicast** tab, and ensure that the following settings are enabled:</span></span>
    -   <span data-ttu-id="2fc7e-150">同時に複数のクライアントにデータを送信するマルチキャストを有効にします。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-150">Enable multicast to simultaneously send data to multiple clients</span></span>
    -   <span data-ttu-id="2fc7e-151">ネットワーク チームの勧告に UDP ポートの範囲を構成します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-151">Configure the UDP port range as per your network team’s recommendation</span></span>

### <a name="configure-the-network-access-account"></a><span data-ttu-id="2fc7e-152">ネットワーク アクセス アカウントを構成します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-152">Configure the Network Access Account</span></span>

1.  <span data-ttu-id="2fc7e-153">構成マネージャー コンソールで、**管理**ページに移動\>**サイトの構成** \> **サイト**、およびサイトを選択します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-153">In the Configuration Manager console, go to **Administration** \> **Site Configuration** \> **Sites**, and then select the site.</span></span>

2.  <span data-ttu-id="2fc7e-154">[**設定**] で、**サイトのコンポーネントの構成**を選択します\>**ソフトウェアの配布**。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-154">In the **Settings** group, select **Configure Site Components** \> **Software Distribution**.</span></span>

3.  <span data-ttu-id="2fc7e-155">[**ネットワーク アクセス アカウント**] タブを 1 つまたは複数のアカウント] をクリックし **[ok]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-155">Select the **Network Access Account** tab. Set up one or more accounts, and then select **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="2fc7e-156">アカウントには、配布ポイント サーバー上の**ネットワークからこのコンピューターへアクセス**を除く、任意の特別な権限が必要がありません。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-156">The accounts don’t need any special rights, except for the **Access this computer from the network** right on the distribution point server.</span></span> <span data-ttu-id="2fc7e-157">汎用的なドメイン ユーザー アカウントに適切ななります。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-157">A generic domain user account will be appropriate.</span></span> <span data-ttu-id="2fc7e-158">詳細については、[システム センター構成マネージャーでのコンテンツにアクセスするアカウントの管理](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-158">For more information, see [Manage accounts to access content in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span></span>

### <a name="configure-a-boot-image"></a><span data-ttu-id="2fc7e-159">ブート イメージを構成します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-159">Configure a boot image</span></span>

1.  <span data-ttu-id="2fc7e-160">**ソフトウェア ライブラリ**には、構成マネージャー コンソールで、 \> **のオペレーティング システム** \> **のブート イメージ**です。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-160">In the Configuration Manager console, go to **Software Library** \> **Operating System** \> **Boot Images**.</span></span>

2.  <span data-ttu-id="2fc7e-161">**ブート イメージ (x64)** を選択し、[**プロパティ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-161">Select **Boot image (x64)**, and then select **Properties**.</span></span>

3.  <span data-ttu-id="2fc7e-162">**データ ソース**] タブを選択し、 **PXE が有効な配布ポイントからは、このブート イメージの展開**を有効にします。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-162">Select the **Data Source** tab, and enable **Deploy this boot image from the PXE-enabled distribution point**.</span></span>

4.  <span data-ttu-id="2fc7e-163">必要なコンポーネントをインストールするのには [**オプション コンポーネント**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-163">Select the **Optional Components** tab to install required components:</span></span>

    1.  <span data-ttu-id="2fc7e-164">スターのアイコンを選択し、 **HTML (WinPE HTA)** を検索</span><span class="sxs-lookup"><span data-stu-id="2fc7e-164">Select the star icon, and search for **HTML (WinPE-HTA)**</span></span>

    2.  <span data-ttu-id="2fc7e-165">ブート イメージへの HTML アプリケーションのサポートを追加するのには **[ok]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-165">Select **OK** to add HTML application support in to the boot image.</span></span>

5.  <span data-ttu-id="2fc7e-166">*オプション:* 展開のエクスペリエンスをカスタマイズするには、[**カスタマイズ**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-166">*Optional:* To customize the deployment experience, select the **Customization** tab.</span></span>
    -   <span data-ttu-id="2fc7e-167">展開時に、コマンド プロンプトへのアクセスが必要な場合 **(テストのみ)] コマンドのサポート**を有効にします。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-167">Enable **command support (testing only)** if you want to have access to a command prompt during the deployment.</span></span> <span data-ttu-id="2fc7e-168">これを有効にすると、展開中に**f8 キー**を選択してコマンド プロンプトを起動できます。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-168">When this is enabled, you can start a command prompt by selecting **F8** at any time during the deployment.</span></span>
    -   <span data-ttu-id="2fc7e-169">展開時に表示するカスタムの背景イメージを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-169">You can also specify a custom background image to be displayed during the deployment.</span></span> <span data-ttu-id="2fc7e-170">イメージを設定するを有効にする**カスタムの背景イメージのファイルを指定 (UNC パス**の背景を選択します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-170">To set an image, enable **Specify the custom background image file (UNC path** and select your background.</span></span>

6.  <span data-ttu-id="2fc7e-171">ダイアログ ボックスが表示されたら、 **[はい]** を選択し、配布ポイントに更新されたブート イメージを配布します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-171">When asked, select **Yes** and distribute the updated boot image to your distribution points.</span></span>

<span data-ttu-id="2fc7e-172">詳細については、[ブート イメージの管理システム センター構成マネージャーの使用](https://docs.microsoft.com/sccm/osd/get-started/manage-boot-images)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-172">For more information, see [Manage boot images with System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-boot-images).</span></span>

> [!NOTE]
> <span data-ttu-id="2fc7e-173">Pxe ブートのサポートがない環境の構成マネージャー タスク シーケンスに基づく展開を開始する起動可能な USB メディアを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-173">You can create a bootable USB media to initiate Configuration Manager task sequence–based deployments for environments that have no PXE support.</span></span> <span data-ttu-id="2fc7e-174">のみブート イメージ、prestart コマンドのオプションと、必要なファイル、および構成マネージャーのバイナリ Windows PE を起動し、展開プロセスの残りの部分の構成マネージャーへの接続をサポートするために、ブート可能なメディアが含まれます。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-174">The bootable media contains only the boot image, optional prestart commands and their required files, and Configuration Manager binaries to support booting into Windows PE and connecting to Configuration Manager for the rest of the deployment process.</span></span> <span data-ttu-id="2fc7e-175">詳細については、[ブータブル メディアを作成する方法](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-175">For more information, see [How to Create Bootable Media](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia).</span></span>

## <a name="create-configuration-manager-packages"></a><span data-ttu-id="2fc7e-176">構成マネージャー パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-176">Create Configuration Manager packages</span></span>

<span data-ttu-id="2fc7e-177">構成マネージャーでは、いくつかのパッケージを展開し、Skype ルーム システム v2 の単位を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-177">Configuration Manager requires a number of packages to deploy and configure the Skype Room System v2 units.</span></span>

<span data-ttu-id="2fc7e-178">作成し、次のパッケージを構成する必要があり、配布ポイント サーバーの役割が割り当てられている構成マネージャー サイト システムに配布します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-178">You need to create and configure the following packages, and then distribute them to the Configuration Manager site systems that have been assigned the distribution point server role.</span></span>

| <span data-ttu-id="2fc7e-179">**パッケージ名**</span><span class="sxs-lookup"><span data-stu-id="2fc7e-179">**Package name**</span></span>                     | <span data-ttu-id="2fc7e-180">**種類**</span><span class="sxs-lookup"><span data-stu-id="2fc7e-180">**Type**</span></span>               | <span data-ttu-id="2fc7e-181">**説明**</span><span class="sxs-lookup"><span data-stu-id="2fc7e-181">**Description**</span></span>                                                                           |
|--------------------------------------|------------------------|-------------------------------------------------------------------------------------------|
| <span data-ttu-id="2fc7e-182">SRS v2 の SRS のアプリケーション パッケージ</span><span class="sxs-lookup"><span data-stu-id="2fc7e-182">SRS v2 - SRS Application Package</span></span>     | <span data-ttu-id="2fc7e-183">ソフトウェア パッケージ</span><span class="sxs-lookup"><span data-stu-id="2fc7e-183">Software package</span></span>       | <span data-ttu-id="2fc7e-184">Skype ルーム システム v2 展開キットのパッケージ</span><span class="sxs-lookup"><span data-stu-id="2fc7e-184">Package for the Skype Room Systems v2 deployment kit</span></span>                                      |
| <span data-ttu-id="2fc7e-185">SRS v2 の Sysprep パッケージ</span><span class="sxs-lookup"><span data-stu-id="2fc7e-185">SRS v2 - Sysprep Package</span></span>             | <span data-ttu-id="2fc7e-186">ソフトウェア パッケージ</span><span class="sxs-lookup"><span data-stu-id="2fc7e-186">Software package</span></span>       | <span data-ttu-id="2fc7e-187">Skype ルーム システム v2 の単位を構成するのにはカスタムの Unattended.xml 用のパッケージ</span><span class="sxs-lookup"><span data-stu-id="2fc7e-187">Package for the custom Unattended.xml to configure Skype Room Systems v2 units</span></span>            |
| <span data-ttu-id="2fc7e-188">SRS v2 - セット-SRSComputerName パッケージ</span><span class="sxs-lookup"><span data-stu-id="2fc7e-188">SRS v2 - Set-SRSComputerName Package</span></span> | <span data-ttu-id="2fc7e-189">ソフトウェア パッケージ</span><span class="sxs-lookup"><span data-stu-id="2fc7e-189">Software package</span></span>       | <span data-ttu-id="2fc7e-190">パッケージの展開時にコンピューター名を割り当てるには、HTML アプリケーション (HTA)</span><span class="sxs-lookup"><span data-stu-id="2fc7e-190">Package for the HTML application (HTA) to assign a computer name during the deployment</span></span>    |
| <span data-ttu-id="2fc7e-191">SRS v2 の SRS の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-191">SRS v2 - Configure SRS Setup</span></span>         | <span data-ttu-id="2fc7e-192">ソフトウェア パッケージ</span><span class="sxs-lookup"><span data-stu-id="2fc7e-192">Software package</span></span>       | <span data-ttu-id="2fc7e-193">Skype ルーム システム v2 アプリケーションの展開を構成するパッケージ</span><span class="sxs-lookup"><span data-stu-id="2fc7e-193">Package to configure deployment of the Skype Room Systems v2 app</span></span>                          |
| <span data-ttu-id="2fc7e-194">SRS v2 - OS の更新パッケージ</span><span class="sxs-lookup"><span data-stu-id="2fc7e-194">SRS v2 - OS Updates Package</span></span>          | <span data-ttu-id="2fc7e-195">ソフトウェア パッケージ</span><span class="sxs-lookup"><span data-stu-id="2fc7e-195">Software package</span></span>       | <span data-ttu-id="2fc7e-196">オペレーティング システムの必須更新プログラムを展開するパッケージ</span><span class="sxs-lookup"><span data-stu-id="2fc7e-196">Package to deploy mandatory operating system updates</span></span>                                      |
| <span data-ttu-id="2fc7e-197">SRS v2 のルート証明書のパッケージ</span><span class="sxs-lookup"><span data-stu-id="2fc7e-197">SRS v2 - Root Certificate Package</span></span>    | <span data-ttu-id="2fc7e-198">ソフトウェア パッケージ</span><span class="sxs-lookup"><span data-stu-id="2fc7e-198">Software package</span></span>       | <span data-ttu-id="2fc7e-199">オプション - (ドメインに参加しているユニットは必要ありません) ルート証明書を展開するためのパッケージ</span><span class="sxs-lookup"><span data-stu-id="2fc7e-199">Optional - Package to deploy the root certificate (not required for domain-joined units)</span></span>  |
| <span data-ttu-id="2fc7e-200">SRS v2 - マイクロソフト OMS エージェント パッケージ</span><span class="sxs-lookup"><span data-stu-id="2fc7e-200">SRS v2 - Microsoft OMS Agent Package</span></span> | <span data-ttu-id="2fc7e-201">ソフトウェア パッケージ</span><span class="sxs-lookup"><span data-stu-id="2fc7e-201">Software package</span></span>       | <span data-ttu-id="2fc7e-202">オプション ・ パッケージを展開し、運用管理スイートの Microsoft エージェントを構成するには</span><span class="sxs-lookup"><span data-stu-id="2fc7e-202">Optional - Package to deploy and configure the Microsoft Operations Management Suite agent</span></span>|
| <span data-ttu-id="2fc7e-203">SRS v2 の WinPE の背景のパッケージ</span><span class="sxs-lookup"><span data-stu-id="2fc7e-203">SRS v2 - WinPE Background Package</span></span>    | <span data-ttu-id="2fc7e-204">ソフトウェア パッケージ</span><span class="sxs-lookup"><span data-stu-id="2fc7e-204">Software package</span></span>       | <span data-ttu-id="2fc7e-205">ブート イメージを使用するカスタムの背景イメージのパッケージ</span><span class="sxs-lookup"><span data-stu-id="2fc7e-205">Package for the custom background image to use with boot images</span></span>                           |
| <span data-ttu-id="2fc7e-206">10 の Windows エンタープライズ</span><span class="sxs-lookup"><span data-stu-id="2fc7e-206">Windows 10 Enterprise</span></span>                | <span data-ttu-id="2fc7e-207">オペレーティング システムのイメージ</span><span class="sxs-lookup"><span data-stu-id="2fc7e-207">Operating system image</span></span> | <span data-ttu-id="2fc7e-208">オペレーティング システム インストール ファイル (install.wim) 用のパッケージ</span><span class="sxs-lookup"><span data-stu-id="2fc7e-208">Package for the operating system installation file (install.wim)</span></span>                          |
| <span data-ttu-id="2fc7e-209">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="2fc7e-209">Surface Pro</span></span>                          | <span data-ttu-id="2fc7e-210">ドライバー パッケージ</span><span class="sxs-lookup"><span data-stu-id="2fc7e-210">Driver package</span></span>         | <span data-ttu-id="2fc7e-211">Microsoft Surface Pro のファームウェアとデバイス ドライバーのパッケージ</span><span class="sxs-lookup"><span data-stu-id="2fc7e-211">Package for the device drivers and firmware for Microsoft Surface Pro</span></span>                     |
| <span data-ttu-id="2fc7e-212">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="2fc7e-212">Surface Pro 4</span></span>                        | <span data-ttu-id="2fc7e-213">ドライバー パッケージ</span><span class="sxs-lookup"><span data-stu-id="2fc7e-213">Driver package</span></span>         | <span data-ttu-id="2fc7e-214">Microsoft Surface Pro 4 のファームウェアとデバイス ドライバーのパッケージ</span><span class="sxs-lookup"><span data-stu-id="2fc7e-214">Package for the device drivers and firmware for Microsoft Surface Pro 4</span></span>                   |

<span data-ttu-id="2fc7e-215">詳細については、[パッケージとプログラムで、システム センター構成マネージャー](https://docs.microsoft.com/sccm/apps/deploy-use/packages-and-programs)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-215">For more information, see [Packages and programs in System Center Configuration Manager](https://docs.microsoft.com/sccm/apps/deploy-use/packages-and-programs).</span></span>

### <a name="create-folders-for-the-package-source-files"></a><span data-ttu-id="2fc7e-216">パッケージのフォルダーを作成するには、ソース ファイル</span><span class="sxs-lookup"><span data-stu-id="2fc7e-216">Create folders for the package source files</span></span>

<span data-ttu-id="2fc7e-217">構成マネージャーには、パッケージのソース ファイルを最初に作成しているとき、および更新されるときに特定のフォルダー構造で整理することが必要です。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-217">Configuration Manager requires package source files to be organized in a specific folder structure when they’re first created and when they’re updated.</span></span>

<span data-ttu-id="2fc7e-218">システム センター構成マネージャー サーバーの全体管理サイトまたはプライマリ サイト、またはを使用してパッケージのソース ファイルをホストするサーバー共有には、次のフォルダー構造を作成します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-218">Create the following folder structure on the System Center Configuration Manager central administration site or primary site, or on a server share you’re using to host package source files:</span></span>

-   <span data-ttu-id="2fc7e-219">SRS v2 - マイクロソフト OMS エージェント パッケージ</span><span class="sxs-lookup"><span data-stu-id="2fc7e-219">SRS v2 - Microsoft OMS Agent Package</span></span>
-   <span data-ttu-id="2fc7e-220">SRS v2 - OS の更新パッケージ</span><span class="sxs-lookup"><span data-stu-id="2fc7e-220">SRS v2 - OS Updates Package</span></span>
-   <span data-ttu-id="2fc7e-221">SRS v2 のルート証明書のパッケージ</span><span class="sxs-lookup"><span data-stu-id="2fc7e-221">SRS v2 - Root Certificate Package</span></span>
-   <span data-ttu-id="2fc7e-222">SRS v2 - セット-SRSComputerName パッケージ</span><span class="sxs-lookup"><span data-stu-id="2fc7e-222">SRS v2 - Set-SRSComputerName Package</span></span>
-   <span data-ttu-id="2fc7e-223">SRS v2 の SRS のアプリケーション パッケージ</span><span class="sxs-lookup"><span data-stu-id="2fc7e-223">SRS v2 - SRS Application Package</span></span>
-   <span data-ttu-id="2fc7e-224">SRS v2 の SRS の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-224">SRS v2 - Configure SRS Setup</span></span>
-   <span data-ttu-id="2fc7e-225">SRS v2 の Sysprep パッケージ</span><span class="sxs-lookup"><span data-stu-id="2fc7e-225">SRS v2 - Sysprep Package</span></span>
-   <span data-ttu-id="2fc7e-226">ドライバー</span><span class="sxs-lookup"><span data-stu-id="2fc7e-226">Drivers</span></span>
    -   <span data-ttu-id="2fc7e-227">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="2fc7e-227">Surface Pro</span></span>
    -   <span data-ttu-id="2fc7e-228">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="2fc7e-228">Surface Pro 4</span></span>
-   <span data-ttu-id="2fc7e-229">オペレーティング ・ システム</span><span class="sxs-lookup"><span data-stu-id="2fc7e-229">Operating Systems</span></span>
    -   <span data-ttu-id="2fc7e-230">10 の Windows エンタープライズ</span><span class="sxs-lookup"><span data-stu-id="2fc7e-230">Windows 10 Enterprise</span></span>

> [!TIP]
> <span data-ttu-id="2fc7e-231">[ダウンロード](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)にも可能性があり、パッケージ スクリプトを使用する必要がありますが、インポートする必要があるタスク シーケンスのテンプレート用のフォルダー構造を含む zip ファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-231">You may also [download](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) and use the zip file that includes the folder structure for the packages, the scripts that you need to use, and the task sequence template, that you need to import.</span></span>

### <a name="create-the-microsoft-operations-management-suite-agent-package"></a><span data-ttu-id="2fc7e-232">運用管理スイートの Microsoft エージェント パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-232">Create the Microsoft Operations Management Suite agent package</span></span>

1.  <span data-ttu-id="2fc7e-233">ダウンロード操作の管理スイートの X-64 エージェントが<https://go.microsoft.com/fwlink/?LinkId=828603>。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-233">Download the Operations Management Suite X-64 agent from <https://go.microsoft.com/fwlink/?LinkId=828603>.</span></span>

2.  <span data-ttu-id="2fc7e-234">コマンド プロンプト ウィンドウを開き、コマンド プロンプトで**MMASetup AMD64.exe の指定**を入力する**SRS v2 - マイクロソフト OMS エージェント パッケージ**フォルダーにパッケージを抽出します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-234">Extract the package into the **SRS v2 - Microsoft OMS Agent Package** folder by opening a Command Prompt window and entering **MMASetup-AMD64.exe /C:**     at the command prompt.</span></span>

3.  <span data-ttu-id="2fc7e-235">**ソフトウェア ライブラリ**には、構成マネージャー コンソールで、 \> **アプリケーション管理** \> **パッケージ**、および**パッケージの作成**を選択します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-235">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="2fc7e-236">パッケージを作成するのには次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-236">Enter the following information to create the package:</span></span>

    -   <span data-ttu-id="2fc7e-237">名前 **: SRS v2 - マイクロソフト OMS エージェント パッケージ**</span><span class="sxs-lookup"><span data-stu-id="2fc7e-237">Name **: SRS v2 - Microsoft OMS Agent Package**</span></span>

    -   <span data-ttu-id="2fc7e-238">製造元 **: Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="2fc7e-238">Manufacturer **: Microsoft Corporation**</span></span>

    -   <span data-ttu-id="2fc7e-239">バージョン **: 8.1.11081.0** (ダウンロードしたインストール ファイルのバージョンを入力してください)</span><span class="sxs-lookup"><span data-stu-id="2fc7e-239">Version **: 8.1.11081.0** (enter the version of the downloaded installation file)</span></span>

    -   <span data-ttu-id="2fc7e-240">**このパッケージにソース ファイルが含まれています**] チェック ボックスをオンに、 **SRS の v2 - マイクロソフト OMS エージェント パッケージ**フォルダーにパスを入力し、**次へ**。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-240">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Microsoft OMS Agent Package** folder, and then select **Next**.</span></span>

5.  <span data-ttu-id="2fc7e-241">**プログラムを作成しない**を選択し、**次へ**します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-241">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="2fc7e-242">**設定の確認**] ページを確認し、**次へ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-242">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="2fc7e-243">**閉じる**を選択します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-243">Select **Close**.</span></span>

### <a name="create-the-operating-system-updates-package"></a><span data-ttu-id="2fc7e-244">オペレーティング システム更新プログラム パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-244">Create the operating system updates package</span></span>

1.  <span data-ttu-id="2fc7e-245">**SRS v2 - OS の更新プログラム パッケージ**のフォルダーに**インストール-SRSv2-OS の Updates.ps1**をという名前の新しい PowerShell スクリプトを作成します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-245">In the **SRS v2 - OS Updates Package** folder, create a new PowerShell script named **Install-SRSv2-OS-Updates.ps1**.</span></span>

2.  <span data-ttu-id="2fc7e-246">**インストール-SRSv2-OS の Updates.ps1**スクリプトに以下のスクリプトをコピーします。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-246">Copy the script below into the **Install-SRSv2-OS-Updates.ps1** script.</span></span> <span data-ttu-id="2fc7e-247">または、[ここ](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)からインストール-SRSv2-OS の Updates.ps1 スクリプトをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-247">Alternatively, you can download the Install-SRSv2-OS-Updates.ps1 script from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
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
3.  <span data-ttu-id="2fc7e-248">必須の Windows 更新プログラム パッケージを同じフォルダーにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-248">Download the mandatory Windows Update packages into the same folder.</span></span>
    > [!NOTE]
    > <span data-ttu-id="2fc7e-249">この資料が公開された時点で、 [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu)だけが必要でした。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-249">At the time this article was published, only [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) was required.</span></span> <span data-ttu-id="2fc7e-250">[Skype ルーム システム v2 のコンソールを構成する](console.md)、他の更新プログラムが必要なかどうかを確認してください。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-250">Check [Configure a Skype Room Systems v2 console](console.md), to see whether any other updates are required.</span></span>

4.  <span data-ttu-id="2fc7e-251">**ソフトウェア ライブラリ**には、構成マネージャー コンソールで、 \> **アプリケーション管理** \> **パッケージ**、および**パッケージの作成**を選択します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-251">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

5.  <span data-ttu-id="2fc7e-252">パッケージを作成するのには次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-252">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="2fc7e-253">名前: の**SRS v2 – OS パッケージを更新します。**</span><span class="sxs-lookup"><span data-stu-id="2fc7e-253">Name: **SRS v2 – OS Updates Package**</span></span>
    -   <span data-ttu-id="2fc7e-254">製造元: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="2fc7e-254">Manufacturer: **Microsoft Corporation**</span></span>
    -   <span data-ttu-id="2fc7e-255">バージョン: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="2fc7e-255">Version: **1.0.0**</span></span>
    -   <span data-ttu-id="2fc7e-256">**このパッケージにソース ファイルが含まれています**] チェック ボックスをオンに、 **SRS の v2 - OS の更新プログラム パッケージ**のフォルダーにパスを入力し、**次へ**。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-256">Select the **This package contains source files** check box, enter the path to the **SRS v2 - OS Updates Package** folder, and then select **Next**.</span></span>

6.  <span data-ttu-id="2fc7e-257">**プログラムを作成しない**を選択し、**次へ**します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-257">Select **Do not create a program**, and then select **Next**.</span></span>

7.  <span data-ttu-id="2fc7e-258">**設定の確認**] ページを確認し、**次へ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-258">Review the **Confirm the settings** page, and then select **Next**.</span></span>

8.  <span data-ttu-id="2fc7e-259">**閉じる**を選択します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-259">Select **Close**.</span></span>

### <a name="create-the-root-certificate-package-optional"></a><span data-ttu-id="2fc7e-260">ルート証明書のパッケージを作成する (省略可能)</span><span class="sxs-lookup"><span data-stu-id="2fc7e-260">Create the root certificate package (optional)</span></span>

<span data-ttu-id="2fc7e-261">Active Directory ドメインに参加しないデバイスのルート証明書を配布するには、このパッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-261">You create this package to distribute the root certificate for devices that won’t be joined to an Active Directory domain.</span></span> <span data-ttu-id="2fc7e-262">次の両方の条件を適用する場合にのみ、このパッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-262">Create this package only if both the following conditions apply:</span></span>
-   <span data-ttu-id="2fc7e-263">展開には、設置が含まれています Lync または Skype ビジネス サーバー用です。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-263">Your deployment includes on-premises Lync or Skype for Business Server.</span></span>
-   <span data-ttu-id="2fc7e-264">Skype ルーム システム v2 の単位は、ドメインのメンバーではなくワークグループで作業するのには構成されます。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-264">Skype Room Systems v2 units are configured to work in a workgroup instead of a domain member.</span></span>

1.  <span data-ttu-id="2fc7e-265">ルート証明書を**SRS v2: ルート証明書のパッケージ**フォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-265">Copy the root certificate into the **SRS v2 – Root Certificate Package** folder.</span></span>

2.  <span data-ttu-id="2fc7e-266">**ソフトウェア ライブラリ**には、構成マネージャー コンソールで、 \> **アプリケーション管理** \> **パッケージ**、および**パッケージの作成**を選択します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-266">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

3.  <span data-ttu-id="2fc7e-267">パッケージを作成するのには次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-267">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="2fc7e-268">**SRS v2: ルート証明書のパッケージ**の名前。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-268">Name: **SRS v2 – Root Certificate Package**</span></span>
    -   <span data-ttu-id="2fc7e-269">製造元:*組織の名前*</span><span class="sxs-lookup"><span data-stu-id="2fc7e-269">Manufacturer: *Your organization’s name*</span></span>
    -   <span data-ttu-id="2fc7e-270">バージョン: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="2fc7e-270">Version: **1.0.0**</span></span>
    -   <span data-ttu-id="2fc7e-271">**このパッケージにソース ファイルが含まれています**] チェック ボックスをオンに、 **SRS のバージョン 2: ルート証明書のパッケージ**のフォルダーにパスを入力し、**次へ**。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-271">Select the **This package contains source files** check box, enter the path to the **SRS v2 – Root Certificate Package** folder, and then select **Next**.</span></span>

4.  <span data-ttu-id="2fc7e-272">**プログラムを作成しない**を選択し、**次へ**します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-272">Select **Do not create a program**, and then select **Next**.</span></span>

5.  <span data-ttu-id="2fc7e-273">**設定の確認**] ページを確認し、**次へ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-273">Review the **Confirm the settings** page, and then select **Next**.</span></span>

6.  <span data-ttu-id="2fc7e-274">**閉じる**を選択します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-274">Select **Close**.</span></span>

### <a name="create-the-skype-room-systems-v2-deployment-kit-package"></a><span data-ttu-id="2fc7e-275">Skype ルーム システム v2 の展開キットのパッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-275">Create the Skype Room Systems v2 deployment kit package</span></span>

1.  <span data-ttu-id="2fc7e-276">**Skype ルーム システム v2 の 『 導入ガイド 』** の最新バージョンをダウンロードして<https://go.microsoft.com/fwlink/?linkid=851168>、ワークステーションにインストールするとします。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-276">Download the latest version of the **Skype Room Systems v2 deployment kit** from <https://go.microsoft.com/fwlink/?linkid=851168>, and install it to a workstation.</span></span>

2.  <span data-ttu-id="2fc7e-277">内容をコピーする**c:\\Program Files (x86)\\Skype ルーム システムの 『 導入ガイド 』** **SRS v2 の SRS のアプリケーション パッケージ**のフォルダーにします。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-277">Copy the content from **C:\\Program Files (x86)\\Skype Room System Deployment Kit** to the **SRS v2 - SRS Application Package** folder.</span></span>

3.  <span data-ttu-id="2fc7e-278">**ソフトウェア ライブラリ**には、構成マネージャー コンソールで、 \> **アプリケーション管理** \> **パッケージ**、および**パッケージの作成**を選択します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-278">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="2fc7e-279">パッケージを作成するのには次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-279">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="2fc7e-280">**SRS v2 – SRS アプリケーション パッケージ**の名前:</span><span class="sxs-lookup"><span data-stu-id="2fc7e-280">Name: **SRS v2 – SRS Application Package**</span></span>
    -   <span data-ttu-id="2fc7e-281">製造元: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="2fc7e-281">Manufacturer: **Microsoft Corporation**</span></span>
    -   <span data-ttu-id="2fc7e-282">バージョン: **3.1.104.0** (ダウンロードしたインストール ファイルのバージョンを入力してください)</span><span class="sxs-lookup"><span data-stu-id="2fc7e-282">Version: **3.1.104.0** (enter the version of the downloaded installation file)</span></span>
    -   <span data-ttu-id="2fc7e-283">**このパッケージにソース ファイルが含まれています**] チェック ボックスをオンに、 **SRS v2 – SRS アプリケーション パッケージ**フォルダーへのパスを入力し、[**次へ**。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-283">Select the **This package contains source files** check box, enter the path to the **SRS v2 – SRS Application Package** folder, and then select **Next**.</span></span>
5.  <span data-ttu-id="2fc7e-284">**プログラムを作成しない**を選択し、**次へ**します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-284">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="2fc7e-285">**設定の確認**] ページを確認し、**次へ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-285">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="2fc7e-286">**閉じる**を選択します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-286">Select **Close**.</span></span>

### <a name="create-the-computer-name-assignment-package"></a><span data-ttu-id="2fc7e-287">コンピューター名のアサイン パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-287">Create the computer name assignment package</span></span>

1.  <span data-ttu-id="2fc7e-288">**SRS v2 - セット SRSComputerName パッケージ**フォルダーには、**セット SRSComputerName.hta**をという名前の新しい HTML アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-288">In the **SRS v2 - Set-SRSComputerName Package** folder, create a new HTML application named **Set-SRSComputerName.hta** .</span></span>

2.  <span data-ttu-id="2fc7e-289">**セット SRSComputerName.hta**ファイルに次のスクリプトをコピーします。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-289">Copy the following script into the **Set-SRSComputerName.hta** file.</span></span> <span data-ttu-id="2fc7e-290">または、[ここ](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)からセット SRSComputerName.hta ファイルをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-290">Alternatively, you can download the Set-SRSComputerName.hta file from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
    ```
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
3.  <span data-ttu-id="2fc7e-291">**ソフトウェア ライブラリ**には、構成マネージャー コンソールで、 \> **アプリケーション管理** \> **パッケージ**、および**パッケージの作成**を選択します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-291">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="2fc7e-292">パッケージを作成するのには次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-292">Enter the following information to create the package:</span></span>

    -   <span data-ttu-id="2fc7e-293">**SRS v2 - セット SRSComputerName パッケージ**の名前:</span><span class="sxs-lookup"><span data-stu-id="2fc7e-293">Name: **SRS v2 - Set-SRSComputerName Package**</span></span>

    -   <span data-ttu-id="2fc7e-294">製造元: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="2fc7e-294">Manufacturer: **Microsoft Corporation**</span></span>

    -   <span data-ttu-id="2fc7e-295">バージョン: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="2fc7e-295">Version: **1.0.0**</span></span>

    -   <span data-ttu-id="2fc7e-296">**このパッケージにソース ファイルが含まれています**] チェック ボックスをオンに、 **SRS の v2 - セット SRSComputerName パッケージ**のフォルダーにパスを入力し、**次へ**。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-296">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Set-SRSComputerName Package** folder, and then select **Next**.</span></span>

5.  <span data-ttu-id="2fc7e-297">**プログラムを作成しない**を選択し、**次へ**します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-297">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="2fc7e-298">**設定の確認**] ページを確認し、**次へ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-298">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="2fc7e-299">**閉じる**を選択します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-299">Select **Close**.</span></span>

### <a name="create-the-sysprep-package"></a><span data-ttu-id="2fc7e-300">Sysprep パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-300">Create the Sysprep package</span></span>

1.  <span data-ttu-id="2fc7e-301">**SRS v2 – パッケージの Sysprep**フォルダーには、 **Unattend.xml**をという名前の新しい XML ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-301">In the **SRS v2 – Sysprep Package** folder, create a new XML file named **Unattend.xml** .</span></span>

2.  <span data-ttu-id="2fc7e-302">**Unattend.xml**ファイルに次のテキストをコピーします。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-302">Copy the following text into the **Unattend.xml** file.</span></span> <span data-ttu-id="2fc7e-303">または、Unattend.xml ファイルを[ここ](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-303">Alternatively, you can download the Unattend.xml file from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
```
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
3.  <span data-ttu-id="2fc7e-304">**ソフトウェア ライブラリ**には、構成マネージャー コンソールで、 \> **アプリケーション管理** \> **パッケージ**、および**パッケージの作成**を選択します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-304">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="2fc7e-305">パッケージを作成するのには次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-305">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="2fc7e-306">**SRS v2 の Sysprep のパッケージ**の名前:</span><span class="sxs-lookup"><span data-stu-id="2fc7e-306">Name: **SRS v2 - Sysprep Package**</span></span>
    -   <span data-ttu-id="2fc7e-307">製造元: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="2fc7e-307">Manufacturer: **Microsoft Corporation**</span></span>
    -   <span data-ttu-id="2fc7e-308">バージョン: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="2fc7e-308">Version: **1.0.0**</span></span>
    -   <span data-ttu-id="2fc7e-309">**このパッケージにソース ファイルが含まれています**] チェック ボックスをオンに、 **SRS v2 – パッケージの Sysprep**フォルダーにパスを入力し、**次へ**。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-309">Select the **This package contains source files** check box, enter the path to the **SRS v2 – Sysprep Package** folder, and then select **Next**.</span></span>
5.  <span data-ttu-id="2fc7e-310">**プログラムを作成しない**を選択し、**次へ**します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-310">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="2fc7e-311">**設定の確認**] ページを確認し、**次へ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-311">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="2fc7e-312">**閉じる**を選択します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-312">Select **Close**.</span></span>

### <a name="create-the-windows-10-enterprise-package"></a><span data-ttu-id="2fc7e-313">10 エンタープライズの Windows パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-313">Create the Windows 10 Enterprise package</span></span>

1.  <span data-ttu-id="2fc7e-314">、10 企業の Windows x64 メディアを入手し、 **install.wim**ファイルのコピー、**のオペレーティング システム\\10 企業の Windows**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-314">Obtain a Windows 10 Enterprise x64 media, and copy the **install.wim** file to the **Operating Systems\\Windows 10 Enterprise** folder.</span></span>

2.  <span data-ttu-id="2fc7e-315">**ソフトウェア ライブラリ**には、構成マネージャー コンソールで、 \> **のオペレーティング システム** \> **オペレーティング システム イメージ**、および [**オペレーティング システム イメージを追加**します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-315">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Operating System Images**, and then select **Add Operating System Image**.</span></span>

3.  <span data-ttu-id="2fc7e-316">**Install.wim**ファイルをコピーしたパスを指定し、**次へ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-316">Specify the path to the **install.wim** file you just copied, and then select **Next**.</span></span>

4.  <span data-ttu-id="2fc7e-317">10 エンタープライズの Windows イメージのビルド番号が一致するように **[バージョン**] フィールドを更新し、**次へ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-317">Update the **Version** field to match the build number of the Windows 10 Enterprise image, and then select **Next**.</span></span>

5.  <span data-ttu-id="2fc7e-318">、**詳細**ページを確認し、**次へ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-318">Review the **Details** page, and then select **Next**.</span></span>

6.  <span data-ttu-id="2fc7e-319">**閉じる**を選択します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-319">Select **Close**.</span></span>

<span data-ttu-id="2fc7e-320">詳細については、[オペレーティング システム イメージの管理システム センター構成マネージャーの使用](https://docs.microsoft.com/sccm/osd/get-started/manage-operating-system-images)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-320">For more information, see [Manage operating system images with System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-operating-system-images).</span></span>

### <a name="create-surface-pro-device-driver-packages"></a><span data-ttu-id="2fc7e-321">Surface Pro デバイス ドライバー パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-321">Create Surface Pro device driver packages</span></span>

<span data-ttu-id="2fc7e-322">Skype ルーム システム v2 は Surface Pro と Surface Pro 4 の両方のサポートします。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-322">Skype Room Systems v2 is supported for both Surface Pro and Surface Pro 4.</span></span> <span data-ttu-id="2fc7e-323">環境内の各 Surface Pro モデル用のドライバー パッケージを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-323">You need to create a driver package for each Surface Pro model you have in your environment.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2fc7e-324">ドライバーは、Windows 10 エンタープライズ ビルドおよび Skype ルーム システム v2 の展開キットのバージョンとの互換性である必要があります。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-324">The drivers must be compatible with the Windows 10 Enterprise build and the Skype Room Systems v2 deployment kit version.</span></span> <span data-ttu-id="2fc7e-325">詳細については、[最新のファームウェア、および表面のデバイス用のドライバーをダウンロード](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices)し[、コンソールの構成](console.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-325">For more information, see [Download the latest firmware and drivers for Surface devices](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) and [Configure a console](console.md).</span></span>

1.  <span data-ttu-id="2fc7e-326">最新のドライバーとファームウェアをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-326">Download the latest drivers and firmware.</span></span>
    -   <span data-ttu-id="2fc7e-327">Surface Pro: の<https://www.microsoft.com/download/details.aspx?id=55484></span><span class="sxs-lookup"><span data-stu-id="2fc7e-327">For Surface Pro: <https://www.microsoft.com/download/details.aspx?id=55484></span></span>
    -   <span data-ttu-id="2fc7e-328">Surface Pro の 4 を実行します。<https://www.microsoft.com/download/details.aspx?id=49498></span><span class="sxs-lookup"><span data-stu-id="2fc7e-328">For Surface Pro 4: <https://www.microsoft.com/download/details.aspx?id=49498></span></span>

2.  <span data-ttu-id="2fc7e-329">ダウンロードしたドライバーとファームウェアを抽出します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-329">Extract the downloaded driver and firmware.</span></span> <span data-ttu-id="2fc7e-330">コマンド プロンプト ウィンドウを開き、コマンド プロンプトで次のコマンドのいずれかを入力します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-330">Open a Command Prompt window and at the command prompt, enter one of the following commands:</span></span>
    -   `msiexec /a C:\SurfacePro_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro"`
    -   `msiexec /a C:\SurfacePro4_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro 4"`

3.  <span data-ttu-id="2fc7e-331">**ソフトウェア ライブラリ**には、構成マネージャー コンソールで、 \> **のオペレーティング システム** \> **ドライバー**、および**インポート ドライバー**を選択します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-331">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Drivers**, and then select **Import Driver**.</span></span>

4.  <span data-ttu-id="2fc7e-332">**次のネットワーク パス (UNC) のすべてのドライバーをインポート**] を選択、コピー元フォルダーを選択 (例、c:\\_Sources\\ドライバー\\Surface Pro)、し、**次へ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-332">Select **Import all drivers in the following network path (UNC)**, select the source folder (for example, C:\\_Sources\\Drivers\\Surface Pro), and then select **Next**.</span></span>

5.  <span data-ttu-id="2fc7e-333">**読み込まれたドライバーの詳細を指定**] ページで、一覧表示されているすべてのドライバーを選択し、選択**これらのドライバーを有効にしてコンピューターにインストールを許可します**。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-333">On the **Specify the details for the imported drivers** page, select all the listed drivers, and then select **Enable these drivers and allow computers to install them**.</span></span>

6.  <span data-ttu-id="2fc7e-334">**カテゴリ**を選択して、サーフェス モデルと一致する新しいカテゴリを作成、 **[ok]** を選択し、**次へ**。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-334">Select **Categories**, create a new category that matches the Surface model, select **OK**, and then select **Next**.</span></span>

7.  <span data-ttu-id="2fc7e-335">**新しいパッケージ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-335">Select **New Package**.</span></span>

8.  <span data-ttu-id="2fc7e-336">Surface Pro のモデルと一致するパッケージ名を指定して、 **[ok]** を選択して、[**次へ**]、ドライバー パッケージ内のファイルを格納するフォルダーのパスを入力します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-336">Specify the package name that matches the Surface Pro model, enter a folder path to store the driver package files in, select **OK**, and then select **Next**.</span></span>

9.  <span data-ttu-id="2fc7e-337">[**ブート イメージ**] ページで、ブート イメージが選択されていると、**次へ**を選択しであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-337">On the **boot images** page, ensure that no boot images are selected, and then select **Next**.</span></span>

10. <span data-ttu-id="2fc7e-338">**閉じる**を選択します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-338">Select **Close**.</span></span>

11. <span data-ttu-id="2fc7e-339">**ソフトウェア ライブラリ**を参照して\>**のオペレーティング システム** \> **ドライバー**を選択**フォルダー\>フォルダーの作成**、Surface Pro のドライバーをインポートしたモデルと一致するフォルダー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-339">Go to **Software Library** \> **Operating Systems** \> **Drivers**, select **Folder \> Create Folder**, and enter a folder name that matches the Surface Pro model that you just imported the drivers for.</span></span>

12. <span data-ttu-id="2fc7e-340">インポートされたすべてのドライバーを簡単に移動および操作の新しく作成したフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-340">Move all the imported drivers to the newly created folder for easier navigation and operation.</span></span>

> [!NOTE]
> <span data-ttu-id="2fc7e-341">他の Surface Pro モデルをする必要があります、同じ手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-341">Repeat the same steps for other Surface Pro models you might have.</span></span> <span data-ttu-id="2fc7e-342">詳細については、[システム センター構成マネージャーでの管理ドライバー](https://docs.microsoft.com/sccm/osd/get-started/manage-drivers)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-342">For more information, see [Manage drivers in System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-drivers).</span></span>

## <a name="distribute-configuration-manager-packages"></a><span data-ttu-id="2fc7e-343">構成マネージャー パッケージを配布します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-343">Distribute Configuration Manager packages</span></span>

<span data-ttu-id="2fc7e-344">すべてのパッケージは、構成マネージャー階層内の配布ポイントの役割が割り当てられているサーバーに分散する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-344">All the packages must be distributed to the servers that have been assigned the distribution point role in the Configuration Manager hierarchy.</span></span> <span data-ttu-id="2fc7e-345">パッケージの配布を開始するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-345">Follow the instructions below to initiate package distribution.</span></span>

1.  <span data-ttu-id="2fc7e-346">ソフトウェア パッケージを配布します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-346">Distribute software packages.</span></span>

    1.  <span data-ttu-id="2fc7e-347">**ソフトウェア ライブラリ**には、構成マネージャー コンソールで、 \> **アプリケーション管理** \> **パッケージ**です。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-347">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**.</span></span> <span data-ttu-id="2fc7e-348">、配布するすべてのソフトウェア パッケージを選択し、**コンテンツを配布**します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-348">Select all the software packages you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="2fc7e-349">、パッケージのリストを確認し、**次へ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-349">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="2fc7e-350">すべての配布ポイント サーバー (または、構成マネージャー階層に応じて、配布ポイント グループ) をリストに追加し、**次へ**します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-350">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="2fc7e-351">**次へ**を選択し、[**閉じる**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-351">Select **Next**, and then select **Close**.</span></span>

2.  <span data-ttu-id="2fc7e-352">ドライバー パッケージを配布します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-352">Distribute driver packages.</span></span>

    1.  <span data-ttu-id="2fc7e-353">**ソフトウェア ライブラリ**には、構成マネージャー コンソールで、 \> **のオペレーティング システム** \> **のドライバー パッケージ**。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-353">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Driver Packages**.</span></span> <span data-ttu-id="2fc7e-354">、配布するすべてのドライバー パッケージを選択し、**コンテンツを配布**します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-354">Select all the driver packages you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="2fc7e-355">、パッケージのリストを確認し、**次へ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-355">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="2fc7e-356">すべての配布ポイント サーバー (または、構成マネージャー階層に応じて、配布ポイント グループ) をリストに追加し、**次へ**します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-356">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="2fc7e-357">**次へ**を選択し、[**閉じる**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-357">Select **Next**, and then select **Close**.</span></span>

3.  <span data-ttu-id="2fc7e-358">オペレーティング システム パッケージを配布します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-358">Distribute operating system packages.</span></span>

    1.  <span data-ttu-id="2fc7e-359">**ソフトウェア ライブラリ**には、構成マネージャー コンソールで、 \> **のオペレーティング システム** \> **オペレーティング システムのイメージ**です。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-359">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Operating System Images**.</span></span> <span data-ttu-id="2fc7e-360">、配布するすべてのオペレーティング システム イメージを選択し、**コンテンツを配布**します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-360">Select all the operating system images you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="2fc7e-361">、パッケージのリストを確認し、**次へ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-361">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="2fc7e-362">すべての配布ポイント サーバー (または、構成マネージャー階層に応じて、配布ポイント グループ) をリストに追加し、**次へ**します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-362">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="2fc7e-363">**次へ**を選択し、[**閉じる**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-363">Select **Next**, and then select **Close**.</span></span>

> [!NOTE]
> <span data-ttu-id="2fc7e-364">パッケージの配布には、パッケージのサイズ、構成マネージャー階層、配布ポイント サーバーの数は、ネットワークで利用できる帯域幅によっては、時間をかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-364">Package distribution might take some time, depending on the package size, Configuration Manager hierarchy, number of distribution point servers, and the bandwidth available in your network.</span></span>

> <span data-ttu-id="2fc7e-365">Skype ルーム システム v2 のユニットを展開する前にすべてのパッケージを配布する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-365">All the packages must be distributed before you can start deploying a Skype Room Systems v2 unit.</span></span>

> <span data-ttu-id="2fc7e-366">構成マネージャー コンソールで、パッケージの配布ステータスを確認するには**監視**することで\>**の配布ステータス** \> **コンテンツの状態**です。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-366">You can review the status of your package distribution in the Configuration Manager console by going to **Monitoring** \> **Distribution Status** \> **Content Status**.</span></span>

## <a name="configuration-manager-task-sequences"></a><span data-ttu-id="2fc7e-367">構成マネージャーのタスク シーケンス</span><span class="sxs-lookup"><span data-stu-id="2fc7e-367">Configuration Manager task sequences</span></span>

<span data-ttu-id="2fc7e-368">使用して、タスク シーケンスがシステム センター構成マネージャーをセットアップ先のコンピューターにオペレーティング システム イメージを展開するための手順を自動化します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-368">You use task sequences with System Center Configuration Manager to automate the steps for deploying an operating system image to a destination computer.</span></span> <span data-ttu-id="2fc7e-369">Skype ルーム システム v2 をセットアップ先のコンピューター、10 企業の Windows オペレーティング システム イメージをインストールしていずれかを起動するために使用するブート イメージを参照するタスク シーケンスを作成する自動化された方法で Skype ルーム システム v2 のユニットを配置するには他のアプリケーションやソフトウェア更新プログラムなどの他の追加コンテンツ。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-369">To deploy a Skype Room Systems v2 unit in an automated fashion, you create a task sequence that references the boot image used to start the destination Skype Room Systems v2 computer, the Windows 10 Enterprise operating system image that you want to install, and any other additional content, such as other applications or software updates.</span></span>

### <a name="import-the-sample-task-sequence"></a><span data-ttu-id="2fc7e-370">サンプル タスク シーケンスをインポートします。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-370">Import the sample task sequence</span></span>

<span data-ttu-id="2fc7e-371">ダウンロードし簡単にサンプルのタスク シーケンスをインポートしてお客様のニーズを満たすためにカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-371">You can download and easily import a sample task sequence and customize it to meet your needs.</span></span>

1.  <span data-ttu-id="2fc7e-372">サンプルのタスク シーケンス[**をダウンロード**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)し、共有の場所にダウンロードした zip ファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-372">[**Download**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) the sample task sequence, and copy the downloaded zip file to a shared location.</span></span>
2.  <span data-ttu-id="2fc7e-373">**ソフトウェア ライブラリ**には、構成マネージャー コンソールで、 \> **のオペレーティング システム** \> **タスク シーケンス**、および選択し、**タスク シーケンスのインポート**します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-373">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Task Sequences**, and then select **Import Task Sequence**.</span></span>

3.  <span data-ttu-id="2fc7e-374">**参照**を選択して、手順 1 で使用する共有フォルダーの場所に、 **Skype ルーム システム v2 (EN-US) の展開の .zip**ファイルを選択し、**次**のように選択を移動します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-374">Select **Browse**, go to the shared folder location you used in step 1, select the **Skype Room Systems v2 Deployment (EN-US).zip** file, and then select **Next**.</span></span>

4.  <span data-ttu-id="2fc7e-375">**アクション**を**新規作成**] を設定し、**次へ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-375">Set **Action** to **Create New**, and then select **Next**.</span></span>

5.  <span data-ttu-id="2fc7e-376">設定内容を確認し、**次へ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-376">Confirm the settings, and then select **Next**.</span></span>

6.  <span data-ttu-id="2fc7e-377">**閉じる**を選択します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-377">Select **Close**.</span></span>

### <a name="validate-that-the-reference-packages-are-correctly-linked-to-each-task-sequence-step"></a><span data-ttu-id="2fc7e-378">各タスク シーケンスのステップには、参照のパッケージが正しくリンクされているかを検証します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-378">Validate that the reference packages are correctly linked to each task sequence step.</span></span>

1.  <span data-ttu-id="2fc7e-379">、インポートされたタスク シーケンスを選択し、**編集**を選択します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-379">Select the imported task sequence, and then select **Edit**.</span></span>

     <span data-ttu-id="2fc7e-380">タスク シーケンス エディターが開き、展開し、Skype ルーム システム v2 の単位を構成する必要がある連続した各ステップが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-380">The Task Sequence Editor opens and displays each sequential step that you need to deploy and configure a Skype Room Systems v2 unit.</span></span>

1.  <span data-ttu-id="2fc7e-381">各ステップを紹介し、推奨される更新プログラムを完了します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-381">Walk through each step and complete the recommended updates:</span></span>

    1.  <span data-ttu-id="2fc7e-382">**Windows PE で再起動**: この手順が再起動し、Windows の PXE にコンピューターを起動します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-382">**Restart in Windows PE**: This step restarts and then boots the computer into Windows PXE.</span></span> <span data-ttu-id="2fc7e-383">変更は、この手順で必要ではありません。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-383">No changes are required for this step.</span></span>

    2.  <span data-ttu-id="2fc7e-384">**パーティション ディスク 0-UEFI**: この手順は、ディスク構成を消去し、構成した設定に基づいてパーティションを作成します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-384">**Partition Disk 0 – UEFI**: This step wipes the disk configuration and creates partitions based on the configured settings.</span></span> <span data-ttu-id="2fc7e-385">おすべての変更この手順をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-385">We recommend that you not make any changes to this step.</span></span>

    3.  <span data-ttu-id="2fc7e-386">**SRS コンピューター名の設定**: この手順には、展開時に Skype ルーム システム v2 単位のコンピューター名を設定するための UI を提供する HTML アプリケーションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-386">**Set SRS Computer Name**: This step includes an HTML application to provide a UI to set a computer name for the Skype Room Systems v2 unit during the deployment.</span></span>
        -  <span data-ttu-id="2fc7e-387">これはオプションの手順ですが、それのみを無効にできます、別のプロセスによって名前付けのコンピューターを管理する場合は。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-387">This is an optional step, but it can only be disabled if you want to manage computer naming through an alternate process.</span></span>
        -  <span data-ttu-id="2fc7e-388">**SRS v2 - セット SRSComputerName**パッケージが選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-388">Verify that the **SRS v2 - Set-SRSComputerName** package is selected.</span></span> <span data-ttu-id="2fc7e-389">いない場合は、パッケージを参照して選択します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-389">If it isn’t, browse to the package and select it.</span></span>

    4.  <span data-ttu-id="2fc7e-390">**オペレーティング システムの適用**: この手順は、オペレーティング システム イメージを展開して、無人 Sysprep 応答ファイルを使用するを指定します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-390">**Apply Operating System**: This step specifies the operating system image to be deployed and the unattended Sysprep answer file to use.</span></span>
        -  <span data-ttu-id="2fc7e-391">正しい 10 企業の Windows オペレーティング システム イメージ ファイルが選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-391">Verify that the correct Windows 10 Enterprise operating system image file is selected.</span></span>
        -  <span data-ttu-id="2fc7e-392">**無人を使用するかカスタム インストール用応答ファイルを Sysprep**を有効にすると、 **SRS v2 の Sysprep のパッケージ**が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-392">Verify that **Use an unattended or Sysprep answer file for a custom installation** is enabled, and the **SRS v2 - Sysprep Package** is selected.</span></span> <span data-ttu-id="2fc7e-393">**Unattend.xml**に**ファイル名**が設定されていることを確認もします。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-393">Also ensure that **File Name** is set to **unattend.xml**.</span></span>

    5.  <span data-ttu-id="2fc7e-394">**Windows の設定を適用**: この手順は、Windows のインストールに関する情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-394">**Apply Windows Settings**: This step gathers information about the Windows installation.</span></span>
        -  <span data-ttu-id="2fc7e-395">プロダクト キー、ローカルの管理者アカウントのパスワード、および (必要) に応じて、タイム ゾーンを含むライセンスと登録の情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-395">Provide licensing and registration information including the product key, local administrator account password, and time zone (depending on your needs).</span></span>

    6.  <span data-ttu-id="2fc7e-396">**ネットワーク設定を適用**: この手順では、ワークグループまたは Active Directory ドメイン名と組織単位を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-396">**Apply Network Settings**: This step allows you to specify a workgroup or Active Directory domain name and organizational unit.</span></span>
    > [!NOTE]
    > <span data-ttu-id="2fc7e-397">Actve ディレクトリ ドメインのメンバーとして Skype ルーム システム v2 のユニットを展開する必要がある、推奨される操作の[Skype ルーム システム ドメイン参加の注意事項](domain-joining-considerations.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-397">See [Skype Room System domain joining considerations](domain-joining-considerations.md) for recommended actions you need to take in deploying Skype Room Systems v2 units as members of an Actve Directory domain.</span></span>
    7.  <span data-ttu-id="2fc7e-398">**ドライバーを適用する:** この手順とその下位の手順は、適用可能なデバイス ドライバーとファームウェアがある Surface Pro モデルをベースに展開する使用されます。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-398">**Apply Drivers:** This step and its sub-steps are used to deploy applicable device drivers and firmware based on the Surface Pro model you have.</span></span> <span data-ttu-id="2fc7e-399">この展開に関連付けられている関連するドライバー パッケージを指定するには、各ステップを更新します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-399">Update each step to specify the relevant driver package associated with this deployment.</span></span>
        -   <span data-ttu-id="2fc7e-400">関連ドライバーを展開する Windows 管理インストルメンテーション (WMI) フィルターを活用する各ドライバー パッケージを構成し、Surface Pro のファームウェアの製造元しモデルします。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-400">Each driver package is configured to leverage Windows Management Instrumentation (WMI) filters to deploy relevant drivers and firmware based on the Surface Pro make and model.</span></span>
        -   <span data-ttu-id="2fc7e-401">これらのドライバーの構成を変更、配置が失敗する可能性がありますそれ以外の場合のことを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-401">We highly recommend that you not alter the configuration of these drivers, otherwise deployment might fail.</span></span>

    8.  <span data-ttu-id="2fc7e-402">**Windows と構成マネージャーの設定**: このステップの配置し、構成マネージャーのクライアントを構成します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-402">**Set up Windows and Configuration Manager**: This step deploys and configures the Configuration Manager client.</span></span> <span data-ttu-id="2fc7e-403">組み込みの構成マネージャーのクライアント パッケージを指定するには、この手順を更新します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-403">Update this step to specify the built-in Configuration Manager Client Package.</span></span>

    9.  <span data-ttu-id="2fc7e-404">**ルート証明書のインストール**: この手順は: ドメインに参加しているデバイスでは、ルート証明書を配布し、そのため、省略可能な既定で無効になっています。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-404">**Install Root Certificate**: This step distributes the root certificate for non–domain-joined devices, and therefore is optional and disabled by default.</span></span>
        -   <span data-ttu-id="2fc7e-405">Skype ルーム システム v2 ユニットにルート証明書を展開する必要がある場合は、この手順を有効にします。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-405">Enable this step if you need to deploy a root certificate to the Skype Room Systems v2 units.</span></span>
        -   <span data-ttu-id="2fc7e-406">この手順を実行する必要がある場合は、 **SRS のバージョン 2: ルート証明書のパッケージ**と**ファイル システムのリダイレクトを無効にする 64 ビット**がオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-406">If you do need to perform this step, verify that the **SRS v2 – Root Certificate Package** and **Disable 64-bit file system redirection** are selected.</span></span>

    10. <span data-ttu-id="2fc7e-407">**インストールおよび OMS のエージェントの構成**: この手順は、オペレーションの管理スイートの Microsoft エージェントの 64 ビット バージョンをインストールし、エージェントが、ログの分析機能のワークスペースへの接続を構成します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-407">**Install and Configure OMS Agent**: This step installs the 64-bit version of the Microsoft Operations Management Suite agent and configures the agent to connect to your Log Analytics workspace.</span></span>
        -   <span data-ttu-id="2fc7e-408">この手順は既定で無効になります。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-408">This step is disabled by default.</span></span> <span data-ttu-id="2fc7e-409">OMS を使用して、Skype ルーム システム v2 の単位の状態を監視しようとしている場合にのみ、この手順を有効にします。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-409">Enable this step only if you’re going to use OMS to monitor the health of your Skype Room Systems v2 units.</span></span>
        -   <span data-ttu-id="2fc7e-410">このステップを編集し、自分の**ワークスペースの ID**と**キーのワークスペース**を指定するコマンド ライン パラメーターを更新します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-410">Edit this step and update the command-line parameters to specify your **Workspace ID** and **Workspace Key**.</span></span>
        -   <span data-ttu-id="2fc7e-411">操作の管理スイートのワークスペース ID とプライマリ ・ キーの入手方法の詳細については、[接続の Windows コンピューター](with-oms.md#configure-test-devices-for-operations-management-suite-setup)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-411">See [Connect Windows computers to the Log Analytics service in Azure](with-oms.md#configure-test-devices-for-operations-management-suite-setup) for more information about obtaining the Operations Management Suite Workspace ID and the primary key.</span></span>
        -   <span data-ttu-id="2fc7e-412">**SRS v2 – マイクロソフト OMS エージェント パッケージ**と**ファイル システムのリダイレクトを無効にする 64 ビット**がオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-412">Verify that the **SRS v2 – Microsoft OMS Agent Package** and **Disable 64-bit file system redirection** are selected.</span></span>
        -   <span data-ttu-id="2fc7e-413">Skype ルーム システム v2 の配置の状態の監視の詳細については、 [OMS を使用しての Skype ルーム システムの計画 v2 の管理](../../plan-your-deployment/clients-and-devices/oms-management.md)および[OMS を使用して Skype ルーム システムの展開 v2 の管理](with-oms.md#configure-test-devices-for-operations-management-suite-setup)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-413">For more information about monitoring the health of your Skype Room Systems v2 deployment, see [Plan Skype Room Systems v2 management with OMS](../../plan-your-deployment/clients-and-devices/oms-management.md) and [Deploy Skype Room Systems v2 management with OMS](with-oms.md#configure-test-devices-for-operations-management-suite-setup).</span></span>

    11. <span data-ttu-id="2fc7e-414">**V2 構成ファイルのコピーの SRS**: この手順は、ローカル ハード ドライブに Skype ルーム システム v2 の導入ガイド 』 から必要なセットアップと構成ファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-414">**Copy SRS v2 Configuration Files**: This step copies the required setup and configuration files from the Skype Room Systems v2 deployment kit to the local hard drive.</span></span> <span data-ttu-id="2fc7e-415">カスタマイズは、この手順は必要ではありません。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-415">No customization is required for this step.</span></span>
        -   <span data-ttu-id="2fc7e-416">**SRS v2 – SRS アプリケーション パッケージ**と**ファイル システムのリダイレクトを無効にする 64 ビット**がオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-416">Verify that the **SRS v2 – SRS Application Package** and **Disable 64-bit file system redirection** are selected.</span></span>

    12. <span data-ttu-id="2fc7e-417">**SRSv2-OS の更新プログラムをインストール**: この手順は、Skype ルーム システム v2 の展開に必要なオペレーティング システムの必須更新プログラムを配置します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-417">**Install-SRSv2-OS-Updates**: This step deploys any mandatory operating system updates required with the Skype Room Systems v2 deployment.</span></span> <span data-ttu-id="2fc7e-418">次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-418">Do the following:</span></span>
        -   <span data-ttu-id="2fc7e-419">必要な更新プログラムを確認するのには、 [Skype ルーム システムのバージョン 2 を構成するコンソール](console.md)を確認してください。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-419">Check [Configure a Skype Room Systems v2 console](console.md) to see which updates are required.</span></span>
        -   <span data-ttu-id="2fc7e-420">**SRS v2 – OS の更新プログラム パッケージ**に必要なすべての更新プログラムが含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-420">Verify that your **SRS v2 – OS Updates Package** includes all the required updates.</span></span>
        -   <span data-ttu-id="2fc7e-421">**SRS v2 – OS の更新プログラム パッケージ**が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-421">Verify that the **SRS v2 – OS Updates Package** is selected.</span></span>
        -   <span data-ttu-id="2fc7e-422">PowerShell 実行ポリシーを**バイパス**に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-422">Verify that the PowerShell execution policy is set to **Bypass**.</span></span>

    13. <span data-ttu-id="2fc7e-423">**コンピューターの再起動**: この手順は、オペレーティング システムの必須更新プログラムをインストールした後にコンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-423">**Restart Computer**: This step reboots the computer after the mandatory operating system updates are installed.</span></span> <span data-ttu-id="2fc7e-424">カスタマイズは、この手順は必要ではありません。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-424">No customization is required for this step.</span></span>

    14. <span data-ttu-id="2fc7e-425">**Windows コンポーネントの構成**: この手順が必要な Windows の機能を構成します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-425">**Configure Windows Components**: This step configures the required Windows features.</span></span> <span data-ttu-id="2fc7e-426">カスタマイズは、この手順は必要ではありません。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-426">No customization is required for this step.</span></span>

    15. <span data-ttu-id="2fc7e-427">**コンピューターの再起動**: この手順は、Windows の機能を構成した後にコンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-427">**Restart Computer**: This step reboots the computer after the Windows features are configured.</span></span> <span data-ttu-id="2fc7e-428">カスタマイズは、この手順は必要ではありません。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-428">No customization is required for this step.</span></span>

    16. <span data-ttu-id="2fc7e-429">**ローカル Skype ユーザーの追加**: この手順が自動的に Windows にサインインして Skype ルーム システム v2 アプリケーションを起動するために使用するローカル Skype アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-429">**Add Local Skype User**: This step creates the local Skype account used to automatically sign in to Windows and start the Skype Room Systems v2 application.</span></span> <span data-ttu-id="2fc7e-430">この手順は、それに関連付けられている任意のソフトウェア パッケージを持っていないし、カスタマイズすることの必要はありません。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-430">This step doesn’t have any software package associated with it, and no customization is required for it.</span></span>

    17. <span data-ttu-id="2fc7e-431">**設定セットアップおよび SRS のアプリケーションを構成する**: この操作により、Skype ルーム システム v2 アプリケーションのインストール、次の起動時にオペレーティング システムの。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-431">**Set up and configure SRS application**: This step configures the Skype Room Systems v2 application installation for the next boot of the operating system.</span></span>
        -   <span data-ttu-id="2fc7e-432">**SRS v2 – SRS セットアップ パッケージの構成**と**ファイル システムのリダイレクトを無効にする 64 ビット**がオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-432">Verify that the **SRS v2 – Configure SRS Setup Package** and **Disable 64-bit file system redirection** are selected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2fc7e-433">タスク シーケンスの手順が記載されている順序である必要がありますが非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-433">It is very important that the task sequence steps must be in the provided order.</span></span> <span data-ttu-id="2fc7e-434">手順の順序を変更または追加の手順を構成するには、展開を壊れる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-434">Modifying the order of steps, or configuring additional steps might break the deployment.</span></span>
>
> <span data-ttu-id="2fc7e-435">**設定セットアップおよび SRS のアプリケーションを構成する**の手順は、タスク シーケンスの最後のステップをする必要があります、それ以外の場合、展開が失敗可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-435">**Set up and configure SRS application** step must be the last step in the task sequence, otherwise the deployment might fail.</span></span>

### <a name="create-deployment-for-the-task-sequence"></a><span data-ttu-id="2fc7e-436">展開タスク シーケンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-436">Create deployment for the task sequence</span></span>

1.  <span data-ttu-id="2fc7e-437">タスク シーケンスを選択し、[**配置**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-437">Select the task sequence, and then select **Deploy**.</span></span>

2.  <span data-ttu-id="2fc7e-438">展開のターゲット コレクションを選択する**参照**を選択します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-438">Select **Browse** to select target collection for deployment.</span></span>

3.  <span data-ttu-id="2fc7e-439">**すべての不明なコンピューター**を選択し、 **[ok]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-439">Select **All Unknown Computers** and then select **OK**.</span></span>

4.  <span data-ttu-id="2fc7e-440">**次へ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-440">Select **Next**.</span></span>

5.  <span data-ttu-id="2fc7e-441">**目的**のドロップ ダウン リストで**利用可能な**を選択します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-441">Select **Available** on the **Purpose** drop down list.</span></span>

6.  <span data-ttu-id="2fc7e-442">**次に使用できるように**する] の一覧で、**のみメディアおよび PXE**を選択し、**次へ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-442">Select **Only Media and PXE** in the **Make available to the following** list, and then select **Next**.</span></span>
> [!WARNING]
> <span data-ttu-id="2fc7e-443">**目的**が**使用可能**に設定されているが非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-443">It is very important that **Purpose** is set to **Available**.</span></span> <span data-ttu-id="2fc7e-444">**目的**では**ない**に**必要な**設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-444">Make sure that the **Purpose** is **NOT** set to **Required**.</span></span> <span data-ttu-id="2fc7e-445">また **、次に使用できるように**する**だけのメディアと PXE**を選択することを確認します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-445">Also make sure that you select **Only Media and PXE** in the **Make available to the following**.</span></span>
>
> <span data-ttu-id="2fc7e-446">別のものにこれらの値を設定すると、すべてのコンピューターの起動時に Skype ルーム システムの展開イメージを取得する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-446">Setting these values to something else might cause all computers to get the Skype Room Systems deployment image when booted.</span></span>
7.  <span data-ttu-id="2fc7e-447">ない任意のスケジュールを指定する] をクリック**します。**</span><span class="sxs-lookup"><span data-stu-id="2fc7e-447">Do not specify any schedule and select **Next**.</span></span>

8.  <span data-ttu-id="2fc7e-448">ない**ユーザー エクスペリエンス**セクション内のすべての変更] をクリック**します。**</span><span class="sxs-lookup"><span data-stu-id="2fc7e-448">Do not change anything within the **User Experience** section and select **Next**.</span></span>

9.  <span data-ttu-id="2fc7e-449">ない、[**通知**] セクション内のすべての変更] をクリック**します。**</span><span class="sxs-lookup"><span data-stu-id="2fc7e-449">Do not change anything within the **Alerts** section and select **Next**.</span></span>

10.  <span data-ttu-id="2fc7e-450">されない、[**配布ポイント**] セクション内のすべての変更] をクリック**します。**</span><span class="sxs-lookup"><span data-stu-id="2fc7e-450">Do not change anything within the **Distribution Points** section and select **Next**.</span></span>

11.  <span data-ttu-id="2fc7e-451">設定を確認し、**次へ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-451">Confirm the settings and then select **Next**.</span></span>

12.  <span data-ttu-id="2fc7e-452">**閉じる**を選択します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-452">Select **Close**.</span></span>

<a name="validate-and-troubleshoot-the-solution"></a><span data-ttu-id="2fc7e-453">検証し、ソリューションのトラブルシューティングを行う</span><span class="sxs-lookup"><span data-stu-id="2fc7e-453">Validate and troubleshoot the solution</span></span>
--------------------------------------

<span data-ttu-id="2fc7e-454">システム センター構成マネージャーのタスク シーケンスが完了したら、タスク シーケンスが展開および Skype ルーム システム v2 の単位を構成することを検証するために実行するテストを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-454">After you’ve completed the System Center Configuration Manager task sequences, you’ll need to perform a test run to validate that the task sequence can deploy and configure Skype Room Systems v2 units.</span></span>

1.  <span data-ttu-id="2fc7e-455">サポートされているイーサネット アダプターのいずれかまたは表面のドッキング ステーションを使用してワイヤード (有線) ネットワークへのテスト デバイスを接続します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-455">Connect the test device to the wired network by using one of the supported Ethernet adapters or using the Surface dock.</span></span> <span data-ttu-id="2fc7e-456">環境内の PXE ブート機能が構成されていない場合は、USB からブートし、構成マネージャーに接続する USB フラッシュ ドライブで[以前に作成した](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media)ブート イメージを使用できます。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-456">If PXE boot functionality hasn’t been configured for your environment, you can use the boot image on the USB flash drive [that you created earlier](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media) to boot from USB and connect to Configuration Manager.</span></span>

2.  <span data-ttu-id="2fc7e-457">ファームウェアにアクセスし、PXE ブートを開始します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-457">Access the firmware and initiate PXE boot:</span></span>

    1.  <span data-ttu-id="2fc7e-458">サーフェスのデバイスの電源を切ったことを確認します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-458">Ensure the Surface device is powered off.</span></span>

    2.  <span data-ttu-id="2fc7e-459">**音量アップ**ボタンを押したままにします。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-459">Press and hold the **Volume Up** button.</span></span>

    3.  <span data-ttu-id="2fc7e-460">キーを押し、**電源**ボタンを離します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-460">Press and release the **Power** button.</span></span>

    4.  <span data-ttu-id="2fc7e-461">デバイス ブートには、**ボリュームの**ボタンを離すと開始します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-461">After the device begins to boot, release the **Volume Up** button.</span></span>

    5.  <span data-ttu-id="2fc7e-462">**ブート構成**を選択します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-462">Select **Boot configuration**.</span></span>

    6.  <span data-ttu-id="2fc7e-463">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-463">Do one of the following:</span></span>

        -   <span data-ttu-id="2fc7e-464">**PXE ブート**を選択し、一覧の一番上にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-464">Select **PXE boot**, and drag it to the top of the list.</span></span> <span data-ttu-id="2fc7e-465">代わりに、デバイスをすぐに起動するようにネットワーク アダプターの左を読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-465">Alternatively, you can swipe left on the network adapter to boot to the device immediately.</span></span> <span data-ttu-id="2fc7e-466">これは、起動順序には影響しません。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-466">This won’t affect the boot order.</span></span>
        -   <span data-ttu-id="2fc7e-467">ブート メディアを保持している USB フラッシュ ドライブを選択します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-467">Select the USB flash drive that holds the boot media.</span></span>

3.  <span data-ttu-id="2fc7e-468">**終了**] を選択し、[**今すぐ再起動**します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-468">Select **Exit**, and then select **Restart Now**.</span></span>

4.  <span data-ttu-id="2fc7e-469">ダイアログ ボックスが表示されたら、ネットワーク ブート サービスの**入力**を選択します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-469">When prompted, select **Enter** for network boot service.</span></span>

5.  <span data-ttu-id="2fc7e-470">Windows PE をメモリにロードされ、タスク シーケンス ウィザードが開始されます。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-470">Windows PE will load into memory, and the Task Sequence Wizard will start.</span></span> <span data-ttu-id="2fc7e-471">**次**へを選択します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-471">Select **Next** to continue.</span></span>

6.  <span data-ttu-id="2fc7e-472">以前では、インポートしたタスク シーケンスを選択し、[**次へ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-472">Select the task sequence that you imported earlier, and then select **Next**.</span></span>

7.  <span data-ttu-id="2fc7e-473">ディスク構成を適用した後、デバイスのコンピューター名を指定するように求めします。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-473">After the disk configuration is applied, you’ll be prompted to specify a computer name for the device.</span></span> <span data-ttu-id="2fc7e-474">Surface Pro デバイスのシリアル番号に基づいて推奨されるコンピューター名は、ユーザー インターフェイスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-474">The user interface will display a recommended computer name based on the serial number of the Surface Pro device.</span></span> <span data-ttu-id="2fc7e-475">提案された名前をそのまま使用するか、新しいパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-475">You can either accept the proposed name or specify a new one.</span></span> <span data-ttu-id="2fc7e-476">コンピューター名の割り当て] 画面の指示に従います。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-476">Follow the instructions on the computer name assignment screen.</span></span> <span data-ttu-id="2fc7e-477">**承諾**を選択すると、展開を開始します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-477">When you select **Accept**, the deployment begins.</span></span>

8.  <span data-ttu-id="2fc7e-478">展開プロセスの残りの部分は、自動、複数のユーザーの入力を要求しません。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-478">The rest of the deployment process is automatic and doesn’t ask for any more user input.</span></span>

9.  <span data-ttu-id="2fc7e-479">展開タスク シーケンスでは、デバイスの構成が完了すると、Skype ルーム システム v2 のアプリケーション設定を構成するように指示する次の構成] 画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-479">After the deployment task sequence finishes configuring the device, you’ll see the following configuration screen that asks you to configure the Skype Room Systems v2 application settings.</span></span>

    ![Skype ルーム システム v2 のアプリケーションのセットアップの初期画面](../../media/room-systems-scale-image2.png)

10.  <span data-ttu-id="2fc7e-481">Surface Pro、Skype ルーム システム v2 のコンソールに接続し、アプリケーションの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-481">Plug the Surface Pro into the Skype Room Systems v2 console, and configure the application settings.</span></span>

11.  <span data-ttu-id="2fc7e-482">[Skype ルーム システム v2 のヘルプ](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)に記載されている機能が展開済みのデバイスで動作しているかを検証します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-482">Validate that the capabilities listed in [Skype Room Systems v2 help](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) are working on the deployed device.</span></span>


<span data-ttu-id="2fc7e-483">インストールの失敗をトラブルシューティングするには、 **SMSTS.log**ファイルは、構成マネージャーのタスク シーケンスで実行されるすべての手順をログに記録を確認してください。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-483">To troubleshoot a failed installation, check the **SMSTS.log** file, which logs all the steps executed in a Configuration Manager task sequence.</span></span>

<span data-ttu-id="2fc7e-484">SMSTS.log ファイルは、複数のビルド プロセスの段階に応じて、パスのいずれかに格納されます。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-484">The SMSTS.log file is stored on one of a number of paths, depending on the stage of the build process.</span></span> <span data-ttu-id="2fc7e-485">SMSTS.log ファイルへのパスを識別するのには次の表を確認してください。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-485">Check the following table to identify the path to the SMSTS.log file.</span></span>


| <span data-ttu-id="2fc7e-486">**展開フェーズ**</span><span class="sxs-lookup"><span data-stu-id="2fc7e-486">**Deployment phase**</span></span>                                                            | <span data-ttu-id="2fc7e-487">**タスク シーケンスのログのパス**</span><span class="sxs-lookup"><span data-stu-id="2fc7e-487">**Task sequence log path**</span></span>                         |
|---------------------------------------------------------------------------------|----------------------------------------------------|
| <span data-ttu-id="2fc7e-488">WinPE の HDD をフォーマットする前に、</span><span class="sxs-lookup"><span data-stu-id="2fc7e-488">WinPE, before HDD format</span></span>                                                        | <span data-ttu-id="2fc7e-489">X:\\Windows\\Temp\\smstslog\\smsts.log</span><span class="sxs-lookup"><span data-stu-id="2fc7e-489">X:\\Windows\\Temp\\smstslog\\smsts.log</span></span>             |
| <span data-ttu-id="2fc7e-490">WinPE の HDD のフォーマット後、</span><span class="sxs-lookup"><span data-stu-id="2fc7e-490">WinPE, after HDD format</span></span>                                                         | <span data-ttu-id="2fc7e-491">C:\\_SMSTaskSequence\\ログ\\Smstslog\\smsts.log</span><span class="sxs-lookup"><span data-stu-id="2fc7e-491">C:\\_SMSTaskSequence\\Logs\\Smstslog\\smsts.log</span></span>    |
| <span data-ttu-id="2fc7e-492">オペレーティング システムの展開、構成マネージャー エージェントをインストールする前に、</span><span class="sxs-lookup"><span data-stu-id="2fc7e-492">Operating system deployed, before the Configuration Manager agent was installed</span></span> | <span data-ttu-id="2fc7e-493">c:\\_SMSTaskSequence\\ログ\\Smstslog\\smsts.log</span><span class="sxs-lookup"><span data-stu-id="2fc7e-493">c:\\_SMSTaskSequence\\Logs\\Smstslog\\smsts.log</span></span>    |
| <span data-ttu-id="2fc7e-494">オペレーティング システムと構成マネージャー エージェントを展開</span><span class="sxs-lookup"><span data-stu-id="2fc7e-494">Operating system and the Configuration Manager agent deployed</span></span>                   | <span data-ttu-id="2fc7e-495">%windir%\\System32\\ccm\\ログ\\Smstslog\\smsts.log</span><span class="sxs-lookup"><span data-stu-id="2fc7e-495">%windir%\\System32\\ccm\\logs\\Smstslog\\smsts.log</span></span> |
| <span data-ttu-id="2fc7e-496">タスク シーケンスの実行が完了しました</span><span class="sxs-lookup"><span data-stu-id="2fc7e-496">Task sequence execution complete</span></span>                                                | <span data-ttu-id="2fc7e-497">%windir%\\System32\\ccm\\ログ\\smsts.log</span><span class="sxs-lookup"><span data-stu-id="2fc7e-497">%windir%\\System32\\ccm\\logs\\smsts.log</span></span>           |

> [!TIP]
> <span data-ttu-id="2fc7e-498">開くにはコマンド コンソールでは、タスク シーケンス中に**f8 キー**を選択し、SMSTS.log ファイルへのアクセスを取得できます。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-498">You can select **F8** at any time during the task sequence to open a command console, and then get access to the SMSTS.log file.</span></span>

<span data-ttu-id="2fc7e-499">PXE ブートの問題をトラブルシューティングするには、PXE のアクションに固有の構成マネージャー サーバー上のログの 2 つファイルを確認します。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-499">To troubleshoot PXE boot issues, check the two log files on the Configuration Manager server that are specific to PXE actions:</span></span>

-   <span data-ttu-id="2fc7e-500">**Pxecontrol.log**、構成マネージャーのインストール ・ ログ ・ ディレクトリ内にあります。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-500">**Pxecontrol.log**, located in the Configuration Manager installation logs directory</span></span>

-   <span data-ttu-id="2fc7e-501">**Smspxe.log**、構成マネージャー管理ポイント (MP) のログ ディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-501">**Smspxe.log**, located in Configuration Manager Management Point (MP) logs directory</span></span>

<span data-ttu-id="2fc7e-502">さらに、構成マネージャーのインストールのトラブルシューティングに使用できるログ ファイルの完全なリストは、[システム センター構成マネージャーのログ ファイル](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/log-files)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2fc7e-502">For a complete list of the log files that you can use to further troubleshoot your Configuration Manager installation, see [Log files in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/log-files).</span></span>
