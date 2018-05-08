---
title: Cloud Connector アプライアンスの準備
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 6eacfa99-9759-4c13-aca3-8992c2ff2710
description: Office 365 の電話システム (クラウド PBX) とともに展開および使用するために Cloud Connector アプライアンスを準備する方法について説明します。
ms.openlocfilehash: 130d593ba94eff9da163363a652bc389b713d1b0
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="prepare-your-cloud-connector-appliance"></a><span data-ttu-id="3812d-103">Cloud Connector アプライアンスの準備</span><span class="sxs-lookup"><span data-stu-id="3812d-103">Prepare your Cloud Connector appliance</span></span>
 
<span data-ttu-id="3812d-104">Office 365 の電話システム (クラウド PBX) とともに展開および使用するために Cloud Connector アプライアンスを準備する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3812d-104">Learn about how to prepare your Cloud Connector appliance for deployment and use with Phone System in Office 365 (Cloud PBX).</span></span>
  
<span data-ttu-id="3812d-105">このセクションでは、Skype for Business Cloud Connector エディションのインストール ファイルの取得、Cloud Connector ソフトウェアのインストール、展開に向けた Cloud Connector アプライアンスの準備を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3812d-105">This section describes how to get the Skype for Business Cloud Connector Edition installation files, install Cloud Connector software, and prepare your Cloud Connector appliance for deployment.</span></span> <span data-ttu-id="3812d-106">このセクションに示す手順を完了すれば、Cloud Connector を単一または複数のサイトに展開する準備が整います。</span><span class="sxs-lookup"><span data-stu-id="3812d-106">After you have completed all steps in this section, you will be ready to deploy Cloud Connector for a single site or multiple sites.</span></span> <span data-ttu-id="3812d-107">既存のコネクタのクラウド展開があり、まだクラウド コネクタ バージョン 2.1 にアップグレードしていない場合は、[クラウドのコネクタを新しいバージョンにアップグレード](upgrade-to-a-new-version-of-cloud-connector.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3812d-107">If you have an existing Cloud Connector deployment, and you have not yet upgraded to Cloud Connector version 2.1, see [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="3812d-108">Microsoft は、Cloud Connector Edition の現在のバージョンであるバージョン 2.1 をサポートします。</span><span class="sxs-lookup"><span data-stu-id="3812d-108">Microsoft supports the current version of Cloud Connector Edition, version 2.1.</span></span> <span data-ttu-id="3812d-109">自動更新を構成している場合、Cloud Connector は自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="3812d-109">If you configured automatic update, Cloud Connector will update automatically.</span></span> <span data-ttu-id="3812d-110">手動更新を構成している場合、リリース後 60日以内にバージョン 2.1 に更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3812d-110">If you configured manual update, you will need to upgrade to version 2.1 within 60 days of its release.</span></span> <span data-ttu-id="3812d-111">Microsoft は、ユーザーによる更新期間を確保するため、2.1 のリリース後 60 日間において以前のバージョンをサポートします。</span><span class="sxs-lookup"><span data-stu-id="3812d-111">Microsoft will support the previous version for 60 days after the release of 2.1 to allow you time to upgrade.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="3812d-112">Cloud Connector のバージョン 2.1 以降の場合、ホスト アプライアンスで .NET Framework 4.6.1 以降がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3812d-112">For Cloud Connector version 2.1 and later, the host appliance must have .NET Framework 4.6.1 or later installed.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="3812d-113">展開を成功させるには、ビジネス クラウド コネクタ ・ エディションの Skype を構成するのには、コマンドレットを実行すると常に同じコンソール セッションを使用で起動するものとします。</span><span class="sxs-lookup"><span data-stu-id="3812d-113">For successful deployment, when you run the cmdlets to configure Skype for Business Cloud Connector Edition, always use the same console session as the one you started in.</span></span> <span data-ttu-id="3812d-114">展開中と設定中に、別のセッションに切り替えないでください。</span><span class="sxs-lookup"><span data-stu-id="3812d-114">Avoid switching to different sessions during the deployment and configuration.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="3812d-115">展開における最初のアプライアンスのみに対して実行する手順として、サイト ディレクトリの共有の作成、ビットのダウンロード、Windows Server ISO イメージからの仮想ハードディスク (VHDX) ファイルの準備があります。</span><span class="sxs-lookup"><span data-stu-id="3812d-115">There are some steps that you perform only for the first appliance in your deployment: creating a share for the site directory, downloading the bits, and preparing a virtual hard disk (VHDX) file from the Windows Server ISO image.</span></span> 
  
## <a name="download-the-skype-for-business-cloud-connector-edition-installer"></a><span data-ttu-id="3812d-116">Skype for Business Cloud Connector Edition インストーラのダウンロード</span><span class="sxs-lookup"><span data-stu-id="3812d-116">Download the Skype for Business Cloud Connector Edition installer</span></span>

1. <span data-ttu-id="3812d-117">クラウド コネクタの Vm を実行するホスト サーバーにインストール ファイルをダウンロードします: [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller)。</span><span class="sxs-lookup"><span data-stu-id="3812d-117">On the host server where the Cloud Connector VMs will run, download the installation files: [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="3812d-118">Cloud Connector のインストール中に新たなファイルがダウンロードされるので、インストール中はホスト サーバーからインターネットにアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="3812d-118">The host server must be able to access the Internet during the installation of Cloud Connector because additional files are downloaded during the installation.</span></span> 
  
2. <span data-ttu-id="3812d-119">インストーラを実行し、インストール中にデフォルト値を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="3812d-119">Run the installer and accept the default values during the installation.</span></span>
    
3. <span data-ttu-id="3812d-120">インストールが正常に完了したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="3812d-120">Confirm that the installation completed successfully.</span></span>
    
## <a name="verify-the-installation-and-configure-the-environment"></a><span data-ttu-id="3812d-121">インストールの検証と環境の設定</span><span class="sxs-lookup"><span data-stu-id="3812d-121">Verify the installation and configure the environment</span></span>

1. <span data-ttu-id="3812d-122">管理者として PowerShell コンソールを開き、ビジネス クラウド コネクタ ・ エディションのコマンドレットの Skype が次のコマンドレットを使用して利用可能であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3812d-122">Open a PowerShell console as administrator and confirm that the Skype for Business Cloud Connector Edition cmdlets are available using the following cmdlet:</span></span>
    
  ```
  Get-Command *-Cc*
  ```

    <span data-ttu-id="3812d-123">コマンドは、ビジネスのクラウド コネクタのエディションの Skype のコマンドレットの一覧を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="3812d-123">The command should return a list of cmdlets for Skype for Business Cloud Connector Edition.</span></span>
    
2. <span data-ttu-id="3812d-124">VHD ファイル、SfBBITS ファイル、VersionInfo ファイルが**サイト ディレクトリ**に格納されます。</span><span class="sxs-lookup"><span data-stu-id="3812d-124">The VHDs, SfBBits, and VersionInfo files will be stored in the **Site Directory**.</span></span>
    
    <span data-ttu-id="3812d-125">次のコマンドレットで**サイト ディレクトリ**の場所を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="3812d-125">You can find the location of the **Site Directory** with the following cmdlet:</span></span>
    
  ```
  Get-CcSiteDirectory
  ```

    <span data-ttu-id="3812d-126">コマンドによってファイル システム内の場所が返されます。</span><span class="sxs-lookup"><span data-stu-id="3812d-126">The command should return a location in your file system.</span></span> <span data-ttu-id="3812d-127">この場所にはローカルのフォルダーまたはファイル共有が該当します。</span><span class="sxs-lookup"><span data-stu-id="3812d-127">The location can be a local folder or a file share.</span></span> <span data-ttu-id="3812d-128">**サイト ディレクトリ**のデフォルトの場所は、%USERPROFILE%\CloudConnector\SiteRoot です。</span><span class="sxs-lookup"><span data-stu-id="3812d-128">The default location for the **Site Directory** is: %USERPROFILE%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="3812d-129">デフォルトの場所は、サイトごとに作成された最初のアプライアンス上のファイル共有に変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3812d-129">The default location should be changed to a file share on the first appliance created in each site.</span></span>
    
    <span data-ttu-id="3812d-130">選択する場所は次を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="3812d-130">The location you select must be:</span></span>
    
  - <span data-ttu-id="3812d-131">サイトごとに作成された最初のアプライアンスで作成された場所であること。</span><span class="sxs-lookup"><span data-stu-id="3812d-131">Created on the first appliance created in each site.</span></span>
    
  - <span data-ttu-id="3812d-132">同じサイトの他のホスト サーバー (アプライアンス) がアクセスできる共有フォルダーであること。</span><span class="sxs-lookup"><span data-stu-id="3812d-132">A shared folder that is accessible by the other host servers (appliances) in the same site.</span></span>
    
    <span data-ttu-id="3812d-133">**サイト ディレクトリ**をデフォルト以外の場所に設定するには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="3812d-133">To set the **Site Directory** to a location other than the default, run the following cmdlet:</span></span>
    
  ```
  Set-CcSiteDirectory <UNC File path>
  ```

    <span data-ttu-id="3812d-134">サイトの高可用性 (HA) を展開する場合、サイト内の各ホスト サーバー上の同じ場所に**サイト ディレクトリ**を設定するのには、コマンドレットを実行することを確認します。</span><span class="sxs-lookup"><span data-stu-id="3812d-134">If you are deploying High Availability (HA) for the site, make sure you run the cmdlet to set the **Site Directory** to the same location on each host server within the site.</span></span>
    
    <span data-ttu-id="3812d-135">ログオンしてサイト内で各アプライアンスを展開する場合、現在のログオン アカウントに**サイト ディレクトリ**への適切なアクセス権があることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="3812d-135">When you log on and deploy each appliance in the site, make sure your current logon account has the right access to the **Site Directory**.</span></span>
    
3. <span data-ttu-id="3812d-136">**アプライアンス ディレクトリ**は、Skype ビジネス クラウド コネクタ ・ エディション、および外部の証明書、インスタンス、およびログの保存場所のローカル作業用のルート ディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="3812d-136">The **Appliance Directory** is the local working root directory for Skype for Business Cloud Connector Edition, and the location where external certificates, instances, and logs are saved.</span></span> <span data-ttu-id="3812d-137">デフォルトで次の場所になります: %USERPROFILE%\CloudConnector\ApplianceRoot</span><span class="sxs-lookup"><span data-stu-id="3812d-137">The default location is: %USERPROFILE%\CloudConnector\ApplianceRoot.</span></span>
    
    <span data-ttu-id="3812d-138">**アプライアンス ディレクトリ**の場所を見つけるには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="3812d-138">To find the location of the **Appliance Directory**, run the following cmdlet:</span></span>
    
  ```
  Get-CcApplianceDirectory
  ```

    <span data-ttu-id="3812d-139">**アプライアンス ディレクトリ**をデフォルト以外の場所に設定するには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="3812d-139">To set the **Appliance Directory** to a location other than the default, run the following cmdlet:</span></span>
    
  ```
  Set-CcApplianceDirectory <File path>
  ```

    <span data-ttu-id="3812d-140">アプライアンス ディレクトリは、アプライアンスのローカル フォルダーに設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3812d-140">The Appliance Directory should be set to a local folder on the appliance.</span></span> <span data-ttu-id="3812d-141">ビジネス クラウド コネクタのエディションの展開での Skype を起動する前にのみ、**アプライアンスのディレクトリ**を設定してください。</span><span class="sxs-lookup"><span data-stu-id="3812d-141">You should only set the **Appliance Directory** before you start the Skype for Business Cloud Connector Edition deployment.</span></span> <span data-ttu-id="3812d-142">展開後にそれを変更する場合は、ホスト サーバーを再び展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3812d-142">If you change it after deployment, you'll need to redeploy the host server.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="3812d-143">**アプライアンス ディレクトリ**へのパスにはスペースを含めないでください。</span><span class="sxs-lookup"><span data-stu-id="3812d-143">The path to the **Appliance Directory** must not contain any spaces.</span></span>
  
## <a name="set-the-path-for-the-external-edge-certificate"></a><span data-ttu-id="3812d-144">外部 Edge 証明書のパスの設定</span><span class="sxs-lookup"><span data-stu-id="3812d-144">Set the path for the external Edge certificate</span></span>

- <span data-ttu-id="3812d-p107">次のコマンドレットを実行して、Microsoft Edge 外部証明書へのパスをファイル名も含めて設定します (例: C:\certs\cce\ap.contoso.com.pfx)。証明書には秘密キーが含まれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="3812d-p107">Run the following cmdlet to set the path, including the file name, to the external Edge certificate. For example: C:\certs\cce\ap.contoso.com.pfx. The certificate must contain private keys.</span></span>
    
  ```
  Set-CcExternalCertificateFilePath -Path <Full path to External certificate, including file name> -Target EdgeServer
  ```

    > [!NOTE]
    > <span data-ttu-id="3812d-148">-Target パラメーターはバージョン 1.4.2 固有のものであることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="3812d-148">Note that the -Target parameter is specific to versions 1.4.2 and later.</span></span> 
  
    <span data-ttu-id="3812d-149">ファイル名を含む、外部証明書への完全なパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="3812d-149">Specify the full path to the external certificate, including the file name.</span></span> <span data-ttu-id="3812d-150">証明書はローカルまたはファイル共有に格納できます。</span><span class="sxs-lookup"><span data-stu-id="3812d-150">The certificate can be stored locally or on a file share.</span></span> <span data-ttu-id="3812d-151">証明書を共有フォルダーに格納する場合、その共有フォルダーは各サイトの最初のアプライアンス上に作成し、同一のサイトに属するその他のアプライアンスによってアクセス可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="3812d-151">If the certificate is stored in a shared folder, the shared folder must be created on the first appliance of each site and must be accessible by other appliances belonging to the same site.</span></span> <span data-ttu-id="3812d-152">このコマンドレットは、外部証明書を**アプライアンス ディレクトリ**にコピーします。</span><span class="sxs-lookup"><span data-stu-id="3812d-152">This cmdlet copies the external certificate to the **Appliance Directory**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="3812d-153">**クラウド コネクタ バージョン 1.4.2 を更新した場合か、後で**、秘密キーと完全な証明書チェーンを含むルート CA 証明書、中間 CA の証明書ですが、準備された外部の証明書に含まれていることを確認 >**がある場合。クラウド コネクタ バージョン 1.4.2 が更新されていない**、準備された外部証明書に秘密キーが含まれているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="3812d-153">**If you have updated to Cloud Connector version 1.4.2 or later**, make sure your prepared external certificate contains private keys and the full certificate chain including the root CA certificate and the intermediate CA certificates.> **If you have NOT yet updated to Cloud Connector version 1.4.2**, make sure your prepared external certificate contains private keys.</span></span> <span data-ttu-id="3812d-154">この外部証明書は、既定で Windows で信頼されている認証局が発行したものである必要があります。</span><span class="sxs-lookup"><span data-stu-id="3812d-154">This external certificate must be issued by a Certificate Authority that is trusted by Windows by default.</span></span>
  
## <a name="set-the-path-for-the-external-pstn-gatewaysbc-certificate"></a><span data-ttu-id="3812d-155">外部 PSTN ゲートウェイ/SBC 証明書のパスの設定</span><span class="sxs-lookup"><span data-stu-id="3812d-155">Set the path for the external PSTN gateway/SBC certificate</span></span>

<span data-ttu-id="3812d-156">仲介サーバーと PSTN ゲートウェイと SBC の間で TLS を使用する場合は、ゲートウェイの証明書に、ファイル名を含むパスを設定するのには次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="3812d-156">If you are using TLS between the Mediation Server and the PSTN gateway/SBC, run the following cmdlet to set the path, including the file name, to the gateway certificate.</span></span> <span data-ttu-id="3812d-157">例: C:\certs\cce\sbc.contoso.com.cer。</span><span class="sxs-lookup"><span data-stu-id="3812d-157">For example: C:\certs\cce\sbc.contoso.com.cer.</span></span> <span data-ttu-id="3812d-158">証明書は、ルート CA と中間ゲートウェイに割り当てられている証明書のチェーンに含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3812d-158">The certificate must contain the root CA and the intermediate chain for the certificate assigned to the gateway:</span></span>
  
```
Set-CcExternalCertificateFilePath -Path <Full path to gateway certificate, including file name> -Target MediationServer 

```

> [!NOTE]
> <span data-ttu-id="3812d-159">-Target パラメーターはバージョン 1.4.2 固有のものであることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="3812d-159">Note that the -Target parameter is specific to versions 1.4.2 and later.</span></span> 
  
## <a name="create-virtual-switches-in-hyper-v-manager"></a><span data-ttu-id="3812d-160">Hyper-V マネージャーでの仮想スイッチの作成</span><span class="sxs-lookup"><span data-stu-id="3812d-160">Create virtual switches in Hyper-V Manager</span></span>

1. <span data-ttu-id="3812d-161">**HYPER-V マネージャー**を開き > **仮想スイッチ マネージャー**、および**新しい仮想スイッチ マネージャー**を選択します。</span><span class="sxs-lookup"><span data-stu-id="3812d-161">Open **Hyper-V Manager** > **Virtual Switch Manager**, and select **New Virtual Switch Manager**.</span></span>
    
2. <span data-ttu-id="3812d-162">外部仮想スイッチを作成し、それを内部のネットワーク ドメインに接続される物理ネットワーク アダプターにバインドします。</span><span class="sxs-lookup"><span data-stu-id="3812d-162">Create an External virtual switch and bind it to the physical network adapter that is connected to your internal network domain:</span></span>
    
    <span data-ttu-id="3812d-163">この仮想スイッチに **[管理オペレーティング システムによるこのネットワーク アダプターの共有を許可する]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="3812d-163">Select **Allow management operating system to share this network adapter** for this virtual switch.</span></span>
    
3. <span data-ttu-id="3812d-164">外部仮想スイッチを作成して、インターネットにルーティングされる物理ネットワーク アダプターにバインドします。</span><span class="sxs-lookup"><span data-stu-id="3812d-164">Create an External virtual switch and bind it to the physical network adapter that is routed to the Internet:</span></span>
    
    <span data-ttu-id="3812d-165">この仮想スイッチについての [**管理オペレーティング システムによるこのネットワーク アダプターの共有を許可する**] の選択を解除します。</span><span class="sxs-lookup"><span data-stu-id="3812d-165">De-select **Allow management operating system to share this network adapter** for this virtual switch.</span></span>
    
4. <span data-ttu-id="3812d-166">境界ネットワークを内部ネットワーク ドメインに接続するスイッチの名前を **SfB CCE Corpnet Switch** に設定します。</span><span class="sxs-lookup"><span data-stu-id="3812d-166">Set the name of the switch that connects your perimeter network to your internal network domain **SfB CCE Corpnet Switch**.</span></span>
    
    <span data-ttu-id="3812d-167">境界ネットワークをインターネットに接続するスイッチの名前を、**SfB CCE Internet Switch** に設定します。</span><span class="sxs-lookup"><span data-stu-id="3812d-167">Set the name of the switch that connects your perimeter network to the Internet **SfB CCE Internet Switch**.</span></span>
    
## <a name="update-the-cloudconnectorini-configuration-file"></a><span data-ttu-id="3812d-168">CloudConnector.ini 構成ファイルの更新</span><span class="sxs-lookup"><span data-stu-id="3812d-168">Update the CloudConnector.ini configuration file</span></span>

<span data-ttu-id="3812d-169">[ビジネス クラウド コネクタ ・ エディションの Skype の計画](plan-skype-for-business-cloud-connector-edition.md)のトピック[を決定する配置パラメーター](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams)で収集した情報を使用して CloudConnector.ini ファイルを準備します。</span><span class="sxs-lookup"><span data-stu-id="3812d-169">Prepare the CloudConnector.ini file using the information you gathered in [Determine deployment parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) in the [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) topic.</span></span>
  
<span data-ttu-id="3812d-170">ファイルを更新するには、まず次のコマンドレットを実行してサンプルのテンプレート (CloudConnector.Sample.ini) を入手します。</span><span class="sxs-lookup"><span data-stu-id="3812d-170">To update the file, first run the following cmdlet to get the sample template (CloudConnector.Sample.ini):</span></span>
  
```
Export-CcConfigurationSampleFile
```

<span data-ttu-id="3812d-171">サンプルのテンプレートは**アプライアンス ディレクトリ**に保存されています。</span><span class="sxs-lookup"><span data-stu-id="3812d-171">The sample template is stored in the **Appliance Directory**.</span></span>
  
<span data-ttu-id="3812d-172">環境に応じた値でファイルを更新したら、ファイルを CloudConnector.ini として**アプライアンス ディレクトリ**に保存します。</span><span class="sxs-lookup"><span data-stu-id="3812d-172">After you update it with the values for your environment, save the file as CloudConnector.ini in the **Appliance Directory**.</span></span> <span data-ttu-id="3812d-173">**アプライアンス ディレクトリ**へのパスを決定するのには、 **Get CcApplianceDirectory**を実行することができます。</span><span class="sxs-lookup"><span data-stu-id="3812d-173">You can run **Get-CcApplianceDirectory** to determine the path to the **Appliance Directory**.</span></span>
  
<span data-ttu-id="3812d-174">.ini ファイルを更新するとき、次を考慮します。</span><span class="sxs-lookup"><span data-stu-id="3812d-174">When updating the .ini file, consider the following:</span></span>
  
> [!NOTE]
> <span data-ttu-id="3812d-175">このセクションでは .ini ファイルのすべての値を取り上げておらず、特別な考慮が必要な値のみを説明しています。</span><span class="sxs-lookup"><span data-stu-id="3812d-175">Not all values for the .ini file are discussed in this section, only those with a special consideration are covered here.</span></span> <span data-ttu-id="3812d-176">完全なリストは、[ビジネス クラウド コネクタ ・ エディションの Skype の計画](plan-skype-for-business-cloud-connector-edition.md)のトピック[を確認する展開のパラメーター](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams)を参照してください > アプライアンスの追加や新しいサイトを変更する必要がある値の詳細については、[を参照してください。1 つのサイトで高可用性 (HA) 複数サイトの展開と比較して](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site)[クラウド コネクタで複数のサイトを展開する](deploy-multiple-sites-in-cloud-connector.md)」のです。</span><span class="sxs-lookup"><span data-stu-id="3812d-176">For a full list, see the [Determine deployment parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) section of the [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) topic.> For more information about what values need to be changed for additional appliances or new sites, see [Single site with High Availability (HA) compared to multi-site deployments](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) in the topic[Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 
  
- <span data-ttu-id="3812d-p113">**SiteName:** デフォルト値は **Site1** です。Cloud Connector の展開前にこれを更新する必要があります。その理由は、**Register-CcAppliance** を実行して既存または新規のサイトにアプライアンスを登録するとき、コマンドレットが **SiteName** を使ってどのサイトに登録するかを決めるからです。</span><span class="sxs-lookup"><span data-stu-id="3812d-p113">**SiteName:** The default value is **Site1**. You must update it before you deploy Cloud Connector, because when you run **Register-CcAppliance** to register an appliance to an existing or new site, the cmdlet will use **SiteName** to determine which site to register.</span></span>
    
     <span data-ttu-id="3812d-179">新規サイトにアプライアンスを登録する場合は、**SiteName** の値は一意で既存のサイトと異なる必要があります。</span><span class="sxs-lookup"><span data-stu-id="3812d-179">If you want to register the appliance to a new site, the value of **SiteName** must be unique and different from existing sites.</span></span> <span data-ttu-id="3812d-180">アプライアンスの既存のサイトを登録する場合は、.ini ファイル内の**サイト名**の値は、Office 365 テナント構成で定義されている名前と一致しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="3812d-180">If you want to register the appliance to an existing site, the value for **SiteName** in .ini file must match the name defined in your Office 365 tenant configuration.</span></span> <span data-ttu-id="3812d-181">あるサイトから別のサイトに構成ファイルをコピーする場合は、必ずサイトごとに **SiteName** の値を更新してください。</span><span class="sxs-lookup"><span data-stu-id="3812d-181">If you are copying a configuration file from one site to another, make sure you update the value for **SiteName** for each site accordingly.</span></span>
    
- <span data-ttu-id="3812d-182">**ServerName:** サーバー名はドメイン名を含まず、15 文字に制限する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3812d-182">**ServerName:** The server name should not contain the domain name and should be limited to 15 characters.</span></span>
    
- <span data-ttu-id="3812d-183">**HardwareType:** 設定または、null 値のままにしない、**通常**の既定値が適用されます。</span><span class="sxs-lookup"><span data-stu-id="3812d-183">**HardwareType:** If you don't set or leave the value to null, the default value of **Normal** will be used.</span></span> <span data-ttu-id="3812d-184">[Skype ビジネス クラウド コネクタ ・ エディションのための計画](plan-skype-for-business-cloud-connector-edition.md)で説明するように、ホスト マシンごとの 500 の同時呼び出しをサポートするクラウドのコネクタの大きなバージョンを展開する場合は、**標準**を使用します。</span><span class="sxs-lookup"><span data-stu-id="3812d-184">Use **Normal** if you plan to deploy the larger version of Cloud Connector to support 500 simultaneous calls per host machine as described in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span> <span data-ttu-id="3812d-185">50 の同時通話をサポートする小規模な展開の場合は **Minimum** を使用します。</span><span class="sxs-lookup"><span data-stu-id="3812d-185">Use **Minimum** for a smaller deployment that supports 50 simultaneous calls.</span></span>
    
- <span data-ttu-id="3812d-186">**インターネット/Corpnet/管理仮想スイッチ:** 作成した仮想スイッチの名前を追加します。</span><span class="sxs-lookup"><span data-stu-id="3812d-186">**Internet/Corpnet/Management virtual switches:**: Add the name of the virtual switches you have created.</span></span> <span data-ttu-id="3812d-187">管理仮想スイッチの場合は、デフォルト値をそのまま残します。</span><span class="sxs-lookup"><span data-stu-id="3812d-187">For the management virtual switch, leave the default value.</span></span> <span data-ttu-id="3812d-188">展開スクリプトは展開の始まりで管理仮想スイッチを作成し、展開の終わりに削除します。</span><span class="sxs-lookup"><span data-stu-id="3812d-188">The deployment script will create the management virtual switch at the beginning of deployment and delete it when the deployment finishes.</span></span>
    
- <span data-ttu-id="3812d-p117">**ManagementIPPrefix:** ネットワーク セクションの ManagementIPPrefix は、他の内部 IP とは異なるサブネットである必要があります。例えば、デフォルト値が示すように、ManagementIPPrefix は 192.168.213.0、AD IPAddress は 192.168.0.238 となります。</span><span class="sxs-lookup"><span data-stu-id="3812d-p117">**ManagementIPPrefix:** ManagementIPPrefix in the Network section must be a different subnet from other internal IPs. For example, as the default value shows, ManagementIPPrefix is 192.168.213.0, while AD IPAddress is 192.168.0.238.</span></span>
    
    <span data-ttu-id="3812d-p118">展開スクリプトは管理ネットワーク アダプターを仮想マシンごとに作成し、管理 IP を割り当て、それを管理仮想スイッチに接続します。これによりホスト サーバーは、この管理ネットワーク経由で各仮想マシンに接続しそれらを管理できます。管理仮想スイッチは展開が終了すると削除されます。</span><span class="sxs-lookup"><span data-stu-id="3812d-p118">The deployment scripts create a management network adapter on each virtual machine, assign a management IP, and connect it to a management virtual switch. This enables the host server to connect to and manage each virtual machine via this management network. The management virtual switch is deleted when the deployment is finished.</span></span>
    
- <span data-ttu-id="3812d-194">**ベースの VM の特定の構成:****変換 CcIsoToVhdx**コマンドレットでは、このセクションの設定を構成しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="3812d-194">**Base VM specific configurations:** Settings in this section must be configured for the **Convert-CcIsoToVhdx** cmdlet.</span></span>
    
    <span data-ttu-id="3812d-p119">ベース VM イメージを準備するとき、ベース VM は内部ネットワーク スイッチに接続されます。次の設定は、VM がインターネットに接続できるようにするために重要です。</span><span class="sxs-lookup"><span data-stu-id="3812d-p119">During base VM image preparation, the base VM will be connected to the internal network switch. The following settings are critical for the VM to be able to access the Internet:</span></span>
    
  - <span data-ttu-id="3812d-197">[Common]BaseVMIP: ベース VM に割り当てられる corpnet IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="3812d-197">[Common]BaseVMIP: the corpnet IP address to be assigned to the base VM.</span></span>
    
  - <span data-ttu-id="3812d-198">[Network]CorpnetDefaultGateway: ベース VM に割り当てられるデフォルトのゲートウェイ。</span><span class="sxs-lookup"><span data-stu-id="3812d-198">[Network]CorpnetDefaultGateway: the default gateway to be assigned to the base VM.</span></span>
    
  - <span data-ttu-id="3812d-199">[Network]CorpnetDNSIPAddress: ベース VM に割り当てられる DNS IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="3812d-199">[Network]CorpnetDNSIPAddress: the DNS IP address to be assigned to the base VM.</span></span>
    
  - <span data-ttu-id="3812d-200">[Network]WSUSServer: Windows Server Update Service の IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="3812d-200">[Network]WSUSServer: the IP address of Windows Server Update Service.</span></span>
    
  - <span data-ttu-id="3812d-201">[Network]WSUSStatusServer: Windows Server Update Service ステータス サーバーの IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="3812d-201">[Network]WSUSStatusServer: the IP address of Windows Server Update Service status server.</span></span>
    
  - <span data-ttu-id="3812d-202">[Network]EnableReferSupport: IP/PBX へのトランク構成で SIP REFER のサポートが有効化または無効化されるかを定義します。</span><span class="sxs-lookup"><span data-stu-id="3812d-202">[Network]EnableReferSupport: this will define whether SIP REFER support is enabled or disabled on the Trunk Configuration to your IP/PBX.</span></span>
    
- <span data-ttu-id="3812d-203">**内部 IP:**</span><span class="sxs-lookup"><span data-stu-id="3812d-203">**Internal IPs:**</span></span>
    
  - <span data-ttu-id="3812d-204">CorpnetIPPrefixLength のサブネット マスクが正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="3812d-204">Make sure subnet mask CorpnetIPPrefixLength is correct.</span></span>
    
  - <span data-ttu-id="3812d-205">これらの内部 ip アドレスの IP が競合していないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="3812d-205">Make sure there are no IP conflicts for these internal IPs.</span></span>
    
- <span data-ttu-id="3812d-206">**外部 IP:**</span><span class="sxs-lookup"><span data-stu-id="3812d-206">**External IPs:**</span></span>
    
  - <span data-ttu-id="3812d-207">MR パブリック ip: NAT 以外の ExternalMRIPs、または NAT の ExternalMRPublicIPs のいずれかを指定します。</span><span class="sxs-lookup"><span data-stu-id="3812d-207">For MR public IP: specify either ExternalMRIPs for non-NAT or ExternalMRPublicIPs for NAT.</span></span>
    
  - <span data-ttu-id="3812d-208">ExternalSIPIPs と ExternalMRIPs を同じにすることができます。</span><span class="sxs-lookup"><span data-stu-id="3812d-208">ExternalSIPIPs and ExternalMRIPs can be the same.</span></span>
    
  - <span data-ttu-id="3812d-209">InternetIPPrefixLength のサブネット マスクが正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="3812d-209">Make sure subnet mask InternetIPPrefixLength is correct.</span></span>
    
  - <span data-ttu-id="3812d-210">これらの外部 ip アドレスの IP が競合していないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="3812d-210">Make sure there are no IP conflicts for these external IPs.</span></span>
    
- <span data-ttu-id="3812d-211">**ゲートウェイ:**</span><span class="sxs-lookup"><span data-stu-id="3812d-211">**Gateways:**</span></span>
    
  - <span data-ttu-id="3812d-p120">ゲートウェイが 1 つだけある場合は、セカンダリ ゲートウェイのセクションを削除します。ゲートウェイが 3 つ以上ある場合は、既存のセクションをコピー貼り付けしてから、それを更新します。</span><span class="sxs-lookup"><span data-stu-id="3812d-p120">If you have only one gateway, remove the section for the secondary gateway. If you have more than two gateways, create additional sections by copying and pasting the existing one and then updating it.</span></span>
    
  - <span data-ttu-id="3812d-214">ゲートウェイの IP アドレスとポートが正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="3812d-214">Make sure that the IP address and port of the gateway(s) are correct.</span></span>
    
  - <span data-ttu-id="3812d-215">PSTN ゲートウェイ レベルの HA をサポートするには、セカンダリ ゲートウェイを残し、新たなゲートウェイをいくつか追加して使います。</span><span class="sxs-lookup"><span data-stu-id="3812d-215">To support PSTN gateway level HA, leave the secondary gateway, and add any additional gateways you will use.</span></span> <span data-ttu-id="3812d-216">コピーして既存のエントリを貼り付けると、それを更新します。</span><span class="sxs-lookup"><span data-stu-id="3812d-216">You can copy and paste an existing entry and then update it.</span></span>
    
- <span data-ttu-id="3812d-217">必要に応じて、送信呼び出しの数を制限するのには LocalRoute の値を更新できます。</span><span class="sxs-lookup"><span data-stu-id="3812d-217">Optionally, you can update the LocalRoute value to restrict outbound call numbers.</span></span>
    
## <a name="download-the-bits-to-the-site-directory"></a><span data-ttu-id="3812d-218">サイト ディレクトリに BITS をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="3812d-218">Download the bits to the Site Directory</span></span>

<span data-ttu-id="3812d-219">次のコマンドレットを実行して、BITS ファイルとバージョン情報ファイルを**サイト ディレクトリ**にダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="3812d-219">Run the following cmdlet to download the bits and version information files to the **Site Directory**:</span></span>
  
```
Start-CcDownload
```

> [!NOTE]
> <span data-ttu-id="3812d-220">最初のアプライアンスでのみ、この手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3812d-220">You need to perform this step for the first appliance only.</span></span> 
  
## <a name="prepare-base-virtual-disk-vhdx-from-the-downloaded-iso-file"></a><span data-ttu-id="3812d-221">ダウンロードした ISO ファイルからベース仮想ディスク (VHDX) を準備します。</span><span class="sxs-lookup"><span data-stu-id="3812d-221">Prepare base virtual disk (VHDX) from the downloaded ISO file</span></span>

<span data-ttu-id="3812d-222">この手順では、Windows Server 2012 の ISO イメージから仮想ハード ディスク (VHDX) ファイルを準備します。</span><span class="sxs-lookup"><span data-stu-id="3812d-222">This step prepares a virtual hard disk (VHDX) file from the Windows Server 2012 ISO image.</span></span> <span data-ttu-id="3812d-223">VHDX は展開時の仮想マシン作成に使われます。</span><span class="sxs-lookup"><span data-stu-id="3812d-223">The VHDX will be used to create virtual machines during deployment.</span></span> <span data-ttu-id="3812d-224">一時的な仮想マシン (VM の基本) が作成され、Windows Server 2012 は、ISO ファイルからインストールされます。</span><span class="sxs-lookup"><span data-stu-id="3812d-224">A temporary virtual machine (base VM) will be created and Windows Server 2012 will be installed from the ISO file.</span></span> <span data-ttu-id="3812d-225">VM を作成した後、必要なコンポーネントがいくつかインストールされ、最新の Windows 更新プログラムが適用されます。</span><span class="sxs-lookup"><span data-stu-id="3812d-225">After the VM is created, some necessary components will be installed and the latest Windows update will be applied.</span></span> <span data-ttu-id="3812d-226">最後に、ベース VM の一般化 (sysprep) とクリーンアップが行われ、生成された仮想ディスク ファイルのみが残ります。</span><span class="sxs-lookup"><span data-stu-id="3812d-226">At the end, the base VM will be generalized (sysprep) and cleaned up, leaving only the generated virtual disk file.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3812d-227">最初のアプライアンスでのみ、この手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3812d-227">You need to perform this step for the first appliance only.</span></span> 
  
<span data-ttu-id="3812d-p123">この手順を進める前に、corpnet スイッチが作成されていることを確認してください。また、CloudConnector.ini ファイルで次の設定が正しく行われていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="3812d-p123">Before proceeding with this step, make sure that the corpnet switch is created. Also, confirm that the following settings are correctly configured in the CloudConnector.ini file:</span></span>
  
- <span data-ttu-id="3812d-230">[ネットワーク]CorpnetSwitchName</span><span class="sxs-lookup"><span data-stu-id="3812d-230">[Network]CorpnetSwitchName</span></span>
    
- <span data-ttu-id="3812d-231">[共通]BaseVMIP</span><span class="sxs-lookup"><span data-stu-id="3812d-231">[Common]BaseVMIP</span></span>
    
- <span data-ttu-id="3812d-232">[ネットワーク]CorpnetIPPrefixLength</span><span class="sxs-lookup"><span data-stu-id="3812d-232">[Network]CorpnetIPPrefixLength</span></span>
    
- <span data-ttu-id="3812d-233">[ネットワーク]CorpnetDefaultGateway</span><span class="sxs-lookup"><span data-stu-id="3812d-233">[Network]CorpnetDefaultGateway</span></span>
    
- <span data-ttu-id="3812d-234">[ネットワーク]CorpnetDNSIPAddress</span><span class="sxs-lookup"><span data-stu-id="3812d-234">[Network]CorpnetDNSIPAddress</span></span>
    
<span data-ttu-id="3812d-235">PowerShell を管理者として起動し、次のコマンドレットを実行して ISO イメージを仮想ハード ディスク (VHD) に変換します。</span><span class="sxs-lookup"><span data-stu-id="3812d-235">Start a PowerShell console as administrator and run the following cmdlet to convert the ISO image to a virtual hard disk (VHD):</span></span>
  
```
Convert-CcIsoToVhdx -IsoFilePath <Windows ISO File Path, including file name>
```

<span data-ttu-id="3812d-p124">ISO イメージへの完全なパスをファイル名も含めて指定します (例: C:\ISO\WindowsServer2012R2.iso)。</span><span class="sxs-lookup"><span data-stu-id="3812d-p124">Specify the full path, including file name, to the ISO image. For example: C:\ISO\WindowsServer2012R2.iso.</span></span>
  
<span data-ttu-id="3812d-238">作成された VHD ファイルは、**サイト ディレクトリ**の \Bits\VHD フォルダーに格納されます。</span><span class="sxs-lookup"><span data-stu-id="3812d-238">The created VHD file is stored in the **Site Directory** \Bits\VHD folder.</span></span> <span data-ttu-id="3812d-239">**サイト ディレクトリ**へのパスは **Get-CcSiteDirectory** を実行して取得できます。</span><span class="sxs-lookup"><span data-stu-id="3812d-239">You can get the path to the **Site Directory** by running the **Get-CcSiteDirectory**.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="3812d-240">デフォルトで、ベース VM でプロキシ設定は構成されません。</span><span class="sxs-lookup"><span data-stu-id="3812d-240">By default, proxy settings are not configured on the base VM.</span></span> <span data-ttu-id="3812d-241">プロキシは、ネットワーク環境で Windows Update を使用して VM を更新すると、「変換 CcIsoToVhdx」を実行すると、- PauseBeforeUpdate スイッチを追加してください。</span><span class="sxs-lookup"><span data-stu-id="3812d-241">If a proxy is required in your network environment to update the VM via Windows Update, you should add the -PauseBeforeUpdate switch when you run "Convert-CcIsoToVhdx".</span></span> <span data-ttu-id="3812d-242">Windows Update の前に、スクリプトを一時停止し、VM 上でプロキシを手動で設定することがあります。</span><span class="sxs-lookup"><span data-stu-id="3812d-242">The script will pause before Windows Update and you'll have a chance to manually set up proxy on the VM.</span></span> <span data-ttu-id="3812d-243">VM がインターネットにアクセスできるようにプロキシを設定したら、スクリプトを再開して残りの手順を完了できます。</span><span class="sxs-lookup"><span data-stu-id="3812d-243">After the proxy is setup and the VM can access Internet, you can resume the script to complete the remaining steps.</span></span> 
  
### <a name="create-vhds-for-a-multi-site-deployment"></a><span data-ttu-id="3812d-244">マルチサイト展開でのVHD の作成</span><span class="sxs-lookup"><span data-stu-id="3812d-244">Create VHDs for a multi-site deployment</span></span>

<span data-ttu-id="3812d-245">このオプションの手順は、マルチサイト展開のみに適用されます。</span><span class="sxs-lookup"><span data-stu-id="3812d-245">This is an optional step that applies only to multi-site deployments.</span></span>
  
<span data-ttu-id="3812d-p127">マルチサイト展開を行う場合、サイトごとに ISO から VHD に変換する必要はありません。最初のサイトに作成した VHDX を、2 番目のサイトのホスト サーバーにコピーできます。</span><span class="sxs-lookup"><span data-stu-id="3812d-p127">If you are deploying a multi-site deployment, you do not need to convert the ISO to a VHD for each site. You can copy the VHDX created for the first site to the host server for a second site.</span></span>
  
 <span data-ttu-id="3812d-248">追加のサイトのホスト サーバー上の同じファイル名と同じファイルの場所 (**サイトのディレクトリ**\Bits\VHD フォルダー) にファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="3812d-248">Copy the file to the same file location ( **Site Directory** \Bits\VHD folder), and with the same file name, on the host server for an additional site.</span></span>
  
## <a name="set-the-powershell-execution-policy-to-remotesigned"></a><span data-ttu-id="3812d-249">PowerShell 実行ポリシーを RemoteSigned に設定する</span><span class="sxs-lookup"><span data-stu-id="3812d-249">Set the PowerShell Execution policy to RemoteSigned</span></span>

<span data-ttu-id="3812d-p128">提供される PowerShell スクリプトでは、実行ポリシーを RemoteSigned に設定する必要があります。現在の設定を表示するには、管理者として PowerShell コンソールを開き、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="3812d-p128">The PowerShell scripts provided require that the execution policy be set to RemoteSigned. To see the current setting, open a PowerShell console as administrator and then run the following cmdlet:</span></span>
  
```
Get-ExecutionPolicy
```

<span data-ttu-id="3812d-252">「RemoteSigned」に設定されていない場合は、次のコマンドレットを実行して設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="3812d-252">If it is not set to "RemoteSigned," run the following cmdlet to change it:</span></span>
  
```
Set-ExecutionPolicy RemoteSigned
```

## <a name="change-local-group-policy-on-the-host-machine-versions-141-and-earlier"></a><span data-ttu-id="3812d-253">ホスト マシンでローカルグループ ポリシーを変更します (バージョン 1.4.1 以前)。</span><span class="sxs-lookup"><span data-stu-id="3812d-253">Change local Group Policy on the host machine (versions 1.4.1 and earlier)</span></span>

> [!NOTE]
> <span data-ttu-id="3812d-254">Cloud Connector バージョン 1.4.2 以降では、このタスクは不要です。</span><span class="sxs-lookup"><span data-stu-id="3812d-254">This task is not required for Cloud Connector versions 1.4.2 and later.</span></span> 
  
<span data-ttu-id="3812d-255">Skype for Business Cloud Connector エディションの展開時に CceService アカウントが作成されます。</span><span class="sxs-lookup"><span data-stu-id="3812d-255">The CceService account is created during the Skype for Business Cloud Connector Edition deployment.</span></span> <span data-ttu-id="3812d-256">クラウド コネクタの管理サービスを実行して、cloudconnector.msi をアンインストールするのには権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="3812d-256">It runs the Cloud Connector Management Service and requires permission to uninstall the cloudconnector.msi.</span></span> <span data-ttu-id="3812d-257">ユーザーのログオフ時にユーザー レジストリがアンロードされないように指定するには、Cloud Connector のホスト コンピューター上のグループ ポリシー設定を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3812d-257">You must change the group policy setting on the Cloud Connector host machine to specify that the user registry should not be unloaded when the user logs off.</span></span> <span data-ttu-id="3812d-258">以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3812d-258">Follow the steps below:</span></span>
  
### <a name="to-change-the-group-policy-setting"></a><span data-ttu-id="3812d-259">グループ ポリシー設定を変更するには</span><span class="sxs-lookup"><span data-stu-id="3812d-259">To change the Group Policy setting</span></span>

1. <span data-ttu-id="3812d-260">Gpedit.msc を実行することによって、**グループ ポリシー エディター**を開きます。</span><span class="sxs-lookup"><span data-stu-id="3812d-260">Open the **Group Policy Editor** by running gpedit.msc.</span></span>
    
2. <span data-ttu-id="3812d-261">**グループ ポリシー エディター**で、[管理用テンプレート] > [システム] > [ユーザー プロファイル] > [ユーザーのログオフ時に強制的にユーザー レジストリをアンロードしない] に移動します。</span><span class="sxs-lookup"><span data-stu-id="3812d-261">In the **Group Policy Editor**, navigate to Administrative Templates > System > UserProfile > Do not forcefully unload the user registry at user logoff.</span></span> 
    
3. <span data-ttu-id="3812d-262">その値が**有効**に設定します。</span><span class="sxs-lookup"><span data-stu-id="3812d-262">Set its value to **Enabled**.</span></span>
    
## <a name="set-up-your-office-365-tenant"></a><span data-ttu-id="3812d-263">Office 365 テナントの設定</span><span class="sxs-lookup"><span data-stu-id="3812d-263">Set up your Office 365 tenant</span></span>

<span data-ttu-id="3812d-264">Skype for Business Online と Office 365 の電話システムを使用している Office 365 テナントが必要です。</span><span class="sxs-lookup"><span data-stu-id="3812d-264">An Office 365 tenant with Skype for Business Online and Phone System in Office 365 is required.</span></span> <span data-ttu-id="3812d-265">テナントを設定し、クラウドのコネクタを使用する前に構成されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="3812d-265">Make sure your tenant is set up and configured before attempting to use Cloud Connector.</span></span>
  
<span data-ttu-id="3812d-266">いくつかの Office 365 のセットアップ手順では、テナント リモート PowerShell (TRPS) を使用して、Office 365 テナントを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3812d-266">Some Office 365 setup steps require you to use Tenant Remote PowerShell (TRPS) to configure your Office 365 tenant.</span></span> <span data-ttu-id="3812d-267">**これはホスト サーバー上にインストールしてください。**</span><span class="sxs-lookup"><span data-stu-id="3812d-267">**This should be installed on the host server.**</span></span> <span data-ttu-id="3812d-268">PowerShell からのオンライン ビジネス モジュールの Skype をダウンロードする:[Windows PowerShell モジュール ビジネス オンラインの Skype](https://www.microsoft.com/en-us/download/details.aspx?id=39366)です。</span><span class="sxs-lookup"><span data-stu-id="3812d-268">You can download the Skype for Business Online module for PowerShell from:[Skype for Business Online, Windows PowerShell Module](https://www.microsoft.com/en-us/download/details.aspx?id=39366).</span></span>
  
<span data-ttu-id="3812d-269">クラウド コネクタのオンライン管理、CceOnlineManagmentAdministrator などのビジネス管理者のアカウント用の専用の Skype を作成します。</span><span class="sxs-lookup"><span data-stu-id="3812d-269">Create a dedicated Skype for Business administrator account for Cloud Connector online management, for example CceOnlineManagmentAdministrator.</span></span> <span data-ttu-id="3812d-270">このアカウントはアプライアンスによって使用され、アプライアンスの追加や削除、自動 OS 更新の有効化や無効化、自動バイナリ更新の有効化や無効化を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="3812d-270">This account will be used by appliance to add or remove appliance, enable or disable automatic OS update, enable or disable automatic binary update.</span></span> <span data-ttu-id="3812d-271">このアカウントのパスワードが期限切れにならないように設定すると、サービスが期限切れになるたびにパスワードを変更する必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="3812d-271">Set the password for this account to never expire so that you do not need to change it for the service each time it expires.</span></span>
  

