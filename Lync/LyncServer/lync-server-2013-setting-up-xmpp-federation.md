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
ms.openlocfilehash: b6cbe8db6b432f8e837e110875881e86adab9c51
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42039265"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="929c3-102">Lync Server 2013 での XMPP フェデレーションのセットアップ</span><span class="sxs-lookup"><span data-stu-id="929c3-102">Setting up XMPP federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="929c3-103">_**トピックの最終更新日:** 2012-12-03_</span><span class="sxs-lookup"><span data-stu-id="929c3-103">_**Topic Last Modified:** 2012-12-03_</span></span>

<span data-ttu-id="929c3-p101">XMPP プロキシをエッジ サーバーに展開するには、エッジ サーバーを XMPP フェデレーション用に構成する必要があります。これを行うには、以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="929c3-p101">To deploy the XMPP Proxy on the Edge Server, you must configure the Edge Server for XMPP federation. To do this, you do the following steps.</span></span>

<div>

## <a name="setting-up-xmpp-federation"></a><span data-ttu-id="929c3-106">XMPP フェデレーションのセットアップ</span><span class="sxs-lookup"><span data-stu-id="929c3-106">Setting Up XMPP Federation</span></span>

1.  <span data-ttu-id="929c3-107">Lync Server 展開ウィザードがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="929c3-107">Log on to the computer where the Lync Server Deployment Wizard is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="929c3-p102">フロントエンド サーバーで、Lync Server 展開ウィザードを開きます。[Lync Server システムのインストールまたは更新] をクリックして、[Lync Server コンポーネントのセットアップまたは削除] をクリックします。[再実行] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="929c3-p102">On the Front End server, open the Lync Server Deployment wizard. Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components. Click Run Again.</span></span>

3.  <span data-ttu-id="929c3-p103">[Lync Server コンポーネントのセットアップ] で、[次へ] をクリックします。概要画面に、実行された処理が表示されます。展開が完了したら、[ログの表示] をクリックして、利用可能なログ ファイルを表示します。[完了] をクリックして、展開を完了します。</span><span class="sxs-lookup"><span data-stu-id="929c3-p103">At Setup Lync Server components, click Next. The summary screen will show actions as they are executed. Once the deployment is done, click View Log to view available log files. Click Finish to complete the deployment.</span></span>

4.  <span data-ttu-id="929c3-p104">エッジ サーバーで、Lync Server 展開ウィザードを開きます。[Lync Server システムのインストールまたは更新] をクリックして、[Lync Server コンポーネントのセットアップまたは削除] をクリックします。[再実行] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="929c3-p104">On the Edge server, open the Lync Server Deployment wizard. Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components. Click Run Again.</span></span>

5.  <span data-ttu-id="929c3-p105">[Lync Server コンポーネントのセットアップ] で、[次へ] をクリックします。概要画面に、実行された処理が表示されます。展開が完了したら、[ログの表示] をクリックして、利用可能なログ ファイルを表示します。[完了] をクリックして、展開を完了します。</span><span class="sxs-lookup"><span data-stu-id="929c3-p105">At Setup Lync Server components, click Next. The summary screen will show actions as they are executed. Once the deployment is done, click View Log to view available log files. Click Finish to complete the deployment.</span></span>

6.  <span data-ttu-id="929c3-122">エッジ サーバーの展開ウィザードで、[ステップ 3: 証明書の要求、インストール、または割り当て] の横にある [再実行] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="929c3-122">On the Edge Server, in the Deployment Wizard, next to Step 3: Request, Install, or Assign Certificates, click Run again.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="929c3-123">初めてエッジ サーバーを展開する場合は、[再実行] ではなく [実行] が表示されます。</span><span class="sxs-lookup"><span data-stu-id="929c3-123">If you are deploying the Edge Server for the first time, you will see Run instead of Run Again.</span></span>

    
    </div>

7.  <span data-ttu-id="929c3-124">[利用可能な証明書タスク] ページで、[新しい証明書要求を作成する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="929c3-124">On the Available Certificate Tasks page, click Create a new certificate request.</span></span>

8.  <span data-ttu-id="929c3-125">[証明書の要求] ページで、[外部エッジの証明書] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="929c3-125">On the Certificate Request page, click External Edge Certificate.</span></span>

9.  <span data-ttu-id="929c3-126">[証明書要求の送信方法] ページで、[要求を準備して後で送信する] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="929c3-126">On the Delayed or Immediate Request page, select the Prepare the request now, but send it later check box.</span></span>

10. <span data-ttu-id="929c3-127">[証明書要求ファイル] ページで、要求を保存するファイルの完全なパスとファイル名を入力します (たとえば、c:\\cert\_外部\_edge. .cer)。</span><span class="sxs-lookup"><span data-stu-id="929c3-127">On the Certificate Request File page, type the full path and file name of the file to which the request is to be saved (for example, c:\\cert\_exernal\_edge.cer).</span></span>

11. <span data-ttu-id="929c3-128">[代替証明書テンプレートの指定] ページで、既定の WebServer テンプレート以外のテンプレートを使用するには、[選択した証明機関に別の証明書テンプレートを使用する] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="929c3-128">On the Specify Alternate Certificate Template page, to use a template other than the default WebServer template, select the Use alternative certificate template for the selected certification authority check box.</span></span>

12. <span data-ttu-id="929c3-129">[名前およびセキュリティの設定] ページで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="929c3-129">On the Name and Security Settings page, do the following:</span></span>
    
    1.  <span data-ttu-id="929c3-130">[フレンドリ名] に、証明書の表示名を入力します。</span><span class="sxs-lookup"><span data-stu-id="929c3-130">In Friendly name, type a display name for the certificate</span></span>
    
    2.  <span data-ttu-id="929c3-131">[ビット長] で、ビット長を指定します (通常は既定値の [2048])。</span><span class="sxs-lookup"><span data-stu-id="929c3-131">In Bit length, specify the bit length (typically, the default of 2048)</span></span>
    
    3.  <span data-ttu-id="929c3-132">[証明書の秘密キーをエクスポート可能としてマークする] チェック ボックスがオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="929c3-132">Verify that the Mark certificate private key as exportable check box is selected</span></span>

13. <span data-ttu-id="929c3-133">[組織情報] ページで、組織の名前と組織単位 (部や課など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="929c3-133">On the Organization Information page, type the name for the organization and the organizational unit (for example, a division or department)</span></span>

14. <span data-ttu-id="929c3-134">[地理情報] ページで、場所情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="929c3-134">On the Geographical Information page, specify the location information</span></span>

15. <span data-ttu-id="929c3-p106">[サブジェクト名/サブジェクト代替名] ページに、ウィザードによって自動的に設定される情報が表示されます。追加のサブジェクトの別名が必要な場合、次の 2 つの手順で指定します。</span><span class="sxs-lookup"><span data-stu-id="929c3-p106">On the Subject Name/Subject Alternate Names page, the information to be automatically populated by the wizard is displayed. If additional subject alternative names are needed, you specify them in the next two steps</span></span>

16. <span data-ttu-id="929c3-137">[サブジェクト代替名 (San) の SIP ドメイン設定] ページで、[ドメイン] チェックボックスをオンにして sip を追加します。\<microsoft.rtc.management.xds.sipdomain\>エントリをサブジェクトの別名一覧に入力します。</span><span class="sxs-lookup"><span data-stu-id="929c3-137">On the SIP Domain Setting on Subject Alternate Names (SANs) page, select the domain check box to add a sip.\<sipdomain\> entry to the subject alternative names list.</span></span>

17. <span data-ttu-id="929c3-138">[追加のサブジェクト代替名の構成] ページで、必要な追加のサブジェクトの別名を指定します。</span><span class="sxs-lookup"><span data-stu-id="929c3-138">On the Configure Additional Subject Alternate Names page, specify any additional subject alternative names that are required</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="929c3-p107">XMPP プロキシがインストールされている場合は、既定でドメイン名 (contoso.com など) が SAN エントリに設定されています。別のエントリが必要な場合は、この手順で追加します。</span><span class="sxs-lookup"><span data-stu-id="929c3-p107">If the XMPP proxy is installed, by default the domain name (such as contoso.com) is populated in the SAN entries. If you require more entries, add them in this step.</span></span>

    
    </div>

18. <span data-ttu-id="929c3-141">[要求の概要] ページで、要求を生成するために使用する証明書情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="929c3-141">On the Request Summary page, review the certificate information to be used to generate the request.</span></span>

19. <span data-ttu-id="929c3-142">コマンドの実行が完了したら、ログを表示するか、または [次へ] をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="929c3-142">After the commands finish running, you can View Log, or click Next to continue.</span></span>

20. <span data-ttu-id="929c3-143">[証明書要求ファイル] ページで、[表示] をクリックして生成済みの証明書の署名要求 (CSR) ファイルを表示するか、または [完了] をクリックして証明書ウィザードを終了します。</span><span class="sxs-lookup"><span data-stu-id="929c3-143">On the Certificate Request File page, you can view the generated certificate signing request (CSR) file by clicking View or exit the Certificate Wizard by clicking Finish.</span></span>

21. <span data-ttu-id="929c3-144">要求ファイルをコピーして、公的証明機関に送信します。</span><span class="sxs-lookup"><span data-stu-id="929c3-144">Copy the request file and submit to your public certification authority.</span></span>

22. <span data-ttu-id="929c3-p108">パブリック証明書の受信、インポート、および割り当てを行った後、エッジ サーバー サービスを停止して再起動する必要があります。これは、Lync Server 管理コンソールで次のコマンドを入力して行います。</span><span class="sxs-lookup"><span data-stu-id="929c3-p108">After receiving, importing and assigning the public certificate, you must stop and restart the Edge Server services. You do this by typing in the Lync Server Management console:</span></span>
    
       ```PowerShell
        Stop-CsWindowsService
       ```
    
       ```PowerShell
        Start-CsWindowsService
       ```

23. <span data-ttu-id="929c3-147">XMPP フェデレーションの DNS を構成するには、次の SRV レコードを外部 DNS\_: xmpp サーバーに追加します。\_tcp。\<ドメイン名\> SRV レコードは、エッジサーバーのアクセスエッジ FQDN に解決され、ポート値は5269になります。</span><span class="sxs-lookup"><span data-stu-id="929c3-147">To configure DNS for XMPP federation, you add the following SRV record to external DNS:\_xmpp-server.\_tcp.\<domain name\> The SRV record will resolve to the access edge FQDN of the Edge server, with a port value of 5269.</span></span> <span data-ttu-id="929c3-148">さらに、アクセスエッジサーバーの IP アドレスをポイントする "A" ホストレコード (たとえば、xmpp.contoso.com) を構成します。</span><span class="sxs-lookup"><span data-stu-id="929c3-148">Additionally, you configure an ‘A’ host record (for example, xmpp.contoso.com) that points to the IP address of the Access Edge Server.</span></span>
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="929c3-p110">複数のサイトにエッジ プールがある場合は、XMPP フェデレーション用に複数の SRV レコードを追加することをお勧めします。組織内のすべてのエッジ プールの SRV レコードを追加し、それらの SRV レコードそれぞれに異なる優先順位を指定します。すべてのエッジ プールが実行中の場合、XMPP 要求は第 1 優先順位のエッジ プールによってすべて処理されますが、そのエッジ プールがダウンした場合、XMPP フェデレーション機能を回復するために新しい SRV レコードを追加する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="929c3-p110">If you have Edge pools in multiple sites, we recommend that you add multiple SRV records for XMPP federation. Add a SRV record for every Edge pool in your organization, and give each of those SRV records a different priority. When all Edge pools are running, XMPP requests will all be handled by the Edge pool with the first priority, but if that Edge pool goes down you won’t then have to add a new SRV record to regain XMPP federation functionality.</span></span>

    
    </div>

24. <span data-ttu-id="929c3-152">フロントエンドで Lync Server 管理シェルを開き、次のコマンドを入力することによって、すべてのユーザーを有効にする新しい外部アクセス ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="929c3-152">Configure a new External Access Policy to enable all users by opening the Lync Server Management Shell on the Front End and typing:</span></span>
    
       ```PowerShell
        New-CsExternalAccessPolicy -Identity <name of policy to create.  If site scope, prepend with 'site:'> -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```PowerShell
        New-CsExternalAccessPolicy -Identity FedPic -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```PowerShell
        Get-CsUser | Grant-CsExternalAccessPolicy -PolicyName FedPic
       ```
    
    <span data-ttu-id="929c3-153">次のように入力して、外部ユーザーの XMPP アクセスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="929c3-153">Enable XMPP Access for External Users by typing:</span></span>
    
       ```PowerShell
        Set-CsExternalAccessPolicy -Identity <name of the policy being used> EnableXmppAccess $true
       ```
    
       ```PowerShell
        Set-CsExternalAccessPolicy -Identity FedPic -EnableXmppAccess $true
       ```

25. <span data-ttu-id="929c3-154">XMPP プロキシが展開されているエッジサーバーで、コマンドプロンプトまたは Windows PowerShell™コマンドラインインターフェイスを開き、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="929c3-154">On the Edge Server where the XMPP Proxy is deployed, open a Command Prompt or a Windows PowerShell™ command-line interface and type the following:</span></span>
    
       ```PowerShell
        Netstat -ano | findstr 5269
       ```
    
       ```PowerShell
        Netstat -ano | findstr 23456
       ```
    
    <span data-ttu-id="929c3-155">コマンド **netstat –ano** はネットワーク統計コマンドで、パラメーター **–ano** は、netstat にすべての接続およびリッスン ポートが表示されること、アドレスとポートが数値形式で表示されること、および所有プロセス ID が各接続に関連付けられていることを要求します。</span><span class="sxs-lookup"><span data-stu-id="929c3-155">The command **netstat –ano** is a network statistics command, the parameters **–ano** request that netstat display all connections and listening ports, address and ports are displayed in a numerical form, and that the owning process ID is associated with each connection.</span></span> <span data-ttu-id="929c3-156">文字**|** は、次のコマンド、 **findstr**、または検索文字列へのパイプを定義します。</span><span class="sxs-lookup"><span data-stu-id="929c3-156">The character **|** defines a pipe to the next command, **findstr**, or find string.</span></span> <span data-ttu-id="929c3-157">パラメーターとして findstr に渡される5269および23456の番号は、findstr に文字列5269と23456の出力を検索するように findstr に指示します。</span><span class="sxs-lookup"><span data-stu-id="929c3-157">The number 5269 and 23456 that is passed to findstr as a parameter instructs findstr to search the output of netstat for the strings 5269 and 23456.</span></span> <span data-ttu-id="929c3-158">XMPP が正しく構成されている場合、コマンドの結果として、外部 (ポート 5269) とエッジサーバーの内部 (ポート 23456) の両方のインターフェイスで、リッスンおよび確立された接続が発生します。</span><span class="sxs-lookup"><span data-stu-id="929c3-158">If XMPP is correctly configured, the result of the commands should result in listening and established connections, both on the external (port 5269) and the internal (port 23456) interfaces of the Edge Server.</span></span>
    
    <span data-ttu-id="929c3-159">コマンドで、5269 および 23456 の確立されたポートまたはリッスン ポートが返されない場合は、次のことを確認します。</span><span class="sxs-lookup"><span data-stu-id="929c3-159">If the commands do not return established or listening ports on 5269 and 23456, check the following:</span></span>

</div>

<div>

## <a name="troubleshooting-xmpp-federation"></a><span data-ttu-id="929c3-160">XMPP フェデレーションのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="929c3-160">Troubleshooting XMPP Federation</span></span>

1.  <span data-ttu-id="929c3-161">XMPP プロキシが実行されているかどうかを確認するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="929c3-161">To determine if the XMPP Proxy is running, do the following:</span></span>

2.  <span data-ttu-id="929c3-162">ローカル管理者のグループのメンバーとして、XMPP プロキシ サービスを実行しているエッジ サーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="929c3-162">Log on to the Edge server that is running the XMPP Proxy service as a member of the local administrator’s group.</span></span>

3.  <span data-ttu-id="929c3-163">[**スタート**] をクリックし、[**すべてのプログラム**]、[**管理ツール**] をクリックし、[**サービス**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="929c3-163">Click **Start**, click **All Programs**, click **Administrative Tools**, click **Services**</span></span>

4.  <span data-ttu-id="929c3-p112">[サービス] で、Lync Server XMPP 翻訳ゲートウェイ プロキシを探します。サービスは [**開始**] 状態である必要があります。開始していない場合は、ツールバーの [**開始**] アイコンをクリックします。アイコンは、緑色の右向き矢印として表示されます。</span><span class="sxs-lookup"><span data-stu-id="929c3-p112">In Services, locate Lync Server XMPP Translating Gateway Proxy. The service should be in the **Started** state. If it is not started, click the **Start** icon in the toolbar. The icon appears as a green, right-pointing arrow.</span></span>

5.  <span data-ttu-id="929c3-p113">サービスが [**開始**] に変更されたことを確認します。正常に開始された場合は、[**サービス**] を終了して続行します。</span><span class="sxs-lookup"><span data-stu-id="929c3-p113">Confirm that the service has changed to **Started**. If it has successfully started, close **Services** and continue.</span></span>
    
    <span data-ttu-id="929c3-170">サービスが正常に開始しなかった場合は、[管理ツール] から [イベント ビューアー] を開き、[**アプリケーションとサービス ログ**] の [**Lync Server**] 部分でエラーと警告を参照します。</span><span class="sxs-lookup"><span data-stu-id="929c3-170">If ther service has not successfully started, from Administrative Tools, open Event Viewer and refer to the errors and warnings in the **Lync Server** portion under **Applications and Services Logs**.</span></span>

6.  <span data-ttu-id="929c3-171">**Lync Server XMPP 翻訳ゲートウェイ** サービスが実行されたら、前に使用した netstat コマンドを再確認します。</span><span class="sxs-lookup"><span data-stu-id="929c3-171">Once the **Lync Server XMPP Translating Gateway** service is running, recheck the netstat commands used previously.</span></span> <span data-ttu-id="929c3-172">セッションが確立されていない場合、またはリッスンしていない場合は、トポロジビルダーで**Xmpp フェデレーションルート**が正しく構成されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="929c3-172">If you are not seeing established or listening sessions, check and ensure that the **XMPP Federation Route** is correctly configured in Topology Builder</span></span>

7.  <span data-ttu-id="929c3-173">トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="929c3-173">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

8.  <span data-ttu-id="929c3-174">トポロジ ビルダーを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server トポロジ ビルダー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="929c3-174">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

9.  <span data-ttu-id="929c3-175">トポロジビルダーで XMPP フェデレーションルートのサイトを選択し、[**サイトのフェデレーションルートの割り当て**] **xmpp フェデレーション**が、選択されている xmpp フェデレーションルートの割り当てとしてエッジサーバーまたはエッジプールを示していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="929c3-175">In Topology Builder, select the site for the XMPP federation route and review to confirm that the **Site federation route assignment** for **XMPP federation** shows your Edge Server or Edge pool as the selected XMPP federation route assignment.</span></span>
    
    <span data-ttu-id="929c3-176">ルート割り当てが正しくないか設定されていない場合は、サイトを右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="929c3-176">If the route assignment is incorrect or is not set, right-click the site, click **Edit Properties**.</span></span> <span data-ttu-id="929c3-177">[XMPP フェデレーション] チェックボックスをオンにして、適切なエッジサーバーまたはエッジプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="929c3-177">Select the XMPP federation check box and then select the correct Edge Server or Edge pool.</span></span>

10. <span data-ttu-id="929c3-178">トポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="929c3-178">Publish the topology.</span></span> <span data-ttu-id="929c3-179">詳細については、「 [Lync Server でのトポロジの公開 2013](lync-server-2013-publish-your-topology.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="929c3-179">For details, see [Publish your topology in Lync Server 2013](lync-server-2013-publish-your-topology.md)</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="929c3-180">必須ではありませんが、通常は不要なので、エッジサーバーを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="929c3-180">Though not required and typically not necessary, you may find that you will need to restart the Edge Servers</span></span>

    
    </div>

11. <span data-ttu-id="929c3-181">以前使用した netstat プロセスを使用して、エッジサーバーがポート5269とポート23456でセッションをリッスンしているか、セッションを確立したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="929c3-181">Using the netstat process used previously, confirm that the Edge Server is now listening or has established sessions on port 5269 and port 23456.</span></span>

12. <span data-ttu-id="929c3-182">必要なセッションがまだ表示されない場合は、イベント ビューアーで、通信の問題について考えられる原因を確認します。</span><span class="sxs-lookup"><span data-stu-id="929c3-182">If you still are not seeing the expected sessions, check the Event Viewer for possible contributing causes for the communication problem.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="929c3-183">関連項目</span><span class="sxs-lookup"><span data-stu-id="929c3-183">See Also</span></span>


[<span data-ttu-id="929c3-184">Lync Server 2013 の XMPP 構成の例-Google Talk との XMPP フェデレーション</span><span class="sxs-lookup"><span data-stu-id="929c3-184">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="929c3-185">Lync Server 2013 での XMPP フェデレーションパートナーの管理</span><span class="sxs-lookup"><span data-stu-id="929c3-185">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

