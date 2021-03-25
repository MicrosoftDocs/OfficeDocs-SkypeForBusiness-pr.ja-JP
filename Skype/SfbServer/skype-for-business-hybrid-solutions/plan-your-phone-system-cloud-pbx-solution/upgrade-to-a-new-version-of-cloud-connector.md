---
title: クラウド コネクタの新バージョンへのアップグレード
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
description: クラウド コネクタ エディションの展開をアップグレードする方法について説明します。
ms.openlocfilehash: fea78c6b1b6ba3b2e644fef71d78b94aa3a244b7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109133"
---
# <a name="upgrade-to-a-new-version-of-cloud-connector"></a><span data-ttu-id="819e2-103">クラウド コネクタの新バージョンへのアップグレード</span><span class="sxs-lookup"><span data-stu-id="819e2-103">Upgrade to a new version of Cloud Connector</span></span>

> [!Important]
> <span data-ttu-id="819e2-104">Cloud Connector Edition は、Skype for Business Online と共に 2021 年 7 月 31 日に廃止されます。</span><span class="sxs-lookup"><span data-stu-id="819e2-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="819e2-105">組織が Teams にアップグレードしたら、直接ルーティングを使用してオンプレミスのテレフォニー ネットワークを Teams に接続する方法 [について説明します](/MicrosoftTeams/direct-routing-landing-page)。</span><span class="sxs-lookup"><span data-stu-id="819e2-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>
 
<span data-ttu-id="819e2-106">クラウド コネクタ エディションの展開をアップグレードする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="819e2-106">Learn about how to upgrade your Cloud Connector Edition deployment.</span></span>
  
<span data-ttu-id="819e2-107">オンライン管理テナント アカウントをセットアップし、自動更新を有効にしている場合、Skype for Business Cloud Connector Edition の既存の展開は、自動更新のタイム ウィンドウ構成に従って、自動的に新しいバージョンにアップグレードされます。</span><span class="sxs-lookup"><span data-stu-id="819e2-107">If you have set up an online management tenant account and enabled automatic updates, your existing deployment of Skype for Business Cloud Connector Edition will be upgraded to the newer version automatically—according to your automatic update time window configuration.</span></span> <span data-ttu-id="819e2-108">手動アップグレードを実行できます。</span><span class="sxs-lookup"><span data-stu-id="819e2-108">You can also perform a manual upgrade.</span></span> 
  
<span data-ttu-id="819e2-109">Cloud Connector Edition バージョン 1.4.1 以降では、既定で自動更新が実行されます。</span><span class="sxs-lookup"><span data-stu-id="819e2-109">Cloud Connector Edition versions 1.4.1 and later perform automatic updates by default.</span></span> <span data-ttu-id="819e2-110">最新バージョン (2.1) に手動でアップグレードする場合は、[](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade)後の「単一サイトを新しいバージョンにアップグレードする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="819e2-110">If you want to upgrade to the latest version (2.1) manually, see [Upgrade a single site to a new version](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) later in this topic.</span></span>
  
<span data-ttu-id="819e2-111">自動更新では、クラウド コネクタ サービスが実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="819e2-111">Automatic update requires that the Cloud Connector service is running.</span></span> <span data-ttu-id="819e2-112">次の手順では、自動更新のプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="819e2-112">The following steps describe the process for automatic updates:</span></span>
  
- <span data-ttu-id="819e2-113">自動更新プロセスは、自動更新用に構成したスケジュールに従って実行されます。</span><span class="sxs-lookup"><span data-stu-id="819e2-113">The automatic update process will run according to the schedule you have configured for automatic updates.</span></span>
    
- <span data-ttu-id="819e2-114">オペレーティング システムの更新タスク</span><span class="sxs-lookup"><span data-stu-id="819e2-114">Operating system update tasks</span></span>
    
  - <span data-ttu-id="819e2-115">すべてのクラウド コネクタ VM に対するオペレーティング システムの更新プログラムを確認してダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="819e2-115">Check and download operating system updates to all Cloud Connector VMs.</span></span> 
    
  - <span data-ttu-id="819e2-116">すべてのクラウド コネクタ VM を 1 つ 1 つインストールして更新し、再起動します。</span><span class="sxs-lookup"><span data-stu-id="819e2-116">Install and update all Cloud Connector VMs one by one and restart.</span></span>
    
  - <span data-ttu-id="819e2-117">Cloud Connector VM の再起動後に、別の再起動が必要な場合に確認します。</span><span class="sxs-lookup"><span data-stu-id="819e2-117">After the Cloud Connector VMs restart, check to see if another restart is needed.</span></span>
    
  - <span data-ttu-id="819e2-118">Cloud Connector VM のパッチが正常に適用された後、クラウド コネクタ ホスト コンピューターのプロセスを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="819e2-118">After the Cloud Connector VMs have been successfully patched, repeat the process for the Cloud Connector host machine.</span></span>
    
  - <span data-ttu-id="819e2-119">クラウド コネクタ ホスト コンピューターが正常に起動すると、未処理のオペレーティング システム更新タスクが完了します。</span><span class="sxs-lookup"><span data-stu-id="819e2-119">After the Cloud Connector host machine successfully boots up, any outstanding operating system update tasks are completed.</span></span>
    
- <span data-ttu-id="819e2-120">クラウド コネクタの更新タスク</span><span class="sxs-lookup"><span data-stu-id="819e2-120">Cloud Connector update tasks</span></span>
    
  - <span data-ttu-id="819e2-121">ダウンロード サイトからバージョン ファイルをダウンロードして確認します。</span><span class="sxs-lookup"><span data-stu-id="819e2-121">Download and check the version file from the download site.</span></span>
    
  - <span data-ttu-id="819e2-122">新しいバージョンの .msi ファイルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="819e2-122">Download the new version .msi file.</span></span> 
    
  - <span data-ttu-id="819e2-123">古い msi ファイルをアンインストールします。新しい msi ファイルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="819e2-123">Uninstall the old msi file; install the new msi file.</span></span>
    
  - <span data-ttu-id="819e2-124">Skype for Business ビットの新しいバージョンをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="819e2-124">Download the new version of Skype for Business bits.</span></span>
    
  - <span data-ttu-id="819e2-125">Register-CcAppliance を呼び出してアプライアンスを登録します。</span><span class="sxs-lookup"><span data-stu-id="819e2-125">Register the appliance by calling Register-CcAppliance.</span></span>
    
  - <span data-ttu-id="819e2-126">新しいクラウド コネクタ バージョンをインストールします。</span><span class="sxs-lookup"><span data-stu-id="819e2-126">Install the new Cloud Connector version.</span></span>
    
  - <span data-ttu-id="819e2-127">古いアプライアンスをドレインし、ネットワーク接続を新しいアプライアンスに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="819e2-127">Drain the old appliance and switch the network connection to the new appliance.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="819e2-128">Cloud Connector が新しいビルドに更新される場合、Cloud Connector コマンドレットは更新されない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="819e2-128">When Cloud Connector updates to a new build, Cloud Connector cmdlets might not be updated.</span></span> <span data-ttu-id="819e2-129">これは、たとえば、自動更新の実行中に PowerShell ウィンドウが開いた残っている場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="819e2-129">This can happen, for example, if a PowerShell window is left open while automatic update occurs.</span></span> <span data-ttu-id="819e2-130">更新されたコマンドレットを読み込むには、次のいずれかの手順を実行します:> クラウド コネクタ アプライアンスで PowerShell を閉じてから、PowerShell.> を再度開くか、Import-Module CloudConnector -Force を実行できます。</span><span class="sxs-lookup"><span data-stu-id="819e2-130">To load the updated cmdlets, you can do either of the following steps:>  Close PowerShell on the Cloud Connector appliance, and then reopen PowerShell.>  Or, you can run Import-Module CloudConnector -Force.</span></span>
  
## <a name="upgrade-a-single-site-to-a-new-version"></a><span data-ttu-id="819e2-131">1 つのサイトを新しいバージョンにアップグレードする</span><span class="sxs-lookup"><span data-stu-id="819e2-131">Upgrade a single site to a new version</span></span>
<span data-ttu-id="819e2-132"><a name="BKMK_Upgrade"> </a></span><span class="sxs-lookup"><span data-stu-id="819e2-132"><a name="BKMK_Upgrade"> </a></span></span>

<span data-ttu-id="819e2-133">アップグレードするアプライアンスがサイトに 1 つだけある場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="819e2-133">If there is only one appliance in the site you want to upgrade, do the following:</span></span>
  
1. <span data-ttu-id="819e2-134">コントロール パネル の [プログラム] で既存のクラウド コネクタのバージョンを **\> \> アンインストールプログラムと機能。**</span><span class="sxs-lookup"><span data-stu-id="819e2-134">Uninstall the existing Cloud Connector version in **Control Panel \> Programs \> Programs and Features**.</span></span>
    
2. <span data-ttu-id="819e2-135">から新しいバージョンのCloudConnector.msiインストールします [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) 。</span><span class="sxs-lookup"><span data-stu-id="819e2-135">Install the new version of CloudConnector.msi from [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span>
    
3. <span data-ttu-id="819e2-136">インストールするバージョンの CloudConnector.ini ファイルを持ち、環境に必要なすべての値を更新したと確認します。</span><span class="sxs-lookup"><span data-stu-id="819e2-136">Confirm that you have the CloudConnector.ini file for the version you are installing, and that you have updated all of the required values for your environment.</span></span> <span data-ttu-id="819e2-137">以前のリリースの .ini ファイルは使用できません。</span><span class="sxs-lookup"><span data-stu-id="819e2-137">You cannot use the .ini file from a previous release.</span></span> <span data-ttu-id="819e2-138">クラウド コネクタをアップグレードする場合は、トピック「クラウド[](prepare-your-cloud-connector-appliance.md)コネクタ アプライアンスの準備」を参照し、SiteName と EnableReferSupport が CloudConnector.ini ファイルの正しい値に設定されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="819e2-138">If you are upgrading Cloud Connector, please refer to the topic [Prepare your Cloud Connector appliance](prepare-your-cloud-connector-appliance.md) and make sure SiteName and EnableReferSupport are set to the correct value in the CloudConnector.ini file.</span></span>
    
4. <span data-ttu-id="819e2-139">PowerShell コンソールを管理者として起動し、次のコマンドレットを実行して現在のアプライアンスを登録します。</span><span class="sxs-lookup"><span data-stu-id="819e2-139">Start a PowerShell console as administrator and run the following cmdlet to register the current appliance:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

5. <span data-ttu-id="819e2-140">次のコマンドレットを実行して、最新バージョンをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="819e2-140">Run the following cmdlet to download the latest version:</span></span>
    
   ```powershell
   Start-CcDownload
   ```

6. <span data-ttu-id="819e2-141">次のコマンドレットを実行してインストールを開始します。</span><span class="sxs-lookup"><span data-stu-id="819e2-141">Run the following cmdlet to start the installation:</span></span> 
    
   ```powershell
   Install-CcAppliance -Upgrade
   ```

7. <span data-ttu-id="819e2-142">次のコマンドレットを実行して新しい展開をアクティブ化し、以前のバージョンをオフにします。</span><span class="sxs-lookup"><span data-stu-id="819e2-142">Run the following cmdlet to activate the new deployment and turn off the previous version:</span></span>
    
   ```powershell
   Switch-CcVersion
   ```

<span data-ttu-id="819e2-143">サイトに複数のアプライアンスがある場合は、前の手順に従って各アプライアンスを 1 つ 1 つアップグレードしてください。</span><span class="sxs-lookup"><span data-stu-id="819e2-143">If there is more than one appliance in the site, please follow the preceding steps to upgrade each appliance one by one.</span></span>
  
<span data-ttu-id="819e2-144">ドメイン管理者、仮想マシン管理者、セーフ モード管理者、テナント管理者の資格情報を更新する場合は  _、UpdateAllCredentials_ パラメーターを使用してコマンドレットを実行して、すべての資格情報をリセットできます。</span><span class="sxs-lookup"><span data-stu-id="819e2-144">If you want to update Domain administrator, Virtual machine administrator, Safe Mode administrator and Tenant administrator credentials, you can run the cmdlet with the  _UpdateAllCredentials_ parameter to reset all credentials:</span></span>
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

<span data-ttu-id="819e2-145">次に、新しいバージョンへのアップグレードを開始すると、新しい資格情報の入力が昇格されます。</span><span class="sxs-lookup"><span data-stu-id="819e2-145">Then, when you start to upgrade to a new version, you will be promoted to input the new credentials.</span></span> 
  
<span data-ttu-id="819e2-146">テナント管理者の資格情報のみをリセットする場合は、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="819e2-146">If you only want to reset your Tenant administrator credentials, run the following cmdlet:</span></span>
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="upgrade-multiple-sites-to-a-new-version"></a><span data-ttu-id="819e2-147">複数のサイトを新しいバージョンにアップグレードする</span><span class="sxs-lookup"><span data-stu-id="819e2-147">Upgrade multiple sites to a new version</span></span>
<span data-ttu-id="819e2-148"><a name="BKMK_Upgrade"> </a></span><span class="sxs-lookup"><span data-stu-id="819e2-148"><a name="BKMK_Upgrade"> </a></span></span>

<span data-ttu-id="819e2-149">1 つのサイトをアップグレードし、展開内の各サイトに対して一度に 1 つのサイトをアップグレードする手順に従います。</span><span class="sxs-lookup"><span data-stu-id="819e2-149">Follow the steps for upgrading a single site, upgrading one site at a time for each site in your deployment.</span></span> <span data-ttu-id="819e2-150">各サイトをアップグレード [した後で、クラウド コネクタの展開](validate-your-cloud-connector-deployment.md) を確認して検証します。</span><span class="sxs-lookup"><span data-stu-id="819e2-150">Make sure and [Validate your Cloud Connector deployment](validate-your-cloud-connector-deployment.md) after upgrading each site.</span></span>
