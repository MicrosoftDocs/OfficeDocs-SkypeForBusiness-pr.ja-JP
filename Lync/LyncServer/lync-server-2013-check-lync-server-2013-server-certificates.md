---
title: 'Lync Server 2013: Lync Server 2013 サーバーの証明書を確認する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Check server certificates
ms:assetid: 7b0474e8-0efe-47f0-84eb-a1ba575dabfd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725210(v=OCS.15)
ms:contentKeyID: 63969620
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dced86c93b7ec35cb410601f1d72720e25d156b0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840586"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="check-lync-server-2013-server-certificates"></a>Lync Server 2013 サーバー証明書を確認する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-11-01_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>確認のスケジュール</p></td>
<td><p>毎月</p></td>
</tr>
<tr class="even">
<td><p>テストツール</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>必要なアクセス許可</p></td>
<td><p>Lync Server 管理シェルを使用してローカルで実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</p>
<p>Windows PowerShell のリモートインスタンスを使って実行する場合、ユーザーには、CsCertificate の取得コマンドレットを実行するためのアクセス許可が与えられた RBAC の役割を割り当てる必要があります。 このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Get-CsCertificate&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

CsCertificate コマンドレットを使用すると、Lync Server の各証明書に関する情報を取得できます。 これは特に重要です。証明書には有効期限があります。 たとえば、プライベートに発行された証明書は通常、12か月後に期限切れになります。 いずれかの Lync Server 証明書の有効期限が切れている場合は、その証明書が更新または置き換えられるまで、付属の機能が失われます。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

Lync Server の各証明書に関する情報を取得するには、次のコマンドを実行します。

`Get-CsCertificate`

または、有効期限日に基づいて、返送証明書情報をフィルター処理することもできます。 たとえば、次のコマンドは、返されるデータを有効期限が切れた証明書 (2014 年6月1日以降は使用できません) に制限します。

`Get-CsCertificate | Where-Object {$_.NotAfter -lt "6/1/2014"}`

詳細については、「CsCertificate を取得する」コマンドレットのヘルプドキュメントを参照してください。

ここでは、テスト用の Csコマンドレットは存在しますが、管理者にとってはあまり役に立ちません。 (その代わりに、このコマンドレットは証明書ウィザードで主に使用されます)。このコマンドレットは動作しますが、次の出力例に示すように、返される情報は最小限の値になります。

拇印の使用

\---------- ---

A9D51A2911C74FABFF7F2A8A994B20857D399107 の既定値

</div>

<div>

## <a name="reviewing-the-output"></a>出力を確認する

各 Lync Server 証明書について、次のような情報が返されます。

発行者: CN = FabrikamCA

NotAfter: 12/28/2015 3:35:41 PM

NotBefore: 1/2/2014 12:49:37 PM

シリアル: 611BB01200000000000C

Subject: CN = LYNC-SE.fabrikam.com

代替: {sip.fabrikam.com、LYNC-SE.fabrikam.com、

meet.fabrikam.com、admin.fabrikam.com

拇印: A9D51A2911C74FABFF7F2A8A994B20857D399107

使用: 既定

ルールとして、Lync Server の証明書に関連する主な問題には、証明書が適用される時期 (NotBefore)、または期限切れになったとき (NotAfter) など、日付と時刻が含まれます。 このような日付と時刻は重要であるため、証明書の使用、証明書のシリアル番号、証明書の有効期限などの情報に、返されるデータを制限することができます。これにより、すべての証明書を簡単に確認して、期限切れにすることができます。 その情報だけを返すには、次のようなオプションと共にコマンドを使用します。

`Get-CsCertificate | Select-Object Use, SerialNumber, NotAfter | Sort-Object NotAfter`

このコマンドを実行すると、次のようなデータが返されます。証明書は有効期限の順に並べ替えられます。

以降のシリアルで使用

\--- ------------ --------

既定の 611BB01200000000000C 12/28/2015 3:35:41 PM

Webservices Interal 32980AA20BBB20000191 02/15/2016 2:16:12 PM

WebServicesExternal 0451B012003872651A0C 02/20/2016 7:11:58 AM

証明書の問題がある場合は、証明書に対して構成されている代替の内容を確認することをお勧めします。 一見したところ、問題に思えるかもしれません。 既定では、コンソールウィンドウのサイズに応じて、ユーザーがすべての名前を表示できない場合があります。

代替: {sip.fabrikam.com、LYNC.fabrikam.com、

meet.fabrikam.com の場合は、fabrika

証明書に割り当てられている代替名をすべて表示するには、次のようなコマンドを使用します。

`Get-CsCertificate | Where-Object {$_.SerialNumber -eq "611BB01200000000000C"} | Select-Object -ExpandProperty AlternativeNames`

これにより、証明書のすべての代替名が表示されます。

sip.fabrikam.com

LYNC.fabrikam.com

meet.fabrikam.com

admin.fabrikam.com

LYNC-SE.fabrikam.com

Dialin.fabrikam.com

</div>

<div>

## <a name="see-also"></a>関連項目


[Get-CsCertificate](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

