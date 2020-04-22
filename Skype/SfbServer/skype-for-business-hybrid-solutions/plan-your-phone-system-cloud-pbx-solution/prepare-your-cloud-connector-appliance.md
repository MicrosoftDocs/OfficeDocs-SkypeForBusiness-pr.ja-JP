---
title: Cloud Connector アプライアンスの準備
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
description: Office 365 (クラウド PBX) の電話システムで展開および使用するための Cloud Connector アプライアンスを準備する方法について説明します。
ms.openlocfilehash: 21943dfd8b86bfeabb4cbd28b501b80a3f2b5c45
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779243"
---
# <a name="prepare-your-cloud-connector-appliance"></a><span data-ttu-id="14f85-103">Cloud Connector アプライアンスの準備</span><span class="sxs-lookup"><span data-stu-id="14f85-103">Prepare your Cloud Connector appliance</span></span>

<span data-ttu-id="14f85-104">Office 365 (クラウド PBX) の電話システムで展開および使用するための Cloud Connector アプライアンスを準備する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="14f85-104">Learn about how to prepare your Cloud Connector appliance for deployment and use with Phone System in Office 365 (Cloud PBX).</span></span>

<span data-ttu-id="14f85-105">このセクションでは、Skype for Business Cloud Connector エディションのインストールファイルを取得する方法、クラウドコネクタソフトウェアをインストールする方法、および展開用に Cloud Connector アプライアンスを準備する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="14f85-105">This section describes how to get the Skype for Business Cloud Connector Edition installation files, install Cloud Connector software, and prepare your Cloud Connector appliance for deployment.</span></span> <span data-ttu-id="14f85-106">このセクションのすべての手順を完了すると、1つまたは複数のサイト用の Cloud Connector を展開する準備が整います。</span><span class="sxs-lookup"><span data-stu-id="14f85-106">After you have completed all steps in this section, you will be ready to deploy Cloud Connector for a single site or multiple sites.</span></span> <span data-ttu-id="14f85-107">既存の Cloud Connector の展開があり、まだ Cloud Connector バージョン2.1 にアップグレードしていない場合は、「 [Cloud connector の新しいバージョンへのアップグレード](upgrade-to-a-new-version-of-cloud-connector.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14f85-107">If you have an existing Cloud Connector deployment, and you have not yet upgraded to Cloud Connector version 2.1, see [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span>

> [!NOTE]
> <span data-ttu-id="14f85-108">Microsoft は、Cloud Connector エディションバージョン2.1 の現在のバージョンをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="14f85-108">Microsoft supports the current version of Cloud Connector Edition, version 2.1.</span></span> <span data-ttu-id="14f85-109">自動更新を構成した場合、Cloud Connector は自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="14f85-109">If you configured automatic update, Cloud Connector will update automatically.</span></span> <span data-ttu-id="14f85-110">手動更新を構成した場合は、リリースから60日以内にバージョン2.1 にアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="14f85-110">If you configured manual update, you will need to upgrade to version 2.1 within 60 days of its release.</span></span> <span data-ttu-id="14f85-111">Microsoft は、2.1 をリリースしてから60日後に、アップグレードに要する時間を確保するために、以前のバージョンをサポートします。</span><span class="sxs-lookup"><span data-stu-id="14f85-111">Microsoft will support the previous version for 60 days after the release of 2.1 to allow you time to upgrade.</span></span> 

> [!NOTE]
> <span data-ttu-id="14f85-112">Cloud Connector バージョン2.1 以降の場合、ホストアプライアンスには .NET Framework 4.6.1 以降がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="14f85-112">For Cloud Connector version 2.1 and later, the host appliance must have .NET Framework 4.6.1 or later installed.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="14f85-113">展開を成功させるには、コマンドレットを実行して Skype for Business Cloud Connector エディションを構成するときに、開始したのと同じコンソールセッションを常に使用します。</span><span class="sxs-lookup"><span data-stu-id="14f85-113">For successful deployment, when you run the cmdlets to configure Skype for Business Cloud Connector Edition, always use the same console session as the one you started in.</span></span> <span data-ttu-id="14f85-114">展開および構成中に異なるセッションに切り替えないようにします。</span><span class="sxs-lookup"><span data-stu-id="14f85-114">Avoid switching to different sessions during the deployment and configuration.</span></span> 

> [!NOTE]
> <span data-ttu-id="14f85-115">展開の最初のアプライアンスに対してのみ実行する手順として、サイトディレクトリの共有を作成する方法、bits をダウンロードする方法、Windows Server ISO イメージから仮想ハードディスク (VHDX) ファイルを準備する方法があります。</span><span class="sxs-lookup"><span data-stu-id="14f85-115">There are some steps that you perform only for the first appliance in your deployment: creating a share for the site directory, downloading the bits, and preparing a virtual hard disk (VHDX) file from the Windows Server ISO image.</span></span> 

## <a name="download-the-skype-for-business-cloud-connector-edition-installer"></a><span data-ttu-id="14f85-116">Skype for Business Cloud Connector エディションのインストーラーをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="14f85-116">Download the Skype for Business Cloud Connector Edition installer</span></span>

1. <span data-ttu-id="14f85-117">Cloud Connector Vm が実行されるホストサーバーで、インストールファイル[https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller)をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="14f85-117">On the host server where the Cloud Connector VMs will run, download the installation files: [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span> 

    > [!IMPORTANT]
    > <span data-ttu-id="14f85-118">インストール中に追加のファイルがダウンロードされるので、ホストサーバーは、Cloud Connector のインストール中にインターネットにアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="14f85-118">The host server must be able to access the Internet during the installation of Cloud Connector because additional files are downloaded during the installation.</span></span> 

2. <span data-ttu-id="14f85-119">インストーラーを実行し、インストール時に既定値をそのまま使用します。</span><span class="sxs-lookup"><span data-stu-id="14f85-119">Run the installer and accept the default values during the installation.</span></span>

3. <span data-ttu-id="14f85-120">インストールが正常に完了したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="14f85-120">Confirm that the installation completed successfully.</span></span>

## <a name="verify-the-installation-and-configure-the-environment"></a><span data-ttu-id="14f85-121">インストールを確認して環境を構成する</span><span class="sxs-lookup"><span data-stu-id="14f85-121">Verify the installation and configure the environment</span></span>

1. <span data-ttu-id="14f85-122">管理者として PowerShell コンソールを開き、次のコマンドレットを使用して Skype for Business Cloud Connector エディションのコマンドレットを使用できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="14f85-122">Open a PowerShell console as administrator and confirm that the Skype for Business Cloud Connector Edition cmdlets are available using the following cmdlet:</span></span>

   ```powershell
   Get-Command *-Cc*
   ```

    <span data-ttu-id="14f85-123">このコマンドを実行すると、Skype for Business Cloud Connector エディションのコマンドレットの一覧が返されます。</span><span class="sxs-lookup"><span data-stu-id="14f85-123">The command should return a list of cmdlets for Skype for Business Cloud Connector Edition.</span></span>

2. <span data-ttu-id="14f85-124">Vhd、SfBBits、および VersionInfo の各ファイルは、**サイトディレクトリ**に格納されます。</span><span class="sxs-lookup"><span data-stu-id="14f85-124">The VHDs, SfBBits, and VersionInfo files will be stored in the **Site Directory**.</span></span>

    <span data-ttu-id="14f85-125">次のコマンドレットを使用して、**サイトディレクトリ**の場所を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="14f85-125">You can find the location of the **Site Directory** with the following cmdlet:</span></span>

   ```powershell
   Get-CcSiteDirectory
   ```

    <span data-ttu-id="14f85-126">このコマンドは、ファイルシステム内の場所を返します。</span><span class="sxs-lookup"><span data-stu-id="14f85-126">The command should return a location in your file system.</span></span> <span data-ttu-id="14f85-127">この場所は、ローカルフォルダーまたはファイル共有にすることができます。</span><span class="sxs-lookup"><span data-stu-id="14f85-127">The location can be a local folder or a file share.</span></span> <span data-ttu-id="14f85-128">**サイトディレクトリ**の既定の場所は次のとおりです。%userprofile%\cloudconnector\siteroot</span><span class="sxs-lookup"><span data-stu-id="14f85-128">The default location for the **Site Directory** is: %USERPROFILE%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="14f85-129">既定の場所は、各サイトで作成された最初のアプライアンスのファイル共有に変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="14f85-129">The default location should be changed to a file share on the first appliance created in each site.</span></span>

    <span data-ttu-id="14f85-130">次の場所を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="14f85-130">The location you select must be:</span></span>

   - <span data-ttu-id="14f85-131">各サイトで作成された最初のアプライアンスで作成されます。</span><span class="sxs-lookup"><span data-stu-id="14f85-131">Created on the first appliance created in each site.</span></span>

   - <span data-ttu-id="14f85-132">同じサイト内の他のホストサーバー (アプライアンス) がアクセスできる共有フォルダー。</span><span class="sxs-lookup"><span data-stu-id="14f85-132">A shared folder that is accessible by the other host servers (appliances) in the same site.</span></span>

     <span data-ttu-id="14f85-133">**サイトディレクトリ**を既定以外の場所に設定するには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="14f85-133">To set the **Site Directory** to a location other than the default, run the following cmdlet:</span></span>

   ```powershell
   Set-CcSiteDirectory <UNC File path>
   ```

    <span data-ttu-id="14f85-134">サイトの高可用性 (HA) を展開する場合は、コマンドレットを実行して、サイト内の各ホストサーバー上の同じ場所に**サイトディレクトリ**を設定してください。</span><span class="sxs-lookup"><span data-stu-id="14f85-134">If you are deploying High Availability (HA) for the site, make sure you run the cmdlet to set the **Site Directory** to the same location on each host server within the site.</span></span>

    <span data-ttu-id="14f85-135">ログオンしてサイト内の各アプライアンスを展開するときに、現在のログオンアカウントが**サイトディレクトリ**に対して適切なアクセス権を持っていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="14f85-135">When you log on and deploy each appliance in the site, make sure your current logon account has the right access to the **Site Directory**.</span></span>

3. <span data-ttu-id="14f85-136">**アプライアンスディレクトリ**は、Skype For Business Cloud Connector エディションのローカルの作業ルートディレクトリであり、外部の証明書、インスタンス、およびログが保存される場所です。</span><span class="sxs-lookup"><span data-stu-id="14f85-136">The **Appliance Directory** is the local working root directory for Skype for Business Cloud Connector Edition, and the location where external certificates, instances, and logs are saved.</span></span> <span data-ttu-id="14f85-137">既定の場所は次のとおりです。%USERPROFILE%\CloudConnector\ApplianceRoot.</span><span class="sxs-lookup"><span data-stu-id="14f85-137">The default location is: %USERPROFILE%\CloudConnector\ApplianceRoot.</span></span>

    <span data-ttu-id="14f85-138">**アプライアンスディレクトリ**の場所を見つけるには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="14f85-138">To find the location of the **Appliance Directory**, run the following cmdlet:</span></span>

   ```powershell
   Get-CcApplianceDirectory
   ```

    <span data-ttu-id="14f85-139">**アプライアンスディレクトリ**を既定以外の場所に設定するには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="14f85-139">To set the **Appliance Directory** to a location other than the default, run the following cmdlet:</span></span>

   ```powershell
   Set-CcApplianceDirectory <File path>
   ```

    <span data-ttu-id="14f85-140">アプライアンスのディレクトリは、アプライアンスのローカルフォルダーに設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="14f85-140">The Appliance Directory should be set to a local folder on the appliance.</span></span> <span data-ttu-id="14f85-141">Skype for Business Cloud Connector エディションの展開を開始する前に、**アプライアンスディレクトリ**のみを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="14f85-141">You should only set the **Appliance Directory** before you start the Skype for Business Cloud Connector Edition deployment.</span></span> <span data-ttu-id="14f85-142">展開後に変更する場合は、ホストサーバーを再展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="14f85-142">If you change it after deployment, you'll need to redeploy the host server.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="14f85-143">**アプライアンスディレクトリ**へのパスにスペースを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="14f85-143">The path to the **Appliance Directory** must not contain any spaces.</span></span>

## <a name="set-the-path-for-the-external-edge-certificate"></a><span data-ttu-id="14f85-144">外部エッジ証明書のパスを設定する</span><span class="sxs-lookup"><span data-stu-id="14f85-144">Set the path for the external Edge certificate</span></span>

- <span data-ttu-id="14f85-145">次のコマンドレットを実行して、ファイル名を含むパスを外部エッジ証明書に設定します。</span><span class="sxs-lookup"><span data-stu-id="14f85-145">Run the following cmdlet to set the path, including the file name, to the external Edge certificate.</span></span> <span data-ttu-id="14f85-146">例: C:\certs\cce\ap.contoso.com.pfx.</span><span class="sxs-lookup"><span data-stu-id="14f85-146">For example: C:\certs\cce\ap.contoso.com.pfx.</span></span> <span data-ttu-id="14f85-147">証明書には秘密キーが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="14f85-147">The certificate must contain private keys.</span></span>

  ```powershell
  Set-CcExternalCertificateFilePath -Path <Full path to External certificate, including file name> -Target EdgeServer
  ```

    > [!NOTE]
    > <span data-ttu-id="14f85-148">-Target パラメーターはバージョン1.4.2 以降に固有のものであることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="14f85-148">Note that the -Target parameter is specific to versions 1.4.2 and later.</span></span> 

    <span data-ttu-id="14f85-149">ファイル名を含む、外部証明書への完全パスを指定します。</span><span class="sxs-lookup"><span data-stu-id="14f85-149">Specify the full path to the external certificate, including the file name.</span></span> <span data-ttu-id="14f85-150">証明書は、ローカルまたはファイル共有に保存できます。</span><span class="sxs-lookup"><span data-stu-id="14f85-150">The certificate can be stored locally or on a file share.</span></span> <span data-ttu-id="14f85-151">証明書が共有フォルダーに格納されている場合は、共有フォルダーを各サイトの最初のアプライアンスに作成し、同じサイトに属する他のアプライアンスからアクセスできるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="14f85-151">If the certificate is stored in a shared folder, the shared folder must be created on the first appliance of each site and must be accessible by other appliances belonging to the same site.</span></span> <span data-ttu-id="14f85-152">このコマンドレットは、外部証明書を**アプライアンスディレクトリ**にコピーします。</span><span class="sxs-lookup"><span data-stu-id="14f85-152">This cmdlet copies the external certificate to the **Appliance Directory**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="14f85-153">**Cloud Connector バージョン1.4.2 以降に更新**した場合は、準備した外部証明書に秘密キーと、ルート ca 証明書と中間 CA 証明書を含む完全な証明書チェーンが含まれていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="14f85-153">**If you have updated to Cloud Connector version 1.4.2 or later**, make sure your prepared external certificate contains private keys and the full certificate chain including the root CA certificate and the intermediate CA certificates.</span></span> <span data-ttu-id="14f85-154">**Cloud Connector バージョン1.4.2 にまだ更新していない場合は**、準備した外部証明書に秘密キーが含まれていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="14f85-154">**If you have NOT yet updated to Cloud Connector version 1.4.2**, make sure your prepared external certificate contains private keys.</span></span> <span data-ttu-id="14f85-155">この外部証明書は、既定で Windows によって信頼されている証明機関によって発行される必要があります。</span><span class="sxs-lookup"><span data-stu-id="14f85-155">This external certificate must be issued by a Certificate Authority that is trusted by Windows by default.</span></span>

## <a name="set-the-path-for-the-external-pstn-gatewaysbc-certificate"></a><span data-ttu-id="14f85-156">外部 PSTN ゲートウェイ/SBC 証明書のパスを設定する</span><span class="sxs-lookup"><span data-stu-id="14f85-156">Set the path for the external PSTN gateway/SBC certificate</span></span>

<span data-ttu-id="14f85-157">仲介サーバーと PSTN ゲートウェイ/SBC 間で TLS を使用している場合は、次のコマンドレットを実行して、ファイル名を含むパスをゲートウェイ証明書に設定します。</span><span class="sxs-lookup"><span data-stu-id="14f85-157">If you are using TLS between the Mediation Server and the PSTN gateway/SBC, run the following cmdlet to set the path, including the file name, to the gateway certificate.</span></span> <span data-ttu-id="14f85-158">例: C:\certs\cce\sbc.contoso.com.cer.</span><span class="sxs-lookup"><span data-stu-id="14f85-158">For example: C:\certs\cce\sbc.contoso.com.cer.</span></span> <span data-ttu-id="14f85-159">この証明書には、ルート CA と、ゲートウェイに割り当てられた証明書の中間チェーンが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="14f85-159">The certificate must contain the root CA and the intermediate chain for the certificate assigned to the gateway:</span></span>

```powershell
Set-CcExternalCertificateFilePath -Path <Full path to gateway certificate, including file name> -Target MediationServer 
```

> [!NOTE]
> <span data-ttu-id="14f85-160">-Target パラメーターはバージョン1.4.2 以降に固有のものであることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="14f85-160">Note that the -Target parameter is specific to versions 1.4.2 and later.</span></span> 

## <a name="create-virtual-switches-in-hyper-v-manager"></a><span data-ttu-id="14f85-161">Hyper-v マネージャーで仮想スイッチを作成する</span><span class="sxs-lookup"><span data-stu-id="14f85-161">Create virtual switches in Hyper-V Manager</span></span>

1. <span data-ttu-id="14f85-162">**Hyper-v マネージャー** > の**仮想スイッチマネージャー**を開き、[**新しい仮想スイッチマネージャー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="14f85-162">Open **Hyper-V Manager** > **Virtual Switch Manager**, and select **New Virtual Switch Manager**.</span></span>

2. <span data-ttu-id="14f85-163">外部仮想スイッチを作成し、それを内部ネットワークドメインに接続されている物理ネットワークアダプターにバインドします。</span><span class="sxs-lookup"><span data-stu-id="14f85-163">Create an External virtual switch and bind it to the physical network adapter that is connected to your internal network domain:</span></span>

    <span data-ttu-id="14f85-164">この仮想スイッチに対して [**管理オペレーティングシステムによるこのネットワークアダプターの共有を許可する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="14f85-164">Select **Allow management operating system to share this network adapter** for this virtual switch.</span></span>

3. <span data-ttu-id="14f85-165">外部仮想スイッチを作成し、それをインターネットにルーティングされる物理ネットワークアダプターにバインドします。</span><span class="sxs-lookup"><span data-stu-id="14f85-165">Create an External virtual switch and bind it to the physical network adapter that is routed to the Internet:</span></span>

    <span data-ttu-id="14f85-166">この仮想スイッチに対して [**管理オペレーティングシステムによるこのネットワークアダプターの共有を許可する**] を選択解除します。</span><span class="sxs-lookup"><span data-stu-id="14f85-166">De-select **Allow management operating system to share this network adapter** for this virtual switch.</span></span>

4. <span data-ttu-id="14f85-167">境界ネットワークを内部ネットワークドメインの**Sfb**の企業向けスイッチに接続するスイッチの名前を設定します。</span><span class="sxs-lookup"><span data-stu-id="14f85-167">Set the name of the switch that connects your perimeter network to your internal network domain **SfB CCE Corpnet Switch**.</span></span>

    <span data-ttu-id="14f85-168">境界ネットワークをインターネットに接続するスイッチの名前を、 **Sfb CCE Internet switch**に設定します。</span><span class="sxs-lookup"><span data-stu-id="14f85-168">Set the name of the switch that connects your perimeter network to the Internet **SfB CCE Internet Switch**.</span></span>

## <a name="update-the-cloudconnectorini-configuration-file"></a><span data-ttu-id="14f85-169">CloudConnector の .ini 構成ファイルを更新する</span><span class="sxs-lookup"><span data-stu-id="14f85-169">Update the CloudConnector.ini configuration file</span></span>

<span data-ttu-id="14f85-170">「 [Plan For Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) 」の「[展開パラメーターの決定](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams)」で収集した情報を使用して、cloudconnector の .ini ファイルを準備します。</span><span class="sxs-lookup"><span data-stu-id="14f85-170">Prepare the CloudConnector.ini file using the information you gathered in [Determine deployment parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) in the [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) topic.</span></span>

<span data-ttu-id="14f85-171">ファイルを更新するには、最初に次のコマンドレットを実行して、サンプルテンプレート (CloudConnector. サンプル) を取得します。</span><span class="sxs-lookup"><span data-stu-id="14f85-171">To update the file, first run the following cmdlet to get the sample template (CloudConnector.Sample.ini):</span></span>

```powershell
Export-CcConfigurationSampleFile
```

<span data-ttu-id="14f85-172">サンプルテンプレートは**アプライアンスディレクトリ**に保存されます。</span><span class="sxs-lookup"><span data-stu-id="14f85-172">The sample template is stored in the **Appliance Directory**.</span></span>

<span data-ttu-id="14f85-173">使用している環境の値で更新した後、ファイルを CloudConnector .ini として**アプライアンスディレクトリ**に保存します。</span><span class="sxs-lookup"><span data-stu-id="14f85-173">After you update it with the values for your environment, save the file as CloudConnector.ini in the **Appliance Directory**.</span></span> <span data-ttu-id="14f85-174">**Set-ccappliancedirectory**を実行して、**アプライアンスディレクトリ**へのパスを確認できます。</span><span class="sxs-lookup"><span data-stu-id="14f85-174">You can run **Get-CcApplianceDirectory** to determine the path to the **Appliance Directory**.</span></span>

<span data-ttu-id="14f85-175">.Ini ファイルを更新するときは、次の点を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="14f85-175">When updating the .ini file, consider the following:</span></span>

> [!NOTE]
> <span data-ttu-id="14f85-176">このセクションでは .ini ファイルのすべての値について説明していませんが、特別な考慮事項のあるものだけをここで説明します。</span><span class="sxs-lookup"><span data-stu-id="14f85-176">Not all values for the .ini file are discussed in this section, only those with a special consideration are covered here.</span></span> <span data-ttu-id="14f85-177">完全なリストについては、「 [Plan For Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) 」の「[展開パラメーターの決定](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="14f85-177">For a full list, see the [Determine deployment parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) section of the [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) topic.</span></span> <span data-ttu-id="14f85-178">追加のアプライアンスまたは新しいサイトで変更する必要がある値の詳細については、「[複数のサイトをクラウドコネクタに展開](deploy-multiple-sites-in-cloud-connector.md)する」のトピックの「[単一サイトと高可用性 (HA)](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14f85-178">For more information about what values need to be changed for additional appliances or new sites, see [Single site with High Availability (HA) compared to multi-site deployments](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) in the topic [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 

- <span data-ttu-id="14f85-179">**SiteName:** 既定値は**Site1**です。</span><span class="sxs-lookup"><span data-stu-id="14f85-179">**SiteName:** The default value is **Site1**.</span></span> <span data-ttu-id="14f85-180">既存または新規のサイトにアプライアンスを登録するために**register**を実行すると、コマンドレットは**SiteName**を使用して登録するサイトを決定するため、Cloud Connector を展開する前に更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="14f85-180">You must update it before you deploy Cloud Connector, because when you run **Register-CcAppliance** to register an appliance to an existing or new site, the cmdlet will use **SiteName** to determine which site to register.</span></span>

     <span data-ttu-id="14f85-181">アプライアンスを新しいサイトに登録する場合は、 **SiteName**の値が一意で、既存のサイトとは異なるものである必要があります。</span><span class="sxs-lookup"><span data-stu-id="14f85-181">If you want to register the appliance to a new site, the value of **SiteName** must be unique and different from existing sites.</span></span> <span data-ttu-id="14f85-182">アプライアンスを既存のサイトに登録する場合は、.ini ファイルの**SiteName**の値は、Office 365 組織の構成で定義されている名前と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="14f85-182">If you want to register the appliance to an existing site, the value for **SiteName** in .ini file must match the name defined in your Office 365 organization configuration.</span></span> <span data-ttu-id="14f85-183">構成ファイルをあるサイトから別のサイトにコピーする場合は、各サイトの**SiteName**の値を適宜更新してください。</span><span class="sxs-lookup"><span data-stu-id="14f85-183">If you are copying a configuration file from one site to another, make sure you update the value for **SiteName** for each site accordingly.</span></span>

- <span data-ttu-id="14f85-184">**ServerName:** サーバー名にドメイン名を含めることはできず、15文字に制限する必要があります。</span><span class="sxs-lookup"><span data-stu-id="14f85-184">**ServerName:** The server name should not contain the domain name and should be limited to 15 characters.</span></span>

- <span data-ttu-id="14f85-185">**ハードウェアの種類:** 値を設定しない場合、または null 値のままにした場合は、既定値の**Normal**が使用されます。</span><span class="sxs-lookup"><span data-stu-id="14f85-185">**HardwareType:** If you don't set or leave the value to null, the default value of **Normal** will be used.</span></span> <span data-ttu-id="14f85-186">「 [Plan For Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md)」に記載されているように、ホストマシンごとに500の同時通話をサポートするために、より大規模な Cloud connector の展開を計画している場合は、 **Normal**を使用します。</span><span class="sxs-lookup"><span data-stu-id="14f85-186">Use **Normal** if you plan to deploy the larger version of Cloud Connector to support 500 simultaneous calls per host machine as described in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span> <span data-ttu-id="14f85-187">50の同時通話をサポートする小規模な展開には、**最小値**を使用します。</span><span class="sxs-lookup"><span data-stu-id="14f85-187">Use **Minimum** for a smaller deployment that supports 50 simultaneous calls.</span></span>

- <span data-ttu-id="14f85-188">**インターネット/社内/管理仮想スイッチ:**: 作成した仮想スイッチの名前を追加します。</span><span class="sxs-lookup"><span data-stu-id="14f85-188">**Internet/Corpnet/Management virtual switches:**: Add the name of the virtual switches you have created.</span></span> <span data-ttu-id="14f85-189">管理仮想スイッチの場合は、既定値のままにします。</span><span class="sxs-lookup"><span data-stu-id="14f85-189">For the management virtual switch, leave the default value.</span></span> <span data-ttu-id="14f85-190">展開スクリプトは、展開の開始時に管理仮想スイッチを作成し、展開が終了したら削除します。</span><span class="sxs-lookup"><span data-stu-id="14f85-190">The deployment script will create the management virtual switch at the beginning of deployment and delete it when the deployment finishes.</span></span>

- <span data-ttu-id="14f85-191">**Managementipprefix:**[ネットワーク] セクションの ManagementIPPrefix は、他の内部 Ip とは異なるサブネットである必要があります。</span><span class="sxs-lookup"><span data-stu-id="14f85-191">**ManagementIPPrefix:** ManagementIPPrefix in the Network section must be a different subnet from other internal IPs.</span></span> <span data-ttu-id="14f85-192">たとえば、既定値が示すように、ManagementIPPrefix は192.168.213.0 ですが、AD IPAddress は192.168.0.238 です。</span><span class="sxs-lookup"><span data-stu-id="14f85-192">For example, as the default value shows, ManagementIPPrefix is 192.168.213.0, while AD IPAddress is 192.168.0.238.</span></span>

    <span data-ttu-id="14f85-193">展開スクリプトは、各仮想マシンに管理ネットワークアダプターを作成し、管理 IP を割り当てて、それを管理仮想スイッチに接続します。</span><span class="sxs-lookup"><span data-stu-id="14f85-193">The deployment scripts create a management network adapter on each virtual machine, assign a management IP, and connect it to a management virtual switch.</span></span> <span data-ttu-id="14f85-194">これにより、ホストサーバーは、この管理ネットワークを介して各仮想マシンに接続して管理できるようになります。</span><span class="sxs-lookup"><span data-stu-id="14f85-194">This enables the host server to connect to and manage each virtual machine via this management network.</span></span> <span data-ttu-id="14f85-195">管理仮想スイッチは、展開が完了した時点で削除されます。</span><span class="sxs-lookup"><span data-stu-id="14f85-195">The management virtual switch is deleted when the deployment is finished.</span></span>

- <span data-ttu-id="14f85-196">**ベース VM 固有の構成:** このセクションの設定は、 **Convert-CcIsoToVhdx**コマンドレット用に構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="14f85-196">**Base VM specific configurations:** Settings in this section must be configured for the **Convert-CcIsoToVhdx** cmdlet.</span></span>

    <span data-ttu-id="14f85-197">ベース vm イメージの準備中に、ベース VM は内部ネットワークスイッチに接続されます。</span><span class="sxs-lookup"><span data-stu-id="14f85-197">During base VM image preparation, the base VM will be connected to the internal network switch.</span></span> <span data-ttu-id="14f85-198">次の設定は、VM がインターネットにアクセスできるようにするために重要です。</span><span class="sxs-lookup"><span data-stu-id="14f85-198">The following settings are critical for the VM to be able to access the Internet:</span></span>

  - <span data-ttu-id="14f85-199">一般的なBaseVMIP: ベース VM に割り当てる社内 IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="14f85-199">[Common]BaseVMIP: the corpnet IP address to be assigned to the base VM.</span></span>

  - <span data-ttu-id="14f85-200">LanCorpnetDefaultGateway: ベース VM に割り当てられる既定のゲートウェイ。</span><span class="sxs-lookup"><span data-stu-id="14f85-200">[Network]CorpnetDefaultGateway: the default gateway to be assigned to the base VM.</span></span>

  - <span data-ttu-id="14f85-201">LanCorpnetDNSIPAddress: ベース VM に割り当てる DNS IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="14f85-201">[Network]CorpnetDNSIPAddress: the DNS IP address to be assigned to the base VM.</span></span>

  - <span data-ttu-id="14f85-202">LanWSUSServer: Windows Server Update Service の IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="14f85-202">[Network]WSUSServer: the IP address of Windows Server Update Service.</span></span>

  - <span data-ttu-id="14f85-203">LanWSUSStatusServer: Windows Server Update Service の状態サーバーの IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="14f85-203">[Network]WSUSStatusServer: the IP address of Windows Server Update Service status server.</span></span>

  - <span data-ttu-id="14f85-204">LanEnableReferSupport: IP/PBX へのトランク構成で SIP 参照サポートが有効または無効になっているかどうかを定義します。</span><span class="sxs-lookup"><span data-stu-id="14f85-204">[Network]EnableReferSupport: this will define whether SIP REFER support is enabled or disabled on the Trunk Configuration to your IP/PBX.</span></span>

- <span data-ttu-id="14f85-205">**内部 Ip:**</span><span class="sxs-lookup"><span data-stu-id="14f85-205">**Internal IPs:**</span></span>

  - <span data-ttu-id="14f85-206">サブネットマスク CorpnetIPPrefixLength が正しいことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="14f85-206">Make sure subnet mask CorpnetIPPrefixLength is correct.</span></span>

  - <span data-ttu-id="14f85-207">これらの内部 ip に IP 競合がないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="14f85-207">Make sure there are no IP conflicts for these internal IPs.</span></span>

- <span data-ttu-id="14f85-208">**外部 Ip:**</span><span class="sxs-lookup"><span data-stu-id="14f85-208">**External IPs:**</span></span>

  - <span data-ttu-id="14f85-209">MR パブリック IP の場合: nat 以外の場合は ExternalMRIPs を指定し、NAT の場合は ExternalMRPublicIPs を指定します。</span><span class="sxs-lookup"><span data-stu-id="14f85-209">For MR public IP: specify either ExternalMRIPs for non-NAT or ExternalMRPublicIPs for NAT.</span></span>

  - <span data-ttu-id="14f85-210">ExternalSIPIPs と Externalsipips は同じでもかまいません。</span><span class="sxs-lookup"><span data-stu-id="14f85-210">ExternalSIPIPs and ExternalMRIPs can be the same.</span></span>

  - <span data-ttu-id="14f85-211">サブネットマスクの Interne"ヒントのプレフィックスが正しいことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="14f85-211">Make sure subnet mask InternetIPPrefixLength is correct.</span></span>

  - <span data-ttu-id="14f85-212">これらの外部 Ip に IP 競合がないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="14f85-212">Make sure there are no IP conflicts for these external IPs.</span></span>

- <span data-ttu-id="14f85-213">**ゲートウェイ**</span><span class="sxs-lookup"><span data-stu-id="14f85-213">**Gateways:**</span></span>

  - <span data-ttu-id="14f85-214">ゲートウェイが1つしかない場合は、セカンダリゲートウェイのセクションを削除します。</span><span class="sxs-lookup"><span data-stu-id="14f85-214">If you have only one gateway, remove the section for the secondary gateway.</span></span> <span data-ttu-id="14f85-215">3つ以上のゲートウェイがある場合は、既存の複数のセクションをコピーして貼り付け、更新することによって、追加のセクションを作成します。</span><span class="sxs-lookup"><span data-stu-id="14f85-215">If you have more than two gateways, create additional sections by copying and pasting the existing one and then updating it.</span></span>

  - <span data-ttu-id="14f85-216">ゲートウェイの IP アドレスとポートが正しいことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="14f85-216">Make sure that the IP address and port of the gateway(s) are correct.</span></span>

  - <span data-ttu-id="14f85-217">PSTN ゲートウェイレベルの HA をサポートするには、セカンダリゲートウェイを残し、使用するゲートウェイを追加します。</span><span class="sxs-lookup"><span data-stu-id="14f85-217">To support PSTN gateway level HA, leave the secondary gateway, and add any additional gateways you will use.</span></span> <span data-ttu-id="14f85-218">既存のエントリをコピーして貼り付け、更新することができます。</span><span class="sxs-lookup"><span data-stu-id="14f85-218">You can copy and paste an existing entry and then update it.</span></span>

- <span data-ttu-id="14f85-219">必要に応じて、LocalRoute 値を更新して発信通話番号を制限することもできます。</span><span class="sxs-lookup"><span data-stu-id="14f85-219">Optionally, you can update the LocalRoute value to restrict outbound call numbers.</span></span>

## <a name="download-the-bits-to-the-site-directory"></a><span data-ttu-id="14f85-220">サイトディレクトリにビットをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="14f85-220">Download the bits to the Site Directory</span></span>

<span data-ttu-id="14f85-221">次のコマンドレットを実行して、bits およびバージョン情報ファイルを**サイトディレクトリ**にダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="14f85-221">Run the following cmdlet to download the bits and version information files to the **Site Directory**:</span></span>

```powershell
Start-CcDownload
```

> [!NOTE]
> <span data-ttu-id="14f85-222">最初のアプライアンスのみに対してこの手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="14f85-222">You need to perform this step for the first appliance only.</span></span> 

## <a name="prepare-base-virtual-disk-vhdx-from-the-downloaded-iso-file"></a><span data-ttu-id="14f85-223">ダウンロードした ISO ファイルからベース仮想ディスク (VHDX) を準備する</span><span class="sxs-lookup"><span data-stu-id="14f85-223">Prepare base virtual disk (VHDX) from the downloaded ISO file</span></span>

<span data-ttu-id="14f85-224">この手順では、Windows Server 2012 ISO イメージから仮想ハードディスク (VHDX) ファイルを準備します。</span><span class="sxs-lookup"><span data-stu-id="14f85-224">This step prepares a virtual hard disk (VHDX) file from the Windows Server 2012 ISO image.</span></span> <span data-ttu-id="14f85-225">VHDX は、展開時に仮想マシンを作成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="14f85-225">The VHDX will be used to create virtual machines during deployment.</span></span> <span data-ttu-id="14f85-226">一時仮想マシン (ベース VM) が作成され、ISO ファイルから Windows Server 2012 がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="14f85-226">A temporary virtual machine (base VM) will be created and Windows Server 2012 will be installed from the ISO file.</span></span> <span data-ttu-id="14f85-227">VM を作成すると、必要なコンポーネントがいくつかインストールされ、最新の Windows 更新プログラムが適用されます。</span><span class="sxs-lookup"><span data-stu-id="14f85-227">After the VM is created, some necessary components will be installed and the latest Windows update will be applied.</span></span> <span data-ttu-id="14f85-228">最後に、ベース VM は一般化 (sysprep) されクリーンアップされ、生成された仮想ディスクファイルのみが残されます。</span><span class="sxs-lookup"><span data-stu-id="14f85-228">At the end, the base VM will be generalized (sysprep) and cleaned up, leaving only the generated virtual disk file.</span></span>

> [!NOTE]
> <span data-ttu-id="14f85-229">最初のアプライアンスのみに対してこの手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="14f85-229">You need to perform this step for the first appliance only.</span></span> 

<span data-ttu-id="14f85-230">この手順を進める前に、企業ネットワークスイッチが作成されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="14f85-230">Before proceeding with this step, make sure that the corpnet switch is created.</span></span> <span data-ttu-id="14f85-231">また、次の設定が CloudConnector .ini ファイルで正しく構成されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="14f85-231">Also, confirm that the following settings are correctly configured in the CloudConnector.ini file:</span></span>

- <span data-ttu-id="14f85-232">LanCorpnetSwitchName</span><span class="sxs-lookup"><span data-stu-id="14f85-232">[Network]CorpnetSwitchName</span></span>

- <span data-ttu-id="14f85-233">一般的なBaseVMIP</span><span class="sxs-lookup"><span data-stu-id="14f85-233">[Common]BaseVMIP</span></span>

- <span data-ttu-id="14f85-234">LanCorpnetIPPrefixLength</span><span class="sxs-lookup"><span data-stu-id="14f85-234">[Network]CorpnetIPPrefixLength</span></span>

- <span data-ttu-id="14f85-235">LanCorpnetDefaultGateway</span><span class="sxs-lookup"><span data-stu-id="14f85-235">[Network]CorpnetDefaultGateway</span></span>

- <span data-ttu-id="14f85-236">LanCorpnetDNSIPAddress</span><span class="sxs-lookup"><span data-stu-id="14f85-236">[Network]CorpnetDNSIPAddress</span></span>

<span data-ttu-id="14f85-237">管理者として PowerShell コンソールを起動し、次のコマンドレットを実行して、ISO イメージを仮想ハードディスク (VHD) に変換します。</span><span class="sxs-lookup"><span data-stu-id="14f85-237">Start a PowerShell console as administrator and run the following cmdlet to convert the ISO image to a virtual hard disk (VHD):</span></span>

```powershell
Convert-CcIsoToVhdx -IsoFilePath <Windows ISO File Path, including file name>
```

<span data-ttu-id="14f85-238">ISO イメージの完全パス (ファイル名を含む) を指定します。</span><span class="sxs-lookup"><span data-stu-id="14f85-238">Specify the full path, including file name, to the ISO image.</span></span> <span data-ttu-id="14f85-239">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="14f85-239">For example: C:\ISO\WindowsServer2012R2.iso.</span></span>

<span data-ttu-id="14f85-240">作成された VHD ファイルは、**サイトディレクトリ**\ bit\ vhd フォルダーに格納されます。</span><span class="sxs-lookup"><span data-stu-id="14f85-240">The created VHD file is stored in the **Site Directory** \Bits\VHD folder.</span></span> <span data-ttu-id="14f85-241">**取得-CcSiteDirectory**を実行することにより、**サイトディレクトリ**へのパスを取得することができます。</span><span class="sxs-lookup"><span data-stu-id="14f85-241">You can get the path to the **Site Directory** by running the **Get-CcSiteDirectory**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="14f85-242">既定では、ベース VM でプロキシ設定が構成されていません。</span><span class="sxs-lookup"><span data-stu-id="14f85-242">By default, proxy settings are not configured on the base VM.</span></span> <span data-ttu-id="14f85-243">Windows Update を介して VM を更新するためにネットワーク環境でプロキシが必要な場合は、"Convert-CcIsoToVhdx" を実行するときに-PauseBeforeUpdate スイッチを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="14f85-243">If a proxy is required in your network environment to update the VM via Windows Update, you should add the -PauseBeforeUpdate switch when you run "Convert-CcIsoToVhdx".</span></span> <span data-ttu-id="14f85-244">このスクリプトは、Windows Update の前に一時停止し、VM でプロキシを手動でセットアップする機会があります。</span><span class="sxs-lookup"><span data-stu-id="14f85-244">The script will pause before Windows Update and you'll have a chance to manually set up proxy on the VM.</span></span> <span data-ttu-id="14f85-245">プロキシがセットアップされ、VM がインターネットにアクセスできるようになったら、スクリプトを再開して残りの手順を完了できます。</span><span class="sxs-lookup"><span data-stu-id="14f85-245">After the proxy is setup and the VM can access Internet, you can resume the script to complete the remaining steps.</span></span> 

### <a name="create-vhds-for-a-multi-site-deployment"></a><span data-ttu-id="14f85-246">複数サイト展開用の Vhd を作成する</span><span class="sxs-lookup"><span data-stu-id="14f85-246">Create VHDs for a multi-site deployment</span></span>

<span data-ttu-id="14f85-247">これは、複数サイト展開のみに適用されるオプションの手順です。</span><span class="sxs-lookup"><span data-stu-id="14f85-247">This is an optional step that applies only to multi-site deployments.</span></span>

<span data-ttu-id="14f85-248">複数サイト展開を展開する場合は、各サイトの ISO を VHD に変換する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="14f85-248">If you are deploying a multi-site deployment, you do not need to convert the ISO to a VHD for each site.</span></span> <span data-ttu-id="14f85-249">最初のサイト用に作成された VHDX を、2番目のサイトのホストサーバーにコピーできます。</span><span class="sxs-lookup"><span data-stu-id="14f85-249">You can copy the VHDX created for the first site to the host server for a second site.</span></span>

 <span data-ttu-id="14f85-250">別のサイトのホストサーバー上で、同じファイルの場所 (**サイトディレクトリ**\ ビット \ VHD フォルダー) に同じファイル名を使用してファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="14f85-250">Copy the file to the same file location ( **Site Directory** \Bits\VHD folder), and with the same file name, on the host server for an additional site.</span></span>

## <a name="set-the-powershell-execution-policy-to-remotesigned"></a><span data-ttu-id="14f85-251">PowerShell 実行ポリシーを RemoteSigned に設定します。</span><span class="sxs-lookup"><span data-stu-id="14f85-251">Set the PowerShell Execution policy to RemoteSigned</span></span>

<span data-ttu-id="14f85-252">提供されている PowerShell スクリプトでは、実行ポリシーを RemoteSigned に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="14f85-252">The PowerShell scripts provided require that the execution policy be set to RemoteSigned.</span></span> <span data-ttu-id="14f85-253">現在の設定を表示するには、管理者として PowerShell コンソールを開き、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="14f85-253">To see the current setting, open a PowerShell console as administrator and then run the following cmdlet:</span></span>

```powershell
Get-ExecutionPolicy
```

<span data-ttu-id="14f85-254">"RemoteSigned" に設定されていない場合は、次のコマンドレットを実行して変更します。</span><span class="sxs-lookup"><span data-stu-id="14f85-254">If it is not set to "RemoteSigned," run the following cmdlet to change it:</span></span>

```powershell
Set-ExecutionPolicy RemoteSigned
```

## <a name="change-local-group-policy-on-the-host-machine-versions-141-and-earlier"></a><span data-ttu-id="14f85-255">ホストマシンのローカルグループポリシーを変更する (バージョン1.4.1 以前)</span><span class="sxs-lookup"><span data-stu-id="14f85-255">Change local Group Policy on the host machine (versions 1.4.1 and earlier)</span></span>

> [!NOTE]
> <span data-ttu-id="14f85-256">このタスクは、Cloud Connector バージョン1.4.2 以降では必要ありません。</span><span class="sxs-lookup"><span data-stu-id="14f85-256">This task is not required for Cloud Connector versions 1.4.2 and later.</span></span> 

<span data-ttu-id="14f85-257">CceService アカウントは、Skype for Business Cloud Connector エディションの展開時に作成されます。</span><span class="sxs-lookup"><span data-stu-id="14f85-257">The CceService account is created during the Skype for Business Cloud Connector Edition deployment.</span></span> <span data-ttu-id="14f85-258">Cloud Connector Management Service を実行し、cloudconnector をアンインストールするためのアクセス許可を必要とします。</span><span class="sxs-lookup"><span data-stu-id="14f85-258">It runs the Cloud Connector Management Service and requires permission to uninstall the cloudconnector.msi.</span></span> <span data-ttu-id="14f85-259">ユーザーがログオフしたときにユーザーのレジストリをアンロードしないように指定するには、Cloud Connector ホストコンピューターのグループポリシー設定を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="14f85-259">You must change the group policy setting on the Cloud Connector host machine to specify that the user registry should not be unloaded when the user logs off.</span></span> <span data-ttu-id="14f85-260">次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="14f85-260">Follow the steps below:</span></span>

### <a name="to-change-the-group-policy-setting"></a><span data-ttu-id="14f85-261">グループポリシー設定を変更するには</span><span class="sxs-lookup"><span data-stu-id="14f85-261">To change the Group Policy setting</span></span>

1. <span data-ttu-id="14f85-262">Gpedit.msc を実行して**グループポリシーエディター**を開きます。</span><span class="sxs-lookup"><span data-stu-id="14f85-262">Open the **Group Policy Editor** by running gpedit.msc.</span></span>

2. <span data-ttu-id="14f85-263">**グループポリシーエディター**で、[管理用テンプレート > System > > UserProfile] に移動します。ユーザーのログオフ時に強制的にユーザーレジストリをアンロードしないようにします。</span><span class="sxs-lookup"><span data-stu-id="14f85-263">In the **Group Policy Editor**, navigate to Administrative Templates > System > UserProfile > Do not forcefully unload the user registry at user logoff.</span></span> 

3. <span data-ttu-id="14f85-264">その値を**有効**に設定します。</span><span class="sxs-lookup"><span data-stu-id="14f85-264">Set its value to **Enabled**.</span></span>

## <a name="set-up-your-office-365-organization"></a><span data-ttu-id="14f85-265">Office 365 組織をセットアップする</span><span class="sxs-lookup"><span data-stu-id="14f85-265">Set up your Office 365 organization</span></span>

<span data-ttu-id="14f85-266">Office 365 組織は、Skype for Business Online と Office 365 の電話システムを使用している必要があります。</span><span class="sxs-lookup"><span data-stu-id="14f85-266">An Office 365 organization with Skype for Business Online and Phone System in Office 365 is required.</span></span> <span data-ttu-id="14f85-267">Cloud Connector を使用する前に、テナントがセットアップおよび構成されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="14f85-267">Make sure your tenant is set up and configured before attempting to use Cloud Connector.</span></span>

<span data-ttu-id="14f85-268">Office 365 のセットアップ手順によっては、テナントのリモート PowerShell (TRPS) を使用して Office 365 組織を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="14f85-268">Some Office 365 setup steps require you to use Tenant Remote PowerShell (TRPS) to configure your Office 365 organization.</span></span> <span data-ttu-id="14f85-269">**これは、ホストサーバーにインストールする必要があります。**</span><span class="sxs-lookup"><span data-stu-id="14f85-269">**This should be installed on the host server.**</span></span> <span data-ttu-id="14f85-270">PowerShell の Skype for Business Online モジュールは、「 [skype For Business online, Windows PowerShell モジュール」](https://www.microsoft.com/download/details.aspx?id=39366)からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="14f85-270">You can download the Skype for Business Online module for PowerShell from: [Skype for Business Online, Windows PowerShell Module](https://www.microsoft.com/download/details.aspx?id=39366).</span></span>

<span data-ttu-id="14f85-271">Cloud Connector online management に専用の Skype for Business 管理者アカウントを作成します (例: CceOnlineManagmentAdministrator)。</span><span class="sxs-lookup"><span data-stu-id="14f85-271">Create a dedicated Skype for Business administrator account for Cloud Connector online management, for example CceOnlineManagmentAdministrator.</span></span> <span data-ttu-id="14f85-272">このアカウントはアプライアンスによって使用され、アプライアンスを追加または削除したり、自動 OS 更新を有効または無効にしたり、自動バイナリ更新を有効または無効にしたりします。</span><span class="sxs-lookup"><span data-stu-id="14f85-272">This account will be used by appliance to add or remove appliance, enable or disable automatic OS update, enable or disable automatic binary update.</span></span> <span data-ttu-id="14f85-273">このアカウントのパスワードを期限切れにならないように設定します。これにより、有効期限が切れるたびにサービスのパスワードを変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="14f85-273">Set the password for this account to never expire so that you do not need to change it for the service each time it expires.</span></span>


