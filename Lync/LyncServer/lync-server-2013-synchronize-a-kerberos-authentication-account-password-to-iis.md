---
title: 'Lync Server 2013: Kerberos 認証アカウント パスワードと IIS との同期'
TOCTitle: Kerberos 認証アカウント パスワードと IIS との同期
ms:assetid: 05925a66-2684-4c1b-adfa-69bd0da1bf38
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398107(v=OCS.15)
ms:contentKeyID: 48271140
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での Kerberos 認証アカウント パスワードと IIS との同期

 

_**トピックの最終更新日:** 2010-11-08_

この手順を正常に完了させるには、RTCUniversalServerAdmins グループのメンバーであるユーザーとしてログオンする必要があります。

サイトにおいて、フロントエンド サーバー、Standard Edition サーバー、およびディレクターは、Web サービス サービスへの要求を認証するのに、Kerberos 認証アカウントを使用することができます。 この手順では、Kerberos アカウントが割り当てられているサイト内で Web サービスを実行している各サーバーを探索し、Kerberos アカウントを使用する インターネット インフォメーション サービス (IIS) 構成設定を更新します。詳細については、「[Lync Server 2013 でのサーバーへの Kerberos 認証アカウント パスワードの設定](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md)」を参照してください。

## Kerberos 認証アカウントのパスワードを設定および構成するには

1.  ソース コンピューター (fe01.contoso.com など) に RTCUniversalServerAdmins グループのメンバーとしてログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  Lync Server 管理シェル コマンド ラインから、次の 2 つのコマンドを実行します。
    
        Set-CsKerberosAccountPassword -FromComputer SourceComputer -ToComputer DestinationComputer
    
    次に例を示します。
    
        Set-CsKerberosAccountPassword -FromComputer fe01.contoso.com -ToComputer dir01.contoso.com
    

    > [!IMPORTANT]
    > ソース コンピューターと宛先のコンピューターの名前は、サーバーの完全修飾ドメイン名 (FQDN) である必要があります。 プール名がソース コンピューターまたは宛先のコンピューターとして使用しているコンピューターの名前と同じでない限り、プール FQDN を使用することはできません。

    

    > [!IMPORTANT]
    > アカウントの追加または削除のように、Kerberos 認証に何らかの変更を行った後は、Lync Server 管理シェル コマンド プロンプトから <STRONG>Enable-CsTopology</STRONG> を実行する必要があります。


