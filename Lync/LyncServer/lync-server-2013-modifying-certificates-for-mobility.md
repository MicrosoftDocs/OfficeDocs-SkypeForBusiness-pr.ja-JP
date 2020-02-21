---
title: 'Lync Server 2013: モビリティの証明書の変更'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modifying certificates for mobility
ms:assetid: 4e9107af-20f4-4c2a-8c98-ca35b39a4e2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690015(v=OCS.15)
ms:contentKeyID: 48184120
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f64676494916bf2c2bd71399bbdd04642da50cee
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217303"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="modifying-certificates-for-mobility-in-lync-server-2013"></a>Lync Server 2013 でのモビリティの証明書の変更

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-06-20_

Lync 環境とモバイルクライアント間のセキュリティ保護された接続をサポートするために、ディレクタープール、フロントエンドプール、リバースプロキシの Secure Socket Layer (SSL) 証明書を、追加のサブジェクトの別名で更新する必要があります (SAN) エントリ。 モビリティの証明書の要件の詳細を確認する必要がある場合は、「 [Lync Server 2013 のモビリティの技術要件](lync-server-2013-technical-requirements-for-mobility.md)」の「証明書の要件」セクションを参照してください。ただし、基本的には、追加の SAN エントリが含まれる証明機関から新しい証明書を取得してから、この記事の手順を使用してそれらの証明書を追加

開始する前に、証明書に既に存在するサブジェクトの別名を知っておくことをお勧めします。 既に構成されている内容がわからない場合は、さまざまな方法で見つけることができます。このオプションを使用して、この情報を表示することができます (以下を参照)。既定**では、** データは切り捨てられるため、必要なすべてのプロパティを表示することはできません。 証明書とそのすべてのプロパティを適切に表示するには、Microsoft 管理コンソール (MMC) に移動して、証明書スナップイン (以下を参照) を読み込むか、Lync Server 展開ウィザードを確認するだけです。

前述したように、次の手順に従って、Lync Server 管理シェルと MMC を使用して証明書を更新します。 このために Lync Server 展開ウィザードで証明書ウィザードを使用することに関心がある場合は、ディレクターまたはディレクタープールに対して、 [2013 ディレクターの証明書を構成](lync-server-2013-configure-certificates-for-the-director.md)してください (必要でない場合があります)。 フロントエンドサーバーまたはフロントエンドプールについては、「 [Lync Server 2013 のサーバーの証明書の構成](lync-server-2013-configure-certificates-for-servers.md)」を参照してください。

最後に、Lync Server 2013 環境に既定の証明書が1つしかない場合や、既定の証明書 (web サービス以外のすべてのもの)、WebServicesExternal、Webservices の内部が存在する場合があることを念頭に置いておくとよいでしょう。 どのような構成であっても、これらの手順はお役になるはずです。

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a>Lync Server 管理シェルを使用して新しいサブジェクトの別名を使用して証明書を更新するには

1.  ローカル管理者の権限とアクセス許可を持つアカウントを使用して、Lync Server 2013 サーバーにログオンする必要があります。 また、手順12以降で PowerShell**要求-CsCertificate**を実行している場合は、指定された証明機関 (CA) に対する権限をアカウントに付与する必要があります。

2.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

3.  更新された証明書を割り当てる前に、サーバーに割り当てられている証明書と使用の種類を確認する必要があります。 コマンドラインで、次のように入力します。
    
        Get-CsCertificate

4.  前の手順の出力を確認して、複数の使用に対して1つの証明書が割り当てられているかどうか、またはそれぞれの使用に異なる証明書が割り当てられているかどうかを確認します。 証明書の使用方法については、Use パラメーターを参照してください。 表示された証明書の Thumbprint パラメーターを比較して、同じ証明書に複数の用途が含まれているかどうかを確認します。 拇印パラメーターに注意してください。

5.  証明書を更新します。 コマンド ラインで、次のように入力します。
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    たとえば、WebServicesExternal**コマンドレットで**、既定値を使用した証明書が表示されていて、もう1つは Webservices internal を使用していて、もう1つはコマンドラインで同じ拇印値を持っていた場合は、次のように入力します。
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    **重要:**
    
    各使用に個別の証明書が割り当てられている場合 (上記でチェックした Thumbprint の値が各証明書で異なる) は、上記の例のように、複数の種類を使用して、 **cscertificate**コマンドレットを実行し**ない**ことが重要です。 この場合、用途ごとに **Set-CsCertificate** コマンドレットを実行します。 次に例を示します。
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  証明書 (または証明書) を表示するには、[**スタート**] をクリックし、[**実行**] をクリックします。 「MMC」と入力して、Microsoft 管理コンソールを開きます。

7.  MMC メニューで、[**ファイル**]、[**スナップインの追加と削除**] を順に選択して、証明書を選択します。 [**追加**] をクリックします。 メッセージが表示されたら、[**コンピューター アカウント**] を選択し [**次へ**] をクリックします。

8.  証明書が配置されているサーバーの場合は、[**ローカルコンピューター**] を選択します。 証明書が別のコンピューターにある場合は、**別のコンピューター**を選択し、コンピューターの完全修飾ドメイン名を入力するか、または [**参照**] をクリックして [**選択するオブジェクト名**を入力してください] をクリックし、コンピューターの名前を入力します。 [**名前の確認**] をクリックします。 コンピューターの名前が解決されると、その名前に下線が付きます。 [ **OK**] をクリックし、[**完了**] をクリックします。 [ **OK** ] をクリックして選択を確定し、[スナップインの**追加と削除**] ダイアログを閉じます。

9.  証明書のプロパティを表示するには、[**証明書**]、[**個人**] を順に展開し、[**証明書**] を選択します。表示する証明書を右クリックし、[**開く**] を選択します。

10. [**証明書**] ビューで [**詳細**] を選択します。ここから、[**サブジェクト**] を選択して、証明書のサブジェクト名を選択できます。割り当てられているサブジェクト名と関連するプロパティが表示されます。

11. 割り当てられたサブジェクトの別名を表示するには、[**サブジェクトの別名**] を選択します。 割り当てられているすべてのサブジェクトの別名がここに表示されます。 既定では、ここに記載されているサブジェクトの別名が**DNS 名**の種類になっています。 次のメンバーが表示されます (すべてのメンバーが、DNS ホスト (A または if IPv6 AAAA) レコードで表される完全修飾ドメイン名である必要があります。
    
      - このプールのプール名、またはこれがプールでない場合は単一のサーバー名
    
      - 証明書が割り当てられるサーバーの名前
    
      - 簡単な URL レコード。通常、会議 (meet) とダイヤルイン (dialin)
    
      - Web サービス内部および Web サービスの外部名 (たとえば、webpool01.contoso.net、webpool01.contoso.com) は、トポロジビルダーおよび優先度のある web サービスの選択肢に基づいて作成されます。
    
      - 既に割り当てられている場合は、lyncdiscover。\<microsoft.rtc.management.xds.sipdomain\>および lyncdiscoverinternal。\<microsoft.rtc.management.xds.sipdomain\>レコード
    
    Lyncdiscover および lyncdiscoverinternal の SAN エントリがある場合は、最後の項目が最も関心を持っています。
    
    複数の証明書をチェックする場合は、この手順を繰り返します。 この情報を取得したら、証明書ビューと MMC を閉じることができます。

12. 自動検出サービスのサブジェクトの別名が欠落している場合、および Default、WebServicesInternal、および WebServiceExternal タイプで単一の Default 証明書を使用している場合は、次の操作を行います。
    
      - Lync Server 管理シェルコマンドラインプロンプトで、次のように入力します。
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        SIP ドメインが多数ある場合は、新しい AllSipDomain パラメーターを使用することはできません。 代わりに、DomainName パラメーターを使用する必要があります。 DomainName パラメーターを使用する場合は、lyncdiscoverinternal および lyncdiscover レコードの FQDN を定義する必要があります。 たとえば、次のようになります。
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - 証明書を割り当てるには、次のように入力します。
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        「Thumbprint」は、新しく発行された証明書用に表示される拇印です。

13. Default、Webservices Internal、および WebServicesExternal に別々の証明書を使用する場合、内部自動検出 SAN が存在しない場合は、次の手順を実行します。
    
      - Lync Server 管理シェルコマンドラインプロンプトで、次のように入力します。
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        SIP ドメインが多数ある場合は、新しい AllSipDomain パラメーターを使用することはできません。 代わりに、DomainName パラメーターを使用する必要があります。 DomainName パラメーターを使用する場合は、SIP ドメインの FQDN に適切なプレフィックスを使用する必要があります。 次に例を示します。
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - 外部自動検出のサブジェクトの別名が欠落している場合、コマンド ラインで、次のように入力します
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        SIP ドメインが多数ある場合は、新しい AllSipDomain パラメーターを使用することはできません。 代わりに、DomainName パラメーターを使用する必要があります。 DomainName パラメーターを使用する場合は、SIP ドメインの FQDN に適切なプレフィックスを使用する必要があります。 次に例を示します。
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - 個々の証明書タイプを割り当てるには、次のように入力します。
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        「Thumbprint」は、新しく発行された個々の証明書用に表示される拇印です。
    
    <div>
    

    > [!NOTE]  
    > 注として、手順12および13は、それらを実行しているアカウントが適切なアクセス許可を持つ証明機関にアクセスできる場合にのみ実行する必要があります。 これらのアクセス許可が付与されているアカウントでログインできない場合、または証明書にパブリックまたはリモートの証明機関を使用している場合は、Lync Server 展開ウィザードを使用して要求する必要があります。これは、アーティクル.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

