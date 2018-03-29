---
title: Cloud Connector 新バージョンへのアップグレード
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Hybrid
ms.assetid: efbe25f2-faf5-41c7-8c95-dbc4a835a4a8
description: 既存の Cloud Connector Edition 展開をアップグレードする方法について説明します。
ms.openlocfilehash: 0538b5d43c6e11aa11f7d265e43eb5f283e2b74e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="upgrade-to-a-new-version-of-cloud-connector"></a><span data-ttu-id="0af3c-103">Cloud Connector 新バージョンへのアップグレード</span><span class="sxs-lookup"><span data-stu-id="0af3c-103">Upgrade to a new version of Cloud Connector</span></span>
 
<span data-ttu-id="0af3c-104">既存の Cloud Connector Edition 展開をアップグレードする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0af3c-104">Learn about how to upgrade your Cloud Connector Edition deployment.</span></span>
  
<span data-ttu-id="0af3c-p101">オンライン管理テナントのアカウントを設定しており、自動更新を有効にしている場合は、自動更新の時間枠の設定に応じて、Skype for Business Cloud Connector エディションの既存の展開がより新しいバージョンに自動でアップグレードされます。手動でアップグレードを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="0af3c-p101">If you have set up an online management tenant account and enabled automatic updates, your existing deployment of Skype for Business Cloud Connector Edition will be upgraded to the newer version automatically—according to your automatic update time window configuration. You can also perform a manual upgrade.</span></span> 
  
<span data-ttu-id="0af3c-107">コネクタ エディション バージョン 1.4.1 のクラウドし、既定で自動更新を後で実行します。</span><span class="sxs-lookup"><span data-stu-id="0af3c-107">Cloud Connector Edition versions 1.4.1 and later perform automatic updates by default.</span></span> <span data-ttu-id="0af3c-108">最新バージョン (2.1) を手動でアップグレードする場合は、このトピックで後で[1 つのサイトを新しいバージョンにアップグレード](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0af3c-108">If you want to upgrade to the latest version (2.1) manually, see [Upgrade a single site to a new version](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) later in this topic.</span></span>
  
<span data-ttu-id="0af3c-109">自動更新では、クラウドのコネクタ サービスが実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0af3c-109">Automatic update requires that the Cloud Connector service is running.</span></span> <span data-ttu-id="0af3c-110">次の手順で、自動更新のプロセスを説明します。</span><span class="sxs-lookup"><span data-stu-id="0af3c-110">The following steps describe the process for automatic updates:</span></span>
  
- <span data-ttu-id="0af3c-111">自動更新プロセスは、自動更新について構成したスケジュールに従って実行します。</span><span class="sxs-lookup"><span data-stu-id="0af3c-111">The automatic update process will run according to the schedule you have configured for automatic updates.</span></span>
    
- <span data-ttu-id="0af3c-112">オペレーティング システムがタスクを更新する</span><span class="sxs-lookup"><span data-stu-id="0af3c-112">Operating system update tasks</span></span>
    
  - <span data-ttu-id="0af3c-113">チェックし、クラウド コネクタのすべての vm のオペレーティング システムの更新プログラムをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="0af3c-113">Check and download operating system updates to all Cloud Connector VMs.</span></span> 
    
  - <span data-ttu-id="0af3c-114">インストールし、すべてのクラウド コネクタ Vm を 1 つずつを更新し、再起動します。</span><span class="sxs-lookup"><span data-stu-id="0af3c-114">Install and update all Cloud Connector VMs one by one and restart.</span></span>
    
  - <span data-ttu-id="0af3c-115">クラウド コネクタの Vm が再起動した後は、もう一度再起動が必要なかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="0af3c-115">After the Cloud Connector VMs restart, check to see if another restart is needed.</span></span>
    
  - <span data-ttu-id="0af3c-116">後クラウド コネクタの Vm が正常にパッチが適用されて、クラウドのコネクタのホスト コンピューターの処理を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="0af3c-116">After the Cloud Connector VMs have been successfully patched, repeat the process for the Cloud Connector host machine.</span></span>
    
  - <span data-ttu-id="0af3c-117">クラウド コネクタのホスト コンピューター正常に起動されると後、は、未処理のオペレーティング システムの更新タスクが完了しました。</span><span class="sxs-lookup"><span data-stu-id="0af3c-117">After the Cloud Connector host machine successfully boots up, any outstanding operating system update tasks are completed.</span></span>
    
- <span data-ttu-id="0af3c-118">クラウドのコネクタ タスクの更新</span><span class="sxs-lookup"><span data-stu-id="0af3c-118">Cloud Connector update tasks</span></span>
    
  - <span data-ttu-id="0af3c-119">ダウンロード サイトからバージョン ファイルをダウンロードして確認します。</span><span class="sxs-lookup"><span data-stu-id="0af3c-119">Download and check the version file from the download site.</span></span>
    
  - <span data-ttu-id="0af3c-120">新しいバージョンの .msi ファイルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="0af3c-120">Download the new version .msi file.</span></span> 
    
  - <span data-ttu-id="0af3c-121">古い msi ファイルをアンインストールします。新しい msi ファイルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="0af3c-121">Uninstall the old msi file; install the new msi file.</span></span>
    
  - <span data-ttu-id="0af3c-122">Skype のビジネスのビットのための新しいバージョンをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="0af3c-122">Download the new version of Skype for Business bits.</span></span>
    
  - <span data-ttu-id="0af3c-123">Register-CcAppliance を呼び出してアプライアンスを登録します。</span><span class="sxs-lookup"><span data-stu-id="0af3c-123">Register the appliance by calling Register-CcAppliance.</span></span>
    
  - <span data-ttu-id="0af3c-124">新しいクラウド コネクタのバージョンをインストールします。</span><span class="sxs-lookup"><span data-stu-id="0af3c-124">Install the new Cloud Connector version.</span></span>
    
  - <span data-ttu-id="0af3c-125">古いアプライアンスをドレインして、ネットワーク接続を新しいアプライアンスに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="0af3c-125">Drain the old appliance and switch the network connection to the new appliance.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="0af3c-126">クラウド コネクタは、新しいビルドに更新すると、クラウドのコネクタのコマンドレットを更新できません可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0af3c-126">When Cloud Connector updates to a new build, Cloud Connector cmdlets might not be updated.</span></span> <span data-ttu-id="0af3c-127">これは、たとえば、PowerShell ウィンドウは開いたままに自動更新が発生したときに場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="0af3c-127">This can happen, for example, if a PowerShell window is left open while automatic update occurs.</span></span> <span data-ttu-id="0af3c-128">更新されたコマンドレットをロードするには、行うことができます次の手順のいずれか: > クラウド コネクタ アプライアンス、および PowerShell。 その後の再オープンを閉じる PowerShell > または、インポート モジュール CloudConnector を実行することができます-フォース。</span><span class="sxs-lookup"><span data-stu-id="0af3c-128">To load the updated cmdlets, you can do either of the following steps:>  Close PowerShell on the Cloud Connector appliance, and then reopen PowerShell.>  Or, you can run Import-Module CloudConnector -Force.</span></span>
  
## <a name="upgrade-a-single-site-to-a-new-version"></a><span data-ttu-id="0af3c-129">単一サイトの新バージョンへのアップグレード</span><span class="sxs-lookup"><span data-stu-id="0af3c-129">Upgrade a single site to a new version</span></span>
<span data-ttu-id="0af3c-130"><a name="BKMK_Upgrade"> </a></span><span class="sxs-lookup"><span data-stu-id="0af3c-130"></span></span>

<span data-ttu-id="0af3c-131">アップグレードするサイト内の 1 つだけのアプライアンスがある場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0af3c-131">If there is only one appliance in the site you want to upgrade, do the following:</span></span>
  
1. <span data-ttu-id="0af3c-132">既存のクラウドのコネクタのバージョンをアンインストール**コントロール パネルの [\>プログラム\>プログラムと機能**。</span><span class="sxs-lookup"><span data-stu-id="0af3c-132">Uninstall the existing Cloud Connector version in **Control Panel \> Programs \> Programs and Features**.</span></span>
    
2. <span data-ttu-id="0af3c-133">CloudConnector.msi の新しいバージョンをインストールする[https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller)。</span><span class="sxs-lookup"><span data-stu-id="0af3c-133">Install the new version of CloudConnector.msi from [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span>
    
3. <span data-ttu-id="0af3c-134">CloudConnector.ini ファイルがインストールするバージョンに該当するファイルで、環境に必要な値をすべて更新したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="0af3c-134">Confirm that you have the CloudConnector.ini file for the version you are installing, and that you have updated all of the required values for your environment.</span></span> <span data-ttu-id="0af3c-135">以前のリリースからの .ini ファイルは使用できません。</span><span class="sxs-lookup"><span data-stu-id="0af3c-135">You cannot use the .ini file from a previous release.</span></span> <span data-ttu-id="0af3c-136">クラウドのコネクタをアップグレードする場合は、[コネクタのクラウド アプライアンスの準備](prepare-your-cloud-connector-appliance.md)のトピックを参照してください、サイト名と EnableReferSupport CloudConnector.ini ファイル内に適切な値に設定されているかどうかを確認してください。</span><span class="sxs-lookup"><span data-stu-id="0af3c-136">If you are upgrading Cloud Connector, please refer to the topic [Prepare your Cloud Connector appliance](prepare-your-cloud-connector-appliance.md) and make sure SiteName and EnableReferSupport are set to the correct value in the CloudConnector.ini file.</span></span>
    
4. <span data-ttu-id="0af3c-137">管理者として PowerShell コンソールを起動し、次のコマンドレットを実行して現在のアプライアンスを登録します。</span><span class="sxs-lookup"><span data-stu-id="0af3c-137">Start a PowerShell console as administrator and run the following cmdlet to register the current appliance:</span></span>
    
  ```
  Register-CcAppliance
  ```

5. <span data-ttu-id="0af3c-138">次のコマンドレットを実行して最新のバージョンをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="0af3c-138">Run the following cmdlet to download the latest version:</span></span>
    
  ```
  Start-CcDownload
  ```

6. <span data-ttu-id="0af3c-139">次のコマンドレットを実行してインストールを開始します。</span><span class="sxs-lookup"><span data-stu-id="0af3c-139">Run the following cmdlet to start the installation:</span></span> 
    
  ```
  Install-CcAppliance -Upgrade
  ```

7. <span data-ttu-id="0af3c-140">次のコマンドレットを実行して、新しい展開をアクティブ化し、以前のバージョンをオフにします。</span><span class="sxs-lookup"><span data-stu-id="0af3c-140">Run the following cmdlet to activate the new deployment and turn off the previous version:</span></span>
    
  ```
  Switch-CcVersion
  ```

<span data-ttu-id="0af3c-141">サイトに複数のアプライアンスがある場合は、前の手順に従い各アプライアンスを一度に 1 台ずつアップグレードしてください。</span><span class="sxs-lookup"><span data-stu-id="0af3c-141">If there is more than one appliance in the site, please follow the preceding steps to upgrade each appliance one by one.</span></span>
  
<span data-ttu-id="0af3c-142">ドメイン管理者、仮想マシンの管理者、セーフ モードの管理者およびテナント管理者の資格情報を更新する場合は、すべての資格情報をリセットするのには_UpdateAllCredentials_パラメーターを持つコマンドレットを実行できます。</span><span class="sxs-lookup"><span data-stu-id="0af3c-142">If you want to update Domain administrator, Virtual machine administrator, Safe Mode administrator and Tenant administrator credentials, you can run the cmdlet with the  _UpdateAllCredentials_ parameter to reset all credentials:</span></span>
  
```
Install-CcAppliance -UpdateAllCredentials
```

<span data-ttu-id="0af3c-143">次に、新しいバージョンへのアップグレードを開始すると、新しい資格情報を入力するように指示されます。</span><span class="sxs-lookup"><span data-stu-id="0af3c-143">Then, when you start to upgrade to a new version, you will be promoted to input the new credentials.</span></span> 
  
<span data-ttu-id="0af3c-144">テナント管理者の資格情報のみをリセットする場合は、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="0af3c-144">If you only want to reset your Tenant administrator credentials, run the following cmdlet:</span></span>
  
```
Set-CcCredential -AccountType TenantAdmin
```

## <a name="upgrade-multiple-sites-to-a-new-version"></a><span data-ttu-id="0af3c-145">マルチサイトの新バージョンへのアップグレード</span><span class="sxs-lookup"><span data-stu-id="0af3c-145">Upgrade multiple sites to a new version</span></span>
<span data-ttu-id="0af3c-146"><a name="BKMK_Upgrade"> </a></span><span class="sxs-lookup"><span data-stu-id="0af3c-146"></span></span>

<span data-ttu-id="0af3c-147">単一サイトのアップグレードの手順に従い、展開でサイトごとに一度に 1 つのサイトずつアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="0af3c-147">Follow the steps for upgrading a single site, upgrading one site at a time for each site in your deployment.</span></span> <span data-ttu-id="0af3c-148">確認と各サイトをアップグレードした後[、クラウドのコネクタの配置を検証](validate-your-cloud-connector-deployment.md)します。</span><span class="sxs-lookup"><span data-stu-id="0af3c-148">Make sure and [Validate your Cloud Connector deployment](validate-your-cloud-connector-deployment.md) after upgrading each site.</span></span>
  

