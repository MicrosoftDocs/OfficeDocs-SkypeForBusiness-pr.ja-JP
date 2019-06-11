---
title: 'Lync Server 2013: 電話番号に対してトランクの構成を確認する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Check trunk configuration against a phone number
ms:assetid: 0800d7a3-fc35-482b-a9a4-203d890bfa45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725206(v=OCS.15)
ms:contentKeyID: 63969574
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b667f43e430b5047f72e2d8352f57337f0849055
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840583"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="check-trunk-configuration-against-a-phone-number-in-lync-server-2013"></a>Lync Server 2013 での電話番号に対するトランクの構成を確認する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-05-20_


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
<p>Windows PowerShell のリモートインスタンスを使って実行する場合は、Set-cstrunkconfiguration コマンドレットを実行するためのアクセス許可が与えられている RBAC の役割をユーザーに割り当てる必要があります。 このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsTrunkConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>説明

SIP trunks Lync Server の内部エンタープライズボイスネットワークを次のいずれかに接続します。

  - 公衆交換電話網 (PSTN)。

  - IP 公衆支店交換 (PBX)。

  - セッション境界コントローラー (SBC)。

Set-cstrunkconfiguration コマンドレットは、電話番号 (ユーザーによってダイヤルされた番号) を E.i ネットワークに変換し、指定された SIP トランクを介してルーティングできることを確認します。

</div>

<div>

## <a name="running-the-test"></a>テストの実行

Set-cstrunkconfiguration コマンドレットを実行するには、最初に Get-Set-cstrunkconfiguration コマンドレットを使用して SIP トランク構成設定のインスタンスを取得する必要があります。このインスタンスは、Set-cstrunkconfiguration にパイプラインとして渡されます。

`Get-CsTrunkConfiguration -Identity "Global" | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

Set-cstrunkconfiguration を実行していない場合、Set-cstrunkconfiguration は動作しません。 たとえば、次のコマンドは、データを返さずに失敗します。

`Test-CsTrunkConfiguration -DialedNumber "12065551219" -TrunkConfiguration "Global"`

SIP トランク構成設定のコレクションが複数ある場合は、次のようなコマンドを同時に使用して、各コレクションを同じ電話番号に対してテストすることができます。

`Get-CsTrunkConfiguration | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

詳細については、「Set-cstrunkconfiguration コマンドレットのヘルプドキュメント」を参照してください。

</div>

<div>

## <a name="determining-success-or-failure"></a>成功または失敗を確認する

Set-cstrunkconfiguration でダイヤルされた電話番号に通話を発信できる場合、翻訳された電話番号 (E.i 形式) と、その電話番号の翻訳に使用するルールは両方とも画面に表示されます。

TranslatedNumber MatchingRule

\---------------- ------------

\+12065551219グローバル/レドモンド

テストに失敗した場合、Set-cstrunkconfiguration は空のプロパティ値を返します。

TranslatedNumber MatchingRule

\---------------- ------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>テストに失敗した可能性がある理由

Set-cstrunkconfiguration によって一致が返されない場合、通常は、テスト対象のトランク構成設定に、ダイヤルされた番号を E.i 形式に変換できる発信呼び出し番号の翻訳ルールがありません。 トランク構成設定のコレクションに割り当てられている翻訳ルールを取得するには、次のような構文を使用できます。

`Get-CsTrunkConfiguration -Identity "global" | Select-Object -ExpandProperty OutboundTranslationRulesList`

これは、翻訳ルールごとに次のような情報を返します。

説明: 国コードまたは市外局番のない電話番号。

パターン: ^\\+ (\\d\*) $

`Translation : $1`

名前: NoAreaCode

この時点で、Pattern プロパティの値 ([正規表現](http://go.microsoft.com/fwlink/?linkid=400464)の文字列) をチェックして、いずれかの翻訳ルールがダイヤルされた番号を処理するように構成されているかどうかを確認します。 存在しない場合は、既存の規則 (CsOutboundTranslationRule) のいずれかを変更するか、CsOutboundTranslationRule コマンドレットを使用して新しいルールをコレクションに追加する必要があります。

</div>

<div>

## <a name="see-also"></a>関連項目


[テスト-Set-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

