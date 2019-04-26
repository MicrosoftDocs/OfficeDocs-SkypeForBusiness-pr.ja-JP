---
title: 既存の Cloud Connector の展開構成の変更
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 90490c65-0e40-4e85-96e1-751f27897e25
description: ビジネス クラウド コネクタ エディション 1.4.1 またはそれ以降の展開は、既存の Skype の構成を変更するには、このトピックの手順を実行します。
ms.openlocfilehash: abe7d9be6ec0ae48ff8cbac09475c6a41bf2a49f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32237610"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a><span data-ttu-id="e9772-103">Modify the configuration of an existing Cloud Connector deployment</span><span class="sxs-lookup"><span data-stu-id="e9772-103">Modify the configuration of an existing Cloud Connector deployment</span></span>
 
<span data-ttu-id="e9772-104">ビジネス クラウド コネクタ エディション 1.4.1 またはそれ以降の展開は、既存の Skype の構成を変更するには、このトピックの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e9772-104">Follow the steps in this topic to modify the configuration of an existing Skype for Business Cloud Connector Edition 1.4.1 or later deployment.</span></span> 
  
## <a name="modify-the-configuration-of-a-single-site"></a><span data-ttu-id="e9772-105">1 つのサイトの構成を変更する</span><span class="sxs-lookup"><span data-stu-id="e9772-105">Modify the configuration of a single site</span></span>
<span data-ttu-id="e9772-106"><a name="BKMK_SIngleSite"> </a></span><span class="sxs-lookup"><span data-stu-id="e9772-106"></span></span>

<span data-ttu-id="e9772-107">サイトに 1 つのアプライアンスしかなく、アプライアンスを展開した後で構成設定を変更する必要がある場合は、CloudConnector.ini ファイルを変更して、もう一度展開を開始することができます。</span><span class="sxs-lookup"><span data-stu-id="e9772-107">If there is only one appliance in the site, when you want to change the configuration settings after the appliance is deployed, you can modify the CloudConnector.ini file and start the deployment again.</span></span>
  
1. <span data-ttu-id="e9772-108">次のコマンドレットを実行して、ホスト サーバー上にあるすべての既存の仮想マシンをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="e9772-108">Run the following cmdlet to uninstall all existing virtual machines on the host server:</span></span> 
    
   ```
   Uninstall-CcAppliance
   ```

2. <span data-ttu-id="e9772-109">アプライアンスを登録解除するには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="e9772-109">Run the following cmdlet to unregister the appliance:</span></span>
    
   ```
   Unregister-CcAppliance
   ```

3. <span data-ttu-id="e9772-110">アプライアンス ディレクトリ の CloudConnector.ini ファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="e9772-110">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="e9772-111">構成を更新するのには次のコマンドレットを実行する: (この手順は、バージョン 2; 以前のバージョンに該当する場合のみ、次の手順に進みます)。</span><span class="sxs-lookup"><span data-stu-id="e9772-111">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
   ```
   Import-CcConfiguration 
   ```

5. <span data-ttu-id="e9772-112">アプライアンスをもう一度登録するには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="e9772-112">Run the following cmdlet to register the appliance again:</span></span>
    
   ```
   Register-CcAppliance
   ```

6. <span data-ttu-id="e9772-113">Skype for Business Cloud Connector エディションをインストールするには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="e9772-113">Run the following cmdlet to install Skype for Business Cloud Connector Edition:</span></span>
    
   ```
   Install-CcAppliance
   ```

<span data-ttu-id="e9772-114">サイトに複数のアプライアンスがある場合は、次の手順に従って、CloudConnector.ini ファイルを変更し、アプライアンスを 1 つずつ再展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9772-114">If there is more than one appliance in the site, you'll need to follow these steps, modify the CloudConnector.ini file, and redeploy the appliances one by one.</span></span>
  
1. <span data-ttu-id="e9772-115">現在のアプライアンス上にある既存の仮想マシンをすべてアンインストールするには、次のコマンドレットを実行します。 </span><span class="sxs-lookup"><span data-stu-id="e9772-115">Run the following cmdlet to uninstall all existing virtual machines on the current appliance:</span></span> 
    
   ```
   Uninstall-CcAppliance
   ```

2. <span data-ttu-id="e9772-116">アプライアンスを登録解除するには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="e9772-116">Run the following cmdlet to unregister the appliance:</span></span>
    
   ```
   Unregister-CcAppliance
   ```

3. <span data-ttu-id="e9772-117">アプライアンス ディレクトリ の CloudConnector.ini ファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="e9772-117">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="e9772-118">構成を更新するのには次のコマンドレットを実行する: (この手順は、バージョン 2; 以前のバージョンに該当する場合のみ、次の手順に進みます)。</span><span class="sxs-lookup"><span data-stu-id="e9772-118">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
   ```
   Import-CcConfiguration 
   ```

5. <span data-ttu-id="e9772-119">アプライアンスをもう一度登録するには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="e9772-119">Run the following cmdlet to register the appliance again:</span></span>
    
   ```
   Register-CcAppliance
   ```

6. <span data-ttu-id="e9772-120">最新の構成を取得するには、サイトにあるその他すべてのアプライアンスで次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="e9772-120">Run the following cmdlet on all other appliances in the site to pick up the latest configuration:</span></span>
    
   ```
   Publish-CcAppliance
   ```

7. <span data-ttu-id="e9772-121">現在のアプライアンスのクラウドのコネクタを再配置するのには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="e9772-121">Run the following cmdlet to redeploy Cloud Connector on the current appliance:</span></span>
    
   ```
   Install-CcAppliance
   ```

## <a name="modify-the-configuration-of-multiple-sites"></a><span data-ttu-id="e9772-122">複数のサイトの構成を変更する</span><span class="sxs-lookup"><span data-stu-id="e9772-122">Modify the configuration of multiple sites</span></span>
<span data-ttu-id="e9772-123"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="e9772-123"></span></span>

<span data-ttu-id="e9772-124">展開で複数のサイトの構成を変更するには、一度に 1 つのサイトを更新、1 つのサイトの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e9772-124">To modify the configuration for multiple sites in a deployment, follow the steps for a single site, updating one site at a time.</span></span>
  
## <a name="modify-the-configuration-of-your-office-365-tenant-to-enable-automatic-updates"></a><span data-ttu-id="e9772-125">自動更新を有効にするために Office 365 テナントの構成を変更する</span><span class="sxs-lookup"><span data-stu-id="e9772-125">Modify the configuration of your Office 365 tenant to enable automatic updates</span></span>
<span data-ttu-id="e9772-126"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="e9772-126"></span></span>

<span data-ttu-id="e9772-127">オペレーティング システムの自動更新と Bits の自動更新を有効にするには、オンライン管理のためのビジネス テナント管理者のアカウントに、Skype を使用する必要があります、リモート PowerShell のテナントを次のように使用します。</span><span class="sxs-lookup"><span data-stu-id="e9772-127">To enable operating system automatic updates and Bits automatic updates, you must use the Skype for Business tenant admin account for online management and use tenant remote PowerShell as follows.</span></span>
  
<span data-ttu-id="e9772-128">オペレーティング システムの自動更新または自動更新のビットを無効にした場合、ホストと仮想マシンは、重要な Windows 更新を見落とす場合があり、クラウドのコネクタは自動的に新しいバージョンにアップグレードされません。</span><span class="sxs-lookup"><span data-stu-id="e9772-128">If you disabled operating system automatic updates or Bits automatic updates, your host and virtual machine may miss important Windows updates, and Cloud Connector will not upgrade to the new version automatically.</span></span> <span data-ttu-id="e9772-129">自動更新を有効にすることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e9772-129">It is highly recommended that you enable automatic updates.</span></span>
  
1. <span data-ttu-id="e9772-130">サイトの EnableAutoUpdate プロパティは、true (既定値) に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9772-130">The EnableAutoUpdate property of the site needs to be set to true (the default value).</span></span> <span data-ttu-id="e9772-131">EnableAutoUpdate が True に設定されていることを確認するには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="e9772-131">Run the following cmdlet to make sure EnableAutoUpdate is set to true:</span></span>
    
   ```
   Get-CsHybridPSTNSite -Identity <SiteName>
   ```

2. <span data-ttu-id="e9772-132">テナントの自動更新の時間枠を作成します。</span><span class="sxs-lookup"><span data-stu-id="e9772-132">Create auto update time window for the tenant.</span></span>
    
    <span data-ttu-id="e9772-p103">時間枠は、日単位、週単位、月単位で設定できます。すべての時間枠には、開始時刻と期間が必要です。</span><span class="sxs-lookup"><span data-stu-id="e9772-p103">The time window can be daily, weekly and monthly. All the time windows need a start time and a duration.</span></span>
    
   - <span data-ttu-id="e9772-135">日単位の時間枠の場合は、開始時刻と期間のみが必要です。</span><span class="sxs-lookup"><span data-stu-id="e9772-135">For a daily time window, only start time and duration are needed.</span></span> 
    
   - <span data-ttu-id="e9772-136">週単位の時間枠の場合は、1 つまたは複数の曜日が必要です。</span><span class="sxs-lookup"><span data-stu-id="e9772-136">For a weekly time window, days of week are needed, which can be a single day or multiple days.</span></span>
    
   - <span data-ttu-id="e9772-p104">月単位の時間枠の場合は、2 種類あります。1 番目の種類では、日付を 1 つ指定します。2 番目の方法では、第何週の何曜日かを (それぞれ 1 つでも複数でも可) 指定します。</span><span class="sxs-lookup"><span data-stu-id="e9772-p104">For a monthly time window, there can be two types. The first type is to specify the day of the month, which can be a single day. The second type is to specify the weeks of the month, along with days of the week, which both can be a single item or multiple items.</span></span>
    
   - <span data-ttu-id="e9772-p105">各テナントに定義できる時間枠は 20 件です。新しいテナントには、オペレーティング システムの更新と BITS の更新用の既定の時間枠が作成されます。日単位、週単位、月単位の時間枠を設定するには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="e9772-p105">Each tenant can have 20 time windows defined. The default time window will be created for a new tenant as the default time window for operating system update and Bits update. Run the following cmdlet(s) to set the daily, weekly or monthly time window:</span></span>
    
   ```
   New-CsTenantUpdateTimeWindow -Identity Night -Daily -StartTime 22:00 -Duration 6:00
   ```

   ```
   New-CsTenantUpdateTimeWindow -Identity WeekdayNight -Weekly -DaysOfWeek Monday,Tuesday,Wednesday,Thursday,Friday -StartTime 22:00 -Duration 4:00
   ```

   ```
   New-CsTenantUpdateTimeWindow -Identity FirstAndLastWeekend -Monthly -WeeksOfMonth First,Last -DaysOfWeek Sunday,Saturday -StartTime 0:00 -Duration 10:00
   ```

   ```
   New-CsTenantUpdateTimeWindow -Identity MidDayOfMonth -Monthly -DayOfMonth 15 -StartTime 0:00 -Duration 1.00:00
   ```

   - <span data-ttu-id="e9772-143">更新時間枠をサイトに割り当てます。 </span><span class="sxs-lookup"><span data-stu-id="e9772-143">Assign update time windows to the site.</span></span> 
    
     <span data-ttu-id="e9772-p106">BITS の更新時間枠と OS の更新時間枠は、個別に構成します。 どちらにも、1 つまたは複数の時間枠を割り当てることができます。 各時間枠は、異なるサイトや異なる用途 (BITS の更新と OS の更新) に割り当てることができます。 次のコマンドレットを実行して時間枠をサイトに設定します。 </span><span class="sxs-lookup"><span data-stu-id="e9772-p106">The Bits update time and OS update time windows are configured separately. Both of them can be assigned single or multiple time windows. Each time window can be assigned to different sites and different purpose (Bits update and OS update). Run the following cmdlet to set the time window for the site:</span></span> 
    
   ```
   Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
   ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a><span data-ttu-id="e9772-148">専用のテナント管理者の資格情報を更新する</span><span class="sxs-lookup"><span data-stu-id="e9772-148">Update the dedicated tenant admin credentials</span></span>
<span data-ttu-id="e9772-149"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="e9772-149"></span></span>

<span data-ttu-id="e9772-150">クラウド コネクタの Office 365 テナントの管理の変更は、必要なアクセス許可を持つアカウントで行われます。</span><span class="sxs-lookup"><span data-stu-id="e9772-150">Administrative changes in the Office 365 tenant for Cloud Connector are made from an account with the needed permissions.</span></span> <span data-ttu-id="e9772-151">クラウド コネクタ 2.0 より前のに、バージョンでは、そのアカウントが専用のグローバル テナント管理者のアカウントです。</span><span class="sxs-lookup"><span data-stu-id="e9772-151">In Cloud Connector versions before 2.0, that account is a dedicated global tenant admin account.</span></span> <span data-ttu-id="e9772-152">クラウド コネクタ バージョン 2.0 以降では、そのアカウントにビジネス管理者の権利を Skype での Office 365 アカウントことができます。</span><span class="sxs-lookup"><span data-stu-id="e9772-152">In Cloud Connector versions 2.0 and later, that account can be an Office 365 account with Skype for Business Administrator rights.</span></span>
  
<span data-ttu-id="e9772-153">Office 365 の管理者アカウントの資格情報を変更する場合は、展開している各コネクタのクラウド アプライアンスの次の管理者の PowerShell コマンドを実行して、クラウドのコネクタのローカルにキャッシュされた資格情報を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9772-153">If your admin account credentials change in Office 365, you also need to update the locally cached credentials in Cloud Connector by running the following Administrator PowerShell command on each Cloud Connector appliance you have deployed:</span></span>
  
```
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a><span data-ttu-id="e9772-154">ホスト サーバーのパスワードを更新する</span><span class="sxs-lookup"><span data-stu-id="e9772-154">Update the password for the host server</span></span>
<span data-ttu-id="e9772-155"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="e9772-155"></span></span>

> [!NOTE]
> <span data-ttu-id="e9772-156">このセクションは Cloud Connector バージョン 2.0 以降のみを対象としています。</span><span class="sxs-lookup"><span data-stu-id="e9772-156">This section is applicable to Cloud Connector version 2.0 and later.</span></span> 
  
<span data-ttu-id="e9772-157">クラウド コネクタのすべての資格情報は、次のファイルに格納されます:"%systemdrive%\programdata\cloudconnector\credentials。\<CurrentUser\>.xml」です。</span><span class="sxs-lookup"><span data-stu-id="e9772-157">All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="e9772-158">ホスト サーバーのパスワードを変更するときには、ローカルで格納されている資格情報を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9772-158">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
  
<span data-ttu-id="e9772-159">クラウド コネクタ ・ アプライアンスのローカルに保存された資格情報を更新するには、 [Get CcCredential](get-cccredential.md)と[セット CcCredential](set-cccredential.md)コマンドレットを使用して、これらの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="e9772-159">To update the locally stored credentials on the Cloud Connector appliance, use the [Get-CcCredential](get-cccredential.md) and [Set-CcCredential](set-cccredential.md) cmdlets and follow these steps:</span></span>
  
1. <span data-ttu-id="e9772-160">次のコマンドを実行して、後で必要になるパスワードを取得します。</span><span class="sxs-lookup"><span data-stu-id="e9772-160">Run the following commands to retrieve the passwords you will need later:</span></span> 
    
   - <span data-ttu-id="e9772-161">Get-CcCredential -AccountType DomainAdmin -DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="e9772-161">Get-CcCredential -AccountType DomainAdmin -DisplayPassword</span></span>
    
   - <span data-ttu-id="e9772-162">Get-CcCredential -AccountType VMAdmin -DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="e9772-162">Get-CcCredential -AccountType VMAdmin -DisplayPassword</span></span>
    
   - <span data-ttu-id="e9772-163">Get-CcCredential -AccountType CceService -DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="e9772-163">Get-CcCredential -AccountType CceService -DisplayPassword</span></span>
    
2. <span data-ttu-id="e9772-164">ホスト サーバー上でお使いのアカウントのパスワードを変更します。</span><span class="sxs-lookup"><span data-stu-id="e9772-164">Change the password of your account on the host server.</span></span>
    
3. <span data-ttu-id="e9772-165">ホスト サーバーを再起動します。</span><span class="sxs-lookup"><span data-stu-id="e9772-165">Restart the host server.</span></span>
    
4. <span data-ttu-id="e9772-166">次のファイルを削除します。"% SystemDrive%\Programdata\Cloudconnector\credentials。\<CurrentUser\>.xml」です。</span><span class="sxs-lookup"><span data-stu-id="e9772-166">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
5. <span data-ttu-id="e9772-167">管理者として PowerShell コンソールを起動し、実行して"登録 CcAppliance-ローカル"次の説明、パスワードを再入力します。</span><span class="sxs-lookup"><span data-stu-id="e9772-167">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="e9772-168">Cloud Connector の展開で前回使用したパスワードと同じパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="e9772-168">Be sure you enter the same password you entered before for the Cloud Connector deployment.</span></span>
    
<span data-ttu-id="e9772-p110">既定では、VmAdmin および DomainAdmin では CceService と同じパスワードが使用されます。手順 1 で返された DomainAdmin、VMAdmin および CceService のパスワードが異なる場合は、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9772-p110">By default, VmAdmin and DomainAdmin use the same password as CceService. If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
  
1. <span data-ttu-id="e9772-171">Set-CcCredential -AccountType DomainAdmin を次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="e9772-171">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
1. <span data-ttu-id="e9772-172">以前のアカウントの資格情報を求められた場合は、CceService パスワードに使用した資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="e9772-172">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="e9772-173">新しいアカウントの資格情報を求められた場合は、手順 1 で返された DomainAdmin パスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="e9772-173">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
2. <span data-ttu-id="e9772-174">Set-CcCredential -AccountType VmAdmin を次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="e9772-174">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
1. <span data-ttu-id="e9772-175">以前のアカウントの資格情報を求められた場合は、CceService パスワードに使用した資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="e9772-175">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="e9772-176">新しいアカウントの資格情報を求められた場合は、手順 1 で返された VmAdmin パスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="e9772-176">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
## <a name="update-the-password-for-the-cceservice-account"></a><span data-ttu-id="e9772-177">CceService アカウントのパスワードを更新します。</span><span class="sxs-lookup"><span data-stu-id="e9772-177">Update the password for the CceService account</span></span>
<span data-ttu-id="e9772-178"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="e9772-178"></span></span>

> [!NOTE]
> <span data-ttu-id="e9772-179">クラウド コネクタ バージョン 2.0.1 に該当する場合、後でこのセクションでは。</span><span class="sxs-lookup"><span data-stu-id="e9772-179">This section is applicable to Cloud Connector version 2.0.1 and later.</span></span> 
  
<span data-ttu-id="e9772-180">クラウド コネクタ サービスは、クラウドのコネクタの管理サービスを実行します。</span><span class="sxs-lookup"><span data-stu-id="e9772-180">The Cloud Connector service runs the Cloud Connector Management service.</span></span> <span data-ttu-id="e9772-181">CceService アカウントがクラウド コネクタのエディションの展開中に作成され、次のファイルに格納されている:"%systemdrive%\programdata\cloudconnector\credentials。\<CurrentUser\>.xml"および"%systemdrive%\programdata\cloudconnector\credentials.CceService.xml"です。</span><span class="sxs-lookup"><span data-stu-id="e9772-181">The CceService account is created during the Cloud Connector Edition deployment and stored in the following files: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" and "%SystemDrive%\Programdata\Cloudconnector\credentials..CceService.xml".</span></span>
  
<span data-ttu-id="e9772-182">サイト ディレクトリの共有のすべてのアプライアンスにアクセスできることを確認するは、CceService のアカウントのパスワードはサイト内に展開されるすべてのアプライアンス上で同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9772-182">To ensure that all appliances can access the site directory share, the password for the CceService account must be the same on all appliances deployed within the site.</span></span> <span data-ttu-id="e9772-183">以下の点について留意してください。</span><span class="sxs-lookup"><span data-stu-id="e9772-183">Keep the following in mind:</span></span>
  
- <span data-ttu-id="e9772-184">既定では、[パスワードを無期限にする"と CceService のアカウントが構成されています。</span><span class="sxs-lookup"><span data-stu-id="e9772-184">By default, the CceService account is configured as "Password never expires".</span></span> <span data-ttu-id="e9772-185">パスワードを更新するときは、この構成を保持することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e9772-185">When you update the password, Microsoft recommends keeping this configuration.</span></span>
    
- <span data-ttu-id="e9772-186">非ピーク時間帯に、ビットまたは Windows の更新プログラムの自動更新の時間帯以外では、パスワードを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9772-186">You should update the password during non-peak usage periods and outside of automatic update time windows for bits or Windows updates.</span></span> <span data-ttu-id="e9772-187">パスワードを更新すると、アプライアンス必要がありますを放電し、再起動すると、時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="e9772-187">When you update the password, the appliance needs to be drained and restarted, which takes some time.</span></span> <span data-ttu-id="e9772-188">アプライアンスを再起動すると、自動更新の操作が中断されます。</span><span class="sxs-lookup"><span data-stu-id="e9772-188">Restarting the appliance will interrupt automatic update operations.</span></span> 
    
- <span data-ttu-id="e9772-189">CceService アカウントのパスワードを変更すると、すべての資格情報を指定し、ローカルに保存されたファイルに更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9772-189">When you change the CceService account password, you will need to specify all the credentials and update them in the locally stored file.</span></span> 
    
<span data-ttu-id="e9772-190">同じ PSTN のサイトに属しているアプライアンスそれぞれに対して、次の指定が必要になります。</span><span class="sxs-lookup"><span data-stu-id="e9772-190">For each appliance that belongs to the same PSTN site, you will need to specify the following:</span></span> 
  
1. <span data-ttu-id="e9772-191">後で使用するパスワードとアカウント名を取得するために次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e9772-191">Run the following commands to retrieve the account names and passwords that you will use later:</span></span>
    
   ```
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

2. <span data-ttu-id="e9772-192">アプライアンスを放電し、手動でのメンテナンス モードに移動する Enter CcUpdate コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="e9772-192">Run the Enter-CcUpdate cmdlet to drain the appliance and move it into manual maintenance mode.</span></span>
    
3. <span data-ttu-id="e9772-193">ホスト サーバー上の CceService のアカウントのパスワードを更新します。</span><span class="sxs-lookup"><span data-stu-id="e9772-193">Update the password of the CceService account on the host server.</span></span>
    
4. <span data-ttu-id="e9772-194">ホスト サーバーを再起動します。</span><span class="sxs-lookup"><span data-stu-id="e9772-194">Restart the host server.</span></span>
    
5. <span data-ttu-id="e9772-195">次の説明、パスワードを再入力するのには復元 CcCredentials コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="e9772-195">Run the Restore-CcCredentials cmdlet to re-enter the passwords following the description.</span></span> 
    
    <span data-ttu-id="e9772-196">CceService アカウントを除くクラウド コネクタの配置の前に入力したパスワードを入力することを確認します。</span><span class="sxs-lookup"><span data-stu-id="e9772-196">Be sure you enter the same password you entered before for the Cloud Connector deployment except for the CceService account.</span></span> <span data-ttu-id="e9772-197">CceService ・ アカウントの新しいパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="e9772-197">For the CceService account, enter your new password.</span></span> <span data-ttu-id="e9772-198">CceService アカウントの新しいパスワードは、PSTN のサイト内のすべてのアプライアンスで同じことを確認します。</span><span class="sxs-lookup"><span data-stu-id="e9772-198">Be sure the new password for the CceService account is the same for all appliances in the PSTN site.</span></span>
    
6. <span data-ttu-id="e9772-p116">既定では、VmAdmin および DomainAdmin では CceService と同じパスワードが使用されます。手順 1 で返された DomainAdmin、VMAdmin および CceService のパスワードが異なる場合は、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9772-p116">By default, VmAdmin and DomainAdmin use the same password as CceService. If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
    
7. <span data-ttu-id="e9772-201">Set-CcCredential -AccountType DomainAdmin を次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="e9772-201">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
   - <span data-ttu-id="e9772-202">以前のアカウントの資格情報を求められた場合は、CceService パスワードに使用した資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="e9772-202">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
   - <span data-ttu-id="e9772-203">新しいアカウントの資格情報を求められた場合は、手順 1 で返された DomainAdmin パスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="e9772-203">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
8. <span data-ttu-id="e9772-204">Set-CcCredential -AccountType VmAdmin を次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="e9772-204">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
   - <span data-ttu-id="e9772-205">以前のアカウントの資格情報を求められた場合は、CceService パスワードに使用した資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="e9772-205">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
   - <span data-ttu-id="e9772-206">新しいアカウントの資格情報を求められた場合は、手順 1 で返された VmAdmin パスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="e9772-206">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
9. <span data-ttu-id="e9772-207">移動手動メンテナンス モードを終了する終了 CcUpdate コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="e9772-207">Run the Exit-CcUpdate cmdlet to move the appliance out of manual maintenance mode.</span></span>
    
10. <span data-ttu-id="e9772-208">同じ PSTN サイト内のすべてのアプライアンス上の次の手順を完了すると後、は、サイトのルート ディレクトリ以下のファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="e9772-208">After you complete these steps on all appliances in the same PSTN site, delete the following files in the site root directory:</span></span>
    
    - <span data-ttu-id="e9772-209">CcLockFile</span><span class="sxs-lookup"><span data-stu-id="e9772-209">CcLockFile</span></span>
    
    - <span data-ttu-id="e9772-210">Site_\<エッジ外部 Sip プールの fqdn\></span><span class="sxs-lookup"><span data-stu-id="e9772-210">Site_\<Edge External Sip Pool fqdn\></span></span>
    
    - <span data-ttu-id="e9772-211">Tenant_\<エッジ外部 Sip プールの fqdn\></span><span class="sxs-lookup"><span data-stu-id="e9772-211">Tenant_\<Edge External Sip Pool fqdn\></span></span>
    
    - <span data-ttu-id="e9772-212">TenantConfigLock_\<エッジ外部 Sip プールの fqdn\></span><span class="sxs-lookup"><span data-stu-id="e9772-212">TenantConfigLock_\<Edge External Sip Pool fqdn\></span></span>
    
## <a name="add-a-new-sip-domain"></a><span data-ttu-id="e9772-213">新しい SIP ドメインを追加する </span><span class="sxs-lookup"><span data-stu-id="e9772-213">Add a new SIP domain</span></span>
<span data-ttu-id="e9772-214"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="e9772-214"></span></span>

<span data-ttu-id="e9772-215">新しい SIP ドメイン (または複数の SIP ドメイン) を既存のクラウドのコネクタの配置に追加するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e9772-215">To add a new SIP domain (or multiple SIP domains) to your existing Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="e9772-216">Office 365 でドメインを更新する手順を完了し、DNS レコードを追加できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e9772-216">Make sure you've completed the steps to update your domain in Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="e9772-217">Office 365 でドメインを設定する方法の詳細については、 [Office 365 にドメインの追加](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9772-217">For more information about how to set up your domain in Office 365, see [Add a domain to Office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="e9772-218">新しい SIP ドメイン、またはドメインを持つクラウド コネクタ構成ファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="e9772-218">Update the Cloud Connector configuration file with the new SIP domain or domains.</span></span>
    
3. <span data-ttu-id="e9772-219">新しいエッジ外部証明書を要求、クラウドのコネクタ構成で定義されている各 SIP ドメインの sip.domain の他の SAN 名。</span><span class="sxs-lookup"><span data-stu-id="e9772-219">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="e9772-220">新しい Microsoft Edge 外部証明書のパスを次のように設定します。</span><span class="sxs-lookup"><span data-stu-id="e9772-220">Set the path for the new Edge external certificate as follows:</span></span>
    
   ```
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    <span data-ttu-id="e9772-221">「[1 つのサイトの構成を変更する](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite)」または「[複数のサイトの構成を変更する](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites)」の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e9772-221">Follow the instructions to [Modify the configuration of a single site](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) or [Modify the configuration of multiple sites](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites).</span></span>
    
## <a name="modify-the-primary-sip-domain"></a><span data-ttu-id="e9772-222">プライマリ SIP ドメインを変更する</span><span class="sxs-lookup"><span data-stu-id="e9772-222">Modify the primary SIP domain</span></span>
<span data-ttu-id="e9772-223"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="e9772-223"></span></span>

<span data-ttu-id="e9772-224">クラウド コネクタ展開にプライマリ SIP ドメインを変更する場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e9772-224">If you need to change the primary SIP domain in your Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="e9772-225">Office 365 でドメインを更新する手順を完了し、DNS レコードを追加できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e9772-225">Make sure you've completed the steps to update your domain in Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="e9772-226">Office 365 でドメインを設定する方法の詳細については、 [Office 365 にドメインの追加](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9772-226">For more information about how to set up your domain in Office 365, see [Add a domain to Office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="e9772-227">新しい SIP ドメインとは、クラウドのコネクタの構成ファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="e9772-227">Update the Cloud Connector configuration file with the new SIP domain.</span></span>
    
3. <span data-ttu-id="e9772-228">新しいエッジ外部証明書を要求、クラウドのコネクタ構成で定義されている各 SIP ドメインの sip.domain の他の SAN 名。</span><span class="sxs-lookup"><span data-stu-id="e9772-228">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="e9772-229">新しい Microsoft Edge 外部証明書のパスを次のように設定します。</span><span class="sxs-lookup"><span data-stu-id="e9772-229">Set the path for the new Edge external certificate as follows:</span></span>
    
   ```
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    <span data-ttu-id="e9772-230">サイト内でクラウドのコネクタの管理者 PowerShell で次のコマンドレットを実行しているアプライアンスそれぞれに対してテナント登録を削除します。</span><span class="sxs-lookup"><span data-stu-id="e9772-230">Remove the tenant registration for each appliance in a site by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```
   Unregister-CcAppliance
   ```

6. 
    
    <span data-ttu-id="e9772-231">Skype for Business Online の PowerShell で次のコマンドを実行して、各サイトのサイト登録を削除します。</span><span class="sxs-lookup"><span data-stu-id="e9772-231">Remove the site registration for each site by running the following cmdlet in Skype for Business Online PowerShell:</span></span>
    
   ```
   Remove-CsHybridPSTNSite
   ```

7. 
    
    <span data-ttu-id="e9772-232">各アプライアンスをアンインストールするには、クラウドのコネクタの管理者 PowerShell で次のコマンドレットを実行しています。</span><span class="sxs-lookup"><span data-stu-id="e9772-232">Uninstall each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```
   Uninstall-CcAppliance
   ```

8. 
    
     <span data-ttu-id="e9772-233">各アプライアンスを登録するには、クラウドのコネクタの管理者 PowerShell で次のコマンドレットを実行しています。</span><span class="sxs-lookup"><span data-stu-id="e9772-233">Register each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```
   Register-ccAppliance
   ```

9. 
    
     <span data-ttu-id="e9772-234">各アプライアンスをインストールする管理者 PowerShell でクラウド コネクタで次のコマンドレットを実行している、1 つずつ。</span><span class="sxs-lookup"><span data-stu-id="e9772-234">Install each appliance, one by one, by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```
   Install-CcAppliance
   ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a><span data-ttu-id="e9772-235">外部境界の証明書を新しい証明書に置き換える</span><span class="sxs-lookup"><span data-stu-id="e9772-235">Replace the external Edge certificate with a new certificate</span></span>
<span data-ttu-id="e9772-236"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="e9772-236"></span></span>

<span data-ttu-id="e9772-237">コネクタのクラウド アプライアンス上のエッジの外部の証明書を交換する場合は、新しいエッジの証明書を取得し、秘密キーと、完全な証明書チェーンを含む PFX ファイルを準備し、各アプライアンスで、次の操作を行います必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9772-237">When you need to replace the external Edge certificate on your Cloud Connector appliances, you will need to obtain a new Edge certificate, prepare the PFX file containing the Private Key and full certificate chain, and then do the following on each appliance:</span></span>
  
1. <span data-ttu-id="e9772-238">入力 CcUpdate コマンドレットを使用してメンテナンス モードでのアプライアンスを配置します。</span><span class="sxs-lookup"><span data-stu-id="e9772-238">Put the appliance in maintenance mode by using the Enter-CcUpdate cmdlet.</span></span>
    
2. <span data-ttu-id="e9772-239">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e9772-239">Run the following command:</span></span> 
    
   ```
   Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
   ```

3. 
    
    <span data-ttu-id="e9772-240">新しい証明書のパスワードが、以前と同じ場合は、インポートが許可されます。</span><span class="sxs-lookup"><span data-stu-id="e9772-240">If the password of the new certificate is the same as the old, the import will be successful.</span></span> <span data-ttu-id="e9772-241">パスワードが間違っている場合は、そのレジスタ CcAppliance コマンドレットを実行してパスワードをリセットする必要があります。 エラーが発生したが、パスワードが異なる場合は、-ローカルのパラメーターを使用し、繰り返しの手順 2 とします。</span><span class="sxs-lookup"><span data-stu-id="e9772-241">If the password is different, you will receive an error that the password is wrong, and you will need to reset the password by running the Register-CcAppliance cmdlet with the -Local parameter, and then repeating step 2.</span></span> 
    
4. <span data-ttu-id="e9772-242">終了 CcUpdate コマンドレットを使用してメンテナンス モードからアプライアンスを実行します。</span><span class="sxs-lookup"><span data-stu-id="e9772-242">Take the appliance out of maintenance mode by using the Exit -CcUpdate cmdlet.</span></span>
    

