---
title: 'Lync Server 2013: サイトへの Kerberos 認証アカウントの割り当て'
TOCTitle: サイトへの Kerberos 認証アカウントの割り当て
ms:assetid: 3d9c587c-c8b8-4f81-8ed9-1458a31fc292
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg425901(v=OCS.15)
ms:contentKeyID: 48271845
ms.date: 04/18/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での、サイトへの Kerberos 認証アカウントの割り当て

 

_**トピックの最終更新日:** 2017-04-18_

この手順を正常に完了させるには、RTCUniversalServerAdmins グループのメンバーであるユーザーとしてログオンする必要があります。

Kerberos アカウントを作成した後、これをサイトに割り当てる必要があります。これは Lync Server 2013 サイトであり、Active Directory サイトではありません。1 つの展開に複数の Kerberos 認証アカウントを作成できますが、サイトに割り当てられるアカウントは 1 つだけです。以前に作成した Kerberos 認証アカウントをサイトに割り当てるには、次の手順を使用します。Kerberos アカウントの作成の詳細については、「[Lync Server 2013 での Kerberos 認証アカウントの作成](lync-server-2013-create-a-kerberos-authentication-account.md)」を参照してください。

## Kerberos 認証アカウントをサイトに割り当てるには

1.  RTCUniversalServerAdmins グループのメンバーとして、Lync Server 2013 を実行するドメイン内のコンピューターまたは管理ツールがインストールされているコンピューターにログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  コマンド ラインで次の 2 つのコマンドを実行します。
    
        New-CsKerberosAccountAssignment -UserAccount "Domain\UserAccount" -Identity "site:SiteName"

       &nbsp;
    
        Enable-CsTopology
    
    次に例を示します。
    
        New-CsKerberosAccountAssignment -UserAccount "contoso\kerbauth" -Identity "site:redmond"

      &nbsp;
    
        Enable-CsTopology
    
    > [!NOTE]
    > UserAccount パラメーターは、ドメイン\ユーザーの形式で指定する必要があります。 ユーザー@ドメイン.拡張子の形式は、Kerberos 認証用に作成されたコンピューター オブジェクトの参照ではサポートされていません。
    

    > [!IMPORTANT]
    > アカウントの追加または削除のように、Kerberos 認証に何らかの変更を行った後は、Lync Server 管理シェル コマンド プロンプトから <STRONG>Enable-CsTopology</STRONG> を実行する必要があります。


