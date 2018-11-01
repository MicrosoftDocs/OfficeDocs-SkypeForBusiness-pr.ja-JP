---
title: 'Lync Server 2013: サーバーへの Kerberos 認証アカウント パスワードの設定'
TOCTitle: サーバーへの Kerberos 認証アカウント パスワードの設定
ms:assetid: 902d3292-678d-4512-9248-586053cb638b
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398734(v=OCS.15)
ms:contentKeyID: 48272826
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのサーバーへの Kerberos 認証アカウント パスワードの設定

 

_**トピックの最終更新日:** 2012-01-16_

この手順を正常に完了させるには、RTCUniversalServerAdmins グループのメンバーであるユーザーとしてログオンする必要があります。

フロントエンド サーバー、Standard Edition サーバー、およびディレクターが存在する各サイトの Kerberos アカウントにパスワードを設定する必要があります。 サイト内の 1 台のサーバー (例、フロント エンド サーバー) で **Set-CsKerberosAccountPassword**  Windows PowerShell コマンドレットを実行することで、パスワードを設定することができます。 それぞれのサイトで **Set-CsKerberosAccountPassword** コマンドレットを実行する必要があります。 コマンドレットは、Web サービス サービスに インターネット インフォメーション サービス (IIS) を構成し、それから Active Directory ドメイン サービス のコンピューター アカウントでパスワードを設定します。 Kerberos アカウント パスワードのソースとして構成された別のサーバーを使用しながら、コマンドレットと使用されるパラメーターに基づいて、別のメソッドが 1 台のサーバーで IIS を構成します。

**Set-CsKerberosAccountPassword** コマンドレットを使用してパスワードを設定する場合、Kerberos はランダムに生成された文字列をパスワードに設定します。このコマンドレットは、このアカウントが割り当てられているすべての Lync Server 2013 中央サイトで、すべての IIS インスタンスに問い合わせます。

## Kerberos 認証アカウントのパスワードを設定するには

1.  Lync Server 管理シェルがインストールされているドメイン コンピューターに、RTCUniversalServerAdmins グループのメンバーとしてログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  コマンド ラインで次の 2 つのコマンドを実行します。
    
        Set-CsKerberosAccountPassword -UserAccount "Domain\UserAccount"
    
    次に例を示します。
    
        Set-CsKerberosAccountPassword -UserAccount "contoso\KerbAuth"
    
    > [!NOTE]
    > UserAccount パラメーターは、ドメイン\ユーザーの形式で指定する必要があります。 Kerberos 認証目的で作成されたコンピューター オブジェクトの参照には、「ユーザー@ドメイン.拡張子」形式はサポートされていません。
    

    > [!IMPORTANT]
    > アカウントの追加または削除のように、Kerberos 認証に何らかの変更を行った後は、Lync Server 管理シェル コマンド プロンプトから <STRONG>Enable-CsTopology</STRONG> を実行する必要があります。


