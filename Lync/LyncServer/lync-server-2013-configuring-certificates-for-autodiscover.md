---
title: 自動検出用の証明書の構成
TOCTitle: 自動検出用の証明書の構成
ms:assetid: 1842191d-df9a-41e0-9286-08c25f9b5dca
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ945617(v=OCS.15)
ms:contentKeyID: 52056542
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 自動検出用の証明書の構成

 

_**トピックの最終更新日:** 2012-12-12_

ディレクター プール、フロント エンド プール、およびリバース プロキシの証明書では、Lync クライアントとのセキュリティで保護された接続をサポートするために追加のサブジェクトの別名エントリが必要です。

> [!NOTE]  
> <strong>Get-CsCertificate</strong> コマンドレットを使用して、現在割り当てられている証明書に関する情報を表示できます。ただし既定の表示では、証明書のプロパティは切り詰められ、SubjectAlternativeNames プロパティのすべての値が表示されるわけではありません。<strong>Get-CsCertificate</strong>、<strong>Request-</strong>CsCertificate、および <strong>Set-CsCertificate</strong> コマンドレットを使用すると、情報の表示や、証明書の要求および割り当てを行うことができます。ただし、現在の証明書のサブジェクトの別名 (SAN) のプロパティが何かわからない場合は、お勧めしません。証明書とすべてのプロパティのメンバーを表示するには、証明書スナップインの Microsoft 管理コンソール (MMC) を使用するか、Lync Server 展開ウィザードを使用します。Lync Server 展開ウィザードでは、証明書ウィザードを使用して証明書のプロパティを表示できます。Lync Server 管理シェルおよび Microsoft 管理コンソール (MMC) を使用して証明書の表示、要求、および割り当てを行う方法の詳細については、以下の手順を参照してください。Lync Server 展開ウィザードを使用するには、任意のディレクターまたはディレクター プールを展開している場合は、「<a href="lync-server-2013-configure-certificates-for-the-director.md">Lync Server 2013 でのディレクターの証明書の構成</a>」を参照してください。フロント エンド サーバーまたはフロント エンド プールを展開している場合は、「<a href="lync-server-2013-configure-certificates-for-servers.md">Lync Server 2013 でのサーバーの証明書の構成</a>」を参照してください。<br />
> この手順の最初のステップは準備ステップで、現在の証明書が果たす役割を確認します。Mobility Service をインストールしていなかったり、証明書を事前に準備していない場合、既定では、証明書には lyncdiscover.&lt;SIP ドメイン&gt; または lyncdiscoverinternal.&lt;内部ドメイン名&gt; エントリはありません。この手順では、例として、SIP ドメイン名に「contoso.com」、内部ドメイン名に「contoso.net」を使用します。<br />
> Lync Server 2013 および Lync Server 2010 の既定の証明書構成は、Default (Web サービス以外のすべての用途に対応)、WebServicesExternal、および WebServicesInternal の用途を持つ単一の証明書 (「Default」という名前) を使用します。任意の構成では、用途ごとに個別の証明書を使用します。証明書は、Lync Server 管理シェルおよび Windows PowerShell コマンドレットを使用するか、Lync Server 展開ウィザードの証明書ウィザードを使用して管理できます。


## Lync Server 管理シェルを使用して、新しいサブジェクトの別名で証明書を更新するには

1.  ローカル管理者の権限とアクセス許可を持つアカウントを使用してコンピューターにログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  サーバーに割り当てられている証明書および用途を確認します。この情報は次の手順で更新した証明書を割り当てるときに必要です。コマンドラインで、次のように入力します。
    
        Get-CsCertificate

4.  前の手順の出力を調べ、1 つの証明書が複数のユーザーに割り当てられているのか、それとも用途ごとに異なる証明書が割り当てられているのかどうかを確認します。Use パラメーターを調べて証明書の使用方法を確認します。表示された証明書の Thumbprint パラメーターを比較して、同じ証明書に複数の用途が含まれているかどうかを確認します。

5.  証明書を更新します。コマンドラインで、次のように入力します。
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    たとえば、**Get-CsCertificate** コマンドレットを実行して、Use が Default の証明書、Use が WebServicesInternal の証明書、および Use が WebServicesExternal の証明書が表示され、そのすべての Thumbprint 値が同じだった場合は、コマンドラインで、次のように入力します。
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    **重要:**
    
    用途ごとに個別の証明書が割り当てられている (証明書ごとに Thumbprint 値が異なる) 場合、複数の種類を使用して **Set-CsCertificate** コマンドレットを実行しないでください。この場合、用途ごとに **Set-CsCertificate** コマンドレットを実行します。たとえば、次のようになります。
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  証明書を表示するには、\[**スタート**\]、\[**ファイル名を指定して実行**\] の順にクリックし、「MMC」と入力して Microsoft 管理コンソールを開きます。

7.  MMC メニューで、\[**ファイル**\]、\[**スナップインの追加と削除**\] の順に選択して、証明書を選択します。\[**追加**\] をクリックします。メッセージが表示されると、\[**コンピューター アカウント**\] を選択し \[**次へ**\] をクリックします。

8.  証明書がこのコンピューターに格納されている場合は、\[**ローカル コンピューター**\] を選択します。証明書が別のコンピューターに格納されている場合は、\[**別のコンピューター**\] を選択して、コンピューターの完全修飾ドメイン名を入力するか \[**参照**\] をクリックします。\[**選択するオブジェクト名を入力してください**\] で、コンピューターの名前を入力します。\[**名前の確認**\] をクリックします。コンピューターの名前が解決されると、下線付きで表示されます。\[**OK**\] をクリックし、\[**完了**\] をクリックします。\[**OK**\] をクリックして選択を確定し、\[**スナップインの追加と削除**\] ダイアログを閉じます。
    

    > [!IMPORTANT]
    > 証明書がコンソールに表示されない場合、User または Service を選択していないことを確認します。Computer を選択する必要があります。それ以外の場合、適切な証明書を見つけることはできません。



9.  証明書のプロパティを表示するには、\[**証明書**\]、\[**個人**\] の順に展開し、\[**証明書**\] を選択します。表示する証明書を右クリックし、\[**開く**\] を選択します。

10. \[**証明書**\] ビューで \[**詳細**\] を選択します。ここから、\[**サブジェクト**\] を選択して、証明書のサブジェクト名を選択できます。割り当てられているサブジェクト名と関連するプロパティが表示されます。

11. 割り当てられているサブジェクトの別名を表示するには、\[**サブジェクトの別名**\] を選択します。割り当てられているすべてのサブジェクトの別名が表示されます。プロパティに表示されるサブジェクトの別名の種類は、既定では \[**DNS 名**\] です。次のメンバーが表示されます。そのすべては、DNS ホスト (A、Ipv6 の場合は AAAA) レコードで表示される完全修飾ドメイン名です。
    
      - このプールのプール名。これがプールでない場合は単一のサーバー名
    
      - 証明書が割り当てられるサーバーの名前
    
      - 簡単な URL レコード。通常、会議 (meet) とダイヤルイン (dialin)
    
      - Web サービスの内部名および外部名 (たとえば webpool01.contoso.net、webpool01.contoso.com)。トポロジ ビルダーでの選択内容および上書きされる Web サービスの選択に基づきます。
    
      - 既に割り当てられている場合は、lyncdiscover.\<SIP ドメイン名\> および lyncdiscoverinternal.\<SIP ドメイン名\> レコード。
    
    lyncdiscover および lyncdiscoverinternal SAN エントリが存在する場合、ユーザーが最も関心のある項目は最後の項目です。
    
    この情報を取得すると、証明書ビューと MMC を閉じることができます。

12. 自動検出サービス、つまり、lyncdiscover.\>ドメイン名\> および lyncdiscoverinternal.\<ドメイン名\> (これが外部または内部のどちらの証明書であるかに基づく) のサブジェクトの別名が欠落している場合、および Default、WebServicesInternal、および WebServiceExternal タイプで単一の Default 証明書を使用している場合は、次の操作を行います。
    
      - Lync Server 管理シェル コマンドライン プロンプトで、次のように入力します。
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        多くの SIP ドメインが存在する場合、新しい AllSipDomain パラメーターを使用できません。代わりに、DomainName パラメーターを使用する必要があります。DomainName パラメーターを使用する場合は、lyncdiscoverinternal および lyncdiscover レコードの FQDN を定義する必要があります。たとえば、次のようになります。
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - 証明書を割り当てるには、次のように入力します。
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        "Thumbprint" は、新しく発行された証明書用に表示される拇印です。

13. Default、WebServicesInternal、および WebServicesExternal で個々の証明書を使用する際に、内部自動検出のサブジェクトの別名が欠落している場合は、次の操作を行います。
    
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

