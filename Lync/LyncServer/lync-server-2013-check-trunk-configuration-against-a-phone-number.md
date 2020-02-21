---
title: 'Lync Server 2013: 電話番号に対してトランク構成を確認する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Check trunk configuration against a phone number
ms:assetid: 0800d7a3-fc35-482b-a9a4-203d890bfa45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725206(v=OCS.15)
ms:contentKeyID: 63969574
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6bf9d53d8702fbd9e63ec05af2c4942538f7298e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190570"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="check-trunk-configuration-against-a-phone-number-in-lync-server-2013"></a>Lync Server 2013 で電話番号に対するトランク構成を確認する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-05-20_


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
<p>Windows PowerShell のリモートインスタンスを使用して実行する場合は、Get-cstrunkconfiguration コマンドレットを実行するためのアクセス許可を持つ RBAC の役割がユーザーに割り当てられている必要があります。 このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsTrunkConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

SIP トランク Lync Server の内部エンタープライズ Voip ネットワークを次のいずれかに接続します。

  - 公衆交換電話網 (PSTN)。

  - IP パブリックブランチ exchange (PBX)。

  - セッションボーダーコントローラー (SBC)。

Get-cstrunkconfiguration コマンドレットでは、(ユーザーによってダイヤルされた) 電話番号を e.164 ネットワークに変換し、指定された SIP トランクを経由してルーティングできることを確認します。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

Get-cstrunkconfiguration コマンドレットを実行するには、最初に Get-cstrunkconfiguration コマンドレットを使用して SIP トランク構成設定のインスタンスを取得する必要があります。その後、そのインスタンスは Get-cstrunkconfiguration にパイプ処理されます。

`Get-CsTrunkConfiguration -Identity "Global" | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

最初に Get-cstrunkconfiguration を実行せずにテストを実行すると、Get-cstrunkconfiguration は機能しません。 たとえば、次のコマンドは、データを返さずに失敗します。

`Test-CsTrunkConfiguration -DialedNumber "12065551219" -TrunkConfiguration "Global"`

SIP トランク構成設定のコレクションが複数ある場合は、次のようなコマンドを同時に使用して、各コレクションを同じ電話番号に対してテストできます。

`Get-CsTrunkConfiguration | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

詳細については、Get-cstrunkconfiguration コマンドレットのヘルプドキュメントを参照してください。

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を判断する

Get-cstrunkconfiguration がダイヤル番号に電話をかけることができる場合は、(e.164 形式で) 翻訳された電話番号と、その電話番号の変換に使用されるルールの両方が画面に表示されます。

TranslatedNumber MatchingRule

\---------------- ------------

\+12065551219グローバル/Redmond

テストが失敗した場合、Get-cstrunkconfiguration は空のプロパティ値を返します。

TranslatedNumber MatchingRule

\---------------- ------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストが失敗した理由

Get-cstrunkconfiguration が一致を返さない場合、通常は、テスト対象のトランク構成設定に、ダイヤル番号を e.164 形式に変換できる発信通話番号変換ルールがないことを意味します。 トランク構成設定のコレクションに割り当てられている変換ルールを取得するには、次のような構文を使用します。

`Get-CsTrunkConfiguration -Identity "global" | Select-Object -ExpandProperty OutboundTranslationRulesList`

これにより、変換ルールごとに次のような情報が返されます。

説明: 国番号またはエリアコードのない電話番号。

パターン: ^\\+ (\\d\*) $

`Translation : $1`

名前: NoAreaCode

その時点で、Pattern プロパティ ([正規表現](https://go.microsoft.com/fwlink/?linkid=400464)文字列) の値をチェックして、いずれかの変換ルールがダイヤル番号を処理するように構成されているかどうかを確認します。 それ以外の場合は、既存のルールの1つを変更するか (New-csoutboundtranslationrule)、New-csoutboundtranslationrule コマンドレットを使用して新しいルールをコレクションに追加します。

</div>

<div>

## <a name="see-also"></a>関連項目


[Get-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

