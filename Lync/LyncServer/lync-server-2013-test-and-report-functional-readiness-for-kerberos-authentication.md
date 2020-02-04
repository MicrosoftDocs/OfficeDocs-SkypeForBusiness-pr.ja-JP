---
title: Kerberos 認証のテストおよびレポート機能の準備
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test and report functional readiness for Kerberos authentication
ms:assetid: d52c39e5-747d-4f29-88aa-30fd6f26b99c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398925(v=OCS.15)
ms:contentKeyID: 48185519
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8763203827afd3d14638b68474c4f9bd9d6d0cfc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746509"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-and-report-functional-readiness-for-kerberos-authentication-in-lync-server-2013"></a>Lync Server 2013 における Kerberos 認証のテストおよびレポート機能の準備

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-01-16_

この手順を正常に完了するには、RTCUniversalServerAdmins グループのメンバーであるユーザーとしてログオンする必要があります。

**CsKerberosAccountAssignment** Windows PowerShell コマンドレットを使用して、Kerberos 認証のサイト割り当ての機能の準備をテストして報告することができます。 このコマンドは、必須の Identity パラメーターで指定されたサイトを照会します。 省略可能なレポートパラメーターを指定すると、コマンドレットは、コマンド\\が実行されているコンピューター上の C: ログに HTML レポートを書き込みます。 オプションの Verbose パラメーターは、画面にアクティビティ情報をレポートします。

<div>

## <a name="to-test-and-report-functional-readiness-for-kerberos-authentication-for-a-site"></a>サイトの Kerberos 認証の機能の準備をテストして報告するには

1.  RTCUniversalServerAdmins グループのメンバーとして、Lync Server 2013 を実行しているドメイン内のコンピューター、または管理ツールがインストールされているコンピューターにログオンします。

2.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

3.  コマンドラインで、次のコマンドを実行します。
    
        Test-CsKerberosAccountAssignment -Identity "site:SiteName" -Report "c:\logs\FileName.htm" -Verbose
    
    例:
    
        Test-CsKerberosAccountAssignment -Identity "site:Redmond" -Report "c:\logs\KerberosReport.htm" -Verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

