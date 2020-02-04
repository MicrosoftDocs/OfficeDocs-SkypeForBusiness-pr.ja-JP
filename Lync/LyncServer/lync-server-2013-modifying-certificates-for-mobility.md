---
title: 'Lync Server 2013: モビリティに合わせた証明書の変更'
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
ms.openlocfilehash: 150dc8c7b4021e1e2c7ccab6ccc71823c01c388e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756871"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modifying-certificates-for-mobility-in-lync-server-2013"></a>Lync Server 2013 でのモビリティに合わせた証明書の変更

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-06-20_

Lync 環境とモバイルクライアント間のセキュリティで保護された接続をサポートするために、ディレクタープール、フロントエンドプール、リバースプロキシ用の Secure Socket Layer (SSL) 証明書を、追加のサブジェクト代替名で更新する必要があります (SAN) エントリ。 モビリティの証明書の要件の詳細について確認する必要がある場合は、「 [Lync Server 2013 でのモビリティの技術要件](lync-server-2013-technical-requirements-for-mobility.md)」の「証明書の要件」セクションを参照してください。基本的に、追加の SAN エントリが含まれる証明機関から新しい証明書を取得し、この記事の手順を使ってそれらの証明書を追加する必要が

もちろん、作業を開始する前に、証明書に既に登録されているサブジェクトの代替名を知っておくことをお勧めします。 まだ設定されているものがわからない場合は、さまざまな方法で確認できます。このオプションでは、ユーザーがこの情報を表示するために、[ **Get-CsCertificate** ] とその他の PowerShell コマンドを実行することができます。これは、既定ではデータが切り捨てられるため、必要なすべてのプロパティを表示することができない場合があります。 証明書とそのすべてのプロパティについて詳しく理解するには、Microsoft 管理コンソール (MMC) に移動して、証明書スナップインを読み込むか (以下を参照)、Lync Server 展開ウィザードを確認してください。

上で説明したように、次の手順では、Lync Server 管理シェルと MMC を使用して証明書を更新する方法について説明します。 代わりに Lync Server Deployment ウィザードで証明書ウィザードを使用する場合は、ディレクターまたはディレクタープールを構成している場合は、 [Lync server 2013 でディレクターの証明書を構成](lync-server-2013-configure-certificates-for-the-director.md)することができます (存在しない可能性があります)。 フロントエンドサーバーまたはフロントエンドプールについては、「 [Lync Server 2013 でサーバーの証明書を構成](lync-server-2013-configure-certificates-for-servers.md)する」を参照してください。

最後に、Lync Server 2013 環境に1つの既定の証明書がある場合、または既定の証明書 (web サービス以外はすべて) が存在する場合があることを覚えておいてください。 どのような構成にしても、これらの手順は役立ちます。

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a>Lync Server 管理シェルを使用して新しいサブジェクト別の名前を使用して証明書を更新するには

1.  ローカルの管理者権限と権限を持つアカウントを使用して、Lync Server 2013 サーバーにログオンする必要があります。 さらに、手順12以降で PowerShell**要求-CsCertificate**を実行している場合、アカウントは指定された証明機関 (CA) に対する権利を持っている必要があります。

2.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

3.  更新された証明書を割り当てる前に、サーバーに割り当てられている証明書と使用の種類を確認する必要があります。 コマンド ラインで次を入力します。
    
        Get-CsCertificate

4.  前の手順からの出力を確認して、複数の使用に対して1つの証明書が割り当てられているかどうか、または使用ごとに異なる証明書が割り当てられているかどうかを確認します。 証明書がどのように使われているかを確認するには、Use パラメーターを参照してください。 表示された証明書の Thumbprint パラメーターと比較して、同じ証明書に複数の使用が含まれているかどうかを確認します。 拇印のパラメーターを常に把握しておきます。

5.  証明書を更新します。 コマンド ラインで次を入力します。
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    たとえば、 **CsCertificate**コマンドレットで、既定値を使用する証明書が表示され、もう1つは Webservices internal を使用していて、もう1つは WebServicesExternal を使用していて、それらのすべてに同じ拇印値が含まれている場合、コマンドラインで次のように入力します。
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    **重要:**
    
    各使用に個別の証明書が割り当てられている場合 (上記でチェックした拇印の値が各証明書に対して異なる場合) は、上の例のように、複数の種類の**Set-cscertificate**コマンドレットを実行し**ない**ことが重要です。 この場合は、使用するたびに、 **Set-CsCertificate**コマンドレットを個別に実行します。 次に例を示します。
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  証明書 (または証明書) を表示するには、[**スタート**] をクリックし、[**実行**] をクリックします。 「MMC」と入力して Microsoft 管理コンソールを開きます。

7.  MMC のメニューで、[**ファイル**]、[**スナップインの追加と削除**] の順番に選択し、[証明書] を選択します。 [**追加**] をクリックします。 メッセージが表示されたら、[**コンピューターアカウント**] を選択し、[**次へ**] をクリックします。

8.  証明書が配置されているサーバーの場合は、[**ローカルコンピューター**] を選択します。 証明書が別のコンピューターにある場合は、**別のコンピューター**を選んでから、コンピューターの完全修飾ドメイン名を入力するか、[**参照**] をクリックして**選択するオブジェクト名**を入力し、コンピューターの名前を入力します。 [**名前の確認**] をクリックします。 コンピューターの名前が解決されると、下線が引かれます。 [ **OK**] をクリックし、[**完了**] をクリックします。 [ **OK** ] をクリックして選択内容を確定し、[スナップインの**追加と削除**] ダイアログボックスを閉じます。

9.  証明書のプロパティを表示するには、[**証明書**]、[**個人用**] の順に展開し、[**証明書**] を選択します。 表示する証明書を選択し、証明書を右クリックして、[**開く**] を選択します。

10. **証明書**ビューで、[**詳細**] を選択します。 ここでは、[**件名**] を選択して証明書のサブジェクト名を選択し、割り当てられたサブジェクト名と関連付けられたプロパティが表示されます。

11. 割り当てられたサブジェクト別の名前を表示するには、[**件名の代替名**] を選択します。 すべての割り当てられた件名の代替名がここに表示されます。 ここで見つかった件名の代替名は、既定で**DNS 名**の種類になっています。 次のメンバーが表示されている必要があります (すべてのメンバーが DNS host (A または IPv6 AAAA の場合は、完全修飾ドメイン名になります)。
    
      - このプールのプール名、または1つのサーバー名 (プールではない場合)
    
      - 証明書が割り当てられているサーバー名
    
      - 単純な URL レコード、通常は会議とダイヤルイン
    
      - Web サービスの内部および Web サービス外部名 (webpool01.contoso.net、webpool01.contoso.com など) は、トポロジビルダーでの選択肢と、[web サービスの変更] オプションに基づいています。
    
      - 既に割り当てられている場合は、lyncdiscover です。\<sipdomain\>と lyncdiscoverinternal。\<sipdomain\>レコード。
    
    最後の項目は、lyncdiscover と lyncdiscoverinternal の SAN エントリがある場合に最も興味を持っている項目です。
    
    複数の証明書を確認する場合は、この手順を繰り返します。 この情報を取得したら、証明書ビューと MMC を閉じることができます。

12. 自動検出サービスのサブジェクトの別名が表示されておらず、既定の Webservices 内部と WebServiceExternal 外部タイプに対して単一の既定の証明書を使用している場合は、次の操作を行います。
    
      - Lync Server 管理シェルのコマンドラインプロンプトで、次のように入力します。
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        SIP ドメインが複数ある場合は、新しい AllSipDomain パラメーターを使うことはできません。 代わりに、DomainName パラメーターを使用する必要があります。 DomainName パラメーターを使用する場合は、lyncdiscoverinternal レコードと lyncdiscover レコードの FQDN を定義する必要があります。 次に例を示します。
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - 証明書を割り当てるには、次のように入力します。
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        "拇印" は、新しく発行された証明書に対して表示される拇印です。

13. 既定の証明書を使用する場合、内部の自動検出 SAN が見つからない場合は、次の手順を実行します。 WebServicesExternal
    
      - Lync Server 管理シェルのコマンドラインプロンプトで、次のように入力します。
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        SIP ドメインが複数ある場合は、新しい AllSipDomain パラメーターを使うことはできません。 代わりに、DomainName パラメーターを使用する必要があります。 DomainName パラメーターを使用する場合は、SIP ドメイン FQDN に適切なプレフィックスを使用する必要があります。 次に例を示します。
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - 外部の自動検出サブジェクトの代替名が見つからない場合は、コマンドラインで次のように入力します。
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        SIP ドメインが複数ある場合は、新しい AllSipDomain パラメーターを使うことはできません。 代わりに、DomainName パラメーターを使用する必要があります。 DomainName パラメーターを使用する場合は、SIP ドメイン FQDN に適切なプレフィックスを使用する必要があります。 次に例を示します。
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - 個々の証明書の種類を割り当てるには、次のように入力します。
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        "拇印" は、新しく発行された個々の証明書に対して表示される拇印です。
    
    <div>
    

    > [!NOTE]  
    > 手順12と13は、実行しているアカウントが適切な権限で証明機関にアクセスしている場合にのみ実行されることに注意してください。 これらのアクセス許可が付与されているアカウントでログインできない場合、または証明書にパブリックまたはリモートの証明機関を使用している場合は、「Lync Server 展開ウィザード」で操作する必要があります。これは、「.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

