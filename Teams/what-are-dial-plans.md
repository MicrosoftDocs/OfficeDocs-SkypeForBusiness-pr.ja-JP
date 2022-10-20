---
title: ダイヤル プランについて
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.voice.dialplans.overview
- Calling Plans
description: 'Teams で使用できるダイヤル通話プラン (PSTN 通話ダイヤル プラン) の種類と、組織に対してダイヤル通話プランを選択する方法について説明します。  '
ms.openlocfilehash: 77ee7801d43bd6a7cf9ae9a9e3fc74c302f8caa0
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/20/2022
ms.locfileid: "68614250"
---
# <a name="what-are-dial-plans"></a>ダイヤル プランについて

ダイヤル プランは、通話承認と音声ルーティングを目的として、個々のユーザーによってダイヤルされた電話番号を別の形式 (通常は E.164) に変換する正規化ルールの名前付きセットです。

ダイヤル プランは、さまざまな形式で表される電話番号が別の 1 つの形式にどのように変換されるかを定義する 1 つ以上の正規化ルールで構成されます。 同じダイヤル文字列が、ダイヤル プランによって異なる形で解釈、変換される可能性があるため、指定されたユーザーに割り当てられているダイヤル プランに応じて、同じダイヤル番号が異なる形で変換、ルーティングされることがあります。 テナント ダイヤル プランは最大 1,000 個まで可能です。

テナントのダイヤル プランを作成および管理する場合は「[ダイヤル プランを作成および管理する](create-and-manage-dial-plans.md)」をご覧ください。

## <a name="tenant-dial-plan-scope"></a>テナント ダイヤル プランのスコープ

ダイヤル プランのスコープによって、ダイヤル プランを適用できる階層レベルが決まります。 クライアントは、ユーザーが Teams にサインインするときに自動的に提供されるプロビジョニング設定を使用して、適切なダイヤル プランを取得します。 管理者は、Microsoft Teams 管理センターまたはリモート PowerShell を使用して、ダイヤル プランのスコープ レベルを管理および割り当てることができます。

Teams には、サービス スコープとテナント スコープ (組織向け) の 2 種類のダイヤル プランがあります。 サービス スコープのダイヤル プランは、電話システムが利用可能なすべての国または地域に対して定義されます。 各ユーザーには、ユーザーに割り当てられた使用場所と一致するサービス国ダイヤル プランが自動的に割り当てられます。 サービス国ダイヤル プランは変更できませんが、テナント スコープダイヤル プランを作成して、サービス国ダイヤル プランを拡張できます。 クライアントがプロビジョニングされると、"有効なダイヤル プラン" が取得されます。これは、サービスの国のダイヤル プランと適切な範囲のテナント ダイヤル プランを組み合わせたものです。 したがって、テナント ダイヤル プラン内のすべての正規化ルールを定義する必要はありません。これは、サービスの国のダイヤル プランに既に存在する可能性があるためです。

テナント ダイヤル プランは、さらに 2 つのスコープ (テナント スコープまたはユーザー スコープ) に分割できます。 テナントがユーザー スコープのダイヤル プランを定義して割り当てる場合、そのユーザーは、ユーザーのサービス国ダイヤル プランと割り当てられたユーザー ダイヤル プランの有効なダイヤル プランを使用してプロビジョニングされます。 テナントがテナント スコープのダイヤル プランを定義しているが、ユーザー スコープのダイヤル プランを割り当てない場合、そのユーザーは、ユーザーのサービス国ダイヤル プランとテナント ダイヤル プランの有効なダイヤル プランを使用してプロビジョニングされます。

Teams のダイヤル プランの継承モデルを次に示します。

![Teams でダイヤル プランを継承する方法。](media/b2744f33-ebbd-4c23-bfba-1747312ab178.png)

次に、考えられる有効なダイヤル プランを示します。

 **サービスの国** テナント スコープダイヤル プランが定義されておらず、テナント ユーザースコープダイヤルプランがプロビジョニングされたユーザーに割り当てられていない場合、ユーザーは、使用場所に関連付けられているサービスの国にマップされた有効なダイヤル プランを受け取ります。

 **テナント グローバル - サービスの国** テナント ユーザー ダイヤル プランが定義されているがユーザーに割り当てられていない場合、プロビジョニングされたユーザーは、マージされたテナント ダイヤル プランと、使用場所に関連付けられたサービス国ダイヤル プランで構成される有効なダイヤル プランを受け取ります。

 **テナント ユーザー - サービスの国** テナント ユーザー ダイヤル プランが定義され、ユーザーに割り当てられている場合、プロビジョニングされたユーザーは、マージされたテナント ユーザー ダイヤル プランと、使用場所に関連付けられたサービス国ダイヤル プランで構成される有効なダイヤル プランを受け取ります。

テナントのダイヤル プランを作成する場合は「[ダイヤル プランを作成および管理する](create-and-manage-dial-plans.md)」をご覧ください。

> [!NOTE]
> ダイヤルされた番号にダイヤル プラン正規化ルールが適用されないシナリオでは、ダイヤルされた文字列は正規化され、"+CC" が付加されます。CC はダイヤルユーザーの使用場所の国コードです。 これは、通話プラン、ダイレクト ルーティング、PSTN 会議ダイヤルアウトのシナリオに適用されます。 さらに、テナント ダイヤル プランの正規化ルールの結果として "+" で始まらない番号が発生した場合、呼び出し元サービスは、テナント ダイヤル プランに基づいて Teams クライアントから受信した番号を正規化しようとします。一致しない場合はリージョン ダイヤル プランで正規化されます。 二重正規化を回避するには、ダイレクト ルーティングのお客様が数値を正規化して + を含め、トランク変換ルールを使用して + を削除することをお勧めします。 

## <a name="planning-for-tenant-dial-plans"></a>テナント ダイヤル プランの計画

カスタム ダイヤル プランを計画するには、次の手順を実行します。

- **Step 1** Decide whether a custom dial plan is needed to enhance the user dialing experience. Typically, the need for one would be to support non-E.164 dialing, such as extensions or abbreviated national dialing.

- **Step 2** Determine whether tenant global or tenant user scoped dial plans are needed, or both. User scoped dial plans are needed if users have different local dialing requirements.

- **Step 3** Identify valid number patterns for each required dial plan. Only the number patterns that are not defined in the service level country dial plans are required.

- **Step 4** Develop an organization-wide scheme for naming dial plans. Adopting a standard naming scheme assures consistency across an organization and makes maintenance and updates easier.


## <a name="creating-your-new-dial-plan"></a>新しいダイヤル プランの作成

ダイヤル プランを新規作成する場合、必要な情報を把握しておく必要があります。

### <a name="name-and-simple-name"></a>名前と簡易名

ユーザー ダイヤル プランの場合は、ダイヤル プランを割り当てるユーザーを識別するわかりやすい名前を指定する必要があります。 ダイヤル プランの単純な名前には、ダイヤル プラン名から派生した文字列が事前に設定されています。 [単純名] フィールドは編集可能で、ダイヤル プラン用のより説明的な名前付け規則を作成することができます。 [単純名] の値は空にすることはできず、一意でなければなりません。 最適な方法は、組織全体の名前付け規則を作成してから、その規則の一貫性をすべてのサイトとユーザーに使用することです。

### <a name="description"></a>説明

地理的な場所または対応するダイヤル プランが適用されるユーザーのグループに関する一般的で認識可能な名前を入力することをお勧めします。

### <a name="external-access-prefix"></a>外部アクセス プレフィックス
<a name="bkexternalprefix"> </a>

ユーザーが外線につなぐために 1 つ以上の追加の先頭数字 (9 など) をダイヤルする必要がある場合は、最大 4 文字 (#、*、0～9) の外部アクセス プレフィックスを指定できます。

> [!NOTE]
> 外部アクセス プレフィックスを指定する場合、プレフィックスを適応させるための正規化ルールを追加で作成する必要はありません。

テナントのダイヤル プランを作成する場合は「[ダイヤル プランを作成および管理する](create-and-manage-dial-plans.md)」をご覧ください。

## <a name="normalization-rules"></a>正規化ルール
<a name="bknormalizationrule"> </a>

Normalization rules define how phone numbers expressed in various formats are to be translated. The same number string may be interpreted and translated differently, depending on the locale from which it is dialed. Normalization rules may be necessary if users need to be able to dial abbreviated internal or external numbers.

1 つ以上の正規化ルールをダイヤル プランに割り当てる必要があります。 正規化ルールは上から下の順に照合されるため、テナント ダイヤル プランにおける順序が重要になります。 たとえば、テナント ダイヤル プランに 10 個の正規化ルールがある場合、ダイヤルされた番号の一致ロジックは 1 番目のルールから試行され、一致がみられない場合は 2 番目、というように順次実行されます。 一致がみられた場合、そのルールが使用され、定義済みのそれ以外のルールとの照合は実行されません。 特定のテナント ダイヤル プランには、最大 50 個の正規化ルールを使用できます。

### <a name="determining-the-required-normalization-rules"></a>必要な正規化ルールの指定

テナント ダイヤル プランは、特定のユーザーのサービス国ダイヤル プランと効果的にマージされるため、必要なテナント ダイヤル プラン正規化ルールを決定するために、サービス国ダイヤル プランの正規化ルールを評価する必要がある可能性があります。 この目的で **Get-CsEffectiveTenantDialPlan** コマンドレットを使用できます。 コマンドレットは入力パラメータとしてユーザー ID を必要とし、ユーザーに適用可能なすべての正規化ルールを返します。

### <a name="creating-normalization-rules"></a>正規化ルールの作成
<a name="createrule"> </a>

正規化規則では、.NET Framework正規表現を使用して、サーバーがダイヤル文字列を E.164 形式に変換するために使用する数値一致パターンを指定します。 正規化ルールは、一致に対する正規表現と、一致が見つかったときに行う変換を指定することで作成できます。 作業が完了したら、テスト番号を入力して、正規化ルールが正常に機能することを確認できます。

.NET Framework の正規表現を使用する場合の詳細については、「[.NET Framework の正規表現](/dotnet/standard/base-types/regular-expressions)」を参照してください。

テナントのダイヤル プランの正規化ルールを作成および管理する場合は「[ダイヤル プランを作成および管理する](create-and-manage-dial-plans.md)」をご覧ください。

> [!NOTE]
> 3pip デバイス (Polycom VVX 601 モデルなど) では、最初のトークンを省略可能にした正規化ルールは現在サポートされていません。 3pip デバイスにオプションを使用して正規化ルールを適用する場合は、1 つではなく 2 つの正規化ルールを作成する必要があります。 たとえば、ルール ^0?(999)$ は、(999)$ (Translation:$1) と ^0(999)$ (Translation:$1) の 2 つのルールに置き換える必要があります。


### <a name="sample-normalization-rules"></a>正規化ルールのサンプル

The following table shows sample normalization rules that are written as .NET Framework regular expressions. The samples are examples only and are not meant to be a prescriptive reference for creating your own normalization rules.

<a name="regularexpression"> </a>
 **.NET Framework正規表現を使用した正規化ルール**

| ルール名<br/> | 説明<br/> | 番号のパターン<br/> | 変換<br/> | 例<br/> |
|:-----|:-----|:-----|:-----|:-----|
|4digitExtension  <br/> |4 桁の内線番号を変換します。  <br/> |^(\\d{4})$  <br/> |+1425555$1  <br/> |0100 は +14255550100 に変換されます  <br/> |
|5digitExtension  <br/> |5 桁の内線番号を変換します。  <br/> |^5(\\d{4})$  <br/> |+1425555$1  <br/> |50100 は +14255550100 に変換されます  <br/> |
|7digitcallingRedmond  <br/> |7 桁の番号をレドモンドの電話番号に変換します。  <br/> |^(\\d{7})$  <br/> |+1425$1  <br/> |5550100 は +14255550100 に変換されます  <br/>|
|RedmondOperator  <br/> |0 をレドモンドのオペレーター呼び出し番号に変換します。  <br/> |^0$  <br/> |+14255550100  <br/> |0 は +14255550100 に変換されます  <br/> |
|RedmondSitePrefix  <br/> |オンネット プレフィックス (6) およびレドモンドのサイト コード (222) 付きの番号を変換します。  <br/> |^6222(\\d{4})$  <br/> |+1425555$1  <br/> |62220100 は +14255550100 に変換されます  <br/> |
|5digitRange  <br/> |3 から 7 を含むその範囲で始まる 5 桁の内線番号を変換します。  <br/> |^([3-7]\\d{4})$  <br/> |+142555$1 <br/> |54567 は +14255554567 に変換されます  <br/> |
|PrefixAdded  <br/> |1 桁目と 3 桁目に制限を付けて、9 桁の番号の前に国番号を追加します。  <br/> |^([2-9]\\d\\d[2-9]\\d{6})$  <br/> |1$1  <br/> |4255554567 は 14255554567 に変換されます  <br/> |
|NoTranslation  <br/> |5 桁と一致しますが、変換は行いません。  <br/> |^(\\d{5})$  <br/> |$1  <br/> |34567 は 34567 に変換されます  <br/> |

 **上に示す正規化ルールに基づくレドモンドのダイヤル プラン**

 次の表に、前の表に示される正規化ルールに基づく、レドモンド、ワシントン、米国のサンプル ダイヤル プランを示します。

| レドモンドのダイヤル プラン<br/> |
|:-----------------------|                                                                                                                      
| 5digitExtension <br/> |                                                                                                                                    
| 7digitcallingRedmond <br/> |
| RedmondSitePrefix <br/> |
| RedmondOperator <br/> |

> [!NOTE]
> 前の表に示す正規化規則の名前にはスペースは含まれませんが、これは選択の問題です。 たとえば、表に最初に示されている名前は、「5 digit extension」と「5-digit Extension」のどちらの形式で記述しても有効になります。

## <a name="related-topics"></a>関連項目

[ダイヤル プランを作成および管理する](create-and-manage-dial-plans.md)

[通話プランで使用されるさまざまな種類の電話番号](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[組織の電話番号を管理する](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[緊急通話の利用条件](emergency-calling-terms-and-conditions.md)

[緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
