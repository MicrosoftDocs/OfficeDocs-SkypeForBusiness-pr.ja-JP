---
title: 既存のクラウド コネクタの展開構成の変更
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
description: このトピックの手順に従って、既存の Skype for Business Cloud Connector Edition 1.4.1 以降の展開の構成を変更します。
ms.openlocfilehash: 7fdfdd5ac5a76ebbc3ac58e12a69e2e3af1330cd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109173"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a><span data-ttu-id="ace0f-103">既存のクラウド コネクタの展開構成の変更</span><span class="sxs-lookup"><span data-stu-id="ace0f-103">Modify the configuration of an existing Cloud Connector deployment</span></span>

> [!Important]
> <span data-ttu-id="ace0f-104">Cloud Connector Edition は、Skype for Business Online と共に 2021 年 7 月 31 日に廃止されます。</span><span class="sxs-lookup"><span data-stu-id="ace0f-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="ace0f-105">組織が Teams にアップグレードしたら、直接ルーティングを使用してオンプレミスのテレフォニー ネットワークを Teams に接続する方法 [について説明します](/MicrosoftTeams/direct-routing-landing-page)。</span><span class="sxs-lookup"><span data-stu-id="ace0f-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="ace0f-106">このトピックの手順に従って、既存の Skype for Business Cloud Connector Edition 1.4.1 以降の展開の構成を変更します。</span><span class="sxs-lookup"><span data-stu-id="ace0f-106">Follow the steps in this topic to modify the configuration of an existing Skype for Business Cloud Connector Edition 1.4.1 or later deployment.</span></span> 
  
## <a name="modify-the-configuration-of-a-single-site"></a><span data-ttu-id="ace0f-107">1 つのサイトの構成を変更する</span><span class="sxs-lookup"><span data-stu-id="ace0f-107">Modify the configuration of a single site</span></span>
<span data-ttu-id="ace0f-108"><a name="BKMK_SIngleSite"> </a></span><span class="sxs-lookup"><span data-stu-id="ace0f-108"><a name="BKMK_SIngleSite"> </a></span></span>

<span data-ttu-id="ace0f-109">サイト内にアプライアンスが 1 つしかない場合、アプライアンスの展開後に構成設定を変更する場合は、CloudConnector.ini ファイルを変更して展開を再度開始できます。</span><span class="sxs-lookup"><span data-stu-id="ace0f-109">If there is only one appliance in the site, when you want to change the configuration settings after the appliance is deployed, you can modify the CloudConnector.ini file and start the deployment again.</span></span>
  
1. <span data-ttu-id="ace0f-110">次のコマンドレットを実行して、ホスト サーバー上のすべての既存の仮想マシンをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="ace0f-110">Run the following cmdlet to uninstall all existing virtual machines on the host server:</span></span> 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. <span data-ttu-id="ace0f-111">次のコマンドレットを実行して、アプライアンスの登録を解除します。</span><span class="sxs-lookup"><span data-stu-id="ace0f-111">Run the following cmdlet to unregister the appliance:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

3. <span data-ttu-id="ace0f-112">アプライアンス ディレクトリCloudConnector.iniファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="ace0f-112">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="ace0f-113">構成を更新するには、次のコマンドレットを実行します (この手順はバージョン 2 にのみ適用されます。以前のバージョンの場合は、次の手順に進みます)。</span><span class="sxs-lookup"><span data-stu-id="ace0f-113">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
   ```powershell
   Import-CcConfiguration 
   ```

5. <span data-ttu-id="ace0f-114">次のコマンドレットを実行して、アプライアンスを再度登録します。</span><span class="sxs-lookup"><span data-stu-id="ace0f-114">Run the following cmdlet to register the appliance again:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

6. <span data-ttu-id="ace0f-115">Skype for Business Cloud Connector Edition をインストールするには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="ace0f-115">Run the following cmdlet to install Skype for Business Cloud Connector Edition:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

<span data-ttu-id="ace0f-116">サイトに複数のアプライアンスがある場合は、次の手順に従い、CloudConnector.ini ファイルを変更し、アプライアンスを 1 つ 1 つ再展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ace0f-116">If there is more than one appliance in the site, you'll need to follow these steps, modify the CloudConnector.ini file, and redeploy the appliances one by one.</span></span>
  
1. <span data-ttu-id="ace0f-117">次のコマンドレットを実行して、現在のアプライアンス上のすべての既存の仮想マシンをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="ace0f-117">Run the following cmdlet to uninstall all existing virtual machines on the current appliance:</span></span> 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. <span data-ttu-id="ace0f-118">次のコマンドレットを実行して、アプライアンスの登録を解除します。</span><span class="sxs-lookup"><span data-stu-id="ace0f-118">Run the following cmdlet to unregister the appliance:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

3. <span data-ttu-id="ace0f-119">アプライアンス ディレクトリCloudConnector.iniファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="ace0f-119">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="ace0f-120">構成を更新するには、次のコマンドレットを実行します (この手順はバージョン 2 にのみ適用されます。以前のバージョンの場合は、次の手順に進みます)。</span><span class="sxs-lookup"><span data-stu-id="ace0f-120">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
   ```powershell
   Import-CcConfiguration 
   ```

5. <span data-ttu-id="ace0f-121">次のコマンドレットを実行して、アプライアンスを再度登録します。</span><span class="sxs-lookup"><span data-stu-id="ace0f-121">Run the following cmdlet to register the appliance again:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

6. <span data-ttu-id="ace0f-122">サイト内の他のすべてのアプライアンスで次のコマンドレットを実行して、最新の構成を取得します。</span><span class="sxs-lookup"><span data-stu-id="ace0f-122">Run the following cmdlet on all other appliances in the site to pick up the latest configuration:</span></span>
    
   ```powershell
   Publish-CcAppliance
   ```

7. <span data-ttu-id="ace0f-123">次のコマンドレットを実行して、現在のアプライアンスにクラウド コネクタを再展開します。</span><span class="sxs-lookup"><span data-stu-id="ace0f-123">Run the following cmdlet to redeploy Cloud Connector on the current appliance:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="modify-the-configuration-of-multiple-sites"></a><span data-ttu-id="ace0f-124">複数のサイトの構成を変更する</span><span class="sxs-lookup"><span data-stu-id="ace0f-124">Modify the configuration of multiple sites</span></span>
<span data-ttu-id="ace0f-125"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="ace0f-125"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="ace0f-126">展開内の複数のサイトの構成を変更するには、1 つのサイトの手順に従って、一度に 1 つのサイトを更新します。</span><span class="sxs-lookup"><span data-stu-id="ace0f-126">To modify the configuration for multiple sites in a deployment, follow the steps for a single site, updating one site at a time.</span></span>
  
## <a name="modify-the-configuration-of-your-microsoft-365-or-office-365-organization-to-enable-automatic-updates"></a><span data-ttu-id="ace0f-127">自動更新を有効にするには、Microsoft 365 または Office 365 組織の構成を変更する</span><span class="sxs-lookup"><span data-stu-id="ace0f-127">Modify the configuration of your Microsoft 365 or Office 365 organization to enable automatic updates</span></span>
<span data-ttu-id="ace0f-128"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="ace0f-128"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="ace0f-129">オペレーティング システムの自動更新と Bits 自動更新を有効にするには、Skype for Business テナント管理者アカウントをオンライン管理に使用し、次のようにテナント リモート PowerShell を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ace0f-129">To enable operating system automatic updates and Bits automatic updates, you must use the Skype for Business tenant admin account for online management and use tenant remote PowerShell as follows.</span></span>
  
<span data-ttu-id="ace0f-130">オペレーティング システムの自動更新または Bits 自動更新を無効にした場合、ホストと仮想マシンは重要な Windows 更新プログラムを見逃す可能性があります。クラウド コネクタは新しいバージョンに自動的にアップグレードしません。</span><span class="sxs-lookup"><span data-stu-id="ace0f-130">If you disabled operating system automatic updates or Bits automatic updates, your host and virtual machine may miss important Windows updates, and Cloud Connector will not upgrade to the new version automatically.</span></span> <span data-ttu-id="ace0f-131">自動更新を有効にすることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ace0f-131">It is highly recommended that you enable automatic updates.</span></span>
  
1. <span data-ttu-id="ace0f-132">サイトの EnableAutoUpdate プロパティを true (既定値) に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ace0f-132">The EnableAutoUpdate property of the site needs to be set to true (the default value).</span></span> <span data-ttu-id="ace0f-133">EnableAutoUpdate が true に設定されている場合は、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="ace0f-133">Run the following cmdlet to make sure EnableAutoUpdate is set to true:</span></span>
    
   ```powershell
   Get-CsHybridPSTNSite -Identity <SiteName>
   ```

2. <span data-ttu-id="ace0f-134">テナントの自動更新タイム ウィンドウを作成します。</span><span class="sxs-lookup"><span data-stu-id="ace0f-134">Create auto update time window for the tenant.</span></span>
    
    <span data-ttu-id="ace0f-135">タイム ウィンドウは、日単位、週単位、月単位で指定できます。</span><span class="sxs-lookup"><span data-stu-id="ace0f-135">The time window can be daily, weekly and monthly.</span></span> <span data-ttu-id="ace0f-136">すべてのタイム ウィンドウには、開始時刻と期間が必要です。</span><span class="sxs-lookup"><span data-stu-id="ace0f-136">All the time windows need a start time and a duration.</span></span>
    
   - <span data-ttu-id="ace0f-137">1 日のタイム ウィンドウでは、開始時刻と期間だけが必要です。</span><span class="sxs-lookup"><span data-stu-id="ace0f-137">For a daily time window, only start time and duration are needed.</span></span> 
    
   - <span data-ttu-id="ace0f-138">週単位のタイム ウィンドウでは、1 日または複数の日を指定できる週の日数が必要です。</span><span class="sxs-lookup"><span data-stu-id="ace0f-138">For a weekly time window, days of week are needed, which can be a single day or multiple days.</span></span>
    
   - <span data-ttu-id="ace0f-139">月次のタイム ウィンドウには、2 つの種類があります。</span><span class="sxs-lookup"><span data-stu-id="ace0f-139">For a monthly time window, there can be two types.</span></span> <span data-ttu-id="ace0f-140">最初の種類は、月の日を指定します。これは 1 日にできます。</span><span class="sxs-lookup"><span data-stu-id="ace0f-140">The first type is to specify the day of the month, which can be a single day.</span></span> <span data-ttu-id="ace0f-141">2 番目の種類は、月の週と、1 つのアイテムまたは複数のアイテムの両方を指定できる週の日数を指定します。</span><span class="sxs-lookup"><span data-stu-id="ace0f-141">The second type is to specify the weeks of the month, along with days of the week, which both can be a single item or multiple items.</span></span>
    
   - <span data-ttu-id="ace0f-142">各テナントには、20 のタイム ウィンドウを定義できます。</span><span class="sxs-lookup"><span data-stu-id="ace0f-142">Each tenant can have 20 time windows defined.</span></span> <span data-ttu-id="ace0f-143">新しいテナントの既定のタイム ウィンドウは、オペレーティング システムの更新とビット更新の既定のタイム ウィンドウとして作成されます。</span><span class="sxs-lookup"><span data-stu-id="ace0f-143">The default time window will be created for a new tenant as the default time window for operating system update and Bits update.</span></span> <span data-ttu-id="ace0f-144">次のコマンドレットを実行して、毎日、毎週、または毎月のタイム ウィンドウを設定します。</span><span class="sxs-lookup"><span data-stu-id="ace0f-144">Run the following cmdlet(s) to set the daily, weekly or monthly time window:</span></span>
    
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

   - <span data-ttu-id="ace0f-145">更新時間ウィンドウをサイトに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="ace0f-145">Assign update time windows to the site.</span></span> 
    
     <span data-ttu-id="ace0f-146">ビット更新時刻と OS 更新時刻ウィンドウは個別に構成されます。</span><span class="sxs-lookup"><span data-stu-id="ace0f-146">The Bits update time and OS update time windows are configured separately.</span></span> <span data-ttu-id="ace0f-147">両方とも、1 つのタイム ウィンドウまたは複数のタイム ウィンドウを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="ace0f-147">Both of them can be assigned single or multiple time windows.</span></span> <span data-ttu-id="ace0f-148">各タイム ウィンドウは、異なるサイトと異なる目的 (ビット更新プログラムと OS 更新プログラム) に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="ace0f-148">Each time window can be assigned to different sites and different purpose (Bits update and OS update).</span></span> <span data-ttu-id="ace0f-149">サイトのタイム ウィンドウを設定するには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="ace0f-149">Run the following cmdlet to set the time window for the site:</span></span> 
    
   ```powershell
   Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
   ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a><span data-ttu-id="ace0f-150">専用テナント管理者の資格情報を更新する</span><span class="sxs-lookup"><span data-stu-id="ace0f-150">Update the dedicated tenant admin credentials</span></span>
<span data-ttu-id="ace0f-151"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="ace0f-151"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="ace0f-152">Microsoft 365 または Office 365 組織の管理上の変更は、必要なアクセス許可を持つアカウントから行います。</span><span class="sxs-lookup"><span data-stu-id="ace0f-152">Administrative changes in the Microsoft 365 or Office 365 organization for Cloud Connector are made from an account with the needed permissions.</span></span> <span data-ttu-id="ace0f-153">2.0 より前の Cloud Connector バージョンでは、そのアカウントは専用のグローバル テナント管理者アカウントです。</span><span class="sxs-lookup"><span data-stu-id="ace0f-153">In Cloud Connector versions before 2.0, that account is a dedicated global tenant admin account.</span></span> <span data-ttu-id="ace0f-154">Cloud Connector バージョン 2.0 以降では、そのアカウントには、Skype for Business 管理者権限を持つ Microsoft 365 または Office 365 アカウントを使用できます。</span><span class="sxs-lookup"><span data-stu-id="ace0f-154">In Cloud Connector versions 2.0 and later, that account can be a Microsoft 365 or Office 365 account with Skype for Business Administrator rights.</span></span>
  
<span data-ttu-id="ace0f-155">Microsoft 365 または Office 365 で管理者アカウントの資格情報が変更された場合は、展開した各クラウド コネクタ アプライアンスで次の Administrator PowerShell コマンドを実行して、クラウド コネクタでローカルにキャッシュされた資格情報も更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ace0f-155">If your admin account credentials change in Microsoft 365 or Office 365, you also need to update the locally cached credentials in Cloud Connector by running the following Administrator PowerShell command on each Cloud Connector appliance you have deployed:</span></span>
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a><span data-ttu-id="ace0f-156">ホスト サーバーのパスワードを更新する</span><span class="sxs-lookup"><span data-stu-id="ace0f-156">Update the password for the host server</span></span>
<span data-ttu-id="ace0f-157"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="ace0f-157"><a name="BKMK_UpdatePassword"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="ace0f-158">このセクションは、Cloud Connector バージョン 2.0 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="ace0f-158">This section is applicable to Cloud Connector version 2.0 and later.</span></span> 
  
<span data-ttu-id="ace0f-159">すべてのクラウド コネクタ資格情報は、"%SystemDrive%\Programdata\Cloudconnector\credentials" というファイルに格納されます \<CurrentUser\> 。xml」</span><span class="sxs-lookup"><span data-stu-id="ace0f-159">All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="ace0f-160">ホスト サーバーのパスワードが変更された場合は、ローカルに保存されている資格情報を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ace0f-160">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
  
<span data-ttu-id="ace0f-161">クラウド コネクタ アプライアンスでローカルに保存されている資格情報を更新するには [、Get-CcCredential](get-cccredential.md) コマンドレットと [Set-CcCredential](set-cccredential.md) コマンドレットを使用し、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ace0f-161">To update the locally stored credentials on the Cloud Connector appliance, use the [Get-CcCredential](get-cccredential.md) and [Set-CcCredential](set-cccredential.md) cmdlets and follow these steps:</span></span>
  
1. <span data-ttu-id="ace0f-162">後で必要なパスワードを取得するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ace0f-162">Run the following commands to retrieve the passwords you will need later:</span></span> 
    
   - <span data-ttu-id="ace0f-163">Get-CcCredential -AccountType DomainAdmin -DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="ace0f-163">Get-CcCredential -AccountType DomainAdmin -DisplayPassword</span></span>
    
   - <span data-ttu-id="ace0f-164">Get-CcCredential -AccountType VMAdmin -DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="ace0f-164">Get-CcCredential -AccountType VMAdmin -DisplayPassword</span></span>
    
   - <span data-ttu-id="ace0f-165">Get-CcCredential -AccountType CceService -DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="ace0f-165">Get-CcCredential -AccountType CceService -DisplayPassword</span></span>
    
2. <span data-ttu-id="ace0f-166">ホスト サーバー上のアカウントのパスワードを変更します。</span><span class="sxs-lookup"><span data-stu-id="ace0f-166">Change the password of your account on the host server.</span></span>
    
3. <span data-ttu-id="ace0f-167">ホスト サーバーを再起動します。</span><span class="sxs-lookup"><span data-stu-id="ace0f-167">Restart the host server.</span></span>
    
4. <span data-ttu-id="ace0f-168">"%SystemDrive%\Programdata\Cloudconnector\credentials" というファイルを削除します \<CurrentUser\> 。xml」</span><span class="sxs-lookup"><span data-stu-id="ace0f-168">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
5. <span data-ttu-id="ace0f-169">管理者として PowerShell コンソールを起動し、"Register-CcAppliance -Local" を実行して、説明に従ってパスワードを再入力します。</span><span class="sxs-lookup"><span data-stu-id="ace0f-169">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="ace0f-170">クラウド コネクタの展開に対して、前に入力したパスワードと同じパスワードを入力してください。</span><span class="sxs-lookup"><span data-stu-id="ace0f-170">Be sure you enter the same password you entered before for the Cloud Connector deployment.</span></span>
    
<span data-ttu-id="ace0f-171">既定では、VmAdmin と DomainAdmin は CceService と同じパスワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="ace0f-171">By default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="ace0f-172">手順 1 で返される DomainAdmin、VMAdmin、および CceService のパスワードが異なる場合は、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ace0f-172">If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
  
1. <span data-ttu-id="ace0f-173">次Set-CcCredential -AccountType DomainAdmin を実行します。</span><span class="sxs-lookup"><span data-stu-id="ace0f-173">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
1. <span data-ttu-id="ace0f-174">古いアカウント資格情報の入力を求めるメッセージが表示されたら、CceService パスワードに使用した資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="ace0f-174">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="ace0f-175">新しいアカウント資格情報の入力を求めるメッセージが表示されたら、手順 1 で返される DomainAdmin パスワードのパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="ace0f-175">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
2. <span data-ttu-id="ace0f-176">次Set-CcCredential -AccountType VmAdmin を実行します。</span><span class="sxs-lookup"><span data-stu-id="ace0f-176">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
1. <span data-ttu-id="ace0f-177">古いアカウント資格情報の入力を求めるメッセージが表示されたら、CceService パスワードに使用した資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="ace0f-177">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="ace0f-178">新しいアカウント資格情報の入力を求めるメッセージが表示されたら、手順 1 で返される VmAdmin パスワードのパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="ace0f-178">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
## <a name="update-the-password-for-the-cceservice-account"></a><span data-ttu-id="ace0f-179">CceService アカウントのパスワードを更新する</span><span class="sxs-lookup"><span data-stu-id="ace0f-179">Update the password for the CceService account</span></span>
<span data-ttu-id="ace0f-180"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="ace0f-180"><a name="BKMK_UpdatePassword"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="ace0f-181">このセクションは、Cloud Connector バージョン 2.0.1 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="ace0f-181">This section is applicable to Cloud Connector version 2.0.1 and later.</span></span> 
  
<span data-ttu-id="ace0f-182">クラウド コネクタ サービスは、クラウド コネクタ管理サービスを実行します。</span><span class="sxs-lookup"><span data-stu-id="ace0f-182">The Cloud Connector service runs the Cloud Connector Management service.</span></span> <span data-ttu-id="ace0f-183">CceService アカウントは、Cloud Connector Edition の展開中に作成され、"%SystemDrive%\Programdata\Cloudconnector\credentials" に格納されます \<CurrentUser\> 。xml" と "%SystemDrive%\Programdata\Cloudconnector\credentials..CceService.xml"</span><span class="sxs-lookup"><span data-stu-id="ace0f-183">The CceService account is created during the Cloud Connector Edition deployment and stored in the following files: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" and "%SystemDrive%\Programdata\Cloudconnector\credentials..CceService.xml".</span></span>
  
<span data-ttu-id="ace0f-184">すべてのアプライアンスがサイト ディレクトリ共有にアクセスするには、サイト内に展開されているすべてのアプライアンスで CceService アカウントのパスワードが同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="ace0f-184">To ensure that all appliances can access the site directory share, the password for the CceService account must be the same on all appliances deployed within the site.</span></span> <span data-ttu-id="ace0f-185">以下の点にご注意ください。</span><span class="sxs-lookup"><span data-stu-id="ace0f-185">Keep the following in mind:</span></span>
  
- <span data-ttu-id="ace0f-186">既定では、CceService アカウントは "Password never expires" として構成されます。</span><span class="sxs-lookup"><span data-stu-id="ace0f-186">By default, the CceService account is configured as "Password never expires".</span></span> <span data-ttu-id="ace0f-187">パスワードを更新する場合は、この構成を維持してください。</span><span class="sxs-lookup"><span data-stu-id="ace0f-187">When you update the password, Microsoft recommends keeping this configuration.</span></span>
    
- <span data-ttu-id="ace0f-188">ピーク時以外の使用期間中、およびビットまたは Windows 更新プログラムの自動更新タイム ウィンドウ以外の場合は、パスワードを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ace0f-188">You should update the password during non-peak usage periods and outside of automatic update time windows for bits or Windows updates.</span></span> <span data-ttu-id="ace0f-189">パスワードを更新する場合、アプライアンスをドレインして再起動する必要があります。時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="ace0f-189">When you update the password, the appliance needs to be drained and restarted, which takes some time.</span></span> <span data-ttu-id="ace0f-190">アプライアンスを再起動すると、自動更新操作が中断されます。</span><span class="sxs-lookup"><span data-stu-id="ace0f-190">Restarting the appliance will interrupt automatic update operations.</span></span> 
    
- <span data-ttu-id="ace0f-191">CceService アカウントのパスワードを変更する場合は、すべての資格情報を指定し、ローカルに保存されたファイルで更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ace0f-191">When you change the CceService account password, you will need to specify all the credentials and update them in the locally stored file.</span></span> 
    
<span data-ttu-id="ace0f-192">同じ PSTN サイトに属するアプライアンスごとに、次の項目を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ace0f-192">For each appliance that belongs to the same PSTN site, you will need to specify the following:</span></span> 
  
1. <span data-ttu-id="ace0f-193">次のコマンドを実行して、後で使用するアカウント名とパスワードを取得します。</span><span class="sxs-lookup"><span data-stu-id="ace0f-193">Run the following commands to retrieve the account names and passwords that you will use later:</span></span>
    
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

2. <span data-ttu-id="ace0f-194">このコマンドレットEnter-CcUpdate実行して、アプライアンスをドレインし、手動メンテナンス モードに移行します。</span><span class="sxs-lookup"><span data-stu-id="ace0f-194">Run the Enter-CcUpdate cmdlet to drain the appliance and move it into manual maintenance mode.</span></span>
    
3. <span data-ttu-id="ace0f-195">ホスト サーバー上の CceService アカウントのパスワードを更新します。</span><span class="sxs-lookup"><span data-stu-id="ace0f-195">Update the password of the CceService account on the host server.</span></span>
    
4. <span data-ttu-id="ace0f-196">ホスト サーバーを再起動します。</span><span class="sxs-lookup"><span data-stu-id="ace0f-196">Restart the host server.</span></span>
    
5. <span data-ttu-id="ace0f-197">説明にRestore-CcCredentialsパスワードを再入力するには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="ace0f-197">Run the Restore-CcCredentials cmdlet to re-enter the passwords following the description.</span></span> 
    
    <span data-ttu-id="ace0f-198">CceService アカウントを除くクラウド コネクタの展開に対して、前に入力したパスワードと同じパスワードを入力してください。</span><span class="sxs-lookup"><span data-stu-id="ace0f-198">Be sure you enter the same password you entered before for the Cloud Connector deployment except for the CceService account.</span></span> <span data-ttu-id="ace0f-199">CceService アカウントに新しいパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="ace0f-199">For the CceService account, enter your new password.</span></span> <span data-ttu-id="ace0f-200">CceService アカウントの新しいパスワードが PSTN サイトのすべてのアプライアンスで同じことを確認します。</span><span class="sxs-lookup"><span data-stu-id="ace0f-200">Be sure the new password for the CceService account is the same for all appliances in the PSTN site.</span></span>
    
6. <span data-ttu-id="ace0f-201">既定では、VmAdmin と DomainAdmin は CceService と同じパスワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="ace0f-201">By default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="ace0f-202">手順 1 で返される DomainAdmin、VMAdmin、および CceService のパスワードが異なる場合は、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ace0f-202">If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
    
7. <span data-ttu-id="ace0f-203">次Set-CcCredential -AccountType DomainAdmin を実行します。</span><span class="sxs-lookup"><span data-stu-id="ace0f-203">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
   - <span data-ttu-id="ace0f-204">古いアカウント資格情報の入力を求めるメッセージが表示されたら、CceService パスワードに使用した資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="ace0f-204">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
   - <span data-ttu-id="ace0f-205">新しいアカウント資格情報の入力を求めるメッセージが表示されたら、手順 1 で返される DomainAdmin パスワードのパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="ace0f-205">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
8. <span data-ttu-id="ace0f-206">次Set-CcCredential -AccountType VmAdmin を実行します。</span><span class="sxs-lookup"><span data-stu-id="ace0f-206">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
   - <span data-ttu-id="ace0f-207">古いアカウント資格情報の入力を求めるメッセージが表示されたら、CceService パスワードに使用した資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="ace0f-207">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
   - <span data-ttu-id="ace0f-208">新しいアカウント資格情報の入力を求めるメッセージが表示されたら、手順 1 で返される VmAdmin パスワードのパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="ace0f-208">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
9. <span data-ttu-id="ace0f-209">手動メンテナンス Exit-CcUpdateからアプライアンスを移動するには、このコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="ace0f-209">Run the Exit-CcUpdate cmdlet to move the appliance out of manual maintenance mode.</span></span>
    
10. <span data-ttu-id="ace0f-210">同じ PSTN サイト内のすべてのアプライアンスでこれらの手順を完了したら、サイト ルート ディレクトリ内の次のファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="ace0f-210">After you complete these steps on all appliances in the same PSTN site, delete the following files in the site root directory:</span></span>
    
    - <span data-ttu-id="ace0f-211">CcLockFile</span><span class="sxs-lookup"><span data-stu-id="ace0f-211">CcLockFile</span></span>
    
    - <span data-ttu-id="ace0f-212">Site_\<Edge External Sip Pool fqdn\></span><span class="sxs-lookup"><span data-stu-id="ace0f-212">Site_\<Edge External Sip Pool fqdn\></span></span>
    
    - <span data-ttu-id="ace0f-213">Tenant_\<Edge External Sip Pool fqdn\></span><span class="sxs-lookup"><span data-stu-id="ace0f-213">Tenant_\<Edge External Sip Pool fqdn\></span></span>
    
    - <span data-ttu-id="ace0f-214">TenantConfigLock_\<Edge External Sip Pool fqdn\></span><span class="sxs-lookup"><span data-stu-id="ace0f-214">TenantConfigLock_\<Edge External Sip Pool fqdn\></span></span>
    
## <a name="add-a-new-sip-domain"></a><span data-ttu-id="ace0f-215">新しい SIP ドメインを追加する</span><span class="sxs-lookup"><span data-stu-id="ace0f-215">Add a new SIP domain</span></span>
<span data-ttu-id="ace0f-216"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="ace0f-216"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="ace0f-217">既存のクラウド コネクタ展開に新しい SIP ドメイン (または複数の SIP ドメイン) を追加するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ace0f-217">To add a new SIP domain (or multiple SIP domains) to your existing Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="ace0f-218">Microsoft 365 または Office 365 でドメインを更新する手順が完了し、DNS レコードを追加する機能を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ace0f-218">Make sure you've completed the steps to update your domain in Microsoft 365 or Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="ace0f-219">Microsoft 365 または Office 365 でドメインをセットアップする方法の詳細については [、「Add a domain to Microsoft 365 or Office 365」を参照](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)してください。</span><span class="sxs-lookup"><span data-stu-id="ace0f-219">For more information about how to set up your domain in Microsoft 365 or Office 365, see [Add a domain to Microsoft 365 or Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="ace0f-220">クラウド コネクタ構成ファイルを新しい SIP ドメインまたはドメインで更新します。</span><span class="sxs-lookup"><span data-stu-id="ace0f-220">Update the Cloud Connector configuration file with the new SIP domain or domains.</span></span>
    
3. <span data-ttu-id="ace0f-221">クラウド コネクタ構成で定義されている SIP ドメインごとに sip.domain 用に追加の SAN 名を持つ新しいエッジ外部証明書を要求します。</span><span class="sxs-lookup"><span data-stu-id="ace0f-221">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="ace0f-222">新しいエッジ外部証明書のパスを次のように設定します。</span><span class="sxs-lookup"><span data-stu-id="ace0f-222">Set the path for the new Edge external certificate as follows:</span></span>
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    <span data-ttu-id="ace0f-223">「1 つのサイトの [構成を変更](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) する」または「複数のサイトの構成 [を変更する」の指示に従います](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites)。</span><span class="sxs-lookup"><span data-stu-id="ace0f-223">Follow the instructions to [Modify the configuration of a single site](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) or [Modify the configuration of multiple sites](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites).</span></span>
    
## <a name="modify-the-primary-sip-domain"></a><span data-ttu-id="ace0f-224">プライマリ SIP ドメインの変更</span><span class="sxs-lookup"><span data-stu-id="ace0f-224">Modify the primary SIP domain</span></span>
<span data-ttu-id="ace0f-225"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="ace0f-225"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="ace0f-226">クラウド コネクタ展開でプライマリ SIP ドメインを変更する必要がある場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ace0f-226">If you need to change the primary SIP domain in your Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="ace0f-227">Microsoft 365 または Office 365 でドメインを更新する手順が完了し、DNS レコードを追加する機能を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ace0f-227">Make sure you've completed the steps to update your domain in Microsoft 365 or Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="ace0f-228">Microsoft 365 または Office 365 でドメインをセットアップする方法の詳細については [、「Add a domain to Microsoft 365 or Office 365」を参照](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)してください。</span><span class="sxs-lookup"><span data-stu-id="ace0f-228">For more information about how to set up your domain in Microsoft 365 or Office 365, see [Add a domain to Microsoft 365 or Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="ace0f-229">新しい SIP ドメインでクラウド コネクタ構成ファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="ace0f-229">Update the Cloud Connector configuration file with the new SIP domain.</span></span>
    
3. <span data-ttu-id="ace0f-230">クラウド コネクタ構成で定義されている SIP ドメインごとに sip.domain 用に追加の SAN 名を持つ新しいエッジ外部証明書を要求します。</span><span class="sxs-lookup"><span data-stu-id="ace0f-230">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="ace0f-231">新しいエッジ外部証明書のパスを次のように設定します。</span><span class="sxs-lookup"><span data-stu-id="ace0f-231">Set the path for the new Edge external certificate as follows:</span></span>
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    <span data-ttu-id="ace0f-232">管理者 PowerShell on Cloud Connector で次のコマンドレットを実行して、サイト内の各アプライアンスのテナント登録を削除します。</span><span class="sxs-lookup"><span data-stu-id="ace0f-232">Remove the tenant registration for each appliance in a site by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

6. 
    
    <span data-ttu-id="ace0f-233">Skype for Business Online PowerShell で次のコマンドレットを実行して、各サイトのサイト登録を削除します。</span><span class="sxs-lookup"><span data-stu-id="ace0f-233">Remove the site registration for each site by running the following cmdlet in Skype for Business Online PowerShell:</span></span>
    
   ```powershell
   Remove-CsHybridPSTNSite
   ```

7. 
    
    <span data-ttu-id="ace0f-234">クラウド コネクタの管理者 PowerShell で次のコマンドレットを実行して、各アプライアンスをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="ace0f-234">Uninstall each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Uninstall-CcAppliance
   ```

8. 
    
     <span data-ttu-id="ace0f-235">クラウド コネクタの管理者 PowerShell で次のコマンドレットを実行して、各アプライアンスを登録します。</span><span class="sxs-lookup"><span data-stu-id="ace0f-235">Register each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Register-ccAppliance
   ```

9. 
    
     <span data-ttu-id="ace0f-236">クラウド コネクタの管理者 PowerShell で次のコマンドレットを実行して、各アプライアンスを 1 つ 1 つインストールします。</span><span class="sxs-lookup"><span data-stu-id="ace0f-236">Install each appliance, one by one, by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a><span data-ttu-id="ace0f-237">外部エッジ証明書を新しい証明書に置き換える</span><span class="sxs-lookup"><span data-stu-id="ace0f-237">Replace the external Edge certificate with a new certificate</span></span>
<span data-ttu-id="ace0f-238"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="ace0f-238"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="ace0f-239">クラウド コネクタ アプライアンスの外部エッジ証明書を置き換える必要がある場合は、新しいエッジ証明書を取得し、プライベート キーと完全な証明書チェーンを含む PFX ファイルを準備し、各アプライアンスで次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="ace0f-239">When you need to replace the external Edge certificate on your Cloud Connector appliances, you will need to obtain a new Edge certificate, prepare the PFX file containing the Private Key and full certificate chain, and then do the following on each appliance:</span></span>
  
1. <span data-ttu-id="ace0f-240">このコマンドレットを使用して、アプライアンスをメンテナンス モードEnter-CcUpdateします。</span><span class="sxs-lookup"><span data-stu-id="ace0f-240">Put the appliance in maintenance mode by using the Enter-CcUpdate cmdlet.</span></span>
    
2. <span data-ttu-id="ace0f-241">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ace0f-241">Run the following command:</span></span> 
    
   ```powershell
   Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
   ```

3. 
    
    <span data-ttu-id="ace0f-242">新しい証明書のパスワードが古い証明書と同じ場合、インポートは成功します。</span><span class="sxs-lookup"><span data-stu-id="ace0f-242">If the password of the new certificate is the same as the old, the import will be successful.</span></span> <span data-ttu-id="ace0f-243">パスワードが異なる場合は、パスワードが間違っているというエラーが表示され、Register-CcAppliance コマンドレットを -Local パラメーターで実行し、手順 2 を繰り返してパスワードをリセットする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ace0f-243">If the password is different, you will receive an error that the password is wrong, and you will need to reset the password by running the Register-CcAppliance cmdlet with the -Local parameter, and then repeating step 2.</span></span> 
    
4. <span data-ttu-id="ace0f-244">Exit -CcUpdate コマンドレットを使用して、アプライアンスをメンテナンス モードから外します。</span><span class="sxs-lookup"><span data-stu-id="ace0f-244">Take the appliance out of maintenance mode by using the Exit -CcUpdate cmdlet.</span></span>
