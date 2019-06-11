---
title: 'Lync Server 2013: 自動検出用の証明書を構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring certificates for Autodiscover
ms:assetid: 1842191d-df9a-41e0-9286-08c25f9b5dca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945617(v=OCS.15)
ms:contentKeyID: 51541453
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d0270aa76adb7cef2a6da8f6a4f9cb6db090e78
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840287"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-certificates-for-autodiscover-in-lync-server-2013"></a>Lync Server 2013 で自動検出用の証明書を構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-12-12_

ディレクタープール、フロントエンドプール、およびリバースプロキシ用の証明書には、Lync クライアントとのセキュリティで保護された接続をサポートするために、追加のサブジェクト代替名エントリが必要です。

<div>


> [!NOTE]  
> このコマンドレットを<STRONG></STRONG>使用して、現在割り当てられている証明書に関する情報を表示できます。 ただし、既定のビューでは、証明書のプロパティは切り捨てられ、Subject代替のベンダーのプロパティにはすべての値が表示されません。 取得した情報を表示したり、証明書を要求および割り当てたりするには、 <STRONG>cscertificate</STRONG> 、<STRONG>要求-</STRONG>Cscertificate、および<STRONG>Set-cscertificate</STRONG>コマンドレットを使用します。 ただし、現在の証明書のサブジェクト代替名 (SAN) のプロパティがわからない場合は、最適な方法ではありません。 証明書とすべてのプロパティメンバーを表示するには、 <EM>Microsoft 管理コンソール (MMC)</EM>の証明書スナップインを使うか、Lync Server 展開ウィザードを使用することをお勧めします。 Lync Server 展開ウィザードでは、証明書ウィザードを使って証明書のプロパティを表示できます。 Lync Server 管理シェルと<EM>Microsoft 管理コンソール (MMC)</EM>を使って、証明書の表示、要求、割り当てを行う手順については、次の手順で詳しく説明します。 Lync Server 展開ウィザードを使用するには、「 <A href="lync-server-2013-configure-certificates-for-the-director.md">Lync server 2013 でディレクターの証明書を構成</A>する」を参照してください。 フロントエンドサーバーまたはフロントエンドプールについては、以下の詳細を参照してください。 <A href="lync-server-2013-configure-certificates-for-servers.md">Lync Server 2013 でサーバーの証明書を構成する</A><BR>この手順の最初の手順では、現在の証明書で再生される役割について説明します。 既定では、証明書に lyncdiscover は表示されません。&lt;sipdomain&gt;または lyncdiscoverinternal。&lt;以前にモビリティ&gt;サービスをインストールしているか、事前に証明書を準備している場合を除き、内部ドメイン名エントリ。 この手順では、SIP ドメイン名 ' contoso.com ' の例と内部ドメイン名 ' contoso.net ' の例を使用します。<BR>Lync Server 2013 および Lync Server 2010 の既定の証明書の構成では、1つの証明書 (web サービスを除くすべての目的で) を目的の既定の証明書として使うことができます。 オプションの構成では、目的ごとに個別の証明書を使用する必要があります。 証明書を管理するには、Lync Server 管理シェルと Windows PowerShell コマンドレットを使用するか、または Lync Server 展開ウィザードで証明書ウィザードを使用します。



</div>

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a>Lync Server 管理シェルを使用して新しいサブジェクト別の名前を使用して証明書を更新するには

1.  ローカルの管理者権限と権限を持つアカウントを使用してコンピューターにログオンします。

2.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

3.  サーバーに割り当てられている証明書と用途の種類を確認します。 更新された証明書を割り当てるには、次の手順でこれらの情報が必要です。 コマンド ラインで次を入力します。
    
        Get-CsCertificate

4.  前の手順の出力を確認して、複数の使用に対して1つの証明書が割り当てられているかどうか、または使用ごとに異なる証明書が割り当てられているかどうかを確認します。 証明書の使用方法については、Use パラメーターを参照してください。 表示された証明書の Thumbprint パラメーターと比較して、同じ証明書に複数の使用が含まれているかどうかを確認します。

5.  証明書を更新します。 コマンド ラインで次を入力します。
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    たとえば、 **CsCertificate**コマンドレットで、既定値を使用する証明書が表示され、もう1つは Webservices internal を使用していて、もう1つは WebServicesExternal を使用している場合、コマンドラインで次のように入力します。
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    **重要:**
    
    各使用に個別の証明書が割り当てられている場合 (拇印の値は各証明書によって異なります)、複数の種類の**Set-cscertificate**コマンドレットを実行しないことが重要です。 この場合は、使用するたびに、 **Set-CsCertificate**コマンドレットを個別に実行します。 次に例を示します。
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  証明書を表示するには、[**スタート**] をクリックし、[**実行**] をクリックします。 「MMC」と入力して Microsoft 管理コンソールを開きます。

7.  MMC のメニューで、[**ファイル**]、[**スナップインの追加と削除**] の順番に選択し、[証明書] を選択します。 [**追加**] をクリックします。 メッセージが表示されたら、[**コンピューターアカウント**] を選択し、[**次へ**] をクリックします。

8.  証明書がこのコンピューター上にある場合は、[**ローカルコンピューター**] を選択します。 証明書が別のコンピューターにある場合は、[**別のコンピューター**] を選択し、コンピューターの完全修飾ドメイン名を入力するか、[**参照**] をクリックして [**選択するオブジェクト名を入力**してください] にコンピューターの名前を入力します。 [**名前の確認**] をクリックします。 コンピューターの名前が解決されると、下線が引かれます。 [ **OK**] をクリックし、[**完了**] をクリックします。 [ **OK** ] をクリックして選択内容を確定し、[スナップインの**追加と削除**] ダイアログボックスを閉じます。
    
    <div>
    

    > [!IMPORTANT]  
    > 証明書が本体に表示されない場合は、ユーザーまたはサービスが選択されていないことを確認します。 [コンピューター] を選ぶ必要があります。または、probper 証明書を見つけることができません。

    
    </div>

9.  証明書のプロパティを表示するには、[**証明書**]、[**個人用**] の順に展開し、[**証明書**] を選択します。 表示する証明書を選択し、証明書を右クリックして、[**開く**] を選択します。

10. **証明書**ビューで、[**詳細**] を選択します。 ここでは、[**件名**] を選択して証明書のサブジェクト名を選択し、割り当てられたサブジェクト名と関連付けられたプロパティが表示されます。

11. 割り当てられたサブジェクト別の名前を表示するには、[**件名の代替名**] を選択します。 すべての割り当てられた件名の代替名が表示されます。 プロパティに含まれるサブジェクトの別名は、既定では**DNS 名**の型です。 次のメンバーが表示されている必要があります (すべてのメンバーが DNS host (A または IPv6 AAAA の場合は、完全修飾ドメイン名になります)。
    
      - このプールのプール名、または1つのサーバー名 (プールではない場合)
    
      - 証明書が割り当てられているサーバー名
    
      - 単純な URL レコード、通常は会議とダイヤルイン
    
      - Web サービスの内部および Web サービス外部名 (webpool01.contoso.net、webpool01.contoso.com など) は、トポロジビルダーでの選択肢と、[web サービスの変更] オプションに基づいています。
    
      - 既に割り当てられている場合は、lyncdiscover です。\<sipdomain\>と lyncdiscoverinternal。\<sipdomain\>レコード。
    
    最も関心の高い項目は、lyncdiscover と lyncdiscoverinternal の SAN エントリがある場合です。
    
    この情報を取得したら、証明書ビューと MMC を閉じることができます。

12. 自動検出サービスの場合は、lyncdiscover を意味します。\>ドメイン名\>と lyncdiscoverinternal。\<ドメイン名\> (外部証明書または内部証明書の場合) サブジェクトの代替名が表示されず、既定の web サービスの内部および webserviceexternal 外部タイプに対して単一の既定の証明書を使用している場合は、次の操作を行います。
    
      - Lync Server 管理シェルのコマンドラインプロンプトで、次のように入力します。
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        SIP ドメインが複数ある場合は、新しい AllSipDomain パラメーターを使うことはできません。 代わりに、DomainName パラメーターを使用する必要があります。 DomainName パラメーターを使用する場合は、lyncdiscoverinternal レコードと lyncdiscover レコードの FQDN を定義する必要があります。 次に例を示します。
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - 証明書を割り当てるには、次のように入力します。
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        "拇印" は、新しく発行された証明書に対して表示される拇印です。

13. 既定の証明書を使用するときに、内部の自動検出サブジェクトの代替名が見つからない場合は、次の操作を行います。
    
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

</div>

</div>

<span> </span>

</div>

</div>

</div>

