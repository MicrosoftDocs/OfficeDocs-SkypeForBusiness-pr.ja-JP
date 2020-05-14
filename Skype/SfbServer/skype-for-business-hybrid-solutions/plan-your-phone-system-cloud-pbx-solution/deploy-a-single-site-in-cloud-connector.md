---
title: Cloud Connector での単一サイトの展開
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
description: Cloud Connector エディションに単一の PSTN サイトを展開する方法について説明します。
ms.openlocfilehash: 334454645be3361794fdd0d16076095a518e58b0
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220537"
---
# <a name="deploy-a-single-site-in-cloud-connector"></a><span data-ttu-id="7f9aa-103">Cloud Connector での単一サイトの展開</span><span class="sxs-lookup"><span data-stu-id="7f9aa-103">Deploy a single site in Cloud Connector</span></span>
 
<span data-ttu-id="7f9aa-104">Cloud Connector エディションに単一の PSTN サイトを展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7f9aa-104">Learn about deploying a single PSTN site in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="7f9aa-105">高可用性 (HA) のサポートがあるかどうかにかかわらず、Skype for Business Cloud Connector エディションを展開できます。</span><span class="sxs-lookup"><span data-stu-id="7f9aa-105">You can deploy Skype for Business Cloud Connector Edition with or without High Availability (HA) support.</span></span> <span data-ttu-id="7f9aa-106">HA を有効にする場合は、1つのサイト内に複数のアプライアンスを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f9aa-106">If you want to enable HA, you'll need to deploy two or more appliances within a site.</span></span> <span data-ttu-id="7f9aa-107">また、既存のアプライアンスを、展開後に HA をサポートするように変換することもできます。</span><span class="sxs-lookup"><span data-stu-id="7f9aa-107">You can also convert an existing appliance to support HA after it is deployed.</span></span>
  
## <a name="deploy-the-first-skype-for-business-cloud-connector-edition-appliance"></a><span data-ttu-id="7f9aa-108">最初の Skype for Business Cloud Connector エディションのアプライアンスを展開する</span><span class="sxs-lookup"><span data-stu-id="7f9aa-108">Deploy the first Skype for Business Cloud Connector Edition appliance</span></span>

<span data-ttu-id="7f9aa-109">サイトに最初のアプライアンスを展開するには、管理者として PowerShell コンソールを開き、次のコマンドレットを実行してアプライアンスを登録します。</span><span class="sxs-lookup"><span data-stu-id="7f9aa-109">To deploy the first appliance in a site, open a PowerShell console as administrator and run the following cmdlet to register the appliance:</span></span>
  
```powershell
Register-CcAppliance
```

<span data-ttu-id="7f9aa-110">指示に従って、テナント管理者のアカウント名とパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="7f9aa-110">Follow the instructions to provide the tenant admin account name and password.</span></span> <span data-ttu-id="7f9aa-111">Cloud Connector online management 用に作成したアカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="7f9aa-111">Use the account you have created for Cloud Connector online management.</span></span> <span data-ttu-id="7f9aa-112">また、手順に従って、外部証明書のパスワード、セーフモード管理者パスワード、ドメイン管理者パスワード、および VM 管理者パスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="7f9aa-112">Also, follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="7f9aa-113">リリース1.4.2 以前の場合は、手順に従って外部証明書のパスワード、セーフモード管理者パスワード、ドメイン管理者パスワード、および VM 管理パスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="7f9aa-113">In release 1.4.2 and earlier, also follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="7f9aa-114">リリース2.0 以降でも、指示に従って外部証明書のパスワード、CceService password、CABackupFile のパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="7f9aa-114">In release 2.0 and later, also follow the instructions to provide the external certificate password, CceService password and CABackupFile password.</span></span>
  
<span data-ttu-id="7f9aa-115">インストールを開始するには、管理者として PowerShell コンソールを開き、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="7f9aa-115">To start the installation, open a PowerShell console as administrator and run the following cmdlet:</span></span>
  
```powershell
Install-CcAppliance
```

## <a name="add-an-appliance-to-an-existing-site"></a><span data-ttu-id="7f9aa-116">既存のサイトにアプライアンスを追加する</span><span class="sxs-lookup"><span data-stu-id="7f9aa-116">Add an appliance to an existing site</span></span>

<span data-ttu-id="7f9aa-117">サイトに追加のアプライアンスを追加して、HA をサポートするように既存の Cloud Connector サイトを拡張することができます。</span><span class="sxs-lookup"><span data-stu-id="7f9aa-117">You can extend an existing Cloud Connector site to support HA by adding additional appliances to the site.</span></span> 
  
1. <span data-ttu-id="7f9aa-118">「 [Cloud connector アプライアンスを準備](prepare-your-cloud-connector-appliance.md)する」で説明されている手順に従って、cloud connector アプライアンスを準備します。</span><span class="sxs-lookup"><span data-stu-id="7f9aa-118">Follow the steps to prepare your Cloud Connector appliance as described in [Prepare your Cloud Connector appliance](prepare-your-cloud-connector-appliance.md).</span></span> <span data-ttu-id="7f9aa-119">一部の手順は、展開の最初のアプライアンスに対してのみ必要になることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="7f9aa-119">Note that some steps are required only for the first appliance in your deployment.</span></span> <span data-ttu-id="7f9aa-120">サイトディレクトリが存在し、HA サポート用に正しく構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7f9aa-120">Confirm that the site directory exists and is correctly configured for HA support.</span></span>
    
2. <span data-ttu-id="7f9aa-121">Microsoft 365 または Office 365 組織の構成のトポロジ情報を更新するには、新しく追加したホストサーバー上でのみ次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="7f9aa-121">Run the following cmdlet only on the newly added host server to update topology information in your Microsoft 365 or Office 365 organization configuration.</span></span> <span data-ttu-id="7f9aa-122">複数のアプライアンスを同時に追加する場合は、新しく追加した各ホストサーバー上でコマンドレットを1つずつ実行します。</span><span class="sxs-lookup"><span data-stu-id="7f9aa-122">If you want to add multiple appliances at the same time, run the cmdlet on each newly added host server one by one:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

3. <span data-ttu-id="7f9aa-123">各ホストサーバーで次のコマンドレットを実行して、既存のアプライアンスのトポロジを更新します。</span><span class="sxs-lookup"><span data-stu-id="7f9aa-123">Update the topology on existing appliances by running the following cmdlet on each host server.</span></span> <span data-ttu-id="7f9aa-124">既存のアプライアンス上でのみコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="7f9aa-124">Only run the cmdlet on the existing appliances.</span></span>
    
   ```powershell
   Publish-CcAppliance
   ```

4. <span data-ttu-id="7f9aa-125">新しく追加したホストサーバー上でのみ次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="7f9aa-125">Run the following cmdlet only on newly added host servers.</span></span> <span data-ttu-id="7f9aa-126">このコマンドレットは、既存のアプライアンスでは実行しないでください。</span><span class="sxs-lookup"><span data-stu-id="7f9aa-126">Do not run this cmdlet on the existing appliance.</span></span> <span data-ttu-id="7f9aa-127">複数のアプライアンスを同時に追加する場合は、新しく追加した各ホストサーバー上で1つずつコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="7f9aa-127">If you want to add multiple appliances at the same time, run the cmdlet on each newly added host server one by one.</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

> [!NOTE]
> <span data-ttu-id="7f9aa-128">サイトディレクトリがローカルフォルダーのパスに設定されている場合は、このフォルダーに対してファイル共有を定義し、新しいアプライアンス上のサイトディレクトリの UNC パスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f9aa-128">If the site directory was set to a local folder path, you need to define a file share for this folder and use a UNC path for the site directory on the new appliance.</span></span> <span data-ttu-id="7f9aa-129">最初のアプライアンスサイトディレクトリをローカルパスのままにするか、共有の UNC パスを使用するように変更することができます。</span><span class="sxs-lookup"><span data-stu-id="7f9aa-129">You may leave the first appliance site directory with the local path or modify it to use the UNC path for the share to the same folder.</span></span> <span data-ttu-id="7f9aa-130">共有サイトディレクトリの場所が変更された場合は、以前にインストールしたすべてのアプライアンスをアンインストールしてから再インストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f9aa-130">If the location for the shared site directory changes, any previously-installed appliances need to be uninstalled and then reinstalled.</span></span> <span data-ttu-id="7f9aa-131">> 重要: CceService アカウントと CABackupFile アカウントの両方のパスワードは、サイト内に展開されているすべてのアプライアンスで同じである必要があります。これにより、アプライアンスはサイトディレクトリ共有と、サイトディレクトリ内の暗号化された CA バックアップファイルにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="7f9aa-131">> Important: The password for both the CceService account and the CABackupFile account must be the same on all appliances deployed within the site, so that the appliances can access the site directory share and the encrypted CA backup file in the site directory.</span></span> 
  
## <a name="remove-an-appliance-from-an-existing-site"></a><span data-ttu-id="7f9aa-132">既存のサイトからアプライアンスを削除する</span><span class="sxs-lookup"><span data-stu-id="7f9aa-132">Remove an appliance from an existing site</span></span>

<span data-ttu-id="7f9aa-133">既存のサイトからアプライアンスを削除するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="7f9aa-133">If you want to remove an appliance from an existing site:</span></span>
  
1. <span data-ttu-id="7f9aa-134">サイトから削除するホストサーバー上でのみ次のコマンドレットを実行して、Microsoft 365 または Office 365 組織の構成のトポロジ情報を更新します。</span><span class="sxs-lookup"><span data-stu-id="7f9aa-134">Run the following cmdlet only on the host servers you want to remove from the site to update the topology information in your Microsoft 365 or Office 365 organization configuration.</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

2. <span data-ttu-id="7f9aa-135">アプライアンスのすべての仮想マシンを削除するホストサーバー上でのみ、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="7f9aa-135">Run the following cmdlet only on the host servers from which you want to remove all the virtual machines of the appliance.</span></span>
    
   ```powershell
   Uninstall-CcAppliance
   ```


