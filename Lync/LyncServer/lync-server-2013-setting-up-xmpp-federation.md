---
title: 'Lync Server 2013: XMPP フェデレーションのセットアップ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up XMPP federation
ms:assetid: 5fda6cb7-8d4d-495d-90c7-601f1036e085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204939(v=OCS.15)
ms:contentKeyID: 48184270
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd61aded33d37e4a1f5f58e9050f3cd62794f9b6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732047"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="f8eeb-102">Lync Server 2013 XMPP フェデレーションのセットアップ</span><span class="sxs-lookup"><span data-stu-id="f8eeb-102">Setting up XMPP federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8eeb-103">_**最終更新日:** 2012-12-03_</span><span class="sxs-lookup"><span data-stu-id="f8eeb-103">_**Topic Last Modified:** 2012-12-03_</span></span>

<span data-ttu-id="f8eeb-104">エッジサーバーに XMPP プロキシを展開するには、Edge Server を XMPP フェデレーション用に構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-104">To deploy the XMPP Proxy on the Edge Server, you must configure the Edge Server for XMPP federation.</span></span> <span data-ttu-id="f8eeb-105">そのためには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-105">To do this, you do the following steps.</span></span>

<div>

## <a name="setting-up-xmpp-federation"></a><span data-ttu-id="f8eeb-106">XMPP フェデレーションのセットアップ</span><span class="sxs-lookup"><span data-stu-id="f8eeb-106">Setting Up XMPP Federation</span></span>

1.  <span data-ttu-id="f8eeb-107">Lync Server 展開ウィザードがドメイン管理者グループと RTCUniversalServerAdmins グループのメンバーとしてインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-107">Log on to the computer where the Lync Server Deployment Wizard is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="f8eeb-108">フロントエンドサーバーで、Lync Server 展開ウィザードを開きます。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-108">On the Front End server, open the Lync Server Deployment wizard.</span></span> <span data-ttu-id="f8eeb-109">[Lync Server System のインストールまたは更新] をクリックし、[Lync Server コンポーネントのセットアップまたは削除] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-109">Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components.</span></span> <span data-ttu-id="f8eeb-110">[実行] をもう一度クリックします。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-110">Click Run Again.</span></span>

3.  <span data-ttu-id="f8eeb-111">Lync Server コンポーネントのセットアップで、[次へ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-111">At Setup Lync Server components, click Next.</span></span> <span data-ttu-id="f8eeb-112">概要画面には、実行中の操作が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-112">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="f8eeb-113">展開が完了したら、[ログの表示] をクリックして、利用可能なログファイルを表示します。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-113">Once the deployment is done, click View Log to view available log files.</span></span> <span data-ttu-id="f8eeb-114">[完了] をクリックして展開を完了します。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-114">Click Finish to complete the deployment.</span></span>

4.  <span data-ttu-id="f8eeb-115">エッジサーバーで、Lync Server 展開ウィザードを開きます。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-115">On the Edge server, open the Lync Server Deployment wizard.</span></span> <span data-ttu-id="f8eeb-116">[Lync Server System のインストールまたは更新] をクリックし、[Lync Server コンポーネントのセットアップまたは削除] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-116">Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components.</span></span> <span data-ttu-id="f8eeb-117">[実行] をもう一度クリックします。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-117">Click Run Again.</span></span>

5.  <span data-ttu-id="f8eeb-118">Lync Server コンポーネントのセットアップで、[次へ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-118">At Setup Lync Server components, click Next.</span></span> <span data-ttu-id="f8eeb-119">概要画面には、実行中の操作が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-119">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="f8eeb-120">展開が完了したら、[ログの表示] をクリックして、利用可能なログファイルを表示します。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-120">Once the deployment is done, click View Log to view available log files.</span></span> <span data-ttu-id="f8eeb-121">[完了] をクリックして展開を完了します。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-121">Click Finish to complete the deployment.</span></span>

6.  <span data-ttu-id="f8eeb-122">エッジサーバーの展開ウィザードで、[手順 3: 証明書の要求、インストール、または割り当て] の横にある [実行] をもう一度クリックします。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-122">On the Edge Server, in the Deployment Wizard, next to Step 3: Request, Install, or Assign Certificates, click Run again.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="f8eeb-123">初めてエッジサーバーを展開する場合は、[実行] ではなく、[実行] と表示されます。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-123">If you are deploying the Edge Server for the first time, you will see Run instead of Run Again.</span></span>

    
    </div>

7.  <span data-ttu-id="f8eeb-124">[利用可能な証明書タスク] ページで、[新しい証明書要求を作成する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-124">On the Available Certificate Tasks page, click Create a new certificate request.</span></span>

8.  <span data-ttu-id="f8eeb-125">[証明書の要求] ページで、[外部境界の証明書] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-125">On the Certificate Request page, click External Edge Certificate.</span></span>

9.  <span data-ttu-id="f8eeb-126">[遅延または即時要求] ページで、[今すぐ要求を準備するが、後で送信する] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-126">On the Delayed or Immediate Request page, select the Prepare the request now, but send it later check box.</span></span>

10. <span data-ttu-id="f8eeb-127">[証明書要求ファイル] ページで、要求を保存するファイルの完全パスとファイル名を入力します (たとえば、c:\\cert\_外部\_edge)。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-127">On the Certificate Request File page, type the full path and file name of the file to which the request is to be saved (for example, c:\\cert\_exernal\_edge.cer).</span></span>

11. <span data-ttu-id="f8eeb-128">[代替証明書テンプレートの指定] ページで、既定の Web サーバテンプレート以外のテンプレートを使用するには、[選択された証明機関に別の証明書テンプレートを使用する] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-128">On the Specify Alternate Certificate Template page, to use a template other than the default WebServer template, select the Use alternative certificate template for the selected certification authority check box.</span></span>

12. <span data-ttu-id="f8eeb-129">[名前およびセキュリティの設定] ページで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-129">On the Name and Security Settings page, do the following:</span></span>
    
    1.  <span data-ttu-id="f8eeb-130">[フレンドリ名] に、証明書の表示名を入力します。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-130">In Friendly name, type a display name for the certificate</span></span>
    
    2.  <span data-ttu-id="f8eeb-131">ビット長では、ビット長 (通常は2048の既定値) を指定します。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-131">In Bit length, specify the bit length (typically, the default of 2048)</span></span>
    
    3.  <span data-ttu-id="f8eeb-132">[証明書の秘密キーをエクスポート可能としてマークする] チェックボックスがオンになっていることを確認する</span><span class="sxs-lookup"><span data-stu-id="f8eeb-132">Verify that the Mark certificate private key as exportable check box is selected</span></span>

13. <span data-ttu-id="f8eeb-133">[組織の情報] ページで、組織の名前と組織単位 (たとえば、部門や部署) を入力します。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-133">On the Organization Information page, type the name for the organization and the organizational unit (for example, a division or department)</span></span>

14. <span data-ttu-id="f8eeb-134">[地理情報] ページで、場所情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-134">On the Geographical Information page, specify the location information</span></span>

15. <span data-ttu-id="f8eeb-135">[Subject Name/Subject Name] ページには、ウィザードによって自動的に入力される情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-135">On the Subject Name/Subject Alternate Names page, the information to be automatically populated by the wizard is displayed.</span></span> <span data-ttu-id="f8eeb-136">追加の件名の代替名が必要な場合は、次の2つの手順で指定します。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-136">If additional subject alternative names are needed, you specify them in the next two steps</span></span>

16. <span data-ttu-id="f8eeb-137">[サブジェクト代替名 (San)] ページの SIP ドメイン設定で、[Domain] チェックボックスをオンにして sip を追加します。\<[\>件名の代替名] ボックスの一覧に sipdomain エントリを入力します。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-137">On the SIP Domain Setting on Subject Alternate Names (SANs) page, select the domain check box to add a sip.\<sipdomain\> entry to the subject alternative names list.</span></span>

17. <span data-ttu-id="f8eeb-138">[追加のサブジェクト代替名の構成] ページで、必要なその他のサブジェクトの代替名を指定します。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-138">On the Configure Additional Subject Alternate Names page, specify any additional subject alternative names that are required</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="f8eeb-139">XMPP プロキシがインストールされている場合、既定では、ドメイン名 (contoso.com など) が SAN エントリに設定されます。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-139">If the XMPP proxy is installed, by default the domain name (such as contoso.com) is populated in the SAN entries.</span></span> <span data-ttu-id="f8eeb-140">他のエントリが必要な場合は、この手順で追加します。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-140">If you require more entries, add them in this step.</span></span>

    
    </div>

18. <span data-ttu-id="f8eeb-141">[要求の概要] ページで、要求の生成に使用する証明書情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-141">On the Request Summary page, review the certificate information to be used to generate the request.</span></span>

19. <span data-ttu-id="f8eeb-142">コマンドの実行が完了したら、ログを表示するか、[次へ] をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-142">After the commands finish running, you can View Log, or click Next to continue.</span></span>

20. <span data-ttu-id="f8eeb-143">[証明書要求ファイル] ページで、[完了] をクリックして、証明書ウィザードの [表示] または [終了] をクリックし、生成された証明書署名要求 (CSR) ファイルを表示できます。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-143">On the Certificate Request File page, you can view the generated certificate signing request (CSR) file by clicking View or exit the Certificate Wizard by clicking Finish.</span></span>

21. <span data-ttu-id="f8eeb-144">要求ファイルをコピーして、公開証明機関に提出します。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-144">Copy the request file and submit to your public certification authority.</span></span>

22. <span data-ttu-id="f8eeb-145">公開証明書の受信、インポート、割り当てが完了したら、Edge Server サービスを停止して再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-145">After receiving, importing and assigning the public certificate, you must stop and restart the Edge Server services.</span></span> <span data-ttu-id="f8eeb-146">これを行うには、Lync Server 管理コンソールで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-146">You do this by typing in the Lync Server Management console:</span></span>
    
       ```PowerShell
        Stop-CsWindowsService
       ```
    
       ```PowerShell
        Start-CsWindowsService
       ```

23. <span data-ttu-id="f8eeb-147">XMPP フェデレーション用の DNS を構成するには、次の SRV レコードを外部\_DNS に追加します。 xmpp-サーバー。\_tcp。\<ドメイン名\> SRV レコードはエッジサーバーのアクセスエッジ FQDN に解決され、ポート値は5269になります。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-147">To configure DNS for XMPP federation, you add the following SRV record to external DNS:\_xmpp-server.\_tcp.\<domain name\> The SRV record will resolve to the access edge FQDN of the Edge server, with a port value of 5269.</span></span> <span data-ttu-id="f8eeb-148">さらに、アクセスエッジサーバーの IP アドレスを参照する "A" ホストレコード (xmpp.contoso.com など) を構成します。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-148">Additionally, you configure an ‘A’ host record (for example, xmpp.contoso.com) that points to the IP address of the Access Edge Server.</span></span>
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f8eeb-149">複数のサイトにエッジプールがある場合は、XMPP フェデレーション用の複数の SRV レコードを追加することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-149">If you have Edge pools in multiple sites, we recommend that you add multiple SRV records for XMPP federation.</span></span> <span data-ttu-id="f8eeb-150">組織内のすべてのエッジプールに SRV レコードを追加し、各 SRV レコードに異なる優先順位を付けます。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-150">Add a SRV record for every Edge pool in your organization, and give each of those SRV records a different priority.</span></span> <span data-ttu-id="f8eeb-151">すべてのエッジプールが実行されている場合は、最初の優先順位の Edge プールによってすべての XMPP 要求が処理されますが、エッジプールがダウンした場合は、新しい SRV レコードを追加しなくても、XMPP のフェデレーション機能を回復することはできません。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-151">When all Edge pools are running, XMPP requests will all be handled by the Edge pool with the first priority, but if that Edge pool goes down you won’t then have to add a new SRV record to regain XMPP federation functionality.</span></span>

    
    </div>

24. <span data-ttu-id="f8eeb-152">新しい外部アクセスポリシーを構成して、すべてのユーザーを有効にするには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-152">Configure a new External Access Policy to enable all users by opening the Lync Server Management Shell on the Front End and typing:</span></span>
    
       ```PowerShell
        New-CsExternalAccessPolicy -Identity <name of policy to create.  If site scope, prepend with 'site:'> -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```PowerShell
        New-CsExternalAccessPolicy -Identity FedPic -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```PowerShell
        Get-CsUser | Grant-CsExternalAccessPolicy -PolicyName FedPic
       ```
    
    <span data-ttu-id="f8eeb-153">外部ユーザーに対して XMPP アクセスを有効にするには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-153">Enable XMPP Access for External Users by typing:</span></span>
    
       ```PowerShell
        Set-CsExternalAccessPolicy -Identity <name of the policy being used> EnableXmppAccess $true
       ```
    
       ```PowerShell
        Set-CsExternalAccessPolicy -Identity FedPic -EnableXmppAccess $true
       ```

25. <span data-ttu-id="f8eeb-154">XMPP プロキシが展開されているエッジサーバーで、コマンドプロンプトまたは Windows PowerShell™のコマンドラインインターフェイスを開き、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-154">On the Edge Server where the XMPP Proxy is deployed, open a Command Prompt or a Windows PowerShell™ command-line interface and type the following:</span></span>
    
       ```PowerShell
        Netstat -ano | findstr 5269
       ```
    
       ```PowerShell
        Netstat -ano | findstr 23456
       ```
    
    <span data-ttu-id="f8eeb-155">コマンド**netstat – ano**は、ネットワーク統計情報コマンドであり、パラメーター **– ano** request は、すべての接続とリスニングポート、アドレスとポートが数値形式で表示され、所有しているプロセス ID は各接続と関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-155">The command **netstat –ano** is a network statistics command, the parameters **–ano** request that netstat display all connections and listening ports, address and ports are displayed in a numerical form, and that the owning process ID is associated with each connection.</span></span> <span data-ttu-id="f8eeb-156">この文字**|** は、次のコマンド、 **findstr**、または検索文字列へのパイプを定義します。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-156">The character **|** defines a pipe to the next command, **findstr**, or find string.</span></span> <span data-ttu-id="f8eeb-157">パラメーターとして findstr に渡される数値5269および23456では、文字列5269と23456の netstat の出力を検索するように findstr に指示します。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-157">The number 5269 and 23456 that is passed to findstr as a parameter instructs findstr to search the output of netstat for the strings 5269 and 23456.</span></span> <span data-ttu-id="f8eeb-158">XMPP が適切に構成されている場合、コマンドの結果は、外部 (ポート 5269) と、エッジサーバーの内部 (ポート 23456) インターフェイスの両方で、リッスンと確立された接続になります。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-158">If XMPP is correctly configured, the result of the commands should result in listening and established connections, both on the external (port 5269) and the internal (port 23456) interfaces of the Edge Server.</span></span>
    
    <span data-ttu-id="f8eeb-159">このコマンドによって5269および23456で、確立済みまたはリッスン中のポートが返されない場合は、次のことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-159">If the commands do not return established or listening ports on 5269 and 23456, check the following:</span></span>

</div>

<div>

## <a name="troubleshooting-xmpp-federation"></a><span data-ttu-id="f8eeb-160">XMPP フェデレーションのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="f8eeb-160">Troubleshooting XMPP Federation</span></span>

1.  <span data-ttu-id="f8eeb-161">XMPP プロキシが実行されているかどうかを確認するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-161">To determine if the XMPP Proxy is running, do the following:</span></span>

2.  <span data-ttu-id="f8eeb-162">ローカル管理者のグループのメンバーとして XMPP プロキシサービスを実行しているエッジサーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-162">Log on to the Edge server that is running the XMPP Proxy service as a member of the local administrator’s group.</span></span>

3.  <span data-ttu-id="f8eeb-163">[**スタート**] をクリックし、[**すべてのプログラム**]、[**管理ツール**]、[**サービス**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-163">Click **Start**, click **All Programs**, click **Administrative Tools**, click **Services**</span></span>

4.  <span data-ttu-id="f8eeb-164">[サービス] で、Lync Server XMPP の翻訳ゲートウェイプロキシを検索します。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-164">In Services, locate Lync Server XMPP Translating Gateway Proxy.</span></span> <span data-ttu-id="f8eeb-165">サービスは**開始**状態である必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-165">The service should be in the **Started** state.</span></span> <span data-ttu-id="f8eeb-166">開始されていない場合は、ツールバーの [**スタート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-166">If it is not started, click the **Start** icon in the toolbar.</span></span> <span data-ttu-id="f8eeb-167">アイコンは、緑の右向き矢印として表示されます。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-167">The icon appears as a green, right-pointing arrow.</span></span>

5.  <span data-ttu-id="f8eeb-168">サービスが**開始**されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-168">Confirm that the service has changed to **Started**.</span></span> <span data-ttu-id="f8eeb-169">正常に開始された場合は、[**サービス**] を閉じて続行します。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-169">If it has successfully started, close **Services** and continue.</span></span>
    
    <span data-ttu-id="f8eeb-170">他のサービスが正常に開始されない場合は、[管理ツール] で [イベントビューアー] を開き、[**アプリケーションとサービスログ**] の**Lync Server**セクションのエラーと警告を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-170">If ther service has not successfully started, from Administrative Tools, open Event Viewer and refer to the errors and warnings in the **Lync Server** portion under **Applications and Services Logs**.</span></span>

6.  <span data-ttu-id="f8eeb-171">**Lync Server XMPP の変換ゲートウェイ**サービスが実行されたら、前に使用した netstat コマンドを再確認します。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-171">Once the **Lync Server XMPP Translating Gateway** service is running, recheck the netstat commands used previously.</span></span> <span data-ttu-id="f8eeb-172">セッションが確立されているかリッスンしていない場合は、トポロジビルダーで**Xmpp フェデレーションルート**が正しく構成されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-172">If you are not seeing established or listening sessions, check and ensure that the **XMPP Federation Route** is correctly configured in Topology Builder</span></span>

7.  <span data-ttu-id="f8eeb-173">トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-173">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

8.  <span data-ttu-id="f8eeb-174">トポロジビルダーを開始します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server Topology Builder**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-174">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

9.  <span data-ttu-id="f8eeb-175">[トポロジビルダー] で、XMPP フェデレーションルートのサイトを選択し、 **[xmpp**フェデレーション] の**サイトフェデレーションルート**の割り当てが、選択されている xmpp フェデレーションルートの割り当てとして Edge サーバーまたはエッジプールを表示しているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-175">In Topology Builder, select the site for the XMPP federation route and review to confirm that the **Site federation route assignment** for **XMPP federation** shows your Edge Server or Edge pool as the selected XMPP federation route assignment.</span></span>
    
    <span data-ttu-id="f8eeb-176">ルートの割り当てが間違っているか設定されていない場合は、サイトを右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-176">If the route assignment is incorrect or is not set, right-click the site, click **Edit Properties**.</span></span> <span data-ttu-id="f8eeb-177">[XMPP フェデレーション] チェックボックスをオンにして、適切なエッジサーバーまたはエッジプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-177">Select the XMPP federation check box and then select the correct Edge Server or Edge pool.</span></span>

10. <span data-ttu-id="f8eeb-178">トポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-178">Publish the topology.</span></span> <span data-ttu-id="f8eeb-179">詳細については、「 [Lync Server 2013 でトポロジを公開](lync-server-2013-publish-your-topology.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-179">For details, see [Publish your topology in Lync Server 2013](lync-server-2013-publish-your-topology.md)</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="f8eeb-180">ただし、必須ではありませんが、通常は不要です。エッジサーバーを再起動する必要があることがわかります。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-180">Though not required and typically not necessary, you may find that you will need to restart the Edge Servers</span></span>

    
    </div>

11. <span data-ttu-id="f8eeb-181">前に使用した netstat プロセスを使用して、エッジサーバーがポート5269およびポート23456でセッションをリッスンしているか、または確立されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-181">Using the netstat process used previously, confirm that the Edge Server is now listening or has established sessions on port 5269 and port 23456.</span></span>

12. <span data-ttu-id="f8eeb-182">それでも予期したセッションが表示されない場合は、通信問題の原因と考えられる原因についてイベントビューアーを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f8eeb-182">If you still are not seeing the expected sessions, check the Event Viewer for possible contributing causes for the communication problem.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f8eeb-183">関連項目</span><span class="sxs-lookup"><span data-stu-id="f8eeb-183">See Also</span></span>


[<span data-ttu-id="f8eeb-184">Lync Server 2013 での XMPP 構成の例  - Google Talk との XMPP フェデレーション</span><span class="sxs-lookup"><span data-stu-id="f8eeb-184">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="f8eeb-185">Lync Server 2013 での組織の XMPP フェデレーション パートナーの管理</span><span class="sxs-lookup"><span data-stu-id="f8eeb-185">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

