---
title: Cloud Connector 展開をトラブルシューティングする
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/5/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e6cf58cc-dbd9-4f35-a51a-3e2fea71b5a5
description: コネクタ Edition のクラウド展開のトラブルシューティングを行います。
ms.openlocfilehash: a80d6977ff565d5d06f2487e5fb3ab8293b5e000
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30894467"
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a><span data-ttu-id="1040a-103">Cloud Connector 展開をトラブルシューティングする</span><span class="sxs-lookup"><span data-stu-id="1040a-103">Troubleshoot your Cloud Connector deployment</span></span>
 
<span data-ttu-id="1040a-104">コネクタ Edition のクラウド展開のトラブルシューティングを行います。</span><span class="sxs-lookup"><span data-stu-id="1040a-104">Troubleshoot your Cloud Connector Edition deployment.</span></span>
  
<span data-ttu-id="1040a-p101">このトピックでは、Cloud Connector Edition の展開に関する一般的な問題の解決策について説明します。公衆交換電話網 (PSTN) による通話で問題が発生する場合は、このトピックで説明する手順に従って調査することができます。</span><span class="sxs-lookup"><span data-stu-id="1040a-p101">This topic describes solutions to common issues with Cloud Connector Edition deployments. If you are experiencing issues with calls to and from the Public Switched Telephone Network (PSTN), you can investigate by following the solutions described in this topic.</span></span>
  
<span data-ttu-id="1040a-107">クラウドのコネクタは、自動的にいくつかの問題を解決するための組み込みのメカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="1040a-107">Cloud Connector provides built-in mechanisms for automatically resolving some issues.</span></span> <span data-ttu-id="1040a-108">自動検出プロセスでは、クラウド コネクタ アプライアンスでは、潜在的な問題を探し、管理者の介入を必要とせず、それらの問題を解決するための是正措置は、可能であれば、です。</span><span class="sxs-lookup"><span data-stu-id="1040a-108">An automatic detection process looks for potential issues with the Cloud Connector appliances, and, if possible, takes corrective action to resolve those issues without the need for administrator intervention.</span></span> <span data-ttu-id="1040a-109">検出プロセスは次のように機能します。</span><span class="sxs-lookup"><span data-stu-id="1040a-109">The detection process works as follows:</span></span>
  
- <span data-ttu-id="1040a-110">**検出シーケンス:** コネクタの管理をクラウド サービスでは、60 秒ごとに、アプライアンスがダウンするかどうかを検出するため、処理を実行します。</span><span class="sxs-lookup"><span data-stu-id="1040a-110">**Detection sequence:** The Cloud Connector Management service runs a process every 60 seconds for detecting whether an appliance is down.</span></span> <span data-ttu-id="1040a-111">クラウド コネクタ バージョン 2.0 以降では、検出プロセスで、Skype のビジネスの社内ネットワークのスイッチの PowerShell へ接続するコネクタのクラウドのマシンです。2.0 より前のバージョンでは、検出プロセスは、クラウドのコネクタの管理スイッチを使用します。</span><span class="sxs-lookup"><span data-stu-id="1040a-111">In Cloud Connector version 2.0 and later, the detection process uses the Skype for Business Corpnet switch for making PowerShell connections to the Cloud Connector machines; for versions previous to 2.0, the detection process uses the Cloud Connector management switch.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1040a-112">成功させるため、自動回復の必要があります、ホストと仮想マシン間のネットワーク接続ホストのネットワーク ・ スイッチ経由で。</span><span class="sxs-lookup"><span data-stu-id="1040a-112">For automatic recovery to succeed, there must be network connectivity between the host and virtual machines over the host network switch.</span></span> <span data-ttu-id="1040a-113">自動検出されることを確認するのにはネットワーク接続を確認することを確認して、回復を成功させるためです。</span><span class="sxs-lookup"><span data-stu-id="1040a-113">Be sure to check network connectivity to ensure that automatic detection and recovery can succeed.</span></span> 
  
- <span data-ttu-id="1040a-114">**の監視:** クラウド コネクタ バージョン 2.0 以降では、次のサービスを監視します。</span><span class="sxs-lookup"><span data-stu-id="1040a-114">**Monitoring:** The following services are monitored in Cloud Connector version 2.0 and later:</span></span>
    
  - <span data-ttu-id="1040a-115">クラウド コネクタ企業またはインターネットの仮想スイッチには、仮想マシンは接続されていません。</span><span class="sxs-lookup"><span data-stu-id="1040a-115">Virtual Machines are not connected to the Cloud Connector Corporate or Internet virtual switches</span></span>
    
  - <span data-ttu-id="1040a-116">仮想マシンが保存されているか停止している状態では</span><span class="sxs-lookup"><span data-stu-id="1040a-116">Virtual Machines are in a saved or stopped status</span></span>
    
  - <span data-ttu-id="1040a-117">中央管理サーバーのサービス: レプリカ、マスター</span><span class="sxs-lookup"><span data-stu-id="1040a-117">Central Management Server services: REPLICA, MASTER</span></span>
    
  - <span data-ttu-id="1040a-118">仲介サーバー サービス: レプリカ、RTCSRV と MEDSVC</span><span class="sxs-lookup"><span data-stu-id="1040a-118">Mediation Server services: REPLICA, RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="1040a-119">エッジ サーバー サービス: レプリカ、RTCSRV、RTCDATAPROXY、RTCMRAUTH、RTCMEDIARELAY</span><span class="sxs-lookup"><span data-stu-id="1040a-119">Edge Server services: REPLICA, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY</span></span>
    
  - <span data-ttu-id="1040a-120">エッジ サーバーでは、仲介サーバー上の CS RTCMEDSRV CS RTCSRV のルールが無効になってファイアウォールを受信します。</span><span class="sxs-lookup"><span data-stu-id="1040a-120">Inbound firewall rules are disabled for CS RTCSRV on Edge server, CS RTCMEDSRV on Mediation server</span></span>
    
    <span data-ttu-id="1040a-121">クラウド コネクタ バージョン 1.4.2 では、次のサービスのみが監視されます。</span><span class="sxs-lookup"><span data-stu-id="1040a-121">In Cloud Connector version 1.4.2, only the following services are monitored:</span></span>
    
  - <span data-ttu-id="1040a-122">仲介サーバー サービス: RTCSRV と MEDSVC</span><span class="sxs-lookup"><span data-stu-id="1040a-122">Mediation Server services: RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="1040a-123">エッジ サーバー サービス: RTCSRV</span><span class="sxs-lookup"><span data-stu-id="1040a-123">Edge Server service: RTCSRV</span></span>
    
- <span data-ttu-id="1040a-124">**リカバリ ・ プロセス:** 監視対象サービスが停止した場合、アプライアンスが値下げを実行し、サービスが停止され、すべての問題を解決するまでに手動でマークを実行します。</span><span class="sxs-lookup"><span data-stu-id="1040a-124">**Recovery process:** If any monitored services are down, an appliance is marked down, and services are stopped and marked manual until all issues can be resolved.</span></span> <span data-ttu-id="1040a-125">これにより、呼び出しの失敗の原因となるアプライアンスへのルーティングからの呼び出しができなくなります。</span><span class="sxs-lookup"><span data-stu-id="1040a-125">This will prevent calls from routing to an appliance that may cause call failures.</span></span>
    
    <span data-ttu-id="1040a-126">コネクタの管理をクラウド サービスとして次のように自動回復を再試行します。</span><span class="sxs-lookup"><span data-stu-id="1040a-126">The Cloud Connector Management service will retry automatic recovery as follows</span></span>
    
  - <span data-ttu-id="1040a-127">最初の再試行の間隔は、10 秒ごとに 1 時間の間隔の最大時間です。</span><span class="sxs-lookup"><span data-stu-id="1040a-127">The initial retry interval is every ten seconds with a maximum interval time of one hour.</span></span>
    
  - <span data-ttu-id="1040a-128">最初の 3 つの回復の試行間隔の時間は 10 秒です。</span><span class="sxs-lookup"><span data-stu-id="1040a-128">For the first three recovery attempts, the interval time is 10 seconds.</span></span> <span data-ttu-id="1040a-129">前の間隔の時間の 2 倍、4 つ目の再試行の開始、間隔の時間が増加します。</span><span class="sxs-lookup"><span data-stu-id="1040a-129">Starting from the fourth retry, the interval time increases by two times the previous interval time.</span></span> <span data-ttu-id="1040a-130">やなどの 4 つ目の再試行は 40 秒、5 分、20 秒間で発生するように。</span><span class="sxs-lookup"><span data-stu-id="1040a-130">For example, the fourth retry will occur in 20 seconds, the fifth in 40 seconds, and so on.</span></span> 
    
  - <span data-ttu-id="1040a-131">1 時間の間隔を最大に達すると、1 時間あたり 1 回の再試行が続行されます。</span><span class="sxs-lookup"><span data-stu-id="1040a-131">When the maximum interval time of one hour is reached, retries will continue once per hour.</span></span>
    
  - <span data-ttu-id="1040a-132">回復が成功した場合は、間隔、再試行カウントの初期値に設定されています。</span><span class="sxs-lookup"><span data-stu-id="1040a-132">When recovery is successful, the interval and retry counts are set to their initial values.</span></span>
    
  - <span data-ttu-id="1040a-133">管理サービスを再起動すると、間隔、再試行カウントの初期値にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="1040a-133">If the Management service is restarted, the interval and retry counts are reset to their initial values.</span></span>
    
## <a name="troubleshooting"></a><span data-ttu-id="1040a-134">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="1040a-134">Troubleshooting</span></span>

<span data-ttu-id="1040a-135">一般的に見られる問題の解決方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="1040a-135">Following are solutions to commonly encountered issues:</span></span>
  
- <span data-ttu-id="1040a-136">**問題: 展開スクリプトを実行すると、展開が失敗するか、応答しなくなる。各 VM にログインすると、管理/内部/外部 NIC の IP アドレスがないか、正しくない。**</span><span class="sxs-lookup"><span data-stu-id="1040a-136">**Issue: Deployment fails or stops responding when running the deployment scripts. After logging on to each VM, the IP address is missing or incorrect for the Management/Internal/External NIC.**</span></span>
    
    <span data-ttu-id="1040a-137">**の解像度:** 自動的にこの問題を解決することはできません。</span><span class="sxs-lookup"><span data-stu-id="1040a-137">**Resolution:** This issue cannot be resolved automatically.</span></span> <span data-ttu-id="1040a-138">実行中の Vm に Nic を追加できません。</span><span class="sxs-lookup"><span data-stu-id="1040a-138">NICs cannot be added to VMs while they are running.</span></span> <span data-ttu-id="1040a-139">シャット ダウンとハイパー v マネージャーでは、これらの Vm を削除、次のコマンドレットを実行してください。</span><span class="sxs-lookup"><span data-stu-id="1040a-139">Please shut down and remove these VMs in hyper-v manager, then run the following cmdlets:</span></span>
    
  ```
  Uninstall-CcAppliance
  ```

  ```
  Install-CcAppliance
  ```

- 
    
    <span data-ttu-id="1040a-140">**問題: Active Directory とフォレストをインストールした後、CMS サーバーや仲介サーバーがドメインに正しく参加しない。**</span><span class="sxs-lookup"><span data-stu-id="1040a-140">**Issue: After the Active Directory Server and forest are installed, the CMS Server and/or Mediation Server did not join the domain correctly.**</span></span>
    
    <span data-ttu-id="1040a-141">**解決策:** この問題を解決するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="1040a-141">**Resolution:** To resolve this issue, take the following steps:</span></span>
    
  - <span data-ttu-id="1040a-142">Active Directory サーバーにログオンし、ドメインが正しく作成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1040a-142">Log on to the Active Directory Server and verify that the domain was created correctly.</span></span>
    
  - <span data-ttu-id="1040a-143">CMS/仲介サーバーにログオンし、Corpnet NIC で有効な IP アドレスが割り当てられていることと、AD サーバーの IP アドレスとして有効な固定 IP アドレスと DNS が構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1040a-143">Log on to the CMS/Mediation Server and verify that on the corpnet NIC a valid IP address is assigned, and that valid static IP and DNS is configured as the AD server's IP address.</span></span>
    
  - <span data-ttu-id="1040a-144">CMS/仲介サーバーにログオンし、コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="1040a-144">Log on to the CMS/Mediation Server, and open a command prompt.</span></span> <span data-ttu-id="1040a-145">Active Directory サーバーの FQDN と IP アドレスに対して ping を実行できることを確かめます。</span><span class="sxs-lookup"><span data-stu-id="1040a-145">Make sure you can ping the FQDN and IP address of the Active Directory Server.</span></span> <span data-ttu-id="1040a-146">実行できない場合は、IP アドレスの競合が考えられます。</span><span class="sxs-lookup"><span data-stu-id="1040a-146">If you cannot, there may be an IP address conflict.</span></span> <span data-ttu-id="1040a-147">Active Directory に新しい IP を割り当てて、CMS/仲介サーバーで DNS を更新することを試してください。</span><span class="sxs-lookup"><span data-stu-id="1040a-147">Please try to assign a new IP for Active Directory and update DNS on the CMS/Mediation server accordingly.</span></span>
    
- <span data-ttu-id="1040a-148">**問題: 次のエラー メッセージを受信する"削除 VMSwitch: 仮想のイーサネット スイッチを削除中に失敗しました。'クラウド コネクタ管理スイッチ' 仮想スイッチの仮想マシンを実行することによって使用されているために、削除またはできない子のプールに割り当てられている。」**</span><span class="sxs-lookup"><span data-stu-id="1040a-148">**Issue: You receive the following error message, "Remove-VMSwitch : Failed while removing virtual Ethernet switch. The virtual switch 'Cloud Connector Management Switch' cannot be deleted because it is being used by running virtual machines or assigned to child pools."**</span></span>
    
    <span data-ttu-id="1040a-149">**の解像度:**「クラウド コネクタ管理スイッチ」は、配置後に削除されませんでした。</span><span class="sxs-lookup"><span data-stu-id="1040a-149">**Resolution:** The "Cloud Connector Management Switch" was not deleted after the deployment.</span></span> <span data-ttu-id="1040a-150">このエラーをヒットした場合は、hyper-v マネージャーにしてくださいがあることを確認してそれに接続されている仮想マシンがまだします。</span><span class="sxs-lookup"><span data-stu-id="1040a-150">If you hit this error, please go to Hyper-v manager and verify that there is not still a virtual machine still connected to it.</span></span> <span data-ttu-id="1040a-151">まだ接続されている仮想マシンがある場合は、接続を切断し、管理スイッチを削除します。</span><span class="sxs-lookup"><span data-stu-id="1040a-151">If there are virtual machines still connected, disconnect them and delete the management switch.</span></span> <span data-ttu-id="1040a-152">管理スイッチも削除できない場合、ホスト サーバーを再起動してからやり直してください。</span><span class="sxs-lookup"><span data-stu-id="1040a-152">If the management switch still cannot be deleted, restart the host server and try again.</span></span>
    
- <span data-ttu-id="1040a-153">**問題: 次のエラー メッセージを受信する、"サービス RTCMRAUTH は、開始に失敗しました。確認して、サービスが無効になっていないかどうかを確認してください。**</span><span class="sxs-lookup"><span data-stu-id="1040a-153">**Issue: You receive the following error message, "Service RTCMRAUTH failed to start. Check to make sure the service is not disabled."**</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1040a-154">この問題にのみ適用されますクラウド コネクタ バージョン 1.4.2 より前です。</span><span class="sxs-lookup"><span data-stu-id="1040a-154">This issue only applies to Cloud Connector versions earlier than 1.4.2.</span></span> 
  
    <span data-ttu-id="1040a-p110">開始できない原因としては、このフロントエンド サーバーが (コンピューターのフェイルオーバーを使用して) 以前も失敗してやり直したことも考えられます。その場合は、(コンピューターのフェールバックアップを使用して) フェールバックを呼び出してください。</span><span class="sxs-lookup"><span data-stu-id="1040a-p110">The failure to start could also be because this Front End server was previously failed over (using computer fail over). If that's the case, please invoke fail back (using computer fail back).</span></span>
    
    <span data-ttu-id="1040a-p111">**解決策:** この問題は、ルート CA 証明書または中間 CA 証明書がエッジ サーバーで信頼されていない場合に、エッジ サーバーで発生します。外部証明書をインポートできるとしても、証明書チェーンが破損しています。この状況では、RTCMRAUTH か RTCSRV、またはその両方のサービスが開始できません。</span><span class="sxs-lookup"><span data-stu-id="1040a-p111">**Resolution:** This issue happens on an Edge Server when the root CA certificate or intermediate CA certificate is not trusted by the Edge Server. Even if the external certificate can be imported but the certificate chain is broken. Under this condition, the RTCMRAUTH and/or RTCSRV service can not start.</span></span>
    
    <span data-ttu-id="1040a-p112">ルート CA 証明書と、外部証明書の中間 CA 証明書をすべて手動でエッジ サーバーにをインポートしてから、エッジ サーバーを再起動します。エッジ サーバーで RTCMRAUTH サービスと RTCSRV サービスが開始したことを確認したら、ホスト サーバーに戻り、管理者として PowerShell コンソールを起動し、次のコマンドレットを実行して新しい展開に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="1040a-p112">Please import the root CA certificate and all intermediate CA certificates of your external certificate manually into the Edge Server and then restart the Edge Server. After you see the RTCMRAUTH and RTCSRV services started on the Edge Server, go back to your host server, launch a PowerShell console as administrator, and run following cmdlet to switch to the new deployment:</span></span>
    
  ```
  Switch-CcVersion
  ```

- 
    
    <span data-ttu-id="1040a-162">**問題: Windows Update の適用中にホスト サーバーが再起動され、サーバーによる呼び出しに失敗する。**</span><span class="sxs-lookup"><span data-stu-id="1040a-162">**Issue: The host server was restarted when Windows updates were applied, and calls serviced by the server are failing.**</span></span>
    
    <span data-ttu-id="1040a-p113">**解決策:** 高可用性環境を展開した場合は、Windows Update を手動で確認およびインストールするときに、1 台のホスト マシン (展開インスタンス) を現在のトポロジに移動するか、またはそこから移動するのに役立つコマンドレットが用意されています。これを行うには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="1040a-p113">**Resolution:** If you deployed a high availability environment, Microsoft provides a cmdlet to help move one host machine (deployment instance) into or out of the current topology when you check and install Windows update manually. Use the following steps to accomplish this:</span></span>
    
1. <span data-ttu-id="1040a-165">ホスト サーバーで、管理者として PowerShell コンソールを起動して、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="1040a-165">On the host server, start a PowerShell console as administrator, then run:</span></span>
    
   ```
   Enter-CcUpdate
   ```

2. <span data-ttu-id="1040a-166">利用可能な更新をチェックしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="1040a-166">Check for updates and install any that are available.</span></span>
    
3. <span data-ttu-id="1040a-167">PowerShell コンソールで、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="1040a-167">In the PowerShell console, run the following cmdlet:</span></span>
    
   ```
   Exit-CcUpdate
   ```

- 
    
    <span data-ttu-id="1040a-168">**問題: PSTN 番号を使って Skype for Business クライアントから通話を発信するとき、別の PSTN 番号を招待することで電話会議に通話をエスカレートできない。**</span><span class="sxs-lookup"><span data-stu-id="1040a-168">**Issue: When a call is made from a Skype for Business client using a PSTN number, the call cannot be escalated to a conference by inviting another PSTN number.**</span></span>
    
    <span data-ttu-id="1040a-169">**の解像度:** この問題を解決するのには、[オンライン ハイブリッド仲介サーバーの設定を構成する](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1040a-169">**Resolution:** To resolve this issue, see [Configure online hybrid Mediation Server Settings](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).</span></span>
    
- <span data-ttu-id="1040a-170">**問題: Active Directory サーバーのインストール中に、「Windows 自動更新が有効になっていません。新しくインストールした役割または機能が自動的に更新されるようにするには、[Windows Update] を有効にしてください」という Windows Update に関する警告メッセージが表示される。**</span><span class="sxs-lookup"><span data-stu-id="1040a-170">**Issue: A warning message is displayed about Windows Update when you are installing Active Directory server - "Windows automatic updating is not enabled. To ensure that your newly-installed role or feature is automatically updated, turn on Windows Update."**</span></span>
    
    <span data-ttu-id="1040a-171">**の解像度:** テナント管理者の資格情報をビジネスの Skype を使用してテナントのリモート PowerShell セッションを起動し、サイトの_EnableAutoUpdate_構成を確認するのには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="1040a-171">**Resolution:** Launch a Tenant Remote PowerShell session using Skype for Business tenant admin credentials, then run the following cmdlet to check the _EnableAutoUpdate_ configuration of your site:</span></span>
    
  ```
  Get-CsHybridPSTNSite
  ```

    <span data-ttu-id="1040a-172">_EnableAutoUpdate_が**True**に設定されている場合をダウンロードして仮想マシンとホスト サーバーの両方の Windows の更新プログラムをインストールする CCEManagement サービスを処理するため、この警告メッセージ安全に無視できます。</span><span class="sxs-lookup"><span data-stu-id="1040a-172">If  _EnableAutoUpdate_ is set to **True**, you can safely ignore this warning message because the CCEManagement service will handle downloading and installing Windows updates for both virtual machines and the host server.</span></span> <span data-ttu-id="1040a-173">_EnableAutoUpdate_は、 **False**に設定されている場合は、次のコマンドレットを**True**に設定する実行します。</span><span class="sxs-lookup"><span data-stu-id="1040a-173">If  _EnableAutoUpdate_ is set to **False**, run following cmdlet to set it to **True**.</span></span>
    
  ```
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    <span data-ttu-id="1040a-174">または、更新プログラムを手動で確認してインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="1040a-174">Alternatively, you can manually check for and install updates.</span></span> <span data-ttu-id="1040a-175">次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1040a-175">See the next section.</span></span>
    
- <span data-ttu-id="1040a-176">**問題: エラー メッセージが表示する: ために、アプライアンスを登録できません、現在の入力と構成\<サイト名\>または\<アプライアンス名\>または\<仲介サーバーの FQDN\>または\<仲介サーバーの IP アドレス\>既存のアプライアンスと競合しています。競合アプライアンスを削除し、入力と構成情報を更新または再登録します。' をオンラインの現在のアプライアンスを登録するのにはレジスタの CcAppliance を実行するとします。**</span><span class="sxs-lookup"><span data-stu-id="1040a-176">**Issue: You receive an error message: Cannot register appliance because your current input/configuration \<SiteName\> or \<ApplianceName\> or \<Mediation Server FQDN\> or \<Mediation Server IP Address\> conflicts with existing appliance(s). Remove conflict appliance or update your input/configuration information then register again. ' when run Register-CcAppliance to register current appliance to online.**</span></span>
    
    <span data-ttu-id="1040a-177">**の解像度:** 値は、\<アプライアンス名\>、 \<、仲介サーバーの FQDN\>と\<仲介サーバーの IP アドレス\>1 つのアプライアンスの登録に使用される一意とする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1040a-177">**Resolution:** Values for the \<ApplianceName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> must be unique and only used for one appliance registration.</span></span> <span data-ttu-id="1040a-178">既定では、\<アプライアンス名\>ホスト名に由来します。</span><span class="sxs-lookup"><span data-stu-id="1040a-178">By default, \<ApplianceName\> comes from the host name.</span></span> <span data-ttu-id="1040a-179">\<仲介サーバーの FQDN\>と\<、仲介サーバーの IP アドレス\>構成の ini ファイルで定義されています。</span><span class="sxs-lookup"><span data-stu-id="1040a-179">\<Mediation Server FQDN\> and \<Mediation Server IP Address\> defined in configuration ini file.</span></span>
    
    <span data-ttu-id="1040a-180">たとえば、(ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) を使用して SiteName=MySite に登録しても、登録済みアプライアンス (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) があると、競合が発生します。</span><span class="sxs-lookup"><span data-stu-id="1040a-180">For example, using (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) to register to SiteName=MySite, but if there is a registered appliance (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10), you will have the conflict.</span></span>
    
    <span data-ttu-id="1040a-181">まず、ApplianceRoot ディレクトリ セクションで CloudConnector.ini ファイルを確認します。</span><span class="sxs-lookup"><span data-stu-id="1040a-181">First, please check your CloudConnector.ini file in ApplianceRoot directory section.</span></span> <span data-ttu-id="1040a-182">表示されます\<サイト名\>、 \<、仲介サーバーの FQDN\>と\<、仲介サーバーの IP アドレス\>ファイル内の値です。</span><span class="sxs-lookup"><span data-stu-id="1040a-182">You will get \<SiteName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> values in the file.</span></span> <span data-ttu-id="1040a-183">\<アプライアンス名\>は、ホスト サーバーの名前です。</span><span class="sxs-lookup"><span data-stu-id="1040a-183">\<ApplianceName\> is your host server name.</span></span>
    
    <span data-ttu-id="1040a-184">次に、起動テナント リモート PowerShell、Skype を使用してテナント管理者の資格情報をビジネスには、登録されているアプライアンスを確認するのには次のコマンドレットを実行してください。</span><span class="sxs-lookup"><span data-stu-id="1040a-184">Second, Launch Tenant Remote PowerShell using your Skype for Business tenant admin credentials, then run the following cmdlet to check the registered appliance(s).</span></span>
    
  ```
  Get-CsHybridPSTNAppliance
  ```

    <span data-ttu-id="1040a-185">競合を特定したら、登録済みアプライアンスと一致する情報を CloudConnector.ini ファイルで更新するか、既存のアプライアンスを登録解除して、競合を解決します。</span><span class="sxs-lookup"><span data-stu-id="1040a-185">After identifying any conflicts, you can either update your CloudConnector.ini file with information that matches the registered appliance, or unregister the existing appliance to resolve the conflicts.</span></span>
    
  ```
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
- <span data-ttu-id="1040a-186">**問題: Get CcRunningVersion コマンドレットは、ホストで実行されている展開済みのアプライアンスがある場合に空の値を返します。**</span><span class="sxs-lookup"><span data-stu-id="1040a-186">**Issue: The Get-CcRunningVersion cmdlet returns an empty value if there is a deployed appliance running on the host.**</span></span>
    
  <span data-ttu-id="1040a-187">**の解像度:** 1.3.4 または 1.3.8 に 1.4.1 からアップグレードする場合に、発生することができます。</span><span class="sxs-lookup"><span data-stu-id="1040a-187">**Resolution:** This can happen when you upgrade from 1.3.4 or 1.3.8 to 1.4.1.</span></span> <span data-ttu-id="1040a-188">実行する必要があります、.msi を持つバージョン 1.4.1 をインストールした後`Register-CcAppliance`その他のすべてのコマンドレットを実行する前にします。</span><span class="sxs-lookup"><span data-stu-id="1040a-188">After you install version 1.4.1 with the .msi, you must run `Register-CcAppliance` before you run any other cmdlet.</span></span> <span data-ttu-id="1040a-189">`Register-CcAppliance`%programdata%\cloudconnector に %UserProfile%\CloudConnector から module.ini ファイルを移行します。</span><span class="sxs-lookup"><span data-stu-id="1040a-189">`Register-CcAppliance` will migrate the module.ini file from %UserProfile%\CloudConnector to %ProgramData%\CloudConnector.</span></span> <span data-ttu-id="1040a-190">その場合は、新しい module.ini は %ProgramData%\CloudConnector フォルダーに作成され、1.3.4 または 1.3.8 の実行中またはバックアップのバージョン情報を置き換えます。</span><span class="sxs-lookup"><span data-stu-id="1040a-190">If you missed it, a new module.ini will be created in %ProgramData%\CloudConnector folder and replace the running/backup version information for 1.3.4 or 1.3.8.</span></span>
    
  <span data-ttu-id="1040a-191">%UserProfile%\CloudConnector と %ProgramData%\CloudConnector フォルダーにある module.ini ファイルを比較します。</span><span class="sxs-lookup"><span data-stu-id="1040a-191">Compare module.ini files in %UserProfile%\CloudConnector and %ProgramData%\CloudConnector folder.</span></span> <span data-ttu-id="1040a-192">Module.ini ファイルに %ProgramData%\CloudConnector し、再実行を削除の違いがある場合は、 `Register-CcAppliance`。</span><span class="sxs-lookup"><span data-stu-id="1040a-192">If there are differences, delete the module.ini file in %ProgramData%\CloudConnector and rerun  `Register-CcAppliance`.</span></span> <span data-ttu-id="1040a-193">正しい実行し、バックアップ ・ バージョンを手動でファイルを変更することも可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1040a-193">You could also modify the file manually to the correct running and backup version.</span></span>
    
- <span data-ttu-id="1040a-194">**問題: 現在のスクリプト ・ バージョンとは別の古いバージョンに切り替えるには、スイッチ CcVersion コマンドレットを実行した後はありませんこの古いバージョンの高可用性のサポート。**</span><span class="sxs-lookup"><span data-stu-id="1040a-194">**Issue: After you run the Switch-CcVersion cmdlet to switch to an old version which is different from current script version, there is no High Availability support for this old version.**</span></span>
    
    <span data-ttu-id="1040a-195">**の解像度:** たとえば、1.4.2 に 1.4.1 からアップグレードされました。</span><span class="sxs-lookup"><span data-stu-id="1040a-195">**Resolution:** For example, you have upgraded from 1.4.1 to 1.4.2.</span></span> <span data-ttu-id="1040a-196">現在スクリプトのバージョンを実行することによって判断できます`Get-CcVersion`、および、実行中のバージョンを実行することによって判断できます`Get-CcRunningVersion`は、両方の 1.4.2。</span><span class="sxs-lookup"><span data-stu-id="1040a-196">Your current script version, which can be determined by running `Get-CcVersion`, and your running version, which can be determined by running  `Get-CcRunningVersion` are both 1.4.2.</span></span> <span data-ttu-id="1040a-197">実行する場合、この時点で`Switch-CcVersion`実行中のバージョンに戻るに 1.4.1、しなければこの古いバージョンの高可用性のサポート。</span><span class="sxs-lookup"><span data-stu-id="1040a-197">At this time, if you run `Switch-CcVersion` to switch the running version back to 1.4.1, then there will be no High Availability support for this old version.</span></span>
    
    <span data-ttu-id="1040a-p121">高可用性を完全にサポートするには、1.4.2 に切り替えて、実行中のバージョンとスクリプト バージョンが同じになるようにします。1.4.2 展開で問題が発生している場合は、できるだけ早くアンインストールして、再インストールしてください。</span><span class="sxs-lookup"><span data-stu-id="1040a-p121">To get full High Availability support, please switch back to 1.4.2, so the running version and script version are the same. If you are experiencing problems with your 1.4.2 deployment, please uninstall and reinstall it as soon as possible.</span></span>
    
- <span data-ttu-id="1040a-200">**問題: 証明機関の証明書、または中央管理ストア、仲介サーバー、エッジ サーバーに対して発行された内部証明書の有効期限が近づいているか、侵害された。**</span><span class="sxs-lookup"><span data-stu-id="1040a-200">**Issue: Certificate authority certificates or internal certificates issued to Central Management Store, Mediation Server, and Edge Server are near expiration or are compromised.**</span></span>
    
    <span data-ttu-id="1040a-p122">**解決策:** Skype for Business 証明機関の証明書は 5 年間有効です。中央管理ストア、仲介サーバー、エッジ サーバーに対して発行された内部証明書は 2 年間有効です。</span><span class="sxs-lookup"><span data-stu-id="1040a-p122">**Resolution:** Skype for Business certification authority certificates are valid for five years. Internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1040a-203">クラウド バージョン 2.0 以降では、コネクタの更新 CcServerCertificate コマンドレットは、更新プログラム CcServerCertificate に変更し、更新 CcCACertificate コマンドレットは、更新プログラム CcCACertificate に変更します。</span><span class="sxs-lookup"><span data-stu-id="1040a-203">In Cloud Connector version 2.0 and later, the Renew-CcServerCertificate cmdlet has changed to Update-CcServerCertificate and the Renew-CcCACertificate cmdlet has changed to Update-CcCACertificate.</span></span> 
  
    <span data-ttu-id="1040a-204">内部発行証明書を中央管理ストア、仲介サーバー、およびエッジ サーバーは、有効期限の近くや、証明書を更新する更新 CcServerCertificate または更新プログラム CcServerCertificate コマンドレットを実行する危険にさらされました。</span><span class="sxs-lookup"><span data-stu-id="1040a-204">If internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are near expiration or compromised, run the Renew-CcServerCertificate or Update-CcServerCertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="1040a-205">証明機関の証明書が有効期限の近くにある場合は、証明書を更新する更新 CcCACertificate または更新プログラム CcCACertificate コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="1040a-205">If certification authority certificates are near expiration, run the Renew-CcCACertificate or Update-CcCACertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="1040a-206">**証明機関の証明書が侵害され、サイトでは、アプライアンスが 1 つだけがある場合**は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="1040a-206">**If certification authority certificates are compromised and there is only one appliance in the site,** perform the following steps:</span></span>
    
1. <span data-ttu-id="1040a-207">Enter-CcUpdate コマンドレットを実行して、サービスをドレインし、アプライアンスをメンテナンス モードにします。</span><span class="sxs-lookup"><span data-stu-id="1040a-207">Run the Enter-CcUpdate cmdlet to drain services and put the appliance in maintenance mode.</span></span>
    
2. <span data-ttu-id="1040a-208">次のコマンドレットを実行して、リセットし、新しい証明機関の証明書とすべての内部サーバー証明書を作成します。</span><span class="sxs-lookup"><span data-stu-id="1040a-208">Run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
    <span data-ttu-id="1040a-209">2.0 より前に、のリリースをクラウド コネクタ。</span><span class="sxs-lookup"><span data-stu-id="1040a-209">For Cloud Connector releases before 2.0:</span></span>
    
    ```
    Reset-CcCACertificate 
    Renew-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

    <span data-ttu-id="1040a-210">またはクラウド コネクタ 2.0 以降のリリース。</span><span class="sxs-lookup"><span data-stu-id="1040a-210">Or for Cloud Connector release 2.0 and later:</span></span>
    
    ```
    Reset-CcCACertificate 
    Update-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

3. <span data-ttu-id="1040a-211">サービスを開始し、保守モードを終了する終了 CcUpdate コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="1040a-211">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span>
    
4. <span data-ttu-id="1040a-212">アプライアンスのローカル ファイルで Export-CcRootCertificate コマンドレットを実行し、エクスポートした証明書を PSTN ゲートウェイにコピーしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="1040a-212">Run the Export-CcRootCertificate cmdlet on the local file in the appliance, and then copy and install the exported certificate to your PSTN gateways.</span></span>
    
    <span data-ttu-id="1040a-213">**証明機関の証明書が侵害され、は、サイト内の複数のアプライアンスのかどうか**は、サイト内には、各アプライアンスを次の一連のステップを実行します。</span><span class="sxs-lookup"><span data-stu-id="1040a-213">**If certification authority certificates are compromised and there are multiple appliances in the site,** perform the following sequential steps on each appliance in the site.</span></span>
    
    <span data-ttu-id="1040a-214">非ピーク時間帯には、次の手順を実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1040a-214">Microsoft recommends that you perform these steps during non-peak usage times.</span></span>
    
   - <span data-ttu-id="1040a-215">最初のアプライアンスでは、CA をクリーンアップのバックアップ内のファイルを削除 CcCertificationAuthorityFile コマンドレットを実行します\<SiteRoot\>ディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="1040a-215">On the first appliance, run the Remove-CcCertificationAuthorityFile cmdlet to clean up the CA backup files in the \<SiteRoot\> directory.</span></span>
    
   - <span data-ttu-id="1040a-216">サービスと、各アプライアンスをメンテナンス モードにするのには Enter CcUpdate コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="1040a-216">Run the Enter-CcUpdate cmdlet to drain services and put each appliance in maintenance mode.</span></span>
    
   - <span data-ttu-id="1040a-217">次のコマンドレットを実行して、リセットし、新しい証明機関の証明書とすべての内部サーバー証明書を作成します。</span><span class="sxs-lookup"><span data-stu-id="1040a-217">Run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
     <span data-ttu-id="1040a-218">2.0 より前に、のリリースをクラウド コネクタ。</span><span class="sxs-lookup"><span data-stu-id="1040a-218">For Cloud Connector releases before 2.0:</span></span>
    
     ```
     Reset-CcCACertificate
     Renew-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

     <span data-ttu-id="1040a-219">またはクラウド コネクタ 2.0 以降のリリース。</span><span class="sxs-lookup"><span data-stu-id="1040a-219">Or for Cloud Connector release 2.0 and later:</span></span>
    
     ```
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

   - <span data-ttu-id="1040a-220">最初のアプライアンスでは、CA のファイルのバックアップを作成するのには次のコマンドレットを実行します\<SiteRoot\>フォルダー。</span><span class="sxs-lookup"><span data-stu-id="1040a-220">On the first appliance, run the following cmdlet to back up the CA files to the \<SiteRoot\> folder.</span></span> <span data-ttu-id="1040a-221">以降では、同じサイト内の他のすべてのアプライアンス、リセット CcCACertificate コマンドレットでは、CA のバックアップ ファイルを自動的に消費されます. アプライアンスでは、同じルート証明書を使用します。</span><span class="sxs-lookup"><span data-stu-id="1040a-221">Later, on all other appliances in the same site, the Reset-CcCACertificate cmdlet will consume the CA backup files automatically and appliances will use the same root certificate.</span></span>
    
     ```
     Backup-CcCertificationAuthority
     ```

   - <span data-ttu-id="1040a-222">サービスを開始し、保守モードを終了する終了 CcUpdate コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="1040a-222">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span> 
    
   - <span data-ttu-id="1040a-223">ゲートウェイと仲介サーバー間で TLS を使用する場合サイトでは、いずれのアプライアンスからのエクスポート CcRootCertificate コマンドレットを実行し、PSTN ゲートウェイにエクスポートする証明書をインストールします。</span><span class="sxs-lookup"><span data-stu-id="1040a-223">If TLS is used between the gateway and the Mediation Server, run the Export-CcRootCertificate cmdlet from any appliance in the site, and then install the exported certificate to your PSTN gateways.</span></span> 
    
- <span data-ttu-id="1040a-224">**問題: クラウド コネクタ管理サービスのログに、"C:\Program Files\Skype のビジネス クラウド コネクタ Edition\ManagementService\CceManagementService.log"次のエラー メッセージが表示する: CceService エラー: 0: 予期しない例外とオンライン ステータスの報告: System.Management.Automation.CmdletInvocationException: ユーザーのログオンに失敗しました\<グローバル テナント管理\>。正しいユーザー名とパスワードを使用していることを確認する、新しい資格情報オブジェクトを作成してください。---\>**</span><span class="sxs-lookup"><span data-stu-id="1040a-224">**Issue: You receive the following error message in the Cloud Connector Management Service Log, "C:\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log": CceService Error: 0 : Unexpected exception when reporting status to online: System.Management.Automation.CmdletInvocationException: Logon failed for the user \<Global Tenant Admin\>. Please create a new credential object, making sure that you have used the correct user name and password. ---\>**</span></span>
    
    <span data-ttu-id="1040a-225">**の解像度:** クラウド コネクタ アプライアンスが登録されているために、Office 365 テナントのグローバル管理者の資格情報が変更されました。</span><span class="sxs-lookup"><span data-stu-id="1040a-225">**Resolution:** The Office 365 global tenant admin credentials have been changed since the Cloud Connector appliance was registered.</span></span> <span data-ttu-id="1040a-226">クラウド コネクタ ・ アプライアンスのローカルに保存された資格情報を更新するには、ホスト ・ アプライアンスの PowerShell の管理者から、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="1040a-226">To update the locally stored credentials on the Cloud Connector appliance, run the following from Administrator PowerShell on the host appliance:</span></span>
    
  ```
  Set-CcCredential -AccountType TenantAdmin
  ```

- <span data-ttu-id="1040a-227">**問題: 展開に使用するホスト サーバーのアカウントのパスワードを変更すると後が表示されたら、次のエラー メッセージ:"寄せ SecureString: で使用できない無効なキーが指定されている状態です"ビジネス クラウド コネクタの %ProgramFiles%\Skype で。Edition\ManagementService\CceManagementService.log または Get CcCredential コマンドレットを実行しているとき。**</span><span class="sxs-lookup"><span data-stu-id="1040a-227">**Issue: After you change the password for the host server account you used for the deployment, you receive the following error message: "ConvertTo-SecureString : Key not valid for use in specified state." in %ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log or while running the Get-CcCredential cmdlet.**</span></span>
    
    <span data-ttu-id="1040a-228">**の解像度:** クラウド コネクタのすべての資格情報は、次のファイルに格納されます:"%systemdrive%\programdata\cloudconnector\credentials。\<CurrentUser\>.xml」です。</span><span class="sxs-lookup"><span data-stu-id="1040a-228">**Resolution:** All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="1040a-229">ホスト サーバーのパスワードを変更するときには、ローカルで格納されている資格情報を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1040a-229">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
    
    <span data-ttu-id="1040a-230">**Cloud Connector バージョン 1.4.2 を実行している場合は、** 次の手順を実行してすべての Cloud Connector パスワードを再生成します。</span><span class="sxs-lookup"><span data-stu-id="1040a-230">**If you are running Cloud Connector version 1.4.2,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  1. <span data-ttu-id="1040a-231">ホスト サーバーを再起動します。</span><span class="sxs-lookup"><span data-stu-id="1040a-231">Restart the host server.</span></span>
    
  2. <span data-ttu-id="1040a-232">次のファイルを削除します。"% SystemDrive%\Programdata\Cloudconnector\credentials。\<CurrentUser\>.xml」です。</span><span class="sxs-lookup"><span data-stu-id="1040a-232">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
  3. <span data-ttu-id="1040a-233">管理者として PowerShell コンソールを起動し、実行して"登録 CcAppliance-ローカル"次の説明、パスワードを再入力します。</span><span class="sxs-lookup"><span data-stu-id="1040a-233">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="1040a-234">Cloud Connector の展開で前回使用したパスワードと同じパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="1040a-234">Enter the same passwords you entered before for the Cloud Connector deployment.</span></span>
    
     <span data-ttu-id="1040a-235">**クラウド コネクタ バージョン 2.0 以降を実行している場合**は、次の手順でクラウドのコネクタのすべてのパスワードを再生成します。</span><span class="sxs-lookup"><span data-stu-id="1040a-235">**If you are running Cloud Connector version 2.0 or later,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  4. <span data-ttu-id="1040a-236">ホスト サーバーを再起動します。</span><span class="sxs-lookup"><span data-stu-id="1040a-236">Restart the host server.</span></span>
    
  5. <span data-ttu-id="1040a-237">次のファイルを削除します。"% SystemDrive%\Programdata\Cloudconnector\credentials。\<CurrentUser\>.xml」です。</span><span class="sxs-lookup"><span data-stu-id="1040a-237">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" .</span></span>
    
  6. <span data-ttu-id="1040a-238">管理者として PowerShell コンソールを起動し、実行して"登録 CcAppliance-ローカル"次の説明、パスワードを再入力します。</span><span class="sxs-lookup"><span data-stu-id="1040a-238">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> 
    
     <span data-ttu-id="1040a-p127">キャッシュされているファイルが Cloud Connector バージョン 1.4.2 で生成されたファイルである場合は、パスワードを求められたときに CceService パスワードの VMAdmin パスワードを使用します。その他すべてのアカウントについては、Cloud Connector の展開で前回使用したパスワードと同じパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="1040a-p127">If the cached password file was generated with Cloud Connector version 1.4.2, use the VMAdmin password for the CceService password when prompted. Enter the same password you entered before for the Cloud Connector deployment for all other accounts.</span></span>
    
     <span data-ttu-id="1040a-241">キャッシュされているパスワード ファイルが Cloud Connector バージョン 1.4.2 で生成されたファイルであり、DomainAdmin と VMAdmin のパスワードが異なる場合は、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1040a-241">If the cached password file was generated with Cloud Connector version 1.4.2 and the DomainAdmin and VMAdmin passwords are different, you must perform the following steps:</span></span>
    
  7. <span data-ttu-id="1040a-242">Set-CcCredential -AccountType DomainAdmin を次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="1040a-242">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
  8. <span data-ttu-id="1040a-243">以前のアカウントの資格情報を求められた場合は、CceService パスワードに使用した資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="1040a-243">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
  9. <span data-ttu-id="1040a-244">新しいアカウントの資格情報を求められた場合は、以前使用していた DomainAdmin パスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="1040a-244">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
     <span data-ttu-id="1040a-245">クラウド コネクタ バージョン 2.0 またはそれ以降、デフォルトでキャッシュされたパスワード ファイルが生成された場合 VmAdmin と DomainAdmin パスワードを使用して、同じ CceService として。</span><span class="sxs-lookup"><span data-stu-id="1040a-245">If the cached password file was generated with Cloud Connector version 2.0 or later, by default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="1040a-246">DomainAdmin と VMAdmin のパスワードを変更した場合は、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1040a-246">If you changed the DomainAdmin and VMAdmin passwords, you must perform the following steps:</span></span>
    
  10. <span data-ttu-id="1040a-247">Set-CcCredential -AccountType DomainAdmin を次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="1040a-247">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
       1. <span data-ttu-id="1040a-248">以前のアカウントの資格情報を求められた場合は、CceService パスワードに使用した資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="1040a-248">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="1040a-249">新しいアカウントの資格情報を求められた場合は、以前使用していた DomainAdmin パスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="1040a-249">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
  11. <span data-ttu-id="1040a-250">Set-CcCredential -AccountType VmAdmin を次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="1040a-250">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
       1. <span data-ttu-id="1040a-251">以前のアカウントの資格情報を求められた場合は、CceService パスワードに使用した資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="1040a-251">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="1040a-252">新しいアカウントの資格情報を求められた場合は、以前使用していた VmAdmin パスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="1040a-252">When prompted for the new account credential, enter the password for the VmAdmin password you used before.</span></span> 
    
- <span data-ttu-id="1040a-253">**問題: クラウド バージョン 2.1 以降では、コネクタで、アプライアンス上のレジスタ CcAppliance またはその他のコマンドレットを実行している場合、エラー メッセージが表示次のように:"の各オブジェクト: '共通' が見つかりませんこのオブジェクトのプロパティです。プロパティが存在することを確認します。14: C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 文字で」**</span><span class="sxs-lookup"><span data-stu-id="1040a-253">**Issue: With Cloud Connector version 2.1 and later, when running Register-CcAppliance or other cmdlets on the appliance, you receive an error message such as: "For Each-Object : The property 'Common' cannot be found on this object. Verify that the property exists. At C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char:14"**</span></span>
    
    <span data-ttu-id="1040a-254">**の解像度:** クラウド コネクタ 2.1 以降を必要と.NET Framework 4.6.1 以降。</span><span class="sxs-lookup"><span data-stu-id="1040a-254">**Resolution:** Cloud Connector 2.1 and later requires .NET Framework 4.6.1 or later.</span></span> <span data-ttu-id="1040a-255">アプライアンスのバージョン 4.6.1 の.NET Framework を更新してくださいまたはそれ以降、cmdlet(s) をもう一度実行するとします。</span><span class="sxs-lookup"><span data-stu-id="1040a-255">Please update .NET Framework on the appliance to version 4.6.1 or later and run the cmdlet(s) again.</span></span>

- <span data-ttu-id="1040a-256">**問題: クラウド コネクタ版 2.1 をインストール CcAppliance を実行している場合、エラー メッセージは、次のように:"エラーのための新しいインスタンスのインストールに失敗しました: XmlNode プロパティを設定する値として文字列のみを使用することができますので「状態」を設定することはできません」**</span><span class="sxs-lookup"><span data-stu-id="1040a-256">**Issue: With Cloud Connector Edition 2.1, when running Install-CcAppliance, you receive an error message such as: "Failed to install new instance with error: Cannot set "State" because only strings can be used as values to set XmlNode properties"**</span></span>

   <span data-ttu-id="1040a-257">**の解像度:** Cloudconnector.ini で [共通] のセクションでは、[追加してください「状態」の構成以下のよう: 市外 = 米国の州都市区町村 = レドモンド</span><span class="sxs-lookup"><span data-stu-id="1040a-257">**Resolution:** In Cloudconnector.ini, under the [Common] section, please add the “State” config as below:  CountryCode=US  State=WA  City=Redmond</span></span>

   <span data-ttu-id="1040a-258">"State"行を Cloudconnector.ini ファイルから削除することはできませんが、"State"行の値を持つには必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="1040a-258">It is not mandatory for the "State" line to have value, however the "State" line cannot be removed from the Cloudconnector.ini file.</span></span>

- <span data-ttu-id="1040a-259">**問題: 次のエラー メッセージを受信する「ディス マウント WindowsImage: ディス マウント WindowsImage で失敗しました。エラー コード = 0xc1550115"をインストールするか、クラウドのコネクタのエディションをアップグレードするとします。**</span><span class="sxs-lookup"><span data-stu-id="1040a-259">**Issue: You receive the following error message "Dismount-WindowsImage : Dismount-WindowsImage failed. Error code = 0xc1550115" when installing or upgrading Cloud Connector Edition.**</span></span>
    
    <span data-ttu-id="1040a-260">**の解像度:** PowerShell コンソールを実行して、管理者として起動"DISM のクリーンアップ-Wim'"です。</span><span class="sxs-lookup"><span data-stu-id="1040a-260">**Resolution:** Launch a PowerShell console as administrator, run "DISM -Cleanup-Wim'".</span></span> <span data-ttu-id="1040a-261">これが問題のあるすべてのイメージをクリーンアップします。</span><span class="sxs-lookup"><span data-stu-id="1040a-261">This will clean up all troubled images.</span></span> <span data-ttu-id="1040a-262">再インストール CcAppliance を実行するか、自動的にアップグレードするのにはビットを待ちます。</span><span class="sxs-lookup"><span data-stu-id="1040a-262">Run Install-CcAppliance again or wait for the bits to automatically upgrade.</span></span>
    
- <span data-ttu-id="1040a-263">**問題: 最初のコネクタのクラウド アプライアンス HA 環境での展開が失敗します。**</span><span class="sxs-lookup"><span data-stu-id="1040a-263">**Issue: Deployment of the first Cloud Connector appliance in an HA environment fails**</span></span>
    
    <span data-ttu-id="1040a-264">**の解像度:** 手順は、展開が失敗した理由によって異なります。</span><span class="sxs-lookup"><span data-stu-id="1040a-264">**Resolution:** The steps you take depend on the reason the deployment failed:</span></span>
    
  - <span data-ttu-id="1040a-265">最初のコネクタのクラウド アプライアンスで障害が発生したエラーの原因を特定できない場合は、まで、展開が成功すると、アプライアンスを再インストールして他のアプライアンスをインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="1040a-265">If the first Cloud Connector appliance fails and you cannot determine the reason for the failure, you must install the appliance again until the deployment is successful, and then install the other appliances.</span></span>
    
  - <span data-ttu-id="1040a-266">軽微な問題が、外部の証明書の問題など、最初のコネクタのクラウド アプライアンスが失敗した場合は、アプライアンスを再インストールすることがなく問題を解決することができます。</span><span class="sxs-lookup"><span data-stu-id="1040a-266">If the first Cloud Connector appliance fails with a minor issue, such as an external certificate issue, you might be able to fix the problem without re-installing the appliance.</span></span> <span data-ttu-id="1040a-267">使用してテナントの成功と展開を次のようにマークするためのリモート PowerShell できます。</span><span class="sxs-lookup"><span data-stu-id="1040a-267">You can then use tenant remote PowerShell to mark the deployment as successful as follows.</span></span> <span data-ttu-id="1040a-268">(も使えます次の手順では、最初の展開が成功したが、成功としての展開を報告する何らかの理由では、クラウドのコネクタが失敗した場合です。)</span><span class="sxs-lookup"><span data-stu-id="1040a-268">(You can also use the following steps if the first deployment was successful, but, for some reason, Cloud Connector fails to report the deployment as a success.)</span></span>
    
  - <span data-ttu-id="1040a-269">最初のコネクタのクラウド アプライアンスの Id (GUID) を取得するには、Get CsHybridPSTNAppliance コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="1040a-269">To get the Identity (GUID) of the first Cloud Connector appliance, run the Get-CsHybridPSTNAppliance cmdlet.</span></span>
    
  - <span data-ttu-id="1040a-270">正常に展開するアプライアンスを設定するには、次のようにセットの CsCceApplianceDeploymentStatus を実行します。</span><span class="sxs-lookup"><span data-stu-id="1040a-270">To mark the appliance as successfully deployed, run the Set-CsCceApplianceDeploymentStatus as follows:</span></span>
    
  ```
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- <span data-ttu-id="1040a-271">**問題: ホスト サーバーまたは仮想マシン上で Windows Update を手動で確認してインストールする必要がある。**</span><span class="sxs-lookup"><span data-stu-id="1040a-271">**Issue: You need to check for and install Windows updates manually on the host server or virtual machines.**</span></span>
    
   <span data-ttu-id="1040a-p132">**解決策:** Skype for Business Cloud Connector エディションが備える自動 OS 更新プログラムを活用することをお勧めします。アプライアンスをオンライン管理に登録して、自動 OS 更新を有効にすると、ホスト サーバーと仮想マシンが自動的に Windows Update を確認して、OS 更新の時間枠設定に従ってインストールします。</span><span class="sxs-lookup"><span data-stu-id="1040a-p132">**Resolution:** We recommend that you take advantage of automated OS updates provided by Skype for Business Cloud Connector Edition. After an appliance is registered for online management and auto OS update is enabled, the host server and virtual machines will check and install Windows Updates automatically according to the OS update time window settings.</span></span>
    
   <span data-ttu-id="1040a-p133">Windows Update を手動で確認してインストールする必要がある場合は、展開の種類に該当する、このセクションに記載されている手順に従ってください。更新に必要なダウン タイムを最小限にするため、ホスト サーバーと、そこで動作する仮想マシンの両方の更新を計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1040a-p133">If you need to check for and install Windows Updates manually, follow the steps in this section that apply to your type of deployment. You should plan on updating both the host server and the virtual machines running on it at the same time to minimize the amount of down time necessary for the updates.</span></span>
    
   <span data-ttu-id="1040a-p134">また、Windows Server Update Services (WSUS) サーバーを使用して、Cloud Connector サーバーに更新プログラムを提供することもできます。Windows Update が自動的にインストール**されない**ように構成してください。</span><span class="sxs-lookup"><span data-stu-id="1040a-p134">If you prefer, you can use a Windows Server Update Services (WSUS) server to provide updates to Cloud Connector servers. Just be sure to configure the Windows Update to **not** install automatically.</span></span>
    
   <span data-ttu-id="1040a-278">Cloud Connector 展開を手動で更新する方法については、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1040a-278">For information about how to manually update your Cloud Connector deployment, see the following section.</span></span>
    
- <span data-ttu-id="1040a-279">**問題: クラウド コネクタは、新しいビルドに更新すると、クラウドのコネクタのコマンドレットが更新されません。**</span><span class="sxs-lookup"><span data-stu-id="1040a-279">**Issue: When Cloud Connector updates to a new build, Cloud Connector cmdlets are not updated.**</span></span> <span data-ttu-id="1040a-280">場合があります、これは自動更新が発生した場合、PowerShell のウィンドウは開いたまま場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="1040a-280">This sometimes happens if a PowerShell window is left open when automatic update occurs.</span></span>
    
  <span data-ttu-id="1040a-281">**の解像度:** 更新されたコマンドレットを読み込むには、次の手順のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="1040a-281">**Resolution:** To load the updated cmdlets, you can do either of the following steps:</span></span>
    
   - <span data-ttu-id="1040a-282">クラウド コネクタ アプライアンスでは、PowerShell を閉じ、PowerShell をもう一度します。</span><span class="sxs-lookup"><span data-stu-id="1040a-282">Close PowerShell on the Cloud Connector appliance, and then reopen PowerShell.</span></span>
    
     - <span data-ttu-id="1040a-283">または、インポート モジュール CloudConnector を実行することができます-強制します。</span><span class="sxs-lookup"><span data-stu-id="1040a-283">Or, you can run Import-Module CloudConnector -Force.</span></span> 
 
-   <span data-ttu-id="1040a-284">**問題:「名前のコマンドレット、関数、スクリプト ファイルまたは実行可能なプログラムです。 としては、用語 ' Stop CsWindowsService' は認識されていません」エラーは、Enter CcUpdate コマンドレットを実行しようとしています。**</span><span class="sxs-lookup"><span data-stu-id="1040a-284">**Issue: "The term 'Stop-CsWindowsService' is not recognized as the name of a cmdlet, function, script file, or operable program." error when attempting to run Enter-CcUpdate cmdlet.**</span></span>

    <span data-ttu-id="1040a-285">**の解像度:**$HOME\AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache ファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="1040a-285">**Resolution:** Delete the $HOME\AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache file.</span></span>
<span data-ttu-id="1040a-286">PowerShell では、本当に時間がかかるものにするようにとするたびにすべてのモジュールを再分析する必要はありませんが検索され、そのモジュールのコマンドレットのキャッシュとしてこのファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="1040a-286">PowerShell creates this file as a cache of cmdlets from modules that it finds so that it doesn’t have to re-analyze all the modules each time as that would make things really slow.</span></span> <span data-ttu-id="1040a-287">ほとんどの場合、そのキャッシュからの読み取りにすると、PowerShell に誤解を招く結果を提供するいくつかのファイルの破損が発生しました。</span><span class="sxs-lookup"><span data-stu-id="1040a-287">Most likely, there was some file corruption that provided misleading results to PowerShell when it was reading back from that cache.</span></span>

-   <span data-ttu-id="1040a-288">**問題:「インポート モジュール CloudConnector」エラーが生成されます"インポート モジュール: 指定されたモジュールのモジュール ディレクトリに有効なモジュール ファイルが見つからなかったため、"CloudConnector"は読み込まれませんでした」**</span><span class="sxs-lookup"><span data-stu-id="1040a-288">**Issue: “Import-Module CloudConnector” generates error “Import-Module: The specified module “CloudConnector” was not loaded because no valid module file was found in any module directory”**</span></span>

    <span data-ttu-id="1040a-289">**解決策:**</span><span class="sxs-lookup"><span data-stu-id="1040a-289">**Resolution:**</span></span>
    - <span data-ttu-id="1040a-290">本当に CloudConnector モジュールが存在する [c:\Program Files\WindowsPowerShell\Modules の検証します。</span><span class="sxs-lookup"><span data-stu-id="1040a-290">Validate that indeed the CloudConnector module exists under c:\Program Files\WindowsPowerShell\Modules</span></span>
    
    - <span data-ttu-id="1040a-291">この場所が存在する CloudConnector モジュールを検証した後、モジュールの場所へのパスを格納する PSModulePath 環境変数を変更できます。</span><span class="sxs-lookup"><span data-stu-id="1040a-291">After validating that CloudConnector module exists under this location, the PSModulePath environment variable storing the path to the locations of the modules can be changed:</span></span>
    
     <span data-ttu-id="1040a-292">a.</span><span class="sxs-lookup"><span data-stu-id="1040a-292">a.</span></span> <span data-ttu-id="1040a-293">一時的な変更: 次のコマンドを実行、管理者として Powershell を開始: $env: psmodulepath 環境変数 = $env: psmodulepath 環境変数"; +C:\Program Files\WindowsPowerShell\Modules\"</span><span class="sxs-lookup"><span data-stu-id="1040a-293">Temporary change: Start Powershell as an Administrator and run the following command: $env:PSModulePath = $env:PSModulePath + ";C:\Program Files\WindowsPowerShell\Modules\"</span></span>
        
     <span data-ttu-id="1040a-294">b.</span><span class="sxs-lookup"><span data-stu-id="1040a-294">b.</span></span> <span data-ttu-id="1040a-295">永続的な変更、実行、管理者として PowerShell を開始の次のコマンド、1 つずつ: $CurrentValue = [環境]:: GetEnvironmentVariable("PSModulePath","Machine") SetEnvironmentVariable("PSModulePath", $CurrentValue +";C:\Program Files\WindowsPowerShell\Modules"、「コンピューター」)</span><span class="sxs-lookup"><span data-stu-id="1040a-295">For persistent change, Start PowerShell as an Administrator and run the following commands, one by one: $CurrentValue = [Environment]::GetEnvironmentVariable("PSModulePath", "Machine") SetEnvironmentVariable("PSModulePath", $CurrentValue + "; C:\Program Files\WindowsPowerShell\Modules", "Machine")</span></span>

    
## <a name="install-windows-updates-manually"></a><span data-ttu-id="1040a-296">Windows の更新プログラムを手動でインストールします。</span><span class="sxs-lookup"><span data-stu-id="1040a-296">Install Windows updates manually</span></span>

<span data-ttu-id="1040a-297">ご利用の環境で自動更新を使用しない場合は、次の手順に従って、Windows Update を手動で確認して適用します。</span><span class="sxs-lookup"><span data-stu-id="1040a-297">If you do not want to use automatic updates in your environment, follow these steps to manually check for and apply Windows updates.</span></span> <span data-ttu-id="1040a-298">Windows Update の確認とインストールでは、サーバーの再起動が必要となる場合があります。</span><span class="sxs-lookup"><span data-stu-id="1040a-298">Checking for and installing Windows updates may require a server restart.</span></span> <span data-ttu-id="1040a-299">ホスト サーバーを再起動すると、ユーザーはクラウドのコネクタを使用して、開始、または呼び出しを受信することはできません。</span><span class="sxs-lookup"><span data-stu-id="1040a-299">When a host server is restarting, users will not be able to use Cloud Connector to place or receive calls.</span></span> <span data-ttu-id="1040a-300">更新プログラムを手動で確認してインストールすることにより更新の実行時期を制御してから、サービスの中断を回避するために選んだ期間中に必要に応じてコンピューターを再起動できます。</span><span class="sxs-lookup"><span data-stu-id="1040a-300">You can manually check for and install updates to control when the updates take place, and then restart the machines as needed during times you choose to avoid disruption of services.</span></span>
  
<span data-ttu-id="1040a-301">更新プログラムを手動で確認するには、各ホスト サーバーに接続し、[**コントロール パネル**] を開きます。</span><span class="sxs-lookup"><span data-stu-id="1040a-301">To manually check for updates, connect to each host server and open the **Control Panel**.</span></span> <span data-ttu-id="1040a-302">選択**システムとセキュリティ\>Windows の更新プログラム**、更新プログラムを管理し、必要に応じて、お客様の環境にサーバーを再起動します。</span><span class="sxs-lookup"><span data-stu-id="1040a-302">Select **System and Security \>Windows Update**, and then manage the updates and server restarts as appropriate for your environment.</span></span>
  
- <span data-ttu-id="1040a-303">サイトにアプライアンスが 1 台しかない場合は、各仮想マシンに接続し、[**コントロール パネル**] に接続します。</span><span class="sxs-lookup"><span data-stu-id="1040a-303">If there is only one appliance in the site, connect to each virtual machine and open the **Control Panel**.</span></span> <span data-ttu-id="1040a-304">選択**システムとセキュリティ\>Windows の更新プログラム**、更新プログラムを構成し、サーバーを再起動する必要に応じてします。</span><span class="sxs-lookup"><span data-stu-id="1040a-304">Select **System and Security \>Windows Update**, and then configure the updates and server restarts as appropriate.</span></span>
    
- <span data-ttu-id="1040a-p142">サイトに複数のアプライアンスがある場合、更新中、更新して再起動するインスタンスにはアクセスできません。更新が完了して、すべての仮想マシンと、仮想マシン上のすべての Skype for Business サービスが開始するまで、展開内の別のインスタンスに接続することになります。サービス中断の可能性を避けるため、更新プログラム適用中にインスタンスから HA を削除し、完了してから復元することができます。その手順は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1040a-p142">If there are more than one appliance in the site, the instance being updated and restarted cannot be accessed by users during the updates. Users will connect to other instances in the deployment until all virtual machines and all Skype for Business services start on the virtual machines after the updates are completed. To avoid any potential disruption to service, you can remove the instance from HA while you apply the updates, and then restore it when complete. To do so:</span></span>
    
1. <span data-ttu-id="1040a-309">ホスト サーバーごとに、管理者として PowerShell コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="1040a-309">On each host server, open a PowerShell console as administrator.</span></span>
    
2. <span data-ttu-id="1040a-310">次のコマンドレットを使用して、HA からインスタンスを削除します。</span><span class="sxs-lookup"><span data-stu-id="1040a-310">Remove the instance from HA with the following cmdlet:</span></span>
    
   ```
   Enter-CcUpdate
   ```

3. 
    
    <span data-ttu-id="1040a-311">単一インスタンスの手順に従い、更新を手動で適用し仮想マシンを再起動します。</span><span class="sxs-lookup"><span data-stu-id="1040a-311">Follow the steps for a single instance to manually apply the updates and restart the virtual machine.</span></span>
    
4. <span data-ttu-id="1040a-312">次のコマンドレットを使用して、HA にインスタンスを戻します。</span><span class="sxs-lookup"><span data-stu-id="1040a-312">Set the instance back to HA with the following cmdlet:</span></span>
    
   ```
   Exit-CcUpdate
   ```

<span data-ttu-id="1040a-313">マルチサイト展開の場合は、展開内の各サイトに対して 1 つのサイトの手順を実行し、一度に 1 つのサイトに対して更新プログラムを適用します。</span><span class="sxs-lookup"><span data-stu-id="1040a-313">For multi-site deployments, follow the steps for a single site for each site in the deployment, applying updates to one site at a time.</span></span>
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a><span data-ttu-id="1040a-314">クラウド コネクタのホスト コンピューターにウイルス対策ソフトウェアをインストールするときのヒントします。</span><span class="sxs-lookup"><span data-stu-id="1040a-314">Tips when installing anti-virus software on the Cloud Connector host machine</span></span>

<span data-ttu-id="1040a-315">クラウド コネクタのホスト コンピューターにウイルス対策ソフトウェアをインストールする場合は、次の除外を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1040a-315">If you need to install anti-virus software on the Cloud Connector host machine, you need to add the following exclusions:</span></span>
  
- <span data-ttu-id="1040a-316">各コンピューターでローカルのアプライアンスのディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="1040a-316">Local Appliance Directory on each machine.</span></span>
    
- <span data-ttu-id="1040a-317">各マシン上のリモート サイト ディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="1040a-317">Remote Site Directory on each machine.</span></span>
    
- <span data-ttu-id="1040a-318">コンピューターのローカル サイトのディレクトリは、共有サイトのルート フォルダーをホストします。</span><span class="sxs-lookup"><span data-stu-id="1040a-318">Local Site Directory on the machine hosts the shared site root folder.</span></span>
    
- <span data-ttu-id="1040a-319">ビジネス クラウド コネクタ ・ エディションの %ProgramFiles%\Skype</span><span class="sxs-lookup"><span data-stu-id="1040a-319">%ProgramFiles%\Skype for Business Cloud Connector Edition</span></span>
    
- <span data-ttu-id="1040a-320">%ALLUSERSPROFILE%\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="1040a-320">%ALLUSERSPROFILE%\CloudConnector</span></span>
    
- <span data-ttu-id="1040a-321">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="1040a-321">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span></span>
    
- <span data-ttu-id="1040a-322">Microsoft.Rtc.CCE.ManagementService.exe プロセスです。</span><span class="sxs-lookup"><span data-stu-id="1040a-322">The process Microsoft.Rtc.CCE.ManagementService.exe.</span></span>
