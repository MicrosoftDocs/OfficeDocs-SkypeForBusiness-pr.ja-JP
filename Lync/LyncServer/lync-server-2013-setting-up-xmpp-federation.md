---
title: 'Lync Server 2013: XMPP フェデレーションのセットアップ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up XMPP federation
ms:assetid: 5fda6cb7-8d4d-495d-90c7-601f1036e085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204939(v=OCS.15)
ms:contentKeyID: 48184270
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cda79f7b80d6f1bbdf2163ecf987f4a05949bfc4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848741"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-xmpp-federation-in-lync-server-2013"></a>Lync Server 2013 XMPP フェデレーションのセットアップ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-12-03_

エッジサーバーに XMPP プロキシを展開するには、Edge Server を XMPP フェデレーション用に構成する必要があります。 そのためには、次の手順を実行します。

<div>

## <a name="setting-up-xmpp-federation"></a>XMPP フェデレーションのセットアップ

1.  Lync Server 展開ウィザードがドメイン管理者グループと RTCUniversalServerAdmins グループのメンバーとしてインストールされているコンピューターにログオンします。

2.  フロントエンドサーバーで、Lync Server 展開ウィザードを開きます。 [Lync Server System のインストールまたは更新] をクリックし、[Lync Server コンポーネントのセットアップまたは削除] をクリックします。 [実行] をもう一度クリックします。

3.  Lync Server コンポーネントのセットアップで、[次へ] をクリックします。 概要画面には、実行中の操作が表示されます。 展開が完了したら、[ログの表示] をクリックして、利用可能なログファイルを表示します。 [完了] をクリックして展開を完了します。

4.  エッジサーバーで、Lync Server 展開ウィザードを開きます。 [Lync Server System のインストールまたは更新] をクリックし、[Lync Server コンポーネントのセットアップまたは削除] をクリックします。 [実行] をもう一度クリックします。

5.  Lync Server コンポーネントのセットアップで、[次へ] をクリックします。 概要画面には、実行中の操作が表示されます。 展開が完了したら、[ログの表示] をクリックして、利用可能なログファイルを表示します。 [完了] をクリックして展開を完了します。

6.  エッジサーバーの展開ウィザードで、[手順 3: 証明書の要求、インストール、または割り当て] の横にある [実行] をもう一度クリックします。
    
    <div class=" ">
    

    > [!TIP]  
    > 初めてエッジサーバーを展開する場合は、[実行] ではなく、[実行] と表示されます。

    
    </div>

7.  [利用可能な証明書タスク] ページで、[新しい証明書要求を作成する] をクリックします。

8.  [証明書の要求] ページで、[外部境界の証明書] をクリックします。

9.  [遅延または即時要求] ページで、[今すぐ要求を準備するが、後で送信する] チェックボックスをオンにします。

10. [証明書要求ファイル] ページで、要求を保存するファイルの完全パスとファイル名を入力します (たとえば、c:\\cert\_外部\_edge)。

11. [代替証明書テンプレートの指定] ページで、既定の Web サーバテンプレート以外のテンプレートを使用するには、[選択された証明機関に別の証明書テンプレートを使用する] チェックボックスをオンにします。

12. [名前およびセキュリティの設定] ページで、次の操作を行います。
    
    1.  [フレンドリ名] に、証明書の表示名を入力します。
    
    2.  ビット長では、ビット長 (通常は2048の既定値) を指定します。
    
    3.  [証明書の秘密キーをエクスポート可能としてマークする] チェックボックスがオンになっていることを確認する

13. [組織の情報] ページで、組織の名前と組織単位 (たとえば、部門や部署) を入力します。

14. [地理情報] ページで、場所情報を指定します。

15. [Subject Name/Subject Name] ページには、ウィザードによって自動的に入力される情報が表示されます。 追加の件名の代替名が必要な場合は、次の2つの手順で指定します。

16. [サブジェクト代替名 (San)] ページの SIP ドメイン設定で、[Domain] チェックボックスをオンにして sip を追加します。\<[\>件名の代替名] ボックスの一覧に sipdomain エントリを入力します。

17. [追加のサブジェクト代替名の構成] ページで、必要なその他のサブジェクトの代替名を指定します。
    
    <div class=" ">
    

    > [!TIP]  
    > XMPP プロキシがインストールされている場合、既定では、ドメイン名 (contoso.com など) が SAN エントリに設定されます。 他のエントリが必要な場合は、この手順で追加します。

    
    </div>

18. [要求の概要] ページで、要求の生成に使用する証明書情報を確認します。

19. コマンドの実行が完了したら、ログを表示するか、[次へ] をクリックして続行します。

20. [証明書要求ファイル] ページで、[完了] をクリックして、証明書ウィザードの [表示] または [終了] をクリックし、生成された証明書署名要求 (CSR) ファイルを表示できます。

21. 要求ファイルをコピーして、公開証明機関に提出します。

22. 公開証明書の受信、インポート、割り当てが完了したら、Edge Server サービスを停止して再起動する必要があります。 これを行うには、Lync Server 管理コンソールで次のように入力します。
    
       ```
        Stop-CsWindowsService
       ```
    
       ```
        Start-CsWindowsService
       ```

23. XMPP フェデレーション用の DNS を構成するには、次の SRV レコードを外部\_DNS に追加します。 xmpp-サーバー。\_tcp。\<ドメイン名\> SRV レコードはエッジサーバーのアクセスエッジ FQDN に解決され、ポート値は5269になります。 さらに、アクセスエッジサーバーの IP アドレスを参照する "A" ホストレコード (xmpp.contoso.com など) を構成します。
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > 複数のサイトにエッジプールがある場合は、XMPP フェデレーション用の複数の SRV レコードを追加することをお勧めします。 組織内のすべてのエッジプールに SRV レコードを追加し、各 SRV レコードに異なる優先順位を付けます。 すべてのエッジプールが実行されている場合は、最初の優先順位の Edge プールによってすべての XMPP 要求が処理されますが、エッジプールがダウンした場合は、新しい SRV レコードを追加しなくても、XMPP のフェデレーション機能を回復することはできません。

    
    </div>

24. 新しい外部アクセスポリシーを構成して、すべてのユーザーを有効にするには、次のようにします。
    
       ```
        New-CsExternalAccessPolicy -Identity <name of policy to create.  If site scope, prepend with 'site:'> -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```
        New-CsExternalAccessPolicy -Identity FedPic -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```
        Get-CsUser | Grant-CsExternalAccessPolicy -PolicyName FedPic
       ```
    
    外部ユーザーに対して XMPP アクセスを有効にするには、次のように入力します。
    
       ```
        Set-CsExternalAccessPolicy -Identity <name of the policy being used> EnableXmppAccess $true
       ```
    
       ```
        Set-CsExternalAccessPolicy -Identity FedPic -EnableXmppAccess $true
       ```

25. XMPP プロキシが展開されているエッジサーバーで、コマンドプロンプトまたは Windows PowerShell™のコマンドラインインターフェイスを開き、次のように入力します。
    
       ```
        Netstat -ano | findstr 5269
       ```
    
       ```
        Netstat -ano | findstr 23456
       ```
    
    コマンド**netstat – ano**は、ネットワーク統計情報のコマンドであり、パラメーター **– ano**で、すべての接続とリスニングポート、アドレスとポートが数値形式で表示され、所有しているプロセス ID が関連付けられています。各接続の場合。 この文字**|** は、次のコマンド、 **findstr**、または検索文字列へのパイプを定義します。 パラメーターとして findstr に渡される数値5269および23456では、文字列5269と23456の netstat の出力を検索するように findstr に指示します。 XMPP が適切に構成されている場合、コマンドの結果は、外部 (ポート 5269) と、エッジサーバーの内部 (ポート 23456) インターフェイスの両方で、リッスンと確立された接続になります。
    
    このコマンドによって5269および23456で、確立済みまたはリッスン中のポートが返されない場合は、次のことを確認してください。

</div>

<div>

## <a name="troubleshooting-xmpp-federation"></a>XMPP フェデレーションのトラブルシューティング

1.  XMPP プロキシが実行されているかどうかを確認するには、次の操作を行います。

2.  ローカル管理者のグループのメンバーとして XMPP プロキシサービスを実行しているエッジサーバーにログオンします。

3.  [**スタート**] をクリックし、[**すべてのプログラム**]、[**管理ツール**]、[**サービス**] をクリックします。

4.  [サービス] で、Lync Server XMPP の翻訳ゲートウェイプロキシを検索します。 サービスは**開始**状態である必要があります。 開始されていない場合は、ツールバーの [**スタート**] をクリックします。 アイコンは、緑の右向き矢印として表示されます。

5.  サービスが**開始**されたことを確認します。 正常に開始された場合は、[**サービス**] を閉じて続行します。
    
    他のサービスが正常に開始されない場合は、[管理ツール] で [イベントビューアー] を開き、[**アプリケーションとサービスログ**] の**Lync Server**セクションのエラーと警告を参照してください。

6.  **Lync Server XMPP の変換ゲートウェイ**サービスが実行されたら、前に使用した netstat コマンドを再確認します。 セッションが確立されているかリッスンしていない場合は、トポロジビルダーで**Xmpp フェデレーションルート**が正しく構成されていることを確認してください。

7.  トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。

8.  トポロジビルダーを開始します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server Topology Builder**] の順にクリックします。

9.  [トポロジビルダー] で、XMPP フェデレーションルートのサイトを選択し、[xmpp フェデレーション] の**サイトフェデレーションルート**の割り当てが、選択されている xmpp フェデレーションルートの割り当てとして edge サーバーまたはエッジプールを表示しているかどうかを確認します。 ****
    
    ルートの割り当てが間違っているか設定されていない場合は、サイトを右クリックし、[**プロパティの編集**] をクリックします。 [XMPP フェデレーション] チェックボックスをオンにして、適切なエッジサーバーまたはエッジプールを選択します。

10. トポロジを公開します。 詳細については、「 [Lync Server 2013 でトポロジを公開](lync-server-2013-publish-your-topology.md)する」を参照してください。
    
    <div class=" ">
    

    > [!TIP]  
    > ただし、必須ではありませんが、通常は不要です。エッジサーバーを再起動する必要があることがわかります。

    
    </div>

11. 前に使用した netstat プロセスを使用して、エッジサーバーがポート5269およびポート23456でセッションをリッスンしているか、または確立されていることを確認します。

12. それでも予期したセッションが表示されない場合は、通信問題の原因と考えられる原因についてイベントビューアーを確認してください。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での XMPP 構成の例  - Google Talk との XMPP フェデレーション](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[Lync Server 2013 での組織の XMPP フェデレーション パートナーの管理](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

