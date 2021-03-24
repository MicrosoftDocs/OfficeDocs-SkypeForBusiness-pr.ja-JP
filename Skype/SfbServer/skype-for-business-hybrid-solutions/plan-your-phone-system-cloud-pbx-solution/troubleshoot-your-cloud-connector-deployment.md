---
title: クラウド コネクタの展開のトラブルシューティング
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
description: クラウド コネクタ エディションの展開のトラブルシューティングを行います。
ms.openlocfilehash: 9da10f1b3e8dd800e57b46f6a56eb6a82c29e22c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094825"
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a><span data-ttu-id="318f9-103">クラウド コネクタの展開のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="318f9-103">Troubleshoot your Cloud Connector deployment</span></span>

> [!Important]
> <span data-ttu-id="318f9-104">Cloud Connector Edition は、Skype for Business Online と共に 2021 年 7 月 31 日に廃止されます。</span><span class="sxs-lookup"><span data-stu-id="318f9-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="318f9-105">組織が Teams にアップグレードしたら、直接ルーティングを使用してオンプレミスのテレフォニー ネットワークを Teams に接続する方法 [について説明します](/MicrosoftTeams/direct-routing-landing-page)。</span><span class="sxs-lookup"><span data-stu-id="318f9-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>
 
<span data-ttu-id="318f9-106">クラウド コネクタ エディションの展開のトラブルシューティングを行います。</span><span class="sxs-lookup"><span data-stu-id="318f9-106">Troubleshoot your Cloud Connector Edition deployment.</span></span>
  
<span data-ttu-id="318f9-107">このトピックでは、Cloud Connector Edition 展開に関する一般的な問題に対する解決策について説明します。</span><span class="sxs-lookup"><span data-stu-id="318f9-107">This topic describes solutions to common issues with Cloud Connector Edition deployments.</span></span> <span data-ttu-id="318f9-108">公衆交換電話網 (PSTN) との間で通話に問題が発生している場合は、このトピックで説明するソリューションに従って調査できます。</span><span class="sxs-lookup"><span data-stu-id="318f9-108">If you are experiencing issues with calls to and from the Public Switched Telephone Network (PSTN), you can investigate by following the solutions described in this topic.</span></span>
  
<span data-ttu-id="318f9-109">クラウド コネクタは、いくつかの問題を自動的に解決するための組み込みのメカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="318f9-109">Cloud Connector provides built-in mechanisms for automatically resolving some issues.</span></span> <span data-ttu-id="318f9-110">自動検出プロセスは、クラウド コネクタ アプライアンスに関する潜在的な問題を探し、可能であれば、管理者の介入を必要とせずに、それらの問題を解決するための修正措置を実行します。</span><span class="sxs-lookup"><span data-stu-id="318f9-110">An automatic detection process looks for potential issues with the Cloud Connector appliances, and, if possible, takes corrective action to resolve those issues without the need for administrator intervention.</span></span> <span data-ttu-id="318f9-111">検出プロセスは次のように動作します。</span><span class="sxs-lookup"><span data-stu-id="318f9-111">The detection process works as follows:</span></span>
  
- <span data-ttu-id="318f9-112">**検出シーケンス:** クラウド コネクタ管理サービスは、アプライアンスがダウンしたかどうかを検出するために 60 秒ごとにプロセスを実行します。</span><span class="sxs-lookup"><span data-stu-id="318f9-112">**Detection sequence:** The Cloud Connector Management service runs a process every 60 seconds for detecting whether an appliance is down.</span></span> <span data-ttu-id="318f9-113">クラウド コネクタ バージョン 2.0 以降では、検出プロセスは Skype for Business Corpnet スイッチを使用して、クラウド コネクタ コンピューターへの PowerShell 接続を行います。2.0 より前のバージョンの場合、検出プロセスは Cloud Connector 管理スイッチを使用します。</span><span class="sxs-lookup"><span data-stu-id="318f9-113">In Cloud Connector version 2.0 and later, the detection process uses the Skype for Business Corpnet switch for making PowerShell connections to the Cloud Connector machines; for versions previous to 2.0, the detection process uses the Cloud Connector management switch.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="318f9-114">自動回復を成功するには、ホスト ネットワーク スイッチを使用してホストと仮想マシンの間にネットワーク接続が必要です。</span><span class="sxs-lookup"><span data-stu-id="318f9-114">For automatic recovery to succeed, there must be network connectivity between the host and virtual machines over the host network switch.</span></span> <span data-ttu-id="318f9-115">ネットワーク接続を確認して、自動検出と回復が成功する可能性を確認してください。</span><span class="sxs-lookup"><span data-stu-id="318f9-115">Be sure to check network connectivity to ensure that automatic detection and recovery can succeed.</span></span> 
  
- <span data-ttu-id="318f9-116">**監視:** クラウド コネクタ バージョン 2.0 以降では、次のサービスが監視されます。</span><span class="sxs-lookup"><span data-stu-id="318f9-116">**Monitoring:** The following services are monitored in Cloud Connector version 2.0 and later:</span></span>
    
  - <span data-ttu-id="318f9-117">仮想マシンがクラウド コネクタ企業またはインターネット仮想スイッチに接続されていない</span><span class="sxs-lookup"><span data-stu-id="318f9-117">Virtual Machines are not connected to the Cloud Connector Corporate or Internet virtual switches</span></span>
    
  - <span data-ttu-id="318f9-118">仮想マシンが保存済みまたは停止中の状態</span><span class="sxs-lookup"><span data-stu-id="318f9-118">Virtual Machines are in a saved or stopped status</span></span>
    
  - <span data-ttu-id="318f9-119">サーバーの全体管理サービス: REPLICA、MASTER</span><span class="sxs-lookup"><span data-stu-id="318f9-119">Central Management Server services: REPLICA, MASTER</span></span>
    
  - <span data-ttu-id="318f9-120">仲介サーバー サービス: REPLICA、RTCSRV、MEDSVC</span><span class="sxs-lookup"><span data-stu-id="318f9-120">Mediation Server services: REPLICA, RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="318f9-121">エッジ サーバー サービス: REPLICA、RTCSRV、RTCDATAPROXY、RTCMRAUTH、RTCMEDIARELAY</span><span class="sxs-lookup"><span data-stu-id="318f9-121">Edge Server services: REPLICA, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY</span></span>
    
  - <span data-ttu-id="318f9-122">エッジ サーバー上の CS RTCSRV、仲介サーバー上の CS RTCMEDSRV に対して受信ファイアウォールルールが無効になっている</span><span class="sxs-lookup"><span data-stu-id="318f9-122">Inbound firewall rules are disabled for CS RTCSRV on Edge server, CS RTCMEDSRV on Mediation server</span></span>
    
    <span data-ttu-id="318f9-123">クラウド コネクタ バージョン 1.4.2 では、次のサービスだけが監視されます。</span><span class="sxs-lookup"><span data-stu-id="318f9-123">In Cloud Connector version 1.4.2, only the following services are monitored:</span></span>
    
  - <span data-ttu-id="318f9-124">仲介サーバー サービス: RTCSRV および MEDSVC</span><span class="sxs-lookup"><span data-stu-id="318f9-124">Mediation Server services: RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="318f9-125">エッジ サーバー サービス: RTCSRV</span><span class="sxs-lookup"><span data-stu-id="318f9-125">Edge Server service: RTCSRV</span></span>
    
- <span data-ttu-id="318f9-126">**回復プロセス:** 監視対象のサービスがダウンしている場合、アプライアンスはマークダウンされ、すべての問題を解決するまでサービスは停止され、手動でマークされます。</span><span class="sxs-lookup"><span data-stu-id="318f9-126">**Recovery process:** If any monitored services are down, an appliance is marked down, and services are stopped and marked manual until all issues can be resolved.</span></span> <span data-ttu-id="318f9-127">これにより、呼び出しが失敗する可能性があるアプライアンスへのルーティングが防止されます。</span><span class="sxs-lookup"><span data-stu-id="318f9-127">This will prevent calls from routing to an appliance that may cause call failures.</span></span>
    
    <span data-ttu-id="318f9-128">クラウド コネクタ管理サービスは、次のように自動回復を再試行します。</span><span class="sxs-lookup"><span data-stu-id="318f9-128">The Cloud Connector Management service will retry automatic recovery as follows</span></span>
    
  - <span data-ttu-id="318f9-129">最初の再試行間隔は 10 秒ごとに、最大間隔は 1 時間です。</span><span class="sxs-lookup"><span data-stu-id="318f9-129">The initial retry interval is every ten seconds with a maximum interval time of one hour.</span></span>
    
  - <span data-ttu-id="318f9-130">最初の 3 回の回復試行では、間隔は 10 秒です。</span><span class="sxs-lookup"><span data-stu-id="318f9-130">For the first three recovery attempts, the interval time is 10 seconds.</span></span> <span data-ttu-id="318f9-131">4 回目の再試行から開始すると、間隔時間は前の間隔時間の 2 倍増加します。</span><span class="sxs-lookup"><span data-stu-id="318f9-131">Starting from the fourth retry, the interval time increases by two times the previous interval time.</span></span> <span data-ttu-id="318f9-132">たとえば、4 回目の再試行は 20 秒、5 回目は 40 秒で発生します。</span><span class="sxs-lookup"><span data-stu-id="318f9-132">For example, the fourth retry will occur in 20 seconds, the fifth in 40 seconds, and so on.</span></span> 
    
  - <span data-ttu-id="318f9-133">1 時間の最大間隔に達すると、再試行は 1 時間に 1 回続きます。</span><span class="sxs-lookup"><span data-stu-id="318f9-133">When the maximum interval time of one hour is reached, retries will continue once per hour.</span></span>
    
  - <span data-ttu-id="318f9-134">回復が成功すると、間隔と再試行回数が初期値に設定されます。</span><span class="sxs-lookup"><span data-stu-id="318f9-134">When recovery is successful, the interval and retry counts are set to their initial values.</span></span>
    
  - <span data-ttu-id="318f9-135">管理サービスが再起動された場合、間隔と再試行回数は初期値にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="318f9-135">If the Management service is restarted, the interval and retry counts are reset to their initial values.</span></span>
    
## <a name="troubleshooting"></a><span data-ttu-id="318f9-136">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="318f9-136">Troubleshooting</span></span>

<span data-ttu-id="318f9-137">一般的に発生する問題の解決策を次に示します。</span><span class="sxs-lookup"><span data-stu-id="318f9-137">Following are solutions to commonly encountered issues:</span></span>
  
- <span data-ttu-id="318f9-138">**問題: 展開スクリプトの実行中に展開が失敗するか、応答を停止します。各 VM にログオンした後、管理/内部/外部 NIC の IP アドレスが見つからないか、正しくありません。**</span><span class="sxs-lookup"><span data-stu-id="318f9-138">**Issue: Deployment fails or stops responding when running the deployment scripts. After logging on to each VM, the IP address is missing or incorrect for the Management/Internal/External NIC.**</span></span>
    
    <span data-ttu-id="318f9-139">**解決策:** この問題は自動的に解決できません。</span><span class="sxs-lookup"><span data-stu-id="318f9-139">**Resolution:** This issue cannot be resolved automatically.</span></span> <span data-ttu-id="318f9-140">NIC は、実行中は VM に追加できません。</span><span class="sxs-lookup"><span data-stu-id="318f9-140">NICs cannot be added to VMs while they are running.</span></span> <span data-ttu-id="318f9-141">Hyper-v マネージャーでこれらの VM をシャットダウンして削除し、次のコマンドレットを実行してください。</span><span class="sxs-lookup"><span data-stu-id="318f9-141">Please shut down and remove these VMs in hyper-v manager, then run the following cmdlets:</span></span>
    
  ```powershell
  Uninstall-CcAppliance
  ```

  ```powershell
  Install-CcAppliance
  ```

- 
    
    <span data-ttu-id="318f9-142">**問題: Active Directory Server とフォレストがインストールされた後、CMS Server または仲介サーバーがドメインに正しく参加しなかった。**</span><span class="sxs-lookup"><span data-stu-id="318f9-142">**Issue: After the Active Directory Server and forest are installed, the CMS Server and/or Mediation Server did not join the domain correctly.**</span></span>
    
    <span data-ttu-id="318f9-143">**解決策:** この問題を解決するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="318f9-143">**Resolution:** To resolve this issue, take the following steps:</span></span>
    
  - <span data-ttu-id="318f9-144">Active Directory Server にログオンし、ドメインが正しく作成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="318f9-144">Log on to the Active Directory Server and verify that the domain was created correctly.</span></span>
    
  - <span data-ttu-id="318f9-145">CMS/Mediation Server にログオンし、corpnet NIC で有効な IP アドレスが割り当てられているか、有効な静的 IP と DNS が AD サーバーの IP アドレスとして構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="318f9-145">Log on to the CMS/Mediation Server and verify that on the corpnet NIC a valid IP address is assigned, and that valid static IP and DNS is configured as the AD server's IP address.</span></span>
    
  - <span data-ttu-id="318f9-146">CMS/仲介サーバーにログオンし、コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="318f9-146">Log on to the CMS/Mediation Server, and open a command prompt.</span></span> <span data-ttu-id="318f9-147">Active Directory Server の FQDN と IP アドレスに ping を実行できます。</span><span class="sxs-lookup"><span data-stu-id="318f9-147">Make sure you can ping the FQDN and IP address of the Active Directory Server.</span></span> <span data-ttu-id="318f9-148">できない場合は、IP アドレスの競合が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="318f9-148">If you cannot, there may be an IP address conflict.</span></span> <span data-ttu-id="318f9-149">Active Directory に新しい IP を割り当て、CMS/仲介サーバーで DNS を更新してください。</span><span class="sxs-lookup"><span data-stu-id="318f9-149">Please try to assign a new IP for Active Directory and update DNS on the CMS/Mediation server accordingly.</span></span>
    
- <span data-ttu-id="318f9-150">**問題: 次のエラー メッセージが表示されます。"Remove-VMSwitch : 仮想イーサネット スイッチの削除中に失敗しました。仮想スイッチ 'Cloud Connector Management Switch' は、仮想マシンの実行によって使用されるか、または子プールに割り当てられているため、削除できません。**</span><span class="sxs-lookup"><span data-stu-id="318f9-150">**Issue: You receive the following error message, "Remove-VMSwitch : Failed while removing virtual Ethernet switch. The virtual switch 'Cloud Connector Management Switch' cannot be deleted because it is being used by running virtual machines or assigned to child pools."**</span></span>
    
    <span data-ttu-id="318f9-151">**解決策:** 展開後に "クラウド コネクタ管理スイッチ" が削除されません。</span><span class="sxs-lookup"><span data-stu-id="318f9-151">**Resolution:** The "Cloud Connector Management Switch" was not deleted after the deployment.</span></span> <span data-ttu-id="318f9-152">このエラーが発生した場合は、Hyper-v マネージャーに移動して、まだ仮想マシンがまだ接続されていないか確認してください。</span><span class="sxs-lookup"><span data-stu-id="318f9-152">If you hit this error, please go to Hyper-v manager and verify that there is not still a virtual machine still connected to it.</span></span> <span data-ttu-id="318f9-153">仮想マシンがまだ接続されている場合は、それらを切断して管理スイッチを削除します。</span><span class="sxs-lookup"><span data-stu-id="318f9-153">If there are virtual machines still connected, disconnect them and delete the management switch.</span></span> <span data-ttu-id="318f9-154">管理スイッチを削除できない場合は、ホスト サーバーを再起動し、もう一度やり直してください。</span><span class="sxs-lookup"><span data-stu-id="318f9-154">If the management switch still cannot be deleted, restart the host server and try again.</span></span>
    
- <span data-ttu-id="318f9-155">**問題: 次のエラー メッセージが表示されます。"Service RTCMRAUTH の開始に失敗しました。サービスが無効にされていないか確認してください。**</span><span class="sxs-lookup"><span data-stu-id="318f9-155">**Issue: You receive the following error message, "Service RTCMRAUTH failed to start. Check to make sure the service is not disabled."**</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="318f9-156">この問題は、1.4.2 より前の Cloud Connector バージョンにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="318f9-156">This issue only applies to Cloud Connector versions earlier than 1.4.2.</span></span> 
  
    <span data-ttu-id="318f9-157">このフロントエンド サーバーが以前に (コンピューターのフェール オーバーを使用して) 失敗したため、開始に失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="318f9-157">The failure to start could also be because this Front End server was previously failed over (using computer fail over).</span></span> <span data-ttu-id="318f9-158">その場合は、(コンピューターのフェール バックを使用して) フェール バックを呼び出してください。</span><span class="sxs-lookup"><span data-stu-id="318f9-158">If that's the case, please invoke fail back (using computer fail back).</span></span>
    
    <span data-ttu-id="318f9-159">**解決策:** この問題は、ルート CA 証明書または中間 CA 証明書がエッジ サーバーによって信頼されていない場合にエッジ サーバーで発生します。</span><span class="sxs-lookup"><span data-stu-id="318f9-159">**Resolution:** This issue happens on an Edge Server when the root CA certificate or intermediate CA certificate is not trusted by the Edge Server.</span></span> <span data-ttu-id="318f9-160">外部証明書をインポートできますが、証明書チェーンが壊れている場合でも。</span><span class="sxs-lookup"><span data-stu-id="318f9-160">Even if the external certificate can be imported but the certificate chain is broken.</span></span> <span data-ttu-id="318f9-161">この条件では、RTCMRAUTH サービスまたは RTCSRV サービスを開始できない。</span><span class="sxs-lookup"><span data-stu-id="318f9-161">Under this condition, the RTCMRAUTH and/or RTCSRV service can not start.</span></span>
    
    <span data-ttu-id="318f9-162">外部証明書のルート CA 証明書とすべての中間 CA 証明書を手動でエッジ サーバーにインポートし、エッジ サーバーを再起動してください。</span><span class="sxs-lookup"><span data-stu-id="318f9-162">Please import the root CA certificate and all intermediate CA certificates of your external certificate manually into the Edge Server and then restart the Edge Server.</span></span> <span data-ttu-id="318f9-163">エッジ サーバーで RTCMRAUTH サービスと RTCSRV サービスが開始されたのを確認した後、ホスト サーバーに戻り、管理者として PowerShell コンソールを起動し、次のコマンドレットを実行して新しい展開に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="318f9-163">After you see the RTCMRAUTH and RTCSRV services started on the Edge Server, go back to your host server, launch a PowerShell console as administrator, and run following cmdlet to switch to the new deployment:</span></span>
    
  ```powershell
  Switch-CcVersion
  ```

- 
    
    <span data-ttu-id="318f9-164">**問題: Windows 更新プログラムが適用されるとホスト サーバーが再起動され、サーバーによってサービスされた呼び出しが失敗しています。**</span><span class="sxs-lookup"><span data-stu-id="318f9-164">**Issue: The host server was restarted when Windows updates were applied, and calls serviced by the server are failing.**</span></span>
    
    <span data-ttu-id="318f9-165">**解決策:** 高可用性環境を展開した場合、Microsoft は、Windows 更新プログラムを手動で確認してインストールするときに、1 つのホスト マシン (展開インスタンス) を現在のトポロジに移動または削除するためのコマンドレットを提供します。</span><span class="sxs-lookup"><span data-stu-id="318f9-165">**Resolution:** If you deployed a high availability environment, Microsoft provides a cmdlet to help move one host machine (deployment instance) into or out of the current topology when you check and install Windows update manually.</span></span> <span data-ttu-id="318f9-166">これを実現するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="318f9-166">Use the following steps to accomplish this:</span></span>
    
1. <span data-ttu-id="318f9-167">ホスト サーバーで、管理者として PowerShell コンソールを起動し、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="318f9-167">On the host server, start a PowerShell console as administrator, then run:</span></span>
    
   ```powershell
   Enter-CcUpdate
   ```

2. <span data-ttu-id="318f9-168">更新プログラムを確認し、利用可能な更新プログラムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="318f9-168">Check for updates and install any that are available.</span></span>
    
3. <span data-ttu-id="318f9-169">PowerShell コンソールで、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="318f9-169">In the PowerShell console, run the following cmdlet:</span></span>
    
   ```powershell
   Exit-CcUpdate
   ```

- 
    
    <span data-ttu-id="318f9-170">**問題: PSTN 番号を使用して Skype for Business クライアントから通話が行われた場合、別の PSTN 番号を招待して電話会議にエスカレートすることはできません。**</span><span class="sxs-lookup"><span data-stu-id="318f9-170">**Issue: When a call is made from a Skype for Business client using a PSTN number, the call cannot be escalated to a conference by inviting another PSTN number.**</span></span>
    
    <span data-ttu-id="318f9-171">**解決策:** この問題を解決するには [、「Configure online hybrid Mediation Server Settings」を参照してください](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer)。</span><span class="sxs-lookup"><span data-stu-id="318f9-171">**Resolution:** To resolve this issue, see [Configure online hybrid Mediation Server Settings](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).</span></span>
    
- <span data-ttu-id="318f9-172">**問題: Active Directory サーバーをインストールするときに、Windows Update に関する警告メッセージが表示されます。"Windows 自動更新が有効になっていません。新しくインストールされた役割または機能が自動的に更新されていることを確認するには、Windows Update を有効にします。**</span><span class="sxs-lookup"><span data-stu-id="318f9-172">**Issue: A warning message is displayed about Windows Update when you are installing Active Directory server - "Windows automatic updating is not enabled. To ensure that your newly-installed role or feature is automatically updated, turn on Windows Update."**</span></span>
    
    <span data-ttu-id="318f9-173">**解決策:** Skype for Business テナント管理者資格情報を使用してテナント リモート PowerShell セッションを起動し、次のコマンドレットを実行してサイトの _EnableAutoUpdate_ 構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="318f9-173">**Resolution:** Launch a Tenant Remote PowerShell session using Skype for Business tenant admin credentials, then run the following cmdlet to check the _EnableAutoUpdate_ configuration of your site:</span></span>
    
  ```powershell
  Get-CsHybridPSTNSite
  ```

    <span data-ttu-id="318f9-174">_EnableAutoUpdate_ が **True** に設定されている場合は、CCEManagement サービスが仮想マシンとホスト サーバーの両方の Windows 更新プログラムのダウンロードとインストールを処理しますので、この警告メッセージを無視しても問題ない場合があります。</span><span class="sxs-lookup"><span data-stu-id="318f9-174">If  _EnableAutoUpdate_ is set to **True**, you can safely ignore this warning message because the CCEManagement service will handle downloading and installing Windows updates for both virtual machines and the host server.</span></span> <span data-ttu-id="318f9-175">_EnableAutoUpdate が False_ に設定されている **場合** は、次のコマンドレットを実行して True に設定 **します**。</span><span class="sxs-lookup"><span data-stu-id="318f9-175">If  _EnableAutoUpdate_ is set to **False**, run following cmdlet to set it to **True**.</span></span>
    
  ```powershell
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    <span data-ttu-id="318f9-176">または、更新プログラムを手動で確認してインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="318f9-176">Alternatively, you can manually check for and install updates.</span></span> <span data-ttu-id="318f9-177">次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="318f9-177">See the next section.</span></span>
    
- <span data-ttu-id="318f9-178">**問題: 現在の入力/構成、または既存のアプライアンスとの競合により、アプライアンスを登録できないというエラー メッセージが \<SiteName\> \<ApplianceName\> \<Mediation Server FQDN\> \<Mediation Server IP Address\> 表示されます。競合アプライアンスを削除するか、入力/構成情報を更新してから、もう一度登録します。' を実行すると、Register-CcApplianceアプライアンスをオンラインに登録できます。**</span><span class="sxs-lookup"><span data-stu-id="318f9-178">**Issue: You receive an error message: Cannot register appliance because your current input/configuration \<SiteName\> or \<ApplianceName\> or \<Mediation Server FQDN\> or \<Mediation Server IP Address\> conflicts with existing appliance(s). Remove conflict appliance or update your input/configuration information then register again. ' when run Register-CcAppliance to register current appliance to online.**</span></span>
    
    <span data-ttu-id="318f9-179">**解決策:** の値は \<ApplianceName\> 、 \<Mediation Server FQDN\> 一 \<Mediation Server IP Address\> 意で、1 つのアプライアンス登録にのみ使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="318f9-179">**Resolution:** Values for the \<ApplianceName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> must be unique and only used for one appliance registration.</span></span> <span data-ttu-id="318f9-180">既定では、 \<ApplianceName\> ホスト名から来ます。</span><span class="sxs-lookup"><span data-stu-id="318f9-180">By default, \<ApplianceName\> comes from the host name.</span></span> <span data-ttu-id="318f9-181">\<Mediation Server FQDN\> 構成 \<Mediation Server IP Address\> ini ファイルで定義されます。</span><span class="sxs-lookup"><span data-stu-id="318f9-181">\<Mediation Server FQDN\> and \<Mediation Server IP Address\> defined in configuration ini file.</span></span>
    
    <span data-ttu-id="318f9-182">たとえば、SiteName=MySite に登録する (ApplianceName= MyserverNew、仲介サーバー FQDN=ms.contoso.com、仲介サーバー IP アドレス=10.10.10.10) を使用しますが、登録アプライアンス (ApplianceName= Myserver、Mediation Server FQDN=ms.contoso.com、仲介サーバー IP アドレス=10.10.10.10)がある場合、競合が発生します。</span><span class="sxs-lookup"><span data-stu-id="318f9-182">For example, using (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) to register to SiteName=MySite, but if there is a registered appliance (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10), you will have the conflict.</span></span>
    
    <span data-ttu-id="318f9-183">まず、[アプライアンスルート ディレクトリ] セクションCloudConnector.iniファイルを確認してください。</span><span class="sxs-lookup"><span data-stu-id="318f9-183">First, please check your CloudConnector.ini file in ApplianceRoot directory section.</span></span> <span data-ttu-id="318f9-184">ファイル内の \<SiteName\> 、 \<Mediation Server FQDN\> および \<Mediation Server IP Address\> 値を取得します。</span><span class="sxs-lookup"><span data-stu-id="318f9-184">You will get \<SiteName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> values in the file.</span></span> <span data-ttu-id="318f9-185">\<ApplianceName\> はホスト サーバー名です。</span><span class="sxs-lookup"><span data-stu-id="318f9-185">\<ApplianceName\> is your host server name.</span></span>
    
    <span data-ttu-id="318f9-186">次に、Skype for Business テナント管理者資格情報を使用してテナント リモート PowerShell を起動し、次のコマンドレットを実行して登録済みのアプライアンスを確認します。</span><span class="sxs-lookup"><span data-stu-id="318f9-186">Second, Launch Tenant Remote PowerShell using your Skype for Business tenant admin credentials, then run the following cmdlet to check the registered appliance(s).</span></span>
    
  ```powershell
  Get-CsHybridPSTNAppliance
  ```

    <span data-ttu-id="318f9-187">競合を特定した後、CloudConnector.ini ファイルを登録されているアプライアンスに一致する情報で更新するか、既存のアプライアンスを登録解除して競合を解決できます。</span><span class="sxs-lookup"><span data-stu-id="318f9-187">After identifying any conflicts, you can either update your CloudConnector.ini file with information that matches the registered appliance, or unregister the existing appliance to resolve the conflicts.</span></span>
    
  ```powershell
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
- <span data-ttu-id="318f9-188">**問題: ホストGet-CcRunningVersion展開されたアプライアンスが実行されている場合、このコマンドレットは空の値を返します。**</span><span class="sxs-lookup"><span data-stu-id="318f9-188">**Issue: The Get-CcRunningVersion cmdlet returns an empty value if there is a deployed appliance running on the host.**</span></span>
    
  <span data-ttu-id="318f9-189">**解決策:** これは、1.3.4 または 1.3.8 から 1.4.1 にアップグレードするときに発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="318f9-189">**Resolution:** This can happen when you upgrade from 1.3.4 or 1.3.8 to 1.4.1.</span></span> <span data-ttu-id="318f9-190">バージョン 1.4.1 を .msi でインストールした後、他のコマンドレットを実行する前 `Register-CcAppliance` に実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="318f9-190">After you install version 1.4.1 with the .msi, you must run `Register-CcAppliance` before you run any other cmdlet.</span></span> <span data-ttu-id="318f9-191">`Register-CcAppliance` %UserProfile%\CloudConnector module.ini%ProgramData%\CloudConnector に移行します。</span><span class="sxs-lookup"><span data-stu-id="318f9-191">`Register-CcAppliance` will migrate the module.ini file from %UserProfile%\CloudConnector to %ProgramData%\CloudConnector.</span></span> <span data-ttu-id="318f9-192">見つからない場合は、%ProgramData%\CloudConnector フォルダーに新しい module.ini が作成され、1.3.4 または 1.3.8 の実行中/バックアップ バージョン情報が置き換されます。</span><span class="sxs-lookup"><span data-stu-id="318f9-192">If you missed it, a new module.ini will be created in %ProgramData%\CloudConnector folder and replace the running/backup version information for 1.3.4 or 1.3.8.</span></span>
    
  <span data-ttu-id="318f9-193">module.ini %UserProfile%\CloudConnector および %ProgramData%\CloudConnector フォルダー内のファイルを比較します。</span><span class="sxs-lookup"><span data-stu-id="318f9-193">Compare module.ini files in %UserProfile%\CloudConnector and %ProgramData%\CloudConnector folder.</span></span> <span data-ttu-id="318f9-194">違いがある場合は、%ProgramData%\CloudConnector module.iniファイルを削除して再実行します  `Register-CcAppliance` 。</span><span class="sxs-lookup"><span data-stu-id="318f9-194">If there are differences, delete the module.ini file in %ProgramData%\CloudConnector and rerun  `Register-CcAppliance`.</span></span> <span data-ttu-id="318f9-195">また、ファイルを手動で正しい実行バージョンとバックアップ バージョンに変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="318f9-195">You could also modify the file manually to the correct running and backup version.</span></span>
    
- <span data-ttu-id="318f9-196">**問題: Switch-CcVersion コマンドレットを実行して、現在のスクリプトバージョンとは異なる古いバージョンに切り替えてから、この古いバージョンに対する高可用性のサポートはありません。**</span><span class="sxs-lookup"><span data-stu-id="318f9-196">**Issue: After you run the Switch-CcVersion cmdlet to switch to an old version which is different from current script version, there is no High Availability support for this old version.**</span></span>
    
    <span data-ttu-id="318f9-197">**解決策:** たとえば、1.4.1 から 1.4.2 にアップグレードしたとします。</span><span class="sxs-lookup"><span data-stu-id="318f9-197">**Resolution:** For example, you have upgraded from 1.4.1 to 1.4.2.</span></span> <span data-ttu-id="318f9-198">現在のスクリプト バージョン (実行によって決定できます)と、実行中のバージョン (実行によって決定できるバージョン) は、両方とも `Get-CcVersion`  `Get-CcRunningVersion` 1.4.2 です。</span><span class="sxs-lookup"><span data-stu-id="318f9-198">Your current script version, which can be determined by running `Get-CcVersion`, and your running version, which can be determined by running  `Get-CcRunningVersion` are both 1.4.2.</span></span> <span data-ttu-id="318f9-199">この時点で、実行中のバージョンを 1.4.1 に切り替える場合、この古いバージョンに対する高可用性 `Switch-CcVersion` のサポートはありません。</span><span class="sxs-lookup"><span data-stu-id="318f9-199">At this time, if you run `Switch-CcVersion` to switch the running version back to 1.4.1, then there will be no High Availability support for this old version.</span></span>
    
    <span data-ttu-id="318f9-200">完全な高可用性のサポートを受け取る場合は、1.4.2 に切り替えて、実行中のバージョンとスクリプトのバージョンが同じにしてください。</span><span class="sxs-lookup"><span data-stu-id="318f9-200">To get full High Availability support, please switch back to 1.4.2, so the running version and script version are the same.</span></span> <span data-ttu-id="318f9-201">1.4.2 の展開で問題が発生している場合は、できるだけ早くアンインストールして再インストールしてください。</span><span class="sxs-lookup"><span data-stu-id="318f9-201">If you are experiencing problems with your 1.4.2 deployment, please uninstall and reinstall it as soon as possible.</span></span>
    
- <span data-ttu-id="318f9-202">**問題: サーバーの全体管理ストア、仲介サーバー、およびエッジ サーバーに発行された証明機関の証明書または内部証明書が有効期限が近いか、侵害されています。**</span><span class="sxs-lookup"><span data-stu-id="318f9-202">**Issue: Certificate authority certificates or internal certificates issued to Central Management Store, Mediation Server, and Edge Server are near expiration or are compromised.**</span></span>
    
    <span data-ttu-id="318f9-203">**解決策:** Skype for Business 証明機関の証明書は 5 年間有効です。</span><span class="sxs-lookup"><span data-stu-id="318f9-203">**Resolution:** Skype for Business certification authority certificates are valid for five years.</span></span> <span data-ttu-id="318f9-204">中央管理ストア、仲介サーバー、エッジ サーバーに発行された内部証明書は、2 年間有効です。</span><span class="sxs-lookup"><span data-stu-id="318f9-204">Internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="318f9-205">クラウド コネクタ バージョン 2.0 以降では、Renew-CcServerCertificate コマンドレットが Update-CcServerCertificate に変更され、Renew-CcCACertificate コマンドレットが Update-CcCACertificate に変更されました。</span><span class="sxs-lookup"><span data-stu-id="318f9-205">In Cloud Connector version 2.0 and later, the Renew-CcServerCertificate cmdlet has changed to Update-CcServerCertificate and the Renew-CcCACertificate cmdlet has changed to Update-CcCACertificate.</span></span> 
  
    <span data-ttu-id="318f9-206">中央管理ストア、仲介サーバー、エッジ サーバーに発行された内部証明書の有効期限が近い場合、または侵害されている場合は、Renew-CcServerCertificate または Update-CcServerCertificate コマンドレットを実行して証明書を更新します。</span><span class="sxs-lookup"><span data-stu-id="318f9-206">If internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are near expiration or compromised, run the Renew-CcServerCertificate or Update-CcServerCertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="318f9-207">証明機関の証明書の有効期限が近い場合は、Renew-CcCACertificateまたはUpdate-CcCACertificateコマンドレットを実行して証明書を更新します。</span><span class="sxs-lookup"><span data-stu-id="318f9-207">If certification authority certificates are near expiration, run the Renew-CcCACertificate or Update-CcCACertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="318f9-208">**証明機関の証明書が侵害** され、サイトにアプライアンスが 1 つしかない場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="318f9-208">**If certification authority certificates are compromised and there is only one appliance in the site,** perform the following steps:</span></span>
    
1. <span data-ttu-id="318f9-209">サービスをEnter-CcUpdateし、アプライアンスをメンテナンス モードに設定するには、このコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="318f9-209">Run the Enter-CcUpdate cmdlet to drain services and put the appliance in maintenance mode.</span></span>
   
   ```powershell
   Enter-CcUpdate
   ```
   
2. <span data-ttu-id="318f9-210">次のコマンドレットを実行して、新しい証明機関証明書とすべての内部サーバー証明書をリセットして作成します。</span><span class="sxs-lookup"><span data-stu-id="318f9-210">Run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
    <span data-ttu-id="318f9-211">2.0 より前のクラウド コネクタ リリースの場合:</span><span class="sxs-lookup"><span data-stu-id="318f9-211">For Cloud Connector releases before 2.0:</span></span>
    
    ```powershell
    Reset-CcCACertificate 
    Renew-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

    <span data-ttu-id="318f9-212">または、クラウド コネクタ リリース 2.0 以降の場合:</span><span class="sxs-lookup"><span data-stu-id="318f9-212">Or for Cloud Connector release 2.0 and later:</span></span>
    
    ```powershell
    Reset-CcCACertificate 
    Update-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```
    
3. <span data-ttu-id="318f9-213">ゲートウェイと仲介サーバーの間で TLS を使用する場合は、アプライアンスから Export-CcRootCertificate コマンドレットを実行し、エクスポートされた証明書を PSTN ゲートウェイにインストールします。</span><span class="sxs-lookup"><span data-stu-id="318f9-213">If TLS is used between the gateway and the Mediation Server, run the Export-CcRootCertificate cmdlet from the appliance, and then install the exported certificate to your PSTN gateways.</span></span> <span data-ttu-id="318f9-214">また、ゲートウェイで証明書を再発行する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="318f9-214">You may also be required to re-issue the certificate on your gateway.</span></span>

   ```powershell
   Export-CcRootCertificate
   ```

4. <span data-ttu-id="318f9-215">サービスを開始Exit-CcUpdateメンテナンス モードを終了するには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="318f9-215">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span>

   ```powershell
   Exit-CcUpdate
   ```


    <span data-ttu-id="318f9-216">**証明機関の証明書が侵害** され、サイト内に複数のアプライアンスがある場合は、サイト内の各アプライアンスで次の順次手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="318f9-216">**If certification authority certificates are compromised and there are multiple appliances in the site,** perform the following sequential steps on each appliance in the site.</span></span>
    
    <span data-ttu-id="318f9-217">ピーク以外の使用時間の間にこれらの手順を実行してください。</span><span class="sxs-lookup"><span data-stu-id="318f9-217">Microsoft recommends that you perform these steps during non-peak usage times.</span></span>
    
1. <span data-ttu-id="318f9-218">最初のアプライアンスで、Remove-CcCertificationAuthorityFile コマンドレットを実行して、ディレクトリ内の CA バックアップ ファイルをクリーンアップ \<SiteRoot\> します。</span><span class="sxs-lookup"><span data-stu-id="318f9-218">On the first appliance, run the Remove-CcCertificationAuthorityFile cmdlet to clean up the CA backup files in the \<SiteRoot\> directory.</span></span>

     ```powershell
     Remove-CcCertificationAuthorityFile
     ```
    
2. <span data-ttu-id="318f9-219">サービスをEnter-CcUpdateし、各アプライアンスをメンテナンス モードに設定するには、Enter-CcUpdate コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="318f9-219">Run the Enter-CcUpdate cmdlet to drain services and put each appliance in maintenance mode.</span></span>

     ```powershell
     Enter-CcUpdate
     ```
    
3. <span data-ttu-id="318f9-220">最初のアプライアンスで、次のコマンドレットを実行して、新しい証明機関証明書とすべての内部サーバー証明書をリセットして作成します。</span><span class="sxs-lookup"><span data-stu-id="318f9-220">On the first appliance, run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
     <span data-ttu-id="318f9-221">2.0 より前のクラウド コネクタ リリースの場合:</span><span class="sxs-lookup"><span data-stu-id="318f9-221">For Cloud Connector releases before 2.0:</span></span>
    
     ```powershell
     Reset-CcCACertificate
     Renew-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

     <span data-ttu-id="318f9-222">または、クラウド コネクタ リリース 2.0 以降の場合:</span><span class="sxs-lookup"><span data-stu-id="318f9-222">Or for Cloud Connector release 2.0 and later:</span></span>
    
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

4. <span data-ttu-id="318f9-223">最初のアプライアンスで、次のコマンドレットを実行して CA ファイルをフォルダーにバックアップ \<SiteRoot\> します。</span><span class="sxs-lookup"><span data-stu-id="318f9-223">On the first appliance, run the following cmdlet to back up the CA files to the \<SiteRoot\> folder.</span></span>
    
     ```powershell
     Backup-CcCertificationAuthority
     ```
   
5. <span data-ttu-id="318f9-224">同じサイト内の他のすべてのアプライアンスで、次のコマンドを実行して CA バックアップ ファイルを使用し、アプライアンスすべてが同じルート証明書を使用し、新しい証明書を要求します。</span><span class="sxs-lookup"><span data-stu-id="318f9-224">On all other appliance's in the same site, run the following commands to consume the CA backup files, so that the appliances all use the same root certificate, and then request new certificates.</span></span> 
   
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```
     
6. <span data-ttu-id="318f9-225">ゲートウェイと仲介サーバーの間で TLS を使用する場合は、サイト内の任意のアプライアンスから Export-CcRootCertificate コマンドレットを実行し、エクスポートされた証明書を PSTN ゲートウェイにインストールします。</span><span class="sxs-lookup"><span data-stu-id="318f9-225">If TLS is used between the gateway and the Mediation Server, run the Export-CcRootCertificate cmdlet from any appliance in the site, and then install the exported certificate to your PSTN gateways.</span></span> <span data-ttu-id="318f9-226">また、ゲートウェイで証明書を再発行する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="318f9-226">You may also be required to re-issue the certificate on your gateway.</span></span>
  
     ```powershell
     Export-CcRootCertificate
     ```
     
7. <span data-ttu-id="318f9-227">サービスを開始Exit-CcUpdateメンテナンス モードを終了するには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="318f9-227">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span> 

     ```powershell
     Exit-CcUpdate
     ```
    
    
- <span data-ttu-id="318f9-228">**問題: クラウド コネクタ管理サービス ログに次のエラー メッセージが表示されます。"C:\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log": CceService エラー: 0 : オンラインに状態を報告するときに予期しない例外: System.Management.Automation.CmdletInvocationException: ユーザーのログオンに失敗しました。 \<Global Tenant Admin\>正しいユーザー名とパスワードを使用していることを確認して、新しい資格情報オブジェクトを作成してください。---\>**</span><span class="sxs-lookup"><span data-stu-id="318f9-228">**Issue: You receive the following error message in the Cloud Connector Management Service Log, "C:\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log": CceService Error: 0 : Unexpected exception when reporting status to online: System.Management.Automation.CmdletInvocationException: Logon failed for the user \<Global Tenant Admin\>. Please create a new credential object, making sure that you have used the correct user name and password. ---\>**</span></span>
    
    <span data-ttu-id="318f9-229">**解決策:** Microsoft 365 または Office 365 グローバル テナント管理者の資格情報は、クラウド コネクタ アプライアンスが登録された後に変更されています。</span><span class="sxs-lookup"><span data-stu-id="318f9-229">**Resolution:** The Microsoft 365 or Office 365 global tenant admin credentials have been changed since the Cloud Connector appliance was registered.</span></span> <span data-ttu-id="318f9-230">クラウド コネクタ アプライアンスでローカルに保存されている資格情報を更新するには、ホスト アプライアンスの Administrator PowerShell から次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="318f9-230">To update the locally stored credentials on the Cloud Connector appliance, run the following from Administrator PowerShell on the host appliance:</span></span>
    
  ```powershell
  Set-CcCredential -AccountType TenantAdmin
  ```

- <span data-ttu-id="318f9-231">**問題: 展開に使用したホスト サーバー アカウントのパスワードを変更した後、%ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log または Get-CcCredential コマンドレットの実行中に、次のエラー メッセージが表示されます。**</span><span class="sxs-lookup"><span data-stu-id="318f9-231">**Issue: After you change the password for the host server account you used for the deployment, you receive the following error message: "ConvertTo-SecureString : Key not valid for use in specified state." in %ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log or while running the Get-CcCredential cmdlet.**</span></span>
    
    <span data-ttu-id="318f9-232">**解決策:** すべてのクラウド コネクタ資格情報は、"%SystemDrive%\Programdata\Cloudconnector\credentials" というファイルに格納されます \<CurrentUser\> 。xml」</span><span class="sxs-lookup"><span data-stu-id="318f9-232">**Resolution:** All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="318f9-233">ホスト サーバーのパスワードが変更された場合は、ローカルに保存されている資格情報を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="318f9-233">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
    
    <span data-ttu-id="318f9-234">**クラウド コネクタ バージョン 1.4.2** を実行している場合は、次の手順に従ってすべてのクラウド コネクタ のパスワードを再生成します。</span><span class="sxs-lookup"><span data-stu-id="318f9-234">**If you are running Cloud Connector version 1.4.2,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  1. <span data-ttu-id="318f9-235">ホスト サーバーを再起動します。</span><span class="sxs-lookup"><span data-stu-id="318f9-235">Restart the host server.</span></span>
    
  2. <span data-ttu-id="318f9-236">"%SystemDrive%\Programdata\Cloudconnector\credentials" というファイルを削除します \<CurrentUser\> 。xml」</span><span class="sxs-lookup"><span data-stu-id="318f9-236">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
  3. <span data-ttu-id="318f9-237">管理者として PowerShell コンソールを起動し、"Register-CcAppliance -Local" を実行して、説明に従ってパスワードを再入力します。</span><span class="sxs-lookup"><span data-stu-id="318f9-237">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="318f9-238">クラウド コネクタの展開に前に入力したパスワードと同じパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="318f9-238">Enter the same passwords you entered before for the Cloud Connector deployment.</span></span>
    
     <span data-ttu-id="318f9-239">**クラウド コネクタ バージョン 2.0** 以降を実行している場合は、次の手順に従ってすべての Cloud Connector パスワードを再生成します。</span><span class="sxs-lookup"><span data-stu-id="318f9-239">**If you are running Cloud Connector version 2.0 or later,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  4. <span data-ttu-id="318f9-240">ホスト サーバーを再起動します。</span><span class="sxs-lookup"><span data-stu-id="318f9-240">Restart the host server.</span></span>
    
  5. <span data-ttu-id="318f9-241">"%SystemDrive%\Programdata\Cloudconnector\credentials" というファイルを削除します \<CurrentUser\> 。xml" .</span><span class="sxs-lookup"><span data-stu-id="318f9-241">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" .</span></span>
    
  6. <span data-ttu-id="318f9-242">管理者として PowerShell コンソールを起動し、"Register-CcAppliance -Local" を実行して、説明に従ってパスワードを再入力します。</span><span class="sxs-lookup"><span data-stu-id="318f9-242">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> 
    
     <span data-ttu-id="318f9-243">キャッシュされたパスワード ファイルが Cloud Connector バージョン 1.4.2 で生成された場合は、プロンプトが表示されたら、CceService パスワードの VMAdmin パスワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="318f9-243">If the cached password file was generated with Cloud Connector version 1.4.2, use the VMAdmin password for the CceService password when prompted.</span></span> <span data-ttu-id="318f9-244">他のすべてのアカウントのクラウド コネクタ展開に対して前に入力したパスワードと同じパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="318f9-244">Enter the same password you entered before for the Cloud Connector deployment for all other accounts.</span></span>
    
     <span data-ttu-id="318f9-245">キャッシュされたパスワード ファイルが Cloud Connector バージョン 1.4.2 で生成され、DomainAdmin と VMAdmin のパスワードが異なる場合は、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="318f9-245">If the cached password file was generated with Cloud Connector version 1.4.2 and the DomainAdmin and VMAdmin passwords are different, you must perform the following steps:</span></span>
    
  7. <span data-ttu-id="318f9-246">次Set-CcCredential -AccountType DomainAdmin を実行します。</span><span class="sxs-lookup"><span data-stu-id="318f9-246">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
  8. <span data-ttu-id="318f9-247">古いアカウント資格情報の入力を求めるメッセージが表示されたら、CceService パスワードに使用した資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="318f9-247">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
  9. <span data-ttu-id="318f9-248">新しいアカウント資格情報の入力を求めるメッセージが表示されたら、前に使用した DomainAdmin パスワードのパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="318f9-248">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
     <span data-ttu-id="318f9-249">キャッシュされたパスワード ファイルが Cloud Connector バージョン 2.0 以降で生成された場合、既定では VmAdmin と DomainAdmin は CceService と同じパスワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="318f9-249">If the cached password file was generated with Cloud Connector version 2.0 or later, by default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="318f9-250">DomainAdmin パスワードと VMAdmin パスワードを変更した場合は、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="318f9-250">If you changed the DomainAdmin and VMAdmin passwords, you must perform the following steps:</span></span>
    
  10. <span data-ttu-id="318f9-251">次Set-CcCredential -AccountType DomainAdmin を実行します。</span><span class="sxs-lookup"><span data-stu-id="318f9-251">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
       1. <span data-ttu-id="318f9-252">古いアカウント資格情報の入力を求めるメッセージが表示されたら、CceService パスワードに使用した資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="318f9-252">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="318f9-253">新しいアカウント資格情報の入力を求めるメッセージが表示されたら、前に使用した DomainAdmin パスワードのパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="318f9-253">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
  11. <span data-ttu-id="318f9-254">次Set-CcCredential -AccountType VmAdmin を実行します。</span><span class="sxs-lookup"><span data-stu-id="318f9-254">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
       1. <span data-ttu-id="318f9-255">古いアカウント資格情報の入力を求めるメッセージが表示されたら、CceService パスワードに使用した資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="318f9-255">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="318f9-256">新しいアカウント資格情報の入力を求めるメッセージが表示されたら、前に使用した VmAdmin パスワードのパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="318f9-256">When prompted for the new account credential, enter the password for the VmAdmin password you used before.</span></span> 
    
- <span data-ttu-id="318f9-257">**問題: クラウド コネクタ バージョン 2.1 以降では、Register-CcAppliance または他のコマンドレットをアプライアンスで実行すると、次のようなエラー メッセージが表示されます。"Each-Object : プロパティ 'Common' はこのオブジェクトで見つかりません。プロパティが存在することを確認します。C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char:14"**</span><span class="sxs-lookup"><span data-stu-id="318f9-257">**Issue: With Cloud Connector version 2.1 and later, when running Register-CcAppliance or other cmdlets on the appliance, you receive an error message such as: "For Each-Object : The property 'Common' cannot be found on this object. Verify that the property exists. At C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char:14"**</span></span>
    
    <span data-ttu-id="318f9-258">**解決策:** クラウド コネクタ 2.1 以降では、.NET Framework 4.6.1 以降が必要です。</span><span class="sxs-lookup"><span data-stu-id="318f9-258">**Resolution:** Cloud Connector 2.1 and later requires .NET Framework 4.6.1 or later.</span></span> <span data-ttu-id="318f9-259">アプライアンスの.NET Frameworkバージョン 4.6.1 以降に更新し、コマンドレットを再度実行してください。</span><span class="sxs-lookup"><span data-stu-id="318f9-259">Please update .NET Framework on the appliance to version 4.6.1 or later and run the cmdlet(s) again.</span></span>

- <span data-ttu-id="318f9-260">**問題: Cloud Connector Edition 2.1 を使用して Install-CcAppliance を実行すると、次のようなエラー メッセージが表示されます。**</span><span class="sxs-lookup"><span data-stu-id="318f9-260">**Issue: With Cloud Connector Edition 2.1, when running Install-CcAppliance, you receive an error message such as: "Failed to install new instance with error: Cannot set "State" because only strings can be used as values to set XmlNode properties"**</span></span>

   <span data-ttu-id="318f9-261">**解決策:** [Cloudconnector.ini[Common] セクションで、次のように "State" 構成を追加してください。 CountryCode=US State=WA City=Redmond</span><span class="sxs-lookup"><span data-stu-id="318f9-261">**Resolution:** In Cloudconnector.ini, under the [Common] section, please add the “State” config as below:  CountryCode=US  State=WA  City=Redmond</span></span>

   <span data-ttu-id="318f9-262">"State" 行に値を設定する必要は必須ではありませんが、"State" 行はファイルファイルからCloudconnector.iniできません。</span><span class="sxs-lookup"><span data-stu-id="318f9-262">It is not mandatory for the "State" line to have value, however the "State" line cannot be removed from the Cloudconnector.ini file.</span></span>

- <span data-ttu-id="318f9-263">**問題: 次のエラー メッセージ "Dismount-WindowsImage : エラーが発生Dismount-WindowsImageされます。Cloud Connector Edition をインストール0xc1550115アップグレードする場合、エラー コード = 0xc1550115" が表示されます。**</span><span class="sxs-lookup"><span data-stu-id="318f9-263">**Issue: You receive the following error message "Dismount-WindowsImage : Dismount-WindowsImage failed. Error code = 0xc1550115" when installing or upgrading Cloud Connector Edition.**</span></span>
    
    <span data-ttu-id="318f9-264">**解決策:** 管理者として PowerShell コンソールを起動し、「DISM -Cleanup-Wim」を実行します。</span><span class="sxs-lookup"><span data-stu-id="318f9-264">**Resolution:** Launch a PowerShell console as administrator, run "DISM -Cleanup-Wim'".</span></span> <span data-ttu-id="318f9-265">これにより、問題が発生した画像はすべてクリーンアップされます。</span><span class="sxs-lookup"><span data-stu-id="318f9-265">This will clean up all troubled images.</span></span> <span data-ttu-id="318f9-266">もうInstall-CcAppliance実行するか、ビットが自動的にアップグレードされるのを待ちます。</span><span class="sxs-lookup"><span data-stu-id="318f9-266">Run Install-CcAppliance again or wait for the bits to automatically upgrade.</span></span>
    
- <span data-ttu-id="318f9-267">**問題: HA 環境での最初のクラウド コネクタ アプライアンスの展開が失敗する**</span><span class="sxs-lookup"><span data-stu-id="318f9-267">**Issue: Deployment of the first Cloud Connector appliance in an HA environment fails**</span></span>
    
    <span data-ttu-id="318f9-268">**解決策:** 実行する手順は、展開が失敗した理由によって異なる。</span><span class="sxs-lookup"><span data-stu-id="318f9-268">**Resolution:** The steps you take depend on the reason the deployment failed:</span></span>
    
  - <span data-ttu-id="318f9-269">最初のクラウド コネクタ アプライアンスが失敗し、障害の理由を特定できない場合は、展開が成功するまでアプライアンスを再度インストールしてから、他のアプライアンスをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="318f9-269">If the first Cloud Connector appliance fails and you cannot determine the reason for the failure, you must install the appliance again until the deployment is successful, and then install the other appliances.</span></span>
    
  - <span data-ttu-id="318f9-270">外部証明書の問題など、軽微な問題で最初のクラウド コネクタ アプライアンスが失敗した場合は、アプライアンスを再インストールせずに問題を解決できる場合があります。</span><span class="sxs-lookup"><span data-stu-id="318f9-270">If the first Cloud Connector appliance fails with a minor issue, such as an external certificate issue, you might be able to fix the problem without re-installing the appliance.</span></span> <span data-ttu-id="318f9-271">その後、テナント リモート PowerShell を使用して、展開を次のように成功としてマークできます。</span><span class="sxs-lookup"><span data-stu-id="318f9-271">You can then use tenant remote PowerShell to mark the deployment as successful as follows.</span></span> <span data-ttu-id="318f9-272">(最初の展開が成功した場合でも、次の手順を使用できますが、何らかの理由で、クラウド コネクタは展開を成功として報告できません)。</span><span class="sxs-lookup"><span data-stu-id="318f9-272">(You can also use the following steps if the first deployment was successful, but, for some reason, Cloud Connector fails to report the deployment as a success.)</span></span>
    
  - <span data-ttu-id="318f9-273">最初のクラウド コネクタ アプライアンスの ID (GUID) を取得するには、次のコマンドレットGet-CsHybridPSTNApplianceします。</span><span class="sxs-lookup"><span data-stu-id="318f9-273">To get the Identity (GUID) of the first Cloud Connector appliance, run the Get-CsHybridPSTNAppliance cmdlet.</span></span>
    
  - <span data-ttu-id="318f9-274">アプライアンスを正常に展開済みとしてマークするには、次のようにSet-CsCceApplianceDeploymentStatusを実行します。</span><span class="sxs-lookup"><span data-stu-id="318f9-274">To mark the appliance as successfully deployed, run the Set-CsCceApplianceDeploymentStatus as follows:</span></span>
    
  ```powershell
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- <span data-ttu-id="318f9-275">**問題: ホスト サーバーまたは仮想マシンで Windows 更新プログラムを手動で確認してインストールする必要があります。**</span><span class="sxs-lookup"><span data-stu-id="318f9-275">**Issue: You need to check for and install Windows updates manually on the host server or virtual machines.**</span></span>
    
   <span data-ttu-id="318f9-276">**解決策:** Skype for Business Cloud Connector Edition が提供する自動 OS 更新プログラムを利用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="318f9-276">**Resolution:** We recommend that you take advantage of automated OS updates provided by Skype for Business Cloud Connector Edition.</span></span> <span data-ttu-id="318f9-277">アプライアンスがオンライン管理用に登録され、自動 OS 更新が有効になると、ホスト サーバーと仮想マシンは、OS の更新タイム ウィンドウの設定に従って Windows Update を自動的にチェックしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="318f9-277">After an appliance is registered for online management and auto OS update is enabled, the host server and virtual machines will check and install Windows Updates automatically according to the OS update time window settings.</span></span>
    
   <span data-ttu-id="318f9-278">Windows 更新プログラムを手動で確認してインストールする必要がある場合は、展開の種類に適用されるこのセクションの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="318f9-278">If you need to check for and install Windows Updates manually, follow the steps in this section that apply to your type of deployment.</span></span> <span data-ttu-id="318f9-279">更新に必要なダウンタイムを最小限に抑えるために、ホスト サーバーとホスト サーバー上で実行されている仮想マシンの両方を同時に更新する予定です。</span><span class="sxs-lookup"><span data-stu-id="318f9-279">You should plan on updating both the host server and the virtual machines running on it at the same time to minimize the amount of down time necessary for the updates.</span></span>
    
   <span data-ttu-id="318f9-280">必要に応じて、WSUS (Windows Server Update Services) サーバーを使用して、クラウド コネクタ サーバーに更新プログラムを提供できます。</span><span class="sxs-lookup"><span data-stu-id="318f9-280">If you prefer, you can use a Windows Server Update Services (WSUS) server to provide updates to Cloud Connector servers.</span></span> <span data-ttu-id="318f9-281">Windows Update が自動的にインストールされない構成 **にしてください** 。</span><span class="sxs-lookup"><span data-stu-id="318f9-281">Just be sure to configure the Windows Update to **not** install automatically.</span></span>
    
   <span data-ttu-id="318f9-282">クラウド コネクタの展開を手動で更新する方法については、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="318f9-282">For information about how to manually update your Cloud Connector deployment, see the following section.</span></span>
    
- <span data-ttu-id="318f9-283">**問題: クラウド コネクタが新しいビルドに更新された場合、Cloud Connector コマンドレットは更新されません。**</span><span class="sxs-lookup"><span data-stu-id="318f9-283">**Issue: When Cloud Connector updates to a new build, Cloud Connector cmdlets are not updated.**</span></span> <span data-ttu-id="318f9-284">これは、自動更新が発生した場合に PowerShell ウィンドウが開いた残っている場合に発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="318f9-284">This sometimes happens if a PowerShell window is left open when automatic update occurs.</span></span>
    
  <span data-ttu-id="318f9-285">**解決策:** 更新されたコマンドレットを読み込むには、次のいずれかの手順を実行できます。</span><span class="sxs-lookup"><span data-stu-id="318f9-285">**Resolution:** To load the updated cmdlets, you can do either of the following steps:</span></span>
    
   - <span data-ttu-id="318f9-286">クラウド コネクタ アプライアンスで PowerShell を閉じ、PowerShell を再度開きます。</span><span class="sxs-lookup"><span data-stu-id="318f9-286">Close PowerShell on the Cloud Connector appliance, and then reopen PowerShell.</span></span>
    
     - <span data-ttu-id="318f9-287">または、CloudConnector -Force Import-Module実行できます。</span><span class="sxs-lookup"><span data-stu-id="318f9-287">Or, you can run Import-Module CloudConnector -Force.</span></span> 
 
-   <span data-ttu-id="318f9-288">**問題: "Stop-CsWindowsService" という用語は、コマンドレット、関数、スクリプト ファイル、または操作可能なプログラムの名前として認識されません。Enter-CcUpdate コマンドレットを実行しようとするとエラーが発生します。**</span><span class="sxs-lookup"><span data-stu-id="318f9-288">**Issue: "The term 'Stop-CsWindowsService' is not recognized as the name of a cmdlet, function, script file, or operable program." error when attempting to run Enter-CcUpdate cmdlet.**</span></span>

    <span data-ttu-id="318f9-289">**解決策:** ファイルを$HOME\AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache ファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="318f9-289">**Resolution:** Delete the $HOME\AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache file.</span></span>
<span data-ttu-id="318f9-290">PowerShell は、見つけたモジュールからコマンドレットのキャッシュとしてこのファイルを作成します。これにより、すべてのモジュールを再分析する必要が生じ、その結果、処理が非常に遅くなります。</span><span class="sxs-lookup"><span data-stu-id="318f9-290">PowerShell creates this file as a cache of cmdlets from modules that it finds so that it doesn’t have to re-analyze all the modules each time as that would make things really slow.</span></span> <span data-ttu-id="318f9-291">ほとんどの場合、そのキャッシュから読み戻す際に、PowerShell に誤解を招く結果を提供するファイルの破損が発生した可能性があります。</span><span class="sxs-lookup"><span data-stu-id="318f9-291">Most likely, there was some file corruption that provided misleading results to PowerShell when it was reading back from that cache.</span></span>

-   <span data-ttu-id="318f9-292">**問題: "Import-Module CloudConnector" はエラー "Import-Module: 指定されたモジュール "CloudConnector" が読み込まれないので、有効なモジュール ファイルがモジュール ディレクトリに見つからなかったため生成されます。**</span><span class="sxs-lookup"><span data-stu-id="318f9-292">**Issue: “Import-Module CloudConnector” generates error “Import-Module: The specified module “CloudConnector” was not loaded because no valid module file was found in any module directory”**</span></span>

    <span data-ttu-id="318f9-293">**解決策:**</span><span class="sxs-lookup"><span data-stu-id="318f9-293">**Resolution:**</span></span>
    - <span data-ttu-id="318f9-294">c:\Program Files\WindowsPowerShell\Modules の下に CloudConnector モジュールが存在することを確認する</span><span class="sxs-lookup"><span data-stu-id="318f9-294">Validate that indeed the CloudConnector module exists under c:\Program Files\WindowsPowerShell\Modules</span></span>
    
    - <span data-ttu-id="318f9-295">CloudConnector モジュールがこの場所に存在することを検証した後、モジュールの場所へのパスを格納する PSModulePath 環境変数を変更できます。</span><span class="sxs-lookup"><span data-stu-id="318f9-295">After validating that CloudConnector module exists under this location, the PSModulePath environment variable storing the path to the locations of the modules can be changed:</span></span>
    
     <span data-ttu-id="318f9-296">a.</span><span class="sxs-lookup"><span data-stu-id="318f9-296">a.</span></span> <span data-ttu-id="318f9-297">一時的な変更: Powershell を管理者として起動し、$env:PSModulePath = $env:PSModulePath + ";C:\Program Files\WindowsPowerShell\Modules\"</span><span class="sxs-lookup"><span data-stu-id="318f9-297">Temporary change: Start Powershell as an Administrator and run the following command: $env:PSModulePath = $env:PSModulePath + ";C:\Program Files\WindowsPowerShell\Modules\"</span></span>
        
     <span data-ttu-id="318f9-298">b.</span><span class="sxs-lookup"><span data-stu-id="318f9-298">b.</span></span> <span data-ttu-id="318f9-299">永続的な変更を行う場合は、PowerShell を管理者として起動し、次のコマンドを 1 つ 1 つ実行します。$CurrentValue = [環境]::GetEnvironmentVariable("PSModulePath","Machine") SetEnvironmentVariable("PSModulePath",$CurrentValue + ";C:\Program Files\WindowsPowerShell\Modules", "Machine")</span><span class="sxs-lookup"><span data-stu-id="318f9-299">For persistent change, Start PowerShell as an Administrator and run the following commands, one by one: $CurrentValue = [Environment]::GetEnvironmentVariable("PSModulePath", "Machine") SetEnvironmentVariable("PSModulePath", $CurrentValue + "; C:\Program Files\WindowsPowerShell\Modules", "Machine")</span></span>

    
## <a name="install-windows-updates-manually"></a><span data-ttu-id="318f9-300">Windows 更新プログラムを手動でインストールする</span><span class="sxs-lookup"><span data-stu-id="318f9-300">Install Windows updates manually</span></span>

<span data-ttu-id="318f9-301">環境で自動更新を使用しない場合は、次の手順に従って Windows 更新プログラムを手動で確認して適用します。</span><span class="sxs-lookup"><span data-stu-id="318f9-301">If you do not want to use automatic updates in your environment, follow these steps to manually check for and apply Windows updates.</span></span> <span data-ttu-id="318f9-302">Windows 更新プログラムを確認してインストールするには、サーバーの再起動が必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="318f9-302">Checking for and installing Windows updates may require a server restart.</span></span> <span data-ttu-id="318f9-303">ホスト サーバーが再起動すると、ユーザーはクラウド コネクタを使用して通話を送受信できません。</span><span class="sxs-lookup"><span data-stu-id="318f9-303">When a host server is restarting, users will not be able to use Cloud Connector to place or receive calls.</span></span> <span data-ttu-id="318f9-304">更新プログラムを手動で確認してインストールして、更新プログラムの実行を制御し、サービスの中断を避けるために選択した時間に必要に応じてコンピューターを再起動できます。</span><span class="sxs-lookup"><span data-stu-id="318f9-304">You can manually check for and install updates to control when the updates take place, and then restart the machines as needed during times you choose to avoid disruption of services.</span></span>
  
<span data-ttu-id="318f9-305">更新プログラムを手動で確認するには、各ホスト サーバーに接続し、コントロール パネルを **開きます**。</span><span class="sxs-lookup"><span data-stu-id="318f9-305">To manually check for updates, connect to each host server and open the **Control Panel**.</span></span> <span data-ttu-id="318f9-306">[ **システムとセキュリティ \> の Windows Update]** を選択し、環境に応じて更新プログラムとサーバーの再起動を管理します。</span><span class="sxs-lookup"><span data-stu-id="318f9-306">Select **System and Security \>Windows Update**, and then manage the updates and server restarts as appropriate for your environment.</span></span>
  
- <span data-ttu-id="318f9-307">サイトにアプライアンスが 1 つしかない場合は、各仮想マシンに接続し、コントロール パネルを **開きます**。</span><span class="sxs-lookup"><span data-stu-id="318f9-307">If there is only one appliance in the site, connect to each virtual machine and open the **Control Panel**.</span></span> <span data-ttu-id="318f9-308">[ **システムとセキュリティ \> の Windows Update]** を選択し、必要に応じて更新プログラムとサーバーの再起動を構成します。</span><span class="sxs-lookup"><span data-stu-id="318f9-308">Select **System and Security \>Windows Update**, and then configure the updates and server restarts as appropriate.</span></span>
    
- <span data-ttu-id="318f9-309">サイト内に複数のアプライアンスがある場合、更新中および再起動中のインスタンスは、更新中にユーザーがアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="318f9-309">If there are more than one appliance in the site, the instance being updated and restarted cannot be accessed by users during the updates.</span></span> <span data-ttu-id="318f9-310">更新が完了した後、すべての仮想マシンとすべての Skype for Business サービスが仮想マシンで開始されるまで、ユーザーは展開内の他のインスタンスに接続します。</span><span class="sxs-lookup"><span data-stu-id="318f9-310">Users will connect to other instances in the deployment until all virtual machines and all Skype for Business services start on the virtual machines after the updates are completed.</span></span> <span data-ttu-id="318f9-311">サービスが中断される可能性を回避するために、更新プログラムの適用中に HA からインスタンスを削除し、完了したら復元できます。</span><span class="sxs-lookup"><span data-stu-id="318f9-311">To avoid any potential disruption to service, you can remove the instance from HA while you apply the updates, and then restore it when complete.</span></span> <span data-ttu-id="318f9-312">これを行うには、以下のようにします。</span><span class="sxs-lookup"><span data-stu-id="318f9-312">To do so:</span></span>
    
1. <span data-ttu-id="318f9-313">各ホスト サーバーで、管理者として PowerShell コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="318f9-313">On each host server, open a PowerShell console as administrator.</span></span>
    
2. <span data-ttu-id="318f9-314">次のコマンドレットを使用して HA からインスタンスを削除します。</span><span class="sxs-lookup"><span data-stu-id="318f9-314">Remove the instance from HA with the following cmdlet:</span></span>
    
   ```powershell
   Enter-CcUpdate
   ```

3. 
    
    <span data-ttu-id="318f9-315">1 つのインスタンスの手順に従って手動で更新プログラムを適用し、仮想マシンを再起動します。</span><span class="sxs-lookup"><span data-stu-id="318f9-315">Follow the steps for a single instance to manually apply the updates and restart the virtual machine.</span></span>
    
4. <span data-ttu-id="318f9-316">次のコマンドレットを使用して、インスタンスを HA に戻します。</span><span class="sxs-lookup"><span data-stu-id="318f9-316">Set the instance back to HA with the following cmdlet:</span></span>
    
   ```powershell
   Exit-CcUpdate
   ```

<span data-ttu-id="318f9-317">複数サイト展開の場合は、展開内の各サイトの 1 つのサイトの手順に従って、一度に 1 つのサイトに更新プログラムを適用します。</span><span class="sxs-lookup"><span data-stu-id="318f9-317">For multi-site deployments, follow the steps for a single site for each site in the deployment, applying updates to one site at a time.</span></span>
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a><span data-ttu-id="318f9-318">クラウド コネクタ ホスト コンピューターにウイルス対策ソフトウェアをインストールする際のヒント</span><span class="sxs-lookup"><span data-stu-id="318f9-318">Tips when installing anti-virus software on the Cloud Connector host machine</span></span>

<span data-ttu-id="318f9-319">クラウド コネクタ ホスト コンピューターにウイルス対策ソフトウェアをインストールする必要がある場合は、次の除外を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="318f9-319">If you need to install anti-virus software on the Cloud Connector host machine, you need to add the following exclusions:</span></span>
  
- <span data-ttu-id="318f9-320">各コンピューター上のローカル アプライアンス ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="318f9-320">Local Appliance Directory on each machine.</span></span>
    
- <span data-ttu-id="318f9-321">各コンピューターのリモート サイト ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="318f9-321">Remote Site Directory on each machine.</span></span>
    
- <span data-ttu-id="318f9-322">コンピューター上のローカル サイト ディレクトリは、共有サイト のルート フォルダーをホストします。</span><span class="sxs-lookup"><span data-stu-id="318f9-322">Local Site Directory on the machine hosts the shared site root folder.</span></span>
    
- <span data-ttu-id="318f9-323">%ProgramFiles%\Skype for Business Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="318f9-323">%ProgramFiles%\Skype for Business Cloud Connector Edition</span></span>
    
- <span data-ttu-id="318f9-324">%ALLUSERSPROFILE%\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="318f9-324">%ALLUSERSPROFILE%\CloudConnector</span></span>
    
- <span data-ttu-id="318f9-325">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="318f9-325">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span></span>
    
- <span data-ttu-id="318f9-326">プロセスはMicrosoft.Rtc.CCE.ManagementService.exe。</span><span class="sxs-lookup"><span data-stu-id="318f9-326">The process Microsoft.Rtc.CCE.ManagementService.exe.</span></span>