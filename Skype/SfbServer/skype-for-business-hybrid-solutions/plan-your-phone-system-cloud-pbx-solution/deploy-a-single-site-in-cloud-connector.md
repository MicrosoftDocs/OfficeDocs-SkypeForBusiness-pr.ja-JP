---
title: クラウド コネクタでの単一サイトの展開
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: fa8aa499-1188-447e-bc30-89d1f5b198a7
description: クラウド コネクタ エディションでの 1 つの PSTN サイトの展開について説明します。
ms.openlocfilehash: 32c981b0f7de3d596dc25c3336000871db9fee65
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094835"
---
# <a name="deploy-a-single-site-in-cloud-connector"></a><span data-ttu-id="753cc-103">クラウド コネクタでの単一サイトの展開</span><span class="sxs-lookup"><span data-stu-id="753cc-103">Deploy a single site in Cloud Connector</span></span>
 
> [!Important]
> <span data-ttu-id="753cc-104">Cloud Connector Edition は、Skype for Business Online と共に 2021 年 7 月 31 日に廃止されます。</span><span class="sxs-lookup"><span data-stu-id="753cc-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="753cc-105">組織が Teams にアップグレードしたら、直接ルーティングを使用してオンプレミスのテレフォニー ネットワークを Teams に接続する方法 [について説明します](/MicrosoftTeams/direct-routing-landing-page)。</span><span class="sxs-lookup"><span data-stu-id="753cc-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="753cc-106">クラウド コネクタ エディションでの 1 つの PSTN サイトの展開について説明します。</span><span class="sxs-lookup"><span data-stu-id="753cc-106">Learn about deploying a single PSTN site in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="753cc-107">Skype for Business Cloud Connector Edition は、高可用性 (HA) のサポートを使用する場合と使用しない場合に展開できます。</span><span class="sxs-lookup"><span data-stu-id="753cc-107">You can deploy Skype for Business Cloud Connector Edition with or without High Availability (HA) support.</span></span> <span data-ttu-id="753cc-108">HA を有効にする場合は、サイト内に 2 つ以上のアプライアンスを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="753cc-108">If you want to enable HA, you'll need to deploy two or more appliances within a site.</span></span> <span data-ttu-id="753cc-109">展開後に既存のアプライアンスを HA をサポートするために変換することもできます。</span><span class="sxs-lookup"><span data-stu-id="753cc-109">You can also convert an existing appliance to support HA after it is deployed.</span></span>
  
## <a name="deploy-the-first-skype-for-business-cloud-connector-edition-appliance"></a><span data-ttu-id="753cc-110">最初の Skype for Business Cloud Connector Edition アプライアンスを展開する</span><span class="sxs-lookup"><span data-stu-id="753cc-110">Deploy the first Skype for Business Cloud Connector Edition appliance</span></span>

<span data-ttu-id="753cc-111">サイトに最初のアプライアンスを展開するには、管理者として PowerShell コンソールを開き、次のコマンドレットを実行してアプライアンスを登録します。</span><span class="sxs-lookup"><span data-stu-id="753cc-111">To deploy the first appliance in a site, open a PowerShell console as administrator and run the following cmdlet to register the appliance:</span></span>
  
```powershell
Register-CcAppliance
```

<span data-ttu-id="753cc-112">手順に従って、テナント管理者アカウント名とパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="753cc-112">Follow the instructions to provide the tenant admin account name and password.</span></span> <span data-ttu-id="753cc-113">クラウド コネクタのオンライン管理用に作成したアカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="753cc-113">Use the account you have created for Cloud Connector online management.</span></span> <span data-ttu-id="753cc-114">また、指示に従って、外部証明書パスワード、セーフ モード管理者パスワード、ドメイン管理者パスワード、VM 管理者パスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="753cc-114">Also, follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="753cc-115">リリース 1.4.2 以前では、指示に従って、外部証明書パスワード、セーフ モード管理者パスワード、ドメイン管理者パスワード、VM 管理者パスワードも提供します。</span><span class="sxs-lookup"><span data-stu-id="753cc-115">In release 1.4.2 and earlier, also follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="753cc-116">リリース 2.0 以降では、指示に従って外部証明書パスワード、CceService パスワード、CABackupFile パスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="753cc-116">In release 2.0 and later, also follow the instructions to provide the external certificate password, CceService password and CABackupFile password.</span></span>
  
<span data-ttu-id="753cc-117">インストールを開始するには、管理者として PowerShell コンソールを開き、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="753cc-117">To start the installation, open a PowerShell console as administrator and run the following cmdlet:</span></span>
  
```powershell
Install-CcAppliance
```

## <a name="add-an-appliance-to-an-existing-site"></a><span data-ttu-id="753cc-118">既存のサイトにアプライアンスを追加する</span><span class="sxs-lookup"><span data-stu-id="753cc-118">Add an appliance to an existing site</span></span>

<span data-ttu-id="753cc-119">既存のクラウド コネクタ サイトを拡張して HA をサポートするには、サイトにアプライアンスを追加します。</span><span class="sxs-lookup"><span data-stu-id="753cc-119">You can extend an existing Cloud Connector site to support HA by adding additional appliances to the site.</span></span> 
  
1. <span data-ttu-id="753cc-120">「クラウド コネクタ アプライアンスの準備」の説明に従って、クラウド コネクタ アプライアンスを [準備する手順に従います](prepare-your-cloud-connector-appliance.md)。</span><span class="sxs-lookup"><span data-stu-id="753cc-120">Follow the steps to prepare your Cloud Connector appliance as described in [Prepare your Cloud Connector appliance](prepare-your-cloud-connector-appliance.md).</span></span> <span data-ttu-id="753cc-121">一部の手順は、展開内の最初のアプライアンスでのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="753cc-121">Note that some steps are required only for the first appliance in your deployment.</span></span> <span data-ttu-id="753cc-122">サイト ディレクトリが存在し、HA サポート用に正しく構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="753cc-122">Confirm that the site directory exists and is correctly configured for HA support.</span></span>
    
2. <span data-ttu-id="753cc-123">Microsoft 365 または 365 組織の構成でトポロジ情報を更新するには、新しく追加されたホスト サーバーでのみ次Office実行します。</span><span class="sxs-lookup"><span data-stu-id="753cc-123">Run the following cmdlet only on the newly added host server to update topology information in your Microsoft 365 or Office 365 organization configuration.</span></span> <span data-ttu-id="753cc-124">複数のアプライアンスを同時に追加する場合は、新しく追加された各ホスト サーバーでコマンドレットを 1 つ 1 つ実行します。</span><span class="sxs-lookup"><span data-stu-id="753cc-124">If you want to add multiple appliances at the same time, run the cmdlet on each newly added host server one by one:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

3. <span data-ttu-id="753cc-125">各ホスト サーバーで次のコマンドレットを実行して、既存のアプライアンスのトポロジを更新します。</span><span class="sxs-lookup"><span data-stu-id="753cc-125">Update the topology on existing appliances by running the following cmdlet on each host server.</span></span> <span data-ttu-id="753cc-126">既存のアプライアンスでのみコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="753cc-126">Only run the cmdlet on the existing appliances.</span></span>
    
   ```powershell
   Publish-CcAppliance
   ```

4. <span data-ttu-id="753cc-127">新しく追加されたホスト サーバーでのみ、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="753cc-127">Run the following cmdlet only on newly added host servers.</span></span> <span data-ttu-id="753cc-128">既存のアプライアンスでこのコマンドレットを実行しない。</span><span class="sxs-lookup"><span data-stu-id="753cc-128">Do not run this cmdlet on the existing appliance.</span></span> <span data-ttu-id="753cc-129">複数のアプライアンスを同時に追加する場合は、新しく追加されたホスト サーバーごとに 1 つ 1 つコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="753cc-129">If you want to add multiple appliances at the same time, run the cmdlet on each newly added host server one by one.</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

> [!NOTE]
> <span data-ttu-id="753cc-130">サイト ディレクトリがローカル フォルダー パスに設定されている場合は、このフォルダーのファイル共有を定義し、新しいアプライアンスのサイト ディレクトリに UNC パスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="753cc-130">If the site directory was set to a local folder path, you need to define a file share for this folder and use a UNC path for the site directory on the new appliance.</span></span> <span data-ttu-id="753cc-131">最初のアプライアンス サイト ディレクトリをローカル パスのままにするか、同じフォルダーへの共有の UNC パスを使用するために変更できます。</span><span class="sxs-lookup"><span data-stu-id="753cc-131">You may leave the first appliance site directory with the local path or modify it to use the UNC path for the share to the same folder.</span></span> <span data-ttu-id="753cc-132">共有サイト ディレクトリの場所が変更された場合は、以前にインストールしたアプライアンスをアンインストールしてから再インストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="753cc-132">If the location for the shared site directory changes, any previously-installed appliances need to be uninstalled and then reinstalled.</span></span> <span data-ttu-id="753cc-133">> 重要: CceService アカウントと CABackupFile アカウントの両方のパスワードは、サイト内に展開されているすべてのアプライアンスで同じにし、アプライアンスがサイト ディレクトリ共有とサイト ディレクトリ内の暗号化された CA バックアップ ファイルにアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="753cc-133">> Important: The password for both the CceService account and the CABackupFile account must be the same on all appliances deployed within the site, so that the appliances can access the site directory share and the encrypted CA backup file in the site directory.</span></span> 
  
## <a name="remove-an-appliance-from-an-existing-site"></a><span data-ttu-id="753cc-134">既存のサイトからアプライアンスを削除する</span><span class="sxs-lookup"><span data-stu-id="753cc-134">Remove an appliance from an existing site</span></span>

<span data-ttu-id="753cc-135">既存のサイトからアプライアンスを削除する場合は、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="753cc-135">If you want to remove an appliance from an existing site:</span></span>
  
1. <span data-ttu-id="753cc-136">サイトから削除するホスト サーバー上でのみ、次のコマンドレットを実行して、Microsoft 365 または Office 365 組織構成のトポロジ情報を更新します。</span><span class="sxs-lookup"><span data-stu-id="753cc-136">Run the following cmdlet only on the host servers you want to remove from the site to update the topology information in your Microsoft 365 or Office 365 organization configuration.</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

2. <span data-ttu-id="753cc-137">アプライアンスのすべての仮想マシンを削除するホスト サーバーでのみ、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="753cc-137">Run the following cmdlet only on the host servers from which you want to remove all the virtual machines of the appliance.</span></span>
    
   ```powershell
   Uninstall-CcAppliance
   ```