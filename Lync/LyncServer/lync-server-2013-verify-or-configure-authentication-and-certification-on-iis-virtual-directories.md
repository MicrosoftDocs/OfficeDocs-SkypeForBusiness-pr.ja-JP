---
title: 'Lync Server 2013: IIS 仮想ディレクトリの認証と証明書を検証または構成する'
TOCTitle: IIS 仮想ディレクトリの認証と証明書を検証または構成する
ms:assetid: 3ca90be0-1d64-447c-807a-3a2ee3bf625e
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg429702(v=OCS.15)
ms:contentKeyID: 48271829
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 で IIS 仮想ディレクトリの認証と証明書を検証または構成する

 

_**トピックの最終更新日:** 2012-05-25_

以下の手順に従って、 インターネット インフォメーション サービス (IIS) 仮想ディレクトリの証明書を構成し、証明書が適切に構成されていることを確認します。以下の手順は、内部の Lync Server プールで IIS を実行している各サーバーか、オプションの ディレクターまたは ディレクター プール サーバーで実行します。

> [!NOTE]
> 以下の手順によって、IIS 内のあらゆる Lync Server、内部 Web サイト、および外部 Web サイトで使用される、共同証明書を要求する手順が定義されます。 Lync Server 2010 では、証明書の要求、インポート、および割り当てを管理する目的で、一連の Lync Server 管理シェルWindows PowerShell コマンドレットが導入されました。手順は、要求を処理できる、内部展開された証明機関 (CA) が存在することを前提としています。 Lync Server 目的でパブリック証明書を使用する場合、または CA がオフライン要求を処理する場合は、 ?Output パラメーターについて、次のトピックの詳細な構文を参照してください。「 <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Request-CsCertificate">Request-CsCertificate</a>」


## IIS 仮想ディレクトリの認証と証明書を構成するには

1.  以下の手順を実行するには、Web サービスがインストールされているコンピューター ( フロント エンド サーバーまたは ディレクター) にログオンする必要があり、ローカル管理者である必要があります。証明書の要求先の証明機関が組織の証明機関の場合は、その証明機関に対して **読み取り** と **登録** のアクセス許可が必要です。オフライン証明書要求を構成および送信する場合は、証明機関に対するアクセス許可は必要ありません。

2.  \[ **スタート** \] ボタンをクリックし、\[ **すべてのプログラム** \] を選択します。次に、\[ **管理ツール** \] を選択し、\[ **インターネット インフォメーション サービス (IIS) マネージャー** \] をクリックします。

3.  \[ **インターネット インフォメーション サービス (IIS) マネージャー** \] で、\[ **\<サーバー名\>** \] を選択します。\[ **機能ビュー** \] で、\[ **サーバー証明書** \] を選択し、\[ **機能を開く** \] を右クリックして選択します。
    

    > [!TIP]
    > サーバーに割り当てられている証明書がある場合は、サーバー証明書の機能ビューにそれが表示されます。IIS 内の外部 Web サイトの要件に一致する証明書がある場合は、その証明書を再利用できます。証明書を表示するには、証明書を右クリックし、[ <STRONG>表示</STRONG> ] を選択します。



4.  証明書の要求先の フロント エンド サーバーまたは ディレクターで、\[ **スタート** \] ボタンをクリックし、\[ **すべてのプログラム** \] を選択します。次に、\[ **Microsoft Lync Server 2013**\] を選択し、\[ **Lync Server 管理シェル**\] をクリックします。

5.  Lync Server 管理シェル で、次のコマンドを入力します。
    
        Get-CsCertificate
    
    出力は、コンピューターの個人証明書ストア内のサーバーに現在ある、証明書の一覧です。共同証明書 (つまり、既定、内部 Web サービス、および外部 Web サービスが同じ証明書を使用している) では、Use プロパティに Default、WebServicesInternal、および WebServicesExternal が設定されることに注意してください。また、Thumbprint プロパティも、各 Use タイプで同じになります。Get-CsCertificate の出力例を、次の例に示します。
    
    ![現在の scert の状態についての Get-CsCertificate 情報](images/Gg429702.664f6326-6cd5-48e2-8235-fc3950ea43b4(OCS.15).jpg "現在の scert の状態についての Get-CsCertificate 情報")

6.  Lync Server 管理シェル で、次のコマンドを入力します。
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA <CA Server FQDN\CA Instance> -Verbose -DomainName "<FQDN entries to be added to the Subject Alternative Name>"
    
    コマンド全体は次の例のようになります。
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA dc01.contoso.net\contoso-DC01-CA -Verbose -DomainName "LyncdiscoverInternal.Contoso.com,Lyncdiscover.Contoso.com"
    

    > [!TIP]
    > 既定では、Request-CsCertificate によって、サブジェクト名にはサーバー名またはプール名が設定され、サブジェクトの別名内のエントリにはサーバーの FQDN、プールの FQDN、簡易 URL の FQDN、および内部 Web サービスと外部 Web サービスの FQDN が設定されます。これは、展開のトポロジ ドキュメントを参照することによって行われます。不足している値があり、-Verbose パラメーターが指定されている場合、別名の計算値と実際値が異なるというメッセージが表示されますが、どの値が不足しているかを示すメッセージは表示されません。コマンドレットが参照する計算値全体が提供されます。出力内の計算された別名文字列を使用して、すべての値を含む新しい証明書を再度要求します。

    
    ![Request-CsCertifica を使った cert 要求からの出力](images/Gg429702.9e59a657-fa75-4454-8fd3-57c81e829f7b(OCS.15).jpg "Request-CsCertifica を使った cert 要求からの出力")

7.  Lync Server 管理シェル で、次のコマンドを入力します。
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Thumbprint of certificate to use>
    
    コマンド全体は次の例のようになります。
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint 466D9BB0E8B928B65AF38FA2D9F41E1B301ECE9D
    
    Set-CsCertificate コマンドレットからの出力には、Default、WebServicesExternal、および WebServicesInternal の使用に対して同じ証明書 (証明書の拇印で識別) が割り当てられることが示されます。
    
    ![IIS WebExt についての Set-CsCertificate からの出力](images/Gg429702.dd451c9d-7b49-4408-8071-c868cb1e678c(OCS.15).jpg "IIS WebExt についての Set-CsCertificate からの出力")

## IIS 仮想ディレクトリの認証と証明書を検証または構成するには

1.  \[ **スタート** \] ボタンをクリックし、\[ **すべてのプログラム** \] を選択します。次に、\[ **管理ツール** \] を選択し、\[ **インターネット インフォメーション サービス (IIS) マネージャー** \] をクリックします。

2.  **インターネット インフォメーション サービス (IIS) マネージャー** で、 **サーバー名** を展開し、\[ **サイト** \] を展開します。

3.  \[ **Lync Server の外部 Web サイト** \] を右クリックし、\[ **バインドの編集** \] をクリックします。

4.  https がポート 4443 と関連付けられていることを確認し、\[ **https** \] をクリックします。

5.  HTTPS エントリを選択し、\[ **編集** \] をクリックして、 Lync Server WebServicesExternalCertificate がこのプロトコルにバインドされていることを確認します。Set-CsCertificate コマンドレットからの拇印を比較して、予期される証明書が HTTPS バインドに適切に関連付けられていることを確認します。

## 関連項目

#### その他のリソース

[Get-CsCertificate](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsCertificate)  
[Set-CsCertificate](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCertificate)

