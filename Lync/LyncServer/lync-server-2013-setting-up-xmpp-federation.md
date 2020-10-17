---
title: 'Lync Server 2013: XMPP フェデレーションのセットアップ'
description: 'Lync Server 2013: XMPP フェデレーションのセットアップ。'
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
ms.openlocfilehash: b8a1fa15e399b0e0596a697420042b7504f8b791
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555703"
---
# <a name="setting-up-xmpp-federation-in-lync-server-2013"></a>Lync Server 2013 での XMPP フェデレーションのセットアップ

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-12-03_

XMPP プロキシをエッジ サーバーに展開するには、エッジ サーバーを XMPP フェデレーション用に構成する必要があります。これを行うには、以下の手順を実行します。

<div>

## <a name="setting-up-xmpp-federation"></a>XMPP フェデレーションのセットアップ

1.  Lync Server 展開ウィザードがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。

2.  フロントエンド サーバーで、Lync Server 展開ウィザードを開きます。[Lync Server システムのインストールまたは更新] をクリックして、[Lync Server コンポーネントのセットアップまたは削除] をクリックします。[再実行] をクリックします。

3.  [Lync Server コンポーネントのセットアップ] で、[次へ] をクリックします。概要画面に、実行された処理が表示されます。展開が完了したら、[ログの表示] をクリックして、利用可能なログ ファイルを表示します。[完了] をクリックして、展開を完了します。

4.  エッジ サーバーで、Lync Server 展開ウィザードを開きます。[Lync Server システムのインストールまたは更新] をクリックして、[Lync Server コンポーネントのセットアップまたは削除] をクリックします。[再実行] をクリックします。

5.  [Lync Server コンポーネントのセットアップ] で、[次へ] をクリックします。概要画面に、実行された処理が表示されます。展開が完了したら、[ログの表示] をクリックして、利用可能なログ ファイルを表示します。[完了] をクリックして、展開を完了します。

6.  エッジ サーバーの展開ウィザードで、[ステップ 3: 証明書の要求、インストール、または割り当て] の横にある [再実行] をクリックします。
    
    <div class=" ">
    

    > [!TIP]  
    > 初めてエッジ サーバーを展開する場合は、[再実行] ではなく [実行] が表示されます。

    
    </div>

7.  [利用可能な証明書タスク] ページで、[新しい証明書要求を作成する] をクリックします。

8.  [証明書の要求] ページで、[外部エッジの証明書] をクリックします。

9.  [証明書要求の送信方法] ページで、[要求を準備して後で送信する] チェック ボックスをオンにします。

10. [証明書要求ファイル] ページで、要求を保存するファイルの完全なパスとファイル名を入力します (たとえば、c: \\ cert \_ 外部 \_ edge. .cer)。

11. [代替証明書テンプレートの指定] ページで、既定の WebServer テンプレート以外のテンプレートを使用するには、[選択した証明機関に別の証明書テンプレートを使用する] チェック ボックスをオンにします。

12. [名前およびセキュリティの設定] ページで、次の操作を行います。
    
    1.  [フレンドリ名] に、証明書の表示名を入力します。
    
    2.  [ビット長] で、ビット長を指定します (通常は既定値の [2048])。
    
    3.  [証明書の秘密キーをエクスポート可能としてマークする] チェック ボックスがオンになっていることを確認します。

13. [組織情報] ページで、組織の名前と組織単位 (部や課など) を入力します。

14. [地理情報] ページで、場所情報を指定します。

15. [サブジェクト名/サブジェクト代替名] ページに、ウィザードによって自動的に設定される情報が表示されます。追加のサブジェクトの別名が必要な場合、次の 2 つの手順で指定します。

16. [サブジェクト代替名 (San) の SIP ドメイン設定] ページで、[ドメイン] チェックボックスをオンにして sip を追加します。\<sipdomain\> サブジェクトの別名リストへのエントリ。

17. [追加のサブジェクト代替名の構成] ページで、必要な追加のサブジェクトの別名を指定します。
    
    <div class=" ">
    

    > [!TIP]  
    > XMPP プロキシがインストールされている場合は、既定でドメイン名 (contoso.com など) が SAN エントリに設定されています。別のエントリが必要な場合は、この手順で追加します。

    
    </div>

18. [要求の概要] ページで、要求を生成するために使用する証明書情報を確認します。

19. コマンドの実行が完了したら、ログを表示するか、または [次へ] をクリックして続行します。

20. [証明書要求ファイル] ページで、[表示] をクリックして生成済みの証明書の署名要求 (CSR) ファイルを表示するか、または [完了] をクリックして証明書ウィザードを終了します。

21. 要求ファイルをコピーして、公的証明機関に送信します。

22. パブリック証明書の受信、インポート、および割り当てを行った後、エッジ サーバー サービスを停止して再起動する必要があります。これは、Lync Server 管理コンソールで次のコマンドを入力して行います。
    
       ```PowerShell
        Stop-CsWindowsService
       ```
    
       ```PowerShell
        Start-CsWindowsService
       ```

23. XMPP フェデレーションの DNS を構成するには、次の SRV レコードを外部 DNS: \_ xmpp サーバーに追加します。 \_プロトコル.\<domain name\> SRV レコードは、エッジサーバーのアクセスエッジ FQDN に解決され、ポート値は5269になります。 さらに、アクセスエッジサーバーの IP アドレスをポイントする "A" ホストレコード (たとえば、xmpp.contoso.com) を構成します。
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > 複数のサイトにエッジ プールがある場合は、XMPP フェデレーション用に複数の SRV レコードを追加することをお勧めします。組織内のすべてのエッジ プールの SRV レコードを追加し、それらの SRV レコードそれぞれに異なる優先順位を指定します。すべてのエッジ プールが実行中の場合、XMPP 要求は第 1 優先順位のエッジ プールによってすべて処理されますが、そのエッジ プールがダウンした場合、XMPP フェデレーション機能を回復するために新しい SRV レコードを追加する必要はありません。

    
    </div>

24. フロントエンドで Lync Server 管理シェルを開き、次のコマンドを入力することによって、すべてのユーザーを有効にする新しい外部アクセス ポリシーを構成します。
    
       ```PowerShell
        New-CsExternalAccessPolicy -Identity <name of policy to create.  If site scope, prepend with 'site:'> -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```PowerShell
        New-CsExternalAccessPolicy -Identity FedPic -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```PowerShell
        Get-CsUser | Grant-CsExternalAccessPolicy -PolicyName FedPic
       ```
    
    次のように入力して、外部ユーザーの XMPP アクセスを有効にします。
    
       ```PowerShell
        Set-CsExternalAccessPolicy -Identity <name of the policy being used> EnableXmppAccess $true
       ```
    
       ```PowerShell
        Set-CsExternalAccessPolicy -Identity FedPic -EnableXmppAccess $true
       ```

25. XMPP プロキシが展開されているエッジサーバーで、コマンドプロンプトまたは Windows PowerShell™コマンドラインインターフェイスを開き、次のように入力します。
    
       ```PowerShell
        Netstat -ano | findstr 5269
       ```
    
       ```PowerShell
        Netstat -ano | findstr 23456
       ```
    
    コマンド **netstat –ano** はネットワーク統計コマンドで、パラメーター **–ano** は、netstat にすべての接続およびリッスン ポートが表示されること、アドレスとポートが数値形式で表示されること、および所有プロセス ID が各接続に関連付けられていることを要求します。 文字は、 **|** 次のコマンド、 **findstr**、または検索文字列へのパイプを定義します。 パラメーターとして findstr に渡される5269および23456の番号は、findstr に文字列5269と23456の出力を検索するように findstr に指示します。 XMPP が正しく構成されている場合、コマンドの結果として、外部 (ポート 5269) とエッジサーバーの内部 (ポート 23456) の両方のインターフェイスで、リッスンおよび確立された接続が発生します。
    
    コマンドで、5269 および 23456 の確立されたポートまたはリッスン ポートが返されない場合は、次のことを確認します。

</div>

<div>

## <a name="troubleshooting-xmpp-federation"></a>XMPP フェデレーションのトラブルシューティング

1.  XMPP プロキシが実行されているかどうかを確認するには、次の手順に従います。

2.  ローカル管理者のグループのメンバーとして、XMPP プロキシ サービスを実行しているエッジ サーバーにログオンします。

3.  [**スタート**] をクリックし、[**すべてのプログラム**]、[**管理ツール**] をクリックし、[**サービス**] をクリックします。

4.  [サービス] で、Lync Server XMPP 翻訳ゲートウェイ プロキシを探します。サービスは [**開始**] 状態である必要があります。開始していない場合は、ツールバーの [**開始**] アイコンをクリックします。アイコンは、緑色の右向き矢印として表示されます。

5.  サービスが [**開始**] に変更されたことを確認します。正常に開始された場合は、[**サービス**] を終了して続行します。
    
    サービスが正常に開始しなかった場合は、[管理ツール] から [イベント ビューアー] を開き、[**アプリケーションとサービス ログ**] の [**Lync Server**] 部分でエラーと警告を参照します。

6.  **Lync Server XMPP 翻訳ゲートウェイ** サービスが実行されたら、前に使用した netstat コマンドを再確認します。 セッションが確立されていない場合、またはリッスンしていない場合は、トポロジビルダーで **Xmpp フェデレーションルート** が正しく構成されていることを確認してください。

7.  トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。

8.  トポロジ ビルダーを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server トポロジ ビルダー**] の順にクリックします。

9.  トポロジビルダーで XMPP フェデレーションルートのサイトを選択し、[ **サイトのフェデレーションルートの割り当て** ] **xmpp フェデレーション** が、選択されている xmpp フェデレーションルートの割り当てとしてエッジサーバーまたはエッジプールを示していることを確認します。
    
    ルート割り当てが正しくないか設定されていない場合は、サイトを右クリックし、[**プロパティの編集**] をクリックします。 [XMPP フェデレーション] チェックボックスをオンにして、適切なエッジサーバーまたはエッジプールを選択します。

10. トポロジを公開します。 詳細については、「 [Lync Server でのトポロジの公開 2013](lync-server-2013-publish-your-topology.md) 」を参照してください。
    
    <div class=" ">
    

    > [!TIP]  
    > 必須ではありませんが、通常は不要なので、エッジサーバーを再起動する必要があります。

    
    </div>

11. 以前使用した netstat プロセスを使用して、エッジサーバーがポート5269とポート23456でセッションをリッスンしているか、セッションを確立したことを確認します。

12. 必要なセッションがまだ表示されない場合は、イベント ビューアーで、通信の問題について考えられる原因を確認します。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 の XMPP 構成の例-Google Talk との XMPP フェデレーション](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[Lync Server 2013 での XMPP フェデレーションパートナーの管理](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

