---
title: 'Lync Server 2013: ダイヤルプランと正規化ルール'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial plans and normalization rules
ms:assetid: fde45195-6eb4-403c-9094-57df7fc0bd2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413082(v=OCS.15)
ms:contentKeyID: 48185960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e9f42d2467a77e35eb9f5a158967357534e86da
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153859"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dial-plans-and-normalization-rules-in-lync-server-2013"></a>Lync Server 2013 のダイヤルプランと正規化ルール

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-21_

ダイヤル プランとは、電話番号の承認と通話のルーティングを目的として、特定の場所、個々のユーザー、または連絡先オブジェクトの電話番号を 1 つの標準形式 (E.164) に変換する正規化ルールのセットに名前を付けたものです。

正規化ルールは、さまざまな形式で表現された電話番号を指定された各場所、ユーザー、または連絡先オブジェクトにルーティングする方法を定義します。 ダイヤル元の場所や、呼び出しを行った人物または連絡先オブジェクトによって、同じダイヤル文字列が異なる方法で解釈および変換される場合があります。

<div>

## <a name="dial-plan-scope"></a>ダイヤル プランのスコープ

ダイヤル プランの*スコープ*によって、ダイヤル プランを適用できる階層レベルが決まります。 Lync Server では、ユーザーに特定のユーザーごとのダイヤルプランを割り当てることができます。 ユーザーのダイヤル プランが割り当てられていない場合は、レジストラー プールのダイヤル プランが適用されます。 レジストラー プールのダイヤル プランがない場合は、サイトのダイヤル プランが適用されます。 ユーザーに適用可能な他のダイヤル プランがない場合は、最後にグローバル ダイヤル プランが適用されます。

クライアントは、ユーザーが Lync Server にログオンするときに提供されるインバンドプロビジョニング設定によって、ダイヤルプランのスコープレベルを取得します。 管理者は、Lync Server コントロールパネルを使用して、ダイヤルプランのスコープレベルの管理と割り当てを行うことができます。

<div>


> [!NOTE]  
> サービスレベルの公衆交換電話網 (PSTN) ゲートウェイのダイヤルプランは、特定のゲートウェイからの着信呼び出しに適用されます。



</div>

ダイヤル プランのスコープ レベルは、次のように定義されます。

  - **ユーザーダイヤルプラン:** 個別のユーザー、グループ、または連絡先オブジェクトに割り当てることができます。 音声アプリケーションは、電話コンテキストがユーザー既定に設定された通話を受信したときに、ユーザーごとのダイヤルプランを検索できます。 ダイヤルプランを割り当てる目的で、連絡先オブジェクトは個別のユーザーとして扱われます。

  - **プールダイヤルプラン:** は、トポロジ内の PSTN ゲートウェイまたはレジストラーのサービスレベルで作成できます。 プール ダイヤル プランを定義するには、ダイヤル プランを適用する特定のサービス (PSTN ゲートウェイまたはレジストラー プール) を指定する必要があります。

  - **サイトダイヤルプラン:** プールダイヤルプランまたはユーザーダイヤルプランが割り当てられているユーザー、グループ、または連絡先オブジェクトを除く、サイト全体に対して作成できます。 サイト ダイヤル プランを定義するには、ダイヤル プランを適用するサイトを指定する必要があります。

  - **グローバルダイヤルプラン:** 製品と共にインストールされる既定のダイヤルプラン。 グローバル ダイヤル プランは、編集はできますが削除することはできません。 このダイヤルプランは、より具体的なスコープを持つダイヤルプランを構成して割り当てる場合を除き、展開内のすべてのエンタープライズ Voip ユーザー、グループ、および連絡先オブジェクトに適用されます。

</div>

<div>

## <a name="planning-for-dial-plans"></a>ダイヤル プランの計画

ダイヤルプランを計画するには、次の手順を実行します。

  - 組織に office があるすべてのロケールを一覧表示します。
    
    リストは、最新の状態にする必要があります。 また、組織の変化に合わせて改訂する必要があります。 多数の小規模な支社を持つ大規模な多国籍企業では、この作業は時間がかかることがあります。

  - 各サイトの有効な番号パターンを特定します。
    
    ダイヤル プランの計画で最も時間がかかるのは、それぞれのサイトの有効な番号パターンを特定することです。 あるダイヤル プラン用に記述した正規化ルールを他のダイヤル プランにコピーできる場合があります (特に、対応しているサイトが同じ国/地域または大陸にある場合)。 これ以外の場合でも、あるダイヤル プランの番号を少し変更すれば他のダイヤル プランに十分使用できる場合があります。

  - ダイヤルプランの名前付けのための、組織全体のスキームを開発します。
    
    標準の名前付けスキームを採用することで、組織間の一貫性を保ち、メンテナンスと更新を簡単に行うことができます。

  - 1つの場所に複数のダイヤルプランが必要かどうかを決定します。
    
    組織が複数の場所で単一のダイヤルプランを保有している場合は、構内交換機 (PBX) から移行していて、既存の内線番号を保持する必要があるエンタープライズ Voip ユーザー向けに、別のダイヤルプランを作成する必要があります。

  - ユーザーごとのダイヤルプランが必要かどうかを決定します。 たとえば、中央サイトに登録されているブランチサイトにユーザーがいる場合、または存続可能 Branch アプライアンスに登録されているユーザーがいる場合は、ユーザーごとのダイヤルプランや正規化ルールを使用して、そのようなユーザーに対して特別なダイヤルシナリオを検討できます。. 詳細については、「 [Lync Server 2013 のブランチサイトの復元要件](lync-server-2013-branch-site-resiliency-requirements.md)」を参照してください。

  - ダイヤルプランのスコープを決定します (このトピックで前述したとおり)。

ダイヤルプランを作成するには、Lync Server コントロールパネルまたは Lync Server 管理シェルを使用して、必要に応じて以下のフィールドに値を指定します。

<div>

## <a name="name-and-simple-name"></a>名前および簡単な名前

ユーザーダイヤルプランの場合は、ダイヤルプランを割り当てるユーザー、グループ、または連絡先オブジェクトを識別するわかりやすい名前を指定する必要があります。 サイト ダイヤル プランの場合、[名前] フィールドにサイト名が事前に入力されており、変更することはできません。 プールダイヤルプランの場合、[名前] フィールドに PSTN ゲートウェイまたはフロントエンドプールの完全修飾ドメイン名 (FQDN) が事前に設定されており、変更することはできません。

ダイヤル プランの*簡単な名前*には、ダイヤル プラン名を使用した文字列が事前に入力されています。 [簡易名] フィールドは編集できます。これにより、ダイヤルプランのわかりやすい名前付け規則を作成できます。 *簡単な名前*の値を空にすることはできず、一意である必要があります。 ベストプラクティスとして、組織全体の名前付け規則を作成し、すべてのサイトとユーザーに対してこの規則を一貫して使用することをお勧めします。

</div>

<div>

## <a name="description"></a>説明

対応するダイヤル プランが適用される地理的な場所の、一般的でわかりやすい名前を入力することをお勧めします。 たとえば、ダイヤル プランの名前が London.Contoso.com である場合、説明を London とすることをお勧めします。

</div>

<div>

## <a name="dial-in-conferencing-region"></a>ダイヤルイン会議の地域

ダイヤルイン会議を展開している場合、ダイヤルイン会議の地域を指定し、ダイヤルイン会議のアクセス番号をダイヤル プランと関連付ける必要があります。

</div>

<div>

## <a name="external-access-prefix"></a>外部アクセス プレフィックス

外部の行を取得するためにユーザーが1つまた\#は\*複数の追加の数字 (9 など) をダイヤルする必要がある場合は、最大4文字 (,, および 0-9) の外部アクセスプレフィックスを指定できます。

<div>


> [!NOTE]  
> 外部アクセス プレフィックスを指定する場合に、プレフィックスに対応するために追加の正規化ルールを作成する必要はありません。



</div>

</div>

</div>

<div>

## <a name="normalization-rules"></a>正規化ルール

正規化ルールは、さまざまな形式で表現される電話番号を、名前付きの場所にルーティングする方法を定義します。 同じ数値文字列は、ダイヤル元のロケールに応じて、異なる方法で解釈および変換される場合があります。 ユーザーが連絡先リストに電話番号を入力する際にさまざまな形式を使用できるため、通話のルーティングに正規化ルールが必要です。

ユーザーが指定した電話番号を正規化すると、次のタスクを容易にする一貫した形式が提供されます。

  - ダイヤル番号を目的の受信者の SIP URI と一致させます。

  - 発信者にダイヤル承認ルールを適用します。

次の番号フィールドでは、正規化ルールの考慮が必要になる可能性があります。

  - ダイヤル プラン

  - 国番号

  - 市外局番

  - 内線番号の長さ

  - サイトのプレフィックス

<div>

## <a name="creating-normalization-rules"></a>正規化ルールの作成

正規化ルールは、.NET Framework 正規表現を使用して、逆引き番号検索を実行するために、サーバーがダイヤル文字列を e.164 形式に変換するために使用する数値一致パターンを指定します。 Lync Server コントロールパネルで正規化ルールを作成するには、式を手動で入力するか、一致するダイヤル文字列の先頭の数字と長さを入力して、Lync Server コントロールパネルで対応する正規表現。 完了したら、テスト番号を入力して、正規化ルールが期待どおりに動作するかどうかを確認できます。

.NET Framework の正規表現の使用の詳細については、「」の[https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927)「.Net Framework 正規表現」を参照してください。

</div>

<span id="BKMK_SampleNormalizationRules"></span>

<div>

## <a name="sample-normalization-rules"></a>正規化ルールの例

次の表は、.NET Framework 正規表現で記述された正規化ルールの例です。 ここに示すのは単なる例であり、ご自分の正規化ルールをこのとおりに作成する必要はありません。

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
<th>翻訳</th>
<th>例</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>4digitExtension</p></td>
<td><p>4 桁の内線番号を変換します。</p></td>
<td><p>^ (\d{4}) $</p></td>
<td><p>+ 1425555 $ 1</p></td>
<td><p>0100 が +14255550100 に変換されます。</p></td>
</tr>
<tr class="even">
<td><p>5digitExtension</p></td>
<td><p>5 桁の内線番号を変換します。</p></td>
<td><p>^ 5 (\d{4}) $</p></td>
<td><p>+ 1425555 $ 1</p></td>
<td><p>50100 が +14255550100 に変換されます。</p></td>
</tr>
<tr class="odd">
<td><p>7digitcallingRedmond</p></td>
<td><p>7 桁の番号を Redmond の電話番号に変換します。</p></td>
<td><p>^ (\d{7}) $</p></td>
<td><p>+ 1425 $ 1</p></td>
<td><p>5550100 が +14255550100 に変換されます。</p></td>
</tr>
<tr class="even">
<td><p>7digitcallingDallas</p></td>
<td><p>7 桁の番号を Dallas の電話番号に変換します。</p></td>
<td><p>^ (\d{7}) $</p></td>
<td><p>+ 1972 $ 1</p></td>
<td><p>5550100 が +19725550100 に変換されます。</p></td>
</tr>
<tr class="odd">
<td><p>10digitcallingUS</p></td>
<td><p>米国の 10 桁の番号を変換します。</p></td>
<td><p>^ (\d{10}) $</p></td>
<td><p>+ 1 $ 1</p></td>
<td><p>2065550100 が +12065550100 に変換されます。</p></td>
</tr>
<tr class="even">
<td><p>LDCallingUS</p></td>
<td><p>米国の長距離プレフィックス付きの番号を変換します。</p></td>
<td><p>^ 1 (\d{10}) $</p></td>
<td><p>+ $1</p></td>
<td><p>12145550100 が +2145550100 に変換されます。</p></td>
</tr>
<tr class="odd">
<td><p>IntlCallingUS</p></td>
<td><p>米国の国際プレフィックス付きの番号を変換します。</p></td>
<td><p>^ 011 (\d *) $</p></td>
<td><p>+ $1</p></td>
<td><p>01191445550100 が +91445550100 に変換されます。</p></td>
</tr>
<tr class="even">
<td><p>RedmondOperator</p></td>
<td><p>0 を Redmond のオペレータ呼び出し番号に変換します。</p></td>
<td><p>^ $0</p></td>
<td><p>+ 14255550100</p></td>
<td><p>0 が +14255550100 に変換されます。</p></td>
</tr>
<tr class="odd">
<td><p>RedmondSitePrefix</p></td>
<td><p>ネットワーク内プレフィックス (6) および Redmond のサイト コード (222) 付きの番号を変換します。</p></td>
<td><p>^ 6222 (\d{4}) $</p></td>
<td><p>+ 1425555 $ 1</p></td>
<td><p>62220100 が +14255550100 に変換されます。</p></td>
</tr>
<tr class="even">
<td><p>NYSitePrefix</p></td>
<td><p>ネットワーク内プレフィックス (6) および NY のサイト コード (333) 付きの番号を変換します。</p></td>
<td><p>^ 6333 (\d{4}) $</p></td>
<td><p>+ 1202555 $ 1</p></td>
<td><p>63330100 が +12025550100 に変換されます。</p></td>
</tr>
<tr class="odd">
<td><p>DallasSitePrefix</p></td>
<td><p>ネットワーク内プレフィックス (6) および Dallas のサイト コード (444) 付きの番号を変換します。</p></td>
<td><p>^ 6444 (\d{4}) $</p></td>
<td><p>+ 1972555 $ 1</p></td>
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
<th>Redmond. forestFQDN</th>
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
> 前の表に記載した正規化ルールの名前にはスペースが含まれていませんが、これは任意に設定できます。たとえば、この表の最初の名前は、「5 digit extension」または「5-digit Extension」のどちらで記述しても問題ありません。



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

