---
title: 'Lync Server 2013: Kerberos アカウント割り当てのレポート'
TOCTitle: Kerberos アカウント割り当てのレポート
ms:assetid: 523231f6-81b3-454b-996d-663d9bd5cf83
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398343(v=OCS.15)
ms:contentKeyID: 48272085
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での Kerberos アカウント割り当てのレポート

 

_**トピックの最終更新日:** 2012-01-16_

この手順を正常に完了させるには、RTCUniversalServerAdmins グループのメンバーであるユーザーとしてログオンする必要があります。

**Get-CsKerberosAccountAssignment** コマンドレットを使用して、Kerberos 認証アカウントの割り当てに関する情報を照会したり、展開の現在の割り当てに関する情報をレポートしたりできます。

## サイトの Kerberos 認証アカウントの割り当てを照会するには

1.  RTCUniversalServerAdmins グループのメンバーとして、Lync Server 2013 を実行するドメイン内のコンピューターまたは管理ツールがインストールされているコンピューターにログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  コマンド ラインで、次のいずれかのコマンドを実行します。
    
      - 組織の Kerberos 認証アカウントの割り当てをすべて照会し、それぞれの割り当て情報を戻すには、パラメーターを指定せずにコマンドレットを実行します。
        
            Get-CsKerberosAccountAssignment
    
      - 展開の Kerberos 認証アカウントの割り当てをすべて照会し、それぞれのサイト割り当て情報を戻すには、Identity パラメーターを指定してコマンドレットを実行します。
        
            Get-CsKerberosAccountAssignment -Identity "site:SiteName"
        
        次に例を示します。
        
            Get-CsKerberosAccountAssignment -Identity "site:Redmond"
    
      - 1 つのサイトの Kerberos 認証アカウントの割り当てをすべて照会し、それぞれの割り当て情報を戻すには、Filter パラメーターを指定してコマンドレットを実行します。
        
            Get-CsKerberosAccountAssignment -Filter "SiteName"
        
        次に例を示します。
        
            Get-CsKerberosAccountAssignment -Filter "*Redmond"
        
        > [!NOTE]  
        > Filter パラメーターに *SiteName を指定すると、指定したサイト名がサイト ID に含まれるすべてのサイトの情報が戻されます (サイト ID に Redmond という文字列が含まれるすべてのサイトなど)。

