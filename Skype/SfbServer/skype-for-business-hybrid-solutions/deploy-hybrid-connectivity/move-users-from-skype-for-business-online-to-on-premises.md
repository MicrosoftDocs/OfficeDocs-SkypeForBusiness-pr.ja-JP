---
title: ビジネス上でオンラインに設置型の Skype のユーザーの移動
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/19/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 55733bb5-6742-4daf-8db5-1c5df86f4cea
description: 概要では、Skype で設置型のオンラインでのビジネス サーバーのユーザー アカウントを移動する方法について説明します。
ms.openlocfilehash: 655c037fc2299044aa3799d06e0d231784248d7e
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2018
ms.locfileid: "23260147"
---
# <a name="move-users-from-skype-for-business-online-to-on-premises"></a><span data-ttu-id="3a004-103">ビジネス上でオンラインに設置型の Skype のユーザーの移動</span><span class="sxs-lookup"><span data-stu-id="3a004-103">Move users from Skype for Business Online to on premises</span></span>

<span data-ttu-id="3a004-104">**の概要:** Skype で設置型のオンラインでのビジネス サーバーのユーザー アカウントを移動する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3a004-104">**Summary:** Learn how to move user accounts from online to on premises in Skype for Business Server.</span></span>

<span data-ttu-id="3a004-105">ユーザーがオンライン ホームし、設置型では、互いに検出可能なことを確認するには、社内設置型のオンラインでのユーザー アカウントを移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a004-105">You might need to move user accounts from online to on premises to ensure that users homed online and on premises are discoverable to one another.</span></span> <span data-ttu-id="3a004-106">互いに発見可能な状態には、すべてのユーザーは、オンプレミスの Active Directory に存在必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a004-106">To be discoverable to one another, all users must have a presence in the on-premises Active Directory.</span></span> <span data-ttu-id="3a004-107">詳細については、[サーバーのビジネスとオンライン ビジネスの Skype の Skype 間のハイブリッド接続の計画](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a004-107">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md).</span></span> <span data-ttu-id="3a004-108">場合など、社内のユーザーがオンラインに移動する場合。</span><span class="sxs-lookup"><span data-stu-id="3a004-108">You might want to move online users to on premises, for example, if:</span></span>

- <span data-ttu-id="3a004-109">設置型で作成し、クラウドへの移行が必要なユーザーは、新しいがあります。</span><span class="sxs-lookup"><span data-stu-id="3a004-109">You have new users who need to be created on premises and then moved to the cloud.</span></span>

- <span data-ttu-id="3a004-110">組織は、Skype をビジネス サーバーに展開する前に、Skype をオンライン ビジネスの展開。</span><span class="sxs-lookup"><span data-stu-id="3a004-110">Your organization deployed Skype for Business Online before it deployed Skype for Business Server.</span></span> <span data-ttu-id="3a004-111">したがって、最初に、クラウドで作成されたユーザーがいるし、オンライン ビジネスの Skype を移動する前に社内に移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a004-111">Therefore, you have users who were created in the cloud first, and now need to be moved to on premises before they are move to Skype for Business Online.</span></span>

<span data-ttu-id="3a004-112">このトピックでは、2 つのシナリオについて説明します。</span><span class="sxs-lookup"><span data-stu-id="3a004-112">This topic describes two scenarios:</span></span>

- [<span data-ttu-id="3a004-113">オンラインのユーザーを移動、ユーザーが最初にオンライン-への設置型</span><span class="sxs-lookup"><span data-stu-id="3a004-113">Move online users—who were originally online—to on premises</span></span>](move-users-from-skype-for-business-online-to-on-premises.md#BKMK_originallyonline)

- [<span data-ttu-id="3a004-114">オンライン ユーザーの移動 (ユーザーの社内には、元々 あった) に設置型の</span><span class="sxs-lookup"><span data-stu-id="3a004-114">Move online users (who were originally on premises) to on premises</span></span>](move-users-from-skype-for-business-online-to-on-premises.md#BKMK_originallyonprem)

## <a name="move-online-userswho-were-originally-onlineto-on-premises"></a><span data-ttu-id="3a004-115">オンラインのユーザーを移動、ユーザーが最初にオンライン-への設置型</span><span class="sxs-lookup"><span data-stu-id="3a004-115">Move online users—who were originally online—to on premises</span></span>
<span data-ttu-id="3a004-116"><a name="BKMK_originallyonline"> </a></span><span class="sxs-lookup"><span data-stu-id="3a004-116"></span></span>

<span data-ttu-id="3a004-117">このセクションは、ユーザーが Active Directory に施設内で、アカウントを持っていないユーザーがユーザーが作成され、オンラインで有効になっているだけに適用されます。</span><span class="sxs-lookup"><span data-stu-id="3a004-117">This section applies only to users who were created and enabled online, but who do not have an account in the on premises Active Directory.</span></span>

<span data-ttu-id="3a004-118">オンライン ユーザーをオンプレミス環境に移動する前に、次のすべての条件が満たされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3a004-118">Before you start moving online users to your on-premises environment, check that all of the following are true:</span></span>

- <span data-ttu-id="3a004-119">オンプレミス環境は、完全に展開および検証されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a004-119">Your on-premises environment must be fully deployed and validated.</span></span> <span data-ttu-id="3a004-120">詳細については、 [Lync Server 2013 の展開](https://technet.microsoft.com/library/b76795a4-4e71-4c70-a5c0-d1197fa8028c.aspx)または[展開の Skype](../../deploy/deploy.md)ビジネス サーバー 2015 のどちらのバージョンによっては、設置型で使用しているを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a004-120">For more information, see [Deploying Lync Server 2013](https://technet.microsoft.com/library/b76795a4-4e71-4c70-a5c0-d1197fa8028c.aspx) or [Deploy Skype for Business Server 2015](../../deploy/deploy.md), depending on which version you are using on premises.</span></span>

- <span data-ttu-id="3a004-121">オンライン、テナントは、PowerShell のリモート アクセス用に構成しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="3a004-121">Your online tenant must be configured for remote PowerShell access.</span></span>

    <span data-ttu-id="3a004-122">これを行うには、ここに到達することができる Windows PowerShell の最初にコネクタ モジュールのオンライン ビジネスの Skype をインストール: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?LinkId=391911)。</span><span class="sxs-lookup"><span data-stu-id="3a004-122">To do this, first install the Skype for Business Online connector module for Windows PowerShell, which you can get here: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span></span>

    <span data-ttu-id="3a004-123">モジュールをインストールした後は、Skype のビジネス サーバー管理シェルの次のコマンドレットを入力してリモート セッションを確立できます。</span><span class="sxs-lookup"><span data-stu-id="3a004-123">After you install the module, you can establish a remote session by typing the following cmdlets in the Skype for Business Server Management Shell:</span></span>

  ```
  Import-Module SkypeOnlineConnector
  ```

  ```
  $cred = Get-Credential
  ```

  ```
  $CSSession = New-CsOnlineSession -Credential $cred
  ```

  ```
  Import-PSSession $CSSession -AllowClobber
  ```

    <span data-ttu-id="3a004-124">PowerShell を Skype でオンライン ビジネスでの使用についての詳細については、 [Windows PowerShell には、コンピューターの設定](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a004-124">For more information about using PowerShell with Skype for Business Online, see [Set up your computer for Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span></span>

- <span data-ttu-id="3a004-125">共有 SIP アドレス スペースのオンライン、テナントを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a004-125">Your online tenant must be configured for a shared SIP address space.</span></span> <span data-ttu-id="3a004-126">これを行うには、まずリモート Powershell セッション Skype でのオンライン ビジネスです。</span><span class="sxs-lookup"><span data-stu-id="3a004-126">To do this, first start a remote Powershell session with Skype for Business Online.</span></span> <span data-ttu-id="3a004-127">続いて、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="3a004-127">Then run the following cmdlet:</span></span>

  ```
  Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
  ```

    > [!NOTE]
    > <span data-ttu-id="3a004-128">最終版では、オンラインに移動するまで、"True"とユーザーを維持するのには SharedSipAddressSpace 属性のニーズは、施設内に残ります。</span><span class="sxs-lookup"><span data-stu-id="3a004-128">The SharedSipAddressSpace attribute needs to remain "True" until moving to online is final, and no users remain on premises.</span></span>

<span data-ttu-id="3a004-129">手順が終了したら後、は、次の手順で説明したようにユーザー アカウントを移行できます。</span><span class="sxs-lookup"><span data-stu-id="3a004-129">After you've finished these steps, you can migrate user accounts as described in the following procedure:</span></span>

### <a name="move-user-accounts-originally-enabled-online-to-an-on-premises-deployment"></a><span data-ttu-id="3a004-130">最初の設置型の展開にオンライン有効になっているユーザー アカウントを移動します。</span><span class="sxs-lookup"><span data-stu-id="3a004-130">Move user accounts originally enabled online to an on-premises deployment</span></span>

1. <span data-ttu-id="3a004-131">最初に、組織がハイブリッド用に構成されていることを確認します (Azure Active Directory Connect と同期ツールを含む)。</span><span class="sxs-lookup"><span data-stu-id="3a004-131">First, make sure that your organization is configured for hybrid, including Azure Active Directory Connect and sync tools.</span></span> <span data-ttu-id="3a004-132">詳細については、[サーバーのビジネスとオンライン ビジネスの Skype の Skype 間のハイブリッド接続の計画](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a004-132">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md).</span></span>

  - <span data-ttu-id="3a004-133">設置型展開、ビジネス サーバー管理シェルには、Skype のオンライン ビジネスの Skype のホスティング プロバイダーを作成するのには、次のコマンドレットを入力します。</span><span class="sxs-lookup"><span data-stu-id="3a004-133">On your on-premises deployment, in the Skype for Business Server Management Shell, type the following cmdlets to create the hosting provider for Skype for Business Online.</span></span> <span data-ttu-id="3a004-134">Identity および Name パラメーターには、必要な任意の値を使用できます。</span><span class="sxs-lookup"><span data-stu-id="3a004-134">You can use whatever value you want for the Identity and Name parameters.</span></span>

  ```
  Set-CsAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $true
  ```

  ```
  New-CsHostingProvider -Identity SkypeforBusinessOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
  ```

2. <span data-ttu-id="3a004-135">確認、設置型のエッジ トランスポート サーバー上のビジネス オンラインでは、Skype への接続を有効にする証明書チェーン、次の表に示すように。</span><span class="sxs-lookup"><span data-stu-id="3a004-135">Confirm that on your on-premises Edge Servers, you have the certificate chain that enables connection to Skype for Business Online, as shown in the following table.</span></span> <span data-ttu-id="3a004-136">このチェーンは、ここをダウンロードすることができます: [https://corp.sts.microsoft.com/Onboard/ADFS_Onboarding_Pack/corp_sts_certs.zip](https://corp.sts.microsoft.com/Onboard/ADFS_Onboarding_Pack/corp_sts_certs.zip)。</span><span class="sxs-lookup"><span data-stu-id="3a004-136">You can download this chain here: [https://corp.sts.microsoft.com/Onboard/ADFS_Onboarding_Pack/corp_sts_certs.zip](https://corp.sts.microsoft.com/Onboard/ADFS_Onboarding_Pack/corp_sts_certs.zip).</span></span>

|<span data-ttu-id="3a004-137">**証明書**</span><span class="sxs-lookup"><span data-stu-id="3a004-137">**Certificate**</span></span>|<span data-ttu-id="3a004-138">**証明書ストア**</span><span class="sxs-lookup"><span data-stu-id="3a004-138">**Certificate Store**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3a004-139">Baltimore CyberTrust Root</span><span class="sxs-lookup"><span data-stu-id="3a004-139">Baltimore CyberTrust Root</span></span>  <br/> |<span data-ttu-id="3a004-140">信頼されたルート CA</span><span class="sxs-lookup"><span data-stu-id="3a004-140">Trusted Root CA</span></span>  <br/> |
|<span data-ttu-id="3a004-141">Microsoft Internet Authority (新しい CA 証明書)</span><span class="sxs-lookup"><span data-stu-id="3a004-141">Microsoft Internet Authority (New CA certificate)</span></span>  <br/> |<span data-ttu-id="3a004-142">中間 CA</span><span class="sxs-lookup"><span data-stu-id="3a004-142">Intermediate CA</span></span>  <br/> |
|<span data-ttu-id="3a004-143">MSIT Machine Auth CA2 (新規発行 CA2)</span><span class="sxs-lookup"><span data-stu-id="3a004-143">MSIT Machine Auth CA2 (New Issuing CA2)</span></span>  <br/> |<span data-ttu-id="3a004-144">中間 CA</span><span class="sxs-lookup"><span data-stu-id="3a004-144">Intermediate CA</span></span>  <br/> |

3. <span data-ttu-id="3a004-145">オンプレミスの Active Directory では、社内のビジネス サーバー 2015 の Skype の影響を受けるユーザー アカウントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="3a004-145">In your on-premises Active Directory, enable the affected user accounts for Skype for Business Server 2015 on premises.</span></span> <span data-ttu-id="3a004-146">ユーザーごとにこの操作を行うには、次のコマンドレットを入力します。</span><span class="sxs-lookup"><span data-stu-id="3a004-146">You can do this for an individual user by typing the following cmdlet:</span></span>

  ```
  Enable-CsUser
-Identity "username "
-SipAddress "sip: username @contoso.com"
-HostingProviderProxyFqdn "sipfed.online.lync.com"
  ```

    <span data-ttu-id="3a004-147">または、ファイルからユーザー名を読み込んで Enable-CsUser コマンドレットへの入力として与えるスクリプトを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="3a004-147">Or you can create a script that reads user names from a file and provides them as input to the Enable-CsUser cmdlet:</span></span>

  ```
  Enable-CsUser
-Identity $Identity
-SipAddress $SipAddress
-HostingProviderProxyFqdn "sipfed.online.lync.com"
  ```

4. <span data-ttu-id="3a004-148">オンプレミスで更新されたユーザーとオンラインのユーザーを同期します。</span><span class="sxs-lookup"><span data-stu-id="3a004-148">Synchronize the online users with the updated on-premises users.</span></span> <span data-ttu-id="3a004-149">詳細については、[ディレクトリの統合ツール](https://go.microsoft.com/fwlink/p/?LinkId=530320)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a004-149">For more information, see [Directory Integration Tools](https://go.microsoft.com/fwlink/p/?LinkId=530320).</span></span>

5. <span data-ttu-id="3a004-150">設置型展開へのすべての SIP トラフィックをダイレクトするのには次の DNS レコードを更新します。</span><span class="sxs-lookup"><span data-stu-id="3a004-150">Update the following DNS records to direct all SIP traffic to your on-premises deployment:</span></span>

  - <span data-ttu-id="3a004-151">オンプレミスのリバース プロキシ サーバーの FQDN を指すように **lyncdiscover.contoso.com** A レコードを更新します。</span><span class="sxs-lookup"><span data-stu-id="3a004-151">Update the **lyncdiscover.contoso.com** A record to point to the FQDN of the on-premises reverse proxy server.</span></span>

  - <span data-ttu-id="3a004-152">更新、 \*\* *_sip* 。 _tls.contoso.com\*\* Lync の設置型のアクセス エッジ サービスのパブリック IP または VIP アドレスに解決するには、SRV レコード。</span><span class="sxs-lookup"><span data-stu-id="3a004-152">Update the ***_sip*  ._tls.contoso.com** SRV record to resolve to the public IP or VIP address of the Access Edge service of Lync on-premises.</span></span>

  - <span data-ttu-id="3a004-153">更新、 \*\* *_sipfederationtls* 。 _tcp.contoso.com\*\*のビジネス サーバー 2015 設置、Skype のアクセス エッジ サービスのパブリック IP または VIP アドレスに解決するには、SRV レコード。</span><span class="sxs-lookup"><span data-stu-id="3a004-153">Update the ***_sipfederationtls*  ._tcp.contoso.com** SRV record to resolve to the public IP or VIP address of the Access Edge service of Skype for Business Server 2015 on-premises.</span></span>

  - <span data-ttu-id="3a004-154">組織で使用するには、DNS が (「DNS の分散管理」とも呼ばれます) を分割する場合は、内部の DNS ゾーンで名前を解決するユーザーは、フロント エンド プールに割り当て、を確認します。</span><span class="sxs-lookup"><span data-stu-id="3a004-154">If your organization uses split DNS (sometimes called "split-brain DNS"), make sure that users resolving names through the internal DNS zone are directed to the Front End Pool.</span></span>

6. <span data-ttu-id="3a004-155">型、`Get-CsUser`を移動するユーザーに関するいくつかのプロパティを確認するコマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="3a004-155">Type the  `Get-CsUser` cmdlet to check some properties about the users you'll be moving.</span></span> <span data-ttu-id="3a004-156">HostingProviderProxyFQDN が `"sipfed.online.lync.com"` に設定されていること、および SIP アドレスが適切に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3a004-156">You want to make sure that the HostingProviderProxyFQDN is set to `"sipfed.online.lync.com"` and that the SIP addresses are set correctly.</span></span>

7. <span data-ttu-id="3a004-157">設置型のオンライン ユーザーを移動します。</span><span class="sxs-lookup"><span data-stu-id="3a004-157">Move online users to on premises.</span></span>

    <span data-ttu-id="3a004-158">単独のユーザーを移動するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="3a004-158">To move a single user, type this:</span></span>

  ```
  $cred = Get-Credential
  Move-CsUser -Identity <username>@contoso.com  -Target "<fe-pool>.contoso.com " -Credential $cred -HostedMigrationOverrideURL <URL>
  ```

    <span data-ttu-id="3a004-159">**Get CsUSer**コマンドレットを使用して複数のユーザーを移動することができますフィルター パラメーターを指定する特定のプロパティを使用してユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="3a004-159">You can move multiple users by using the **Get-CsUSer** cmdlet with the -Filter parameter to select the users with a specific property.</span></span> <span data-ttu-id="3a004-160">たとえば、{プロバイダーをホストしている eq"sipfed.online.lync.om"} のフィルターを使用して、オンラインのすべてのユーザーを選択できます。</span><span class="sxs-lookup"><span data-stu-id="3a004-160">For example, you could select all Online users by filtering for {Hosting Provider -eq "sipfed.online.lync.om"}.</span></span> <span data-ttu-id="3a004-161">コマンドレットにパイプ**移動 CsUSer**コマンドレットでは、返されるユーザーは、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="3a004-161">You can then pipe the returned users to the **Move-CsUSer** cmdlet, as shown below.</span></span>

  ```
  Get-CsUser -Filter {Hosting Provider -eq "sipfed.online.lync.com"} | Move-CsUser -Target "<fe-pool>.contoso.com " -Credential $creds -HostedMigrationOverrideURL <URL>
  ```

    <span data-ttu-id="3a004-162">**HostedMigrationOverrideUrl**パラメーターは次の形式で、ホストの移行サービスが実行されているプールへの URL である必要があります用に指定された URL の形式: _Https://\<プールの FQDN\>/HostedMigration/hostedmigrationService.svc_。</span><span class="sxs-lookup"><span data-stu-id="3a004-162">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format: _Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc_.</span></span>

    <span data-ttu-id="3a004-163">ホスティング型移行サービスへの URL は、ご使用の Office 365 テナント アカウント用の Lync Online コントロール パネルの URL を表示することで確認できます。</span><span class="sxs-lookup"><span data-stu-id="3a004-163">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Office 365 tenant account.</span></span>

### <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a><span data-ttu-id="3a004-164">Office 365 テナントのホスティング型移行サービスの URL を確認するには</span><span class="sxs-lookup"><span data-stu-id="3a004-164">To determine the Hosted Migration Service URL for your Office 365 tenant</span></span>

1. <span data-ttu-id="3a004-165">管理者として Office 365 テナントにログインします。</span><span class="sxs-lookup"><span data-stu-id="3a004-165">Login to your Office 365 tenant as an administrator.</span></span>

2. <span data-ttu-id="3a004-166">[**Skype for Business 管理センター**] を開きます。</span><span class="sxs-lookup"><span data-stu-id="3a004-166">Open the **Skype for Business admin center**.</span></span>

3. <span data-ttu-id="3a004-p112">[**Skype for Business 管理センター**] が表示されたら、**lync.com** の近くのアドレス バーの URL を選択してコピーします。URL は、次のような書式です。</span><span class="sxs-lookup"><span data-stu-id="3a004-p112">With the **Skype for Business admin center** displayed, select and copy the URL in the address bar up to **lync.com**. An example URL looks similar to the following:</span></span>

     `https://webdir0a.online.lync.com/lscp/?language=en-US&amp;tenantID=`

4. <span data-ttu-id="3a004-169">URL の **webdir** を **admin** に置き換えると、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="3a004-169">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>

     `https://admin0a.online.lync.com`

5. <span data-ttu-id="3a004-170">URL に以下の文字列を付加します。**/HostedMigration/hostedmigrationservice.svc**</span><span class="sxs-lookup"><span data-stu-id="3a004-170">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>

    <span data-ttu-id="3a004-171">結果の URL は、 **HostedMigrationOverrideUrl**の値は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="3a004-171">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>

     `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

    > [!NOTE]
    > <span data-ttu-id="3a004-172">rtcxds データベースのトランザクション ログ ファイルの既定の最大サイズは 16 GB です。</span><span class="sxs-lookup"><span data-stu-id="3a004-172">The default maximum size for transaction log files of the rtcxds database is 16 GB.</span></span> <span data-ttu-id="3a004-173">これがあります十分な大きさを一度に多数のユーザーを移動する場合特に有効になっているミラー化がある場合。</span><span class="sxs-lookup"><span data-stu-id="3a004-173">This might not be big enough if you're moving a large number of users at once, especially if you have mirroring enabled.</span></span> <span data-ttu-id="3a004-174">これに対処するには、ファイル サイズを大きくするか、ログ ファイルを定期的にバックアップします。</span><span class="sxs-lookup"><span data-stu-id="3a004-174">To get around this you can increase the file size or back up the log files regularly.</span></span> <span data-ttu-id="3a004-175">詳細についてを参照してください[https://support.microsoft.com/kb/2756725](https://support.microsoft.com/kb/2756725)。</span><span class="sxs-lookup"><span data-stu-id="3a004-175">For more information, see [https://support.microsoft.com/kb/2756725](https://support.microsoft.com/kb/2756725).</span></span>

8. <span data-ttu-id="3a004-176">この手順は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="3a004-176">This is an optional step.</span></span> <span data-ttu-id="3a004-177">Exchange 2013 Online と統合する必要がある場合は、追加のホスティング プロバイダーが必要になります。</span><span class="sxs-lookup"><span data-stu-id="3a004-177">If you need to integrate with Exchange 2013 Online, you need to use an additional hosting provider.</span></span> <span data-ttu-id="3a004-178">詳細については、[設置型の Skype ビジネス サーバー 2015 と Outlook Web App の構成の統合](../../deploy/integrate-with-exchange-server/outlook-web-app.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a004-178">For details, see [Configure integration between on-premises Skype for Business Server 2015 and Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md).</span></span>

9. <span data-ttu-id="3a004-p115">ユーザーが移動されます。次の表に示すユーザーの属性の値が適切であることを確認するために、次のコマンドレットを入力します。</span><span class="sxs-lookup"><span data-stu-id="3a004-p115">The users are now moved. To check that a user has correct values for the attributes shown in the following table, type this cmdlet:</span></span>

  ```
  Get-CsUser | fl DisplayName,HostingProvider,SipAddress,Enabled
  ```

|<span data-ttu-id="3a004-181">**Active Directory 属性**</span><span class="sxs-lookup"><span data-stu-id="3a004-181">**Active Directory attribute**</span></span>|<span data-ttu-id="3a004-182">**属性名**</span><span class="sxs-lookup"><span data-stu-id="3a004-182">**Attribute name**</span></span>|<span data-ttu-id="3a004-183">**オンライン ユーザーに適切な値**</span><span class="sxs-lookup"><span data-stu-id="3a004-183">**Correct value for Online user**</span></span>|<span data-ttu-id="3a004-184">**オンプレミス ユーザーの適切な値**</span><span class="sxs-lookup"><span data-stu-id="3a004-184">**Correct value for on-premises users**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3a004-185">msRTCSIP DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="3a004-185">msRTCSIP-DeploymentLocator</span></span>  <br/> |<span data-ttu-id="3a004-186">HostingProvider</span><span class="sxs-lookup"><span data-stu-id="3a004-186">HostingProvider</span></span>  <br/> |<span data-ttu-id="3a004-187">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="3a004-187">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="3a004-188">SRV</span><span class="sxs-lookup"><span data-stu-id="3a004-188">SRV:</span></span>  <br/> |
|<span data-ttu-id="3a004-189">msRTCSIP PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="3a004-189">msRTCSIP-PrimaryUserAddress</span></span>  <br/> |<span data-ttu-id="3a004-190">SIPAddress</span><span class="sxs-lookup"><span data-stu-id="3a004-190">SIPAddress</span></span>  <br/> |<span data-ttu-id="3a004-191">sip:userName@contoso.com</span><span class="sxs-lookup"><span data-stu-id="3a004-191">sip:userName@contoso.com</span></span>  <br/> |<span data-ttu-id="3a004-192">sip:userName@contoso.com</span><span class="sxs-lookup"><span data-stu-id="3a004-192">sip:userName@contoso.com</span></span>  <br/> |
|<span data-ttu-id="3a004-193">msRTCSIP UserEnabled</span><span class="sxs-lookup"><span data-stu-id="3a004-193">msRTCSIP-UserEnabled</span></span>  <br/> |<span data-ttu-id="3a004-194">Enabled</span><span class="sxs-lookup"><span data-stu-id="3a004-194">Enabled</span></span>  <br/> |<span data-ttu-id="3a004-195">True</span><span class="sxs-lookup"><span data-stu-id="3a004-195">True</span></span>  <br/> |<span data-ttu-id="3a004-196">True</span><span class="sxs-lookup"><span data-stu-id="3a004-196">True</span></span>  <br/> |

10. <span data-ttu-id="3a004-p116">移動された各ユーザーは、いったんログアウトしてからログインし直す必要があります。ユーザーは、ログイン時に連絡先リストを確認し、必要に応じて連絡先を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a004-p116">Each user who has been moved will need to log out, then log back in. When they log in they should verify their contact lists, and add contacts if needed.</span></span>

    <span data-ttu-id="3a004-p117">スケジュールされていた会議は、オンラインからオンプレミスに移行されないことに注意してください。ユーザーは、移動後にこれらの会議をスケジュールし直す必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a004-p117">Note that scheduled meetings are not migrated from online to on-premises. Users will need to reschedule these meetings after being moved.</span></span>

    <span data-ttu-id="3a004-201">DNS レコードが更新され、すべてのユーザーは、オンプレミスに割り当て、HostingProvider 属性にログオンする SRV レコードを使用するか、問い合わせオンライン プロバイダー"sipfed.online.lync.com"にします。</span><span class="sxs-lookup"><span data-stu-id="3a004-201">After the DNS records are updated and all users are directed to On-premises, the HostingProvider attribute directs the user to either use SRV records or direct them to the Online provider "sipfed.online.lync.com."</span></span>

## <a name="move-online-users-who-were-originally-on-premises-to-on-premises"></a><span data-ttu-id="3a004-202">オンライン ユーザーの移動 (ユーザーの社内には、元々 あった) に設置型の</span><span class="sxs-lookup"><span data-stu-id="3a004-202">Move online users (who were originally on premises) to on premises</span></span>
<span data-ttu-id="3a004-203"><a name="BKMK_originallyonprem"> </a></span><span class="sxs-lookup"><span data-stu-id="3a004-203"></span></span>

<span data-ttu-id="3a004-204">このセクションでは、作成し設置型の展開を有効にし、設置型展開からオンラインへ移動されたユーザーにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="3a004-204">This section applies only to users who were created and enabled for an on-premises deployment and then moved from an on-premises deployment to online.</span></span>

- <span data-ttu-id="3a004-205">ユーザーからに移動する Skype ビジネス オンラインの設置、お客様の環境の値を修正するのには**Id**と**ターゲット**のパラメーターの値を置き換えるには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="3a004-205">Run the following cmdlets to move a user from Skype for Business Online back to on-premises, replacing the value for the **Identity** and **Target** parameters to correct values for your environment:</span></span>

  ```
  $cred=Get-Credential
  ```

  ```
  Move-CsUser -Identity username@contoso.com -Target localpool.contoso.com -Credential $cred -HostedMigrationOverrideUrl <URL>
  ```

<span data-ttu-id="3a004-206">**HostedMigrationOverrideUrl**パラメーターに指定された URL の形式は次の形式で、ホストの移行サービスが実行されているプールへの URL である必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a004-206">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format:</span></span>

 <span data-ttu-id="3a004-207">_Https://\<プールの FQDN\>/HostedMigration/hostedmigrationService.svc_。</span><span class="sxs-lookup"><span data-stu-id="3a004-207">_Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc_.</span></span> <span data-ttu-id="3a004-208">ホスティング型移行サービスへの URL は、ご使用の Office 365 テナント アカウント用の Lync Online コントロール パネルの URL を表示することで確認できます。</span><span class="sxs-lookup"><span data-stu-id="3a004-208">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Office 365 tenant account.</span></span>

### <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a><span data-ttu-id="3a004-209">Office 365 テナントのホスティング型移行サービスの URL を確認するには</span><span class="sxs-lookup"><span data-stu-id="3a004-209">To determine the Hosted Migration Service URL for your Office 365 tenant</span></span>

1. <span data-ttu-id="3a004-210">管理者として Office 365 テナントにログインします。</span><span class="sxs-lookup"><span data-stu-id="3a004-210">Login to your Office 365 tenant as an administrator.</span></span>

2. <span data-ttu-id="3a004-211">[**Skype for Business 管理センター**] を開きます。</span><span class="sxs-lookup"><span data-stu-id="3a004-211">Open the **Skype for Business admin center**.</span></span>

3. <span data-ttu-id="3a004-p119">[**Skype for Business 管理センター**] が表示されたら、**lync.com** の近くのアドレス バーの URL を選択してコピーします。URL は、次のような書式です。</span><span class="sxs-lookup"><span data-stu-id="3a004-p119">With the **Skype for Business admin center** displayed, select and copy the URL in the address bar up to **lync.com**. An example URL looks similar to the following:</span></span>

     `https://webdir0a.online.lync.com/lscp/?language=en-US&amp;tenantID=`

4. <span data-ttu-id="3a004-214">URL の **webdir** を **admin** に置き換えると、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="3a004-214">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>

     `https://admin0a.online.lync.com`

5. <span data-ttu-id="3a004-215">URL に以下の文字列を付加します。**/HostedMigration/hostedmigrationservice.svc**</span><span class="sxs-lookup"><span data-stu-id="3a004-215">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>

    <span data-ttu-id="3a004-216">結果の URL は、 **HostedMigrationOverrideUrl**の値は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="3a004-216">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>

     `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`


