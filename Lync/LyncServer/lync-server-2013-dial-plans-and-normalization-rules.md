---
title: 'Lync Server 2013: ダイヤルプランと正規化ルール'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Dial plans and normalization rules
ms:assetid: fde45195-6eb4-403c-9094-57df7fc0bd2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413082(v=OCS.15)
ms:contentKeyID: 48185960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5d399c49db109a7bac1a1cd3ac430280cb70f665
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833420"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dial-plans-and-normalization-rules-in-lync-server-2013"></a>Lync Server 2013 でのダイヤルプランと正規化ルール

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-21_

ダイヤル プランとは、電話番号の承認と通話のルーティングを目的として、特定の場所、個々のユーザー、または連絡先オブジェクトの電話番号を 1 つの標準形式 (E.164) に変換する正規化ルールのセットに名前を付けたものです。

正規化ルールは、さまざまな形式で表現された電話番号を指定された各場所、ユーザー、または連絡先オブジェクトにルーティングする方法を定義します。ダイヤル元の場所および電話をかける人や連絡先オブジェクトによって、同じダイヤル文字列が異なる方法で解釈および変換される場合があります。

<div>

## <a name="dial-plan-scope"></a>ダイヤル プランのスコープ

ダイヤル プランの*スコープ*によって、ダイヤル プランを適用できる階層レベルが決まります。 Lync Server では、ユーザーに特定のユーザーごとのダイヤルプランを割り当てることができます。 ユーザーダイヤルプランが割り当てられていない場合は、レジストラー pool dial plan が適用されます。 レジストラー pool ダイヤルプランがない場合は、サイトダイヤルプランが適用されます。 ユーザーに適用可能な他のダイヤル プランがない場合は、最後にグローバル ダイヤル プランが適用されます。

クライアントは、ユーザーが Lync Server にログオンしたときに提供されるインバンドプロビジョニングの設定を通じて、ダイヤルプランのスコープレベルを取得します。 管理者は、Lync Server コントロールパネルを使用して、ダイヤルプランのスコープレベルを管理して割り当てることができます。

<div>


> [!NOTE]  
> サービス レベルの公衆交換電話網 (PSTN) ゲートウェイのダイヤル プランは、特定のゲートウェイからの着信に適用されます。



</div>

ダイヤル プランのスコープ レベルは、次のように定義されます。

  - **ユーザーダイヤルプラン:** 個々のユーザー、グループ、または連絡先オブジェクトに割り当てることができます。 音声アプリケーションは、user-default に設定された電話コンテキストのコールを受信したとき、ユーザーごとのダイヤル プランを参照できます。 連絡先オブジェクトは、ダイヤル プラン割り当ての際には個々のユーザーとして扱われます。

  - **プールダイヤルプラン:** お客様のトポロジの PSTN ゲートウェイまたはレジストラーのサービスレベルで作成できます。 プール ダイヤル プランを定義するには、ダイヤル プランを適用する特定のサービス (PSTN ゲートウェイまたはレジストラー プール) を指定する必要があります。

  - **サイトダイヤルプラン:** プールダイヤルプランまたはユーザーダイヤルプランが割り当てられているユーザー、グループ、または連絡先オブジェクトを除き、サイト全体に対して作成できます。 サイト ダイヤル プランを定義するには、ダイヤル プランを適用するサイトを指定する必要があります。

  - **グローバルダイヤルプラン:** 製品と共にインストールされた既定のダイヤルプラン。 グローバル ダイヤル プランは、編集することはできますが削除はできません。 このダイヤルプランは、より具体的なスコープのダイヤルプランを構成して割り当てる場合を除き、展開内のすべてのエンタープライズボイスユーザー、グループ、連絡先オブジェクトに適用されます。

</div>

<div>

## <a name="planning-for-dial-plans"></a>ダイヤル プランの計画

ダイヤル プランを計画するには、次の手順を実行します。

  - 組織内のオフィスがあるすべてのロケールをリストアップします。
    
    このリストは、すべてを網羅した最新の情報である必要があります。また、組織の変化に合わせて改訂する必要があります。多数の小規模なブランチ オフィスを持つ大規模な多国籍企業の場合は、この作業に時間がかかる可能性があります。

  - 各サイトにおける有効な番号パターンを特定します。
    
    ダイヤル プランの計画で最も時間がかかるのは、それぞれのサイトの有効な番号パターンを特定することです。あるダイヤル プラン用に記述した正規化ルールを他のダイヤル プランにコピーできる場合があります (特に、対応しているサイトが同じ国/地域または大陸にある場合)。これ以外の場合でも、あるダイヤル プランの番号を少し変更すれば他のダイヤル プランに十分使用できる場合があります。

  - ダイヤル プランの名前付けのための、組織全体のスキームを開発します。
    
    標準の名前付けスキームを採用することで、組織間の一貫性を保ち、メンテナンスと更新を簡単に行うことができます。

  - 1 つの場所で複数のダイヤル プランが必要かどうかを判断します。
    
    組織が複数の場所で1つのダイヤルプランを管理している場合は、プライベートブランチ exchange (PBX) から移行している、または既存の拡張機能が保持されている必要があるエンタープライズボイスユーザーに対して、別のダイヤルプランを作成する必要があります。

  - ユーザーごとのダイヤル プランが必要かどうかを決定します。 たとえば、セントラルサイトに登録されているブランチサイトにユーザーがいる場合、または Survivable Branch アプライアンスに登録されているユーザーがいる場合、ユーザーのダイヤルプランと正規化ルールを使用しているユーザーのために特別なダイヤルシナリオを検討することができます。. 詳細については、「 [Lync Server 2013 のブランチサイトの回復性の要件](lync-server-2013-branch-site-resiliency-requirements.md)」を参照してください。

  - ダイヤル プランのスコープを決定します (このトピック内で前述)。

ダイヤルプランを作成するには、Lync Server コントロールパネルまたは Lync Server 管理シェルを使用して、必要に応じて次のフィールドの値を指定します。

<div>

## <a name="name-and-simple-name"></a>名前および簡単な名前

ユーザー ダイヤル プランの場合、ダイヤル プランの割り当て先のユーザー、グループ、または連絡先オブジェクトを識別する説明的な名前を指定する必要があります。 サイトダイヤルプランの場合、[名前] フィールドにはサイト名があらかじめ記載されているため、変更することはできません。 プールダイヤルプランの場合、[名前] フィールドには PSTN ゲートウェイまたはフロントエンドプールの完全修飾ドメイン名 (FQDN) が事前に指定されているため、変更することはできません。

ダイヤルプランの*簡易名*は、ダイヤルプラン名から派生した文字列を基にして編成されます。 "簡単な名前" フィールドは編集することができ、よりわかりやすいダイヤル プランの名前付け規則を作成できるようになっています。 *簡単な名前*の値を空にすることはできず、一意である必要があります。 組織全体の名前付け規則を開発し、この規則をすべてのサイトとユーザーで一貫して使用することをお勧めします。

</div>

<div>

## <a name="description"></a>説明

対応するダイヤル プランが適用される地理的な場所の、一般的でわかりやすい名前を入力することをお勧めします。たとえば、ダイヤル プランの名前が London.Contoso.com である場合、説明を London とすることをお勧めします。

</div>

<div>

## <a name="dial-in-conferencing-region"></a>ダイヤルイン会議の地域

ダイヤルイン会議を展開している場合、ダイヤルイン会議の地域を指定し、ダイヤルイン会議のアクセス番号をダイヤル プランと関連付ける必要があります。

</div>

<div>

## <a name="external-access-prefix"></a>外部アクセス プレフィックス

ユーザーが追加の先頭の数字 (9 など) をダイヤル\#する\*必要がある場合は、最大4文字 (,、0-9) の外部アクセスプレフィックスを指定して、外部の行を取得できます。

<div>


> [!NOTE]  
> 外部アクセス プレフィックスを指定する場合に、プレフィックスに対応するために追加の正規化ルールを作成する必要はありません。



</div>

</div>

</div>

<div>

## <a name="normalization-rules"></a>正規化ルール

正規化ルールは、さまざまな形式で表現された電話番号を指定の場所にルーティングする方法を定義します。同じ電話番号文字列が、その番号がダイヤルされたロケールに応じて、異なる方法で解釈および変換されることがあります。正規化ルールは通話のルーティングに不可欠です。これは、ユーザーが連絡先リストに電話番号を入力する際にさまざまな形式を使用する可能性があるためです。

ユーザーがダイヤルした電話番号を正規化することによって、形式の一貫性を確保できます。これは、次の処理に役立ちます。

  - ダイヤルされた番号と受信者の SIP-URI のマッチング

  - 発信者へのダイヤル承認ルールの適用

次の番号フィールドでは、正規化ルールの考慮が必要になる可能性があります。

  - ダイヤル プラン

  - 国番号

  - 市外局番

  - 内線番号の長さ

  - サイトのプレフィックス

<div>

## <a name="creating-normalization-rules"></a>正規化ルールの作成

正規化ルールでは、リバース番号検索でダイヤル文字列を E.164 形式に変換するためにサーバーによって使用される番号一致パターンを指定するために, .NET Framework の正規表現が使用されます。 Lync Server コントロールパネルで正規化ルールを作成するには、式を手動で入力するか、対応するダイヤル文字列の開始番号と長さを入力して、Lync Server コントロールパネルで対応する正規表現。 どちらの場合も、完了したら、テスト番号を入力して正規化ルールが期待どおりに動作することを確認できます。

.NET Framework の正規表現の使い方の詳細については、「」の[http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927)「.net Framework の正規表現」を参照してください。

</div>

<span id="BKMK_SampleNormalizationRules"></span>

<div>

## <a name="sample-normalization-rules"></a>正規化ルールの例

次の表は、.NET Framework 正規表現で記述された正規化ルールの例です。ここに示すのは単なる例であり、ご自分の正規化ルールをこのとおりに作成する必要はありません。

### <a name="table-1normalization-rules-using-net-framework-regular-expressions"></a>表 1. .NET Framework 正規表現を使用した正規化ルール

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>ルール名</th>
<th>説明</th>
<th>番号のパターン</th>
<th>変換</th>
<th>例</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>4digitExtension</p></td>
<td><p>4 桁の内線番号を変換します。</p></td>
<td><p>^ (\d{4}) $</p></td>
<td><p>+1425555$1</p></td>
<td><p>0100 は +14255550100 に変換されます</p></td>
</tr>
<tr class="even">
<td><p>5digitExtension</p></td>
<td><p>5 桁の内線番号を変換します。</p></td>
<td><p>^ 5 (\d{4}) $</p></td>
<td><p>+1425555$1</p></td>
<td><p>50100 は +14255550100 に変換されます</p></td>
</tr>
<tr class="odd">
<td><p>7digitcallingRedmond</p></td>
<td><p>7 桁の番号を Redmond の電話番号に変換します。</p></td>
<td><p>^ (\d{7}) $</p></td>
<td><p>+1425$1</p></td>
<td><p>5550100 が +14255550100 に変換されます。</p></td>
</tr>
<tr class="even">
<td><p>7digitcallingDallas</p></td>
<td><p>7 桁の番号を Dallas の電話番号に変換します。</p></td>
<td><p>^ (\d{7}) $</p></td>
<td><p>+1972$1</p></td>
<td><p>5550100 が +19725550100 に変換されます。</p></td>
</tr>
<tr class="odd">
<td><p>10digitcallingUS</p></td>
<td><p>米国の 10 桁の番号を変換します。</p></td>
<td><p>^ (\d{10}) $</p></td>
<td><p>+1$1</p></td>
<td><p>2065550100 が +12065550100 に変換されます。</p></td>
</tr>
<tr class="even">
<td><p>LDCallingUS</p></td>
<td><p>米国の長距離プレフィックス付きの番号を変換します。</p></td>
<td><p>^ 1 (\d{10}) $</p></td>
<td><p>+$1</p></td>
<td><p>12145550100 が +2145550100 に変換されます。</p></td>
</tr>
<tr class="odd">
<td><p>IntlCallingUS</p></td>
<td><p>米国の国際プレフィックス付きの番号を変換します。</p></td>
<td><p>^011(\d*)$</p></td>
<td><p>+$1</p></td>
<td><p>01191445550100 が +91445550100 に変換されます。</p></td>
</tr>
<tr class="even">
<td><p>RedmondOperator</p></td>
<td><p>0 を Redmond のオペレーター呼び出し番号に変換します。</p></td>
<td><p>^0$</p></td>
<td><p>+14255550100</p></td>
<td><p>0 は +14255550100 に変換されます</p></td>
</tr>
<tr class="odd">
<td><p>RedmondSitePrefix</p></td>
<td><p>ネットワーク内プレフィックス (6) および Redmond のサイト コード (222) 付きの番号を変換します。</p></td>
<td><p>^ 6222 (\d{4}) $</p></td>
<td><p>+1425555$1</p></td>
<td><p>62220100 が +14255550100 に変換されます。</p></td>
</tr>
<tr class="even">
<td><p>NYSitePrefix</p></td>
<td><p>ネットワーク内プレフィックス (6) および NY のサイト コード (333) 付きの番号を変換します。</p></td>
<td><p>^ 6333 (\d{4}) $</p></td>
<td><p>+1202555$1</p></td>
<td><p>63330100 が +12025550100 に変換されます。</p></td>
</tr>
<tr class="odd">
<td><p>DallasSitePrefix</p></td>
<td><p>ネットワーク内プレフィックス (6) および Dallas のサイト コード (444) 付きの番号を変換します。</p></td>
<td><p>^ 6444 (\d{4}) $</p></td>
<td><p>+1972555$1</p></td>
<td><p>64440100 が +19725550100 に変換されます。</p></td>
</tr>
</tbody>
</table>


以下の表は、Redmond (Washington、米国) の場所のダイヤル プランの例です。これは、前の表に示す正規化ルールに基づいています。

### <a name="table-2-redmond-dial-plan-based-on-normalization-rules-shown-in-table-1"></a>表 2. 表 1 の正規化ルールに基づく Redmond のダイヤル プラン

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th>Redmond.forestFQDN</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>5digitExtension</p></td>
</tr>
<tr class="even">
<td><p>7digitcallingRedmond</p></td>
</tr>
<tr class="odd">
<td><p>10digitcallingUS</p></td>
</tr>
<tr class="even">
<td><p>IntlCallingUS</p></td>
</tr>
<tr class="odd">
<td><p>RedmondSitePrefix</p></td>
</tr>
<tr class="even">
<td><p>NYSitePrefix</p></td>
</tr>
<tr class="odd">
<td><p>DallasSitePrefix</p></td>
</tr>
<tr class="even">
<td><p>RedmondOperator</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 前の表に示した正規化ルールの名前にはスペースが含まれていませんが、必要に応じて含めることもできます。たとえば、表に最初に示されている名前は、「5 digit extension」と「5-digit Extension」のどちらの形式で記述しても有効になります。



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

