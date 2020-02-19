---
title: 'Lync Server 2013: IIS 仮想ディレクトリの認証と証明書を検証または構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify or configure authentication and certification on IIS virtual directories
ms:assetid: 3ca90be0-1d64-447c-807a-3a2ee3bf625e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429702(v=OCS.15)
ms:contentKeyID: 48183883
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28011a5eb436096d0d8486a6f05ac9024ac388d8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136975"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-or-configure-authentication-and-certification-on-iis-virtual-directories-in-lync-server-2013"></a>Lync Server 2013 で IIS 仮想ディレクトリの認証と証明書を検証または構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-05-25_

次の手順を使用して、インターネットインフォメーションサービス (IIS) 仮想ディレクトリの証明書を構成するか、証明書が正しく構成されていることを確認します。 内部の Lync Server プールとオプションのディレクターまたはディレクタープールサーバーで、IIS を実行している各サーバーで以下の手順を実行します。

<div>


> [!NOTE]  
> 次の手順では、IIS のすべての目的の Lync Server、内部 Web サイト、および外部 Web サイトに使用される証明書の組み合わせを要求する手順を定義します。 Lync Server 2010 証明書の要求、インポート、および&nbsp;割り当てを管理するための、一連の Lync Server 管理シェル Windows PowerShell コマンドレットが導入されました。 手順は、要求を処理できる、内部展開された証明機関 (CA) が存在することを前提としています。 Lync Server の目的でパブリック証明書を使用する場合、または CA がオフライン要求を必要とする場合は、このトピックの詳細な構文を参照して、-Output パラメーターに関する情報を参照してください。 <A href="https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate">要求-CsCertificate</A>



</div>

<div>

## <a name="to-configure-authentication-and-certificates-on-iis-virtual-directories"></a>IIS 仮想ディレクトリの認証と証明書を構成するには

1.  次の手順を正常に完了するには、web サービスがインストールされていて、ローカル管理者であるコンピューター (フロントエンドサーバーまたはディレクター) にログオンしている必要があります。 証明書の要求先の証明機関が組織の証明機関の場合は、その証明機関に対して**読み取り**と**登録**のアクセス許可が必要です。 オフライン証明書要求を構成および送信する場合は、証明機関に対するアクセス許可は必要ありません。

2.  [**スタート**] ボタンをクリックし、[**すべてのプログラム**] を選択します。次に、[**管理ツール**] を選択し、[**インターネット インフォメーション サービス (IIS) マネージャー**] をクリックします。

3.  [**インターネット インフォメーション サービス (IIS) マネージャー**] で、[**<サーバー名>**] を選択します。[**機能ビュー**] で、[**サーバー証明書**] を選択し、[**機能を開く**] を右クリックして選択します。
    
    <div>
    

    > [!TIP]  
    > サーバーに割り当てられている証明書がある場合は、サーバー証明書の機能ビューにそれが表示されます。IIS 内の外部 Web サイトの要件に一致する証明書がある場合は、その証明書を再利用できます。証明書を表示するには、証明書を右クリックし、[<STRONG>表示</STRONG>] を選択します。

    
    </div>

4.  証明書を要求しているフロントエンドサーバーまたはディレクターで、[**スタート**] をクリックし、[**すべてのプログラム**] を選択し、[ **Microsoft lync server 2013**] を選択して、[ **lync server 管理シェル**] をクリックします。

5.  Lync Server 管理シェルで、次のように入力します。
    
        Get-CsCertificate
    
    出力は、コンピューターの個人証明書ストア内のサーバーに現在ある、証明書の一覧です。共同証明書 (つまり、既定、内部 Web サービス、および外部 Web サービスが同じ証明書を使用している) では、Use プロパティに Default、WebServicesInternal、および WebServicesExternal が設定されることに注意してください。また、Thumbprint プロパティも、各 Use タイプで同じになります。Get-CsCertificate の出力例を、次の例に示します。
    
    ![現在の scert の状態での [CsCertificate info] を取得する](images/Gg429702.664f6326-6cd5-48e2-8235-fc3950ea43b4(OCS.15).jpg "現在の scert の状態での [CsCertificate info] を取得する")

6.  Lync Server 管理シェルで、次のように入力します。
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA <CA Server FQDN\CA Instance> -Verbose -DomainName "<FQDN entries to be added to the Subject Alternative Name>"
    
    コマンド全体は次の例のようになります。
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA dc01.contoso.net\contoso-DC01-CA -Verbose -DomainName "LyncdiscoverInternal.Contoso.com,Lyncdiscover.Contoso.com"
    
    <div>
    

    > [!TIP]  
    > 既定では、Request-CsCertificate によって、サブジェクト名にはサーバー名またはプール名が設定され、サブジェクトの別名内のエントリにはサーバーの FQDN、プールの FQDN、簡易 URL の FQDN、および内部 Web サービスと外部 Web サービスの FQDN が設定されます。これは、展開のトポロジ ドキュメントを参照することによって行われます。不足している値があり、–Verbose パラメーターが指定されている場合、別名の計算値と実際値が異なるというメッセージが表示されますが、どの値が不足しているかを示すメッセージは表示されません。コマンドレットが参照する計算値全体が提供されます。出力内の計算された別名文字列を使用して、すべての値を含む新しい証明書を再度要求します。

    
    </div>
    
    ![要求を使用した証明書要求の出力 CsCertifica](images/Gg429702.9e59a657-fa75-4454-8fd3-57c81e829f7b(OCS.15).jpg "要求を使用した証明書要求の出力 CsCertifica")

7.  Lync Server 管理シェルで、次のように入力します。
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Thumbprint of certificate to use>
    
    コマンド全体は次の例のようになります。
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint 466D9BB0E8B928B65AF38FA2D9F41E1B301ECE9D
    
    Set-CsCertificate コマンドレットからの出力には、Default、WebServicesExternal、および WebServicesInternal の使用に対して同じ証明書 (証明書の拇印で識別) が割り当てられることが示されます。
    
    ![IIS WebExt での Set-CsCertificate からの出力](images/Gg429702.dd451c9d-7b49-4408-8071-c868cb1e678c(OCS.15).jpg "IIS WebExt での Set-CsCertificate からの出力")

</div>

<div>

## <a name="to-verify-or-configure-authentication-and-certificates-on-iis-virtual-directories"></a>IIS 仮想ディレクトリの認証と証明書を検証または構成するには

1.  [**スタート**] ボタンをクリックし、[**すべてのプログラム**] を選択します。次に、[**管理ツール**] を選択し、[**インターネット インフォメーション サービス (IIS) マネージャー**] をクリックします。

2.  **インターネットインフォメーションサービス (IIS) マネージャー**で、 **ServerName**を展開し、[**サイト**] を展開します。

3.  [**Lync Server の外部 Web サイト**] を右クリックし、[**バインドの編集**] をクリックします。

4.  https がポート 4443 と関連付けられていることを確認し、[**https**] をクリックします。

5.  HTTPS エントリを選択し、[**編集**] をクリックして、Lync Server WebServicesExternalCertificate がこのプロトコルにバインドされていることを確認します。 Set-CsCertificate コマンドレットからの拇印を比較して、予期される証明書が HTTPS バインドに適切に関連付けられていることを確認します。

</div>

<div>

## <a name="see-also"></a>関連項目


[-CsCertificate の取得](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
[設定-CsCertificate](https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

