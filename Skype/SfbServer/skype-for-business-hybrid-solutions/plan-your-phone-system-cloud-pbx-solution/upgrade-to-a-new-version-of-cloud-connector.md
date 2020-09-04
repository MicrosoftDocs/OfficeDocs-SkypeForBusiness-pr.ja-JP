---
title: Cloud Connector 新バージョンへのアップグレード
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: efbe25f2-faf5-41c7-8c95-dbc4a835a4a8
description: Cloud Connector エディションの展開をアップグレードする方法について説明します。
ms.openlocfilehash: dc9473dbf605f00df76daa1a88a29c7d5ed65fd8
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359293"
---
# <a name="upgrade-to-a-new-version-of-cloud-connector"></a><span data-ttu-id="e284b-103">Cloud Connector 新バージョンへのアップグレード</span><span class="sxs-lookup"><span data-stu-id="e284b-103">Upgrade to a new version of Cloud Connector</span></span>

> [!Important]
> <span data-ttu-id="e284b-104">Cloud Connector エディションは、2021年7月31日、Skype for Business Online と共に廃止されます。</span><span class="sxs-lookup"><span data-stu-id="e284b-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="e284b-105">組織が Teams にアップグレードされたら、 [直接ルーティング](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)を使用してオンプレミスのテレフォニーネットワークを teams に接続する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e284b-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>
 
<span data-ttu-id="e284b-106">Cloud Connector エディションの展開をアップグレードする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e284b-106">Learn about how to upgrade your Cloud Connector Edition deployment.</span></span>
  
<span data-ttu-id="e284b-107">オンライン管理テナントアカウントを設定し、自動更新を有効にしている場合、既存の Skype for Business Cloud Connector エディションの展開は、自動更新の時間枠の構成に従って、新しいバージョンに自動的にアップグレードされます。</span><span class="sxs-lookup"><span data-stu-id="e284b-107">If you have set up an online management tenant account and enabled automatic updates, your existing deployment of Skype for Business Cloud Connector Edition will be upgraded to the newer version automatically—according to your automatic update time window configuration.</span></span> <span data-ttu-id="e284b-108">手動アップグレードを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="e284b-108">You can also perform a manual upgrade.</span></span> 
  
<span data-ttu-id="e284b-109">Cloud Connector Edition バージョン1.4.1 以降では、既定で自動更新が実行されます。</span><span class="sxs-lookup"><span data-stu-id="e284b-109">Cloud Connector Edition versions 1.4.1 and later perform automatic updates by default.</span></span> <span data-ttu-id="e284b-110">最新バージョン (2.1) に手動でアップグレードする場合は、このトピックで後述する「 [1 つのサイトを新しいバージョンにアップグレード](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e284b-110">If you want to upgrade to the latest version (2.1) manually, see [Upgrade a single site to a new version](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) later in this topic.</span></span>
  
<span data-ttu-id="e284b-111">自動更新では、Cloud Connector service が実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e284b-111">Automatic update requires that the Cloud Connector service is running.</span></span> <span data-ttu-id="e284b-112">次の手順では、自動更新のプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="e284b-112">The following steps describe the process for automatic updates:</span></span>
  
- <span data-ttu-id="e284b-113">自動更新プロセスは、自動更新のために構成したスケジュールに従って実行されます。</span><span class="sxs-lookup"><span data-stu-id="e284b-113">The automatic update process will run according to the schedule you have configured for automatic updates.</span></span>
    
- <span data-ttu-id="e284b-114">オペレーティングシステムの更新タスク</span><span class="sxs-lookup"><span data-stu-id="e284b-114">Operating system update tasks</span></span>
    
  - <span data-ttu-id="e284b-115">すべての Cloud Connector Vm に対するオペレーティングシステムの更新プログラムを確認してダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="e284b-115">Check and download operating system updates to all Cloud Connector VMs.</span></span> 
    
  - <span data-ttu-id="e284b-116">すべての Cloud Connector Vm を1つずつインストールして更新し、再起動します。</span><span class="sxs-lookup"><span data-stu-id="e284b-116">Install and update all Cloud Connector VMs one by one and restart.</span></span>
    
  - <span data-ttu-id="e284b-117">Cloud Connector Vm が再起動したら、別の再起動が必要かどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="e284b-117">After the Cloud Connector VMs restart, check to see if another restart is needed.</span></span>
    
  - <span data-ttu-id="e284b-118">Cloud Connector Vm が正常にパッチされたら、Cloud Connector ホストコンピューターのプロセスを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="e284b-118">After the Cloud Connector VMs have been successfully patched, repeat the process for the Cloud Connector host machine.</span></span>
    
  - <span data-ttu-id="e284b-119">Cloud Connector ホストマシンが正常に起動すると、すべての未解決のオペレーティングシステムの更新タスクが完了します。</span><span class="sxs-lookup"><span data-stu-id="e284b-119">After the Cloud Connector host machine successfully boots up, any outstanding operating system update tasks are completed.</span></span>
    
- <span data-ttu-id="e284b-120">Cloud Connector の更新タスク</span><span class="sxs-lookup"><span data-stu-id="e284b-120">Cloud Connector update tasks</span></span>
    
  - <span data-ttu-id="e284b-121">ダウンロードサイトからバージョンファイルをダウンロードして確認します。</span><span class="sxs-lookup"><span data-stu-id="e284b-121">Download and check the version file from the download site.</span></span>
    
  - <span data-ttu-id="e284b-122">新しいバージョンの .msi ファイルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="e284b-122">Download the new version .msi file.</span></span> 
    
  - <span data-ttu-id="e284b-123">古い msi ファイルをアンインストールします。新しい msi ファイルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="e284b-123">Uninstall the old msi file; install the new msi file.</span></span>
    
  - <span data-ttu-id="e284b-124">新しいバージョンの Skype for Business ビットをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="e284b-124">Download the new version of Skype for Business bits.</span></span>
    
  - <span data-ttu-id="e284b-125">Register-CcAppliance を呼び出してアプライアンスを登録します。</span><span class="sxs-lookup"><span data-stu-id="e284b-125">Register the appliance by calling Register-CcAppliance.</span></span>
    
  - <span data-ttu-id="e284b-126">新しい Cloud Connector のバージョンをインストールします。</span><span class="sxs-lookup"><span data-stu-id="e284b-126">Install the new Cloud Connector version.</span></span>
    
  - <span data-ttu-id="e284b-127">古いアプライアンスをドレインし、ネットワーク接続を新しいアプライアンスに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="e284b-127">Drain the old appliance and switch the network connection to the new appliance.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="e284b-128">Cloud Connector が新しいビルドに更新された場合、Cloud Connector コマンドレットは更新されない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e284b-128">When Cloud Connector updates to a new build, Cloud Connector cmdlets might not be updated.</span></span> <span data-ttu-id="e284b-129">これは、自動更新の実行中に PowerShell ウィンドウを開いたままにした場合などに発生します。</span><span class="sxs-lookup"><span data-stu-id="e284b-129">This can happen, for example, if a PowerShell window is left open while automatic update occurs.</span></span> <span data-ttu-id="e284b-130">更新されたコマンドレットを読み込むには、次のいずれかの手順を実行します。 Cloud Connector アプライアンスで PowerShell を > てから、PowerShell をもう一度開いてください。または、> を実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="e284b-130">To load the updated cmdlets, you can do either of the following steps:>  Close PowerShell on the Cloud Connector appliance, and then reopen PowerShell.>  Or, you can run Import-Module CloudConnector -Force.</span></span>
  
## <a name="upgrade-a-single-site-to-a-new-version"></a><span data-ttu-id="e284b-131">1つのサイトを新しいバージョンにアップグレードする</span><span class="sxs-lookup"><span data-stu-id="e284b-131">Upgrade a single site to a new version</span></span>
<span data-ttu-id="e284b-132"><a name="BKMK_Upgrade"> </a></span><span class="sxs-lookup"><span data-stu-id="e284b-132"><a name="BKMK_Upgrade"> </a></span></span>

<span data-ttu-id="e284b-133">アップグレードするサイトにアプライアンスが1つだけある場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e284b-133">If there is only one appliance in the site you want to upgrade, do the following:</span></span>
  
1. <span data-ttu-id="e284b-134">**コントロールパネルの \> [プログラム \> と機能]** で既存の Cloud Connector のバージョンをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="e284b-134">Uninstall the existing Cloud Connector version in **Control Panel \> Programs \> Programs and Features**.</span></span>
    
2. <span data-ttu-id="e284b-135">新しいバージョンの CloudConnector.msi をからインストール [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) します。</span><span class="sxs-lookup"><span data-stu-id="e284b-135">Install the new version of CloudConnector.msi from [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span>
    
3. <span data-ttu-id="e284b-136">インストールしているバージョンの CloudConnector.ini ファイルがあること、および環境に必要なすべての値が更新されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e284b-136">Confirm that you have the CloudConnector.ini file for the version you are installing, and that you have updated all of the required values for your environment.</span></span> <span data-ttu-id="e284b-137">以前のリリースから .ini ファイルを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="e284b-137">You cannot use the .ini file from a previous release.</span></span> <span data-ttu-id="e284b-138">Cloud Connector をアップグレードする場合は、「 [Cloud connector を準備](prepare-your-cloud-connector-appliance.md) する」および「SiteName と EnableReferSupport が CloudConnector.ini ファイルの正しい値に設定されていることを確認してください」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e284b-138">If you are upgrading Cloud Connector, please refer to the topic [Prepare your Cloud Connector appliance](prepare-your-cloud-connector-appliance.md) and make sure SiteName and EnableReferSupport are set to the correct value in the CloudConnector.ini file.</span></span>
    
4. <span data-ttu-id="e284b-139">管理者として PowerShell コンソールを起動し、次のコマンドレットを実行して現在のアプライアンスを登録します。</span><span class="sxs-lookup"><span data-stu-id="e284b-139">Start a PowerShell console as administrator and run the following cmdlet to register the current appliance:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

5. <span data-ttu-id="e284b-140">次のコマンドレットを実行して、最新バージョンをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="e284b-140">Run the following cmdlet to download the latest version:</span></span>
    
   ```powershell
   Start-CcDownload
   ```

6. <span data-ttu-id="e284b-141">次のコマンドレットを実行して、インストールを開始します。</span><span class="sxs-lookup"><span data-stu-id="e284b-141">Run the following cmdlet to start the installation:</span></span> 
    
   ```powershell
   Install-CcAppliance -Upgrade
   ```

7. <span data-ttu-id="e284b-142">次のコマンドレットを実行して、新しい展開をアクティブ化し、以前のバージョンをオフにします。</span><span class="sxs-lookup"><span data-stu-id="e284b-142">Run the following cmdlet to activate the new deployment and turn off the previous version:</span></span>
    
   ```powershell
   Switch-CcVersion
   ```

<span data-ttu-id="e284b-143">サイト内に複数のアプライアンスがある場合は、前の手順に従って各アプライアンスを1つずつアップグレードしてください。</span><span class="sxs-lookup"><span data-stu-id="e284b-143">If there is more than one appliance in the site, please follow the preceding steps to upgrade each appliance one by one.</span></span>
  
<span data-ttu-id="e284b-144">ドメイン管理者、仮想マシン管理者、セーフモード管理者、テナント管理者の資格情報を更新する場合は、  _Updateallcredentials_ パラメーターを指定してコマンドレットを実行すると、すべての資格情報をリセットできます。</span><span class="sxs-lookup"><span data-stu-id="e284b-144">If you want to update Domain administrator, Virtual machine administrator, Safe Mode administrator and Tenant administrator credentials, you can run the cmdlet with the  _UpdateAllCredentials_ parameter to reset all credentials:</span></span>
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

<span data-ttu-id="e284b-145">その後、新しいバージョンへのアップグレードを開始すると、新しい資格情報を入力するように求められます。</span><span class="sxs-lookup"><span data-stu-id="e284b-145">Then, when you start to upgrade to a new version, you will be promoted to input the new credentials.</span></span> 
  
<span data-ttu-id="e284b-146">テナント管理者の資格情報のみをリセットする場合は、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="e284b-146">If you only want to reset your Tenant administrator credentials, run the following cmdlet:</span></span>
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="upgrade-multiple-sites-to-a-new-version"></a><span data-ttu-id="e284b-147">複数のサイトを新しいバージョンにアップグレードする</span><span class="sxs-lookup"><span data-stu-id="e284b-147">Upgrade multiple sites to a new version</span></span>
<span data-ttu-id="e284b-148"><a name="BKMK_Upgrade"> </a></span><span class="sxs-lookup"><span data-stu-id="e284b-148"><a name="BKMK_Upgrade"> </a></span></span>

<span data-ttu-id="e284b-149">1つのサイトをアップグレードする手順を実行し、展開内のサイトごとに1つずつサイトをアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="e284b-149">Follow the steps for upgrading a single site, upgrading one site at a time for each site in your deployment.</span></span> <span data-ttu-id="e284b-150">各サイトをアップグレードした後 [に、Cloud Connector の展開](validate-your-cloud-connector-deployment.md) を確認して検証してください。</span><span class="sxs-lookup"><span data-stu-id="e284b-150">Make sure and [Validate your Cloud Connector deployment](validate-your-cloud-connector-deployment.md) after upgrading each site.</span></span>
  

