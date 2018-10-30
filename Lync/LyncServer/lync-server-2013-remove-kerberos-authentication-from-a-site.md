---
title: 'Lync Server 2013: サイトからの Kerberos 認証の削除'
TOCTitle: サイトからの Kerberos 認証の削除
ms:assetid: 93171b02-bb36-42dc-943d-86d9dde45b59
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398749(v=OCS.15)
ms:contentKeyID: 48272884
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのサイトからの Kerberos 認証の削除

 

_**トピックの最終更新日:** 2012-01-16_

この手順を正常に完了させるには、RTCUniversalServerAdmins グループのメンバーであるユーザーとしてログオンする必要があります。

サイトから Kerberos 認証を削除する場合やサイトを廃止する場合、 **Remove-CsKerberosAccountAssignment** コマンドレットを使用して Kerberos 認証アカウントの割り当てをサイトから削除する必要があります。次の手順を使用して、Kerberos 認証アカウントの割り当てを削除します。これにより、サイトのすべてのコンピューターから割り当てが削除されます。


> [!WARNING]
> Kerberos が有効になっているアカウントを永続的に廃止する場合、割り当てを削除した後に [Active Directory ユーザーとコンピューター] を使用して Active Directory ドメイン サービス からアカウントを削除する必要があります。オブジェクトを後で使用する場合、Active Directory オブジェクトを保持しておくことができます。



## サイトから Kerberos 認証を削除するには

1.  RTCUniversalServerAdmins グループのメンバーとして、 Lync Server 2013 を実行するドメイン内のコンピューターまたは管理ツールがインストールされているコンピューターにログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  コマンド ラインで次の 2 つのコマンドを実行します。
    
        Remove-CsKerberosAccountAssignment -Identity "site:SiteName"

       &nbsp;
    
        Enable-CsTopology
    
    次に例を示します。
    
        Remove-CsKerberosAccountAssignment -Identity "site:Redmond"

       &nbsp;
    
        Enable-CsTopology
    

    > [!IMPORTANT]
    > アカウントの追加または削除のように、Kerberos 認証に何らかの変更を行った後は、 Lync Server 管理シェル コマンド プロンプトから <STRONG>Enable-CsTopology</STRONG> を実行する必要があります。


