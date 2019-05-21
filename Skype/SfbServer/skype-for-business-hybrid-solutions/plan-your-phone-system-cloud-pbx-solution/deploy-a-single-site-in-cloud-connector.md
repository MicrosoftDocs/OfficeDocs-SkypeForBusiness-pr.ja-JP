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
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: fa8aa499-1188-447e-bc30-89d1f5b198a7
description: Cloud Connector エディションで単一の PSTN サイトを展開する方法について説明します。
ms.openlocfilehash: 10d9e5f286b00af8791097707dc0345e100e55d5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287364"
---
# <a name="deploy-a-single-site-in-cloud-connector"></a><span data-ttu-id="e5f15-103">Deploy a single site in Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="e5f15-103">Deploy a single site in Cloud Connector</span></span>
 
<span data-ttu-id="e5f15-104">Cloud Connector エディションで単一の PSTN サイトを展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e5f15-104">Learn about deploying a single PSTN site in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="e5f15-105">Skype for Business Cloud Connector エディションは、高可用性 (HA) に対応した状態で展開できます。</span><span class="sxs-lookup"><span data-stu-id="e5f15-105">You can deploy Skype for Business Cloud Connector Edition with or without High Availability (HA) support.</span></span> <span data-ttu-id="e5f15-106">HA を有効にする場合は、2 台以上のアプライアンスをサイト内で展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5f15-106">If you want to enable HA, you'll need to deploy two or more appliances within a site.</span></span> <span data-ttu-id="e5f15-107">また、展開後に既存のアプライアンスを、HA をサポートするように変換することもできます。</span><span class="sxs-lookup"><span data-stu-id="e5f15-107">You can also convert an existing appliance to support HA after it is deployed.</span></span>
  
## <a name="deploy-the-first-skype-for-business-cloud-connector-edition-appliance"></a><span data-ttu-id="e5f15-108">最初の Skype for Business Cloud Connector エディションのアプライアンスを展開する</span><span class="sxs-lookup"><span data-stu-id="e5f15-108">Deploy the first Skype for Business Cloud Connector Edition appliance</span></span>

<span data-ttu-id="e5f15-109">サイトで最初のアプライアンスを展開するには、管理者として PowerShell コンソールを開き、次のコマンドレットを実行して、アプライアンスを登録します。</span><span class="sxs-lookup"><span data-stu-id="e5f15-109">To deploy the first appliance in a site, open a PowerShell console as administrator and run the following cmdlet to register the appliance:</span></span>
  
```
Register-CcAppliance
```

<span data-ttu-id="e5f15-p102">指示に従って、テナント管理者のアカウント名とパスワードを入力します。Cloud Connector のオンライン管理用に作成したアカウントを使用します。また、指示に従って、外部証明書のパスワード、セーフ モード管理者パスワード、ドメイン管理者パスワード、仮想マシン管理者パスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="e5f15-p102">Follow the instructions to provide the tenant admin account name and password. Use the account you have created for Cloud Connector online management. Also, follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="e5f15-113">[Release 1.4.2 以前] では、次の手順に従って、外部証明書のパスワード、セーフモードのパスワード、ドメイン管理者のパスワード、および VM 管理者のパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="e5f15-113">In release 1.4.2 and earlier, also follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="e5f15-114">リリース 2.0 以降の場合は、外部証明書のパスワード、CceService パスワード、CABackupFile パスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="e5f15-114">In release 2.0 and later, also follow the instructions to provide the external certificate password, CceService password and CABackupFile password.</span></span>
  
<span data-ttu-id="e5f15-115">インストールを開始するには、管理者として PowerShell コンソールを開き、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="e5f15-115">To start the installation, open a PowerShell console as administrator and run the following cmdlet:</span></span>
  
```
Install-CcAppliance
```

## <a name="add-an-appliance-to-an-existing-site"></a><span data-ttu-id="e5f15-116">既存のサイトにアプライアンスを追加する</span><span class="sxs-lookup"><span data-stu-id="e5f15-116">Add an appliance to an existing site</span></span>

<span data-ttu-id="e5f15-117">既存のクラウドコネクタサイトを拡張して、HA をサポートするには、サイトに追加のアプライアンスを追加します。</span><span class="sxs-lookup"><span data-stu-id="e5f15-117">You can extend an existing Cloud Connector site to support HA by adding additional appliances to the site.</span></span> 
  
1. <span data-ttu-id="e5f15-118">「[クラウドコネクタのアプライアンスを準備](prepare-your-cloud-connector-appliance.md)する」の手順に従って、クラウドコネクタのアプライアンスを準備する手順に従います。</span><span class="sxs-lookup"><span data-stu-id="e5f15-118">Follow the steps to prepare your Cloud Connector appliance as described in [Prepare your Cloud Connector appliance](prepare-your-cloud-connector-appliance.md).</span></span> <span data-ttu-id="e5f15-119">手順の一部は展開内の最初のアプライアンスのみで必要になります。</span><span class="sxs-lookup"><span data-stu-id="e5f15-119">Note that some steps are required only for the first appliance in your deployment.</span></span> <span data-ttu-id="e5f15-120">サイト ディレクトリが存在し、HA のサポートのために正しく構成されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="e5f15-120">Confirm that the site directory exists and is correctly configured for HA support.</span></span>
    
2. <span data-ttu-id="e5f15-p104">Office 365 テナント構成のトポロジ情報を更新するには、新たに追加したホスト サーバー上でのみ次のコマンドレットを実行します。複数のアプライアンスを同時に追加する場合は、新たに追加した各ホスト サーバー上で 1 つずつコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="e5f15-p104">Run the following cmdlet only on the newly added host server to update topology information in your Office 365 tenant configuration. If you want to add multiple appliances at the same time, run the cmdlet on each newly added host server one by one:</span></span>
    
   ```
   Register-CcAppliance
   ```

3. <span data-ttu-id="e5f15-p105">既存のアプライアンスのトポロジを更新するには、各ホスト サーバー上で次のコマンドレットを実行します。コマンドレットは、既存のアプライアンス上でのみ実行します。</span><span class="sxs-lookup"><span data-stu-id="e5f15-p105">Update the topology on existing appliances by running the following cmdlet on each host server. Only run the cmdlet on the existing appliances.</span></span>
    
   ```
   Publish-CcAppliance
   ```

4. <span data-ttu-id="e5f15-125">新たに追加したホスト サーバー上でのみ次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="e5f15-125">Run the following cmdlet only on newly added host servers.</span></span> <span data-ttu-id="e5f15-126">このコマンドレットを、既存のアプライアンス上で実行しないでください。</span><span class="sxs-lookup"><span data-stu-id="e5f15-126">Do not run this cmdlet on the existing appliance.</span></span> <span data-ttu-id="e5f15-127">複数のアプライアンスを同時に追加する場合は、新たに追加した各ホスト サーバー上で 1 つずつコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="e5f15-127">If you want to add multiple appliances at the same time, run the cmdlet on each newly added host server one by one.</span></span>
    
   ```
   Install-CcAppliance
   ```

> [!NOTE]
> <span data-ttu-id="e5f15-128">サイト ディレクトリがローカル フォルダー パスに設定されていた場合は、このフォルダーのファイル共有を定義し、新しいアプライアンスのサイト ディレクトリに UNC パスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5f15-128">If the site directory was set to a local folder path, you need to define a file share for this folder and use a UNC path for the site directory on the new appliance.</span></span> <span data-ttu-id="e5f15-129">最初のアプライアンス サイト ディレクトリをローカル パスのままにするか、共有の UNC パスを使用するようにそのパスを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="e5f15-129">You may leave the first appliance site directory with the local path or modify it to use the UNC path for the share to the same folder.</span></span> <span data-ttu-id="e5f15-130">共有サイト ディレクトリの場所を変更する場合は、以前にインストールしたすべてのアプライアンスをアンインストールしてから、再びインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5f15-130">If the location for the shared site directory changes, any previously-installed appliances need to be uninstalled and then reinstalled.</span></span> <span data-ttu-id="e5f15-131">> 重要: CceService アカウントと CABackupFile アカウントの両方のパスワードは、サイト内に展開されているすべてのアプライアンスで同じである必要があります。そのため、サイトディレクトリ共有と、サイトディレクトリ内の暗号化された CA バックアップファイルにそれらのアプライアンスがアクセスできるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5f15-131">> Important: The password for both the CceService account and the CABackupFile account must be the same on all appliances deployed within the site, so that the appliances can access the site directory share and the encrypted CA backup file in the site directory.</span></span> 
  
## <a name="remove-an-appliance-from-an-existing-site"></a><span data-ttu-id="e5f15-132">既存のサイトからアプライアンスを削除する</span><span class="sxs-lookup"><span data-stu-id="e5f15-132">Remove an appliance from an existing site</span></span>

<span data-ttu-id="e5f15-133">既存のサイトからアプライアンスを削除するには:</span><span class="sxs-lookup"><span data-stu-id="e5f15-133">If you want to remove an appliance from an existing site:</span></span>
  
1. <span data-ttu-id="e5f15-134">Office 365 テナント構成でトポロジ情報を更新するサイトから削除するホスト サーバー上でのみ、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="e5f15-134">Run the following cmdlet only on the host servers you want to remove from the site to update the topology information in your Office 365 tenant configuration.</span></span>
    
   ```
   Unregister-CcAppliance
   ```

2. <span data-ttu-id="e5f15-135">アプライアンスのすべての仮想マシンを削除するホスト サーバー上でのみ、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="e5f15-135">Run the following cmdlet only on the host servers from which you want to remove all the virtual machines of the appliance.</span></span>
    
   ```
   Uninstall-CcAppliance
   ```


