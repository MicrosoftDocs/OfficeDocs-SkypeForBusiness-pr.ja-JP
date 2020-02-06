---
title: Cloud Connector 展開をトラブルシューティングする
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/5/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e6cf58cc-dbd9-4f35-a51a-3e2fea71b5a5
description: クラウドコネクタエディションの展開のトラブルシューティングを行います。
ms.openlocfilehash: 3a6fd80cc0c4125303021746cdb626d8c5b49a5a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814225"
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a><span data-ttu-id="45978-103">Cloud Connector 展開をトラブルシューティングする</span><span class="sxs-lookup"><span data-stu-id="45978-103">Troubleshoot your Cloud Connector deployment</span></span>
 
<span data-ttu-id="45978-104">クラウドコネクタエディションの展開のトラブルシューティングを行います。</span><span class="sxs-lookup"><span data-stu-id="45978-104">Troubleshoot your Cloud Connector Edition deployment.</span></span>
  
<span data-ttu-id="45978-p101">このトピックでは、Cloud Connector Edition の展開に関する一般的な問題の解決策について説明します。公衆交換電話網 (PSTN) による通話で問題が発生する場合は、このトピックで説明する手順に従って調査することができます。</span><span class="sxs-lookup"><span data-stu-id="45978-p101">This topic describes solutions to common issues with Cloud Connector Edition deployments. If you are experiencing issues with calls to and from the Public Switched Telephone Network (PSTN), you can investigate by following the solutions described in this topic.</span></span>
  
<span data-ttu-id="45978-107">クラウドコネクタには、一部の問題を自動的に解決するための組み込みメカニズムが用意されています。</span><span class="sxs-lookup"><span data-stu-id="45978-107">Cloud Connector provides built-in mechanisms for automatically resolving some issues.</span></span> <span data-ttu-id="45978-108">自動検出プロセスでは、クラウドコネクタのアプライアンスで発生する可能性のある問題を探し、可能であれば、管理者の介入なしでそれらの問題を解決するための修正措置をとることができます。</span><span class="sxs-lookup"><span data-stu-id="45978-108">An automatic detection process looks for potential issues with the Cloud Connector appliances, and, if possible, takes corrective action to resolve those issues without the need for administrator intervention.</span></span> <span data-ttu-id="45978-109">検出プロセスは次のように機能します。</span><span class="sxs-lookup"><span data-stu-id="45978-109">The detection process works as follows:</span></span>
  
- <span data-ttu-id="45978-110">**検出シーケンス:** クラウドコネクタ管理サービスは、60秒ごとに、アプライアンスがダウンしているかどうかを検出するためのプロセスを実行します。</span><span class="sxs-lookup"><span data-stu-id="45978-110">**Detection sequence:** The Cloud Connector Management service runs a process every 60 seconds for detecting whether an appliance is down.</span></span> <span data-ttu-id="45978-111">クラウドコネクタバージョン2.0 以降では、検出プロセスでは、クラウドコネクタマシンへの PowerShell 接続を実現するために、Skype for Business ネットワークのスイッチを使用します。2.0 より前のバージョンでは、検出プロセスではクラウドコネクタ管理スイッチを使用します。</span><span class="sxs-lookup"><span data-stu-id="45978-111">In Cloud Connector version 2.0 and later, the detection process uses the Skype for Business Corpnet switch for making PowerShell connections to the Cloud Connector machines; for versions previous to 2.0, the detection process uses the Cloud Connector management switch.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="45978-112">自動回復を正常に実行するには、ホストと仮想マシン間のネットワーク接続がホストネットワークスイッチを経由している必要があります。</span><span class="sxs-lookup"><span data-stu-id="45978-112">For automatic recovery to succeed, there must be network connectivity between the host and virtual machines over the host network switch.</span></span> <span data-ttu-id="45978-113">自動検出と回復が正常に機能することを確認するため、ネットワーク接続を確認してください。</span><span class="sxs-lookup"><span data-stu-id="45978-113">Be sure to check network connectivity to ensure that automatic detection and recovery can succeed.</span></span> 
  
- <span data-ttu-id="45978-114">**監視:** クラウドコネクタバージョン2.0 以降では、次のサービスが監視されています。</span><span class="sxs-lookup"><span data-stu-id="45978-114">**Monitoring:** The following services are monitored in Cloud Connector version 2.0 and later:</span></span>
    
  - <span data-ttu-id="45978-115">仮想マシンがクラウドコネクタの企業またはインターネット仮想スイッチに接続されていない</span><span class="sxs-lookup"><span data-stu-id="45978-115">Virtual Machines are not connected to the Cloud Connector Corporate or Internet virtual switches</span></span>
    
  - <span data-ttu-id="45978-116">仮想マシンが保存済みまたは停止状態である</span><span class="sxs-lookup"><span data-stu-id="45978-116">Virtual Machines are in a saved or stopped status</span></span>
    
  - <span data-ttu-id="45978-117">サーバーの全体管理サーバーサービス: REPLICA、MASTER</span><span class="sxs-lookup"><span data-stu-id="45978-117">Central Management Server services: REPLICA, MASTER</span></span>
    
  - <span data-ttu-id="45978-118">仲介サーバーサービス: REPLICA、RTCSRV、MEDSVC</span><span class="sxs-lookup"><span data-stu-id="45978-118">Mediation Server services: REPLICA, RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="45978-119">Edge Server services: REPLICA、RTCSRV、RTCDATAPROXY、RTCMRAUTH、RTCDATAPROXY</span><span class="sxs-lookup"><span data-stu-id="45978-119">Edge Server services: REPLICA, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY</span></span>
    
  - <span data-ttu-id="45978-120">エッジサーバー上の CS RTCSRV の受信ファイアウォールルールが無効になっている (仲介サーバー上の CS RTCMEDSRV)</span><span class="sxs-lookup"><span data-stu-id="45978-120">Inbound firewall rules are disabled for CS RTCSRV on Edge server, CS RTCMEDSRV on Mediation server</span></span>
    
    <span data-ttu-id="45978-121">Cloud Connector バージョン1.4.2 では、次のサービスのみが監視されます。</span><span class="sxs-lookup"><span data-stu-id="45978-121">In Cloud Connector version 1.4.2, only the following services are monitored:</span></span>
    
  - <span data-ttu-id="45978-122">仲介サーバーサービス: RTCSRV と MEDSVC</span><span class="sxs-lookup"><span data-stu-id="45978-122">Mediation Server services: RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="45978-123">エッジサーバーサービス: RTCSRV</span><span class="sxs-lookup"><span data-stu-id="45978-123">Edge Server service: RTCSRV</span></span>
    
- <span data-ttu-id="45978-124">**回復プロセス:** 監視されているサービスがダウンしている場合は、アプライアンスがダウンしていて、すべての問題を解決するまで、サービスが停止され、手動でマークされます。</span><span class="sxs-lookup"><span data-stu-id="45978-124">**Recovery process:** If any monitored services are down, an appliance is marked down, and services are stopped and marked manual until all issues can be resolved.</span></span> <span data-ttu-id="45978-125">これにより、通話の失敗の原因となる可能性があるアプライアンスへのルーティングからの通話ができなくなります。</span><span class="sxs-lookup"><span data-stu-id="45978-125">This will prevent calls from routing to an appliance that may cause call failures.</span></span>
    
    <span data-ttu-id="45978-126">クラウドコネクタ管理サービスは、次のように自動回復を再試行します。</span><span class="sxs-lookup"><span data-stu-id="45978-126">The Cloud Connector Management service will retry automatic recovery as follows</span></span>
    
  - <span data-ttu-id="45978-127">最初の再試行間隔は、最長で1時間の時間間隔で10秒ごとに指定します。</span><span class="sxs-lookup"><span data-stu-id="45978-127">The initial retry interval is every ten seconds with a maximum interval time of one hour.</span></span>
    
  - <span data-ttu-id="45978-128">最初の3回の回復試行の場合、間隔は10秒です。</span><span class="sxs-lookup"><span data-stu-id="45978-128">For the first three recovery attempts, the interval time is 10 seconds.</span></span> <span data-ttu-id="45978-129">4回目の再試行から開始します。間隔は、前の間隔の2倍で増加します。</span><span class="sxs-lookup"><span data-stu-id="45978-129">Starting from the fourth retry, the interval time increases by two times the previous interval time.</span></span> <span data-ttu-id="45978-130">たとえば、4回目の再試行は20秒、5分40秒で行われます。</span><span class="sxs-lookup"><span data-stu-id="45978-130">For example, the fourth retry will occur in 20 seconds, the fifth in 40 seconds, and so on.</span></span> 
    
  - <span data-ttu-id="45978-131">1時間の最大間隔の時間に達すると、再試行は1時間に1回続行されます。</span><span class="sxs-lookup"><span data-stu-id="45978-131">When the maximum interval time of one hour is reached, retries will continue once per hour.</span></span>
    
  - <span data-ttu-id="45978-132">回復が成功すると、間隔と再試行回数が初期値に設定されます。</span><span class="sxs-lookup"><span data-stu-id="45978-132">When recovery is successful, the interval and retry counts are set to their initial values.</span></span>
    
  - <span data-ttu-id="45978-133">管理サービスが再開されると、間隔と再試行カウントは初期値にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="45978-133">If the Management service is restarted, the interval and retry counts are reset to their initial values.</span></span>
    
## <a name="troubleshooting"></a><span data-ttu-id="45978-134">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="45978-134">Troubleshooting</span></span>

<span data-ttu-id="45978-135">一般的に発生する問題の解決策を次に示します。</span><span class="sxs-lookup"><span data-stu-id="45978-135">Following are solutions to commonly encountered issues:</span></span>
  
- <span data-ttu-id="45978-136">**問題: 展開スクリプトを実行すると、展開が失敗するか、応答しなくなる。各 VM にログインすると、管理/内部/外部 NIC の IP アドレスがないか、正しくない。**</span><span class="sxs-lookup"><span data-stu-id="45978-136">**Issue: Deployment fails or stops responding when running the deployment scripts. After logging on to each VM, the IP address is missing or incorrect for the Management/Internal/External NIC.**</span></span>
    
    <span data-ttu-id="45978-137">**解像度:** この問題は自動的に解決することはできません。</span><span class="sxs-lookup"><span data-stu-id="45978-137">**Resolution:** This issue cannot be resolved automatically.</span></span> <span data-ttu-id="45978-138">Nic は、実行中に Vm に追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="45978-138">NICs cannot be added to VMs while they are running.</span></span> <span data-ttu-id="45978-139">Hyper-v manager でこれらの Vm をシャットダウンして削除してから、次のコマンドレットを実行してください。</span><span class="sxs-lookup"><span data-stu-id="45978-139">Please shut down and remove these VMs in hyper-v manager, then run the following cmdlets:</span></span>
    
  ```powershell
  Uninstall-CcAppliance
  ```

  ```powershell
  Install-CcAppliance
  ```

- 
    
    <span data-ttu-id="45978-140">**問題: Active Directory とフォレストをインストールした後、CMS サーバーや仲介サーバーがドメインに正しく参加しない。**</span><span class="sxs-lookup"><span data-stu-id="45978-140">**Issue: After the Active Directory Server and forest are installed, the CMS Server and/or Mediation Server did not join the domain correctly.**</span></span>
    
    <span data-ttu-id="45978-141">**解決策:** この問題を解決するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="45978-141">**Resolution:** To resolve this issue, take the following steps:</span></span>
    
  - <span data-ttu-id="45978-142">Active Directory サーバーにログオンし、ドメインが正しく作成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="45978-142">Log on to the Active Directory Server and verify that the domain was created correctly.</span></span>
    
  - <span data-ttu-id="45978-143">CMS/仲介サーバーにログオンし、Corpnet NIC で有効な IP アドレスが割り当てられていることと、AD サーバーの IP アドレスとして有効な固定 IP アドレスと DNS が構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="45978-143">Log on to the CMS/Mediation Server and verify that on the corpnet NIC a valid IP address is assigned, and that valid static IP and DNS is configured as the AD server's IP address.</span></span>
    
  - <span data-ttu-id="45978-144">CMS/仲介サーバーにログオンし、コマンドプロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="45978-144">Log on to the CMS/Mediation Server, and open a command prompt.</span></span> <span data-ttu-id="45978-145">Active Directory サーバーの FQDN と IP アドレスに対して ping を実行できることを確かめます。</span><span class="sxs-lookup"><span data-stu-id="45978-145">Make sure you can ping the FQDN and IP address of the Active Directory Server.</span></span> <span data-ttu-id="45978-146">実行できない場合は、IP アドレスの競合が考えられます。</span><span class="sxs-lookup"><span data-stu-id="45978-146">If you cannot, there may be an IP address conflict.</span></span> <span data-ttu-id="45978-147">Active Directory に新しい IP を割り当てて、CMS/仲介サーバーで DNS を更新することを試してください。</span><span class="sxs-lookup"><span data-stu-id="45978-147">Please try to assign a new IP for Active Directory and update DNS on the CMS/Mediation server accordingly.</span></span>
    
- <span data-ttu-id="45978-148">**問題: "仮想イーサネットスイッチの削除中にエラーが発生しました。" というエラーメッセージが表示されます。仮想スイッチ ' Cloud Connector 管理スイッチ ' は、仮想マシンを実行しているか、子プールに割り当てられているため、削除できません。 "**</span><span class="sxs-lookup"><span data-stu-id="45978-148">**Issue: You receive the following error message, "Remove-VMSwitch : Failed while removing virtual Ethernet switch. The virtual switch 'Cloud Connector Management Switch' cannot be deleted because it is being used by running virtual machines or assigned to child pools."**</span></span>
    
    <span data-ttu-id="45978-149">**解像度:** 展開後、"クラウドコネクタ管理スイッチ" は削除されませんでした。</span><span class="sxs-lookup"><span data-stu-id="45978-149">**Resolution:** The "Cloud Connector Management Switch" was not deleted after the deployment.</span></span> <span data-ttu-id="45978-150">このエラーが発生した場合は、Hyper-v マネージャーに移動して、仮想マシンがまだ接続されていないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="45978-150">If you hit this error, please go to Hyper-v manager and verify that there is not still a virtual machine still connected to it.</span></span> <span data-ttu-id="45978-151">仮想マシンがまだ接続されている場合は、切断し、管理スイッチを削除します。</span><span class="sxs-lookup"><span data-stu-id="45978-151">If there are virtual machines still connected, disconnect them and delete the management switch.</span></span> <span data-ttu-id="45978-152">それでも管理スイッチを削除できない場合は、ホストサーバーを再起動して、もう一度やり直してください。</span><span class="sxs-lookup"><span data-stu-id="45978-152">If the management switch still cannot be deleted, restart the host server and try again.</span></span>
    
- <span data-ttu-id="45978-153">**問題: 次のエラーメッセージが表示されました。 "サービス RTCMRAUTH を開始できませんでした。サービスが無効になっていないことを確認してください。 "**</span><span class="sxs-lookup"><span data-stu-id="45978-153">**Issue: You receive the following error message, "Service RTCMRAUTH failed to start. Check to make sure the service is not disabled."**</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="45978-154">この問題は、Cloud Connector バージョン1.4.2 より前のバージョンにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="45978-154">This issue only applies to Cloud Connector versions earlier than 1.4.2.</span></span> 
  
    <span data-ttu-id="45978-p110">開始できない原因としては、このフロントエンド サーバーが (コンピューターのフェイルオーバーを使用して) 以前も失敗してやり直したことも考えられます。その場合は、(コンピューターのフェールバックアップを使用して) フェールバックを呼び出してください。</span><span class="sxs-lookup"><span data-stu-id="45978-p110">The failure to start could also be because this Front End server was previously failed over (using computer fail over). If that's the case, please invoke fail back (using computer fail back).</span></span>
    
    <span data-ttu-id="45978-p111">**解決策:** この問題は、ルート CA 証明書または中間 CA 証明書がエッジ サーバーで信頼されていない場合に、エッジ サーバーで発生します。外部証明書をインポートできるとしても、証明書チェーンが破損しています。この状況では、RTCMRAUTH か RTCSRV、またはその両方のサービスが開始できません。</span><span class="sxs-lookup"><span data-stu-id="45978-p111">**Resolution:** This issue happens on an Edge Server when the root CA certificate or intermediate CA certificate is not trusted by the Edge Server. Even if the external certificate can be imported but the certificate chain is broken. Under this condition, the RTCMRAUTH and/or RTCSRV service can not start.</span></span>
    
    <span data-ttu-id="45978-p112">ルート CA 証明書と、外部証明書の中間 CA 証明書をすべて手動でエッジ サーバーにをインポートしてから、エッジ サーバーを再起動します。エッジ サーバーで RTCMRAUTH サービスと RTCSRV サービスが開始したことを確認したら、ホスト サーバーに戻り、管理者として PowerShell コンソールを起動し、次のコマンドレットを実行して新しい展開に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="45978-p112">Please import the root CA certificate and all intermediate CA certificates of your external certificate manually into the Edge Server and then restart the Edge Server. After you see the RTCMRAUTH and RTCSRV services started on the Edge Server, go back to your host server, launch a PowerShell console as administrator, and run following cmdlet to switch to the new deployment:</span></span>
    
  ```powershell
  Switch-CcVersion
  ```

- 
    
    <span data-ttu-id="45978-162">**問題: Windows Update の適用中にホスト サーバーが再起動され、サーバーによる呼び出しに失敗する。**</span><span class="sxs-lookup"><span data-stu-id="45978-162">**Issue: The host server was restarted when Windows updates were applied, and calls serviced by the server are failing.**</span></span>
    
    <span data-ttu-id="45978-p113">**解決策:** 高可用性環境を展開した場合は、Windows Update を手動で確認およびインストールするときに、1 台のホスト マシン (展開インスタンス) を現在のトポロジに移動するか、またはそこから移動するのに役立つコマンドレットが用意されています。これを行うには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="45978-p113">**Resolution:** If you deployed a high availability environment, Microsoft provides a cmdlet to help move one host machine (deployment instance) into or out of the current topology when you check and install Windows update manually. Use the following steps to accomplish this:</span></span>
    
1. <span data-ttu-id="45978-165">ホスト サーバーで、管理者として PowerShell コンソールを起動して、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="45978-165">On the host server, start a PowerShell console as administrator, then run:</span></span>
    
   ```powershell
   Enter-CcUpdate
   ```

2. <span data-ttu-id="45978-166">利用可能な更新をチェックしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="45978-166">Check for updates and install any that are available.</span></span>
    
3. <span data-ttu-id="45978-167">PowerShell コンソールで、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="45978-167">In the PowerShell console, run the following cmdlet:</span></span>
    
   ```powershell
   Exit-CcUpdate
   ```

- 
    
    <span data-ttu-id="45978-168">**問題: PSTN 番号を使って Skype for Business クライアントから通話を発信するとき、別の PSTN 番号を招待することで電話会議に通話をエスカレートできない。**</span><span class="sxs-lookup"><span data-stu-id="45978-168">**Issue: When a call is made from a Skype for Business client using a PSTN number, the call cannot be escalated to a conference by inviting another PSTN number.**</span></span>
    
    <span data-ttu-id="45978-169">**解像度:** この問題を解決するには、「[オンラインハイブリッド仲介サーバーの設定を構成](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45978-169">**Resolution:** To resolve this issue, see [Configure online hybrid Mediation Server Settings](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).</span></span>
    
- <span data-ttu-id="45978-170">**問題: Active Directory サーバーのインストール中に、「Windows 自動更新が有効になっていません。新しくインストールした役割または機能が自動的に更新されるようにするには、[Windows Update] を有効にしてください」という Windows Update に関する警告メッセージが表示される。**</span><span class="sxs-lookup"><span data-stu-id="45978-170">**Issue: A warning message is displayed about Windows Update when you are installing Active Directory server - "Windows automatic updating is not enabled. To ensure that your newly-installed role or feature is automatically updated, turn on Windows Update."**</span></span>
    
    <span data-ttu-id="45978-171">**解像度:** Skype for Business テナント管理者の資格情報を使用してテナントリモート PowerShell セッションを開始し、次のコマンドレットを実行して、サイトの_Enableautoupdate_構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="45978-171">**Resolution:** Launch a Tenant Remote PowerShell session using Skype for Business tenant admin credentials, then run the following cmdlet to check the _EnableAutoUpdate_ configuration of your site:</span></span>
    
  ```powershell
  Get-CsHybridPSTNSite
  ```

    <span data-ttu-id="45978-172">_Enableautoupdate_が**True**に設定されている場合、CCEManagement サービスは仮想マシンとホストサーバーの両方の Windows 更新プログラムのダウンロードとインストールを処理するため、この警告メッセージは安全に無視できます。</span><span class="sxs-lookup"><span data-stu-id="45978-172">If  _EnableAutoUpdate_ is set to **True**, you can safely ignore this warning message because the CCEManagement service will handle downloading and installing Windows updates for both virtual machines and the host server.</span></span> <span data-ttu-id="45978-173">_Enableautoupdate_が**False**に設定されている場合は、次のコマンドレットを実行して**True**に設定します。</span><span class="sxs-lookup"><span data-stu-id="45978-173">If  _EnableAutoUpdate_ is set to **False**, run following cmdlet to set it to **True**.</span></span>
    
  ```powershell
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    <span data-ttu-id="45978-174">または、更新プログラムを手動で確認してインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="45978-174">Alternatively, you can manually check for and install updates.</span></span> <span data-ttu-id="45978-175">次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="45978-175">See the next section.</span></span>
    
- <span data-ttu-id="45978-176">**問題: エラーメッセージが表示される: 現在の入力/ \<構成サイト\>名また\<\> \<はアプライアンスのドメイン\> \<名または仲介サーバーの IP アドレス\>が既存のアプライアンスと競合しているため、アプライアンスを登録できません。コンフリクト製品を削除するか、入力/構成情報を更新して、もう一度登録します。' Register-CcAppliance を実行して、現在のアプライアンスをオンラインに登録します。**</span><span class="sxs-lookup"><span data-stu-id="45978-176">**Issue: You receive an error message: Cannot register appliance because your current input/configuration \<SiteName\> or \<ApplianceName\> or \<Mediation Server FQDN\> or \<Mediation Server IP Address\> conflicts with existing appliance(s). Remove conflict appliance or update your input/configuration information then register again. ' when run Register-CcAppliance to register current appliance to online.**</span></span>
    
    <span data-ttu-id="45978-177">**解像度:** アプライアンスのドメイン\<\>名、 \<仲介サーバーの FQDN\> 、 \<仲介サーバーの IP アドレス\>の値は、一意であり、1つのアプライアンス登録でのみ使用されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="45978-177">**Resolution:** Values for the \<ApplianceName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> must be unique and only used for one appliance registration.</span></span> <span data-ttu-id="45978-178">既定では\<、ホスト名\>から取得されます。</span><span class="sxs-lookup"><span data-stu-id="45978-178">By default, \<ApplianceName\> comes from the host name.</span></span> <span data-ttu-id="45978-179">\<構成 ini ファイル\>で\<定義されて\>いる仲介サーバーの FQDN と仲介サーバーの IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="45978-179">\<Mediation Server FQDN\> and \<Mediation Server IP Address\> defined in configuration ini file.</span></span>
    
    <span data-ttu-id="45978-180">たとえば、(ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) を使用して SiteName=MySite に登録しても、登録済みアプライアンス (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) があると、競合が発生します。</span><span class="sxs-lookup"><span data-stu-id="45978-180">For example, using (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) to register to SiteName=MySite, but if there is a registered appliance (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10), you will have the conflict.</span></span>
    
    <span data-ttu-id="45978-181">まず、ApplianceRoot ディレクトリ セクションで CloudConnector.ini ファイルを確認します。</span><span class="sxs-lookup"><span data-stu-id="45978-181">First, please check your CloudConnector.ini file in ApplianceRoot directory section.</span></span> <span data-ttu-id="45978-182">ファイルには\<、\>SiteName \<、仲介サーバー\>の\<FQDN、および仲介\>サーバーの IP アドレスの値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="45978-182">You will get \<SiteName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> values in the file.</span></span> <span data-ttu-id="45978-183">\<アプライアンス名\>は、ホストサーバー名です。</span><span class="sxs-lookup"><span data-stu-id="45978-183">\<ApplianceName\> is your host server name.</span></span>
    
    <span data-ttu-id="45978-184">次に、Skype for Business テナント管理者の資格情報を使用してテナントリモート PowerShell を起動し、次のコマンドレットを実行して登録済みのアプライアンスを確認します。</span><span class="sxs-lookup"><span data-stu-id="45978-184">Second, Launch Tenant Remote PowerShell using your Skype for Business tenant admin credentials, then run the following cmdlet to check the registered appliance(s).</span></span>
    
  ```powershell
  Get-CsHybridPSTNAppliance
  ```

    <span data-ttu-id="45978-185">競合を特定したら、登録済みアプライアンスと一致する情報を CloudConnector.ini ファイルで更新するか、既存のアプライアンスを登録解除して、競合を解決します。</span><span class="sxs-lookup"><span data-stu-id="45978-185">After identifying any conflicts, you can either update your CloudConnector.ini file with information that matches the registered appliance, or unregister the existing appliance to resolve the conflicts.</span></span>
    
  ```powershell
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
- <span data-ttu-id="45978-186">**問題: ホストで実行されている展開済みのアプライアンスがある場合、Get-CcRunningVersion コマンドレットは空の値を返します。**</span><span class="sxs-lookup"><span data-stu-id="45978-186">**Issue: The Get-CcRunningVersion cmdlet returns an empty value if there is a deployed appliance running on the host.**</span></span>
    
  <span data-ttu-id="45978-187">**解像度:** これは、1.3.4 または1.3.8 から1.4.1 にアップグレードした場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="45978-187">**Resolution:** This can happen when you upgrade from 1.3.4 or 1.3.8 to 1.4.1.</span></span> <span data-ttu-id="45978-188">.Msi を使ってバージョン1.4.1 をインストールした後、他`Register-CcAppliance`のコマンドレットを実行する前に実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="45978-188">After you install version 1.4.1 with the .msi, you must run `Register-CcAppliance` before you run any other cmdlet.</span></span> <span data-ttu-id="45978-189">`Register-CcAppliance`%UserProfile%\CloudConnector から%ProgramData%\CloudConnector. にモジュール .ini ファイルを移行します</span><span class="sxs-lookup"><span data-stu-id="45978-189">`Register-CcAppliance` will migrate the module.ini file from %UserProfile%\CloudConnector to %ProgramData%\CloudConnector.</span></span> <span data-ttu-id="45978-190">見逃した場合は、%ProgramData%\CloudConnector フォルダーに新しい system.ini が作成され、1.3.4 または1.3.8 の実行/バックアップバージョンの情報が置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="45978-190">If you missed it, a new module.ini will be created in %ProgramData%\CloudConnector folder and replace the running/backup version information for 1.3.4 or 1.3.8.</span></span>
    
  <span data-ttu-id="45978-191">%UserProfile%\CloudConnector と %ProgramData%\CloudConnector フォルダーにある module.ini ファイルを比較します。</span><span class="sxs-lookup"><span data-stu-id="45978-191">Compare module.ini files in %UserProfile%\CloudConnector and %ProgramData%\CloudConnector folder.</span></span> <span data-ttu-id="45978-192">相違点がある場合は、%ProgramData%\CloudConnector でそのモジュールの .ini ファイルを`Register-CcAppliance`削除して再実行します。</span><span class="sxs-lookup"><span data-stu-id="45978-192">If there are differences, delete the module.ini file in %ProgramData%\CloudConnector and rerun  `Register-CcAppliance`.</span></span> <span data-ttu-id="45978-193">また、ファイルを手動で実行およびバックアップバージョンに変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="45978-193">You could also modify the file manually to the correct running and backup version.</span></span>
    
- <span data-ttu-id="45978-194">**問題: スイッチ-CcVersion コマンドレットを実行して、現在のスクリプトのバージョンとは異なる古いバージョンに切り替えると、この古いバージョンでは高可用性のサポートはありません。**</span><span class="sxs-lookup"><span data-stu-id="45978-194">**Issue: After you run the Switch-CcVersion cmdlet to switch to an old version which is different from current script version, there is no High Availability support for this old version.**</span></span>
    
    <span data-ttu-id="45978-195">**解像度:** たとえば、1.4.1 から1.4.2 にアップグレードしたとします。</span><span class="sxs-lookup"><span data-stu-id="45978-195">**Resolution:** For example, you have upgraded from 1.4.1 to 1.4.2.</span></span> <span data-ttu-id="45978-196">現在のスクリプトのバージョンは、実行`Get-CcVersion`によって決定され、実行中のバージョン`Get-CcRunningVersion`はどちらも1.4.2 であることが確認できます。</span><span class="sxs-lookup"><span data-stu-id="45978-196">Your current script version, which can be determined by running `Get-CcVersion`, and your running version, which can be determined by running  `Get-CcRunningVersion` are both 1.4.2.</span></span> <span data-ttu-id="45978-197">現時点では、実行され`Switch-CcVersion`ているバージョンを1.4.1 に戻す場合、この古いバージョンについては高可用性のサポートはありません。</span><span class="sxs-lookup"><span data-stu-id="45978-197">At this time, if you run `Switch-CcVersion` to switch the running version back to 1.4.1, then there will be no High Availability support for this old version.</span></span>
    
    <span data-ttu-id="45978-p121">高可用性を完全にサポートするには、1.4.2 に切り替えて、実行中のバージョンとスクリプト バージョンが同じになるようにします。1.4.2 展開で問題が発生している場合は、できるだけ早くアンインストールして、再インストールしてください。</span><span class="sxs-lookup"><span data-stu-id="45978-p121">To get full High Availability support, please switch back to 1.4.2, so the running version and script version are the same. If you are experiencing problems with your 1.4.2 deployment, please uninstall and reinstall it as soon as possible.</span></span>
    
- <span data-ttu-id="45978-200">**問題: 証明機関の証明書、または中央管理ストア、仲介サーバー、エッジ サーバーに対して発行された内部証明書の有効期限が近づいているか、侵害された。**</span><span class="sxs-lookup"><span data-stu-id="45978-200">**Issue: Certificate authority certificates or internal certificates issued to Central Management Store, Mediation Server, and Edge Server are near expiration or are compromised.**</span></span>
    
    <span data-ttu-id="45978-p122">**解決策:** Skype for Business 証明機関の証明書は 5 年間有効です。中央管理ストア、仲介サーバー、エッジ サーバーに対して発行された内部証明書は 2 年間有効です。</span><span class="sxs-lookup"><span data-stu-id="45978-p122">**Resolution:** Skype for Business certification authority certificates are valid for five years. Internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="45978-203">クラウドコネクタバージョン2.0 以降では、更新-CcServerCertificate コマンドレットが更新-CcServerCertificate に変更され、CcCACertificate コマンドレットが更新-CcCACertificate に変更されました。</span><span class="sxs-lookup"><span data-stu-id="45978-203">In Cloud Connector version 2.0 and later, the Renew-CcServerCertificate cmdlet has changed to Update-CcServerCertificate and the Renew-CcCACertificate cmdlet has changed to Update-CcCACertificate.</span></span> 
  
    <span data-ttu-id="45978-204">中央管理ストア、仲介サーバー、エッジサーバーに対して発行された内部証明書の有効期限が近づいている場合は、CcServerCertificate または Update-CcServerCertificate コマンドレットを実行して、証明書を更新します。</span><span class="sxs-lookup"><span data-stu-id="45978-204">If internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are near expiration or compromised, run the Renew-CcServerCertificate or Update-CcServerCertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="45978-205">証明機関証明書の有効期限が近づいている場合は、CcCACertificate または CcCACertificate コマンドレットを実行して証明書を更新します。</span><span class="sxs-lookup"><span data-stu-id="45978-205">If certification authority certificates are near expiration, run the Renew-CcCACertificate or Update-CcCACertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="45978-206">**証明機関の証明書が侵害され、サイトに1つのアプライアンスしか存在しない場合は、** 次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="45978-206">**If certification authority certificates are compromised and there is only one appliance in the site,** perform the following steps:</span></span>
    
1. <span data-ttu-id="45978-207">Enter-CcUpdate コマンドレットを実行して、サービスをドレインし、アプライアンスをメンテナンス モードにします。</span><span class="sxs-lookup"><span data-stu-id="45978-207">Run the Enter-CcUpdate cmdlet to drain services and put the appliance in maintenance mode.</span></span>
   
   ```powershell
   Enter-CcUpdate
   ```
   
2. <span data-ttu-id="45978-208">次のコマンドレットを実行して、リセットし、新しい証明機関の証明書とすべての内部サーバー証明書を作成します。</span><span class="sxs-lookup"><span data-stu-id="45978-208">Run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
    <span data-ttu-id="45978-209">2.0 より前のクラウドコネクタリリースの場合:</span><span class="sxs-lookup"><span data-stu-id="45978-209">For Cloud Connector releases before 2.0:</span></span>
    
    ```powershell
    Reset-CcCACertificate 
    Renew-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

    <span data-ttu-id="45978-210">または、クラウドコネクタのリリース2.0 以降:</span><span class="sxs-lookup"><span data-stu-id="45978-210">Or for Cloud Connector release 2.0 and later:</span></span>
    
    ```powershell
    Reset-CcCACertificate 
    Update-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```
    
3. <span data-ttu-id="45978-211">ゲートウェイと仲介サーバーの間で TLS が使用されている場合は、アプライアンスから CcRootCertificate コマンドレットを実行してから、エクスポートされた証明書を PSTN ゲートウェイにインストールします。</span><span class="sxs-lookup"><span data-stu-id="45978-211">If TLS is used between the gateway and the Mediation Server, run the Export-CcRootCertificate cmdlet from the appliance, and then install the exported certificate to your PSTN gateways.</span></span> <span data-ttu-id="45978-212">また、ゲートウェイで証明書を再発行する必要がある場合もあります。</span><span class="sxs-lookup"><span data-stu-id="45978-212">You may also be required to re-issue the certificate on your gateway.</span></span>

   ```powershell
   Export-CcRootCertificate
   ```

4. <span data-ttu-id="45978-213">終了-CcUpdate コマンドレットを実行してサービスを開始し、メンテナンスモードを終了します。</span><span class="sxs-lookup"><span data-stu-id="45978-213">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span>

   ```powershell
   Exit-CcUpdate
   ```


    <span data-ttu-id="45978-214">**証明機関の証明書が侵害され、サイトに複数のアプライアンスがある場合は、** サイト内の各アプライアンスで次の一連の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="45978-214">**If certification authority certificates are compromised and there are multiple appliances in the site,** perform the following sequential steps on each appliance in the site.</span></span>
    
    <span data-ttu-id="45978-215">この手順は、ピーク時以外の時間帯に実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="45978-215">Microsoft recommends that you perform these steps during non-peak usage times.</span></span>
    
1. <span data-ttu-id="45978-216">最初のアプライアンスで、CcCertificationAuthorityFile コマンドレットを実行して、 \<siteroot\>ディレクトリにある CA バックアップファイルをクリーンアップします。</span><span class="sxs-lookup"><span data-stu-id="45978-216">On the first appliance, run the Remove-CcCertificationAuthorityFile cmdlet to clean up the CA backup files in the \<SiteRoot\> directory.</span></span>

     ```powershell
     Remove-CcCertificationAuthorityFile
     ```
    
2. <span data-ttu-id="45978-217">「CcUpdate」コマンドレットを実行してサービスをドレインし、各アプライアンスをメンテナンスモードにします。</span><span class="sxs-lookup"><span data-stu-id="45978-217">Run the Enter-CcUpdate cmdlet to drain services and put each appliance in maintenance mode.</span></span>

     ```powershell
     Enter-CcUpdate
     ```
    
3. <span data-ttu-id="45978-218">最初のアプライアンスで、次のコマンドレットを実行して、新しい証明機関証明書とすべての内部サーバー証明書をリセットして作成します。</span><span class="sxs-lookup"><span data-stu-id="45978-218">On the first appliance, run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
     <span data-ttu-id="45978-219">2.0 より前のクラウドコネクタリリースの場合:</span><span class="sxs-lookup"><span data-stu-id="45978-219">For Cloud Connector releases before 2.0:</span></span>
    
     ```powershell
     Reset-CcCACertificate
     Renew-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

     <span data-ttu-id="45978-220">または、クラウドコネクタのリリース2.0 以降:</span><span class="sxs-lookup"><span data-stu-id="45978-220">Or for Cloud Connector release 2.0 and later:</span></span>
    
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

4. <span data-ttu-id="45978-221">最初のアプライアンスで、次のコマンドレットを実行して、CA ファイルを\<siteroot\>フォルダにバックアップします。</span><span class="sxs-lookup"><span data-stu-id="45978-221">On the first appliance, run the following cmdlet to back up the CA files to the \<SiteRoot\> folder.</span></span>
    
     ```powershell
     Backup-CcCertificationAuthority
     ```
   
5. <span data-ttu-id="45978-222">同じサイト内の他のすべてのアプライアンスで、次のコマンドを実行して CA バックアップファイルを使用すると、すべてのアプライアンスで同じルート証明書が使用され、新しい証明書が要求されます。</span><span class="sxs-lookup"><span data-stu-id="45978-222">On all other appliance's in the same site, run the following commands to consume the CA backup files, so that the appliances all use the same root certificate, and then request new certificates.</span></span> 
   
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```
     
6. <span data-ttu-id="45978-223">ゲートウェイと仲介サーバーの間で TLS が使用されている場合は、サイト内の任意のアプライアンスから CcRootCertificate コマンドレットを実行し、エクスポートされた証明書を PSTN ゲートウェイにインストールします。</span><span class="sxs-lookup"><span data-stu-id="45978-223">If TLS is used between the gateway and the Mediation Server, run the Export-CcRootCertificate cmdlet from any appliance in the site, and then install the exported certificate to your PSTN gateways.</span></span> <span data-ttu-id="45978-224">また、ゲートウェイで証明書を再発行する必要がある場合もあります。</span><span class="sxs-lookup"><span data-stu-id="45978-224">You may also be required to re-issue the certificate on your gateway.</span></span>
  
     ```powershell
     Export-CcRootCertificate
     ```
     
7. <span data-ttu-id="45978-225">終了-CcUpdate コマンドレットを実行してサービスを開始し、メンテナンスモードを終了します。</span><span class="sxs-lookup"><span data-stu-id="45978-225">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span> 

     ```powershell
     Exit-CcUpdate
     ```
    
    
- <span data-ttu-id="45978-226">**問題: クラウドコネクタ管理サービスログ "C:\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log": CceService Error: 0: 状態をオンラインに報告するときに、予期しない例外が発生しました。 CmdletInvocationException: ユーザー \<グローバルテナント管理者\>のログオンに失敗しました。新しい credential オブジェクトを作成して、正しいユーザー名とパスワードを使用したことを確認してください。---\>**</span><span class="sxs-lookup"><span data-stu-id="45978-226">**Issue: You receive the following error message in the Cloud Connector Management Service Log, "C:\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log": CceService Error: 0 : Unexpected exception when reporting status to online: System.Management.Automation.CmdletInvocationException: Logon failed for the user \<Global Tenant Admin\>. Please create a new credential object, making sure that you have used the correct user name and password. ---\>**</span></span>
    
    <span data-ttu-id="45978-227">**解像度:** クラウドコネクタのアプライアンスが登録されてから、Office 365 グローバルテナント管理者の資格情報が変更されました。</span><span class="sxs-lookup"><span data-stu-id="45978-227">**Resolution:** The Office 365 global tenant admin credentials have been changed since the Cloud Connector appliance was registered.</span></span> <span data-ttu-id="45978-228">クラウドコネクタアプライアンスでローカルに保存されている資格情報を更新するには、ホストアプライアンスで、管理者 PowerShell から次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="45978-228">To update the locally stored credentials on the Cloud Connector appliance, run the following from Administrator PowerShell on the host appliance:</span></span>
    
  ```powershell
  Set-CcCredential -AccountType TenantAdmin
  ```

- <span data-ttu-id="45978-229">**問題: 展開に使用した host server アカウントのパスワードを変更すると、次のエラーメッセージが表示されます: "Convertto-json-「: 指定された状態で使用するためのキーが無効です。"%ProgramFiles%\Skype for Business Cloud Connector の場合Edition\ManagementService\CceManagementService.log または Get-CcCredential コマンドレットを実行中です。**</span><span class="sxs-lookup"><span data-stu-id="45978-229">**Issue: After you change the password for the host server account you used for the deployment, you receive the following error message: "ConvertTo-SecureString : Key not valid for use in specified state." in %ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log or while running the Get-CcCredential cmdlet.**</span></span>
    
    <span data-ttu-id="45978-230">**解像度:** すべてのクラウドコネクタの資格情報は、次のファイルに格納されます。 "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.</span><span class="sxs-lookup"><span data-stu-id="45978-230">**Resolution:** All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="45978-231">ホスト サーバーのパスワードを変更するときには、ローカルで格納されている資格情報を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="45978-231">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
    
    <span data-ttu-id="45978-232">**Cloud Connector バージョン 1.4.2 を実行している場合は、** 次の手順を実行してすべての Cloud Connector パスワードを再生成します。</span><span class="sxs-lookup"><span data-stu-id="45978-232">**If you are running Cloud Connector version 1.4.2,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  1. <span data-ttu-id="45978-233">ホスト サーバーを再起動します。</span><span class="sxs-lookup"><span data-stu-id="45978-233">Restart the host server.</span></span>
    
  2. <span data-ttu-id="45978-234">次のファイルを削除します: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.</span><span class="sxs-lookup"><span data-stu-id="45978-234">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
  3. <span data-ttu-id="45978-235">管理者として PowerShell コンソールを起動し、[この説明に従ってパスワードを再入力するには、"Register Appliance-Local]" を実行します。</span><span class="sxs-lookup"><span data-stu-id="45978-235">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="45978-236">Cloud Connector の展開で前回使用したパスワードと同じパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="45978-236">Enter the same passwords you entered before for the Cloud Connector deployment.</span></span>
    
     <span data-ttu-id="45978-237">**クラウドコネクタバージョン2.0 以降を実行**している場合は、次の手順に従って、すべてのクラウドコネクタのパスワードを再生成します。</span><span class="sxs-lookup"><span data-stu-id="45978-237">**If you are running Cloud Connector version 2.0 or later,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  4. <span data-ttu-id="45978-238">ホスト サーバーを再起動します。</span><span class="sxs-lookup"><span data-stu-id="45978-238">Restart the host server.</span></span>
    
  5. <span data-ttu-id="45978-239">次のファイルを削除します: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.</span><span class="sxs-lookup"><span data-stu-id="45978-239">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" .</span></span>
    
  6. <span data-ttu-id="45978-240">管理者として PowerShell コンソールを起動し、[この説明に従ってパスワードを再入力するには、"Register Appliance-Local]" を実行します。</span><span class="sxs-lookup"><span data-stu-id="45978-240">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> 
    
     <span data-ttu-id="45978-p128">キャッシュされているファイルが Cloud Connector バージョン 1.4.2 で生成されたファイルである場合は、パスワードを求められたときに CceService パスワードの VMAdmin パスワードを使用します。その他すべてのアカウントについては、Cloud Connector の展開で前回使用したパスワードと同じパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="45978-p128">If the cached password file was generated with Cloud Connector version 1.4.2, use the VMAdmin password for the CceService password when prompted. Enter the same password you entered before for the Cloud Connector deployment for all other accounts.</span></span>
    
     <span data-ttu-id="45978-243">キャッシュされているパスワード ファイルが Cloud Connector バージョン 1.4.2 で生成されたファイルであり、DomainAdmin と VMAdmin のパスワードが異なる場合は、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="45978-243">If the cached password file was generated with Cloud Connector version 1.4.2 and the DomainAdmin and VMAdmin passwords are different, you must perform the following steps:</span></span>
    
  7. <span data-ttu-id="45978-244">Set-CcCredential -AccountType DomainAdmin を次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="45978-244">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
  8. <span data-ttu-id="45978-245">以前のアカウントの資格情報を求められた場合は、CceService パスワードに使用した資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="45978-245">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
  9. <span data-ttu-id="45978-246">新しいアカウントの資格情報を求められた場合は、以前使用していた DomainAdmin パスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="45978-246">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
     <span data-ttu-id="45978-247">キャッシュされたパスワードファイルがクラウドコネクタバージョン2.0 以降で生成された場合、既定では、VmAdmin と DomainAdmin は CceService と同じパスワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="45978-247">If the cached password file was generated with Cloud Connector version 2.0 or later, by default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="45978-248">DomainAdmin と VMAdmin のパスワードを変更した場合は、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="45978-248">If you changed the DomainAdmin and VMAdmin passwords, you must perform the following steps:</span></span>
    
  10. <span data-ttu-id="45978-249">Set-CcCredential -AccountType DomainAdmin を次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="45978-249">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
       1. <span data-ttu-id="45978-250">以前のアカウントの資格情報を求められた場合は、CceService パスワードに使用した資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="45978-250">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="45978-251">新しいアカウントの資格情報を求められた場合は、以前使用していた DomainAdmin パスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="45978-251">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
  11. <span data-ttu-id="45978-252">Set-CcCredential -AccountType VmAdmin を次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="45978-252">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
       1. <span data-ttu-id="45978-253">以前のアカウントの資格情報を求められた場合は、CceService パスワードに使用した資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="45978-253">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="45978-254">新しいアカウントの資格情報を求められた場合は、以前使用していた VmAdmin パスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="45978-254">When prompted for the new account credential, enter the password for the VmAdmin password you used before.</span></span> 
    
- <span data-ttu-id="45978-255">**問題: Cloud Connector バージョン2.1 以降で、Register-CcAppliance またはアプライアンス上のその他のコマンドレットを実行すると、次のようなエラーメッセージが表示されます。このオブジェクトには、プロパティ ' Common ' が見つかりません。プロパティが存在することを確認します。C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1: 681 char:14 "**</span><span class="sxs-lookup"><span data-stu-id="45978-255">**Issue: With Cloud Connector version 2.1 and later, when running Register-CcAppliance or other cmdlets on the appliance, you receive an error message such as: "For Each-Object : The property 'Common' cannot be found on this object. Verify that the property exists. At C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char:14"**</span></span>
    
    <span data-ttu-id="45978-256">**解像度:** Cloud Connector 2.1 以降には、.NET Framework 4.6.1 以降が必要です。</span><span class="sxs-lookup"><span data-stu-id="45978-256">**Resolution:** Cloud Connector 2.1 and later requires .NET Framework 4.6.1 or later.</span></span> <span data-ttu-id="45978-257">アプライアンスの .NET Framework をバージョン4.6.1 以降に更新して、もう一度コマンドレットを実行してください。</span><span class="sxs-lookup"><span data-stu-id="45978-257">Please update .NET Framework on the appliance to version 4.6.1 or later and run the cmdlet(s) again.</span></span>

- <span data-ttu-id="45978-258">**問題: Cloud Connector エディション2.1 で、インストール-CcAppliance を実行しているときに、"新しいインスタンスをインストールできませんでした。" というエラーメッセージが表示されることがあります。これは、XmlNode のプロパティを設定するために文字列のみを値として使うことができるためです。**</span><span class="sxs-lookup"><span data-stu-id="45978-258">**Issue: With Cloud Connector Edition 2.1, when running Install-CcAppliance, you receive an error message such as: "Failed to install new instance with error: Cannot set "State" because only strings can be used as values to set XmlNode properties"**</span></span>

   <span data-ttu-id="45978-259">**解像度:** Cloudconnector の [Common] セクションで、以下のように "状態" の構成を追加してください: CountryCode = US 州 = WA City = レドモンド</span><span class="sxs-lookup"><span data-stu-id="45978-259">**Resolution:** In Cloudconnector.ini, under the [Common] section, please add the “State” config as below:  CountryCode=US  State=WA  City=Redmond</span></span>

   <span data-ttu-id="45978-260">"状態" 行に値を設定することは必須ではありませんが、Cloudconnector の .ini ファイルから "状態" 行を削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="45978-260">It is not mandatory for the "State" line to have value, however the "State" line cannot be removed from the Cloudconnector.ini file.</span></span>

- <span data-ttu-id="45978-261">**問題: 次のエラーメッセージが表示されます。 "WindowsImage: WindowsImage に失敗しました。エラーコード = 0xc1550115 "は、クラウドコネクタエディションをインストールまたはアップグレードするときに発生します。**</span><span class="sxs-lookup"><span data-stu-id="45978-261">**Issue: You receive the following error message "Dismount-WindowsImage : Dismount-WindowsImage failed. Error code = 0xc1550115" when installing or upgrading Cloud Connector Edition.**</span></span>
    
    <span data-ttu-id="45978-262">**解像度:** 管理者として PowerShell コンソールを起動し、"DISM.EXE-Cleanup-Wim" を実行します。</span><span class="sxs-lookup"><span data-stu-id="45978-262">**Resolution:** Launch a PowerShell console as administrator, run "DISM -Cleanup-Wim'".</span></span> <span data-ttu-id="45978-263">Troubled のすべての画像がクリーンアップされます。</span><span class="sxs-lookup"><span data-stu-id="45978-263">This will clean up all troubled images.</span></span> <span data-ttu-id="45978-264">インストール-CcAppliance をもう一度実行するか、bits が自動的にアップグレードされるのを待ちます。</span><span class="sxs-lookup"><span data-stu-id="45978-264">Run Install-CcAppliance again or wait for the bits to automatically upgrade.</span></span>
    
- <span data-ttu-id="45978-265">**問題: HA 環境での第1のクラウドコネクタのアプライアンスの展開に失敗する**</span><span class="sxs-lookup"><span data-stu-id="45978-265">**Issue: Deployment of the first Cloud Connector appliance in an HA environment fails**</span></span>
    
    <span data-ttu-id="45978-266">**解像度:** 実行する手順は、展開の失敗の理由によって異なります。</span><span class="sxs-lookup"><span data-stu-id="45978-266">**Resolution:** The steps you take depend on the reason the deployment failed:</span></span>
    
  - <span data-ttu-id="45978-267">最初の Cloud Connector アプライアンスに障害が発生し、その原因を特定できない場合は、展開が成功するまでもう一度アプライアンスをインストールしてから、他のアプライアンスをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="45978-267">If the first Cloud Connector appliance fails and you cannot determine the reason for the failure, you must install the appliance again until the deployment is successful, and then install the other appliances.</span></span>
    
  - <span data-ttu-id="45978-268">最初のクラウドコネクタのアプライアンスで、外部証明書の問題などの軽微な問題が発生した場合は、アプライアンスを再インストールしなくても問題を解決できる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="45978-268">If the first Cloud Connector appliance fails with a minor issue, such as an external certificate issue, you might be able to fix the problem without re-installing the appliance.</span></span> <span data-ttu-id="45978-269">次に、テナントのリモート PowerShell を使用して、次のように展開を成功としてマークできます。</span><span class="sxs-lookup"><span data-stu-id="45978-269">You can then use tenant remote PowerShell to mark the deployment as successful as follows.</span></span> <span data-ttu-id="45978-270">(最初の展開が成功した場合に、次の手順を使用することもできますが、何らかの理由により、クラウドコネクタが成功として展開を報告できない場合もあります)。</span><span class="sxs-lookup"><span data-stu-id="45978-270">(You can also use the following steps if the first deployment was successful, but, for some reason, Cloud Connector fails to report the deployment as a success.)</span></span>
    
  - <span data-ttu-id="45978-271">最初の Cloud Connector アプライアンスの Id (GUID) を取得するには、CsHybridPSTNAppliance コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="45978-271">To get the Identity (GUID) of the first Cloud Connector appliance, run the Get-CsHybridPSTNAppliance cmdlet.</span></span>
    
  - <span data-ttu-id="45978-272">アプライアンスが正常に展開されたことを示すには、次のように CsCceApplianceDeploymentStatus を実行します。</span><span class="sxs-lookup"><span data-stu-id="45978-272">To mark the appliance as successfully deployed, run the Set-CsCceApplianceDeploymentStatus as follows:</span></span>
    
  ```powershell
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- <span data-ttu-id="45978-273">**問題: ホスト サーバーまたは仮想マシン上で Windows Update を手動で確認してインストールする必要がある。**</span><span class="sxs-lookup"><span data-stu-id="45978-273">**Issue: You need to check for and install Windows updates manually on the host server or virtual machines.**</span></span>
    
   <span data-ttu-id="45978-p133">**解決策:** Skype for Business Cloud Connector エディションが備える自動 OS 更新プログラムを活用することをお勧めします。アプライアンスをオンライン管理に登録して、自動 OS 更新を有効にすると、ホスト サーバーと仮想マシンが自動的に Windows Update を確認して、OS 更新の時間枠設定に従ってインストールします。</span><span class="sxs-lookup"><span data-stu-id="45978-p133">**Resolution:** We recommend that you take advantage of automated OS updates provided by Skype for Business Cloud Connector Edition. After an appliance is registered for online management and auto OS update is enabled, the host server and virtual machines will check and install Windows Updates automatically according to the OS update time window settings.</span></span>
    
   <span data-ttu-id="45978-p134">Windows Update を手動で確認してインストールする必要がある場合は、展開の種類に該当する、このセクションに記載されている手順に従ってください。更新に必要なダウン タイムを最小限にするため、ホスト サーバーと、そこで動作する仮想マシンの両方の更新を計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="45978-p134">If you need to check for and install Windows Updates manually, follow the steps in this section that apply to your type of deployment. You should plan on updating both the host server and the virtual machines running on it at the same time to minimize the amount of down time necessary for the updates.</span></span>
    
   <span data-ttu-id="45978-p135">また、Windows Server Update Services (WSUS) サーバーを使用して、Cloud Connector サーバーに更新プログラムを提供することもできます。Windows Update が自動的にインストール**されない**ように構成してください。</span><span class="sxs-lookup"><span data-stu-id="45978-p135">If you prefer, you can use a Windows Server Update Services (WSUS) server to provide updates to Cloud Connector servers. Just be sure to configure the Windows Update to **not** install automatically.</span></span>
    
   <span data-ttu-id="45978-280">Cloud Connector 展開を手動で更新する方法については、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="45978-280">For information about how to manually update your Cloud Connector deployment, see the following section.</span></span>
    
- <span data-ttu-id="45978-281">**問題: Cloud Connector が新しいビルドに更新された場合、クラウドコネクタコマンドレットは更新されません。**</span><span class="sxs-lookup"><span data-stu-id="45978-281">**Issue: When Cloud Connector updates to a new build, Cloud Connector cmdlets are not updated.**</span></span> <span data-ttu-id="45978-282">これは、自動更新が行われたときに PowerShell ウィンドウを開いたままにした場合に発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="45978-282">This sometimes happens if a PowerShell window is left open when automatic update occurs.</span></span>
    
  <span data-ttu-id="45978-283">**解像度:** 更新されたコマンドレットを読み込むには、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="45978-283">**Resolution:** To load the updated cmdlets, you can do either of the following steps:</span></span>
    
   - <span data-ttu-id="45978-284">クラウドコネクタのアプライアンスで PowerShell を閉じ、PowerShell をもう一度開きます。</span><span class="sxs-lookup"><span data-stu-id="45978-284">Close PowerShell on the Cloud Connector appliance, and then reopen PowerShell.</span></span>
    
     - <span data-ttu-id="45978-285">または、Import-モジュール CloudConnector-Force を実行できます。</span><span class="sxs-lookup"><span data-stu-id="45978-285">Or, you can run Import-Module CloudConnector -Force.</span></span> 
 
-   <span data-ttu-id="45978-286">**問題: "Stop-CsWindowsService" という用語は、コマンドレット、関数、スクリプトファイル、または操作可能なプログラムの名前として認識されません。 "入力-CcUpdate コマンドレットを実行しようとしたときにエラーが発生しました。"**</span><span class="sxs-lookup"><span data-stu-id="45978-286">**Issue: "The term 'Stop-CsWindowsService' is not recognized as the name of a cmdlet, function, script file, or operable program." error when attempting to run Enter-CcUpdate cmdlet.**</span></span>

    <span data-ttu-id="45978-287">**解像度:**$HOME \AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache ファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="45978-287">**Resolution:** Delete the $HOME\AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache file.</span></span>
<span data-ttu-id="45978-288">PowerShell では、このファイルが検出されたモジュールのコマンドレットのキャッシュとして作成されるため、そのたびにすべてのモジュールを再分析する必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="45978-288">PowerShell creates this file as a cache of cmdlets from modules that it finds so that it doesn’t have to re-analyze all the modules each time as that would make things really slow.</span></span> <span data-ttu-id="45978-289">多くの場合、そのキャッシュから読み戻されたときに、誤った結果を示すファイルが破損していました。</span><span class="sxs-lookup"><span data-stu-id="45978-289">Most likely, there was some file corruption that provided misleading results to PowerShell when it was reading back from that cache.</span></span>

-   <span data-ttu-id="45978-290">**問題: "インポート-モジュール CloudConnector" でエラー "Import-モジュールが発生しました。モジュールディレクトリで有効なモジュールファイルが見つからなかったため、指定されたモジュール" CloudConnector "は読み込まれませんでした"**</span><span class="sxs-lookup"><span data-stu-id="45978-290">**Issue: “Import-Module CloudConnector” generates error “Import-Module: The specified module “CloudConnector” was not loaded because no valid module file was found in any module directory”**</span></span>

    <span data-ttu-id="45978-291">**解決策:**</span><span class="sxs-lookup"><span data-stu-id="45978-291">**Resolution:**</span></span>
    - <span data-ttu-id="45978-292">実際に CloudConnector モジュールが c:\Program Files\WindowsPowerShell\Modules の下に存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="45978-292">Validate that indeed the CloudConnector module exists under c:\Program Files\WindowsPowerShell\Modules</span></span>
    
    - <span data-ttu-id="45978-293">この場所に CloudConnector モジュールが存在することを検証した後、モジュールの場所へのパスを格納する PSModulePath 環境変数を変更できます。</span><span class="sxs-lookup"><span data-stu-id="45978-293">After validating that CloudConnector module exists under this location, the PSModulePath environment variable storing the path to the locations of the modules can be changed:</span></span>
    
     <span data-ttu-id="45978-294">a.</span><span class="sxs-lookup"><span data-stu-id="45978-294">a.</span></span> <span data-ttu-id="45978-295">一時的な変更: 管理者として Powershell を起動し、次のコマンドを実行します。 $env:P SModulePath = $env:P SModulePath + ";C:\Program Files\WindowsPowerShell\Modules\"</span><span class="sxs-lookup"><span data-stu-id="45978-295">Temporary change: Start Powershell as an Administrator and run the following command: $env:PSModulePath = $env:PSModulePath + ";C:\Program Files\WindowsPowerShell\Modules\"</span></span>
        
     <span data-ttu-id="45978-296">b.</span><span class="sxs-lookup"><span data-stu-id="45978-296">b.</span></span> <span data-ttu-id="45978-297">永続的な変更を行うには、管理者として PowerShell を起動し、次のコマンドを1つずつ実行します。 $CurrentValue = [環境]:: GetEnvironmentVariable ("PSModulePath", "Machine") SetEnvironmentVariable ("PSModulePath", "コンピューター") ("" $CurrentValue, "")C:\Program Files\WindowsPowerShell\Modules "," Machine ")</span><span class="sxs-lookup"><span data-stu-id="45978-297">For persistent change, Start PowerShell as an Administrator and run the following commands, one by one: $CurrentValue = [Environment]::GetEnvironmentVariable("PSModulePath", "Machine") SetEnvironmentVariable("PSModulePath", $CurrentValue + "; C:\Program Files\WindowsPowerShell\Modules", "Machine")</span></span>

    
## <a name="install-windows-updates-manually"></a><span data-ttu-id="45978-298">Windows 更新プログラムを手動でインストールする</span><span class="sxs-lookup"><span data-stu-id="45978-298">Install Windows updates manually</span></span>

<span data-ttu-id="45978-299">ご利用の環境で自動更新を使用しない場合は、次の手順に従って、Windows Update を手動で確認して適用します。</span><span class="sxs-lookup"><span data-stu-id="45978-299">If you do not want to use automatic updates in your environment, follow these steps to manually check for and apply Windows updates.</span></span> <span data-ttu-id="45978-300">Windows Update の確認とインストールでは、サーバーの再起動が必要となる場合があります。</span><span class="sxs-lookup"><span data-stu-id="45978-300">Checking for and installing Windows updates may require a server restart.</span></span> <span data-ttu-id="45978-301">ホストサーバーが再起動すると、ユーザーはクラウドコネクタを使用して通話の発信や受信を行うことができなくなります。</span><span class="sxs-lookup"><span data-stu-id="45978-301">When a host server is restarting, users will not be able to use Cloud Connector to place or receive calls.</span></span> <span data-ttu-id="45978-302">更新プログラムを手動で確認してインストールすることにより更新の実行時期を制御してから、サービスの中断を回避するために選んだ期間中に必要に応じてコンピューターを再起動できます。</span><span class="sxs-lookup"><span data-stu-id="45978-302">You can manually check for and install updates to control when the updates take place, and then restart the machines as needed during times you choose to avoid disruption of services.</span></span>
  
<span data-ttu-id="45978-303">更新プログラムを手動で確認するには、各ホスト サーバーに接続し、[**コントロール パネル**] を開きます。</span><span class="sxs-lookup"><span data-stu-id="45978-303">To manually check for updates, connect to each host server and open the **Control Panel**.</span></span> <span data-ttu-id="45978-304">[**システムとセキュリティ\>の Windows Update**] を選択し、環境に合わせて更新とサーバーの再起動を管理します。</span><span class="sxs-lookup"><span data-stu-id="45978-304">Select **System and Security \>Windows Update**, and then manage the updates and server restarts as appropriate for your environment.</span></span>
  
- <span data-ttu-id="45978-305">サイトにアプライアンスが 1 台しかない場合は、各仮想マシンに接続し、[**コントロール パネル**] に接続します。</span><span class="sxs-lookup"><span data-stu-id="45978-305">If there is only one appliance in the site, connect to each virtual machine and open the **Control Panel**.</span></span> <span data-ttu-id="45978-306">[**システムとセキュリティ\>の Windows Update**] を選び、必要に応じて、更新プログラムとサーバーの再起動を構成します。</span><span class="sxs-lookup"><span data-stu-id="45978-306">Select **System and Security \>Windows Update**, and then configure the updates and server restarts as appropriate.</span></span>
    
- <span data-ttu-id="45978-p143">サイトに複数のアプライアンスがある場合、更新中、更新して再起動するインスタンスにはアクセスできません。更新が完了して、すべての仮想マシンと、仮想マシン上のすべての Skype for Business サービスが開始するまで、展開内の別のインスタンスに接続することになります。サービス中断の可能性を避けるため、更新プログラム適用中にインスタンスから HA を削除し、完了してから復元することができます。その手順は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="45978-p143">If there are more than one appliance in the site, the instance being updated and restarted cannot be accessed by users during the updates. Users will connect to other instances in the deployment until all virtual machines and all Skype for Business services start on the virtual machines after the updates are completed. To avoid any potential disruption to service, you can remove the instance from HA while you apply the updates, and then restore it when complete. To do so:</span></span>
    
1. <span data-ttu-id="45978-311">ホスト サーバーごとに、管理者として PowerShell コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="45978-311">On each host server, open a PowerShell console as administrator.</span></span>
    
2. <span data-ttu-id="45978-312">次のコマンドレットを使用して、HA からインスタンスを削除します。</span><span class="sxs-lookup"><span data-stu-id="45978-312">Remove the instance from HA with the following cmdlet:</span></span>
    
   ```powershell
   Enter-CcUpdate
   ```

3. 
    
    <span data-ttu-id="45978-313">単一インスタンスの手順に従い、更新を手動で適用し仮想マシンを再起動します。</span><span class="sxs-lookup"><span data-stu-id="45978-313">Follow the steps for a single instance to manually apply the updates and restart the virtual machine.</span></span>
    
4. <span data-ttu-id="45978-314">次のコマンドレットを使用して、HA にインスタンスを戻します。</span><span class="sxs-lookup"><span data-stu-id="45978-314">Set the instance back to HA with the following cmdlet:</span></span>
    
   ```powershell
   Exit-CcUpdate
   ```

<span data-ttu-id="45978-315">マルチサイト展開の場合は、展開内の各サイトに対して 1 つのサイトの手順を実行し、一度に 1 つのサイトに対して更新プログラムを適用します。</span><span class="sxs-lookup"><span data-stu-id="45978-315">For multi-site deployments, follow the steps for a single site for each site in the deployment, applying updates to one site at a time.</span></span>
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a><span data-ttu-id="45978-316">クラウドコネクタホストコンピューターにウイルス対策ソフトウェアをインストールするときのヒント</span><span class="sxs-lookup"><span data-stu-id="45978-316">Tips when installing anti-virus software on the Cloud Connector host machine</span></span>

<span data-ttu-id="45978-317">クラウドコネクタホストコンピューターにウイルス対策ソフトウェアをインストールする必要がある場合は、次の除外を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="45978-317">If you need to install anti-virus software on the Cloud Connector host machine, you need to add the following exclusions:</span></span>
  
- <span data-ttu-id="45978-318">各マシンのローカルアプライアンスディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="45978-318">Local Appliance Directory on each machine.</span></span>
    
- <span data-ttu-id="45978-319">各コンピューター上のリモートサイトディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="45978-319">Remote Site Directory on each machine.</span></span>
    
- <span data-ttu-id="45978-320">コンピューター上のローカルサイトディレクトリは共有サイトルートフォルダーをホストします。</span><span class="sxs-lookup"><span data-stu-id="45978-320">Local Site Directory on the machine hosts the shared site root folder.</span></span>
    
- <span data-ttu-id="45978-321">%ProgramFiles%\Skype for Business Cloud Connector エディション</span><span class="sxs-lookup"><span data-stu-id="45978-321">%ProgramFiles%\Skype for Business Cloud Connector Edition</span></span>
    
- <span data-ttu-id="45978-322">%ALLUSERSPROFILE%\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="45978-322">%ALLUSERSPROFILE%\CloudConnector</span></span>
    
- <span data-ttu-id="45978-323">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="45978-323">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span></span>
    
- <span data-ttu-id="45978-324">ManagementService のプロセスを実行します。</span><span class="sxs-lookup"><span data-stu-id="45978-324">The process Microsoft.Rtc.CCE.ManagementService.exe.</span></span>
