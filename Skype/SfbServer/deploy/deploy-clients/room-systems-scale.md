---
title: システム センター構成マネージャーを使用して Microsoft チームの会議室を配置します。
author: jambirk
ms.author: jambirk
ms.reviewer: Turgayo
manager: serdars
ms.date: 5/10/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
ms.collection: M365-voice
description: 大規模な展開でマイクロソフト チームの会議室を展開する方法については、このトピックを参照してください。
ms.openlocfilehash: fe6ffee0c6ab86496204ab4e17b86cc84a70a2a7
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214916"
---
# <a name="deploy-microsoft-teams-rooms-by-using-system-center-configuration-manager"></a><span data-ttu-id="45671-103">システム センター構成マネージャーを使用して Microsoft チームの会議室を配置します。</span><span class="sxs-lookup"><span data-stu-id="45671-103">Deploy Microsoft Teams Rooms by using System Center Configuration Manager</span></span>

<span data-ttu-id="45671-104">この記事では、システム センター構成マネージャーを使用して、マイクロソフト チームの会議室の環境を作成するために必要なすべての情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="45671-104">This article gives you all the necessary information to create your Microsoft Teams Rooms deployments by using System Center Configuration Manager.</span></span>

<span data-ttu-id="45671-105">システム センター構成マネージャーで提供される使用する方法、オペレーティング システムと複数のターゲット ・ デバイスには、他のアプリケーションを導入できます。</span><span class="sxs-lookup"><span data-stu-id="45671-105">With the easy-to-use methods provided by System Center Configuration Manager, you can deploy the operating system and other applications to multiple target devices.</span></span>

<span data-ttu-id="45671-106">指示に従って、構成マネージャーの構成を以下に示す方法を使用し、サンプル パッケージと、組織の必要に応じて、このガイドで提供されているスクリプトをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="45671-106">Use the approach illustrated below to guide you through your Configuration Manager configuration, and customize the sample packages and scripts provided throughout this guidance as needed for your organization.</span></span>

![構成マネージャーを使用して Microsoft チームの会議室の展開プロセス](../../media/room-systems-scale-image1.png)

> [!IMPORTANT]
> <span data-ttu-id="45671-108">このソリューションは、Surface Pro ベースの環境でのみテストされています。</span><span class="sxs-lookup"><span data-stu-id="45671-108">This solution has only been tested with Surface Pro–based deployments.</span></span> <span data-ttu-id="45671-109">Surface Pro に基づかない場合、製造元のガイドラインに従います。</span><span class="sxs-lookup"><span data-stu-id="45671-109">Follow the manufacturer’s guidelines for configurations that aren’t based on Surface Pro.</span></span>

## <a name="validate-prerequisites"></a><span data-ttu-id="45671-110">前提条件を検証します。</span><span class="sxs-lookup"><span data-stu-id="45671-110">Validate prerequisites</span></span>

<span data-ttu-id="45671-111">マイクロソフト チームの会議室の構成マネージャーを使用してを展開するには、次の前提条件と要件を満たすことを確認します。</span><span class="sxs-lookup"><span data-stu-id="45671-111">To deploy Microsoft Teams Rooms with Configuration Manager, ensure that you meet the following prerequisites and requirements.</span></span>

### <a name="system-center-configuration-manager-requirements"></a><span data-ttu-id="45671-112">システム センター構成マネージャーの要件</span><span class="sxs-lookup"><span data-stu-id="45671-112">System Center Configuration Manager requirements</span></span>

-   <span data-ttu-id="45671-113">システム センター構成マネージャーのバージョンは、少なくとも 1706 をする必要がありますまたはそれ以上です。</span><span class="sxs-lookup"><span data-stu-id="45671-113">System Center Configuration Manager version must be at least 1706 or above.</span></span> <span data-ttu-id="45671-114">1710 またはそれ以降を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="45671-114">We recommend using 1710 or later.</span></span> <span data-ttu-id="45671-115">[サポートの Windows 10 ですシステム センター構成マネージャーで](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client)の構成マネージャーをサポートしている 10 の Windows のバージョンに関する詳細をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="45671-115">Check out [Support for Windows 10 in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) to learn about the Windows 10 versions that Configuration Manager supports.</span></span>

-   <span data-ttu-id="45671-116">Windows の評価と 10 の Windows の展開キット (ADK) のサポートされているバージョンをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="45671-116">A supported version of Windows Assessment and Deployment Kit (ADK) for Windows 10 must be installed.</span></span> <span data-ttu-id="45671-117">さまざまなバージョンの構成マネージャーを使用して、展開に適切なバージョンが含まれていることを確認する[10 ADK の Windows](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-adk)のバージョンを参照してください。</span><span class="sxs-lookup"><span data-stu-id="45671-117">See the versions of the [Windows 10 ADK](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-adk) that you can use with different versions of Configuration Manager, and ensure that your deployment includes the correct version.</span></span>

-   <span data-ttu-id="45671-118">サイト システム サーバーする必要があります割り当てられている配布ポイントの役割とのネットワークによる展開を有効にするのには、[プレブート実行環境 (PXE) のサポート](https://docs.microsoft.com/sccm/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network)を有効にするブート イメージです。</span><span class="sxs-lookup"><span data-stu-id="45671-118">The site system servers must have been assigned the distribution point role, and the boot images should be enabled for [preboot execution environment (PXE) support](https://docs.microsoft.com/sccm/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) to enable network-initiated deployments.</span></span> <span data-ttu-id="45671-119">Pxe ブートのサポートが有効でない場合は、展開では、[ブータブル メディア](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network)を使用できます。</span><span class="sxs-lookup"><span data-stu-id="45671-119">If PXE support isn’t enabled, you can use [bootable media](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) for your deployments.</span></span>

-   <span data-ttu-id="45671-120">コンピューター (ベア メタル) の新しい展開シナリオをサポートするためには、ネットワーク アクセス アカウントを構成しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="45671-120">A network access account must be configured to support new computer (bare metal) deployment scenarios.</span></span> <span data-ttu-id="45671-121">ネットワーク アクセス アカウントの構成に関する詳細については、[システム センター構成マネージャーでのコンテンツにアクセスするアカウントの管理](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45671-121">To learn more about the configuration of a network access account, see [Manage accounts to access content in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span></span>

-   <span data-ttu-id="45671-122">複数のユニットを同時に同じマイクロソフト チームの会議室のイメージを展開する場合、[マルチキャスト サポート](https://docs.microsoft.com/sccm/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network)を有効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="45671-122">We recommend that you enable [multicast support](https://docs.microsoft.com/sccm/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network), if you’re likely to deploy the same Microsoft Teams Rooms image to multiple units at the same time.</span></span>

### <a name="networking-requirements"></a><span data-ttu-id="45671-123">ネットワーク要件</span><span class="sxs-lookup"><span data-stu-id="45671-123">Networking requirements</span></span>

-   <span data-ttu-id="45671-124">ネットワークには、動的ホスト構成プロトコル (DHCP) サーバーは、マイクロソフト チームの会議室のユニットを配置する場所のサブネットに IP アドレスの配分を自動で構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="45671-124">Your network should have a Dynamic Host Configuration Protocol (DHCP) server, configured for automatic IP address distribution to the subnets where Microsoft Teams Rooms units will be deployed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="45671-125">DHCP のリース期間は、イメージの展開期間よりも長い値に設定しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="45671-125">DHCP lease duration must be set to a value longer than the image deployment duration.</span></span> <span data-ttu-id="45671-126">それ以外の場合、展開が失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="45671-126">Otherwise, the deployment might fail.</span></span>

-   <span data-ttu-id="45671-127">PXE をサポートするためにスイッチ、仮想 Lan (Vlan) など、ネットワークを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="45671-127">Your network, including switches and virtual LANs (VLANs), should be configured to support PXE.</span></span> <span data-ttu-id="45671-128">IP ヘルパーと PXE の構成の詳細については、ネットワークの製造元を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45671-128">Refer to your network vendor for more information about IP Helper and PXE configuration.</span></span> <span data-ttu-id="45671-129">または、pxe ブートのサポートが有効になっていない場合は、展開の場合、[起動可能なメディア](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network)を使用できます。</span><span class="sxs-lookup"><span data-stu-id="45671-129">Alternatively, you can use [bootable media](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) for your deployments, if PXE support isn’t enabled.</span></span>

    > [!NOTE]
    > <span data-ttu-id="45671-130">Surface Pro のイーサネット アダプターまたはマイクロソフトからのドッキング ステーションを使用する場合のみ、デバイス、ネットワーク (PXE ブート) からの起動がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="45671-130">For Surface Pro devices, booting from the network (PXE boot) is only supported when you use an Ethernet adapter or docking station from Microsoft.</span></span> <span data-ttu-id="45671-131">Surface Pro で PXE ブートをサポートしていないサードパーティ製のイーサネット アダプターです。</span><span class="sxs-lookup"><span data-stu-id="45671-131">Third-party Ethernet adapters don’t support PXE boot with Surface Pro.</span></span> <span data-ttu-id="45671-132">詳細については、[イーサネット アダプターとサーフェスの配置](https://docs.microsoft.com/surface/ethernet-adapters-and-surface-device-deployment)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45671-132">See [Ethernet adapters and Surface deployment](https://docs.microsoft.com/surface/ethernet-adapters-and-surface-device-deployment) for more information.</span></span>

## <a name="configure-system-center-configuration-manager-for-operating-system-deployment"></a><span data-ttu-id="45671-133">システム センター構成マネージャーをオペレーティング システムの展開の構成します。</span><span class="sxs-lookup"><span data-stu-id="45671-133">Configure System Center Configuration Manager for operating system deployment</span></span>

<span data-ttu-id="45671-134">この資料では、既に正常なシステム センター構成マネージャーの展開があり、詳細を展開し、最初から構成マネージャーを構成するために必要なすべての手順を実行しないと仮定します。</span><span class="sxs-lookup"><span data-stu-id="45671-134">This article assumes you already have a healthy System Center Configuration Manager deployment, and doesn’t detail all the steps required to deploy and configure Configuration Manager from scratch.</span></span> <span data-ttu-id="45671-135">[ドキュメントおよび構成ガイド](https://docs.microsoft.com/sccm/)、システム センター構成マネージャーでは、優れたリソースです。構成マネージャーをまだ展開していない場合、これらのリソースを開始することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="45671-135">The [documentation and the configuration guidance](https://docs.microsoft.com/sccm/) on the System Center Configuration Manager is a great resource; we recommend you start with these resources if you haven’t yet deployed Configuration Manager.</span></span>

<span data-ttu-id="45671-136">オペレーティング システムの展開 (OSD) 機能が正しく構成されていることを確認するのにには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="45671-136">Use the following instructions to verify that the operating system deployment (OSD) features are configured properly.</span></span>

### <a name="validate-and-upgrade-configuration-manager"></a><span data-ttu-id="45671-137">検証し、構成マネージャーのアップグレード</span><span class="sxs-lookup"><span data-stu-id="45671-137">Validate and upgrade Configuration Manager</span></span>

1.  <span data-ttu-id="45671-138">構成マネージャー コンソールで、**管理**ページに移動\>**の更新プログラムおよびサービス**です。</span><span class="sxs-lookup"><span data-stu-id="45671-138">In the Configuration Manager console, go to **Administration** \> **Updates and Servicing**.</span></span>

2.  <span data-ttu-id="45671-139">まだインストールされていない適用可能な更新プログラム、インストールされているビルドを確認します。</span><span class="sxs-lookup"><span data-stu-id="45671-139">Check the installed build and applicable updates that haven’t been installed yet.</span></span>

3.  <span data-ttu-id="45671-140">[10 System Center 構成マネージャーでの Windows のサポート](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client)を確認します。配置をアップグレードする場合をインストールする更新プログラムを選択し、**ダウンロード**します。</span><span class="sxs-lookup"><span data-stu-id="45671-140">Review [Support for Windows 10 in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client); if you need to upgrade your deployment, select the update you want to install, and then select **Download**.</span></span>

4.  <span data-ttu-id="45671-141">ダウンロードが完了した後、更新プログラムを選択し、**更新パックをインストール**します。</span><span class="sxs-lookup"><span data-stu-id="45671-141">After the download is complete, select the update, and then select **Install Update Pack**.</span></span>

### <a name="configure-distribution-points-to-support-pxe-and-multicast"></a><span data-ttu-id="45671-142">PXE、マルチキャストをサポートするために配布ポイントを構成します。</span><span class="sxs-lookup"><span data-stu-id="45671-142">Configure distribution points to support PXE and multicast</span></span>

1.  <span data-ttu-id="45671-143">構成マネージャー コンソールで、**管理**ページに移動\>**の配布ポイント**です。</span><span class="sxs-lookup"><span data-stu-id="45671-143">In the Configuration Manager console, go to **Administration** \> **Distribution Points**.</span></span>

2.  <span data-ttu-id="45671-144">マイクロソフト チームの会議室の配置、サービスを提供し、**プロパティ**を選択し、配布ポイント サーバーを選択します。</span><span class="sxs-lookup"><span data-stu-id="45671-144">Select the distribution point server that will serve the Microsoft Teams Rooms deployment, and then select **Properties**.</span></span>

3.  <span data-ttu-id="45671-145">**PXE** ] タブを選択し、次の設定が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="45671-145">Select the **PXE** tab, and ensure that the following settings are enabled:</span></span>
    -   <span data-ttu-id="45671-146">クライアントの pxe ブートのサポートを有効にします。</span><span class="sxs-lookup"><span data-stu-id="45671-146">Enable PXE support for clients</span></span>
    -   <span data-ttu-id="45671-147">受信 PXE 要求に応答するには、この配布ポイントを許可します。</span><span class="sxs-lookup"><span data-stu-id="45671-147">Allow this distribution point to respond to incoming PXE requests</span></span>
    -   <span data-ttu-id="45671-148">不明なコンピューターのサポートを有効にします。</span><span class="sxs-lookup"><span data-stu-id="45671-148">Enable unknown computer support</span></span>

4.  <span data-ttu-id="45671-149">*オプション:* マルチキャスト サポートを有効にするには、[**マルチキャスト**] タブを選択し、[次の設定が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="45671-149">*Optional:* To enable multicast support, select the **Multicast** tab, and ensure that the following settings are enabled:</span></span>
    -   <span data-ttu-id="45671-150">同時に複数のクライアントにデータを送信するマルチキャストを有効にします。</span><span class="sxs-lookup"><span data-stu-id="45671-150">Enable multicast to simultaneously send data to multiple clients</span></span>
    -   <span data-ttu-id="45671-151">ネットワーク チームの勧告に UDP ポートの範囲を構成します。</span><span class="sxs-lookup"><span data-stu-id="45671-151">Configure the UDP port range as per your network team’s recommendation</span></span>

### <a name="configure-the-network-access-account"></a><span data-ttu-id="45671-152">ネットワーク アクセス アカウントを構成します。</span><span class="sxs-lookup"><span data-stu-id="45671-152">Configure the Network Access Account</span></span>

1.  <span data-ttu-id="45671-153">構成マネージャー コンソールで、**管理**ページに移動\>**サイトの構成** \> **サイト**、およびサイトを選択します。</span><span class="sxs-lookup"><span data-stu-id="45671-153">In the Configuration Manager console, go to **Administration** \> **Site Configuration** \> **Sites**, and then select the site.</span></span>

2.  <span data-ttu-id="45671-154">[**設定**] で、**サイトのコンポーネントの構成**を選択します\>**ソフトウェアの配布**。</span><span class="sxs-lookup"><span data-stu-id="45671-154">In the **Settings** group, select **Configure Site Components** \> **Software Distribution**.</span></span>

3.  <span data-ttu-id="45671-155">[**ネットワーク アクセス アカウント**] タブを 1 つまたは複数のアカウント] をクリックし **[ok]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="45671-155">Select the **Network Access Account** tab. Set up one or more accounts, and then select **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="45671-156">アカウントには、配布ポイント サーバー上の**ネットワークからこのコンピューターへアクセス**を除く、任意の特別な権限が必要がありません。</span><span class="sxs-lookup"><span data-stu-id="45671-156">The accounts don’t need any special rights, except for the **Access this computer from the network** right on the distribution point server.</span></span> <span data-ttu-id="45671-157">汎用的なドメイン ユーザー アカウントに適切ななります。</span><span class="sxs-lookup"><span data-stu-id="45671-157">A generic domain user account will be appropriate.</span></span> <span data-ttu-id="45671-158">詳細については、[システム センター構成マネージャーでのコンテンツにアクセスするアカウントの管理](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45671-158">For more information, see [Manage accounts to access content in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span></span>

### <a name="configure-a-boot-image"></a><span data-ttu-id="45671-159">ブート イメージを構成します。</span><span class="sxs-lookup"><span data-stu-id="45671-159">Configure a boot image</span></span>

1.  <span data-ttu-id="45671-160">**ソフトウェア ライブラリ**には、構成マネージャー コンソールで、 \> **のオペレーティング システム** \> **のブート イメージ**です。</span><span class="sxs-lookup"><span data-stu-id="45671-160">In the Configuration Manager console, go to **Software Library** \> **Operating System** \> **Boot Images**.</span></span>

2.  <span data-ttu-id="45671-161">**ブート イメージ (x64)** を選択し、[**プロパティ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="45671-161">Select **Boot image (x64)**, and then select **Properties**.</span></span>

3.  <span data-ttu-id="45671-162">**データ ソース**] タブを選択し、 **PXE が有効な配布ポイントからは、このブート イメージの展開**を有効にします。</span><span class="sxs-lookup"><span data-stu-id="45671-162">Select the **Data Source** tab, and enable **Deploy this boot image from the PXE-enabled distribution point**.</span></span>

4.  <span data-ttu-id="45671-163">必要なコンポーネントをインストールするのには [**オプション コンポーネント**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="45671-163">Select the **Optional Components** tab to install required components:</span></span>

    1.  <span data-ttu-id="45671-164">スターのアイコンを選択し、 **HTML (WinPE HTA)** を検索</span><span class="sxs-lookup"><span data-stu-id="45671-164">Select the star icon, and search for **HTML (WinPE-HTA)**</span></span>

    2.  <span data-ttu-id="45671-165">ブート イメージへの HTML アプリケーションのサポートを追加するのには **[ok]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="45671-165">Select **OK** to add HTML application support in to the boot image.</span></span>

5.  <span data-ttu-id="45671-166">*オプション:* 展開のエクスペリエンスをカスタマイズするには、[**カスタマイズ**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="45671-166">*Optional:* To customize the deployment experience, select the **Customization** tab.</span></span>
    -   <span data-ttu-id="45671-167">展開時に、コマンド プロンプトへのアクセスが必要な場合 **(テストのみ)] コマンドのサポート**を有効にします。</span><span class="sxs-lookup"><span data-stu-id="45671-167">Enable **command support (testing only)** if you want to have access to a command prompt during the deployment.</span></span> <span data-ttu-id="45671-168">これを有効にすると、展開中に**f8 キー**を選択してコマンド プロンプトを起動できます。</span><span class="sxs-lookup"><span data-stu-id="45671-168">When this is enabled, you can start a command prompt by selecting **F8** at any time during the deployment.</span></span>
    -   <span data-ttu-id="45671-169">展開時に表示するカスタムの背景イメージを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="45671-169">You can also specify a custom background image to be displayed during the deployment.</span></span> <span data-ttu-id="45671-170">イメージを設定するを有効にする**カスタムの背景イメージのファイルを指定 (UNC パス**の背景を選択します。</span><span class="sxs-lookup"><span data-stu-id="45671-170">To set an image, enable **Specify the custom background image file (UNC path** and select your background.</span></span>

6.  <span data-ttu-id="45671-171">ダイアログ ボックスが表示されたら、 **[はい]** を選択し、配布ポイントに更新されたブート イメージを配布します。</span><span class="sxs-lookup"><span data-stu-id="45671-171">When asked, select **Yes** and distribute the updated boot image to your distribution points.</span></span>

<span data-ttu-id="45671-172">詳細については、[ブート イメージの管理システム センター構成マネージャーの使用](https://docs.microsoft.com/sccm/osd/get-started/manage-boot-images)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45671-172">For more information, see [Manage boot images with System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-boot-images).</span></span>

> [!NOTE]
> <span data-ttu-id="45671-173">Pxe ブートのサポートがない環境の構成マネージャー タスク シーケンスに基づく展開を開始する起動可能な USB メディアを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="45671-173">You can create a bootable USB media to initiate Configuration Manager task sequence–based deployments for environments that have no PXE support.</span></span> <span data-ttu-id="45671-174">のみブート イメージ、prestart コマンドのオプションと、必要なファイル、および構成マネージャーのバイナリ Windows PE を起動し、展開プロセスの残りの部分の構成マネージャーへの接続をサポートするために、ブート可能なメディアが含まれます。</span><span class="sxs-lookup"><span data-stu-id="45671-174">The bootable media contains only the boot image, optional prestart commands and their required files, and Configuration Manager binaries to support booting into Windows PE and connecting to Configuration Manager for the rest of the deployment process.</span></span> <span data-ttu-id="45671-175">詳細については、[ブータブル メディアを作成する方法](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45671-175">For more information, see [How to Create Bootable Media](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia).</span></span>

## <a name="create-configuration-manager-packages"></a><span data-ttu-id="45671-176">構成マネージャー パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="45671-176">Create Configuration Manager packages</span></span>

<span data-ttu-id="45671-177">構成マネージャーでは、いくつかのパッケージを展開し、マイクロソフト チームの会議室の単位を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="45671-177">Configuration Manager requires a number of packages to deploy and configure the Microsoft Teams Rooms units.</span></span>

<span data-ttu-id="45671-178">作成し、次のパッケージを構成する必要があり、配布ポイント サーバーの役割が割り当てられている構成マネージャー サイト システムに配布します。</span><span class="sxs-lookup"><span data-stu-id="45671-178">You need to create and configure the following packages, and then distribute them to the Configuration Manager site systems that have been assigned the distribution point server role.</span></span>

| <span data-ttu-id="45671-179">**パッケージ名**</span><span class="sxs-lookup"><span data-stu-id="45671-179">**Package name**</span></span>                     | <span data-ttu-id="45671-180">**型**</span><span class="sxs-lookup"><span data-stu-id="45671-180">**Type**</span></span>               | <span data-ttu-id="45671-181">**説明**</span><span class="sxs-lookup"><span data-stu-id="45671-181">**Description**</span></span>                                                                           |
|--------------------------------------|------------------------|-------------------------------------------------------------------------------------------|
| <span data-ttu-id="45671-182">SRS v2 の SRS のアプリケーション パッケージ</span><span class="sxs-lookup"><span data-stu-id="45671-182">SRS v2 - SRS Application Package</span></span>     | <span data-ttu-id="45671-183">ソフトウェア パッケージ</span><span class="sxs-lookup"><span data-stu-id="45671-183">Software package</span></span>       | <span data-ttu-id="45671-184">マイクロソフト チーム ルーム展開キットのパッケージ</span><span class="sxs-lookup"><span data-stu-id="45671-184">Package for the Microsoft Teams Rooms deployment kit</span></span>                                      |
| <span data-ttu-id="45671-185">SRS v2 の Sysprep パッケージ</span><span class="sxs-lookup"><span data-stu-id="45671-185">SRS v2 - Sysprep Package</span></span>             | <span data-ttu-id="45671-186">ソフトウェア パッケージ</span><span class="sxs-lookup"><span data-stu-id="45671-186">Software package</span></span>       | <span data-ttu-id="45671-187">マイクロソフト チームの会議室の単位を構成するのにはカスタムの Unattended.xml 用のパッケージ</span><span class="sxs-lookup"><span data-stu-id="45671-187">Package for the custom Unattended.xml to configure Microsoft Teams Rooms units</span></span>            |
| <span data-ttu-id="45671-188">SRS v2 - セット-SRSComputerName パッケージ</span><span class="sxs-lookup"><span data-stu-id="45671-188">SRS v2 - Set-SRSComputerName Package</span></span> | <span data-ttu-id="45671-189">ソフトウェア パッケージ</span><span class="sxs-lookup"><span data-stu-id="45671-189">Software package</span></span>       | <span data-ttu-id="45671-190">パッケージの展開時にコンピューター名を割り当てるには、HTML アプリケーション (HTA)</span><span class="sxs-lookup"><span data-stu-id="45671-190">Package for the HTML application (HTA) to assign a computer name during the deployment</span></span>    |
| <span data-ttu-id="45671-191">SRS v2 の SRS の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="45671-191">SRS v2 - Configure SRS Setup</span></span>         | <span data-ttu-id="45671-192">ソフトウェア パッケージ</span><span class="sxs-lookup"><span data-stu-id="45671-192">Software package</span></span>       | <span data-ttu-id="45671-193">マイクロソフト チーム ルーム アプリケーションの展開を構成するパッケージ</span><span class="sxs-lookup"><span data-stu-id="45671-193">Package to configure deployment of the Microsoft Teams Rooms app</span></span>                          |
| <span data-ttu-id="45671-194">SRS v2 - OS の更新パッケージ</span><span class="sxs-lookup"><span data-stu-id="45671-194">SRS v2 - OS Updates Package</span></span>          | <span data-ttu-id="45671-195">ソフトウェア パッケージ</span><span class="sxs-lookup"><span data-stu-id="45671-195">Software package</span></span>       | <span data-ttu-id="45671-196">オペレーティング システムの必須更新プログラムを展開するパッケージ</span><span class="sxs-lookup"><span data-stu-id="45671-196">Package to deploy mandatory operating system updates</span></span>                                      |
| <span data-ttu-id="45671-197">SRS v2 のルート証明書のパッケージ</span><span class="sxs-lookup"><span data-stu-id="45671-197">SRS v2 - Root Certificate Package</span></span>    | <span data-ttu-id="45671-198">ソフトウェア パッケージ</span><span class="sxs-lookup"><span data-stu-id="45671-198">Software package</span></span>       | <span data-ttu-id="45671-199">オプション - (ドメインに参加しているユニットは必要ありません) ルート証明書を展開するためのパッケージ</span><span class="sxs-lookup"><span data-stu-id="45671-199">Optional - Package to deploy the root certificate (not required for domain-joined units)</span></span>  |
| <span data-ttu-id="45671-200">SRS v2 - エージェント パッケージを監視する Microsoft</span><span class="sxs-lookup"><span data-stu-id="45671-200">SRS v2 - Microsoft Monitoring Agent Package</span></span> | <span data-ttu-id="45671-201">ソフトウェア パッケージ</span><span class="sxs-lookup"><span data-stu-id="45671-201">Software package</span></span>       | <span data-ttu-id="45671-202">オプション ・ パッケージを展開し、運用管理スイートの Microsoft エージェントを構成するには</span><span class="sxs-lookup"><span data-stu-id="45671-202">Optional - Package to deploy and configure the Microsoft Operations Management Suite agent</span></span>|
| <span data-ttu-id="45671-203">SRS v2 の WinPE の背景のパッケージ</span><span class="sxs-lookup"><span data-stu-id="45671-203">SRS v2 - WinPE Background Package</span></span>    | <span data-ttu-id="45671-204">ソフトウェア パッケージ</span><span class="sxs-lookup"><span data-stu-id="45671-204">Software package</span></span>       | <span data-ttu-id="45671-205">ブート イメージを使用するカスタムの背景イメージのパッケージ</span><span class="sxs-lookup"><span data-stu-id="45671-205">Package for the custom background image to use with boot images</span></span>                           |
| <span data-ttu-id="45671-206">10 の Windows エンタープライズ</span><span class="sxs-lookup"><span data-stu-id="45671-206">Windows 10 Enterprise</span></span>                | <span data-ttu-id="45671-207">オペレーティング システムのイメージ</span><span class="sxs-lookup"><span data-stu-id="45671-207">Operating system image</span></span> | <span data-ttu-id="45671-208">オペレーティング システム インストール ファイル (install.wim) 用のパッケージ</span><span class="sxs-lookup"><span data-stu-id="45671-208">Package for the operating system installation file (install.wim)</span></span>                          |
| <span data-ttu-id="45671-209">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="45671-209">Surface Pro</span></span>                          | <span data-ttu-id="45671-210">ドライバー パッケージ</span><span class="sxs-lookup"><span data-stu-id="45671-210">Driver package</span></span>         | <span data-ttu-id="45671-211">Microsoft Surface Pro のファームウェアとデバイス ドライバーのパッケージ</span><span class="sxs-lookup"><span data-stu-id="45671-211">Package for the device drivers and firmware for Microsoft Surface Pro</span></span>                     |
| <span data-ttu-id="45671-212">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="45671-212">Surface Pro 4</span></span>                        | <span data-ttu-id="45671-213">ドライバー パッケージ</span><span class="sxs-lookup"><span data-stu-id="45671-213">Driver package</span></span>         | <span data-ttu-id="45671-214">Microsoft Surface Pro 4 のファームウェアとデバイス ドライバーのパッケージ</span><span class="sxs-lookup"><span data-stu-id="45671-214">Package for the device drivers and firmware for Microsoft Surface Pro 4</span></span>                   |

<span data-ttu-id="45671-215">詳細については、[パッケージとプログラムで、システム センター構成マネージャー](https://docs.microsoft.com/sccm/apps/deploy-use/packages-and-programs)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45671-215">For more information, see [Packages and programs in System Center Configuration Manager](https://docs.microsoft.com/sccm/apps/deploy-use/packages-and-programs).</span></span>

### <a name="create-folders-for-the-package-source-files"></a><span data-ttu-id="45671-216">パッケージのフォルダーを作成するには、ソース ファイル</span><span class="sxs-lookup"><span data-stu-id="45671-216">Create folders for the package source files</span></span>

<span data-ttu-id="45671-217">構成マネージャーには、パッケージのソース ファイルを最初に作成しているとき、および更新されるときに特定のフォルダー構造で整理することが必要です。</span><span class="sxs-lookup"><span data-stu-id="45671-217">Configuration Manager requires package source files to be organized in a specific folder structure when they’re first created and when they’re updated.</span></span>

<span data-ttu-id="45671-218">システム センター構成マネージャー サーバーの全体管理サイトまたはプライマリ サイト、またはを使用してパッケージのソース ファイルをホストするサーバー共有には、次のフォルダー構造を作成します。</span><span class="sxs-lookup"><span data-stu-id="45671-218">Create the following folder structure on the System Center Configuration Manager central administration site or primary site, or on a server share you’re using to host package source files:</span></span>

-   <span data-ttu-id="45671-219">SRS v2 - エージェント パッケージを監視する Microsoft</span><span class="sxs-lookup"><span data-stu-id="45671-219">SRS v2 - Microsoft Monitoring Agent Package</span></span>
-   <span data-ttu-id="45671-220">SRS v2 - OS の更新パッケージ</span><span class="sxs-lookup"><span data-stu-id="45671-220">SRS v2 - OS Updates Package</span></span>
-   <span data-ttu-id="45671-221">SRS v2 のルート証明書のパッケージ</span><span class="sxs-lookup"><span data-stu-id="45671-221">SRS v2 - Root Certificate Package</span></span>
-   <span data-ttu-id="45671-222">SRS v2 - セット-SRSComputerName パッケージ</span><span class="sxs-lookup"><span data-stu-id="45671-222">SRS v2 - Set-SRSComputerName Package</span></span>
-   <span data-ttu-id="45671-223">SRS v2 の SRS のアプリケーション パッケージ</span><span class="sxs-lookup"><span data-stu-id="45671-223">SRS v2 - SRS Application Package</span></span>
-   <span data-ttu-id="45671-224">SRS v2 の SRS の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="45671-224">SRS v2 - Configure SRS Setup</span></span>
-   <span data-ttu-id="45671-225">SRS v2 の Sysprep パッケージ</span><span class="sxs-lookup"><span data-stu-id="45671-225">SRS v2 - Sysprep Package</span></span>
-   <span data-ttu-id="45671-226">ドライバー</span><span class="sxs-lookup"><span data-stu-id="45671-226">Drivers</span></span>
    -   <span data-ttu-id="45671-227">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="45671-227">Surface Pro</span></span>
    -   <span data-ttu-id="45671-228">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="45671-228">Surface Pro 4</span></span>
-   <span data-ttu-id="45671-229">オペレーティング ・ システム</span><span class="sxs-lookup"><span data-stu-id="45671-229">Operating Systems</span></span>
    -   <span data-ttu-id="45671-230">10 の Windows エンタープライズ</span><span class="sxs-lookup"><span data-stu-id="45671-230">Windows 10 Enterprise</span></span>

> [!TIP]
> <span data-ttu-id="45671-231">[ダウンロード](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)にも可能性があり、パッケージ スクリプトを使用する必要がありますが、インポートする必要があるタスク シーケンスのテンプレート用のフォルダー構造を含む zip ファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="45671-231">You may also [download](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) and use the zip file that includes the folder structure for the packages, the scripts that you need to use, and the task sequence template, that you need to import.</span></span>

### <a name="create-the-monitoring-agent-package"></a><span data-ttu-id="45671-232">監視エージェント パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="45671-232">Create the Monitoring agent package</span></span>

1. <span data-ttu-id="45671-233">監視エージェントをダウンロード<https://go.microsoft.com/fwlink/?LinkId=828603>。</span><span class="sxs-lookup"><span data-stu-id="45671-233">Download the Monitoring agent from <https://go.microsoft.com/fwlink/?LinkId=828603>.</span></span>

2. <span data-ttu-id="45671-234">コマンド プロンプト ウィンドウを開き、コマンド プロンプトで**MMASetup AMD64.exe の指定**を入力する**SRS v2 - マイクロソフトの監視エージェントのパッケージ**フォルダーにパッケージを抽出します。</span><span class="sxs-lookup"><span data-stu-id="45671-234">Extract the package into the **SRS v2 - Microsoft Monitoring Agent Package** folder by opening a Command Prompt window and entering **MMASetup-AMD64.exe /C:**     at the command prompt.</span></span>

3. <span data-ttu-id="45671-235">**ソフトウェア ライブラリ**には、構成マネージャー コンソールで、 \> **アプリケーション管理** \> **パッケージ**、および**パッケージの作成**を選択します。</span><span class="sxs-lookup"><span data-stu-id="45671-235">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4. <span data-ttu-id="45671-236">パッケージを作成するのには次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="45671-236">Enter the following information to create the package:</span></span>

   - <span data-ttu-id="45671-237">名前<strong>: SRS v2 - エージェント パッケージを監視する Microsoft</strong></span><span class="sxs-lookup"><span data-stu-id="45671-237">Name<strong>: SRS v2 - Microsoft Monitoring Agent Package</strong></span></span>

   - <span data-ttu-id="45671-238">製造元<strong>: Microsoft Corporation</strong></span><span class="sxs-lookup"><span data-stu-id="45671-238">Manufacturer<strong>: Microsoft Corporation</strong></span></span>

   - <span data-ttu-id="45671-239">バージョン<strong>: 8.1.11081.0</strong> (ダウンロードしたインストール ファイルのバージョンを入力してください)</span><span class="sxs-lookup"><span data-stu-id="45671-239">Version<strong>: 8.1.11081.0</strong> (enter the version of the downloaded installation file)</span></span>

   - <span data-ttu-id="45671-240">**このパッケージにソース ファイルが含まれています**] チェック ボックスをオンに、 **SRS の v2 - マイクロソフトの監視エージェントのパッケージ**のフォルダーにパスを入力し、**次へ**。</span><span class="sxs-lookup"><span data-stu-id="45671-240">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Microsoft Monitoring Agent Package** folder, and then select **Next**.</span></span>

5. <span data-ttu-id="45671-241">**プログラムを作成しない**を選択し、**次へ**します。</span><span class="sxs-lookup"><span data-stu-id="45671-241">Select **Do not create a program**, and then select **Next**.</span></span>

6. <span data-ttu-id="45671-242">**設定の確認**] ページを確認し、**次へ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="45671-242">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7. <span data-ttu-id="45671-243">**閉じる**を選択します。</span><span class="sxs-lookup"><span data-stu-id="45671-243">Select **Close**.</span></span>

### <a name="create-the-operating-system-updates-package"></a><span data-ttu-id="45671-244">オペレーティング システム更新プログラム パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="45671-244">Create the operating system updates package</span></span>

1. <span data-ttu-id="45671-245">**SRS v2 - OS の更新プログラム パッケージ**のフォルダーに**インストール-SRSv2-OS の Updates.ps1**をという名前の新しい PowerShell スクリプトを作成します。</span><span class="sxs-lookup"><span data-stu-id="45671-245">In the **SRS v2 - OS Updates Package** folder, create a new PowerShell script named **Install-SRSv2-OS-Updates.ps1**.</span></span>

2. <span data-ttu-id="45671-246">**インストール-SRSv2-OS の Updates.ps1**スクリプトに以下のスクリプトをコピーします。</span><span class="sxs-lookup"><span data-stu-id="45671-246">Copy the script below into the **Install-SRSv2-OS-Updates.ps1** script.</span></span> <span data-ttu-id="45671-247">または、[ここ](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)からインストール-SRSv2-OS の Updates.ps1 スクリプトをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="45671-247">Alternatively, you can download the Install-SRSv2-OS-Updates.ps1 script from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
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
3. <span data-ttu-id="45671-248">必須の Windows 更新プログラム パッケージを同じフォルダーにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="45671-248">Download the mandatory Windows Update packages into the same folder.</span></span>
   > [!NOTE]
   > <span data-ttu-id="45671-249">この資料が公開された時点で、 [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu)だけが必要でした。</span><span class="sxs-lookup"><span data-stu-id="45671-249">At the time this article was published, only [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) was required.</span></span> <span data-ttu-id="45671-250">[マイクロソフト チームの会議室のコンソールを構成する](console.md)、他の更新プログラムが必要なかどうかを確認してください。</span><span class="sxs-lookup"><span data-stu-id="45671-250">Check [Configure a Microsoft Teams Rooms console](console.md), to see whether any other updates are required.</span></span>

4. <span data-ttu-id="45671-251">**ソフトウェア ライブラリ**には、構成マネージャー コンソールで、 \> **アプリケーション管理** \> **パッケージ**、および**パッケージの作成**を選択します。</span><span class="sxs-lookup"><span data-stu-id="45671-251">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

5. <span data-ttu-id="45671-252">パッケージを作成するのには次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="45671-252">Enter the following information to create the package:</span></span>
   -   <span data-ttu-id="45671-253">名前: の**SRS v2 – OS パッケージを更新します。**</span><span class="sxs-lookup"><span data-stu-id="45671-253">Name: **SRS v2 – OS Updates Package**</span></span>
   -   <span data-ttu-id="45671-254">製造元: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="45671-254">Manufacturer: **Microsoft Corporation**</span></span>
   -   <span data-ttu-id="45671-255">バージョン: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="45671-255">Version: **1.0.0**</span></span>
   -   <span data-ttu-id="45671-256">**このパッケージにソース ファイルが含まれています**] チェック ボックスをオンに、 **SRS の v2 - OS の更新プログラム パッケージ**のフォルダーにパスを入力し、**次へ**。</span><span class="sxs-lookup"><span data-stu-id="45671-256">Select the **This package contains source files** check box, enter the path to the **SRS v2 - OS Updates Package** folder, and then select **Next**.</span></span>

6. <span data-ttu-id="45671-257">**プログラムを作成しない**を選択し、**次へ**します。</span><span class="sxs-lookup"><span data-stu-id="45671-257">Select **Do not create a program**, and then select **Next**.</span></span>

7. <span data-ttu-id="45671-258">**設定の確認**] ページを確認し、**次へ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="45671-258">Review the **Confirm the settings** page, and then select **Next**.</span></span>

8. <span data-ttu-id="45671-259">**閉じる**を選択します。</span><span class="sxs-lookup"><span data-stu-id="45671-259">Select **Close**.</span></span>

### <a name="create-the-root-certificate-package-optional"></a><span data-ttu-id="45671-260">ルート証明書のパッケージを作成する (省略可能)</span><span class="sxs-lookup"><span data-stu-id="45671-260">Create the root certificate package (optional)</span></span>

<span data-ttu-id="45671-261">Active Directory ドメインに参加しないデバイスのルート証明書を配布するには、このパッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="45671-261">You create this package to distribute the root certificate for devices that won’t be joined to an Active Directory domain.</span></span> <span data-ttu-id="45671-262">次の両方の条件を適用する場合にのみ、このパッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="45671-262">Create this package only if both the following conditions apply:</span></span>
-   <span data-ttu-id="45671-263">展開には、設置が含まれています Lync または Skype ビジネス サーバー用です。</span><span class="sxs-lookup"><span data-stu-id="45671-263">Your deployment includes on-premises Lync or Skype for Business Server.</span></span>
-   <span data-ttu-id="45671-264">マイクロソフト チームの会議室の単位は、ドメインのメンバーではなくワークグループで作業するのには構成されます。</span><span class="sxs-lookup"><span data-stu-id="45671-264">Microsoft Teams Rooms units are configured to work in a workgroup instead of a domain member.</span></span>

1.  <span data-ttu-id="45671-265">ルート証明書を**SRS v2: ルート証明書のパッケージ**フォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="45671-265">Copy the root certificate into the **SRS v2 – Root Certificate Package** folder.</span></span>

2.  <span data-ttu-id="45671-266">**ソフトウェア ライブラリ**には、構成マネージャー コンソールで、 \> **アプリケーション管理** \> **パッケージ**、および**パッケージの作成**を選択します。</span><span class="sxs-lookup"><span data-stu-id="45671-266">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

3.  <span data-ttu-id="45671-267">パッケージを作成するのには次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="45671-267">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="45671-268">**SRS v2: ルート証明書のパッケージ**の名前。</span><span class="sxs-lookup"><span data-stu-id="45671-268">Name: **SRS v2 – Root Certificate Package**</span></span>
    -   <span data-ttu-id="45671-269">製造元:*組織の名前*</span><span class="sxs-lookup"><span data-stu-id="45671-269">Manufacturer: *Your organization’s name*</span></span>
    -   <span data-ttu-id="45671-270">バージョン: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="45671-270">Version: **1.0.0**</span></span>
    -   <span data-ttu-id="45671-271">**このパッケージにソース ファイルが含まれています**] チェック ボックスをオンに、 **SRS のバージョン 2: ルート証明書のパッケージ**のフォルダーにパスを入力し、**次へ**。</span><span class="sxs-lookup"><span data-stu-id="45671-271">Select the **This package contains source files** check box, enter the path to the **SRS v2 – Root Certificate Package** folder, and then select **Next**.</span></span>

4.  <span data-ttu-id="45671-272">**プログラムを作成しない**を選択し、**次へ**します。</span><span class="sxs-lookup"><span data-stu-id="45671-272">Select **Do not create a program**, and then select **Next**.</span></span>

5.  <span data-ttu-id="45671-273">**設定の確認**] ページを確認し、**次へ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="45671-273">Review the **Confirm the settings** page, and then select **Next**.</span></span>

6.  <span data-ttu-id="45671-274">**閉じる**を選択します。</span><span class="sxs-lookup"><span data-stu-id="45671-274">Select **Close**.</span></span>

### <a name="create-the-microsoft-teams-rooms-deployment-kit-package"></a><span data-ttu-id="45671-275">マイクロソフト チーム ルーム展開キットのパッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="45671-275">Create the Microsoft Teams Rooms deployment kit package</span></span>

1.  <span data-ttu-id="45671-276">**マイクロソフト チームの会議室の導入ガイド 』** の最新バージョンをダウンロードして<https://go.microsoft.com/fwlink/?linkid=851168>、ワークステーションにインストールするとします。</span><span class="sxs-lookup"><span data-stu-id="45671-276">Download the latest version of the **Microsoft Teams Rooms deployment kit** from <https://go.microsoft.com/fwlink/?linkid=851168>, and install it to a workstation.</span></span>

2.  <span data-ttu-id="45671-277">内容をコピーする**c:\\Program Files (x86)\\Skype ルーム システムの 『 導入ガイド 』** **SRS v2 の SRS のアプリケーション パッケージ**のフォルダーにします。</span><span class="sxs-lookup"><span data-stu-id="45671-277">Copy the content from **C:\\Program Files (x86)\\Skype Room System Deployment Kit** to the **SRS v2 - SRS Application Package** folder.</span></span>

3.  <span data-ttu-id="45671-278">**ソフトウェア ライブラリ**には、構成マネージャー コンソールで、 \> **アプリケーション管理** \> **パッケージ**、および**パッケージの作成**を選択します。</span><span class="sxs-lookup"><span data-stu-id="45671-278">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="45671-279">パッケージを作成するのには次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="45671-279">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="45671-280">**SRS v2 – SRS アプリケーション パッケージ**の名前:</span><span class="sxs-lookup"><span data-stu-id="45671-280">Name: **SRS v2 – SRS Application Package**</span></span>
    -   <span data-ttu-id="45671-281">製造元: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="45671-281">Manufacturer: **Microsoft Corporation**</span></span>
    -   <span data-ttu-id="45671-282">バージョン: **3.1.104.0** (ダウンロードしたインストール ファイルのバージョンを入力してください)</span><span class="sxs-lookup"><span data-stu-id="45671-282">Version: **3.1.104.0** (enter the version of the downloaded installation file)</span></span>
    -   <span data-ttu-id="45671-283">**このパッケージにソース ファイルが含まれています**] チェック ボックスをオンに、 **SRS v2 – SRS アプリケーション パッケージ**フォルダーへのパスを入力し、[**次へ**。</span><span class="sxs-lookup"><span data-stu-id="45671-283">Select the **This package contains source files** check box, enter the path to the **SRS v2 – SRS Application Package** folder, and then select **Next**.</span></span>
5.  <span data-ttu-id="45671-284">**プログラムを作成しない**を選択し、**次へ**します。</span><span class="sxs-lookup"><span data-stu-id="45671-284">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="45671-285">**設定の確認**] ページを確認し、**次へ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="45671-285">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="45671-286">**閉じる**を選択します。</span><span class="sxs-lookup"><span data-stu-id="45671-286">Select **Close**.</span></span>

### <a name="create-the-computer-name-assignment-package"></a><span data-ttu-id="45671-287">コンピューター名のアサイン パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="45671-287">Create the computer name assignment package</span></span>

1.  <span data-ttu-id="45671-288">**SRS v2 - セット SRSComputerName パッケージ**フォルダーには、**セット SRSComputerName.hta**をという名前の新しい HTML アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="45671-288">In the **SRS v2 - Set-SRSComputerName Package** folder, create a new HTML application named **Set-SRSComputerName.hta** .</span></span>

2.  <span data-ttu-id="45671-289">**セット SRSComputerName.hta**ファイルに次のスクリプトをコピーします。</span><span class="sxs-lookup"><span data-stu-id="45671-289">Copy the following script into the **Set-SRSComputerName.hta** file.</span></span> <span data-ttu-id="45671-290">または、[ここ](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)からセット SRSComputerName.hta ファイルをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="45671-290">Alternatively, you can download the Set-SRSComputerName.hta file from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
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
3.  <span data-ttu-id="45671-291">**ソフトウェア ライブラリ**には、構成マネージャー コンソールで、 \> **アプリケーション管理** \> **パッケージ**、および**パッケージの作成**を選択します。</span><span class="sxs-lookup"><span data-stu-id="45671-291">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="45671-292">パッケージを作成するのには次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="45671-292">Enter the following information to create the package:</span></span>

    -   <span data-ttu-id="45671-293">**SRS v2 - セット SRSComputerName パッケージ**の名前:</span><span class="sxs-lookup"><span data-stu-id="45671-293">Name: **SRS v2 - Set-SRSComputerName Package**</span></span>

    -   <span data-ttu-id="45671-294">製造元: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="45671-294">Manufacturer: **Microsoft Corporation**</span></span>

    -   <span data-ttu-id="45671-295">バージョン: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="45671-295">Version: **1.0.0**</span></span>

    -   <span data-ttu-id="45671-296">**このパッケージにソース ファイルが含まれています**] チェック ボックスをオンに、 **SRS の v2 - セット SRSComputerName パッケージ**のフォルダーにパスを入力し、**次へ**。</span><span class="sxs-lookup"><span data-stu-id="45671-296">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Set-SRSComputerName Package** folder, and then select **Next**.</span></span>

5.  <span data-ttu-id="45671-297">**プログラムを作成しない**を選択し、**次へ**します。</span><span class="sxs-lookup"><span data-stu-id="45671-297">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="45671-298">**設定の確認**] ページを確認し、**次へ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="45671-298">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="45671-299">**閉じる**を選択します。</span><span class="sxs-lookup"><span data-stu-id="45671-299">Select **Close**.</span></span>

### <a name="create-the-sysprep-package"></a><span data-ttu-id="45671-300">Sysprep パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="45671-300">Create the Sysprep package</span></span>

1. <span data-ttu-id="45671-301">**SRS v2 – パッケージの Sysprep**フォルダーには、 **Unattend.xml**をという名前の新しい XML ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="45671-301">In the **SRS v2 – Sysprep Package** folder, create a new XML file named **Unattend.xml** .</span></span>

2. <span data-ttu-id="45671-302">**Unattend.xml**ファイルに次のテキストをコピーします。</span><span class="sxs-lookup"><span data-stu-id="45671-302">Copy the following text into the **Unattend.xml** file.</span></span> <span data-ttu-id="45671-303">または、Unattend.xml ファイルを[ここ](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="45671-303">Alternatively, you can download the Unattend.xml file from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
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
3. <span data-ttu-id="45671-304">**ソフトウェア ライブラリ**には、構成マネージャー コンソールで、 \> **アプリケーション管理** \> **パッケージ**、および**パッケージの作成**を選択します。</span><span class="sxs-lookup"><span data-stu-id="45671-304">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4. <span data-ttu-id="45671-305">パッケージを作成するのには次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="45671-305">Enter the following information to create the package:</span></span>
   -   <span data-ttu-id="45671-306">**SRS v2 の Sysprep のパッケージ**の名前:</span><span class="sxs-lookup"><span data-stu-id="45671-306">Name: **SRS v2 - Sysprep Package**</span></span>
   -   <span data-ttu-id="45671-307">製造元: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="45671-307">Manufacturer: **Microsoft Corporation**</span></span>
   -   <span data-ttu-id="45671-308">バージョン: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="45671-308">Version: **1.0.0**</span></span>
   -   <span data-ttu-id="45671-309">**このパッケージにソース ファイルが含まれています**] チェック ボックスをオンに、 **SRS v2 – パッケージの Sysprep**フォルダーにパスを入力し、**次へ**。</span><span class="sxs-lookup"><span data-stu-id="45671-309">Select the **This package contains source files** check box, enter the path to the **SRS v2 – Sysprep Package** folder, and then select **Next**.</span></span>
5. <span data-ttu-id="45671-310">**プログラムを作成しない**を選択し、**次へ**します。</span><span class="sxs-lookup"><span data-stu-id="45671-310">Select **Do not create a program**, and then select **Next**.</span></span>

6. <span data-ttu-id="45671-311">**設定の確認**] ページを確認し、**次へ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="45671-311">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7. <span data-ttu-id="45671-312">**閉じる**を選択します。</span><span class="sxs-lookup"><span data-stu-id="45671-312">Select **Close**.</span></span>

### <a name="create-the-windows-10-enterprise-package"></a><span data-ttu-id="45671-313">10 エンタープライズの Windows パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="45671-313">Create the Windows 10 Enterprise package</span></span>

1.  <span data-ttu-id="45671-314">、10 企業の Windows x64 メディアを入手し、 **install.wim**ファイルのコピー、**のオペレーティング システム\\10 企業の Windows**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="45671-314">Obtain a Windows 10 Enterprise x64 media, and copy the **install.wim** file to the **Operating Systems\\Windows 10 Enterprise** folder.</span></span>

2.  <span data-ttu-id="45671-315">**ソフトウェア ライブラリ**には、構成マネージャー コンソールで、 \> **のオペレーティング システム** \> **オペレーティング システム イメージ**、および [**オペレーティング システム イメージを追加**します。</span><span class="sxs-lookup"><span data-stu-id="45671-315">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Operating System Images**, and then select **Add Operating System Image**.</span></span>

3.  <span data-ttu-id="45671-316">**Install.wim**ファイルをコピーしたパスを指定し、**次へ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="45671-316">Specify the path to the **install.wim** file you just copied, and then select **Next**.</span></span>

4.  <span data-ttu-id="45671-317">10 エンタープライズの Windows イメージのビルド番号が一致するように **[バージョン**] フィールドを更新し、**次へ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="45671-317">Update the **Version** field to match the build number of the Windows 10 Enterprise image, and then select **Next**.</span></span>

5.  <span data-ttu-id="45671-318">、**詳細**ページを確認し、**次へ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="45671-318">Review the **Details** page, and then select **Next**.</span></span>

6.  <span data-ttu-id="45671-319">**閉じる**を選択します。</span><span class="sxs-lookup"><span data-stu-id="45671-319">Select **Close**.</span></span>

<span data-ttu-id="45671-320">詳細については、[オペレーティング システム イメージの管理システム センター構成マネージャーの使用](https://docs.microsoft.com/sccm/osd/get-started/manage-operating-system-images)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45671-320">For more information, see [Manage operating system images with System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-operating-system-images).</span></span>

### <a name="create-surface-pro-device-driver-packages"></a><span data-ttu-id="45671-321">Surface Pro デバイス ドライバー パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="45671-321">Create Surface Pro device driver packages</span></span>

<span data-ttu-id="45671-322">Surface Pro と Surface Pro 4 の両方のマイクロソフト チームの会議室がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="45671-322">Microsoft Teams Rooms is supported for both Surface Pro and Surface Pro 4.</span></span> <span data-ttu-id="45671-323">環境内の各 Surface Pro モデル用のドライバー パッケージを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="45671-323">You need to create a driver package for each Surface Pro model you have in your environment.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="45671-324">ドライバーは、Windows 10 エンタープライズ ビルドとマイクロソフト チーム ルーム展開キットのバージョンと互換性のあるである必要があります。</span><span class="sxs-lookup"><span data-stu-id="45671-324">The drivers must be compatible with the Windows 10 Enterprise build and the Microsoft Teams Rooms deployment kit version.</span></span> <span data-ttu-id="45671-325">詳細については、[最新のファームウェア、および表面のデバイス用のドライバーをダウンロード](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices)し[、コンソールの構成](console.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45671-325">For more information, see [Download the latest firmware and drivers for Surface devices](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) and [Configure a console](console.md).</span></span>

1.  <span data-ttu-id="45671-326">最新のドライバーとファームウェアをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="45671-326">Download the latest drivers and firmware.</span></span>
    -   <span data-ttu-id="45671-327">Surface Pro: の<https://www.microsoft.com/download/details.aspx?id=55484></span><span class="sxs-lookup"><span data-stu-id="45671-327">For Surface Pro: <https://www.microsoft.com/download/details.aspx?id=55484></span></span>
    -   <span data-ttu-id="45671-328">Surface Pro の 4 を実行します。<https://www.microsoft.com/download/details.aspx?id=49498></span><span class="sxs-lookup"><span data-stu-id="45671-328">For Surface Pro 4: <https://www.microsoft.com/download/details.aspx?id=49498></span></span>

2.  <span data-ttu-id="45671-329">ダウンロードしたドライバーとファームウェアを抽出します。</span><span class="sxs-lookup"><span data-stu-id="45671-329">Extract the downloaded driver and firmware.</span></span> <span data-ttu-id="45671-330">コマンド プロンプト ウィンドウを開き、コマンド プロンプトで次のコマンドのいずれかを入力します。</span><span class="sxs-lookup"><span data-stu-id="45671-330">Open a Command Prompt window and at the command prompt, enter one of the following commands:</span></span>
    -   `msiexec /a C:\SurfacePro_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro"`
    -   `msiexec /a C:\SurfacePro4_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro 4"`

3.  <span data-ttu-id="45671-331">**ソフトウェア ライブラリ**には、構成マネージャー コンソールで、 \> **のオペレーティング システム** \> **ドライバー**、および**インポート ドライバー**を選択します。</span><span class="sxs-lookup"><span data-stu-id="45671-331">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Drivers**, and then select **Import Driver**.</span></span>

4.  <span data-ttu-id="45671-332">**次のネットワーク パス (UNC) のすべてのドライバーをインポート**] を選択、コピー元フォルダーを選択 (例、c:\\_Sources\\ドライバー\\Surface Pro)、し、**次へ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="45671-332">Select **Import all drivers in the following network path (UNC)**, select the source folder (for example, C:\\_Sources\\Drivers\\Surface Pro), and then select **Next**.</span></span>

5.  <span data-ttu-id="45671-333">**読み込まれたドライバーの詳細を指定**] ページで、一覧表示されているすべてのドライバーを選択し、選択**これらのドライバーを有効にしてコンピューターにインストールを許可します**。</span><span class="sxs-lookup"><span data-stu-id="45671-333">On the **Specify the details for the imported drivers** page, select all the listed drivers, and then select **Enable these drivers and allow computers to install them**.</span></span>

6.  <span data-ttu-id="45671-334">**カテゴリ**を選択して、サーフェス モデルと一致する新しいカテゴリを作成、 **[ok]** を選択し、**次へ**。</span><span class="sxs-lookup"><span data-stu-id="45671-334">Select **Categories**, create a new category that matches the Surface model, select **OK**, and then select **Next**.</span></span>

7.  <span data-ttu-id="45671-335">**新しいパッケージ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="45671-335">Select **New Package**.</span></span>

8.  <span data-ttu-id="45671-336">Surface Pro のモデルと一致するパッケージ名を指定して、 **[ok]** を選択して、[**次へ**]、ドライバー パッケージ内のファイルを格納するフォルダーのパスを入力します。</span><span class="sxs-lookup"><span data-stu-id="45671-336">Specify the package name that matches the Surface Pro model, enter a folder path to store the driver package files in, select **OK**, and then select **Next**.</span></span>

9.  <span data-ttu-id="45671-337">[**ブート イメージ**] ページで、ブート イメージが選択されていると、**次へ**を選択しであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="45671-337">On the **boot images** page, ensure that no boot images are selected, and then select **Next**.</span></span>

10. <span data-ttu-id="45671-338">**閉じる**を選択します。</span><span class="sxs-lookup"><span data-stu-id="45671-338">Select **Close**.</span></span>

11. <span data-ttu-id="45671-339">**ソフトウェア ライブラリ**を参照して\>**のオペレーティング システム** \> **ドライバー**を選択**フォルダー\>フォルダーの作成**、Surface Pro のドライバーをインポートしたモデルと一致するフォルダー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="45671-339">Go to **Software Library** \> **Operating Systems** \> **Drivers**, select **Folder \> Create Folder**, and enter a folder name that matches the Surface Pro model that you just imported the drivers for.</span></span>

12. <span data-ttu-id="45671-340">インポートされたすべてのドライバーを簡単に移動および操作の新しく作成したフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="45671-340">Move all the imported drivers to the newly created folder for easier navigation and operation.</span></span>

> [!NOTE]
> <span data-ttu-id="45671-341">他の Surface Pro モデルをする必要があります、同じ手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="45671-341">Repeat the same steps for other Surface Pro models you might have.</span></span> <span data-ttu-id="45671-342">詳細については、[システム センター構成マネージャーでの管理ドライバー](https://docs.microsoft.com/sccm/osd/get-started/manage-drivers)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45671-342">For more information, see [Manage drivers in System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-drivers).</span></span>

### <a name="create-microsoft-teams-rooms-configuration-package"></a><span data-ttu-id="45671-343">マイクロソフトのチーム会議室の構成パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="45671-343">Create Microsoft Teams Rooms Configuration Package</span></span>

1.  <span data-ttu-id="45671-344">**ソフトウェア ライブラリ**には、構成マネージャー コンソールで、 \> **アプリケーション管理** \> **パッケージ**、および**パッケージの作成**を選択します。</span><span class="sxs-lookup"><span data-stu-id="45671-344">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

2.  <span data-ttu-id="45671-345">パッケージを作成するのには次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="45671-345">Enter the following information to create the package:</span></span>

    -   <span data-ttu-id="45671-346">名前: **SRS v2 の SRS のセットアップ パッケージを構成します。**</span><span class="sxs-lookup"><span data-stu-id="45671-346">Name: **SRS v2 - Configure SRS Setup Package**</span></span>

    -   <span data-ttu-id="45671-347">製造元: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="45671-347">Manufacturer: **Microsoft Corporation**</span></span>

    -   <span data-ttu-id="45671-348">バージョン: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="45671-348">Version: **1.0.0**</span></span>

    -   <span data-ttu-id="45671-349">**このパッケージにソース ファイルが含まれています**] チェック ボックスをオンに、 **SRS v2 の SRS の設定を構成する**フォルダーのパスを入力し、[**次へ**。</span><span class="sxs-lookup"><span data-stu-id="45671-349">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Configure SRS Setup** folder, and then select **Next**.</span></span>

3.  <span data-ttu-id="45671-350">**プログラムを作成しない**を選択し、**次へ**します。</span><span class="sxs-lookup"><span data-stu-id="45671-350">Select **Do not create a program**, and then select **Next**.</span></span>

4.  <span data-ttu-id="45671-351">**設定の確認**] ページを確認し、**次へ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="45671-351">Review the **Confirm the settings** page, and then select **Next**.</span></span>

5.  <span data-ttu-id="45671-352">**閉じる**を選択します。</span><span class="sxs-lookup"><span data-stu-id="45671-352">Select **Close**.</span></span>



## <a name="distribute-configuration-manager-packages"></a><span data-ttu-id="45671-353">構成マネージャー パッケージを配布します。</span><span class="sxs-lookup"><span data-stu-id="45671-353">Distribute Configuration Manager packages</span></span>

<span data-ttu-id="45671-354">すべてのパッケージは、構成マネージャー階層内の配布ポイントの役割が割り当てられているサーバーに分散する必要があります。</span><span class="sxs-lookup"><span data-stu-id="45671-354">All the packages must be distributed to the servers that have been assigned the distribution point role in the Configuration Manager hierarchy.</span></span> <span data-ttu-id="45671-355">パッケージの配布を開始するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="45671-355">Follow the instructions below to initiate package distribution.</span></span>

1.  <span data-ttu-id="45671-356">ソフトウェア パッケージを配布します。</span><span class="sxs-lookup"><span data-stu-id="45671-356">Distribute software packages.</span></span>

    1.  <span data-ttu-id="45671-357">**ソフトウェア ライブラリ**には、構成マネージャー コンソールで、 \> **アプリケーション管理** \> **パッケージ**です。</span><span class="sxs-lookup"><span data-stu-id="45671-357">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**.</span></span> <span data-ttu-id="45671-358">、配布するすべてのソフトウェア パッケージを選択し、**コンテンツを配布**します。</span><span class="sxs-lookup"><span data-stu-id="45671-358">Select all the software packages you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="45671-359">、パッケージのリストを確認し、**次へ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="45671-359">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="45671-360">すべての配布ポイント サーバー (または、構成マネージャー階層に応じて、配布ポイント グループ) をリストに追加し、**次へ**します。</span><span class="sxs-lookup"><span data-stu-id="45671-360">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="45671-361">**次へ**を選択し、[**閉じる**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="45671-361">Select **Next**, and then select **Close**.</span></span>

2.  <span data-ttu-id="45671-362">ドライバー パッケージを配布します。</span><span class="sxs-lookup"><span data-stu-id="45671-362">Distribute driver packages.</span></span>

    1.  <span data-ttu-id="45671-363">**ソフトウェア ライブラリ**には、構成マネージャー コンソールで、 \> **のオペレーティング システム** \> **のドライバー パッケージ**。</span><span class="sxs-lookup"><span data-stu-id="45671-363">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Driver Packages**.</span></span> <span data-ttu-id="45671-364">、配布するすべてのドライバー パッケージを選択し、**コンテンツを配布**します。</span><span class="sxs-lookup"><span data-stu-id="45671-364">Select all the driver packages you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="45671-365">、パッケージのリストを確認し、**次へ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="45671-365">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="45671-366">すべての配布ポイント サーバー (または、構成マネージャー階層に応じて、配布ポイント グループ) をリストに追加し、**次へ**します。</span><span class="sxs-lookup"><span data-stu-id="45671-366">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="45671-367">**次へ**を選択し、[**閉じる**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="45671-367">Select **Next**, and then select **Close**.</span></span>

3.  <span data-ttu-id="45671-368">オペレーティング システム パッケージを配布します。</span><span class="sxs-lookup"><span data-stu-id="45671-368">Distribute operating system packages.</span></span>

    1.  <span data-ttu-id="45671-369">**ソフトウェア ライブラリ**には、構成マネージャー コンソールで、 \> **のオペレーティング システム** \> **オペレーティング システムのイメージ**です。</span><span class="sxs-lookup"><span data-stu-id="45671-369">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Operating System Images**.</span></span> <span data-ttu-id="45671-370">、配布するすべてのオペレーティング システム イメージを選択し、**コンテンツを配布**します。</span><span class="sxs-lookup"><span data-stu-id="45671-370">Select all the operating system images you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="45671-371">、パッケージのリストを確認し、**次へ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="45671-371">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="45671-372">すべての配布ポイント サーバー (または、構成マネージャー階層に応じて、配布ポイント グループ) をリストに追加し、**次へ**します。</span><span class="sxs-lookup"><span data-stu-id="45671-372">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="45671-373">**次へ**を選択し、[**閉じる**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="45671-373">Select **Next**, and then select **Close**.</span></span>

> [!NOTE]
> <span data-ttu-id="45671-374">パッケージの配布には、パッケージのサイズ、構成マネージャー階層、配布ポイント サーバーの数は、ネットワークで利用できる帯域幅によっては、時間をかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="45671-374">Package distribution might take some time, depending on the package size, Configuration Manager hierarchy, number of distribution point servers, and the bandwidth available in your network.</span></span>
> 
> <span data-ttu-id="45671-375">マイクロソフト チームの会議室のユニットを展開する前にすべてのパッケージを配布する必要があります。</span><span class="sxs-lookup"><span data-stu-id="45671-375">All the packages must be distributed before you can start deploying a Microsoft Teams Rooms unit.</span></span>
> 
> <span data-ttu-id="45671-376">構成マネージャー コンソールで、パッケージの配布ステータスを確認するには**監視**することで\>**の配布ステータス** \> **コンテンツの状態**です。</span><span class="sxs-lookup"><span data-stu-id="45671-376">You can review the status of your package distribution in the Configuration Manager console by going to **Monitoring** \> **Distribution Status** \> **Content Status**.</span></span>

## <a name="configuration-manager-task-sequences"></a><span data-ttu-id="45671-377">構成マネージャーのタスク シーケンス</span><span class="sxs-lookup"><span data-stu-id="45671-377">Configuration Manager task sequences</span></span>

<span data-ttu-id="45671-378">使用して、タスク シーケンスがシステム センター構成マネージャーをセットアップ先のコンピューターにオペレーティング システム イメージを展開するための手順を自動化します。</span><span class="sxs-lookup"><span data-stu-id="45671-378">You use task sequences with System Center Configuration Manager to automate the steps for deploying an operating system image to a destination computer.</span></span> <span data-ttu-id="45671-379">自動化された方法でマイクロソフト チームの会議室のユニットを配置するには、マイクロソフト チームの会議室のセットアップ先のコンピューター、10 企業の Windows オペレーティング システム イメージをインストールしていずれかを起動するために使用するブート イメージを参照するタスク シーケンスを作成します。他のアプリケーションやソフトウェア更新プログラムなどの他の追加コンテンツ。</span><span class="sxs-lookup"><span data-stu-id="45671-379">To deploy a Microsoft Teams Rooms unit in an automated fashion, you create a task sequence that references the boot image used to start the destination Microsoft Teams Rooms computer, the Windows 10 Enterprise operating system image that you want to install, and any other additional content, such as other applications or software updates.</span></span>

### <a name="import-the-sample-task-sequence"></a><span data-ttu-id="45671-380">サンプル タスク シーケンスをインポートします。</span><span class="sxs-lookup"><span data-stu-id="45671-380">Import the sample task sequence</span></span>

<span data-ttu-id="45671-381">ダウンロードし簡単にサンプルのタスク シーケンスをインポートしてお客様のニーズを満たすためにカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="45671-381">You can download and easily import a sample task sequence and customize it to meet your needs.</span></span>

1.  <span data-ttu-id="45671-382">サンプルのタスク シーケンス[**をダウンロード**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)し、共有の場所にダウンロードした zip ファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="45671-382">[**Download**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) the sample task sequence, and copy the downloaded zip file to a shared location.</span></span>
2.  <span data-ttu-id="45671-383">**ソフトウェア ライブラリ**には、構成マネージャー コンソールで、 \> **のオペレーティング システム** \> **タスク シーケンス**、および選択し、**タスク シーケンスのインポート**します。</span><span class="sxs-lookup"><span data-stu-id="45671-383">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Task Sequences**, and then select **Import Task Sequence**.</span></span>

3.  <span data-ttu-id="45671-384">**参照**を選択して、手順 1 で使用する共有フォルダーの場所に、**マイクロソフト チームの会議室の展開 (EN-US) の .zip**ファイルを選択し、**次**のように選択を移動します。</span><span class="sxs-lookup"><span data-stu-id="45671-384">Select **Browse**, go to the shared folder location you used in step 1, select the **Microsoft Teams Rooms Deployment (EN-US).zip** file, and then select **Next**.</span></span>

4.  <span data-ttu-id="45671-385">**アクション**を**新規作成**] を設定し、**次へ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="45671-385">Set **Action** to **Create New**, and then select **Next**.</span></span>

5.  <span data-ttu-id="45671-386">設定内容を確認し、**次へ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="45671-386">Confirm the settings, and then select **Next**.</span></span>

6.  <span data-ttu-id="45671-387">**閉じる**を選択します。</span><span class="sxs-lookup"><span data-stu-id="45671-387">Select **Close**.</span></span>

### <a name="validate-that-the-reference-packages-are-correctly-linked-to-each-task-sequence-step"></a><span data-ttu-id="45671-388">各タスク シーケンスのステップには、参照のパッケージが正しくリンクされているかを検証します。</span><span class="sxs-lookup"><span data-stu-id="45671-388">Validate that the reference packages are correctly linked to each task sequence step.</span></span>

1. <span data-ttu-id="45671-389">、インポートされたタスク シーケンスを選択し、**編集**を選択します。</span><span class="sxs-lookup"><span data-stu-id="45671-389">Select the imported task sequence, and then select **Edit**.</span></span>

    <span data-ttu-id="45671-390">タスク シーケンス エディターが開き、展開し、マイクロソフト チームの会議室のユニットを構成する必要がある連続した各ステップが表示されます。</span><span class="sxs-lookup"><span data-stu-id="45671-390">The Task Sequence Editor opens and displays each sequential step that you need to deploy and configure a Microsoft Teams Rooms unit.</span></span>

2. <span data-ttu-id="45671-391">各ステップを紹介し、推奨される更新プログラムを完了します。</span><span class="sxs-lookup"><span data-stu-id="45671-391">Walk through each step and complete the recommended updates:</span></span>

   1. <span data-ttu-id="45671-392">**Windows PE で再起動**: この手順が再起動し、Windows の PXE にコンピューターを起動します。</span><span class="sxs-lookup"><span data-stu-id="45671-392">**Restart in Windows PE**: This step restarts and then boots the computer into Windows PXE.</span></span> <span data-ttu-id="45671-393">変更は、この手順で必要ではありません。</span><span class="sxs-lookup"><span data-stu-id="45671-393">No changes are required for this step.</span></span>

   2. <span data-ttu-id="45671-394">**パーティション ディスク 0-UEFI**: この手順は、ディスク構成を消去し、構成した設定に基づいてパーティションを作成します。</span><span class="sxs-lookup"><span data-stu-id="45671-394">**Partition Disk 0 – UEFI**: This step wipes the disk configuration and creates partitions based on the configured settings.</span></span> <span data-ttu-id="45671-395">おすべての変更この手順をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="45671-395">We recommend that you not make any changes to this step.</span></span>

   3. <span data-ttu-id="45671-396">**SRS コンピューター名の設定**: この手順には、展開時にマイクロソフト チーム ルーム単位のコンピューター名を設定するための UI を提供する HTML アプリケーションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="45671-396">**Set SRS Computer Name**: This step includes an HTML application to provide a UI to set a computer name for the Microsoft Teams Rooms unit during the deployment.</span></span>
      -  <span data-ttu-id="45671-397">これはオプションの手順ですが、それのみを無効にできます、別のプロセスによって名前付けのコンピューターを管理する場合は。</span><span class="sxs-lookup"><span data-stu-id="45671-397">This is an optional step, but it can only be disabled if you want to manage computer naming through an alternate process.</span></span>
      -  <span data-ttu-id="45671-398">**SRS v2 - セット SRSComputerName**パッケージが選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="45671-398">Verify that the **SRS v2 - Set-SRSComputerName** package is selected.</span></span> <span data-ttu-id="45671-399">いない場合は、パッケージを参照して選択します。</span><span class="sxs-lookup"><span data-stu-id="45671-399">If it isn’t, browse to the package and select it.</span></span>

   4. <span data-ttu-id="45671-400">**オペレーティング システムの適用**: この手順は、オペレーティング システム イメージを展開して、無人 Sysprep 応答ファイルを使用するを指定します。</span><span class="sxs-lookup"><span data-stu-id="45671-400">**Apply Operating System**: This step specifies the operating system image to be deployed and the unattended Sysprep answer file to use.</span></span>
      -  <span data-ttu-id="45671-401">正しい 10 企業の Windows オペレーティング システム イメージ ファイルが選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="45671-401">Verify that the correct Windows 10 Enterprise operating system image file is selected.</span></span>
      -  <span data-ttu-id="45671-402">**無人を使用するかカスタム インストール用応答ファイルを Sysprep**を有効にすると、 **SRS v2 の Sysprep のパッケージ**が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="45671-402">Verify that **Use an unattended or Sysprep answer file for a custom installation** is enabled, and the **SRS v2 - Sysprep Package** is selected.</span></span> <span data-ttu-id="45671-403">**Unattend.xml**に**ファイル名**が設定されていることを確認もします。</span><span class="sxs-lookup"><span data-stu-id="45671-403">Also ensure that **File Name** is set to **unattend.xml**.</span></span>

   5. <span data-ttu-id="45671-404">**Windows の設定を適用**: この手順は、Windows のインストールに関する情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="45671-404">**Apply Windows Settings**: This step gathers information about the Windows installation.</span></span>
      -  <span data-ttu-id="45671-405">プロダクト キー、ローカルの管理者アカウントのパスワード、および (必要) に応じて、タイム ゾーンを含むライセンスと登録の情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="45671-405">Provide licensing and registration information including the product key, local administrator account password, and time zone (depending on your needs).</span></span>

   6. <span data-ttu-id="45671-406">**ネットワーク設定を適用**: この手順では、ワークグループまたは Active Directory ドメイン名と組織単位を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="45671-406">**Apply Network Settings**: This step allows you to specify a workgroup or Active Directory domain name and organizational unit.</span></span>
      > [!NOTE]
      > <span data-ttu-id="45671-407">Actve ディレクトリ ドメインのメンバーとしてマイクロソフト チームの会議室のユニットを展開する必要がある、推奨される操作の[Skype ルーム ・ システム ・ ドメインへの参加に関する考慮事項](domain-joining-considerations.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45671-407">See [Skype Room System domain joining considerations](domain-joining-considerations.md) for recommended actions you need to take in deploying Microsoft Teams Rooms units as members of an Actve Directory domain.</span></span>
   7. <span data-ttu-id="45671-408">**ドライバーを適用する:** この手順とその下位の手順は、適用可能なデバイス ドライバーとファームウェアがある Surface Pro モデルをベースに展開する使用されます。</span><span class="sxs-lookup"><span data-stu-id="45671-408">**Apply Drivers:** This step and its sub-steps are used to deploy applicable device drivers and firmware based on the Surface Pro model you have.</span></span> <span data-ttu-id="45671-409">この展開に関連付けられている関連するドライバー パッケージを指定するには、各ステップを更新します。</span><span class="sxs-lookup"><span data-stu-id="45671-409">Update each step to specify the relevant driver package associated with this deployment.</span></span>
      -   <span data-ttu-id="45671-410">関連ドライバーを展開する Windows 管理インストルメンテーション (WMI) フィルターを活用する各ドライバー パッケージを構成し、Surface Pro のファームウェアの製造元しモデルします。</span><span class="sxs-lookup"><span data-stu-id="45671-410">Each driver package is configured to leverage Windows Management Instrumentation (WMI) filters to deploy relevant drivers and firmware based on the Surface Pro make and model.</span></span>
      -   <span data-ttu-id="45671-411">これらのドライバーの構成を変更、配置が失敗する可能性がありますそれ以外の場合のことを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="45671-411">We highly recommend that you not alter the configuration of these drivers, otherwise deployment might fail.</span></span>

   8. <span data-ttu-id="45671-412">**Windows と構成マネージャーの設定**: このステップの配置し、構成マネージャーのクライアントを構成します。</span><span class="sxs-lookup"><span data-stu-id="45671-412">**Set up Windows and Configuration Manager**: This step deploys and configures the Configuration Manager client.</span></span> <span data-ttu-id="45671-413">組み込みの構成マネージャーのクライアント パッケージを指定するには、この手順を更新します。</span><span class="sxs-lookup"><span data-stu-id="45671-413">Update this step to specify the built-in Configuration Manager Client Package.</span></span>

   9. <span data-ttu-id="45671-414">**ルート証明書のインストール**: この手順は: ドメインに参加しているデバイスでは、ルート証明書を配布し、そのため、省略可能な既定で無効になっています。</span><span class="sxs-lookup"><span data-stu-id="45671-414">**Install Root Certificate**: This step distributes the root certificate for non–domain-joined devices, and therefore is optional and disabled by default.</span></span>
      -   <span data-ttu-id="45671-415">マイクロソフト チームの会議室のユニットにルート証明書を展開する必要がある場合は、この手順を有効にします。</span><span class="sxs-lookup"><span data-stu-id="45671-415">Enable this step if you need to deploy a root certificate to the Microsoft Teams Rooms units.</span></span>
      -   <span data-ttu-id="45671-416">この手順を実行する必要がある場合は、 **SRS のバージョン 2: ルート証明書のパッケージ**と**ファイル システムのリダイレクトを無効にする 64 ビット**がオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="45671-416">If you do need to perform this step, verify that the **SRS v2 – Root Certificate Package** and **Disable 64-bit file system redirection** are selected.</span></span>

   10. <span data-ttu-id="45671-417">**インストールし監視エージェントの構成**: この手順は、Microsoft Azure のモニター ・ エージェントの 64 ビット バージョンをインストールし、エージェントが、ログの分析機能のワークスペースへの接続を構成します。</span><span class="sxs-lookup"><span data-stu-id="45671-417">**Install and Configure Monitoring Agent**: This step installs the 64-bit version of the Microsoft Azure Monitor agent and configures the agent to connect to your Log Analytics workspace.</span></span>
       -   <span data-ttu-id="45671-418">この手順は既定で無効になります。</span><span class="sxs-lookup"><span data-stu-id="45671-418">This step is disabled by default.</span></span> <span data-ttu-id="45671-419">マイクロソフト チームの部屋にいるユニットの状態を監視する監視エージェントを使用しようとしている場合にのみ、この手順を有効にします。</span><span class="sxs-lookup"><span data-stu-id="45671-419">Enable this step only if you’re going to use the Monitoring Agent to monitor the health of your Microsoft Teams Rooms units.</span></span>
       -   <span data-ttu-id="45671-420">このステップを編集し、自分の**ワークスペースの ID**と**キーのワークスペース**を指定するコマンド ライン パラメーターを更新します。</span><span class="sxs-lookup"><span data-stu-id="45671-420">Edit this step and update the command-line parameters to specify your **Workspace ID** and **Workspace Key**.</span></span>
       -   <span data-ttu-id="45671-421">操作の管理スイートのワークスペース ID とプライマリ ・ キーの入手方法の詳細については、 [Azure を監視するためのデバイスをテスト構成](azure-monitor.md#configure-test-devices-for-azure-monitoring)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45671-421">See [Configure test devices for Azure Monitoring](azure-monitor.md#configure-test-devices-for-azure-monitoring) for more information about obtaining the Operations Management Suite Workspace ID and the primary key.</span></span>
       -   <span data-ttu-id="45671-422">**SRS v2 – マイクロソフトの監視エージェントのパッケージ**と**ファイル システムのリダイレクトを無効にする 64 ビット**がオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="45671-422">Verify that the **SRS v2 – Microsoft Monitoring Agent Package** and **Disable 64-bit file system redirection** are selected.</span></span>
       -   <span data-ttu-id="45671-423">マイクロソフト チームの会議室の配置の正常性の監視の詳細については、「 [Azure のモニターを使用して Microsoft チーム部屋計画の管理](../../plan-your-deployment/clients-and-devices/azure-monitor.md) [Azure モニターを使用してマイクロソフトの展開チームの会議室の管理](azure-monitor.md)および[管理 Microsoft の使用」を参照してください。Azure のモニターを使用してデバイスを会議室のチーム](../../manage/skype-room-systems-v2/azure-monitor.md)です。</span><span class="sxs-lookup"><span data-stu-id="45671-423">For more information about monitoring the health of your Microsoft Teams Rooms deployment, see [Plan Microsoft Teams Rooms management with Azure Monitor](../../plan-your-deployment/clients-and-devices/azure-monitor.md), [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor.md) and [Manage Microsoft Teams Rooms devices with Azure Monitor](../../manage/skype-room-systems-v2/azure-monitor.md).</span></span>

   11. <span data-ttu-id="45671-424">**V2 構成ファイルのコピーの SRS**: ここでは、マイクロソフトのチーム会議室 『 導入ガイド 』 からローカル ハード ドライブに必要なセットアップと構成ファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="45671-424">**Copy SRS v2 Configuration Files**: This step copies the required setup and configuration files from the Microsoft Teams Rooms deployment kit to the local hard drive.</span></span> <span data-ttu-id="45671-425">カスタマイズは、この手順は必要ではありません。</span><span class="sxs-lookup"><span data-stu-id="45671-425">No customization is required for this step.</span></span>
       -   <span data-ttu-id="45671-426">**SRS v2 – SRS アプリケーション パッケージ**と**ファイル システムのリダイレクトを無効にする 64 ビット**がオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="45671-426">Verify that the **SRS v2 – SRS Application Package** and **Disable 64-bit file system redirection** are selected.</span></span>

   12. <span data-ttu-id="45671-427">**SRSv2-OS の更新プログラムをインストール**: この手順は、マイクロソフト チームの会議室の配置に必要なオペレーティング システムの必須更新プログラムを配置します。</span><span class="sxs-lookup"><span data-stu-id="45671-427">**Install-SRSv2-OS-Updates**: This step deploys any mandatory operating system updates required with the Microsoft Teams Rooms deployment.</span></span> <span data-ttu-id="45671-428">次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="45671-428">Do the following:</span></span>
       -   <span data-ttu-id="45671-429">必要な更新プログラムを確認するのには、[マイクロソフト チームの会議室のコンソールの構成](console.md)を確認します。</span><span class="sxs-lookup"><span data-stu-id="45671-429">Check [Configure a Microsoft Teams Rooms console](console.md) to see which updates are required.</span></span>
       -   <span data-ttu-id="45671-430">**SRS v2 – OS の更新プログラム パッケージ**に必要なすべての更新プログラムが含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="45671-430">Verify that your **SRS v2 – OS Updates Package** includes all the required updates.</span></span>
       -   <span data-ttu-id="45671-431">**SRS v2 – OS の更新プログラム パッケージ**が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="45671-431">Verify that the **SRS v2 – OS Updates Package** is selected.</span></span>
       -   <span data-ttu-id="45671-432">PowerShell 実行ポリシーを**バイパス**に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="45671-432">Verify that the PowerShell execution policy is set to **Bypass**.</span></span>

   13. <span data-ttu-id="45671-433">**コンピューターの再起動**: この手順は、オペレーティング システムの必須更新プログラムをインストールした後にコンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="45671-433">**Restart Computer**: This step reboots the computer after the mandatory operating system updates are installed.</span></span> <span data-ttu-id="45671-434">カスタマイズは、この手順は必要ではありません。</span><span class="sxs-lookup"><span data-stu-id="45671-434">No customization is required for this step.</span></span>

   14. <span data-ttu-id="45671-435">**Windows コンポーネントの構成**: この手順が必要な Windows の機能を構成します。</span><span class="sxs-lookup"><span data-stu-id="45671-435">**Configure Windows Components**: This step configures the required Windows features.</span></span> <span data-ttu-id="45671-436">カスタマイズは、この手順は必要ではありません。</span><span class="sxs-lookup"><span data-stu-id="45671-436">No customization is required for this step.</span></span>

   15. <span data-ttu-id="45671-437">**コンピューターの再起動**: この手順は、Windows の機能を構成した後にコンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="45671-437">**Restart Computer**: This step reboots the computer after the Windows features are configured.</span></span> <span data-ttu-id="45671-438">カスタマイズは、この手順は必要ではありません。</span><span class="sxs-lookup"><span data-stu-id="45671-438">No customization is required for this step.</span></span>

   16. <span data-ttu-id="45671-439">**ローカル Skype ユーザーの追加**: この手順が自動的に Windows にサインインし、チームの会議室をマイクロソフトのアプリケーションを起動するために使用するローカル Skype アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="45671-439">**Add Local Skype User**: This step creates the local Skype account used to automatically sign in to Windows and start the Microsoft Teams Rooms application.</span></span> <span data-ttu-id="45671-440">この手順は、それに関連付けられている任意のソフトウェア パッケージを持っていないし、カスタマイズすることの必要はありません。</span><span class="sxs-lookup"><span data-stu-id="45671-440">This step doesn’t have any software package associated with it, and no customization is required for it.</span></span>

   17. <span data-ttu-id="45671-441">**設定セットアップおよび SRS のアプリケーションを構成する**: この手順は、オペレーティング システムの次回の起動時には、マイクロソフト チームの会議室アプリケーションのインストールを構成します。</span><span class="sxs-lookup"><span data-stu-id="45671-441">**Set up and configure SRS application**: This step configures the Microsoft Teams Rooms application installation for the next boot of the operating system.</span></span>
       -   <span data-ttu-id="45671-442">**SRS v2 – SRS セットアップ パッケージの構成**と**ファイル システムのリダイレクトを無効にする 64 ビット**がオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="45671-442">Verify that the **SRS v2 – Configure SRS Setup Package** and **Disable 64-bit file system redirection** are selected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="45671-443">タスク シーケンスの手順が記載されている順序である必要がありますが非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="45671-443">It is very important that the task sequence steps must be in the provided order.</span></span> <span data-ttu-id="45671-444">手順の順序を変更または追加の手順を構成するには、展開を壊れる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="45671-444">Modifying the order of steps, or configuring additional steps might break the deployment.</span></span>
>
> <span data-ttu-id="45671-445">**設定セットアップおよび SRS のアプリケーションを構成する**の手順は、タスク シーケンスの最後のステップをする必要があります、それ以外の場合、展開が失敗可能性があります。</span><span class="sxs-lookup"><span data-stu-id="45671-445">**Set up and configure SRS application** step must be the last step in the task sequence, otherwise the deployment might fail.</span></span>

### <a name="create-deployment-for-the-task-sequence"></a><span data-ttu-id="45671-446">展開タスク シーケンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="45671-446">Create deployment for the task sequence</span></span>

1. <span data-ttu-id="45671-447">タスク シーケンスを選択し、[**配置**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="45671-447">Select the task sequence, and then select **Deploy**.</span></span>

2. <span data-ttu-id="45671-448">展開のターゲット コレクションを選択する**参照**を選択します。</span><span class="sxs-lookup"><span data-stu-id="45671-448">Select **Browse** to select target collection for deployment.</span></span>

3. <span data-ttu-id="45671-449">**すべての不明なコンピューター**を選択し、 **[ok]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="45671-449">Select **All Unknown Computers** and then select **OK**.</span></span>

4. <span data-ttu-id="45671-450">**次へ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="45671-450">Select **Next**.</span></span>

5. <span data-ttu-id="45671-451">**目的**のドロップ ダウン リストで**利用可能な**を選択します。</span><span class="sxs-lookup"><span data-stu-id="45671-451">Select **Available** on the **Purpose** drop down list.</span></span>

6. <span data-ttu-id="45671-452">**次に使用できるように**する] の一覧で、**のみメディアおよび PXE**を選択し、**次へ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="45671-452">Select **Only Media and PXE** in the **Make available to the following** list, and then select **Next**.</span></span>
   > [!WARNING]
   > <span data-ttu-id="45671-453">**目的**が**使用可能**に設定されているが非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="45671-453">It is very important that **Purpose** is set to **Available**.</span></span> <span data-ttu-id="45671-454">**目的**では**ない**に**必要な**設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="45671-454">Make sure that the **Purpose** is **NOT** set to **Required**.</span></span> <span data-ttu-id="45671-455">また **、次に使用できるように**する**だけのメディアと PXE**を選択することを確認します。</span><span class="sxs-lookup"><span data-stu-id="45671-455">Also make sure that you select **Only Media and PXE** in the **Make available to the following**.</span></span>
   >
   > <span data-ttu-id="45671-456">別のものにこれらの値を設定すると、すべてのコンピューターを起動したときマイクロソフト チームの会議室の展開イメージを取得する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="45671-456">Setting these values to something else might cause all computers to get the Microsoft Teams Rooms deployment image when booted.</span></span>
7. <span data-ttu-id="45671-457">ない任意のスケジュールを指定する] をクリック**します。**</span><span class="sxs-lookup"><span data-stu-id="45671-457">Do not specify any schedule and select **Next**.</span></span>

8. <span data-ttu-id="45671-458">ない**ユーザー エクスペリエンス**セクション内のすべての変更] をクリック**します。**</span><span class="sxs-lookup"><span data-stu-id="45671-458">Do not change anything within the **User Experience** section and select **Next**.</span></span>

9. <span data-ttu-id="45671-459">ない、[**通知**] セクション内のすべての変更] をクリック**します。**</span><span class="sxs-lookup"><span data-stu-id="45671-459">Do not change anything within the **Alerts** section and select **Next**.</span></span>

10. <span data-ttu-id="45671-460">されない、[**配布ポイント**] セクション内のすべての変更] をクリック**します。**</span><span class="sxs-lookup"><span data-stu-id="45671-460">Do not change anything within the **Distribution Points** section and select **Next**.</span></span>

11. <span data-ttu-id="45671-461">設定を確認し、**次へ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="45671-461">Confirm the settings and then select **Next**.</span></span>

12. <span data-ttu-id="45671-462">**閉じる**を選択します。</span><span class="sxs-lookup"><span data-stu-id="45671-462">Select **Close**.</span></span>

<a name="validate-and-troubleshoot-the-solution"></a><span data-ttu-id="45671-463">検証し、ソリューションのトラブルシューティングを行う</span><span class="sxs-lookup"><span data-stu-id="45671-463">Validate and troubleshoot the solution</span></span>
--------------------------------------

<span data-ttu-id="45671-464">システム センター構成マネージャーのタスク シーケンスが完了したら、タスク シーケンスが展開し、マイクロソフト チームの会議室のユニットの構成を検証するために実行するテストを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="45671-464">After you’ve completed the System Center Configuration Manager task sequences, you’ll need to perform a test run to validate that the task sequence can deploy and configure Microsoft Teams Rooms units.</span></span>

1.  <span data-ttu-id="45671-465">サポートされているイーサネット アダプターのいずれかまたは表面のドッキング ステーションを使用してワイヤード (有線) ネットワークへのテスト デバイスを接続します。</span><span class="sxs-lookup"><span data-stu-id="45671-465">Connect the test device to the wired network by using one of the supported Ethernet adapters or using the Surface dock.</span></span> <span data-ttu-id="45671-466">環境内の PXE ブート機能が構成されていない場合は、USB からブートし、構成マネージャーに接続する USB フラッシュ ドライブで[以前に作成した](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media)ブート イメージを使用できます。</span><span class="sxs-lookup"><span data-stu-id="45671-466">If PXE boot functionality hasn’t been configured for your environment, you can use the boot image on the USB flash drive [that you created earlier](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media) to boot from USB and connect to Configuration Manager.</span></span>

2.  <span data-ttu-id="45671-467">ファームウェアにアクセスし、PXE ブートを開始します。</span><span class="sxs-lookup"><span data-stu-id="45671-467">Access the firmware and initiate PXE boot:</span></span>

    1.  <span data-ttu-id="45671-468">サーフェスのデバイスの電源を切ったことを確認します。</span><span class="sxs-lookup"><span data-stu-id="45671-468">Ensure the Surface device is powered off.</span></span>

    2.  <span data-ttu-id="45671-469">**音量アップ**ボタンを押したままにします。</span><span class="sxs-lookup"><span data-stu-id="45671-469">Press and hold the **Volume Up** button.</span></span>

    3.  <span data-ttu-id="45671-470">キーを押し、**電源**ボタンを離します。</span><span class="sxs-lookup"><span data-stu-id="45671-470">Press and release the **Power** button.</span></span>

    4.  <span data-ttu-id="45671-471">デバイス ブートには、**ボリュームの**ボタンを離すと開始します。</span><span class="sxs-lookup"><span data-stu-id="45671-471">After the device begins to boot, release the **Volume Up** button.</span></span>

    5.  <span data-ttu-id="45671-472">**ブート構成**を選択します。</span><span class="sxs-lookup"><span data-stu-id="45671-472">Select **Boot configuration**.</span></span>

    6.  <span data-ttu-id="45671-473">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="45671-473">Do one of the following:</span></span>

        -   <span data-ttu-id="45671-474">**PXE ブート**を選択し、一覧の一番上にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="45671-474">Select **PXE boot**, and drag it to the top of the list.</span></span> <span data-ttu-id="45671-475">代わりに、デバイスをすぐに起動するようにネットワーク アダプターの左を読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="45671-475">Alternatively, you can swipe left on the network adapter to boot to the device immediately.</span></span> <span data-ttu-id="45671-476">これは、起動順序には影響しません。</span><span class="sxs-lookup"><span data-stu-id="45671-476">This won’t affect the boot order.</span></span>
        -   <span data-ttu-id="45671-477">ブート メディアを保持している USB フラッシュ ドライブを選択します。</span><span class="sxs-lookup"><span data-stu-id="45671-477">Select the USB flash drive that holds the boot media.</span></span>

3.  <span data-ttu-id="45671-478">**終了**] を選択し、[**今すぐ再起動**します。</span><span class="sxs-lookup"><span data-stu-id="45671-478">Select **Exit**, and then select **Restart Now**.</span></span>

4.  <span data-ttu-id="45671-479">ダイアログ ボックスが表示されたら、ネットワーク ブート サービスの**入力**を選択します。</span><span class="sxs-lookup"><span data-stu-id="45671-479">When prompted, select **Enter** for network boot service.</span></span>

5.  <span data-ttu-id="45671-480">Windows PE をメモリにロードされ、タスク シーケンス ウィザードが開始されます。</span><span class="sxs-lookup"><span data-stu-id="45671-480">Windows PE will load into memory, and the Task Sequence Wizard will start.</span></span> <span data-ttu-id="45671-481">**次**へを選択します。</span><span class="sxs-lookup"><span data-stu-id="45671-481">Select **Next** to continue.</span></span>

6.  <span data-ttu-id="45671-482">以前では、インポートしたタスク シーケンスを選択し、[**次へ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="45671-482">Select the task sequence that you imported earlier, and then select **Next**.</span></span>

7.  <span data-ttu-id="45671-483">ディスク構成を適用した後、デバイスのコンピューター名を指定するように求めします。</span><span class="sxs-lookup"><span data-stu-id="45671-483">After the disk configuration is applied, you’ll be prompted to specify a computer name for the device.</span></span> <span data-ttu-id="45671-484">Surface Pro デバイスのシリアル番号に基づいて推奨されるコンピューター名は、ユーザー インターフェイスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="45671-484">The user interface will display a recommended computer name based on the serial number of the Surface Pro device.</span></span> <span data-ttu-id="45671-485">提案された名前をそのまま使用するか、新しいパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="45671-485">You can either accept the proposed name or specify a new one.</span></span> <span data-ttu-id="45671-486">コンピューター名の割り当て] 画面の指示に従います。</span><span class="sxs-lookup"><span data-stu-id="45671-486">Follow the instructions on the computer name assignment screen.</span></span> <span data-ttu-id="45671-487">**承諾**を選択すると、展開を開始します。</span><span class="sxs-lookup"><span data-stu-id="45671-487">When you select **Accept**, the deployment begins.</span></span>

8.  <span data-ttu-id="45671-488">展開プロセスの残りの部分は、自動、複数のユーザーの入力を要求しません。</span><span class="sxs-lookup"><span data-stu-id="45671-488">The rest of the deployment process is automatic and doesn’t ask for any more user input.</span></span>

9.  <span data-ttu-id="45671-489">展開タスク シーケンスでは、デバイスの構成が完了すると、チームの会議室をマイクロソフトのアプリケーション設定を構成するように指示する次の構成] 画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="45671-489">After the deployment task sequence finishes configuring the device, you’ll see the following configuration screen that asks you to configure the Microsoft Teams Rooms application settings.</span></span>

    ![マイクロソフト チームの会議室のアプリケーションのセットアップの初期画面](../../media/room-systems-scale-image2.png)

10.  <span data-ttu-id="45671-491">Surface Pro、マイクロソフト チームの会議室のコンソールに接続し、アプリケーションの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="45671-491">Plug the Surface Pro into the Microsoft Teams Rooms console, and configure the application settings.</span></span>

11.  <span data-ttu-id="45671-492">展開済みのデバイスの[Microsoft チームの会議室のヘルプ](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)に記載されている機能が動作しているかを検証します。</span><span class="sxs-lookup"><span data-stu-id="45671-492">Validate that the capabilities listed in [Microsoft Teams Rooms help](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) are working on the deployed device.</span></span>


<span data-ttu-id="45671-493">インストールの失敗をトラブルシューティングするには、 **SMSTS.log**ファイルは、構成マネージャーのタスク シーケンスで実行されるすべての手順をログに記録を確認してください。</span><span class="sxs-lookup"><span data-stu-id="45671-493">To troubleshoot a failed installation, check the **SMSTS.log** file, which logs all the steps executed in a Configuration Manager task sequence.</span></span>

<span data-ttu-id="45671-494">SMSTS.log ファイルは、複数のビルド プロセスの段階に応じて、パスのいずれかに格納されます。</span><span class="sxs-lookup"><span data-stu-id="45671-494">The SMSTS.log file is stored on one of a number of paths, depending on the stage of the build process.</span></span> <span data-ttu-id="45671-495">SMSTS.log ファイルへのパスを識別するのには次の表を確認してください。</span><span class="sxs-lookup"><span data-stu-id="45671-495">Check the following table to identify the path to the SMSTS.log file.</span></span>


| <span data-ttu-id="45671-496">**展開フェーズ**</span><span class="sxs-lookup"><span data-stu-id="45671-496">**Deployment phase**</span></span>                                                            | <span data-ttu-id="45671-497">**タスク シーケンスのログのパス**</span><span class="sxs-lookup"><span data-stu-id="45671-497">**Task sequence log path**</span></span>                         |
|---------------------------------------------------------------------------------|----------------------------------------------------|
| <span data-ttu-id="45671-498">WinPE の HDD をフォーマットする前に、</span><span class="sxs-lookup"><span data-stu-id="45671-498">WinPE, before HDD format</span></span>                                                        | <span data-ttu-id="45671-499">X:\\Windows\\Temp\\smstslog\\smsts.log</span><span class="sxs-lookup"><span data-stu-id="45671-499">X:\\Windows\\Temp\\smstslog\\smsts.log</span></span>             |
| <span data-ttu-id="45671-500">WinPE の HDD のフォーマット後、</span><span class="sxs-lookup"><span data-stu-id="45671-500">WinPE, after HDD format</span></span>                                                         | <span data-ttu-id="45671-501">C:\\_SMSTaskSequence\\ログ\\Smstslog\\smsts.log</span><span class="sxs-lookup"><span data-stu-id="45671-501">C:\\_SMSTaskSequence\\Logs\\Smstslog\\smsts.log</span></span>    |
| <span data-ttu-id="45671-502">オペレーティング システムの展開、構成マネージャー エージェントをインストールする前に、</span><span class="sxs-lookup"><span data-stu-id="45671-502">Operating system deployed, before the Configuration Manager agent was installed</span></span> | <span data-ttu-id="45671-503">c:\\_SMSTaskSequence\\ログ\\Smstslog\\smsts.log</span><span class="sxs-lookup"><span data-stu-id="45671-503">c:\\_SMSTaskSequence\\Logs\\Smstslog\\smsts.log</span></span>    |
| <span data-ttu-id="45671-504">オペレーティング システムと構成マネージャー エージェントを展開</span><span class="sxs-lookup"><span data-stu-id="45671-504">Operating system and the Configuration Manager agent deployed</span></span>                   | <span data-ttu-id="45671-505">%windir%\\System32\\ccm\\ログ\\Smstslog\\smsts.log</span><span class="sxs-lookup"><span data-stu-id="45671-505">%windir%\\System32\\ccm\\logs\\Smstslog\\smsts.log</span></span> |
| <span data-ttu-id="45671-506">タスク シーケンスの実行が完了しました</span><span class="sxs-lookup"><span data-stu-id="45671-506">Task sequence execution complete</span></span>                                                | <span data-ttu-id="45671-507">%windir%\\System32\\ccm\\ログ\\smsts.log</span><span class="sxs-lookup"><span data-stu-id="45671-507">%windir%\\System32\\ccm\\logs\\smsts.log</span></span>           |

> [!TIP]
> <span data-ttu-id="45671-508">開くにはコマンド コンソールでは、タスク シーケンス中に**f8 キー**を選択し、SMSTS.log ファイルへのアクセスを取得できます。</span><span class="sxs-lookup"><span data-stu-id="45671-508">You can select **F8** at any time during the task sequence to open a command console, and then get access to the SMSTS.log file.</span></span>

<span data-ttu-id="45671-509">PXE ブートの問題をトラブルシューティングするには、PXE のアクションに固有の構成マネージャー サーバー上のログの 2 つファイルを確認します。</span><span class="sxs-lookup"><span data-stu-id="45671-509">To troubleshoot PXE boot issues, check the two log files on the Configuration Manager server that are specific to PXE actions:</span></span>

-   <span data-ttu-id="45671-510">**Pxecontrol.log**、構成マネージャーのインストール ・ ログ ・ ディレクトリ内にあります。</span><span class="sxs-lookup"><span data-stu-id="45671-510">**Pxecontrol.log**, located in the Configuration Manager installation logs directory</span></span>

-   <span data-ttu-id="45671-511">**Smspxe.log**、構成マネージャー管理ポイント (MP) のログ ディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="45671-511">**Smspxe.log**, located in Configuration Manager Management Point (MP) logs directory</span></span>

<span data-ttu-id="45671-512">さらに、構成マネージャーのインストールのトラブルシューティングに使用できるログ ファイルの完全なリストは、[システム センター構成マネージャーのログ ファイル](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/log-files)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45671-512">For a complete list of the log files that you can use to further troubleshoot your Configuration Manager installation, see [Log files in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/log-files).</span></span>
