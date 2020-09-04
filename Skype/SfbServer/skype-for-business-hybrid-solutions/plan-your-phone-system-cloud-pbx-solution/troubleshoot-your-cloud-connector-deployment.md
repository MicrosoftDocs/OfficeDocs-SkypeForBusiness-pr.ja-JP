---
title: Cloud Connector 展開のトラブルシューティング
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
description: Cloud Connector エディションの展開のトラブルシューティングを行います。
ms.openlocfilehash: 7a1caea67c5b5899c2dc0909ef771a57c7c50389
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359333"
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a><span data-ttu-id="f02cd-103">Cloud Connector 展開のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="f02cd-103">Troubleshoot your Cloud Connector deployment</span></span>

> [!Important]
> <span data-ttu-id="f02cd-104">Cloud Connector エディションは、2021年7月31日、Skype for Business Online と共に廃止されます。</span><span class="sxs-lookup"><span data-stu-id="f02cd-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="f02cd-105">組織が Teams にアップグレードされたら、 [直接ルーティング](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)を使用してオンプレミスのテレフォニーネットワークを teams に接続する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f02cd-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>
 
<span data-ttu-id="f02cd-106">Cloud Connector エディションの展開のトラブルシューティングを行います。</span><span class="sxs-lookup"><span data-stu-id="f02cd-106">Troubleshoot your Cloud Connector Edition deployment.</span></span>
  
<span data-ttu-id="f02cd-107">このトピックでは、Cloud Connector Edition の展開に関する一般的な問題の解決方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f02cd-107">This topic describes solutions to common issues with Cloud Connector Edition deployments.</span></span> <span data-ttu-id="f02cd-108">公衆交換電話網 (PSTN) の呼び出しで問題が発生している場合は、このトピックで説明するソリューションに従って調査できます。</span><span class="sxs-lookup"><span data-stu-id="f02cd-108">If you are experiencing issues with calls to and from the Public Switched Telephone Network (PSTN), you can investigate by following the solutions described in this topic.</span></span>
  
<span data-ttu-id="f02cd-109">Cloud Connector には、いくつかの問題を自動的に解決するための組み込みのメカニズムが用意されています。</span><span class="sxs-lookup"><span data-stu-id="f02cd-109">Cloud Connector provides built-in mechanisms for automatically resolving some issues.</span></span> <span data-ttu-id="f02cd-110">自動検出プロセスでは、Cloud Connector アプライアンスの潜在的な問題を検索し、可能であれば、管理者の介入なしにこれらの問題を解決するための是正措置を行います。</span><span class="sxs-lookup"><span data-stu-id="f02cd-110">An automatic detection process looks for potential issues with the Cloud Connector appliances, and, if possible, takes corrective action to resolve those issues without the need for administrator intervention.</span></span> <span data-ttu-id="f02cd-111">検出プロセスは次のように動作します。</span><span class="sxs-lookup"><span data-stu-id="f02cd-111">The detection process works as follows:</span></span>
  
- <span data-ttu-id="f02cd-112">**検出シーケンス:** Cloud Connector Management service は、アプライアンスがダウンしているかどうかを検出するために60秒ごとに処理を実行します。</span><span class="sxs-lookup"><span data-stu-id="f02cd-112">**Detection sequence:** The Cloud Connector Management service runs a process every 60 seconds for detecting whether an appliance is down.</span></span> <span data-ttu-id="f02cd-113">Cloud Connector バージョン2.0 以降では、検出プロセスでは、クラウドコネクタマシンへの PowerShell 接続を行うために Skype for Business の社内ネットワークスイッチを使用しています。2.0 より前のバージョンでは、検出プロセスは Cloud Connector management スイッチを使用します。</span><span class="sxs-lookup"><span data-stu-id="f02cd-113">In Cloud Connector version 2.0 and later, the detection process uses the Skype for Business Corpnet switch for making PowerShell connections to the Cloud Connector machines; for versions previous to 2.0, the detection process uses the Cloud Connector management switch.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f02cd-114">自動回復を正常に行うには、ホストと仮想マシンの間のネットワーク接続がホストネットワークスイッチを経由する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f02cd-114">For automatic recovery to succeed, there must be network connectivity between the host and virtual machines over the host network switch.</span></span> <span data-ttu-id="f02cd-115">自動検出と回復が成功することを確認するために、必ずネットワーク接続を確認してください。</span><span class="sxs-lookup"><span data-stu-id="f02cd-115">Be sure to check network connectivity to ensure that automatic detection and recovery can succeed.</span></span> 
  
- <span data-ttu-id="f02cd-116">**監視:** Cloud Connector バージョン2.0 以降では、次のサービスが監視されます。</span><span class="sxs-lookup"><span data-stu-id="f02cd-116">**Monitoring:** The following services are monitored in Cloud Connector version 2.0 and later:</span></span>
    
  - <span data-ttu-id="f02cd-117">仮想マシンが Cloud Connector の企業またはインターネット仮想スイッチに接続されていない</span><span class="sxs-lookup"><span data-stu-id="f02cd-117">Virtual Machines are not connected to the Cloud Connector Corporate or Internet virtual switches</span></span>
    
  - <span data-ttu-id="f02cd-118">仮想マシンが保存済みまたは停止状態になっている</span><span class="sxs-lookup"><span data-stu-id="f02cd-118">Virtual Machines are in a saved or stopped status</span></span>
    
  - <span data-ttu-id="f02cd-119">中央管理サーバーサービス: レプリカ、マスター</span><span class="sxs-lookup"><span data-stu-id="f02cd-119">Central Management Server services: REPLICA, MASTER</span></span>
    
  - <span data-ttu-id="f02cd-120">仲介サーバーサービス: REPLICA、RTCSRV、MEDSVC</span><span class="sxs-lookup"><span data-stu-id="f02cd-120">Mediation Server services: REPLICA, RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="f02cd-121">エッジサーバーサービス: REPLICA、RTCSRV、RTCDATAPROXY、RTCMRAUTH、RTCDATAPROXY</span><span class="sxs-lookup"><span data-stu-id="f02cd-121">Edge Server services: REPLICA, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY</span></span>
    
  - <span data-ttu-id="f02cd-122">エッジサーバー上の CS RTCSRV で、受信ファイアウォールルールが無効になっている。仲介サーバー上の CS RTCMEDSRV</span><span class="sxs-lookup"><span data-stu-id="f02cd-122">Inbound firewall rules are disabled for CS RTCSRV on Edge server, CS RTCMEDSRV on Mediation server</span></span>
    
    <span data-ttu-id="f02cd-123">Cloud Connector バージョン1.4.2 では、次のサービスのみが監視されます。</span><span class="sxs-lookup"><span data-stu-id="f02cd-123">In Cloud Connector version 1.4.2, only the following services are monitored:</span></span>
    
  - <span data-ttu-id="f02cd-124">仲介サーバーサービス: RTCSRV および MEDSVC</span><span class="sxs-lookup"><span data-stu-id="f02cd-124">Mediation Server services: RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="f02cd-125">エッジサーバーサービス: RTCSRV</span><span class="sxs-lookup"><span data-stu-id="f02cd-125">Edge Server service: RTCSRV</span></span>
    
- <span data-ttu-id="f02cd-126">**回復プロセス:** 監視対象のサービスがダウンしている場合は、アプライアンスが停止し、すべての問題を解決できるように、サービスが停止して、手動でマーク付けされます。</span><span class="sxs-lookup"><span data-stu-id="f02cd-126">**Recovery process:** If any monitored services are down, an appliance is marked down, and services are stopped and marked manual until all issues can be resolved.</span></span> <span data-ttu-id="f02cd-127">これにより、通話エラーが発生する可能性があるアプライアンスへのルーティングからの呼び出しを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="f02cd-127">This will prevent calls from routing to an appliance that may cause call failures.</span></span>
    
    <span data-ttu-id="f02cd-128">Cloud Connector Management service では、次のように自動回復が再試行されます。</span><span class="sxs-lookup"><span data-stu-id="f02cd-128">The Cloud Connector Management service will retry automatic recovery as follows</span></span>
    
  - <span data-ttu-id="f02cd-129">最初の再試行間隔は、最大間隔が1時間の10秒ごとになります。</span><span class="sxs-lookup"><span data-stu-id="f02cd-129">The initial retry interval is every ten seconds with a maximum interval time of one hour.</span></span>
    
  - <span data-ttu-id="f02cd-130">最初の3回の回復試行では、間隔は10秒です。</span><span class="sxs-lookup"><span data-stu-id="f02cd-130">For the first three recovery attempts, the interval time is 10 seconds.</span></span> <span data-ttu-id="f02cd-131">4回目の再試行から、間隔は前の間隔の2倍の時間になります。</span><span class="sxs-lookup"><span data-stu-id="f02cd-131">Starting from the fourth retry, the interval time increases by two times the previous interval time.</span></span> <span data-ttu-id="f02cd-132">たとえば、4回目の再試行は20秒で、5秒間に40秒間実行されます。</span><span class="sxs-lookup"><span data-stu-id="f02cd-132">For example, the fourth retry will occur in 20 seconds, the fifth in 40 seconds, and so on.</span></span> 
    
  - <span data-ttu-id="f02cd-133">最大間隔の時間が1時間に達すると、再試行は1時間に1回続行されます。</span><span class="sxs-lookup"><span data-stu-id="f02cd-133">When the maximum interval time of one hour is reached, retries will continue once per hour.</span></span>
    
  - <span data-ttu-id="f02cd-134">回復に成功すると、間隔と再試行回数は初期値に設定されます。</span><span class="sxs-lookup"><span data-stu-id="f02cd-134">When recovery is successful, the interval and retry counts are set to their initial values.</span></span>
    
  - <span data-ttu-id="f02cd-135">管理サービスを再起動すると、間隔と再試行回数が初期値にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="f02cd-135">If the Management service is restarted, the interval and retry counts are reset to their initial values.</span></span>
    
## <a name="troubleshooting"></a><span data-ttu-id="f02cd-136">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="f02cd-136">Troubleshooting</span></span>

<span data-ttu-id="f02cd-137">一般的に発生する問題の解決策を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f02cd-137">Following are solutions to commonly encountered issues:</span></span>
  
- <span data-ttu-id="f02cd-138">**問題: 展開スクリプトを実行すると、展開に失敗するか、応答が停止します。各 VM にログオンした後、管理/内部/外部 NIC に対して IP アドレスが見つからないか、または正しくありません。**</span><span class="sxs-lookup"><span data-stu-id="f02cd-138">**Issue: Deployment fails or stops responding when running the deployment scripts. After logging on to each VM, the IP address is missing or incorrect for the Management/Internal/External NIC.**</span></span>
    
    <span data-ttu-id="f02cd-139">**解決策:** この問題を自動的に解決することはできません。</span><span class="sxs-lookup"><span data-stu-id="f02cd-139">**Resolution:** This issue cannot be resolved automatically.</span></span> <span data-ttu-id="f02cd-140">Nic は、実行中に Vm に追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="f02cd-140">NICs cannot be added to VMs while they are running.</span></span> <span data-ttu-id="f02cd-141">Hyper-v マネージャーでこれらの Vm をシャットダウンし、削除してから、次のコマンドレットを実行してください。</span><span class="sxs-lookup"><span data-stu-id="f02cd-141">Please shut down and remove these VMs in hyper-v manager, then run the following cmdlets:</span></span>
    
  ```powershell
  Uninstall-CcAppliance
  ```

  ```powershell
  Install-CcAppliance
  ```

- 
    
    <span data-ttu-id="f02cd-142">**問題: Active Directory サーバーとフォレストがインストールされた後、CMS サーバーや仲介サーバーがドメインに正しく参加しませんでした。**</span><span class="sxs-lookup"><span data-stu-id="f02cd-142">**Issue: After the Active Directory Server and forest are installed, the CMS Server and/or Mediation Server did not join the domain correctly.**</span></span>
    
    <span data-ttu-id="f02cd-143">**解決策:** この問題を解決するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f02cd-143">**Resolution:** To resolve this issue, take the following steps:</span></span>
    
  - <span data-ttu-id="f02cd-144">Active Directory サーバーにログオンし、ドメインが正しく作成されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="f02cd-144">Log on to the Active Directory Server and verify that the domain was created correctly.</span></span>
    
  - <span data-ttu-id="f02cd-145">CMS/仲介サーバーにログオンし、社内の NIC で有効な IP アドレスが割り当てられていること、および有効な静的 IP と DNS が AD サーバーの IP アドレスとして構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f02cd-145">Log on to the CMS/Mediation Server and verify that on the corpnet NIC a valid IP address is assigned, and that valid static IP and DNS is configured as the AD server's IP address.</span></span>
    
  - <span data-ttu-id="f02cd-146">CMS/仲介サーバーにログオンし、コマンドプロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="f02cd-146">Log on to the CMS/Mediation Server, and open a command prompt.</span></span> <span data-ttu-id="f02cd-147">Active Directory サーバーの FQDN と IP アドレスに ping を実行できることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f02cd-147">Make sure you can ping the FQDN and IP address of the Active Directory Server.</span></span> <span data-ttu-id="f02cd-148">できない場合は、IP アドレスの競合が発生している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f02cd-148">If you cannot, there may be an IP address conflict.</span></span> <span data-ttu-id="f02cd-149">Active Directory の新しい IP を割り当てて、CMS/仲介サーバーで DNS を更新してみてください。</span><span class="sxs-lookup"><span data-stu-id="f02cd-149">Please try to assign a new IP for Active Directory and update DNS on the CMS/Mediation server accordingly.</span></span>
    
- <span data-ttu-id="f02cd-150">**問題: "削除-VMSwitch: 仮想イーサネットスイッチの削除中にエラーが発生しました。" というエラーメッセージが表示される。仮想スイッチ ' Cloud Connector Management スイッチ ' は、実行中の仮想マシンによって使用されているか、子プールに割り当てられているため、削除できません。 "**</span><span class="sxs-lookup"><span data-stu-id="f02cd-150">**Issue: You receive the following error message, "Remove-VMSwitch : Failed while removing virtual Ethernet switch. The virtual switch 'Cloud Connector Management Switch' cannot be deleted because it is being used by running virtual machines or assigned to child pools."**</span></span>
    
    <span data-ttu-id="f02cd-151">**解決策:** 展開後に "Cloud Connector Management スイッチ" が削除されていません。</span><span class="sxs-lookup"><span data-stu-id="f02cd-151">**Resolution:** The "Cloud Connector Management Switch" was not deleted after the deployment.</span></span> <span data-ttu-id="f02cd-152">このエラーが発生した場合は、Hyper-v マネージャーに移動して、仮想マシンがまだ接続されていないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f02cd-152">If you hit this error, please go to Hyper-v manager and verify that there is not still a virtual machine still connected to it.</span></span> <span data-ttu-id="f02cd-153">まだ接続されている仮想マシンがある場合は、それらを切断して管理スイッチを削除します。</span><span class="sxs-lookup"><span data-stu-id="f02cd-153">If there are virtual machines still connected, disconnect them and delete the management switch.</span></span> <span data-ttu-id="f02cd-154">引き続き管理スイッチを削除できない場合は、ホストサーバーを再起動し、もう一度実行してください。</span><span class="sxs-lookup"><span data-stu-id="f02cd-154">If the management switch still cannot be deleted, restart the host server and try again.</span></span>
    
- <span data-ttu-id="f02cd-155">**問題: 次のエラーメッセージが表示されます。 "サービス RTCMRAUTH を開始できませんでした。サービスが無効になっていないことを確認してください。 "**</span><span class="sxs-lookup"><span data-stu-id="f02cd-155">**Issue: You receive the following error message, "Service RTCMRAUTH failed to start. Check to make sure the service is not disabled."**</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f02cd-156">この問題は、1.4.2 より前の Cloud Connector バージョンにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="f02cd-156">This issue only applies to Cloud Connector versions earlier than 1.4.2.</span></span> 
  
    <span data-ttu-id="f02cd-157">また、このフロントエンドサーバーが以前にフェールオーバーされた (コンピューターのフェールオーバーを使用した) ために、開始に失敗することもあります。</span><span class="sxs-lookup"><span data-stu-id="f02cd-157">The failure to start could also be because this Front End server was previously failed over (using computer fail over).</span></span> <span data-ttu-id="f02cd-158">その場合は、フェールバックを呼び出してください (コンピューターのフェールバックを使用)。</span><span class="sxs-lookup"><span data-stu-id="f02cd-158">If that's the case, please invoke fail back (using computer fail back).</span></span>
    
    <span data-ttu-id="f02cd-159">**解決策:** この問題は、ルート CA 証明書または中間 CA 証明書がエッジサーバーによって信頼されていない場合に、エッジサーバーで発生します。</span><span class="sxs-lookup"><span data-stu-id="f02cd-159">**Resolution:** This issue happens on an Edge Server when the root CA certificate or intermediate CA certificate is not trusted by the Edge Server.</span></span> <span data-ttu-id="f02cd-160">外部証明書をインポートできるが、証明書チェーンが破損している場合でも、</span><span class="sxs-lookup"><span data-stu-id="f02cd-160">Even if the external certificate can be imported but the certificate chain is broken.</span></span> <span data-ttu-id="f02cd-161">この条件下では、RTCMRAUTH または RTCSRV サービスを開始できません。</span><span class="sxs-lookup"><span data-stu-id="f02cd-161">Under this condition, the RTCMRAUTH and/or RTCSRV service can not start.</span></span>
    
    <span data-ttu-id="f02cd-162">ルート CA 証明書と外部証明書のすべての中間 CA 証明書をエッジサーバーに手動でインポートし、エッジサーバーを再起動してください。</span><span class="sxs-lookup"><span data-stu-id="f02cd-162">Please import the root CA certificate and all intermediate CA certificates of your external certificate manually into the Edge Server and then restart the Edge Server.</span></span> <span data-ttu-id="f02cd-163">エッジサーバー上で RTCMRAUTH サービスおよび RTCSRV サービスが開始されたことを確認した後、ホストサーバーに戻り、管理者として PowerShell コンソールを起動し、次のコマンドレットを実行して新しい展開に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="f02cd-163">After you see the RTCMRAUTH and RTCSRV services started on the Edge Server, go back to your host server, launch a PowerShell console as administrator, and run following cmdlet to switch to the new deployment:</span></span>
    
  ```powershell
  Switch-CcVersion
  ```

- 
    
    <span data-ttu-id="f02cd-164">**問題: Windows 更新プログラムの適用中にホストサーバーが再起動され、サーバーによって処理された呼び出しが失敗する。**</span><span class="sxs-lookup"><span data-stu-id="f02cd-164">**Issue: The host server was restarted when Windows updates were applied, and calls serviced by the server are failing.**</span></span>
    
    <span data-ttu-id="f02cd-165">**解決策:** 高可用性環境を展開した場合、Microsoft は、Windows update を手動で確認してインストールするときに、現在のトポロジから1つのホストマシン (展開インスタンス) を移行するためのコマンドレットを提供します。</span><span class="sxs-lookup"><span data-stu-id="f02cd-165">**Resolution:** If you deployed a high availability environment, Microsoft provides a cmdlet to help move one host machine (deployment instance) into or out of the current topology when you check and install Windows update manually.</span></span> <span data-ttu-id="f02cd-166">これを行うには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="f02cd-166">Use the following steps to accomplish this:</span></span>
    
1. <span data-ttu-id="f02cd-167">ホストサーバーで、管理者として PowerShell コンソールを起動し、次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="f02cd-167">On the host server, start a PowerShell console as administrator, then run:</span></span>
    
   ```powershell
   Enter-CcUpdate
   ```

2. <span data-ttu-id="f02cd-168">更新プログラムを確認し、利用可能なものをインストールします。</span><span class="sxs-lookup"><span data-stu-id="f02cd-168">Check for updates and install any that are available.</span></span>
    
3. <span data-ttu-id="f02cd-169">PowerShell コンソールで、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="f02cd-169">In the PowerShell console, run the following cmdlet:</span></span>
    
   ```powershell
   Exit-CcUpdate
   ```

- 
    
    <span data-ttu-id="f02cd-170">**問題: PSTN 番号を使用して Skype for Business クライアントから通話を発信したときに、別の PSTN 番号を招待することで、その通話を会議にエスカレートすることはできません。**</span><span class="sxs-lookup"><span data-stu-id="f02cd-170">**Issue: When a call is made from a Skype for Business client using a PSTN number, the call cannot be escalated to a conference by inviting another PSTN number.**</span></span>
    
    <span data-ttu-id="f02cd-171">**解決策:** この問題を解決するには、「 [Configure online Hybrid 仲介サーバーの設定](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f02cd-171">**Resolution:** To resolve this issue, see [Configure online hybrid Mediation Server Settings](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).</span></span>
    
- <span data-ttu-id="f02cd-172">**問題: Active Directory サーバーのインストール時に Windows Update に関する警告メッセージが表示されます。 "Windows 自動更新が有効になっていません。"新しくインストールした役割または機能が自動的に更新されるようにするには、[Windows Update] を有効にします。**</span><span class="sxs-lookup"><span data-stu-id="f02cd-172">**Issue: A warning message is displayed about Windows Update when you are installing Active Directory server - "Windows automatic updating is not enabled. To ensure that your newly-installed role or feature is automatically updated, turn on Windows Update."**</span></span>
    
    <span data-ttu-id="f02cd-173">**解決策:** Skype for Business テナント管理者の資格情報を使用してテナントのリモート PowerShell セッションを起動し、次のコマンドレットを実行して、サイトの _Enableautoupdate_ の構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="f02cd-173">**Resolution:** Launch a Tenant Remote PowerShell session using Skype for Business tenant admin credentials, then run the following cmdlet to check the _EnableAutoUpdate_ configuration of your site:</span></span>
    
  ```powershell
  Get-CsHybridPSTNSite
  ```

    <span data-ttu-id="f02cd-174">_Enableautoupdate_が**True**に設定されている場合、CCEManagement サービスは仮想マシンとホストサーバーの両方の Windows 更新プログラムのダウンロードとインストールを処理するため、この警告メッセージは無視しても問題ありません。</span><span class="sxs-lookup"><span data-stu-id="f02cd-174">If  _EnableAutoUpdate_ is set to **True**, you can safely ignore this warning message because the CCEManagement service will handle downloading and installing Windows updates for both virtual machines and the host server.</span></span> <span data-ttu-id="f02cd-175">_Enableautoupdate_が**False**に設定されている場合は、次のコマンドレットを実行して**True**に設定します。</span><span class="sxs-lookup"><span data-stu-id="f02cd-175">If  _EnableAutoUpdate_ is set to **False**, run following cmdlet to set it to **True**.</span></span>
    
  ```powershell
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    <span data-ttu-id="f02cd-176">別の方法として、更新プログラムを手動で確認してインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="f02cd-176">Alternatively, you can manually check for and install updates.</span></span> <span data-ttu-id="f02cd-177">次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f02cd-177">See the next section.</span></span>
    
- <span data-ttu-id="f02cd-178">**問題: エラーメッセージが表示される: 現在の入力/構成 \<SiteName\> または既存の \<ApplianceName\> \<Mediation Server FQDN\> \<Mediation Server IP Address\> アプライアンスと競合しているため、アプライアンスを登録できません。競合するアプライアンスを削除するか、入力/構成情報を更新してから、もう一度登録します。' Register → CcAppliance を実行して、現在のアプライアンスをオンラインに登録します。**</span><span class="sxs-lookup"><span data-stu-id="f02cd-178">**Issue: You receive an error message: Cannot register appliance because your current input/configuration \<SiteName\> or \<ApplianceName\> or \<Mediation Server FQDN\> or \<Mediation Server IP Address\> conflicts with existing appliance(s). Remove conflict appliance or update your input/configuration information then register again. ' when run Register-CcAppliance to register current appliance to online.**</span></span>
    
    <span data-ttu-id="f02cd-179">**解決策:** の値は \<ApplianceName\> で \<Mediation Server FQDN\> 、 \<Mediation Server IP Address\> 一意であり、1つのアプライアンス登録でのみ使用される必要があります。</span><span class="sxs-lookup"><span data-stu-id="f02cd-179">**Resolution:** Values for the \<ApplianceName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> must be unique and only used for one appliance registration.</span></span> <span data-ttu-id="f02cd-180">既定では、 \<ApplianceName\> ホスト名から取得されます。</span><span class="sxs-lookup"><span data-stu-id="f02cd-180">By default, \<ApplianceName\> comes from the host name.</span></span> <span data-ttu-id="f02cd-181">\<Mediation Server FQDN\>\<Mediation Server IP Address\>構成 ini ファイルで定義されています。</span><span class="sxs-lookup"><span data-stu-id="f02cd-181">\<Mediation Server FQDN\> and \<Mediation Server IP Address\> defined in configuration ini file.</span></span>
    
    <span data-ttu-id="f02cd-182">たとえば、(アプライアンス名を使用している場合は) を使用します。 (ただし、登録されているアプライアンスがある場合には、登録済みのアプライアンス (アプライアンス名 Ename = Myserver、仲介サーバーの FQDN = マックス、仲介サーバーの IP アドレス = 10.10.10.10) がある場合は、この競合が発生します。</span><span class="sxs-lookup"><span data-stu-id="f02cd-182">For example, using (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) to register to SiteName=MySite, but if there is a registered appliance (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10), you will have the conflict.</span></span>
    
    <span data-ttu-id="f02cd-183">最初に、ApplianceRoot directory セクションの CloudConnector.ini ファイルを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f02cd-183">First, please check your CloudConnector.ini file in ApplianceRoot directory section.</span></span> <span data-ttu-id="f02cd-184">ファイル内の値が取得され \<SiteName\> \<Mediation Server FQDN\> \<Mediation Server IP Address\> ます。</span><span class="sxs-lookup"><span data-stu-id="f02cd-184">You will get \<SiteName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> values in the file.</span></span> <span data-ttu-id="f02cd-185">\<ApplianceName\> は、ホストサーバー名です。</span><span class="sxs-lookup"><span data-stu-id="f02cd-185">\<ApplianceName\> is your host server name.</span></span>
    
    <span data-ttu-id="f02cd-186">2番目に、Skype for Business テナント管理者の資格情報を使用してテナントのリモート PowerShell を起動し、次のコマンドレットを実行して、登録されているアプライアンスを確認します。</span><span class="sxs-lookup"><span data-stu-id="f02cd-186">Second, Launch Tenant Remote PowerShell using your Skype for Business tenant admin credentials, then run the following cmdlet to check the registered appliance(s).</span></span>
    
  ```powershell
  Get-CsHybridPSTNAppliance
  ```

    <span data-ttu-id="f02cd-187">競合を特定したら、登録されているアプライアンスと一致する情報を使用して CloudConnector.ini ファイルを更新するか、既存のアプライアンスの登録を解除して競合を解決することができます。</span><span class="sxs-lookup"><span data-stu-id="f02cd-187">After identifying any conflicts, you can either update your CloudConnector.ini file with information that matches the registered appliance, or unregister the existing appliance to resolve the conflicts.</span></span>
    
  ```powershell
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
- <span data-ttu-id="f02cd-188">**問題: ホスト上で実行されている展開済みのアプライアンスがある場合、Get-CcRunningVersion コマンドレットは空の値を返します。**</span><span class="sxs-lookup"><span data-stu-id="f02cd-188">**Issue: The Get-CcRunningVersion cmdlet returns an empty value if there is a deployed appliance running on the host.**</span></span>
    
  <span data-ttu-id="f02cd-189">**解決策:** これは、1.3.4 または1.3.8 から1.4.1 にアップグレードしたときに発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f02cd-189">**Resolution:** This can happen when you upgrade from 1.3.4 or 1.3.8 to 1.4.1.</span></span> <span data-ttu-id="f02cd-190">バージョン1.4.1 を .msi と共にインストールした後、 `Register-CcAppliance` 他のコマンドレットを実行する前に、を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f02cd-190">After you install version 1.4.1 with the .msi, you must run `Register-CcAppliance` before you run any other cmdlet.</span></span> <span data-ttu-id="f02cd-191">`Register-CcAppliance` module.ini ファイルを%UserProfile%\CloudConnector から%ProgramData%\CloudConnector. に移行します。</span><span class="sxs-lookup"><span data-stu-id="f02cd-191">`Register-CcAppliance` will migrate the module.ini file from %UserProfile%\CloudConnector to %ProgramData%\CloudConnector.</span></span> <span data-ttu-id="f02cd-192">不在の場合は、新しい module.ini が%ProgramData%\CloudConnector フォルダーに作成され、1.3.4 または1.3.8 の実行/バックアップバージョン情報が置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="f02cd-192">If you missed it, a new module.ini will be created in %ProgramData%\CloudConnector folder and replace the running/backup version information for 1.3.4 or 1.3.8.</span></span>
    
  <span data-ttu-id="f02cd-193">%UserProfile%\CloudConnector および%ProgramData%\CloudConnector フォルダー内のファイル module.ini 比較します。</span><span class="sxs-lookup"><span data-stu-id="f02cd-193">Compare module.ini files in %UserProfile%\CloudConnector and %ProgramData%\CloudConnector folder.</span></span> <span data-ttu-id="f02cd-194">相違点がある場合は、%ProgramData%\CloudConnector の module.ini ファイルを削除して、再度実行  `Register-CcAppliance` します。</span><span class="sxs-lookup"><span data-stu-id="f02cd-194">If there are differences, delete the module.ini file in %ProgramData%\CloudConnector and rerun  `Register-CcAppliance`.</span></span> <span data-ttu-id="f02cd-195">また、適切な実行およびバックアップバージョンにファイルを手動で変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="f02cd-195">You could also modify the file manually to the correct running and backup version.</span></span>
    
- <span data-ttu-id="f02cd-196">**問題: スイッチ-CcVersion コマンドレットを実行して、現在のスクリプトバージョンとは異なる古いバージョンに切り替えた場合、古いバージョンでは高可用性がサポートされません。**</span><span class="sxs-lookup"><span data-stu-id="f02cd-196">**Issue: After you run the Switch-CcVersion cmdlet to switch to an old version which is different from current script version, there is no High Availability support for this old version.**</span></span>
    
    <span data-ttu-id="f02cd-197">**解決策:** たとえば、1.4.1 から1.4.2 にアップグレードしたとします。</span><span class="sxs-lookup"><span data-stu-id="f02cd-197">**Resolution:** For example, you have upgraded from 1.4.1 to 1.4.2.</span></span> <span data-ttu-id="f02cd-198">現在のスクリプトバージョンは、を実行することによって決定され、実行中の `Get-CcVersion` バージョンは、両方が1.4.2 であることを確認でき  `Get-CcRunningVersion` ます。</span><span class="sxs-lookup"><span data-stu-id="f02cd-198">Your current script version, which can be determined by running `Get-CcVersion`, and your running version, which can be determined by running  `Get-CcRunningVersion` are both 1.4.2.</span></span> <span data-ttu-id="f02cd-199">現時点で、実行 `Switch-CcVersion` 中のバージョンを1.4.1 に戻すために実行した場合、古いバージョンでは高可用性がサポートされません。</span><span class="sxs-lookup"><span data-stu-id="f02cd-199">At this time, if you run `Switch-CcVersion` to switch the running version back to 1.4.1, then there will be no High Availability support for this old version.</span></span>
    
    <span data-ttu-id="f02cd-200">完全な高可用性サポートを取得するには、1.4.2 に切り替えて、実行中のバージョンとスクリプトバージョンが同じであることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f02cd-200">To get full High Availability support, please switch back to 1.4.2, so the running version and script version are the same.</span></span> <span data-ttu-id="f02cd-201">1.4.2 展開で問題が発生している場合は、できるだけ早くアンインストールして再インストールしてください。</span><span class="sxs-lookup"><span data-stu-id="f02cd-201">If you are experiencing problems with your 1.4.2 deployment, please uninstall and reinstall it as soon as possible.</span></span>
    
- <span data-ttu-id="f02cd-202">**問題: 中央管理ストア、仲介サーバー、エッジサーバーに対して発行された証明機関証明書または内部証明書の有効期限が近づいているか、侵害されています。**</span><span class="sxs-lookup"><span data-stu-id="f02cd-202">**Issue: Certificate authority certificates or internal certificates issued to Central Management Store, Mediation Server, and Edge Server are near expiration or are compromised.**</span></span>
    
    <span data-ttu-id="f02cd-203">**解決策:** Skype for Business の証明機関証明書は5年間有効です。</span><span class="sxs-lookup"><span data-stu-id="f02cd-203">**Resolution:** Skype for Business certification authority certificates are valid for five years.</span></span> <span data-ttu-id="f02cd-204">中央管理ストア、仲介サーバー、エッジサーバーに対して発行された内部証明書は、2年間有効です。</span><span class="sxs-lookup"><span data-stu-id="f02cd-204">Internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f02cd-205">Cloud Connector バージョン2.0 以降では、Renew-cccacertificate コマンドレットが更新-CcServerCertificate に変更され、コマンドレットが Renew-cccacertificate に変更されました。</span><span class="sxs-lookup"><span data-stu-id="f02cd-205">In Cloud Connector version 2.0 and later, the Renew-CcServerCertificate cmdlet has changed to Update-CcServerCertificate and the Renew-CcCACertificate cmdlet has changed to Update-CcCACertificate.</span></span> 
  
    <span data-ttu-id="f02cd-206">中央管理ストア、仲介サーバー、エッジサーバーに対して発行された内部証明書の有効期限が近づいているか、または危険にさらされている場合は、更新-CcServerCertificate または Update-CcServerCertificate コマンドレットを実行して証明書を更新します。</span><span class="sxs-lookup"><span data-stu-id="f02cd-206">If internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are near expiration or compromised, run the Renew-CcServerCertificate or Update-CcServerCertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="f02cd-207">証明機関の証明書の有効期限が近づいている場合は、Renew-cccacertificate または Renew-cccacertificate コマンドレットを実行して証明書を更新します。</span><span class="sxs-lookup"><span data-stu-id="f02cd-207">If certification authority certificates are near expiration, run the Renew-CcCACertificate or Update-CcCACertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="f02cd-208">**証明機関の証明書が侵害され、サイトにアプライアンスが1つしか存在しない場合は、** 次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f02cd-208">**If certification authority certificates are compromised and there is only one appliance in the site,** perform the following steps:</span></span>
    
1. <span data-ttu-id="f02cd-209">コマンドレットを実行してサービスをドレインし、アプライアンスをメンテナンスモードにします。</span><span class="sxs-lookup"><span data-stu-id="f02cd-209">Run the Enter-CcUpdate cmdlet to drain services and put the appliance in maintenance mode.</span></span>
   
   ```powershell
   Enter-CcUpdate
   ```
   
2. <span data-ttu-id="f02cd-210">次のコマンドレットを実行してリセットし、新しい証明機関の証明書とすべての内部サーバー証明書を作成します。</span><span class="sxs-lookup"><span data-stu-id="f02cd-210">Run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
    <span data-ttu-id="f02cd-211">2.0 より前の Cloud Connector のリリースの場合:</span><span class="sxs-lookup"><span data-stu-id="f02cd-211">For Cloud Connector releases before 2.0:</span></span>
    
    ```powershell
    Reset-CcCACertificate 
    Renew-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

    <span data-ttu-id="f02cd-212">または、Cloud Connector リリース2.0 以降の場合:</span><span class="sxs-lookup"><span data-stu-id="f02cd-212">Or for Cloud Connector release 2.0 and later:</span></span>
    
    ```powershell
    Reset-CcCACertificate 
    Update-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```
    
3. <span data-ttu-id="f02cd-213">ゲートウェイと仲介サーバーの間で TLS が使用されている場合は、アプライアンスから Export-ccrootcertificate コマンドレットを実行して、エクスポートした証明書を PSTN ゲートウェイにインストールします。</span><span class="sxs-lookup"><span data-stu-id="f02cd-213">If TLS is used between the gateway and the Mediation Server, run the Export-CcRootCertificate cmdlet from the appliance, and then install the exported certificate to your PSTN gateways.</span></span> <span data-ttu-id="f02cd-214">また、ゲートウェイで証明書を再発行する必要がある場合もあります。</span><span class="sxs-lookup"><span data-stu-id="f02cd-214">You may also be required to re-issue the certificate on your gateway.</span></span>

   ```powershell
   Export-CcRootCertificate
   ```

4. <span data-ttu-id="f02cd-215">終了-CcUpdate コマンドレットを実行して、サービスを開始し、メンテナンスモードを終了します。</span><span class="sxs-lookup"><span data-stu-id="f02cd-215">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span>

   ```powershell
   Exit-CcUpdate
   ```


    <span data-ttu-id="f02cd-216">**証明機関の証明書が侵害され、サイトに複数のアプライアンスが存在する場合** は、サイト内の各アプライアンスで次の順次手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f02cd-216">**If certification authority certificates are compromised and there are multiple appliances in the site,** perform the following sequential steps on each appliance in the site.</span></span>
    
    <span data-ttu-id="f02cd-217">Microsoft では、ピーク時以外の時間帯にこれらの手順を実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f02cd-217">Microsoft recommends that you perform these steps during non-peak usage times.</span></span>
    
1. <span data-ttu-id="f02cd-218">最初のアプライアンスで、Remove-cccertificationauthorityfile コマンドレットを実行して、ディレクトリ内の CA バックアップファイルをクリーンアップし \<SiteRoot\> ます。</span><span class="sxs-lookup"><span data-stu-id="f02cd-218">On the first appliance, run the Remove-CcCertificationAuthorityFile cmdlet to clean up the CA backup files in the \<SiteRoot\> directory.</span></span>

     ```powershell
     Remove-CcCertificationAuthorityFile
     ```
    
2. <span data-ttu-id="f02cd-219">コマンドレットを実行してサービスをドレインし、各アプライアンスをメンテナンスモードにします。</span><span class="sxs-lookup"><span data-stu-id="f02cd-219">Run the Enter-CcUpdate cmdlet to drain services and put each appliance in maintenance mode.</span></span>

     ```powershell
     Enter-CcUpdate
     ```
    
3. <span data-ttu-id="f02cd-220">最初のアプライアンスで、次のコマンドレットを実行してリセットし、新しい証明機関の証明書とすべての内部サーバー証明書を作成します。</span><span class="sxs-lookup"><span data-stu-id="f02cd-220">On the first appliance, run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
     <span data-ttu-id="f02cd-221">2.0 より前の Cloud Connector のリリースの場合:</span><span class="sxs-lookup"><span data-stu-id="f02cd-221">For Cloud Connector releases before 2.0:</span></span>
    
     ```powershell
     Reset-CcCACertificate
     Renew-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

     <span data-ttu-id="f02cd-222">または、Cloud Connector リリース2.0 以降の場合:</span><span class="sxs-lookup"><span data-stu-id="f02cd-222">Or for Cloud Connector release 2.0 and later:</span></span>
    
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

4. <span data-ttu-id="f02cd-223">最初のアプライアンスで、次のコマンドレットを実行して CA ファイルをフォルダーにバックアップし \<SiteRoot\> ます。</span><span class="sxs-lookup"><span data-stu-id="f02cd-223">On the first appliance, run the following cmdlet to back up the CA files to the \<SiteRoot\> folder.</span></span>
    
     ```powershell
     Backup-CcCertificationAuthority
     ```
   
5. <span data-ttu-id="f02cd-224">同じサイト内の他のすべてのアプライアンスで、次のコマンドを実行して CA バックアップファイルを使用し、すべてのアプライアンスで同じルート証明書が使用されるようにして、新しい証明書を要求します。</span><span class="sxs-lookup"><span data-stu-id="f02cd-224">On all other appliance's in the same site, run the following commands to consume the CA backup files, so that the appliances all use the same root certificate, and then request new certificates.</span></span> 
   
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```
     
6. <span data-ttu-id="f02cd-225">ゲートウェイと仲介サーバーの間で TLS が使用されている場合は、サイト内の任意のアプライアンスから Export-ccrootcertificate コマンドレットを実行して、エクスポートした証明書を PSTN ゲートウェイにインストールします。</span><span class="sxs-lookup"><span data-stu-id="f02cd-225">If TLS is used between the gateway and the Mediation Server, run the Export-CcRootCertificate cmdlet from any appliance in the site, and then install the exported certificate to your PSTN gateways.</span></span> <span data-ttu-id="f02cd-226">また、ゲートウェイで証明書を再発行する必要がある場合もあります。</span><span class="sxs-lookup"><span data-stu-id="f02cd-226">You may also be required to re-issue the certificate on your gateway.</span></span>
  
     ```powershell
     Export-CcRootCertificate
     ```
     
7. <span data-ttu-id="f02cd-227">終了-CcUpdate コマンドレットを実行して、サービスを開始し、メンテナンスモードを終了します。</span><span class="sxs-lookup"><span data-stu-id="f02cd-227">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span> 

     ```powershell
     Exit-CcUpdate
     ```
    
    
- <span data-ttu-id="f02cd-228">**問題: Cloud Connector Management Service ログに "C:\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log" というエラーメッセージが表示されます。 CceService Error: 0: 状態をオンラインに報告しているときに、予期しない例外が発生しました。 CmdletInvocationException: ユーザーのログオンに失敗しました \<Global Tenant Admin\> 。新しい資格情報オブジェクトを作成してください。正しいユーザー名とパスワードを使用していることを確認してください。---\>**</span><span class="sxs-lookup"><span data-stu-id="f02cd-228">**Issue: You receive the following error message in the Cloud Connector Management Service Log, "C:\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log": CceService Error: 0 : Unexpected exception when reporting status to online: System.Management.Automation.CmdletInvocationException: Logon failed for the user \<Global Tenant Admin\>. Please create a new credential object, making sure that you have used the correct user name and password. ---\>**</span></span>
    
    <span data-ttu-id="f02cd-229">**解決策:** Cloud Connector アプライアンスが登録されてから、Microsoft 365 または Office 365 グローバルテナント管理者の資格情報が変更されました。</span><span class="sxs-lookup"><span data-stu-id="f02cd-229">**Resolution:** The Microsoft 365 or Office 365 global tenant admin credentials have been changed since the Cloud Connector appliance was registered.</span></span> <span data-ttu-id="f02cd-230">Cloud Connector アプライアンスでローカルに格納されている資格情報を更新するには、ホストアプライアンスの管理者 PowerShell から次を実行します。</span><span class="sxs-lookup"><span data-stu-id="f02cd-230">To update the locally stored credentials on the Cloud Connector appliance, run the following from Administrator PowerShell on the host appliance:</span></span>
    
  ```powershell
  Set-CcCredential -AccountType TenantAdmin
  ```

- <span data-ttu-id="f02cd-231">**問題: 展開に使用したホストサーバーアカウントのパスワードを変更すると、次のエラーメッセージが表示されます。 "Convertto-securestring-System.security.securestring: キーが指定した状態で使用できません。" というエラーメッセージが表示されます。%ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log または Get-CcCredential コマンドレットを実行しています。**</span><span class="sxs-lookup"><span data-stu-id="f02cd-231">**Issue: After you change the password for the host server account you used for the deployment, you receive the following error message: "ConvertTo-SecureString : Key not valid for use in specified state." in %ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log or while running the Get-CcCredential cmdlet.**</span></span>
    
    <span data-ttu-id="f02cd-232">**解決策:** すべての Cloud Connector 資格情報は、次のファイルに格納されます。 "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> 。xml "。</span><span class="sxs-lookup"><span data-stu-id="f02cd-232">**Resolution:** All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="f02cd-233">ホストサーバーのパスワードが変更された場合は、ローカルに格納されている資格情報を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f02cd-233">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
    
    <span data-ttu-id="f02cd-234">**Cloud connector バージョン1.4.2 を実行** している場合は、次の手順に従って、すべての cloud connector パスワードを再生成します。</span><span class="sxs-lookup"><span data-stu-id="f02cd-234">**If you are running Cloud Connector version 1.4.2,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  1. <span data-ttu-id="f02cd-235">ホストサーバーを再起動します。</span><span class="sxs-lookup"><span data-stu-id="f02cd-235">Restart the host server.</span></span>
    
  2. <span data-ttu-id="f02cd-236">次のファイルを \<CurrentUser\> 削除します。 "%SystemDrive%\Programdata\Cloudconnector\credentials.xml "。</span><span class="sxs-lookup"><span data-stu-id="f02cd-236">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
  3. <span data-ttu-id="f02cd-237">管理者として PowerShell コンソールを起動してから、説明に従ってパスワードを再入力するには、「Register-CcAppliance-Local」を実行します。</span><span class="sxs-lookup"><span data-stu-id="f02cd-237">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="f02cd-238">Cloud Connector を展開する前に入力したのと同じパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="f02cd-238">Enter the same passwords you entered before for the Cloud Connector deployment.</span></span>
    
     <span data-ttu-id="f02cd-239">**Cloud connector バージョン2.0 以降を実行** している場合は、次の手順に従って、すべての cloud connector パスワードを再生成します。</span><span class="sxs-lookup"><span data-stu-id="f02cd-239">**If you are running Cloud Connector version 2.0 or later,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  4. <span data-ttu-id="f02cd-240">ホストサーバーを再起動します。</span><span class="sxs-lookup"><span data-stu-id="f02cd-240">Restart the host server.</span></span>
    
  5. <span data-ttu-id="f02cd-241">次のファイルを \<CurrentUser\> 削除します。 "%SystemDrive%\Programdata\Cloudconnector\credentials.xml "。</span><span class="sxs-lookup"><span data-stu-id="f02cd-241">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" .</span></span>
    
  6. <span data-ttu-id="f02cd-242">管理者として PowerShell コンソールを起動してから、説明に従ってパスワードを再入力するには、「Register-CcAppliance-Local」を実行します。</span><span class="sxs-lookup"><span data-stu-id="f02cd-242">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> 
    
     <span data-ttu-id="f02cd-243">キャッシュされたパスワードファイルが Cloud Connector バージョン1.4.2 で生成されている場合は、CceService パスワードの入力を求められたときに、VMAdmin パスワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="f02cd-243">If the cached password file was generated with Cloud Connector version 1.4.2, use the VMAdmin password for the CceService password when prompted.</span></span> <span data-ttu-id="f02cd-244">他のすべてのアカウントに対して、Cloud Connector の展開の前に入力したパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="f02cd-244">Enter the same password you entered before for the Cloud Connector deployment for all other accounts.</span></span>
    
     <span data-ttu-id="f02cd-245">キャッシュされたパスワードファイルが Cloud Connector バージョン1.4.2 を使用して生成され、DomainAdmin と VMAdmin のパスワードが異なる場合は、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f02cd-245">If the cached password file was generated with Cloud Connector version 1.4.2 and the DomainAdmin and VMAdmin passwords are different, you must perform the following steps:</span></span>
    
  7. <span data-ttu-id="f02cd-246">Set-CcCredential-AccountType DomainAdmin を次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="f02cd-246">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
  8. <span data-ttu-id="f02cd-247">古いアカウントの資格情報の入力を求められたら、CceService パスワードに使用した資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="f02cd-247">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
  9. <span data-ttu-id="f02cd-248">新しいアカウントの資格情報の入力を求められたら、前に使用した DomainAdmin パスワードのパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="f02cd-248">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
     <span data-ttu-id="f02cd-249">キャッシュされたパスワードファイルが Cloud Connector バージョン2.0 以降で生成された場合、既定では、VmAdmin と DomainAdmin は CceService と同じパスワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="f02cd-249">If the cached password file was generated with Cloud Connector version 2.0 or later, by default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="f02cd-250">DomainAdmin および VMAdmin のパスワードを変更した場合は、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f02cd-250">If you changed the DomainAdmin and VMAdmin passwords, you must perform the following steps:</span></span>
    
  10. <span data-ttu-id="f02cd-251">Set-CcCredential-AccountType DomainAdmin を次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="f02cd-251">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
       1. <span data-ttu-id="f02cd-252">古いアカウントの資格情報の入力を求められたら、CceService パスワードに使用した資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="f02cd-252">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="f02cd-253">新しいアカウントの資格情報の入力を求められたら、前に使用した DomainAdmin パスワードのパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="f02cd-253">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
  11. <span data-ttu-id="f02cd-254">Set-CcCredential-AccountType VmAdmin を次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="f02cd-254">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
       1. <span data-ttu-id="f02cd-255">古いアカウントの資格情報の入力を求められたら、CceService パスワードに使用した資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="f02cd-255">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="f02cd-256">新しいアカウントの資格情報の入力を求められたら、以前使用した VmAdmin パスワードのパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="f02cd-256">When prompted for the new account credential, enter the password for the VmAdmin password you used before.</span></span> 
    
- <span data-ttu-id="f02cd-257">**問題: Cloud Connector バージョン2.1 以降で、アプライアンスで Register-CcAppliance またはその他のコマンドレットを実行すると、次のようなエラーメッセージが表示されます。このオブジェクトには、プロパティ ' Common ' が見つかりません。プロパティが存在することを確認します。C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1: 681 char:14 "**</span><span class="sxs-lookup"><span data-stu-id="f02cd-257">**Issue: With Cloud Connector version 2.1 and later, when running Register-CcAppliance or other cmdlets on the appliance, you receive an error message such as: "For Each-Object : The property 'Common' cannot be found on this object. Verify that the property exists. At C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char:14"**</span></span>
    
    <span data-ttu-id="f02cd-258">**解決策:** Cloud Connector 2.1 以降では、.NET Framework 4.6.1 以降が必要です。</span><span class="sxs-lookup"><span data-stu-id="f02cd-258">**Resolution:** Cloud Connector 2.1 and later requires .NET Framework 4.6.1 or later.</span></span> <span data-ttu-id="f02cd-259">アプライアンスの .NET Framework をバージョン4.6.1 以降に更新して、コマンドレットを再度実行してください。</span><span class="sxs-lookup"><span data-stu-id="f02cd-259">Please update .NET Framework on the appliance to version 4.6.1 or later and run the cmdlet(s) again.</span></span>

- <span data-ttu-id="f02cd-260">**問題: Cloud Connector エディション2.1 で、インストール-CcAppliance を実行すると、"新しいインスタンスをインストールできませんでした:" というエラーメッセージが表示されます。これは、文字列のみを値として使用して XmlNode のプロパティを設定することができるため、"状態を設定できません" です。**</span><span class="sxs-lookup"><span data-stu-id="f02cd-260">**Issue: With Cloud Connector Edition 2.1, when running Install-CcAppliance, you receive an error message such as: "Failed to install new instance with error: Cannot set "State" because only strings can be used as values to set XmlNode properties"**</span></span>

   <span data-ttu-id="f02cd-261">**解決策:** Cloudconnector.ini の [Common] セクションで、次のように「State」 config を追加してください。 CountryCode = US State = WA City = Redmond</span><span class="sxs-lookup"><span data-stu-id="f02cd-261">**Resolution:** In Cloudconnector.ini, under the [Common] section, please add the “State” config as below:  CountryCode=US  State=WA  City=Redmond</span></span>

   <span data-ttu-id="f02cd-262">"State" 行に値を設定することは必須ではありませんが、"State" 行を Cloudconnector.ini ファイルから削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="f02cd-262">It is not mandatory for the "State" line to have value, however the "State" line cannot be removed from the Cloudconnector.ini file.</span></span>

- <span data-ttu-id="f02cd-263">**問題: "WindowsImage: WindowsImage に失敗しました" というエラーメッセージが表示されます。Cloud Connector エディションをインストールまたはアップグレードするときに、エラーコード = 0xc1550115 "が返されます。**</span><span class="sxs-lookup"><span data-stu-id="f02cd-263">**Issue: You receive the following error message "Dismount-WindowsImage : Dismount-WindowsImage failed. Error code = 0xc1550115" when installing or upgrading Cloud Connector Edition.**</span></span>
    
    <span data-ttu-id="f02cd-264">**解決策:** 管理者として PowerShell コンソールを起動し、"DISM-Cleanup-Wim '" を実行します。</span><span class="sxs-lookup"><span data-stu-id="f02cd-264">**Resolution:** Launch a PowerShell console as administrator, run "DISM -Cleanup-Wim'".</span></span> <span data-ttu-id="f02cd-265">これにより、すべての troubled 画像がクリーンアップされます。</span><span class="sxs-lookup"><span data-stu-id="f02cd-265">This will clean up all troubled images.</span></span> <span data-ttu-id="f02cd-266">もう一度インストール-CcAppliance を実行するか、bits が自動的にアップグレードされるのを待ちます。</span><span class="sxs-lookup"><span data-stu-id="f02cd-266">Run Install-CcAppliance again or wait for the bits to automatically upgrade.</span></span>
    
- <span data-ttu-id="f02cd-267">**問題: HA 環境での最初の Cloud Connector アプライアンスの展開が失敗する**</span><span class="sxs-lookup"><span data-stu-id="f02cd-267">**Issue: Deployment of the first Cloud Connector appliance in an HA environment fails**</span></span>
    
    <span data-ttu-id="f02cd-268">**解決策:** 実行する手順は、展開が失敗した理由によって異なります。</span><span class="sxs-lookup"><span data-stu-id="f02cd-268">**Resolution:** The steps you take depend on the reason the deployment failed:</span></span>
    
  - <span data-ttu-id="f02cd-269">最初の Cloud Connector アプライアンスに障害が発生し、障害の原因を特定できない場合は、展開が成功するまでアプライアンスを再度インストールして、他のアプライアンスをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f02cd-269">If the first Cloud Connector appliance fails and you cannot determine the reason for the failure, you must install the appliance again until the deployment is successful, and then install the other appliances.</span></span>
    
  - <span data-ttu-id="f02cd-270">最初の Cloud Connector アプライアンスが、外部証明書の問題などの軽微な問題で失敗した場合は、アプライアンスを再インストールしなくても問題を解決できる場合があります。</span><span class="sxs-lookup"><span data-stu-id="f02cd-270">If the first Cloud Connector appliance fails with a minor issue, such as an external certificate issue, you might be able to fix the problem without re-installing the appliance.</span></span> <span data-ttu-id="f02cd-271">その後、テナントのリモート PowerShell を使用して、展開を次のようにマークできます。</span><span class="sxs-lookup"><span data-stu-id="f02cd-271">You can then use tenant remote PowerShell to mark the deployment as successful as follows.</span></span> <span data-ttu-id="f02cd-272">(最初の展開が成功した場合は、次の手順を使用することもできますが、何らかの理由で、クラウドコネクタが成功として展開を報告できない場合もあります)。</span><span class="sxs-lookup"><span data-stu-id="f02cd-272">(You can also use the following steps if the first deployment was successful, but, for some reason, Cloud Connector fails to report the deployment as a success.)</span></span>
    
  - <span data-ttu-id="f02cd-273">最初の Cloud Connector アプライアンスの Id (GUID) を取得するには、CsHybridPSTNAppliance コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="f02cd-273">To get the Identity (GUID) of the first Cloud Connector appliance, run the Get-CsHybridPSTNAppliance cmdlet.</span></span>
    
  - <span data-ttu-id="f02cd-274">正常に展開された状態でアプライアンスをマークするには、次のように CsCceApplianceDeploymentStatus を実行します。</span><span class="sxs-lookup"><span data-stu-id="f02cd-274">To mark the appliance as successfully deployed, run the Set-CsCceApplianceDeploymentStatus as follows:</span></span>
    
  ```powershell
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- <span data-ttu-id="f02cd-275">**問題: ホストサーバーまたは仮想マシンで Windows 更新プログラムを手動で確認してインストールする必要があります。**</span><span class="sxs-lookup"><span data-stu-id="f02cd-275">**Issue: You need to check for and install Windows updates manually on the host server or virtual machines.**</span></span>
    
   <span data-ttu-id="f02cd-276">**解決策:** Skype for Business Cloud Connector エディションで提供される自動 OS 更新プログラムを利用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f02cd-276">**Resolution:** We recommend that you take advantage of automated OS updates provided by Skype for Business Cloud Connector Edition.</span></span> <span data-ttu-id="f02cd-277">アプライアンスがオンライン管理用に登録され、自動 OS 更新が有効になると、ホストサーバーと仮想マシンは、OS 更新時間ウィンドウの設定に従って自動的に Windows 更新プログラムをチェックしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="f02cd-277">After an appliance is registered for online management and auto OS update is enabled, the host server and virtual machines will check and install Windows Updates automatically according to the OS update time window settings.</span></span>
    
   <span data-ttu-id="f02cd-278">Windows 更新プログラムを手動で確認してインストールする必要がある場合は、展開の種類に該当するこのセクションの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f02cd-278">If you need to check for and install Windows Updates manually, follow the steps in this section that apply to your type of deployment.</span></span> <span data-ttu-id="f02cd-279">更新に必要なダウンタイムを最小限に抑えるために、ホストサーバーと仮想マシンの両方を同時に更新することを計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f02cd-279">You should plan on updating both the host server and the virtual machines running on it at the same time to minimize the amount of down time necessary for the updates.</span></span>
    
   <span data-ttu-id="f02cd-280">必要に応じて、Windows Server Update Services (WSUS) サーバーを使用して、Cloud Connector サーバーに更新を提供することができます。</span><span class="sxs-lookup"><span data-stu-id="f02cd-280">If you prefer, you can use a Windows Server Update Services (WSUS) server to provide updates to Cloud Connector servers.</span></span> <span data-ttu-id="f02cd-281">Windows Update を自動的にインストールし **ない** ように構成してください。</span><span class="sxs-lookup"><span data-stu-id="f02cd-281">Just be sure to configure the Windows Update to **not** install automatically.</span></span>
    
   <span data-ttu-id="f02cd-282">Cloud Connector の展開を手動で更新する方法については、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f02cd-282">For information about how to manually update your Cloud Connector deployment, see the following section.</span></span>
    
- <span data-ttu-id="f02cd-283">**問題: Cloud Connector が新しいビルドに更新されても、Cloud Connector コマンドレットは更新されません。**</span><span class="sxs-lookup"><span data-stu-id="f02cd-283">**Issue: When Cloud Connector updates to a new build, Cloud Connector cmdlets are not updated.**</span></span> <span data-ttu-id="f02cd-284">これは、自動更新の実行時に PowerShell ウィンドウを開いたままになっている場合に発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="f02cd-284">This sometimes happens if a PowerShell window is left open when automatic update occurs.</span></span>
    
  <span data-ttu-id="f02cd-285">**解決策:** 更新されたコマンドレットを読み込むには、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f02cd-285">**Resolution:** To load the updated cmdlets, you can do either of the following steps:</span></span>
    
   - <span data-ttu-id="f02cd-286">Cloud Connector アプライアンスで PowerShell を閉じてから、PowerShell をもう一度開きます。</span><span class="sxs-lookup"><span data-stu-id="f02cd-286">Close PowerShell on the Cloud Connector appliance, and then reopen PowerShell.</span></span>
    
     - <span data-ttu-id="f02cd-287">または、Import モジュール CloudConnector-Force を実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="f02cd-287">Or, you can run Import-Module CloudConnector -Force.</span></span> 
 
-   <span data-ttu-id="f02cd-288">**問題: "Stop-CsWindowsService ' という用語は、コマンドレット、関数、スクリプトファイル、または実行可能なプログラムの名前として認識されません。" というメッセージが返されます。**</span><span class="sxs-lookup"><span data-stu-id="f02cd-288">**Issue: "The term 'Stop-CsWindowsService' is not recognized as the name of a cmdlet, function, script file, or operable program." error when attempting to run Enter-CcUpdate cmdlet.**</span></span>

    <span data-ttu-id="f02cd-289">**解決策:** $HOME \AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache ファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="f02cd-289">**Resolution:** Delete the $HOME\AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache file.</span></span>
<span data-ttu-id="f02cd-290">このファイルは、PowerShell によって検出されたモジュールのコマンドレットのキャッシュとして作成されるので、実際に処理が遅くなるように毎回すべてのモジュールを再分析する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f02cd-290">PowerShell creates this file as a cache of cmdlets from modules that it finds so that it doesn’t have to re-analyze all the modules each time as that would make things really slow.</span></span> <span data-ttu-id="f02cd-291">多くの場合、キャッシュから戻ってきたときに、誤って PowerShell に結果を提供するファイルの破損が発生しました。</span><span class="sxs-lookup"><span data-stu-id="f02cd-291">Most likely, there was some file corruption that provided misleading results to PowerShell when it was reading back from that cache.</span></span>

-   <span data-ttu-id="f02cd-292">**問題: "インポート-モジュール CloudConnector" でエラー "Import-モジュールが生成されました" が、モジュールディレクトリに有効なモジュールファイルが見つからないため、読み込まれませんでした "**</span><span class="sxs-lookup"><span data-stu-id="f02cd-292">**Issue: “Import-Module CloudConnector” generates error “Import-Module: The specified module “CloudConnector” was not loaded because no valid module file was found in any module directory”**</span></span>

    <span data-ttu-id="f02cd-293">**解決方法:**</span><span class="sxs-lookup"><span data-stu-id="f02cd-293">**Resolution:**</span></span>
    - <span data-ttu-id="f02cd-294">CloudConnector モジュールが c:\Program Files\WindowsPowerShell\Modules の下に存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="f02cd-294">Validate that indeed the CloudConnector module exists under c:\Program Files\WindowsPowerShell\Modules</span></span>
    
    - <span data-ttu-id="f02cd-295">この位置の下に CloudConnector モジュールが存在することを検証した後、モジュールの場所へのパスを格納する PSModulePath 環境変数を変更できます。</span><span class="sxs-lookup"><span data-stu-id="f02cd-295">After validating that CloudConnector module exists under this location, the PSModulePath environment variable storing the path to the locations of the modules can be changed:</span></span>
    
     <span data-ttu-id="f02cd-296">a.</span><span class="sxs-lookup"><span data-stu-id="f02cd-296">a.</span></span> <span data-ttu-id="f02cd-297">一時的な変更: 管理者として Powershell を起動し、次のコマンドを実行します。 $env:P SModulePath = $env:P SModulePath + ";C:\Program Files\WindowsPowerShell\Modules\"</span><span class="sxs-lookup"><span data-stu-id="f02cd-297">Temporary change: Start Powershell as an Administrator and run the following command: $env:PSModulePath = $env:PSModulePath + ";C:\Program Files\WindowsPowerShell\Modules\"</span></span>
        
     <span data-ttu-id="f02cd-298">b.</span><span class="sxs-lookup"><span data-stu-id="f02cd-298">b.</span></span> <span data-ttu-id="f02cd-299">永続的な変更では、管理者として PowerShell を起動し、次のコマンドを1つずつ実行します。 $CurrentValue = [Environment]::: GetEnvironmentVariable ("PSModulePath", "Machine") SetEnvironmentVariable ("PSModulePath", $CurrentValue + ";C:\Program Files\WindowsPowerShell\Modules "," Machine ")</span><span class="sxs-lookup"><span data-stu-id="f02cd-299">For persistent change, Start PowerShell as an Administrator and run the following commands, one by one: $CurrentValue = [Environment]::GetEnvironmentVariable("PSModulePath", "Machine") SetEnvironmentVariable("PSModulePath", $CurrentValue + "; C:\Program Files\WindowsPowerShell\Modules", "Machine")</span></span>

    
## <a name="install-windows-updates-manually"></a><span data-ttu-id="f02cd-300">Windows 更新プログラムを手動でインストールする</span><span class="sxs-lookup"><span data-stu-id="f02cd-300">Install Windows updates manually</span></span>

<span data-ttu-id="f02cd-301">環境で自動更新を使用しない場合は、次の手順に従って、Windows 更新プログラムを手動で確認して適用します。</span><span class="sxs-lookup"><span data-stu-id="f02cd-301">If you do not want to use automatic updates in your environment, follow these steps to manually check for and apply Windows updates.</span></span> <span data-ttu-id="f02cd-302">Windows 更新プログラムを確認してインストールするには、サーバーの再起動が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="f02cd-302">Checking for and installing Windows updates may require a server restart.</span></span> <span data-ttu-id="f02cd-303">ホストサーバーを再起動すると、ユーザーはクラウドコネクタを使用して通話を発信または受信できなくなります。</span><span class="sxs-lookup"><span data-stu-id="f02cd-303">When a host server is restarting, users will not be able to use Cloud Connector to place or receive calls.</span></span> <span data-ttu-id="f02cd-304">更新プログラムが実行されるタイミングを制御する更新プログラムを手動で確認してインストールし、必要に応じて、サービスの中断を回避するためにコンピューターを再起動することができます。</span><span class="sxs-lookup"><span data-stu-id="f02cd-304">You can manually check for and install updates to control when the updates take place, and then restart the machines as needed during times you choose to avoid disruption of services.</span></span>
  
<span data-ttu-id="f02cd-305">更新プログラムを手動で確認するには、各ホストサーバーに接続し、[ **コントロールパネル]** を開きます。</span><span class="sxs-lookup"><span data-stu-id="f02cd-305">To manually check for updates, connect to each host server and open the **Control Panel**.</span></span> <span data-ttu-id="f02cd-306">[ **システムとセキュリティ] [ \> Windows Update**] を選択し、環境に合わせて更新プログラムとサーバーの再起動を管理します。</span><span class="sxs-lookup"><span data-stu-id="f02cd-306">Select **System and Security \>Windows Update**, and then manage the updates and server restarts as appropriate for your environment.</span></span>
  
- <span data-ttu-id="f02cd-307">サイトにアプライアンスが1つしかない場合は、各仮想マシンに接続して [ **コントロールパネル]** を開きます。</span><span class="sxs-lookup"><span data-stu-id="f02cd-307">If there is only one appliance in the site, connect to each virtual machine and open the **Control Panel**.</span></span> <span data-ttu-id="f02cd-308">[ **システムとセキュリティ] [ \> Windows Update**] を選択し、必要に応じて更新プログラムとサーバーの再起動を構成します。</span><span class="sxs-lookup"><span data-stu-id="f02cd-308">Select **System and Security \>Windows Update**, and then configure the updates and server restarts as appropriate.</span></span>
    
- <span data-ttu-id="f02cd-309">サイト内に複数のアプライアンスが存在する場合、更新中に更新中または再起動されているインスタンスはユーザーがアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="f02cd-309">If there are more than one appliance in the site, the instance being updated and restarted cannot be accessed by users during the updates.</span></span> <span data-ttu-id="f02cd-310">更新が完了した後、すべての仮想マシンとすべての Skype for Business サービスが仮想マシンで開始されるまで、ユーザーは展開内の他のインスタンスに接続します。</span><span class="sxs-lookup"><span data-stu-id="f02cd-310">Users will connect to other instances in the deployment until all virtual machines and all Skype for Business services start on the virtual machines after the updates are completed.</span></span> <span data-ttu-id="f02cd-311">サービスの中断を回避するには、更新プログラムを適用している間に、そのインスタンスを HA から削除して、完了した時点で復元することができます。</span><span class="sxs-lookup"><span data-stu-id="f02cd-311">To avoid any potential disruption to service, you can remove the instance from HA while you apply the updates, and then restore it when complete.</span></span> <span data-ttu-id="f02cd-312">これを行うには、以下のようにします:</span><span class="sxs-lookup"><span data-stu-id="f02cd-312">To do so:</span></span>
    
1. <span data-ttu-id="f02cd-313">各ホストサーバーで、管理者として PowerShell コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="f02cd-313">On each host server, open a PowerShell console as administrator.</span></span>
    
2. <span data-ttu-id="f02cd-314">次のコマンドレットを使用して、HA からインスタンスを削除します。</span><span class="sxs-lookup"><span data-stu-id="f02cd-314">Remove the instance from HA with the following cmdlet:</span></span>
    
   ```powershell
   Enter-CcUpdate
   ```

3. 
    
    <span data-ttu-id="f02cd-315">単一インスタンスの手順に従って、更新プログラムを手動で適用し、仮想マシンを再起動します。</span><span class="sxs-lookup"><span data-stu-id="f02cd-315">Follow the steps for a single instance to manually apply the updates and restart the virtual machine.</span></span>
    
4. <span data-ttu-id="f02cd-316">次のコマンドレットを使用して、インスタンスを HA に戻します。</span><span class="sxs-lookup"><span data-stu-id="f02cd-316">Set the instance back to HA with the following cmdlet:</span></span>
    
   ```powershell
   Exit-CcUpdate
   ```

<span data-ttu-id="f02cd-317">複数サイト展開の場合は、展開内の各サイトに対して1つのサイトの手順を実行し、一度に1つのサイトに対して更新プログラムを適用します。</span><span class="sxs-lookup"><span data-stu-id="f02cd-317">For multi-site deployments, follow the steps for a single site for each site in the deployment, applying updates to one site at a time.</span></span>
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a><span data-ttu-id="f02cd-318">Cloud Connector ホストコンピューターにウイルス対策ソフトウェアをインストールするときのヒント</span><span class="sxs-lookup"><span data-stu-id="f02cd-318">Tips when installing anti-virus software on the Cloud Connector host machine</span></span>

<span data-ttu-id="f02cd-319">Cloud Connector ホストコンピューターにウイルス対策ソフトウェアをインストールする必要がある場合は、次の除外を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f02cd-319">If you need to install anti-virus software on the Cloud Connector host machine, you need to add the following exclusions:</span></span>
  
- <span data-ttu-id="f02cd-320">各コンピューターのローカルアプライアンスディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="f02cd-320">Local Appliance Directory on each machine.</span></span>
    
- <span data-ttu-id="f02cd-321">各コンピューター上のリモートサイトディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="f02cd-321">Remote Site Directory on each machine.</span></span>
    
- <span data-ttu-id="f02cd-322">コンピューター上のローカルサイトディレクトリは、共有サイトのルートフォルダーをホストします。</span><span class="sxs-lookup"><span data-stu-id="f02cd-322">Local Site Directory on the machine hosts the shared site root folder.</span></span>
    
- <span data-ttu-id="f02cd-323">%ProgramFiles%\Skype for Business Cloud Connector エディション</span><span class="sxs-lookup"><span data-stu-id="f02cd-323">%ProgramFiles%\Skype for Business Cloud Connector Edition</span></span>
    
- <span data-ttu-id="f02cd-324">%ALLUSERSPROFILE%\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="f02cd-324">%ALLUSERSPROFILE%\CloudConnector</span></span>
    
- <span data-ttu-id="f02cd-325">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="f02cd-325">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span></span>
    
- <span data-ttu-id="f02cd-326">プロセス Microsoft.Rtc.CCE.ManagementService.exe。</span><span class="sxs-lookup"><span data-stu-id="f02cd-326">The process Microsoft.Rtc.CCE.ManagementService.exe.</span></span>
