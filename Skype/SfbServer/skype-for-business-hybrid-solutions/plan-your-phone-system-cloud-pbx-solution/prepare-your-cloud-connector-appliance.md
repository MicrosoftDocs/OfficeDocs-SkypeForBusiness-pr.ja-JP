---
title: クラウド コネクタ アプライアンスの準備
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 6eacfa99-9759-4c13-aca3-8992c2ff2710
description: クラウド コネクタ アプライアンスを展開および電話システム (クラウド PBX) で使用するために準備する方法について説明します。
ms.openlocfilehash: 536e9b98520e4274e00d43d57224267f5b824dc9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092635"
---
# <a name="prepare-your-cloud-connector-appliance"></a><span data-ttu-id="7847f-103">クラウド コネクタ アプライアンスの準備</span><span class="sxs-lookup"><span data-stu-id="7847f-103">Prepare your Cloud Connector appliance</span></span>

> [!Important]
> <span data-ttu-id="7847f-104">Cloud Connector Edition は、Skype for Business Online と共に 2021 年 7 月 31 日に廃止されます。</span><span class="sxs-lookup"><span data-stu-id="7847f-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="7847f-105">組織が Teams にアップグレードしたら、直接ルーティングを使用してオンプレミスのテレフォニー ネットワークを Teams に接続する方法 [について説明します](/MicrosoftTeams/direct-routing-landing-page)。</span><span class="sxs-lookup"><span data-stu-id="7847f-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="7847f-106">クラウド コネクタ アプライアンスを展開および電話システム (クラウド PBX) で使用するために準備する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7847f-106">Learn about how to prepare your Cloud Connector appliance for deployment and use with Phone System (Cloud PBX).</span></span>

<span data-ttu-id="7847f-107">このセクションでは、Skype for Business Cloud Connector Edition インストール ファイルを取得し、クラウド コネクタ ソフトウェアをインストールし、クラウド コネクタ アプライアンスを展開用に準備する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7847f-107">This section describes how to get the Skype for Business Cloud Connector Edition installation files, install Cloud Connector software, and prepare your Cloud Connector appliance for deployment.</span></span> <span data-ttu-id="7847f-108">このセクションのすべての手順を完了したら、1 つのサイトまたは複数のサイトに対してクラウド コネクタを展開する準備が整います。</span><span class="sxs-lookup"><span data-stu-id="7847f-108">After you have completed all steps in this section, you will be ready to deploy Cloud Connector for a single site or multiple sites.</span></span> <span data-ttu-id="7847f-109">既存のクラウド コネクタ展開を使用し、まだクラウド コネクタ バージョン 2.1 にアップグレードしていない場合は、「Upgrade to new version of Cloud Connector 」を [参照してください](upgrade-to-a-new-version-of-cloud-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="7847f-109">If you have an existing Cloud Connector deployment, and you have not yet upgraded to Cloud Connector version 2.1, see [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span>

> [!NOTE]
> <span data-ttu-id="7847f-110">Microsoft では、現在のバージョンの Cloud Connector Edition バージョン 2.1 がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="7847f-110">Microsoft supports the current version of Cloud Connector Edition, version 2.1.</span></span> <span data-ttu-id="7847f-111">自動更新を構成した場合、クラウド コネクタは自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="7847f-111">If you configured automatic update, Cloud Connector will update automatically.</span></span> <span data-ttu-id="7847f-112">手動更新プログラムを構成した場合は、リリースから 60 日以内にバージョン 2.1 にアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7847f-112">If you configured manual update, you will need to upgrade to version 2.1 within 60 days of its release.</span></span> <span data-ttu-id="7847f-113">Microsoft は、2.1 のリリース後 60 日間、以前のバージョンをサポートし、アップグレードの時間を提供します。</span><span class="sxs-lookup"><span data-stu-id="7847f-113">Microsoft will support the previous version for 60 days after the release of 2.1 to allow you time to upgrade.</span></span> 

> [!NOTE]
> <span data-ttu-id="7847f-114">Cloud Connector バージョン 2.1 以降の場合、ホスト アプライアンスには 4.6.1 以降.NET Frameworkインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7847f-114">For Cloud Connector version 2.1 and later, the host appliance must have .NET Framework 4.6.1 or later installed.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="7847f-115">展開を成功するには、コマンドレットを実行して Skype for Business Cloud Connector Edition を構成する場合は、常に開始したコンソール セッションと同じコンソール セッションを使用します。</span><span class="sxs-lookup"><span data-stu-id="7847f-115">For successful deployment, when you run the cmdlets to configure Skype for Business Cloud Connector Edition, always use the same console session as the one you started in.</span></span> <span data-ttu-id="7847f-116">展開と構成中に異なるセッションに切り替えるのを避ける。</span><span class="sxs-lookup"><span data-stu-id="7847f-116">Avoid switching to different sessions during the deployment and configuration.</span></span> 

> [!NOTE]
> <span data-ttu-id="7847f-117">展開の最初のアプライアンスに対してのみ実行する手順として、サイト ディレクトリの共有の作成、ビットのダウンロード、Windows Server ISO イメージからの仮想ハード ディスク (VHDX) ファイルの準備があります。</span><span class="sxs-lookup"><span data-stu-id="7847f-117">There are some steps that you perform only for the first appliance in your deployment: creating a share for the site directory, downloading the bits, and preparing a virtual hard disk (VHDX) file from the Windows Server ISO image.</span></span> 

## <a name="download-the-skype-for-business-cloud-connector-edition-installer"></a><span data-ttu-id="7847f-118">Skype for Business Cloud Connector Edition インストーラーをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="7847f-118">Download the Skype for Business Cloud Connector Edition installer</span></span>

1. <span data-ttu-id="7847f-119">クラウド コネクタ VM が実行されるホスト サーバーで、インストール ファイルをダウンロードします [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) 。</span><span class="sxs-lookup"><span data-stu-id="7847f-119">On the host server where the Cloud Connector VMs will run, download the installation files: [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span> 

    > [!IMPORTANT]
    > <span data-ttu-id="7847f-120">追加のファイルはインストール中にダウンロードされますので、クラウド コネクタのインストール中にホスト サーバーがインターネットにアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="7847f-120">The host server must be able to access the Internet during the installation of Cloud Connector because additional files are downloaded during the installation.</span></span> 

2. <span data-ttu-id="7847f-121">インストーラーを実行し、インストール中に既定値を受け入れる。</span><span class="sxs-lookup"><span data-stu-id="7847f-121">Run the installer and accept the default values during the installation.</span></span>

3. <span data-ttu-id="7847f-122">インストールが正常に完了したと確認します。</span><span class="sxs-lookup"><span data-stu-id="7847f-122">Confirm that the installation completed successfully.</span></span>

## <a name="verify-the-installation-and-configure-the-environment"></a><span data-ttu-id="7847f-123">インストールを確認し、環境を構成する</span><span class="sxs-lookup"><span data-stu-id="7847f-123">Verify the installation and configure the environment</span></span>

1. <span data-ttu-id="7847f-124">管理者として PowerShell コンソールを開き、次のコマンドレットを使用して Skype for Business Cloud Connector Edition コマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="7847f-124">Open a PowerShell console as administrator and confirm that the Skype for Business Cloud Connector Edition cmdlets are available using the following cmdlet:</span></span>

   ```powershell
   Get-Command *-Cc*
   ```

    <span data-ttu-id="7847f-125">このコマンドは、Skype for Business Cloud Connector Edition のコマンドレットの一覧を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="7847f-125">The command should return a list of cmdlets for Skype for Business Cloud Connector Edition.</span></span>

2. <span data-ttu-id="7847f-126">VHDs、SfBBits、VersionInfo ファイルはサイト ディレクトリに **格納されます**。</span><span class="sxs-lookup"><span data-stu-id="7847f-126">The VHDs, SfBBits, and VersionInfo files will be stored in the **Site Directory**.</span></span>

    <span data-ttu-id="7847f-127">次のコマンドレットを使用して **、サイト ディレクトリ** の場所を確認できます。</span><span class="sxs-lookup"><span data-stu-id="7847f-127">You can find the location of the **Site Directory** with the following cmdlet:</span></span>

   ```powershell
   Get-CcSiteDirectory
   ```

    <span data-ttu-id="7847f-128">コマンドは、ファイル システム内の場所を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="7847f-128">The command should return a location in your file system.</span></span> <span data-ttu-id="7847f-129">場所には、ローカル フォルダーまたはファイル共有を指定できます。</span><span class="sxs-lookup"><span data-stu-id="7847f-129">The location can be a local folder or a file share.</span></span> <span data-ttu-id="7847f-130">サイト ディレクトリの既定の **場所** は、%USERPROFILE%\CloudConnector\SiteRoot です。</span><span class="sxs-lookup"><span data-stu-id="7847f-130">The default location for the **Site Directory** is: %USERPROFILE%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="7847f-131">既定の場所は、各サイトで作成された最初のアプライアンスのファイル共有に変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7847f-131">The default location should be changed to a file share on the first appliance created in each site.</span></span>

    <span data-ttu-id="7847f-132">選択する場所は次の場所である必要があります。</span><span class="sxs-lookup"><span data-stu-id="7847f-132">The location you select must be:</span></span>

   - <span data-ttu-id="7847f-133">各サイトで作成された最初のアプライアンスで作成されます。</span><span class="sxs-lookup"><span data-stu-id="7847f-133">Created on the first appliance created in each site.</span></span>

   - <span data-ttu-id="7847f-134">同じサイト内の他のホスト サーバー (アプライアンス) がアクセスできる共有フォルダー。</span><span class="sxs-lookup"><span data-stu-id="7847f-134">A shared folder that is accessible by the other host servers (appliances) in the same site.</span></span>

     <span data-ttu-id="7847f-135">サイト ディレクトリを **既定以外** の場所に設定するには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="7847f-135">To set the **Site Directory** to a location other than the default, run the following cmdlet:</span></span>

   ```powershell
   Set-CcSiteDirectory <UNC File path>
   ```

    <span data-ttu-id="7847f-136">サイトに高可用性 (HA) を展開する場合は、コマンドレットを実行してサイト **ディレクトリ** をサイト内の各ホスト サーバー上の同じ場所に設定してください。</span><span class="sxs-lookup"><span data-stu-id="7847f-136">If you are deploying High Availability (HA) for the site, make sure you run the cmdlet to set the **Site Directory** to the same location on each host server within the site.</span></span>

    <span data-ttu-id="7847f-137">サイト内の各アプライアンスにログオンして展開する場合は、現在のログオン アカウントがサイト ディレクトリへの適切なアクセス権を **持っている必要があります**。</span><span class="sxs-lookup"><span data-stu-id="7847f-137">When you log on and deploy each appliance in the site, make sure your current logon account has the right access to the **Site Directory**.</span></span>

3. <span data-ttu-id="7847f-138">アプライアンス **ディレクトリは** 、Skype for Business Cloud Connector Edition のローカル作業ルート ディレクトリであり、外部証明書、インスタンス、ログが保存される場所です。</span><span class="sxs-lookup"><span data-stu-id="7847f-138">The **Appliance Directory** is the local working root directory for Skype for Business Cloud Connector Edition, and the location where external certificates, instances, and logs are saved.</span></span> <span data-ttu-id="7847f-139">既定の場所は%USERPROFILE%\CloudConnector\ApplianceRoot です。</span><span class="sxs-lookup"><span data-stu-id="7847f-139">The default location is: %USERPROFILE%\CloudConnector\ApplianceRoot.</span></span>

    <span data-ttu-id="7847f-140">アプライアンス ディレクトリの場所を見 **つけるには、** 次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="7847f-140">To find the location of the **Appliance Directory**, run the following cmdlet:</span></span>

   ```powershell
   Get-CcApplianceDirectory
   ```

    <span data-ttu-id="7847f-141">アプライアンス ディレクトリを **既定以外** の場所に設定するには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="7847f-141">To set the **Appliance Directory** to a location other than the default, run the following cmdlet:</span></span>

   ```powershell
   Set-CcApplianceDirectory <File path>
   ```

    <span data-ttu-id="7847f-142">アプライアンス ディレクトリは、アプライアンスのローカル フォルダーに設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7847f-142">The Appliance Directory should be set to a local folder on the appliance.</span></span> <span data-ttu-id="7847f-143">Skype for Business  Cloud Connector Edition 展開を開始する前に、アプライアンス ディレクトリのみを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7847f-143">You should only set the **Appliance Directory** before you start the Skype for Business Cloud Connector Edition deployment.</span></span> <span data-ttu-id="7847f-144">展開後に変更する場合は、ホスト サーバーを再展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7847f-144">If you change it after deployment, you'll need to redeploy the host server.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="7847f-145">アプライアンス ディレクトリへの **パスにスペース** を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="7847f-145">The path to the **Appliance Directory** must not contain any spaces.</span></span>

## <a name="set-the-path-for-the-external-edge-certificate"></a><span data-ttu-id="7847f-146">外部エッジ証明書のパスを設定する</span><span class="sxs-lookup"><span data-stu-id="7847f-146">Set the path for the external Edge certificate</span></span>

- <span data-ttu-id="7847f-147">次のコマンドレットを実行して、ファイル名を含むパスを外部エッジ証明書に設定します。</span><span class="sxs-lookup"><span data-stu-id="7847f-147">Run the following cmdlet to set the path, including the file name, to the external Edge certificate.</span></span> <span data-ttu-id="7847f-148">たとえば、C:\certs\cce\ap.contoso.com.pfx。</span><span class="sxs-lookup"><span data-stu-id="7847f-148">For example: C:\certs\cce\ap.contoso.com.pfx.</span></span> <span data-ttu-id="7847f-149">証明書には、プライベート キーが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7847f-149">The certificate must contain private keys.</span></span>

  ```powershell
  Set-CcExternalCertificateFilePath -Path <Full path to External certificate, including file name> -Target EdgeServer
  ```

    > [!NOTE]
    > <span data-ttu-id="7847f-150">-Target パラメーターはバージョン 1.4.2 以降に固有のパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="7847f-150">Note that the -Target parameter is specific to versions 1.4.2 and later.</span></span> 

    <span data-ttu-id="7847f-151">ファイル名を含む外部証明書への完全なパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="7847f-151">Specify the full path to the external certificate, including the file name.</span></span> <span data-ttu-id="7847f-152">証明書は、ローカルまたはファイル共有に保存できます。</span><span class="sxs-lookup"><span data-stu-id="7847f-152">The certificate can be stored locally or on a file share.</span></span> <span data-ttu-id="7847f-153">証明書が共有フォルダーに保存されている場合は、共有フォルダーを各サイトの最初のアプライアンス上に作成し、同じサイトに属する他のアプライアンスからアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="7847f-153">If the certificate is stored in a shared folder, the shared folder must be created on the first appliance of each site and must be accessible by other appliances belonging to the same site.</span></span> <span data-ttu-id="7847f-154">このコマンドレットは、外部証明書をアプライアンス ディレクトリに **コピーします**。</span><span class="sxs-lookup"><span data-stu-id="7847f-154">This cmdlet copies the external certificate to the **Appliance Directory**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="7847f-155">Cloud Connector バージョン **1.4.2** 以降に更新した場合は、準備された外部証明書にプライベート キーと、ルート CA 証明書と中間 CA 証明書を含む完全な証明書チェーンが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7847f-155">**If you have updated to Cloud Connector version 1.4.2 or later**, make sure your prepared external certificate contains private keys and the full certificate chain including the root CA certificate and the intermediate CA certificates.</span></span> <span data-ttu-id="7847f-156">**Cloud Connector バージョン 1.4.2** にまだ更新されていない場合は、準備された外部証明書にプライベート キーが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7847f-156">**If you have NOT yet updated to Cloud Connector version 1.4.2**, make sure your prepared external certificate contains private keys.</span></span> <span data-ttu-id="7847f-157">この外部証明書は、既定で Windows によって信頼されている証明機関によって発行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7847f-157">This external certificate must be issued by a Certificate Authority that is trusted by Windows by default.</span></span>

## <a name="set-the-path-for-the-external-pstn-gatewaysbc-certificate"></a><span data-ttu-id="7847f-158">外部 PSTN ゲートウェイ/SBC 証明書のパスを設定する</span><span class="sxs-lookup"><span data-stu-id="7847f-158">Set the path for the external PSTN gateway/SBC certificate</span></span>

<span data-ttu-id="7847f-159">仲介サーバーと PSTN ゲートウェイ/SBC の間で TLS を使用している場合は、次のコマンドレットを実行して、ファイル名を含むパスをゲートウェイ証明書に設定します。</span><span class="sxs-lookup"><span data-stu-id="7847f-159">If you are using TLS between the Mediation Server and the PSTN gateway/SBC, run the following cmdlet to set the path, including the file name, to the gateway certificate.</span></span> <span data-ttu-id="7847f-160">たとえば、C:\certs\cce\sbc.contoso.com.cer。</span><span class="sxs-lookup"><span data-stu-id="7847f-160">For example: C:\certs\cce\sbc.contoso.com.cer.</span></span> <span data-ttu-id="7847f-161">証明書には、ゲートウェイに割り当てられた証明書のルート CA と中間チェーンが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7847f-161">The certificate must contain the root CA and the intermediate chain for the certificate assigned to the gateway:</span></span>

```powershell
Set-CcExternalCertificateFilePath -Path <Full path to gateway certificate, including file name> -Target MediationServer 
```

> [!NOTE]
> <span data-ttu-id="7847f-162">-Target パラメーターはバージョン 1.4.2 以降に固有のパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="7847f-162">Note that the -Target parameter is specific to versions 1.4.2 and later.</span></span> 

## <a name="create-virtual-switches-in-hyper-v-manager"></a><span data-ttu-id="7847f-163">Hyper-V マネージャーで仮想スイッチを作成する</span><span class="sxs-lookup"><span data-stu-id="7847f-163">Create virtual switches in Hyper-V Manager</span></span>

1. <span data-ttu-id="7847f-164">**Hyper-V Manager 仮想スイッチ**  >  **マネージャーを開き、[** 新しい仮想スイッチ マネージャー **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="7847f-164">Open **Hyper-V Manager** > **Virtual Switch Manager**, and select **New Virtual Switch Manager**.</span></span>

2. <span data-ttu-id="7847f-165">外部仮想スイッチを作成し、内部ネットワーク ドメインに接続されている物理ネットワーク アダプターにバインドします。</span><span class="sxs-lookup"><span data-stu-id="7847f-165">Create an External virtual switch and bind it to the physical network adapter that is connected to your internal network domain:</span></span>

    <span data-ttu-id="7847f-166">[ **この仮想スイッチのこのネットワーク アダプターを共有する管理オペレーティング** システムを許可する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7847f-166">Select **Allow management operating system to share this network adapter** for this virtual switch.</span></span>

3. <span data-ttu-id="7847f-167">外部仮想スイッチを作成し、インターネットにルーティングされる物理ネットワーク アダプターにバインドします。</span><span class="sxs-lookup"><span data-stu-id="7847f-167">Create an External virtual switch and bind it to the physical network adapter that is routed to the Internet:</span></span>

    <span data-ttu-id="7847f-168">[管理オペレーティング **システムでこの仮想スイッチのこのネットワーク アダプターを共有** する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7847f-168">De-select **Allow management operating system to share this network adapter** for this virtual switch.</span></span>

4. <span data-ttu-id="7847f-169">境界ネットワークを内部ネットワーク ドメイン SfB CCE Corpnet Switch に接続するスイッチ **の名前を設定します**。</span><span class="sxs-lookup"><span data-stu-id="7847f-169">Set the name of the switch that connects your perimeter network to your internal network domain **SfB CCE Corpnet Switch**.</span></span>

    <span data-ttu-id="7847f-170">境界ネットワークをインターネット SfB CCE インターネット スイッチに接続するスイッチ **の名前を設定します**。</span><span class="sxs-lookup"><span data-stu-id="7847f-170">Set the name of the switch that connects your perimeter network to the Internet **SfB CCE Internet Switch**.</span></span>

## <a name="update-the-cloudconnectorini-configuration-file"></a><span data-ttu-id="7847f-171">構成ファイルCloudConnector.ini更新する</span><span class="sxs-lookup"><span data-stu-id="7847f-171">Update the CloudConnector.ini configuration file</span></span>

<span data-ttu-id="7847f-172">「Plan for Business [Cloud Connector Edition」](plan-skype-for-business-cloud-connector-edition.md)の[](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams)「展開パラメーターの決定」で収集した情報を使用して、CloudConnector.iniファイルを準備します。</span><span class="sxs-lookup"><span data-stu-id="7847f-172">Prepare the CloudConnector.ini file using the information you gathered in [Determine deployment parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) in the [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) topic.</span></span>

<span data-ttu-id="7847f-173">ファイルを更新するには、まず次のコマンドレットを実行してサンプル テンプレートを取得します (CloudConnector.Sample.ini)。</span><span class="sxs-lookup"><span data-stu-id="7847f-173">To update the file, first run the following cmdlet to get the sample template (CloudConnector.Sample.ini):</span></span>

```powershell
Export-CcConfigurationSampleFile
```

<span data-ttu-id="7847f-174">サンプル テンプレートはアプライアンス ディレクトリに **格納されます**。</span><span class="sxs-lookup"><span data-stu-id="7847f-174">The sample template is stored in the **Appliance Directory**.</span></span>

<span data-ttu-id="7847f-175">環境の値を使用して更新した後、アプライアンス ディレクトリにファイルCloudConnector.iniとして **保存します**。</span><span class="sxs-lookup"><span data-stu-id="7847f-175">After you update it with the values for your environment, save the file as CloudConnector.ini in the **Appliance Directory**.</span></span> <span data-ttu-id="7847f-176">**Get-CcApplianceDirectory を** 実行して、アプライアンス ディレクトリへのパスを **決定できます**。</span><span class="sxs-lookup"><span data-stu-id="7847f-176">You can run **Get-CcApplianceDirectory** to determine the path to the **Appliance Directory**.</span></span>

<span data-ttu-id="7847f-177">.ini ファイルを更新する場合は、次の点を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="7847f-177">When updating the .ini file, consider the following:</span></span>

> [!NOTE]
> <span data-ttu-id="7847f-178">このセクションでは、.ini ファイルのすべての値について説明する必要はありません。ここでは、特別な考慮事項を持つ値についてのみ説明します。</span><span class="sxs-lookup"><span data-stu-id="7847f-178">Not all values for the .ini file are discussed in this section, only those with a special consideration are covered here.</span></span> <span data-ttu-id="7847f-179">完全な一覧については、「Plan [](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) for Skype for Business Cloud Connector Edition」の「展開パラメーターの決定」[セクションを参照](plan-skype-for-business-cloud-connector-edition.md)してください。</span><span class="sxs-lookup"><span data-stu-id="7847f-179">For a full list, see the [Determine deployment parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) section of the [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) topic.</span></span> <span data-ttu-id="7847f-180">追加のアプライアンスまたは新しいサイトに対して変更する必要がある値の詳細については、「Cloud [Connector](deploy-multiple-sites-in-cloud-connector.md)で複数のサイトを展開する」のトピックの「高可用性[(HA)](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site)を備えた単一サイト」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7847f-180">For more information about what values need to be changed for additional appliances or new sites, see [Single site with High Availability (HA) compared to multi-site deployments](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) in the topic [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 

- <span data-ttu-id="7847f-181">**SiteName:** 既定値は **Site1 です**。</span><span class="sxs-lookup"><span data-stu-id="7847f-181">**SiteName:** The default value is **Site1**.</span></span> <span data-ttu-id="7847f-182">**Register-CcAppliance** を実行してアプライアンスを既存または新しいサイトに登録する場合、コマンドレットは **SiteName** を使用して登録するサイトを決定するために、クラウド コネクタを展開する前に更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7847f-182">You must update it before you deploy Cloud Connector, because when you run **Register-CcAppliance** to register an appliance to an existing or new site, the cmdlet will use **SiteName** to determine which site to register.</span></span>

     <span data-ttu-id="7847f-183">アプライアンスを新しいサイトに登録する場合 **、SiteName** の値は一意で、既存のサイトとは異なる値である必要があります。</span><span class="sxs-lookup"><span data-stu-id="7847f-183">If you want to register the appliance to a new site, the value of **SiteName** must be unique and different from existing sites.</span></span> <span data-ttu-id="7847f-184">アプライアンスを既存のサイトに登録する場合は **、.ini** ファイルの SiteName の値が、Microsoft 365 または Office 365 組織構成で定義されている名前と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="7847f-184">If you want to register the appliance to an existing site, the value for **SiteName** in .ini file must match the name defined in your Microsoft 365 or Office 365 organization configuration.</span></span> <span data-ttu-id="7847f-185">あるサイトから別のサイトに構成ファイルをコピーする場合は、必ずサイトごとに **SiteName** の値を更新してください。</span><span class="sxs-lookup"><span data-stu-id="7847f-185">If you are copying a configuration file from one site to another, make sure you update the value for **SiteName** for each site accordingly.</span></span>

- <span data-ttu-id="7847f-186">**ServerName:** サーバー名にはドメイン名を含めず、15 文字に制限する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7847f-186">**ServerName:** The server name should not contain the domain name and should be limited to 15 characters.</span></span>

- <span data-ttu-id="7847f-187">**HardwareType:** 値を null に設定または残しておかなかった場合は、既定値 **の Normal が** 使用されます。</span><span class="sxs-lookup"><span data-stu-id="7847f-187">**HardwareType:** If you don't set or leave the value to null, the default value of **Normal** will be used.</span></span> <span data-ttu-id="7847f-188">「Plan [for Skype for Business Cloud Connector Edition」](plan-skype-for-business-cloud-connector-edition.md)の説明に従って、ホスト コンピューターごとに 500 の同時呼び出しをサポートするために、より大きなバージョンのクラウド コネクタを展開する予定の場合は、標準を使用します。 </span><span class="sxs-lookup"><span data-stu-id="7847f-188">Use **Normal** if you plan to deploy the larger version of Cloud Connector to support 500 simultaneous calls per host machine as described in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span> <span data-ttu-id="7847f-189">50 **回** の同時呼び出しをサポートする小規模な展開には、Minimum を使用します。</span><span class="sxs-lookup"><span data-stu-id="7847f-189">Use **Minimum** for a smaller deployment that supports 50 simultaneous calls.</span></span>

- <span data-ttu-id="7847f-190">**Internet/Corpnet/Management 仮想スイッチ:** 作成した仮想スイッチの名前を追加します。</span><span class="sxs-lookup"><span data-stu-id="7847f-190">**Internet/Corpnet/Management virtual switches:**: Add the name of the virtual switches you have created.</span></span> <span data-ttu-id="7847f-191">管理仮想スイッチの場合は、既定値のままにします。</span><span class="sxs-lookup"><span data-stu-id="7847f-191">For the management virtual switch, leave the default value.</span></span> <span data-ttu-id="7847f-192">展開スクリプトは、展開の開始時に管理仮想スイッチを作成し、展開が完了すると削除します。</span><span class="sxs-lookup"><span data-stu-id="7847f-192">The deployment script will create the management virtual switch at the beginning of deployment and delete it when the deployment finishes.</span></span>

- <span data-ttu-id="7847f-193">**ManagementIPPrefix:** [ネットワーク] セクションの ManagementIPPrefix は、他の内部 IP とは異なるサブネットである必要があります。</span><span class="sxs-lookup"><span data-stu-id="7847f-193">**ManagementIPPrefix:** ManagementIPPrefix in the Network section must be a different subnet from other internal IPs.</span></span> <span data-ttu-id="7847f-194">たとえば、既定値が示すように、ManagementIPPrefix は 192.168.213.0、AD IPAddress は 192.168.0.238 です。</span><span class="sxs-lookup"><span data-stu-id="7847f-194">For example, as the default value shows, ManagementIPPrefix is 192.168.213.0, while AD IPAddress is 192.168.0.238.</span></span>

    <span data-ttu-id="7847f-195">展開スクリプトは、各仮想マシンに管理ネットワーク アダプターを作成し、管理 IP を割り当て、管理仮想スイッチに接続します。</span><span class="sxs-lookup"><span data-stu-id="7847f-195">The deployment scripts create a management network adapter on each virtual machine, assign a management IP, and connect it to a management virtual switch.</span></span> <span data-ttu-id="7847f-196">これにより、ホスト サーバーは、この管理ネットワークを介して各仮想マシンに接続して管理できます。</span><span class="sxs-lookup"><span data-stu-id="7847f-196">This enables the host server to connect to and manage each virtual machine via this management network.</span></span> <span data-ttu-id="7847f-197">展開が完了すると、管理仮想スイッチが削除されます。</span><span class="sxs-lookup"><span data-stu-id="7847f-197">The management virtual switch is deleted when the deployment is finished.</span></span>

- <span data-ttu-id="7847f-198">**基本 VM 固有の構成:** このセクションの設定は **、Convert-CcIsoToVhdx コマンドレット用に構成する必要** があります。</span><span class="sxs-lookup"><span data-stu-id="7847f-198">**Base VM specific configurations:** Settings in this section must be configured for the **Convert-CcIsoToVhdx** cmdlet.</span></span>

    <span data-ttu-id="7847f-199">基本 VM イメージの準備中に、基本 VM は内部ネットワーク スイッチに接続されます。</span><span class="sxs-lookup"><span data-stu-id="7847f-199">During base VM image preparation, the base VM will be connected to the internal network switch.</span></span> <span data-ttu-id="7847f-200">VM がインターネットにアクセスするには、次の設定が重要です。</span><span class="sxs-lookup"><span data-stu-id="7847f-200">The following settings are critical for the VM to be able to access the Internet:</span></span>

  - <span data-ttu-id="7847f-201">[共通]BaseVMIP: 基本 VM に割り当てる corpnet IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="7847f-201">[Common]BaseVMIP: the corpnet IP address to be assigned to the base VM.</span></span>

  - <span data-ttu-id="7847f-202">[ネットワーク]CorpnetDefaultGateway: 基本 VM に割り当てられる既定のゲートウェイ。</span><span class="sxs-lookup"><span data-stu-id="7847f-202">[Network]CorpnetDefaultGateway: the default gateway to be assigned to the base VM.</span></span>

  - <span data-ttu-id="7847f-203">[ネットワーク]CorpnetDNSIPAddress: ベース VM に割り当てる DNS IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="7847f-203">[Network]CorpnetDNSIPAddress: the DNS IP address to be assigned to the base VM.</span></span>

  - <span data-ttu-id="7847f-204">[ネットワーク]WSUSServer: Windows Server Update Service の IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="7847f-204">[Network]WSUSServer: the IP address of Windows Server Update Service.</span></span>

  - <span data-ttu-id="7847f-205">[ネットワーク]WSUSStatusServer: Windows Server Update Service 状態サーバーの IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="7847f-205">[Network]WSUSStatusServer: the IP address of Windows Server Update Service status server.</span></span>

  - <span data-ttu-id="7847f-206">[ネットワーク]EnableReferSupport: これは、IP/PBX のトランク構成で SIP REFER のサポートが有効か無効かを定義します。</span><span class="sxs-lookup"><span data-stu-id="7847f-206">[Network]EnableReferSupport: this will define whether SIP REFER support is enabled or disabled on the Trunk Configuration to your IP/PBX.</span></span>

- <span data-ttu-id="7847f-207">**内部の IPs:**</span><span class="sxs-lookup"><span data-stu-id="7847f-207">**Internal IPs:**</span></span>

  - <span data-ttu-id="7847f-208">サブネット マスク CorpnetIPPrefixLength が正しいか確認します。</span><span class="sxs-lookup"><span data-stu-id="7847f-208">Make sure subnet mask CorpnetIPPrefixLength is correct.</span></span>

  - <span data-ttu-id="7847f-209">これらの内部 IP に対して IP の競合が発生しなかご確認ください。</span><span class="sxs-lookup"><span data-stu-id="7847f-209">Make sure there are no IP conflicts for these internal IPs.</span></span>

- <span data-ttu-id="7847f-210">**外部 AP:**</span><span class="sxs-lookup"><span data-stu-id="7847f-210">**External IPs:**</span></span>

  - <span data-ttu-id="7847f-211">MR パブリック IP の場合: NAT 以外の場合は ExternalMRIP、NAT の場合は ExternalMRPublicIP を指定します。</span><span class="sxs-lookup"><span data-stu-id="7847f-211">For MR public IP: specify either ExternalMRIPs for non-NAT or ExternalMRPublicIPs for NAT.</span></span>

  - <span data-ttu-id="7847f-212">ExternalSIPIPs と ExternalMRIP は同じにできます。</span><span class="sxs-lookup"><span data-stu-id="7847f-212">ExternalSIPIPs and ExternalMRIPs can be the same.</span></span>

  - <span data-ttu-id="7847f-213">サブネット マスク InternetIPPrefixLength が正しいか確認します。</span><span class="sxs-lookup"><span data-stu-id="7847f-213">Make sure subnet mask InternetIPPrefixLength is correct.</span></span>

  - <span data-ttu-id="7847f-214">これらの外部 IP に対して IP 競合が発生しなかからなか確認してください。</span><span class="sxs-lookup"><span data-stu-id="7847f-214">Make sure there are no IP conflicts for these external IPs.</span></span>

- <span data-ttu-id="7847f-215">**ゲートウェイ:**</span><span class="sxs-lookup"><span data-stu-id="7847f-215">**Gateways:**</span></span>

  - <span data-ttu-id="7847f-216">ゲートウェイが 1 つのみである場合は、セカンダリ ゲートウェイのセクションを削除します。</span><span class="sxs-lookup"><span data-stu-id="7847f-216">If you have only one gateway, remove the section for the secondary gateway.</span></span> <span data-ttu-id="7847f-217">2 つ以上のゲートウェイがある場合は、既存のゲートウェイをコピーして貼り付け、更新することで、追加のセクションを作成します。</span><span class="sxs-lookup"><span data-stu-id="7847f-217">If you have more than two gateways, create additional sections by copying and pasting the existing one and then updating it.</span></span>

  - <span data-ttu-id="7847f-218">ゲートウェイの IP アドレスとポートが正しいか確認します。</span><span class="sxs-lookup"><span data-stu-id="7847f-218">Make sure that the IP address and port of the gateway(s) are correct.</span></span>

  - <span data-ttu-id="7847f-219">PSTN ゲートウェイ レベルの HA をサポートするには、セカンダリ ゲートウェイを離れ、使用する追加のゲートウェイを追加します。</span><span class="sxs-lookup"><span data-stu-id="7847f-219">To support PSTN gateway level HA, leave the secondary gateway, and add any additional gateways you will use.</span></span> <span data-ttu-id="7847f-220">既存のエントリをコピーして貼り付け、更新できます。</span><span class="sxs-lookup"><span data-stu-id="7847f-220">You can copy and paste an existing entry and then update it.</span></span>

- <span data-ttu-id="7847f-221">必要に応じて、LocalRoute 値を更新して発信通話番号を制限できます。</span><span class="sxs-lookup"><span data-stu-id="7847f-221">Optionally, you can update the LocalRoute value to restrict outbound call numbers.</span></span>

## <a name="download-the-bits-to-the-site-directory"></a><span data-ttu-id="7847f-222">サイト ディレクトリにビットをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="7847f-222">Download the bits to the Site Directory</span></span>

<span data-ttu-id="7847f-223">次のコマンドレットを実行して、ビットおよびバージョン情報ファイルをサイト ディレクトリに **ダウンロードします**。</span><span class="sxs-lookup"><span data-stu-id="7847f-223">Run the following cmdlet to download the bits and version information files to the **Site Directory**:</span></span>

```powershell
Start-CcDownload
```

> [!NOTE]
> <span data-ttu-id="7847f-224">この手順は、最初のアプライアンスでのみ実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7847f-224">You need to perform this step for the first appliance only.</span></span> 

## <a name="prepare-base-virtual-disk-vhdx-from-the-downloaded-iso-file"></a><span data-ttu-id="7847f-225">ダウンロードした ISO ファイルから基本仮想ディスク (VHDX) を準備する</span><span class="sxs-lookup"><span data-stu-id="7847f-225">Prepare base virtual disk (VHDX) from the downloaded ISO file</span></span>

<span data-ttu-id="7847f-226">この手順では、ISO イメージから仮想ハード ディスク (VHDX) Windows Server 2012準備します。</span><span class="sxs-lookup"><span data-stu-id="7847f-226">This step prepares a virtual hard disk (VHDX) file from the Windows Server 2012 ISO image.</span></span> <span data-ttu-id="7847f-227">VHDX は、展開中に仮想マシンを作成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="7847f-227">The VHDX will be used to create virtual machines during deployment.</span></span> <span data-ttu-id="7847f-228">一時的な仮想マシン (基本 VM) が作成されWindows Server 2012 ISO ファイルからインストールされます。</span><span class="sxs-lookup"><span data-stu-id="7847f-228">A temporary virtual machine (base VM) will be created and Windows Server 2012 will be installed from the ISO file.</span></span> <span data-ttu-id="7847f-229">VM が作成されると、必要なコンポーネントがインストールされ、最新の Windows 更新プログラムが適用されます。</span><span class="sxs-lookup"><span data-stu-id="7847f-229">After the VM is created, some necessary components will be installed and the latest Windows update will be applied.</span></span> <span data-ttu-id="7847f-230">最後に、基本 VM は一般化 (sysprep) され、クリーンアップされ、生成された仮想ディスク ファイルだけが残されます。</span><span class="sxs-lookup"><span data-stu-id="7847f-230">At the end, the base VM will be generalized (sysprep) and cleaned up, leaving only the generated virtual disk file.</span></span>

> [!NOTE]
> <span data-ttu-id="7847f-231">この手順は、最初のアプライアンスでのみ実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7847f-231">You need to perform this step for the first appliance only.</span></span> 

<span data-ttu-id="7847f-232">この手順に進む前に、corpnet スイッチが作成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7847f-232">Before proceeding with this step, make sure that the corpnet switch is created.</span></span> <span data-ttu-id="7847f-233">また、次の設定がファイルファイルで正しく構成CloudConnector.iniします。</span><span class="sxs-lookup"><span data-stu-id="7847f-233">Also, confirm that the following settings are correctly configured in the CloudConnector.ini file:</span></span>

- <span data-ttu-id="7847f-234">[ネットワーク]CorpnetSwitchName</span><span class="sxs-lookup"><span data-stu-id="7847f-234">[Network]CorpnetSwitchName</span></span>

- <span data-ttu-id="7847f-235">[共通]BaseVMIP</span><span class="sxs-lookup"><span data-stu-id="7847f-235">[Common]BaseVMIP</span></span>

- <span data-ttu-id="7847f-236">[ネットワーク]CorpnetIPPrefixLength</span><span class="sxs-lookup"><span data-stu-id="7847f-236">[Network]CorpnetIPPrefixLength</span></span>

- <span data-ttu-id="7847f-237">[ネットワーク]CorpnetDefaultGateway</span><span class="sxs-lookup"><span data-stu-id="7847f-237">[Network]CorpnetDefaultGateway</span></span>

- <span data-ttu-id="7847f-238">[ネットワーク]CorpnetDNSIPAddress</span><span class="sxs-lookup"><span data-stu-id="7847f-238">[Network]CorpnetDNSIPAddress</span></span>

<span data-ttu-id="7847f-239">管理者として PowerShell コンソールを起動し、次のコマンドレットを実行して、ISO イメージを仮想ハード ディスク (VHD) に変換します。</span><span class="sxs-lookup"><span data-stu-id="7847f-239">Start a PowerShell console as administrator and run the following cmdlet to convert the ISO image to a virtual hard disk (VHD):</span></span>

```powershell
Convert-CcIsoToVhdx -IsoFilePath <Windows ISO File Path, including file name>
```

<span data-ttu-id="7847f-240">ISO イメージへの完全なパス (ファイル名を含む) を指定します。</span><span class="sxs-lookup"><span data-stu-id="7847f-240">Specify the full path, including file name, to the ISO image.</span></span> <span data-ttu-id="7847f-241">たとえば、C:\ISO\WindowsServer2012R2.iso。</span><span class="sxs-lookup"><span data-stu-id="7847f-241">For example: C:\ISO\WindowsServer2012R2.iso.</span></span>

<span data-ttu-id="7847f-242">作成された VHD ファイルは、サイト ディレクトリ **\Bits\VHD** フォルダーに格納されます。</span><span class="sxs-lookup"><span data-stu-id="7847f-242">The created VHD file is stored in the **Site Directory** \Bits\VHD folder.</span></span> <span data-ttu-id="7847f-243">**Get-CcSiteDirectory** を実行すると、サイト ディレクトリへのパスを取得できます。</span><span class="sxs-lookup"><span data-stu-id="7847f-243">You can get the path to the **Site Directory** by running the **Get-CcSiteDirectory**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7847f-244">既定では、プロキシ設定は基本 VM で構成されていません。</span><span class="sxs-lookup"><span data-stu-id="7847f-244">By default, proxy settings are not configured on the base VM.</span></span> <span data-ttu-id="7847f-245">Windows Update 経由で VM を更新するためにネットワーク環境でプロキシが必要な場合は、"Convert-CcIsoToVhdx" を実行するときに -PauseBeforeUpdate スイッチを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7847f-245">If a proxy is required in your network environment to update the VM via Windows Update, you should add the -PauseBeforeUpdate switch when you run "Convert-CcIsoToVhdx".</span></span> <span data-ttu-id="7847f-246">スクリプトは Windows Update の前に一時停止し、VM で手動でプロキシを設定する機会があります。</span><span class="sxs-lookup"><span data-stu-id="7847f-246">The script will pause before Windows Update and you'll have a chance to manually set up proxy on the VM.</span></span> <span data-ttu-id="7847f-247">プロキシがセットアップされ、VM がインターネットにアクセスしたら、スクリプトを再開して残りの手順を完了できます。</span><span class="sxs-lookup"><span data-stu-id="7847f-247">After the proxy is setup and the VM can access Internet, you can resume the script to complete the remaining steps.</span></span> 

### <a name="create-vhds-for-a-multi-site-deployment"></a><span data-ttu-id="7847f-248">複数サイト展開の VHD を作成する</span><span class="sxs-lookup"><span data-stu-id="7847f-248">Create VHDs for a multi-site deployment</span></span>

<span data-ttu-id="7847f-249">これは、複数サイト展開にのみ適用されるオプションの手順です。</span><span class="sxs-lookup"><span data-stu-id="7847f-249">This is an optional step that applies only to multi-site deployments.</span></span>

<span data-ttu-id="7847f-250">複数サイト展開を展開する場合は、サイトごとに ISO を VHD に変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7847f-250">If you are deploying a multi-site deployment, you do not need to convert the ISO to a VHD for each site.</span></span> <span data-ttu-id="7847f-251">最初のサイト用に作成された VHDX を、2 番目のサイトのホスト サーバーにコピーできます。</span><span class="sxs-lookup"><span data-stu-id="7847f-251">You can copy the VHDX created for the first site to the host server for a second site.</span></span>

 <span data-ttu-id="7847f-252">追加サイトのホスト サーバー上で、同じファイルの場所 **(Site Directory** \Bits\VHD フォルダー) と同じファイル名でファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="7847f-252">Copy the file to the same file location ( **Site Directory** \Bits\VHD folder), and with the same file name, on the host server for an additional site.</span></span>

## <a name="set-the-powershell-execution-policy-to-remotesigned"></a><span data-ttu-id="7847f-253">PowerShell 実行ポリシーを RemoteSigned に設定する</span><span class="sxs-lookup"><span data-stu-id="7847f-253">Set the PowerShell Execution policy to RemoteSigned</span></span>

<span data-ttu-id="7847f-254">指定された PowerShell スクリプトでは、実行ポリシーを RemoteSigned に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7847f-254">The PowerShell scripts provided require that the execution policy be set to RemoteSigned.</span></span> <span data-ttu-id="7847f-255">現在の設定を表示するには、管理者として PowerShell コンソールを開き、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="7847f-255">To see the current setting, open a PowerShell console as administrator and then run the following cmdlet:</span></span>

```powershell
Get-ExecutionPolicy
```

<span data-ttu-id="7847f-256">"RemoteSigned" に設定されていない場合は、次のコマンドレットを実行して変更します。</span><span class="sxs-lookup"><span data-stu-id="7847f-256">If it is not set to "RemoteSigned," run the following cmdlet to change it:</span></span>

```powershell
Set-ExecutionPolicy RemoteSigned
```

## <a name="change-local-group-policy-on-the-host-machine-versions-141-and-earlier"></a><span data-ttu-id="7847f-257">ホスト コンピューターのローカル グループ ポリシーの変更 (バージョン 1.4.1 以前)</span><span class="sxs-lookup"><span data-stu-id="7847f-257">Change local Group Policy on the host machine (versions 1.4.1 and earlier)</span></span>

> [!NOTE]
> <span data-ttu-id="7847f-258">このタスクは、Cloud Connector バージョン 1.4.2 以降では必要ありません。</span><span class="sxs-lookup"><span data-stu-id="7847f-258">This task is not required for Cloud Connector versions 1.4.2 and later.</span></span> 

<span data-ttu-id="7847f-259">CceService アカウントは、Skype for Business Cloud Connector Edition の展開中に作成されます。</span><span class="sxs-lookup"><span data-stu-id="7847f-259">The CceService account is created during the Skype for Business Cloud Connector Edition deployment.</span></span> <span data-ttu-id="7847f-260">クラウド コネクタ管理サービスを実行し、クラウド コネクタ管理サービスをアンインストールするためのアクセス許可がcloudconnector.msi。</span><span class="sxs-lookup"><span data-stu-id="7847f-260">It runs the Cloud Connector Management Service and requires permission to uninstall the cloudconnector.msi.</span></span> <span data-ttu-id="7847f-261">Cloud Connector ホスト コンピューターのグループ ポリシー設定を変更して、ユーザーがログオフするときにユーザー レジストリをアンロードしなけれと指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7847f-261">You must change the group policy setting on the Cloud Connector host machine to specify that the user registry should not be unloaded when the user logs off.</span></span> <span data-ttu-id="7847f-262">以下の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="7847f-262">Follow the steps below:</span></span>

### <a name="to-change-the-group-policy-setting"></a><span data-ttu-id="7847f-263">グループ ポリシー設定を変更するには</span><span class="sxs-lookup"><span data-stu-id="7847f-263">To change the Group Policy setting</span></span>

1. <span data-ttu-id="7847f-264">gpedit.msc **を実行して** グループ ポリシー エディターを開きます。</span><span class="sxs-lookup"><span data-stu-id="7847f-264">Open the **Group Policy Editor** by running gpedit.msc.</span></span>

2. <span data-ttu-id="7847f-265">グループ ポリシー **エディター** で、[管理用テンプレート] > System > UserProfile > [ユーザー ログオフ時にユーザー レジストリを強制的にアンロードしない] に移動します。</span><span class="sxs-lookup"><span data-stu-id="7847f-265">In the **Group Policy Editor**, navigate to Administrative Templates > System > UserProfile > Do not forcefully unload the user registry at user logoff.</span></span> 

3. <span data-ttu-id="7847f-266">値を [有効] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="7847f-266">Set its value to **Enabled**.</span></span>

## <a name="set-up-your-microsoft-365-or-office-365-organization"></a><span data-ttu-id="7847f-267">Microsoft 365 または 365 Officeをセットアップする</span><span class="sxs-lookup"><span data-stu-id="7847f-267">Set up your Microsoft 365 or Office 365 organization</span></span>

<span data-ttu-id="7847f-268">Skype for Business Online および電話システムOffice Microsoft 365 または 365 組織が必要です。</span><span class="sxs-lookup"><span data-stu-id="7847f-268">A Microsoft 365 or Office 365 organization with Skype for Business Online and Phone System is required.</span></span> <span data-ttu-id="7847f-269">クラウド コネクタを使用する前に、テナントがセットアップおよび構成されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="7847f-269">Make sure your tenant is set up and configured before attempting to use Cloud Connector.</span></span>

<span data-ttu-id="7847f-270">一部の Microsoft 365 および Office 365 セットアップ手順では、テナント リモート PowerShell (TRPS) を使用して Microsoft 365 または 365 組織Officeする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7847f-270">Some Microsoft 365 and Office 365 setup steps require you to use Tenant Remote PowerShell (TRPS) to configure your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="7847f-271">**これはホスト サーバーにインストールする必要があります。**</span><span class="sxs-lookup"><span data-stu-id="7847f-271">**This should be installed on the host server.**</span></span> <span data-ttu-id="7847f-272">PowerShell 用の Skype for Business Online モジュールは [、Skype for Business Online、skype for Business Online、](https://www.microsoft.com/download/details.aspx?id=39366)および Windows PowerShellダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="7847f-272">You can download the Skype for Business Online module for PowerShell from: [Skype for Business Online, Windows PowerShell Module](https://www.microsoft.com/download/details.aspx?id=39366).</span></span>

<span data-ttu-id="7847f-273">CceOnlineManagmentAdministrator など、クラウド コネクタ のオンライン管理用の専用の Skype for Business 管理者アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="7847f-273">Create a dedicated Skype for Business administrator account for Cloud Connector online management, for example CceOnlineManagmentAdministrator.</span></span> <span data-ttu-id="7847f-274">このアカウントは、アプライアンスを追加または削除したり、自動 OS 更新を有効または無効にしたり、自動バイナリ更新を有効または無効にしたりするためにアプライアンスによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="7847f-274">This account will be used by appliance to add or remove appliance, enable or disable automatic OS update, enable or disable automatic binary update.</span></span> <span data-ttu-id="7847f-275">このアカウントのパスワードを有効期限が切れることはありませんので、有効期限が切れる度にサービスのパスワードを変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="7847f-275">Set the password for this account to never expire so that you do not need to change it for the service each time it expires.</span></span>