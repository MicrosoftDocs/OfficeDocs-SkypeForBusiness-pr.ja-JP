---
title: 'Lync Server 2013: 自動検出用の証明書の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring certificates for Autodiscover
ms:assetid: 1842191d-df9a-41e0-9286-08c25f9b5dca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945617(v=OCS.15)
ms:contentKeyID: 51541453
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e2f39db761462f2f92ebde377fc9c9ecc5c27b6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146980"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-certificates-for-autodiscover-in-lync-server-2013"></a>Lync Server 2013 での自動検出用の証明書の構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-12-12_

ディレクタープール、フロントエンドプール、およびリバースプロキシの証明書には、Lync クライアントとのセキュリティで保護された接続をサポートするために、追加のサブジェクトの別名エントリが必要です。

<div>


> [!NOTE]  
> <STRONG>Get-CsCertificate</STRONG> コマンドレットを使用して、現在割り当てられている証明書に関する情報を表示できます。 ただし既定の表示では、証明書のプロパティは切り詰められ、SubjectAlternativeNames プロパティのすべての値が表示されるわけではありません。 <STRONG>Get-CsCertificate</STRONG>、<STRONG>Request-</STRONG>CsCertificate、および <STRONG>Set-CsCertificate</STRONG> コマンドレットを使用すると、情報の表示や、証明書の要求および割り当てを行うことができます。 ただし、現在の証明書のサブジェクトの別名 (SAN) のプロパティが何かわからない場合は、お勧めしません。 証明書とすべてのプロパティメンバーを表示するには、 <EM>Microsoft 管理コンソール (MMC)</EM>の証明書スナップインを使用するか、Lync Server 展開ウィザードを使用することをお勧めします。 Lync Server 展開ウィザードでは、証明書ウィザードを使用して証明書のプロパティを表示できます。 Lync Server 管理シェルと<EM>Microsoft 管理コンソール (MMC)</EM>を使用して証明書を表示、要求、および割り当てる手順については、以下の手順で詳細に説明します。 Lync Server 展開ウィザードを使用するには、オプションのディレクターまたはディレクタープールを展開している場合は、「 <A href="lync-server-2013-configure-certificates-for-the-director.md">Lync server 2013 でディレクターの証明書を構成</A>する」を参照してください。 フロントエンドサーバーまたはフロントエンドプールについては、詳細を参照してください。 <A href="lync-server-2013-configure-certificates-for-servers.md">Lync Server 2013 のサーバーの証明書を構成</A>します。<BR>この手順の最初のステップは準備ステップで、現在の証明書が果たす役割を確認します。 既定では、証明書に lyncdiscover は含まれていません。&lt;microsoft.rtc.management.xds.sipdomain&gt;または lyncdiscoverinternal。&lt;以前に Mobility&gt; service をインストールしたか、または事前に証明書を準備していない場合は、内部ドメイン名エントリ。 この手順では、例として、SIP ドメイン名に「contoso.com」、内部ドメイン名に「contoso.net」を使用します。<BR>Lync Server 2013 および Lync Server 2010 の既定の証明書の構成では、(web サービスを除くすべての目的で) 目的の既定の単一の証明書 (' Default ') を使用して、WebServicesExternal と Webservices Internal を指定します。 任意の構成では、用途ごとに個別の証明書を使用します。 証明書は、Lync Server 管理シェルおよび Windows PowerShell コマンドレットを使用して管理することも、Lync Server 展開ウィザードで証明書ウィザードを使用して管理することもできます。



</div>

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a>Lync Server 管理シェルを使用して新しいサブジェクトの別名を使用して証明書を更新するには

1.  ローカル管理者の権限とアクセス許可を持つアカウントを使用してコンピューターにログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

3.  サーバーに割り当てられている証明書および用途を確認します。この情報は次の手順で更新した証明書を割り当てるときに必要です。コマンド ラインで、次のように入力します。
    
        Get-CsCertificate

4.  前の手順の出力を調べ、1 つの証明書が複数のユーザーに割り当てられているのか、それとも用途ごとに異なる証明書が割り当てられているのかどうかを確認します。Use パラメーターを調べて証明書の使用方法を確認します。表示された証明書の Thumbprint パラメーターを比較して、同じ証明書に複数の用途が含まれているかどうかを確認します。

5.  証明書を更新します。 コマンド ラインで、次のように入力します。
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    たとえば、**Get-CsCertificate** コマンドレットを実行して、Use が Default の証明書、Use が WebServicesInternal の証明書、および Use が WebServicesExternal の証明書が表示され、そのすべての Thumbprint 値が同じだった場合は、コマンド ラインで、次のように入力します。
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    **重要:**
    
    用途ごとに個別の証明書が割り当てられている (証明書ごとに Thumbprint 値が異なる) 場合、複数の種類を使用して **Set-CsCertificate** コマンドレットを実行しないでください。 この場合、用途ごとに **Set-CsCertificate** コマンドレットを実行します。 次に例を示します。
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  証明書を表示するには、[**スタート**]、[**ファイル名を指定して実行**] を順にクリックし、MMC と入力して Microsoft 管理コンソールを開きます。

7.  MMC メニューで、[**ファイル**]、[**スナップインの追加と削除**] を順に選択して、証明書を選択します。[**追加**] をクリックします。メッセージが表示されたら、[**コンピューター アカウント**] を選択し [**次へ**] をクリックします。

8.  このコンピューターに証明書がある場合は、[**ローカルコンピューター**] を選択します。 証明書が別のコンピューターにある場合は、**別のコンピューター**を選択し、コンピューターの完全修飾ドメイン名を入力するか、または [**参照**] をクリックして [**選択するオブジェクト名を入力**してください] にコンピューターの名前を入力します。 [**名前の確認**] をクリックします。 コンピューターの名前が解決されると、下線が表示されます。 [ **OK**] をクリックし、[**完了**] をクリックします。 [ **OK** ] をクリックして選択を確定し、[スナップインの**追加と削除**] ダイアログを閉じます。
    
    <div>
    

    > [!IMPORTANT]  
    > コンソールに証明書が表示されない場合は、ユーザーまたはサービスが選択されていないことを確認してください。 [コンピューター] を選択する必要があります。または、probper 証明書を見つけることができません。

    
    </div>

9.  証明書のプロパティを表示するには、[**証明書**]、[**個人**] を順に展開し、[**証明書**] を選択します。表示する証明書を右クリックし、[**開く**] を選択します。

10. [**証明書**] ビューで [**詳細**] を選択します。ここから、[**サブジェクト**] を選択して、証明書のサブジェクト名を選択できます。割り当てられているサブジェクト名と関連するプロパティが表示されます。

11. 割り当てられたサブジェクトの別名を表示するには、[**サブジェクトの別名**] を選択します。 すべての割り当てられたサブジェクトの別名が表示されます。 プロパティに含まれるサブジェクトの別名は、既定では**DNS 名**の種類になっています。 次のメンバーが表示されます (すべてのメンバーが、DNS ホスト (A または if IPv6 AAAA) レコードで表される完全修飾ドメイン名である必要があります。
    
      - このプールのプール名。これがプールでない場合は単一のサーバー名
    
      - 証明書が割り当てられるサーバーの名前
    
      - 簡単な URL レコード。通常、会議 (meet) とダイヤルイン (dialin)
    
      - Web サービス内部および Web サービスの外部名 (たとえば、webpool01.contoso.net、webpool01.contoso.com) は、トポロジビルダーおよび優先度のある web サービスの選択肢に基づいて作成されます。
    
      - 既に割り当てられている場合は、lyncdiscover。\<microsoft.rtc.management.xds.sipdomain\>および lyncdiscoverinternal。\<microsoft.rtc.management.xds.sipdomain\>レコード
    
    lyncdiscover および lyncdiscoverinternal SAN エントリが存在する場合、ユーザーが最も関心のある項目は最後の項目です。
    
    この情報を取得したら、証明書ビューと MMC を閉じることができます。

12. 自動検出サービスの場合は、lyncdiscover を意味します。\>ドメイン名\>と lyncdiscoverinternal。\<ドメイン名\> (これが外部または内部証明書である場合に基づいて) サブジェクトの別名が欠落しており、Default、webservices Internal、および webserviceexternal types に対して単一の既定の証明書を使用している場合は、次の操作を行います。
    
      - Lync Server 管理シェルコマンドラインプロンプトで、次のように入力します。
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        多くの SIP ドメインが存在する場合、新しい AllSipDomain パラメーターを使用できません。 代わりに、DomainName パラメーターを使用する必要があります。 DomainName パラメーターを使用する場合は、lyncdiscoverinternal および lyncdiscover レコードの FQDN を定義する必要があります。 たとえば、次のようになります。
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - 証明書を割り当てるには、次のように入力します。
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        「Thumbprint」は、新しく発行された証明書用に表示される拇印です。

13. Default、WebServicesInternal、および WebServicesExternal で個々の証明書を使用する際に、内部自動検出のサブジェクトの別名が欠落している場合は、次の操作を行います。
    
      - Lync Server 管理シェルコマンドラインプロンプトで、次のように入力します。
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        多くの SIP ドメインが存在する場合、新しい AllSipDomain パラメーターを使用できません。代わりに、DomainName パラメーターを使用する必要があります。DomainName パラメーターを使用する場合は、次のように、SIP ドメインの FQDN 用の適切なプレフィックスを使用する必要があります。
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - 外部自動検出のサブジェクトの別名が欠落している場合、コマンド ラインで、次のように入力します
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        多くの SIP ドメインが存在する場合、新しい AllSipDomain パラメーターを使用できません。代わりに、DomainName パラメーターを使用する必要があります。DomainName パラメーターを使用する場合は、次のように、SIP ドメインの FQDN 用の適切なプレフィックスを使用する必要があります。
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - 個々の証明書タイプを割り当てるには、次のように入力します。
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        「Thumbprint」は、新しく発行された個々の証明書用に表示される拇印です。

</div>

</div>

<span> </span>

</div>

</div>

</div>

