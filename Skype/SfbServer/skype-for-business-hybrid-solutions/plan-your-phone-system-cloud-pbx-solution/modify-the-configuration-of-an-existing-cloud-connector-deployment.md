---
title: 既存の Cloud Connector の展開構成の変更
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
ms.assetid: 90490c65-0e40-4e85-96e1-751f27897e25
description: 既存の Skype for Business Cloud Connector エディション1.4.1 以降の展開の構成を変更するには、このトピックの手順に従います。
ms.openlocfilehash: 4b551d7cd7a61a1113b4b2bb05e2c0f5ca4f3288
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220297"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a><span data-ttu-id="a7de0-103">既存の Cloud Connector の展開構成の変更</span><span class="sxs-lookup"><span data-stu-id="a7de0-103">Modify the configuration of an existing Cloud Connector deployment</span></span>
 
<span data-ttu-id="a7de0-104">既存の Skype for Business Cloud Connector エディション1.4.1 以降の展開の構成を変更するには、このトピックの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="a7de0-104">Follow the steps in this topic to modify the configuration of an existing Skype for Business Cloud Connector Edition 1.4.1 or later deployment.</span></span> 
  
## <a name="modify-the-configuration-of-a-single-site"></a><span data-ttu-id="a7de0-105">1つのサイトの構成を変更する</span><span class="sxs-lookup"><span data-stu-id="a7de0-105">Modify the configuration of a single site</span></span>
<span data-ttu-id="a7de0-106"><a name="BKMK_SIngleSite"> </a></span><span class="sxs-lookup"><span data-stu-id="a7de0-106"><a name="BKMK_SIngleSite"> </a></span></span>

<span data-ttu-id="a7de0-107">サイト内にアプライアンスが1つしかない場合は、アプライアンスの展開後に構成設定を変更するときに、CloudConnector の .ini ファイルを変更して展開を再度開始することができます。</span><span class="sxs-lookup"><span data-stu-id="a7de0-107">If there is only one appliance in the site, when you want to change the configuration settings after the appliance is deployed, you can modify the CloudConnector.ini file and start the deployment again.</span></span>
  
1. <span data-ttu-id="a7de0-108">次のコマンドレットを実行して、ホストサーバー上の既存の仮想マシンをすべてアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="a7de0-108">Run the following cmdlet to uninstall all existing virtual machines on the host server:</span></span> 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. <span data-ttu-id="a7de0-109">次のコマンドレットを実行してアプライアンスの登録を解除します。</span><span class="sxs-lookup"><span data-stu-id="a7de0-109">Run the following cmdlet to unregister the appliance:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

3. <span data-ttu-id="a7de0-110">アプライアンスディレクトリで CloudConnector .ini ファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="a7de0-110">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="a7de0-111">次のコマンドレットを実行して構成を更新します。 (この手順はバージョン2にのみ適用されます。以前のバージョンでは、次の手順に進んでください。)</span><span class="sxs-lookup"><span data-stu-id="a7de0-111">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
   ```powershell
   Import-CcConfiguration 
   ```

5. <span data-ttu-id="a7de0-112">次のコマンドレットを実行して、アプライアンスを再度登録します。</span><span class="sxs-lookup"><span data-stu-id="a7de0-112">Run the following cmdlet to register the appliance again:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

6. <span data-ttu-id="a7de0-113">Skype for Business Cloud Connector エディションをインストールするには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="a7de0-113">Run the following cmdlet to install Skype for Business Cloud Connector Edition:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

<span data-ttu-id="a7de0-114">サイト内に複数のアプライアンスがある場合は、次の手順に従って、CloudConnector の .ini ファイルを変更し、各アプライアンスを1つずつ再展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7de0-114">If there is more than one appliance in the site, you'll need to follow these steps, modify the CloudConnector.ini file, and redeploy the appliances one by one.</span></span>
  
1. <span data-ttu-id="a7de0-115">次のコマンドレットを実行して、現在のアプライアンス上にある既存の仮想マシンをすべてアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="a7de0-115">Run the following cmdlet to uninstall all existing virtual machines on the current appliance:</span></span> 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. <span data-ttu-id="a7de0-116">次のコマンドレットを実行してアプライアンスの登録を解除します。</span><span class="sxs-lookup"><span data-stu-id="a7de0-116">Run the following cmdlet to unregister the appliance:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

3. <span data-ttu-id="a7de0-117">アプライアンスディレクトリで CloudConnector .ini ファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="a7de0-117">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="a7de0-118">次のコマンドレットを実行して構成を更新します。 (この手順はバージョン2にのみ適用されます。以前のバージョンでは、次の手順に進んでください。)</span><span class="sxs-lookup"><span data-stu-id="a7de0-118">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
   ```powershell
   Import-CcConfiguration 
   ```

5. <span data-ttu-id="a7de0-119">次のコマンドレットを実行して、アプライアンスを再度登録します。</span><span class="sxs-lookup"><span data-stu-id="a7de0-119">Run the following cmdlet to register the appliance again:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

6. <span data-ttu-id="a7de0-120">サイト内の他のすべてのアプライアンスで次のコマンドレットを実行して、最新の構成を選択します。</span><span class="sxs-lookup"><span data-stu-id="a7de0-120">Run the following cmdlet on all other appliances in the site to pick up the latest configuration:</span></span>
    
   ```powershell
   Publish-CcAppliance
   ```

7. <span data-ttu-id="a7de0-121">次のコマンドレットを実行して、現在のアプライアンスで Cloud Connector を再展開します。</span><span class="sxs-lookup"><span data-stu-id="a7de0-121">Run the following cmdlet to redeploy Cloud Connector on the current appliance:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="modify-the-configuration-of-multiple-sites"></a><span data-ttu-id="a7de0-122">複数のサイトの構成を変更する</span><span class="sxs-lookup"><span data-stu-id="a7de0-122">Modify the configuration of multiple sites</span></span>
<span data-ttu-id="a7de0-123"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="a7de0-123"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="a7de0-124">展開内の複数のサイトの構成を変更するには、1つのサイトの手順に従って、一度に1つのサイトを更新します。</span><span class="sxs-lookup"><span data-stu-id="a7de0-124">To modify the configuration for multiple sites in a deployment, follow the steps for a single site, updating one site at a time.</span></span>
  
## <a name="modify-the-configuration-of-your-microsoft-365-or-office-365-organization-to-enable-automatic-updates"></a><span data-ttu-id="a7de0-125">Microsoft 365 または Office 365 組織の構成を変更して自動更新を有効にする</span><span class="sxs-lookup"><span data-stu-id="a7de0-125">Modify the configuration of your Microsoft 365 or Office 365 organization to enable automatic updates</span></span>
<span data-ttu-id="a7de0-126"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="a7de0-126"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="a7de0-127">オペレーティングシステムの自動更新と Bits の自動更新を有効にするには、オンライン管理用の Skype for Business テナント管理者アカウントを使用し、テナントのリモート PowerShell を次のように使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7de0-127">To enable operating system automatic updates and Bits automatic updates, you must use the Skype for Business tenant admin account for online management and use tenant remote PowerShell as follows.</span></span>
  
<span data-ttu-id="a7de0-128">オペレーティングシステムの自動更新または Bits 自動更新を無効にした場合、ホストと仮想マシンで重要な Windows 更新プログラムが使用できなくなり、Cloud Connector が新しいバージョンに自動的にアップグレードされることはありません。</span><span class="sxs-lookup"><span data-stu-id="a7de0-128">If you disabled operating system automatic updates or Bits automatic updates, your host and virtual machine may miss important Windows updates, and Cloud Connector will not upgrade to the new version automatically.</span></span> <span data-ttu-id="a7de0-129">自動更新を有効にすることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a7de0-129">It is highly recommended that you enable automatic updates.</span></span>
  
1. <span data-ttu-id="a7de0-130">サイトの EnableAutoUpdate プロパティを true (既定値) に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7de0-130">The EnableAutoUpdate property of the site needs to be set to true (the default value).</span></span> <span data-ttu-id="a7de0-131">次のコマンドレットを実行して、EnableAutoUpdate が true に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a7de0-131">Run the following cmdlet to make sure EnableAutoUpdate is set to true:</span></span>
    
   ```powershell
   Get-CsHybridPSTNSite -Identity <SiteName>
   ```

2. <span data-ttu-id="a7de0-132">テナントの自動更新時間ウィンドウを作成します。</span><span class="sxs-lookup"><span data-stu-id="a7de0-132">Create auto update time window for the tenant.</span></span>
    
    <span data-ttu-id="a7de0-133">時間枠は、日単位、週単位、月単位で指定できます。</span><span class="sxs-lookup"><span data-stu-id="a7de0-133">The time window can be daily, weekly and monthly.</span></span> <span data-ttu-id="a7de0-134">すべての時間帯に、開始時刻と期間が必要です。</span><span class="sxs-lookup"><span data-stu-id="a7de0-134">All the time windows need a start time and a duration.</span></span>
    
   - <span data-ttu-id="a7de0-135">日単位の時間枠の場合は、開始時刻と期間のみが必要です。</span><span class="sxs-lookup"><span data-stu-id="a7de0-135">For a daily time window, only start time and duration are needed.</span></span> 
    
   - <span data-ttu-id="a7de0-136">週単位の時間枠の場合、曜日が必要です。これは、1日または複数の日数でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="a7de0-136">For a weekly time window, days of week are needed, which can be a single day or multiple days.</span></span>
    
   - <span data-ttu-id="a7de0-137">月単位の時間枠の場合は、2つの種類があります。</span><span class="sxs-lookup"><span data-stu-id="a7de0-137">For a monthly time window, there can be two types.</span></span> <span data-ttu-id="a7de0-138">最初の種類は、月の日付を指定することで、1日にすることができます。</span><span class="sxs-lookup"><span data-stu-id="a7de0-138">The first type is to specify the day of the month, which can be a single day.</span></span> <span data-ttu-id="a7de0-139">2番目の種類は、月の週と曜日を指定することです。1つまたは複数のアイテムでもかまいません。</span><span class="sxs-lookup"><span data-stu-id="a7de0-139">The second type is to specify the weeks of the month, along with days of the week, which both can be a single item or multiple items.</span></span>
    
   - <span data-ttu-id="a7de0-140">各テナントでは、20時間のウィンドウを定義できます。</span><span class="sxs-lookup"><span data-stu-id="a7de0-140">Each tenant can have 20 time windows defined.</span></span> <span data-ttu-id="a7de0-141">新しいテナントの既定の時間枠は、オペレーティングシステムの更新および Bits 更新の既定の時間枠として作成されます。</span><span class="sxs-lookup"><span data-stu-id="a7de0-141">The default time window will be created for a new tenant as the default time window for operating system update and Bits update.</span></span> <span data-ttu-id="a7de0-142">次のコマンドレットを実行して、日単位、週単位、または月単位の時間枠を設定します。</span><span class="sxs-lookup"><span data-stu-id="a7de0-142">Run the following cmdlet(s) to set the daily, weekly or monthly time window:</span></span>
    
   ```powershell
   New-CsTenantUpdateTimeWindow -Identity Night -Daily -StartTime 22:00 -Duration 6:00
   ```

   ```powershell
   New-CsTenantUpdateTimeWindow -Identity WeekdayNight -Weekly -DaysOfWeek Monday,Tuesday,Wednesday,Thursday,Friday -StartTime 22:00 -Duration 4:00
   ```

   ```powershell
   New-CsTenantUpdateTimeWindow -Identity FirstAndLastWeekend -Monthly -WeeksOfMonth First,Last -DaysOfWeek Sunday,Saturday -StartTime 0:00 -Duration 10:00
   ```

   ```powershell
   New-CsTenantUpdateTimeWindow -Identity MidDayOfMonth -Monthly -DayOfMonth 15 -StartTime 0:00 -Duration 1.00:00
   ```

   - <span data-ttu-id="a7de0-143">更新時刻ウィンドウをサイトに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="a7de0-143">Assign update time windows to the site.</span></span> 
    
     <span data-ttu-id="a7de0-144">Bits 更新時間および OS 更新時間ウィンドウは個別に構成されます。</span><span class="sxs-lookup"><span data-stu-id="a7de0-144">The Bits update time and OS update time windows are configured separately.</span></span> <span data-ttu-id="a7de0-145">これらの両方には、1つまたは複数の時間帯を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="a7de0-145">Both of them can be assigned single or multiple time windows.</span></span> <span data-ttu-id="a7de0-146">各時間枠は、さまざまなサイトに割り当てることができ、さまざまな目的 (Bits 更新および OS 更新) に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="a7de0-146">Each time window can be assigned to different sites and different purpose (Bits update and OS update).</span></span> <span data-ttu-id="a7de0-147">サイトの時間枠を設定するには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="a7de0-147">Run the following cmdlet to set the time window for the site:</span></span> 
    
   ```powershell
   Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
   ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a><span data-ttu-id="a7de0-148">専用のテナント管理者の資格情報を更新する</span><span class="sxs-lookup"><span data-stu-id="a7de0-148">Update the dedicated tenant admin credentials</span></span>
<span data-ttu-id="a7de0-149"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="a7de0-149"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="a7de0-150">クラウドコネクタの Microsoft 365 または Office 365 組織の管理上の変更は、必要なアクセス許可を持つアカウントから作成されます。</span><span class="sxs-lookup"><span data-stu-id="a7de0-150">Administrative changes in the Microsoft 365 or Office 365 organization for Cloud Connector are made from an account with the needed permissions.</span></span> <span data-ttu-id="a7de0-151">2.0 より前の Cloud Connector のバージョンでは、このアカウントは専用のグローバルテナント管理者アカウントです。</span><span class="sxs-lookup"><span data-stu-id="a7de0-151">In Cloud Connector versions before 2.0, that account is a dedicated global tenant admin account.</span></span> <span data-ttu-id="a7de0-152">Cloud Connector バージョン2.0 以降では、このアカウントは、Skype for Business 管理者権限を持つ Microsoft 365 または Office 365 アカウントにすることができます。</span><span class="sxs-lookup"><span data-stu-id="a7de0-152">In Cloud Connector versions 2.0 and later, that account can be a Microsoft 365 or Office 365 account with Skype for Business Administrator rights.</span></span>
  
<span data-ttu-id="a7de0-153">Microsoft 365 または Office 365 で管理者アカウントの資格情報が変更された場合は、展開した各 Cloud Connector アプライアンス上で次の管理者 PowerShell コマンドを実行して、ローカルにキャッシュされた資格情報を Cloud Connector で更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7de0-153">If your admin account credentials change in Microsoft 365 or Office 365, you also need to update the locally cached credentials in Cloud Connector by running the following Administrator PowerShell command on each Cloud Connector appliance you have deployed:</span></span>
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a><span data-ttu-id="a7de0-154">ホストサーバーのパスワードを更新する</span><span class="sxs-lookup"><span data-stu-id="a7de0-154">Update the password for the host server</span></span>
<span data-ttu-id="a7de0-155"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="a7de0-155"><a name="BKMK_UpdatePassword"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="a7de0-156">このセクションは、Cloud Connector バージョン2.0 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="a7de0-156">This section is applicable to Cloud Connector version 2.0 and later.</span></span> 
  
<span data-ttu-id="a7de0-157">すべての Cloud Connector 資格情報は、次のファイルに格納されます。 "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser \></span><span class="sxs-lookup"><span data-stu-id="a7de0-157">All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="a7de0-158">ホストサーバーのパスワードが変更された場合は、ローカルに格納されている資格情報を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7de0-158">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
  
<span data-ttu-id="a7de0-159">Cloud Connector アプライアンスでローカルに格納されている資格情報を更新するには、 [Get](get-cccredential.md) [と cccredential の各コマンドレット](set-cccredential.md)を使用して、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a7de0-159">To update the locally stored credentials on the Cloud Connector appliance, use the [Get-CcCredential](get-cccredential.md) and [Set-CcCredential](set-cccredential.md) cmdlets and follow these steps:</span></span>
  
1. <span data-ttu-id="a7de0-160">後で必要になるパスワードを取得するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a7de0-160">Run the following commands to retrieve the passwords you will need later:</span></span> 
    
   - <span data-ttu-id="a7de0-161">取得-CcCredential-AccountType DomainAdmin-DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="a7de0-161">Get-CcCredential -AccountType DomainAdmin -DisplayPassword</span></span>
    
   - <span data-ttu-id="a7de0-162">取得-CcCredential-AccountType VMAdmin-DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="a7de0-162">Get-CcCredential -AccountType VMAdmin -DisplayPassword</span></span>
    
   - <span data-ttu-id="a7de0-163">取得-CcCredential-AccountType CceService-DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="a7de0-163">Get-CcCredential -AccountType CceService -DisplayPassword</span></span>
    
2. <span data-ttu-id="a7de0-164">ホストサーバー上のアカウントのパスワードを変更します。</span><span class="sxs-lookup"><span data-stu-id="a7de0-164">Change the password of your account on the host server.</span></span>
    
3. <span data-ttu-id="a7de0-165">ホストサーバーを再起動します。</span><span class="sxs-lookup"><span data-stu-id="a7de0-165">Restart the host server.</span></span>
    
4. <span data-ttu-id="a7de0-166">次のファイルを削除します。 "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser \></span><span class="sxs-lookup"><span data-stu-id="a7de0-166">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
5. <span data-ttu-id="a7de0-167">管理者として PowerShell コンソールを起動してから、説明に従ってパスワードを再入力するには、「Register-CcAppliance-Local」を実行します。</span><span class="sxs-lookup"><span data-stu-id="a7de0-167">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="a7de0-168">Cloud Connector の展開の前に入力したのと同じパスワードを入力してください。</span><span class="sxs-lookup"><span data-stu-id="a7de0-168">Be sure you enter the same password you entered before for the Cloud Connector deployment.</span></span>
    
<span data-ttu-id="a7de0-169">既定では、VmAdmin と DomainAdmin は CceService と同じパスワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="a7de0-169">By default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="a7de0-170">手順1で返された DomainAdmin、VMAdmin、および CceService のパスワードが異なる場合は、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7de0-170">If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
  
1. <span data-ttu-id="a7de0-171">Set-CcCredential-AccountType DomainAdmin を次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="a7de0-171">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
1. <span data-ttu-id="a7de0-172">古いアカウントの資格情報の入力を求められたら、CceService パスワードに使用した資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="a7de0-172">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="a7de0-173">新しいアカウントの資格情報の入力を求められたら、手順1で返された DomainAdmin パスワードのパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="a7de0-173">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
2. <span data-ttu-id="a7de0-174">Set-CcCredential-AccountType VmAdmin を次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="a7de0-174">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
1. <span data-ttu-id="a7de0-175">古いアカウントの資格情報の入力を求められたら、CceService パスワードに使用した資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="a7de0-175">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="a7de0-176">新しいアカウントの資格情報の入力を求められたら、手順1で返された VmAdmin パスワードのパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="a7de0-176">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
## <a name="update-the-password-for-the-cceservice-account"></a><span data-ttu-id="a7de0-177">CceService アカウントのパスワードを更新する</span><span class="sxs-lookup"><span data-stu-id="a7de0-177">Update the password for the CceService account</span></span>
<span data-ttu-id="a7de0-178"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="a7de0-178"><a name="BKMK_UpdatePassword"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="a7de0-179">このセクションは、Cloud Connector バージョン2.0.1 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="a7de0-179">This section is applicable to Cloud Connector version 2.0.1 and later.</span></span> 
  
<span data-ttu-id="a7de0-180">Cloud Connector service は、Cloud Connector Management service を実行します。</span><span class="sxs-lookup"><span data-stu-id="a7de0-180">The Cloud Connector service runs the Cloud Connector Management service.</span></span> <span data-ttu-id="a7de0-181">CceService アカウントは、Cloud Connector Edition の展開時に作成され、次のファイルに格納されます。 "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser \> "および"%SystemDrive%\Programdata\Cloudconnector\credentials..CceService "。</span><span class="sxs-lookup"><span data-stu-id="a7de0-181">The CceService account is created during the Cloud Connector Edition deployment and stored in the following files: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" and "%SystemDrive%\Programdata\Cloudconnector\credentials..CceService.xml".</span></span>
  
<span data-ttu-id="a7de0-182">すべてのアプライアンスがサイトディレクトリ共有にアクセスできるようにするには、CceService アカウントのパスワードが、サイト内に展開されているすべてのアプライアンスで同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7de0-182">To ensure that all appliances can access the site directory share, the password for the CceService account must be the same on all appliances deployed within the site.</span></span> <span data-ttu-id="a7de0-183">以下の点にご注意ください。</span><span class="sxs-lookup"><span data-stu-id="a7de0-183">Keep the following in mind:</span></span>
  
- <span data-ttu-id="a7de0-184">既定では、CceService アカウントは、[パスワードを無期限にする] として構成されています。</span><span class="sxs-lookup"><span data-stu-id="a7de0-184">By default, the CceService account is configured as "Password never expires".</span></span> <span data-ttu-id="a7de0-185">パスワードを更新するときは、この構成を維持することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a7de0-185">When you update the password, Microsoft recommends keeping this configuration.</span></span>
    
- <span data-ttu-id="a7de0-186">Bits または Windows update では、非ピーク時の使用時と自動更新時間帯の外部でパスワードを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7de0-186">You should update the password during non-peak usage periods and outside of automatic update time windows for bits or Windows updates.</span></span> <span data-ttu-id="a7de0-187">パスワードを更新するときは、アプライアンスをドレインして再起動する必要があります。これにはしばらく時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="a7de0-187">When you update the password, the appliance needs to be drained and restarted, which takes some time.</span></span> <span data-ttu-id="a7de0-188">アプライアンスを再起動すると、自動更新操作が中断されます。</span><span class="sxs-lookup"><span data-stu-id="a7de0-188">Restarting the appliance will interrupt automatic update operations.</span></span> 
    
- <span data-ttu-id="a7de0-189">CceService アカウントのパスワードを変更する場合は、すべての資格情報を指定して、ローカルに格納されているファイルで更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7de0-189">When you change the CceService account password, you will need to specify all the credentials and update them in the locally stored file.</span></span> 
    
<span data-ttu-id="a7de0-190">同じ PSTN サイトに属するアプライアンスごとに、次のものを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7de0-190">For each appliance that belongs to the same PSTN site, you will need to specify the following:</span></span> 
  
1. <span data-ttu-id="a7de0-191">後で使用するアカウント名とパスワードを取得するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a7de0-191">Run the following commands to retrieve the account names and passwords that you will use later:</span></span>
    
   ```powershell
   Get-CcCredential -AccountType TenantAdmin -DisplayPassword
   Get-CcCredential -AccountType TenantAdmin
   Get-CcCredential -AccountType OMSWorkspace -DisplayPassword
   Get-CcCredential -AccountType OMSWorkspace 
   Get-CcCredential -AccountType ExternalCert -DisplayPassword
   Get-CcCredential -AccountType CABackupFile -DisplayPassword
   Get-CcCredential -AccountType CceService -DisplayPassword
   Get-CcCredential -AccountType VMAdmin -DisplayPassword
   Get-CcCredential -AccountType DomainAdmin -DisplayPassword
   ```

2. <span data-ttu-id="a7de0-192">コマンドレットを実行してアプライアンスをドレインし、手動メンテナンスモードに移行します。</span><span class="sxs-lookup"><span data-stu-id="a7de0-192">Run the Enter-CcUpdate cmdlet to drain the appliance and move it into manual maintenance mode.</span></span>
    
3. <span data-ttu-id="a7de0-193">ホストサーバー上の CceService アカウントのパスワードを更新します。</span><span class="sxs-lookup"><span data-stu-id="a7de0-193">Update the password of the CceService account on the host server.</span></span>
    
4. <span data-ttu-id="a7de0-194">ホストサーバーを再起動します。</span><span class="sxs-lookup"><span data-stu-id="a7de0-194">Restart the host server.</span></span>
    
5. <span data-ttu-id="a7de0-195">Restore-CcCredentials コマンドレットを実行して、説明に従ってパスワードを再入力します。</span><span class="sxs-lookup"><span data-stu-id="a7de0-195">Run the Restore-CcCredentials cmdlet to re-enter the passwords following the description.</span></span> 
    
    <span data-ttu-id="a7de0-196">CceService アカウントを除き、Cloud Connector の展開の前に入力したのと同じパスワードを入力してください。</span><span class="sxs-lookup"><span data-stu-id="a7de0-196">Be sure you enter the same password you entered before for the Cloud Connector deployment except for the CceService account.</span></span> <span data-ttu-id="a7de0-197">CceService アカウントには、新しいパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="a7de0-197">For the CceService account, enter your new password.</span></span> <span data-ttu-id="a7de0-198">CceService アカウントの新しいパスワードが、PSTN サイト内のすべてのアプライアンスで同じであることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="a7de0-198">Be sure the new password for the CceService account is the same for all appliances in the PSTN site.</span></span>
    
6. <span data-ttu-id="a7de0-199">既定では、VmAdmin と DomainAdmin は CceService と同じパスワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="a7de0-199">By default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="a7de0-200">手順1で返された DomainAdmin、VMAdmin、および CceService のパスワードが異なる場合は、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7de0-200">If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
    
7. <span data-ttu-id="a7de0-201">Set-CcCredential-AccountType DomainAdmin を次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="a7de0-201">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
   - <span data-ttu-id="a7de0-202">古いアカウントの資格情報の入力を求められたら、CceService パスワードに使用した資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="a7de0-202">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
   - <span data-ttu-id="a7de0-203">新しいアカウントの資格情報の入力を求められたら、手順1で返された DomainAdmin パスワードのパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="a7de0-203">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
8. <span data-ttu-id="a7de0-204">Set-CcCredential-AccountType VmAdmin を次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="a7de0-204">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
   - <span data-ttu-id="a7de0-205">古いアカウントの資格情報の入力を求められたら、CceService パスワードに使用した資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="a7de0-205">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
   - <span data-ttu-id="a7de0-206">新しいアカウントの資格情報の入力を求められたら、手順1で返された VmAdmin パスワードのパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="a7de0-206">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
9. <span data-ttu-id="a7de0-207">終了-CcUpdate コマンドレットを実行してアプライアンスを手動メンテナンスモードの外に移動します。</span><span class="sxs-lookup"><span data-stu-id="a7de0-207">Run the Exit-CcUpdate cmdlet to move the appliance out of manual maintenance mode.</span></span>
    
10. <span data-ttu-id="a7de0-208">同じ PSTN サイト内のすべてのアプライアンスでこれらの手順を完了した後、サイトのルートディレクトリにある次のファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="a7de0-208">After you complete these steps on all appliances in the same PSTN site, delete the following files in the site root directory:</span></span>
    
    - <span data-ttu-id="a7de0-209">CcLockFile</span><span class="sxs-lookup"><span data-stu-id="a7de0-209">CcLockFile</span></span>
    
    - <span data-ttu-id="a7de0-210">Site_ \< エッジ外部 Sip プールの fqdn\></span><span class="sxs-lookup"><span data-stu-id="a7de0-210">Site_\<Edge External Sip Pool fqdn\></span></span>
    
    - <span data-ttu-id="a7de0-211">Tenant_ \< エッジ外部 Sip プールの fqdn\></span><span class="sxs-lookup"><span data-stu-id="a7de0-211">Tenant_\<Edge External Sip Pool fqdn\></span></span>
    
    - <span data-ttu-id="a7de0-212">TenantConfigLock_ \< エッジ外部 Sip プールの fqdn\></span><span class="sxs-lookup"><span data-stu-id="a7de0-212">TenantConfigLock_\<Edge External Sip Pool fqdn\></span></span>
    
## <a name="add-a-new-sip-domain"></a><span data-ttu-id="a7de0-213">新しい SIP ドメインを追加する</span><span class="sxs-lookup"><span data-stu-id="a7de0-213">Add a new SIP domain</span></span>
<span data-ttu-id="a7de0-214"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="a7de0-214"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="a7de0-215">既存の Cloud Connector 展開に新しい SIP ドメイン (または複数の SIP ドメイン) を追加するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a7de0-215">To add a new SIP domain (or multiple SIP domains) to your existing Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="a7de0-216">Microsoft 365 または Office 365 でドメインを更新する手順を完了しており、DNS レコードを追加できることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="a7de0-216">Make sure you've completed the steps to update your domain in Microsoft 365 or Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="a7de0-217">Microsoft 365 または Office 365 でドメインをセットアップする方法の詳細については、「 [Add a domain To microsoft 365」または「office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a7de0-217">For more information about how to set up your domain in Microsoft 365 or Office 365, see [Add a domain to Microsoft 365 or Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="a7de0-218">新しい SIP ドメインを使用して、Cloud Connector 構成ファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="a7de0-218">Update the Cloud Connector configuration file with the new SIP domain or domains.</span></span>
    
3. <span data-ttu-id="a7de0-219">Cloud Connector の構成で定義されている各 SIP ドメインについて、sip の追加の SAN 名を使用して新しいエッジの外部証明書を要求します。</span><span class="sxs-lookup"><span data-stu-id="a7de0-219">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="a7de0-220">新しいエッジの外部証明書のパスを次のように設定します。</span><span class="sxs-lookup"><span data-stu-id="a7de0-220">Set the path for the new Edge external certificate as follows:</span></span>
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    <span data-ttu-id="a7de0-221">指示に従って、 [1 つのサイトの構成を変更](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite)するか、[複数のサイトの構成を変更](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites)します。</span><span class="sxs-lookup"><span data-stu-id="a7de0-221">Follow the instructions to [Modify the configuration of a single site](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) or [Modify the configuration of multiple sites](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites).</span></span>
    
## <a name="modify-the-primary-sip-domain"></a><span data-ttu-id="a7de0-222">プライマリ SIP ドメインを変更する</span><span class="sxs-lookup"><span data-stu-id="a7de0-222">Modify the primary SIP domain</span></span>
<span data-ttu-id="a7de0-223"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="a7de0-223"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="a7de0-224">Cloud Connector の展開でプライマリ SIP ドメインを変更する必要がある場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a7de0-224">If you need to change the primary SIP domain in your Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="a7de0-225">Microsoft 365 または Office 365 でドメインを更新する手順を完了しており、DNS レコードを追加できることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="a7de0-225">Make sure you've completed the steps to update your domain in Microsoft 365 or Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="a7de0-226">Microsoft 365 または Office 365 でドメインをセットアップする方法の詳細については、「 [Add a domain To microsoft 365」または「office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a7de0-226">For more information about how to set up your domain in Microsoft 365 or Office 365, see [Add a domain to Microsoft 365 or Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="a7de0-227">新しい SIP ドメインを使用して、Cloud Connector 構成ファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="a7de0-227">Update the Cloud Connector configuration file with the new SIP domain.</span></span>
    
3. <span data-ttu-id="a7de0-228">Cloud Connector の構成で定義されている各 SIP ドメインについて、sip の追加の SAN 名を使用して新しいエッジの外部証明書を要求します。</span><span class="sxs-lookup"><span data-stu-id="a7de0-228">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="a7de0-229">新しいエッジの外部証明書のパスを次のように設定します。</span><span class="sxs-lookup"><span data-stu-id="a7de0-229">Set the path for the new Edge external certificate as follows:</span></span>
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    <span data-ttu-id="a7de0-230">Cloud Connector 上の管理者 PowerShell で次のコマンドレットを実行して、サイト内の各アプライアンスのテナント登録を削除します。</span><span class="sxs-lookup"><span data-stu-id="a7de0-230">Remove the tenant registration for each appliance in a site by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

6. 
    
    <span data-ttu-id="a7de0-231">Skype for Business Online PowerShell で次のコマンドレットを実行して、各サイトのサイト登録を削除します。</span><span class="sxs-lookup"><span data-stu-id="a7de0-231">Remove the site registration for each site by running the following cmdlet in Skype for Business Online PowerShell:</span></span>
    
   ```powershell
   Remove-CsHybridPSTNSite
   ```

7. 
    
    <span data-ttu-id="a7de0-232">Cloud Connector 上の管理者 PowerShell で次のコマンドレットを実行して、各アプライアンスをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="a7de0-232">Uninstall each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Uninstall-CcAppliance
   ```

8. 
    
     <span data-ttu-id="a7de0-233">Cloud Connector 上の管理者 PowerShell で次のコマンドレットを実行して、各アプライアンスを登録します。</span><span class="sxs-lookup"><span data-stu-id="a7de0-233">Register each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Register-ccAppliance
   ```

9. 
    
     <span data-ttu-id="a7de0-234">Cloud Connector 上の管理者 PowerShell で次のコマンドレットを実行して、各アプライアンスを1つずつインストールします。</span><span class="sxs-lookup"><span data-stu-id="a7de0-234">Install each appliance, one by one, by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a><span data-ttu-id="a7de0-235">外部エッジ証明書を新しい証明書に置き換える</span><span class="sxs-lookup"><span data-stu-id="a7de0-235">Replace the external Edge certificate with a new certificate</span></span>
<span data-ttu-id="a7de0-236"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="a7de0-236"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="a7de0-237">Cloud Connector アプライアンスで外部エッジ証明書を置き換える必要がある場合は、新しいエッジ証明書を取得し、秘密キーと完全な証明書チェーンを含む PFX ファイルを準備してから、各アプライアンスで次の操作を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7de0-237">When you need to replace the external Edge certificate on your Cloud Connector appliances, you will need to obtain a new Edge certificate, prepare the PFX file containing the Private Key and full certificate chain, and then do the following on each appliance:</span></span>
  
1. <span data-ttu-id="a7de0-238">コマンドレットを使用して、アプライアンスをメンテナンスモードにします。</span><span class="sxs-lookup"><span data-stu-id="a7de0-238">Put the appliance in maintenance mode by using the Enter-CcUpdate cmdlet.</span></span>
    
2. <span data-ttu-id="a7de0-239">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a7de0-239">Run the following command:</span></span> 
    
   ```powershell
   Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
   ```

3. 
    
    <span data-ttu-id="a7de0-240">新しい証明書のパスワードが old と同じ場合は、インポートが成功します。</span><span class="sxs-lookup"><span data-stu-id="a7de0-240">If the password of the new certificate is the same as the old, the import will be successful.</span></span> <span data-ttu-id="a7de0-241">パスワードが異なる場合は、パスワードが間違っているというエラーが表示されます。-Local パラメーターを指定して CcAppliance コマンドレットを実行し、手順2を繰り返して、パスワードをリセットする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7de0-241">If the password is different, you will receive an error that the password is wrong, and you will need to reset the password by running the Register-CcAppliance cmdlet with the -Local parameter, and then repeating step 2.</span></span> 
    
4. <span data-ttu-id="a7de0-242">終了-CcUpdate コマンドレットを使用してアプライアンスのメンテナンスモードを停止します。</span><span class="sxs-lookup"><span data-stu-id="a7de0-242">Take the appliance out of maintenance mode by using the Exit -CcUpdate cmdlet.</span></span>
    

