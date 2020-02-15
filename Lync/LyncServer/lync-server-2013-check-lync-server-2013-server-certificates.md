---
title: 'Lync Server 2013: Lync Server 2013 サーバー証明書の確認'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Check server certificates
ms:assetid: 7b0474e8-0efe-47f0-84eb-a1ba575dabfd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725210(v=OCS.15)
ms:contentKeyID: 63969620
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ebdbfdc4ed0f88d78fc78037a3522c73bd220270
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043509"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="check-lync-server-2013-server-certificates"></a>Lync Server 2013 のサーバー証明書を確認する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-11-01_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>検証スケジュール</p></td>
<td><p>毎月</p></td>
</tr>
<tr class="even">
<td><p>テストツール</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>必要なアクセス許可</p></td>
<td><p>Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</p>
<p>Windows PowerShell のリモートインスタンスを使用して実行する場合は、ユーザーに、CsCertificate コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。 このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Get-CsCertificate&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

Get-help Certificate コマンドレットを使用すると、各 Lync Server 証明書に関する情報を取得できます。 証明書には有効期限が組み込まれているため、これは特に重要です。 たとえば、非公開で発行された証明書は、通常12か月後に期限切れになります。 いずれかの Lync Server 証明書の有効期限が切れた場合は、その証明書が更新または置き換えられるまで、付随する機能が失われます。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

各 Lync Server 証明書に関する情報を戻すには、次のコマンドを実行するだけです。

`Get-CsCertificate`

または、有効期限の日付に基づいて、返却証明書の情報をフィルター処理することができます。 たとえば、次のコマンドは、返されるデータを、有効期限が切れた (後で使用することができない) 証明書 (2014 年6月1日) に制限します。

`Get-CsCertificate | Where-Object {$_.NotAfter -lt "6/1/2014"}`

詳細については、「Get-help Certificate コマンドレットのヘルプドキュメント」を参照してください。

なお、Test-Cs/cs/コマンドレットは存在していても、管理者にとってはあまり役に立たないことに注意してください。 (そのコマンドレットは、主に証明書ウィザードによって使用されます)。コマンドレットは動作しますが、次の出力例に示すように、返される情報は最小値です。

拇印の使用

\---------- ---

A9D51A2911C74FABFF7F2A8A994B20857D399107 の既定値

</div>

<div>

## <a name="reviewing-the-output"></a>出力の確認

Get-help Certificate コマンドレットは、各 Lync Server 証明書について次のような情報を返します。

発行者: CN = FabrikamCA

NotAfter: 12/28/2015 3:35:41 PM

NotBefore: 1/2/2014 12:49:37 PM

シリアル: 611BB01200000000000C

件名: CN = LYNC-SE.fabrikam.com

代替の [ベンダー]: {sip.fabrikam.com, LYNC-SE.fabrikam.com,

meet.fabrikam.com、admin.fabrikam.com

Thumbprint: A9D51A2911C74FABFF7F2A8A994B20857D399107

Use: Default

原則として、Lync Server 証明書に関連する主な問題には、証明書が有効になったときや期限切れになったとき (NotAfter) など、日付と時刻が含まれます。 これらの日付と時刻が重要であるため、返されるデータを証明書の使用、証明書のシリアル番号、証明書の有効期限などの情報に制限することをお勧めします。これにより、すべての証明書とその期限が切れるまでの時間をすばやく確認できます。 その情報のみを返すには、次のようなオプションを使用してコマンドを使用します。

`Get-CsCertificate | Select-Object Use, SerialNumber, NotAfter | Sort-Object NotAfter`

このコマンドは、証明書が有効期限の順に並べ替えられた状態で、次のようなデータを返します。

シリアルの使用

\--- ------------ --------

Default 611BB01200000000000C 12/28/2015 3:35:41 PM

Webサービス Interal 32980AA20BBB20000191 02/15/2016 2:16:12 PM

WebServicesExternal 0451B012003872651A0C 02/20/2016 7:11:58 AM

証明書に問題がある場合は、証明書に対して構成された代替のベンダーを確認する必要があります。 一見すると、問題があるように見えます。 既定では、コンソールウィンドウのサイズによっては、を取得すると、すべての名前を表示できない場合があります。

代替の [ベンダー]: {sip.fabrikam.com, LYNC.fabrikam.com,

meet.fabrikam.com, fabrika...}

証明書に割り当てられているすべての代替名を表示するには、次のようなコマンドを使用します。

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


[-CsCertificate の取得](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

