---
title: 'Lync Server 2013: IIS 仮想ディレクトリの認証と証明書を検証または構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verify or configure authentication and certification on IIS virtual directories
ms:assetid: 3ca90be0-1d64-447c-807a-3a2ee3bf625e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429702(v=OCS.15)
ms:contentKeyID: 48183883
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ae692f788d906d01852990490ace01f67eebe63
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848238"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-or-configure-authentication-and-certification-on-iis-virtual-directories-in-lync-server-2013"></a>Lync Server 2013 で IIS 仮想ディレクトリの認証と証明書を検証または構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-05-25_

インターネットインフォメーションサービス (IIS) 仮想ディレクトリで証明書を構成するか、証明書が正しく構成されていることを確認するには、次の手順を使用します。 内部の Lync Server プールで IIS を実行している各サーバーと、オプションのディレクターまたはディレクタープールサーバーで、次の手順を実行します。

<div>


> [!NOTE]  
> 次の手順では、IIS のすべての用途の Lync Server、内部 Web サイト、外部 Web サイトに使用される証明書を組み合わせて要求する手順を定義します。 Lync Server 2010 は、証明書の要求、インポート&nbsp;、および割り当てを管理するための、一連の Lync Server Management Shell Windows PowerShell コマンドレットを導入しました。 この手順では、要求を処理できる内部で展開された証明機関 (CA) があることを前提としています。 Lync Server の目的でパブリック証明書を使う場合、または CA でオフライン要求が必要な場合は、このトピックの「出力パラメーターについての詳細な構文」を参照してください。 <A href="https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate">要求-CsCertificate</A>



</div>

<div>

## <a name="to-configure-authentication-and-certificates-on-iis-virtual-directories"></a>IIS 仮想ディレクトリで認証と証明書を構成するには

1.  次の手順を完了するには、web サービスがインストールされていて、ローカル管理者であるコンピューター (フロントエンドサーバーまたはディレクター) にログオンしている必要があります。 証明機関が組織の証明機関である場合は、証明機関に対する**読み取り**と**登録**のアクセス許可を持っている必要があります。 オフライン証明書の要求を構成して送信する場合は、証明機関に対するアクセス許可は必要ありません。

2.  [**スタート**] をクリックし、[**すべてのプログラム**]、[**管理ツール**]、[**インターネットインフォメーションサービス (IIS) マネージャー**] の順にクリックします。

3.  **インターネットインフォメーションサービス (IIS) マネージャー**で、[ **ServerName**] を選びます。 **機能ビュー**で、[**サーバー証明書**] を選択し、右クリックして [**機能を開く**] を選択します。
    
    <div>
    

    > [!TIP]  
    > [サーバー証明書] 機能ビューで、サーバーに割り当てられている証明書がある場合は、ここに表示されます。 IIS で外部 Web サイトの要件を満たす証明書がある場合は、その証明書を再利用することができます。 証明書を表示するには、証明書を右クリックし、[<STRONG>表示.</STRONG> ..] を選択します。

    
    </div>

4.  証明書を要求するフロントエンドサーバーまたはディレクターで、[**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

5.  Lync Server 管理シェルで、次のように入力します。
    
        Get-CsCertificate
    
    出力は、コンピューターの個人証明書ストアの現在のサーバー上にある証明書の一覧です。 結合された証明書 (つまり、既定の web サービスの内部と web サービスの外部が同じ証明書を使用している場合) では、Use プロパティに Default、WebWebServicesExternal Internal、およびが設定されていることに注意してください。 また、Thumbprint プロパティは、それぞれの使用の種類に対して同じになります。 次の例では、CsCertificate の出力例を示します。
    
    ![現在の証明書の状態での CsCertificate 情報の取得](images/Gg429702.664f6326-6cd5-48e2-8235-fc3950ea43b4(OCS.15).jpg "現在の証明書の状態での CsCertificate 情報の取得")

6.  Lync Server 管理シェルで、次のように入力します。
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA <CA Server FQDN\CA Instance> -Verbose -DomainName "<FQDN entries to be added to the Subject Alternative Name>"
    
    次の例のように、完全なコマンドが表示されます。
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA dc01.contoso.net\contoso-DC01-CA -Verbose -DomainName "LyncdiscoverInternal.Contoso.com,Lyncdiscover.Contoso.com"
    
    <div>
    

    > [!TIP]  
    > 既定では、要求-CsCertificate は、サブジェクト名にサーバーまたはプールの名前を付けて、サブジェクトの代替名にサーバーの FQDN、プールの FQDN、URL の Fqdn、および内部と外部の web サービスの Fqdn を入力します。 これは、展開でトポロジドキュメントを参照することで行われます。 存在しない値があり、– Verbose パラメーターを指定している場合は、別の名前の計算値と実際の値が異なっていることが通知されますが、どの値が失われているかは通知されません。 これにより、コマンドレットで参照される計算値全体が提供されます。 出力で計算された代替名の文字列を使用して、すべての値を含む新しい証明書を再要求します。

    
    </div>
    
    ![要求-CsCertifica を使用した証明書要求の出力](images/Gg429702.9e59a657-fa75-4454-8fd3-57c81e829f7b(OCS.15).jpg "要求-CsCertifica を使用した証明書要求の出力")

7.  Lync Server 管理シェルで、次のように入力します。
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Thumbprint of certificate to use>
    
    次の例のように、完全なコマンドが表示されます。
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint 466D9BB0E8B928B65AF38FA2D9F41E1B301ECE9D
    
    Set-CsCertificate コマンドレットの出力では、(証明書の拇印によって識別される) 同じ証明書が、Default、WebServicesExternal、Webservices の内部使用法として割り当てられていることが示されます。
    
    ![IIS Web ext での Set-CsCertificate からの出力](images/Gg429702.dd451c9d-7b49-4408-8071-c868cb1e678c(OCS.15).jpg "IIS Web ext での Set-CsCertificate からの出力")

</div>

<div>

## <a name="to-verify-or-configure-authentication-and-certificates-on-iis-virtual-directories"></a>IIS 仮想ディレクトリで認証と証明書を確認または構成するには

1.  [**スタート**] をクリックし、[**すべてのプログラム**]、[**管理ツール**]、[**インターネットインフォメーションサービス (IIS) マネージャー**] の順にクリックします。

2.  **インターネットインフォメーションサービス (IIS) マネージャー**で、[ **ServerName**] を展開し、[**サイト**] を展開します。

3.  [ **Lync Server 外部 Web サイト**] を右クリックし、[**バインドの編集**] をクリックします。

4.  Https がポート4443に関連付けられていることを確認し、[ **https**] をクリックします。

5.  [HTTPS] エントリを選び、[**編集**] をクリックして、Lync Server WebServicesExternalCertificate がこのプロトコルにバインドされていることを確認します。 要求された証明書が HTTPS バインドと適切に関連付けられていることを確認するために、Set-CsCertificate コマンドレットの拇印を比較します。

</div>

<div>

## <a name="see-also"></a>関連項目


[Get-CsCertificate](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
[設定-CsCertificate](https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

