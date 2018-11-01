---
title: 'Lync Server 2013: Kerberos 認証のテストおよびレポート機能の準備'
TOCTitle: Kerberos 認証のテストおよびレポート機能の準備
ms:assetid: d52c39e5-747d-4f29-88aa-30fd6f26b99c
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398925(v=OCS.15)
ms:contentKeyID: 48273693
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 における Kerberos 認証のテストおよびレポート機能の準備

 

_**トピックの最終更新日:** 2012-01-16_

この手順を正常に完了させるには、RTCUniversalServerAdmins グループのメンバーであるユーザーとしてログオンする必要があります。

Windows PowerShellの **Test-CsKerberosAccountAssignment** コマンドレットを使用して、Kerberos 認証を使用するサイト割り当ての機能的な準備ができているかどうかをテストし、報告することができます。このコマンドは、必須の Identity パラメーターで指定されているサイトを照会します。オプションの Report パラメーターを指定すると、このコマンドレットにより、コマンドを実行するコンピューターの C:\\Logs に HTML レポートが書き込まれます。オプションの Verbose パラメーターを指定すると、アクティビティ情報が画面に表示されます。

## サイトで Kerberos 認証を使用する機能的な準備ができていることをテストおよび報告するには

1.  RTCUniversalServerAdmins グループのメンバーとして、 Lync Server 2013 が実行されているドメインのコンピューターにログオンするか、管理ツールがインストールされているコンピューターにログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  コマンド ラインで、次のコマンドを実行します。
    
        Test-CsKerberosAccountAssignment -Identity "site:SiteName" -Report "c:\logs\FileName.htm" -Verbose
    
    次に例を示します。
    
        Test-CsKerberosAccountAssignment -Identity "site:Redmond" -Report "c:\logs\KerberosReport.htm" -Verbose

