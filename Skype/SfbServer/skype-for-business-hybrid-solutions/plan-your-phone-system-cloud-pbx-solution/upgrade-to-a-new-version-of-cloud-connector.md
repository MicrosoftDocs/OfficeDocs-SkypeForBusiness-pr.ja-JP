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
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: efbe25f2-faf5-41c7-8c95-dbc4a835a4a8
description: 既存の Cloud Connector Edition 展開をアップグレードする方法について説明します。
ms.openlocfilehash: c2613069f1626f8fc7e28b4fb5a246fc7647cf98
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286628"
---
# <a name="upgrade-to-a-new-version-of-cloud-connector"></a><span data-ttu-id="b2787-103">Upgrade to a new version of Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="b2787-103">Upgrade to a new version of Cloud Connector</span></span>
 
<span data-ttu-id="b2787-104">既存の Cloud Connector Edition 展開をアップグレードする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b2787-104">Learn about how to upgrade your Cloud Connector Edition deployment.</span></span>
  
<span data-ttu-id="b2787-p101">オンライン管理テナントのアカウントを設定しており、自動更新を有効にしている場合は、自動更新の時間枠の設定に応じて、Skype for Business Cloud Connector エディションの既存の展開がより新しいバージョンに自動でアップグレードされます。手動でアップグレードを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="b2787-p101">If you have set up an online management tenant account and enabled automatic updates, your existing deployment of Skype for Business Cloud Connector Edition will be upgraded to the newer version automatically—according to your automatic update time window configuration. You can also perform a manual upgrade.</span></span> 
  
<span data-ttu-id="b2787-107">Cloud Connector Edition バージョン1.4.1 以降では、既定で自動更新が実行されます。</span><span class="sxs-lookup"><span data-stu-id="b2787-107">Cloud Connector Edition versions 1.4.1 and later perform automatic updates by default.</span></span> <span data-ttu-id="b2787-108">最新バージョン (2.1) に手動でアップグレードする場合は、このトピックで後述する「 [1 つのサイトを新しいバージョンにアップグレード](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2787-108">If you want to upgrade to the latest version (2.1) manually, see [Upgrade a single site to a new version](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) later in this topic.</span></span>
  
<span data-ttu-id="b2787-109">自動更新を有効にするには、クラウドコネクタサービスが実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2787-109">Automatic update requires that the Cloud Connector service is running.</span></span> <span data-ttu-id="b2787-110">次の手順で、自動更新のプロセスを説明します。</span><span class="sxs-lookup"><span data-stu-id="b2787-110">The following steps describe the process for automatic updates:</span></span>
  
- <span data-ttu-id="b2787-111">自動更新プロセスは、自動更新について構成したスケジュールに従って実行します。</span><span class="sxs-lookup"><span data-stu-id="b2787-111">The automatic update process will run according to the schedule you have configured for automatic updates.</span></span>
    
- <span data-ttu-id="b2787-112">オペレーティング システムがタスクを更新する</span><span class="sxs-lookup"><span data-stu-id="b2787-112">Operating system update tasks</span></span>
    
  - <span data-ttu-id="b2787-113">すべてのクラウドコネクタ Vm のオペレーティングシステム更新プログラムを確認してダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="b2787-113">Check and download operating system updates to all Cloud Connector VMs.</span></span> 
    
  - <span data-ttu-id="b2787-114">すべてのクラウドコネクタ Vm を1つずつインストールして更新し、再起動します。</span><span class="sxs-lookup"><span data-stu-id="b2787-114">Install and update all Cloud Connector VMs one by one and restart.</span></span>
    
  - <span data-ttu-id="b2787-115">クラウドコネクタ Vm を再起動した後で、別の再起動が必要かどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="b2787-115">After the Cloud Connector VMs restart, check to see if another restart is needed.</span></span>
    
  - <span data-ttu-id="b2787-116">クラウドコネクタの Vm を正常に修正したら、クラウドコネクタホストコンピューターのプロセスを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="b2787-116">After the Cloud Connector VMs have been successfully patched, repeat the process for the Cloud Connector host machine.</span></span>
    
  - <span data-ttu-id="b2787-117">クラウドコネクタホストマシンが正常に起動すると、すべての未解決のオペレーティングシステム更新タスクが完了します。</span><span class="sxs-lookup"><span data-stu-id="b2787-117">After the Cloud Connector host machine successfully boots up, any outstanding operating system update tasks are completed.</span></span>
    
- <span data-ttu-id="b2787-118">クラウドコネクタの更新タスク</span><span class="sxs-lookup"><span data-stu-id="b2787-118">Cloud Connector update tasks</span></span>
    
  - <span data-ttu-id="b2787-119">ダウンロード サイトからバージョン ファイルをダウンロードして確認します。</span><span class="sxs-lookup"><span data-stu-id="b2787-119">Download and check the version file from the download site.</span></span>
    
  - <span data-ttu-id="b2787-120">新しいバージョンの .msi ファイルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="b2787-120">Download the new version .msi file.</span></span> 
    
  - <span data-ttu-id="b2787-121">古い msi ファイルをアンインストールします。新しい msi ファイルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="b2787-121">Uninstall the old msi file; install the new msi file.</span></span>
    
  - <span data-ttu-id="b2787-122">Skype for Business bits の新しいバージョンをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="b2787-122">Download the new version of Skype for Business bits.</span></span>
    
  - <span data-ttu-id="b2787-123">Register-CcAppliance を呼び出してアプライアンスを登録します。</span><span class="sxs-lookup"><span data-stu-id="b2787-123">Register the appliance by calling Register-CcAppliance.</span></span>
    
  - <span data-ttu-id="b2787-124">新しいクラウドコネクタバージョンをインストールします。</span><span class="sxs-lookup"><span data-stu-id="b2787-124">Install the new Cloud Connector version.</span></span>
    
  - <span data-ttu-id="b2787-125">古いアプライアンスをドレインして、ネットワーク接続を新しいアプライアンスに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="b2787-125">Drain the old appliance and switch the network connection to the new appliance.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="b2787-126">Cloud Connector が新しいビルドに更新されると、クラウドコネクタコマンドレットが更新されないことがあります。</span><span class="sxs-lookup"><span data-stu-id="b2787-126">When Cloud Connector updates to a new build, Cloud Connector cmdlets might not be updated.</span></span> <span data-ttu-id="b2787-127">これは、たとえば、自動更新が行われているときに PowerShell ウィンドウを開いたままにした場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b2787-127">This can happen, for example, if a PowerShell window is left open while automatic update occurs.</span></span> <span data-ttu-id="b2787-128">更新されたコマンドレットを読み込むには、次のいずれかの手順を実行します: > Cloud Connector アプライアンスで PowerShell を閉じて、> をもう一度起動するか、または、Import モジュール CloudConnector-Force を実行できます。</span><span class="sxs-lookup"><span data-stu-id="b2787-128">To load the updated cmdlets, you can do either of the following steps:>  Close PowerShell on the Cloud Connector appliance, and then reopen PowerShell.>  Or, you can run Import-Module CloudConnector -Force.</span></span>
  
## <a name="upgrade-a-single-site-to-a-new-version"></a><span data-ttu-id="b2787-129">単一サイトの新バージョンへのアップグレード</span><span class="sxs-lookup"><span data-stu-id="b2787-129">Upgrade a single site to a new version</span></span>
<span data-ttu-id="b2787-130"><a name="BKMK_Upgrade"> </a></span><span class="sxs-lookup"><span data-stu-id="b2787-130"></span></span>

<span data-ttu-id="b2787-131">アップグレードするサイトにアプライアンスが 1 台のみある場合は、次を行います。</span><span class="sxs-lookup"><span data-stu-id="b2787-131">If there is only one appliance in the site you want to upgrade, do the following:</span></span>
  
1. <span data-ttu-id="b2787-132">コントロールパネルの [プログラム\*\*と機能] \> \> \*\*で既存のクラウドコネクタのバージョンをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="b2787-132">Uninstall the existing Cloud Connector version in **Control Panel \> Programs \> Programs and Features**.</span></span>
    
2. <span data-ttu-id="b2787-133">新しいバージョンの CloudConnector の .msi をから[https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller)インストールします。</span><span class="sxs-lookup"><span data-stu-id="b2787-133">Install the new version of CloudConnector.msi from [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span>
    
3. <span data-ttu-id="b2787-134">CloudConnector.ini ファイルがインストールするバージョンに該当するファイルで、環境に必要な値をすべて更新したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="b2787-134">Confirm that you have the CloudConnector.ini file for the version you are installing, and that you have updated all of the required values for your environment.</span></span> <span data-ttu-id="b2787-135">以前のリリースからの .ini ファイルを使うことはできませんCloudConnector_shortest をアップグレードする場合は「Prepare your environment for Cloud Connector」トピックをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b2787-135">You cannot use the .ini file from a previous release.</span></span> <span data-ttu-id="b2787-136">クラウドコネクタをアップグレードする場合は、「[クラウドコネクタの製品を準備](prepare-your-cloud-connector-appliance.md)する」のトピックを参照して、[SiteName] と [EnableReferSupport] が cloudconnector の .ini ファイルで適切な値に設定されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="b2787-136">If you are upgrading Cloud Connector, please refer to the topic [Prepare your Cloud Connector appliance](prepare-your-cloud-connector-appliance.md) and make sure SiteName and EnableReferSupport are set to the correct value in the CloudConnector.ini file.</span></span>
    
4. <span data-ttu-id="b2787-137">管理者として PowerShell コンソールを起動し、次のコマンドレットを実行して現在のアプライアンスを登録します。</span><span class="sxs-lookup"><span data-stu-id="b2787-137">Start a PowerShell console as administrator and run the following cmdlet to register the current appliance:</span></span>
    
   ```
   Register-CcAppliance
   ```

5. <span data-ttu-id="b2787-138">次のコマンドレットを実行して最新のバージョンをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="b2787-138">Run the following cmdlet to download the latest version:</span></span>
    
   ```
   Start-CcDownload
   ```

6. <span data-ttu-id="b2787-139">次のコマンドレットを実行してインストールを開始します。</span><span class="sxs-lookup"><span data-stu-id="b2787-139">Run the following cmdlet to start the installation:</span></span> 
    
   ```
   Install-CcAppliance -Upgrade
   ```

7. <span data-ttu-id="b2787-140">次のコマンドレットを実行して、新しい展開をアクティブ化し、以前のバージョンをオフにします。</span><span class="sxs-lookup"><span data-stu-id="b2787-140">Run the following cmdlet to activate the new deployment and turn off the previous version:</span></span>
    
   ```
   Switch-CcVersion
   ```

<span data-ttu-id="b2787-141">サイトに複数のアプライアンスがある場合は、前の手順に従い各アプライアンスを一度に 1 台ずつアップグレードしてください。</span><span class="sxs-lookup"><span data-stu-id="b2787-141">If there is more than one appliance in the site, please follow the preceding steps to upgrade each appliance one by one.</span></span>
  
<span data-ttu-id="b2787-142">ドメイン管理者、仮想マシン管理者、セーフモード管理者、テナント管理者の資格情報を更新する場合は、 _Updateallcredentials_パラメーターを指定してコマンドレットを実行して、すべての資格情報をリセットすることができます。</span><span class="sxs-lookup"><span data-stu-id="b2787-142">If you want to update Domain administrator, Virtual machine administrator, Safe Mode administrator and Tenant administrator credentials, you can run the cmdlet with the  _UpdateAllCredentials_ parameter to reset all credentials:</span></span>
  
```
Install-CcAppliance -UpdateAllCredentials
```

<span data-ttu-id="b2787-143">次に、新しいバージョンへのアップグレードを開始すると、新しい資格情報を入力するように指示されます。</span><span class="sxs-lookup"><span data-stu-id="b2787-143">Then, when you start to upgrade to a new version, you will be promoted to input the new credentials.</span></span> 
  
<span data-ttu-id="b2787-144">テナント管理者の資格情報のみをリセットする場合は、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="b2787-144">If you only want to reset your Tenant administrator credentials, run the following cmdlet:</span></span>
  
```
Set-CcCredential -AccountType TenantAdmin
```

## <a name="upgrade-multiple-sites-to-a-new-version"></a><span data-ttu-id="b2787-145">マルチサイトの新バージョンへのアップグレード</span><span class="sxs-lookup"><span data-stu-id="b2787-145">Upgrade multiple sites to a new version</span></span>
<span data-ttu-id="b2787-146"><a name="BKMK_Upgrade"> </a></span><span class="sxs-lookup"><span data-stu-id="b2787-146"></span></span>

<span data-ttu-id="b2787-p106">単一サイトのアップグレードの手順に従い、展開でサイトごとに一度に 1 つのサイトずつアップグレードします。各サイトをアップグレードしたら、必ず[Validate your Cloud Connector deployment](validate-your-cloud-connector-deployment.md)を行ってください。</span><span class="sxs-lookup"><span data-stu-id="b2787-p106">Follow the steps for upgrading a single site, upgrading one site at a time for each site in your deployment. Make sure and [Validate your Cloud Connector deployment](validate-your-cloud-connector-deployment.md) after upgrading each site.</span></span>
  

