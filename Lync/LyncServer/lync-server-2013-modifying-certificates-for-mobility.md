---
title: 'Lync Server 2013: モビリティに合わせた証明書の変更'
TOCTitle: モビリティに合わせた証明書の変更
ms:assetid: 4e9107af-20f4-4c2a-8c98-ca35b39a4e2d
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Hh690015(v=OCS.15)
ms:contentKeyID: 48272051
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのモビリティに合わせた証明書の変更

 

_**トピックの最終更新日:** 2014-06-20_

Lync 環境とモバイル クライアントの間のセキュリティで保護された接続をサポートするため、追加のサブジェクトの別名 (SAN) エントリを使って、ディレクター プール、フロント エンド プール、およびリバース プロキシの Secure Socket Layer (SSL) 証明書を更新する必要があります。モビリティの証明書要件の詳細については、「[Lync Server 2013 でのモビリティの技術要件](lync-server-2013-technical-requirements-for-mobility.md)」の「証明書の要件」セクションを参照してください。ただし基本的には、追加の SAN エントリが含まれた新しい証明書を証明機関から取得し、この記事の手順に従って追加する必要があります。

まずは、証明書に既に含まれているサブジェクトの別名を把握しておくことをお勧めします。構成内容が不明な場合は、さまざまな方法で知ることができます。**Get-CsCertificate** やその他の PowerShell コマンドでこの情報を表示できますが (以下で説明します)、このデータは既定では切り捨てられるので、必要なプロパティをすべて見ることはできない可能性があります。証明書とそのすべてのプロパティを確認するには、Microsoft 管理コンソール (MMC) で証明書スナップインを読み込むか (これについても以下で説明します)、Lync Server 展開ウィザードで確認できます。

上記のとおり、次の手順では、Lync Server 管理シェルと MMC を使った証明書の更新方法について説明します。代わりに Lync Server 展開ウィザードの証明書ウィザードを使用したい場合、ディレクターやディレクター プールを構成済みであれば、その「[Lync Server 2013 でのディレクターの証明書の構成](lync-server-2013-configure-certificates-for-the-director.md)」を参照してください (構成済みでない場合もあります)。フロント エンド サーバーやフロント エンド プールの場合は、「[Lync Server 2013 でのサーバーの証明書の構成](lync-server-2013-configure-certificates-for-servers.md)」を参照してください。

Lync Server 2013 環境で 1 つの既定の証明書を使用することも、既定 (Web サービス以外全部)、WebServicesExternal、WebServicesInternal で別々の証明書を使用することもできます。構成に関わらず、以下の手順は役に立ちます。

## Lync Server 管理シェルを使用して、新しいサブジェクトの別名で証明書を更新するには

1.  ローカルの管理者権限とアクセス許可を持つアカウントを使って Lync Server 2013 サーバーにログオンする必要があります。また、手順 12. 以降で PowerShell の **Request-CsCertificate** を実行する場合は、指定した証明機関 (CA) に対する権限を持つ必要があります。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  更新した証明書を割り当てるには、サーバーに割り当てられている証明書とその用途を知っておく必要があります。コマンドラインで、次のように入力します。
    
        Get-CsCertificate

4.  前の手順の出力を調べ、1 つの証明書が複数のユーザーに割り当てられているのか、それとも用途ごとに異なる証明書が割り当てられているのかどうかを確認します。Use パラメーターを調べて証明書の使用方法を確認します。表示された証明書の Thumbprint パラメーターを比較して、同じ証明書に複数の用途が含まれているかどうかを確認します。Thumbprint パラメーターに注意してください。

5.  証明書を更新します。コマンドラインで、次のように入力します。
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    たとえば、**Get-CsCertificate** コマンドレットを実行して、Use が Default の証明書、Use が WebServicesInternal の証明書、および Use が WebServicesExternal の証明書が表示され、そのすべての Thumbprint 値が同じだった場合は、コマンドラインで、次のように入力します。
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    **重要:**
    
    用途別に別々の証明書が割り当てられている場合 (つまり、以上で確認した Thumbprint の値が証明書ごとに異なる場合)、上記の例のように複数の用途で **Set-CsCertificate** コマンドレットを実行**しないで**ください。この場合は、用途ごとに **Set-CsCertificate** コマンドレットを実行します。次に例を示します。
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  証明書を表示するには、\[**スタート**\]、\[**ファイル名を指定して実行**\] の順にクリックし、「MMC」と入力して Microsoft 管理コンソールを開きます。

7.  MMC メニューで、\[**ファイル**\]、\[**スナップインの追加と削除**\] の順に選択して、証明書を選択します。\[**追加**\] をクリックします。メッセージが表示されると、\[**コンピューター アカウント**\] を選択し \[**次へ**\] をクリックします。

8.  これが、証明書が格納されているサーバーである場合は、\[**ローカル コンピューター**\] を選択します。証明書が別のコンピューターに格納されている場合は、\[**別のコンピューター**\] を選択して、コンピューターの完全修飾ドメイン名を入力するか \[**参照**\] をクリックします。\[**選択するオブジェクト名を入力してください**\] で、コンピューターの名前を入力します。\[**名前の確認**\] をクリックします。コンピューターの名前が解決されたら、下線付きで表示されます。\[**OK**\] をクリックし、\[**完了**\] をクリックします。\[**OK**\] をクリックして選択を確定し、\[**スナップインの追加と削除**\] ダイアログを閉じます。

9.  証明書のプロパティを表示するには、\[**証明書**\]、\[**個人**\] の順に展開し、\[**証明書**\] を選択します。表示する証明書を右クリックし、\[**開く**\] を選択します。

10. \[**証明書**\] ビューで \[**詳細**\] を選択します。ここから、\[**サブジェクト**\] を選択して、証明書のサブジェクト名を選択できます。割り当てられているサブジェクト名と関連するプロパティが表示されます。

11. 割り当てられているサブジェクトの別名を表示するには、\[**サブジェクトの別名**\] を選択します。割り当てられているすべてのサブジェクトの別名が表示されます。ここに表示されるサブジェクトの別名の種類は、既定では \[**DNS 名**\] です。次のメンバーが表示されます。そのすべては、DNS ホスト (A、IPv6 の場合は AAAA) レコードで表示される完全修飾ドメイン名です。
    
      - このプールのプール名。これがプールでない場合は単一のサーバー名
    
      - 証明書が割り当てられるサーバーの名前
    
      - 簡単な URL レコード。通常、会議 (meet) とダイヤルイン (dialin)
    
      - Web サービスの内部名および外部名 (たとえば webpool01.contoso.net、webpool01.contoso.com)。トポロジ ビルダーでの選択内容および上書きされる Web サービスの選択に基づきます。
    
      - 既に割り当てられている場合は、lyncdiscover.\<SIP ドメイン名\> および lyncdiscoverinternal.\<SIP ドメイン名\> レコード。
    
    lyncdiscover および lyncdiscoverinternal SAN エントリが存在する場合、ユーザーが最も関心のある項目は最後の項目です。
    
    確認する証明書が複数ある場合は、これらの手順を繰り返します。この情報を取得すると、証明書ビューと MMC を閉じることができます。

12. 自動検出サービスのサブジェクトの別名が欠落している場合、および Default、WebServicesInternal、および WebServiceExternal タイプで単一の Default 証明書を使用している場合は、次の操作を行います。
    
      - Lync Server 管理シェル コマンドライン プロンプトで、次のように入力します。
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        多くの SIP ドメインが存在する場合、新しい AllSipDomain パラメーターを使用できません。代わりに、DomainName パラメーターを使用する必要があります。DomainName パラメーターを使用する場合は、lyncdiscoverinternal および lyncdiscover レコードの FQDN を定義する必要があります。たとえば、次のようになります。
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - 証明書を割り当てるには、次のように入力します。
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        "Thumbprint" は、新しく発行された証明書用に表示される拇印です。

13. Default、WebServicesInternal、および WebServicesExternal で個々の証明書を使用する際に、内部自動検出の SAN が欠落している場合は、次の操作を行います。
    
      - Lync Server 管理シェル コマンドライン プロンプトで、次のように入力します。
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        多くの SIP ドメインが存在する場合、新しい AllSipDomain パラメーターを使用できません。代わりに、DomainName パラメーターを使用する必要があります。DomainName パラメーターを使用する場合は、SIP ドメインの FQDN 用の適切なプレフィックスを使用する必要があります。たとえば、次のようになります。
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - 外部自動検出のサブジェクトの別名が欠落している場合、コマンドラインで、次のように入力します
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        多くの SIP ドメインが存在する場合、新しい AllSipDomain パラメーターを使用できません。代わりに、DomainName パラメーターを使用する必要があります。DomainName パラメーターを使用する場合は、SIP ドメインの FQDN 用の適切なプレフィックスを使用する必要があります。たとえば、次のようになります。
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - 個々の証明書タイプを割り当てるには、次のように入力します。
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        "Thumbprint" は、新しく発行された個々の証明書用に表示される拇印です。
    
    > [!NOTE]
    > 手順 12. と 13. は、実行するアカウントが証明機関に対する適切なアクセス許可を持っている場合にのみ実行してください。これらのアクセス許可があるアカウントでログインできなかったり、証明書でパブリックまたはリモートの証明機関を使用している場合は、この記事の最初で説明した Lync Server 展開ウィザードを使って証明書をリクエストする必要があります。

