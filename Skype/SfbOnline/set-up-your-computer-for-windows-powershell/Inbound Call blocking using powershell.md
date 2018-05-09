---
title: 着信通話の Skype のビジネスの Onlin の Powershell の使用をブロック
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 05/07/2018
ms.topic: article
ms.assetid: ''
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: PowerShell を使用すると、着信呼び出しのビジネス オンラインの Skype のブロックを管理できます。
ms.openlocfilehash: 10aa92233f2a804edffef8bf6d5b8e5dd7746b06
ms.sourcegitcommit: 7ec95ea34422e635661f3659bbc43a7a3484ff99
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/09/2018
---
# <a name="inbound-pstn-call-blocking-for-calling-plans"></a>着信 PSTN 通話の通話プランのブロック

Skype ビジネス オンラインを呼び出すことを計画するのでは、公衆交換電話網 (PSTN) からの着信呼び出しをブロックする機能をサポートしています。 この機能により、テナントの番号のパターンを定義するテナントのすべての着信 PSTN 通話の発信者番号は、一致をリストでチェックできるようにグローバル リスト。 一致する場合は、着信呼び出しは拒否されます。 

この着信呼び出しのブロック機能は PSTN からの着信呼び出しに対してだけ機能テナント グローバル単位でのみ機能し、ユーザー単位では利用できません。

この機能はまだ直接ルーティング可能ではありません。

>[メモ]着信禁止一覧は、ブロックされたときに、わずかに異なる動作にすることがあります。 動作は、ブロックされている呼び出し元のキャリアが正常に完了するのには、呼び出しは許可されていない通知を処理する方法に基づきます。 例としては、ダイヤル呼び出しを完了できませんを示すメッセージがキャリアを含めることが、または単に呼び出しを削除します。

## <a name="call-blocking-admin-controls-and-information"></a>管理コントロールと情報のブロックの呼び出し
PowerShell を使用してのみ、ブロック番号の管理コントロールが提供されます。 番号のブロック パターンは、正規表現のパターンとして定義されます。 式の順序は重要な – がリストに一致する最初のパターンと、呼び出しがブロックされていること。 新しい番号またはパターンが追加または削除でブロックされている呼び出し元のリストは最大で 24 時間にアクティブになるパターンをかかることがあります。

## <a name="call-blocking-powershell-commands"></a>通話の PowerShell コマンドをブロック

*InboundBlockedNumberPattern*番号のパターンは、**新規**、**取得**、**設定**、および**削除**は、 *CsInboundBlockedNumberPattern*コマンドを使用して管理されます。  

指定したパターンのアクティブ化を切り替える機能など、これらのコマンドレットを使用して特定のパターンを管理できます。
- *Get CsInboundBlockedNumberPattern*それぞれの名前、説明、有効 (True または False)、およびパターンを含むテナント リストに追加されたすべてのブロック番号パターンの一覧を返します。
- *新しい-CsInboundBlockedNumberPattern*テナントの一覧には、ブロック番号のパターンを追加します。
- *削除 CsInboundBlockedNumberPattern*テナント リストからブロックされている番号のパターンを削除します。
- *セット CsInboundBlockedNumberPattern*テナント リストでブロックされている番号のパターンの 1 つまたは複数のパラメーターを変更します。
- *TenantBlockedCallingNumbers*表示とすべての呼び出しのブロック機能のアクティブ化は、CsTenantBlockingCallingNumbers のコマンドを取得および設定を使用して管理されます。 
- *Get CsTenantBlockedCallingNumbers*有効 (True または False) を含むグローバルのブロック番号リストのパラメーターを返します。 完全にオン/オフ機能を有効にする以外の手動で変更できない 1 つのグローバル テナント ポリシーがあります。
- *セット CsTenantBlockedCallingNumbers*テナントのレベルでオン/オフするにはグローバルのテナントがブロックされている呼び出しを変更することができます。

### <a name="examples"></a>例
#### <a name="blocking-a-number"></a>いくつかのブロック

この例で、有効になっているし、パラメーターの説明は省略可能。

`New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”`

 新しいパターンが既定で追加を有効にするパターンと説明は、常に作成して、詳細情報を提供する省略可能なフィールドです。 

パターンが追加された理由を簡単に理解できるわかりやすい名前を提供することをお勧めします。 スパムをブロックするだけの場合は番号、同じルールに名前を付けると見なされますは番号のパターンと一致すると必要に応じて、[説明] に情報を追加します。

パターンは、正規表現 (regex) を使用して照合されます。 テストおよび検証する前にレプリケーションに要する時間を許可します。

#### <a name="allowing-a-number"></a>数値を許可します。

この例では、identity パラメーター (is?) が必要な場合。`Remove-CsInboundBlockedNumberPattern -Identity “<identity>”`
 
Id が不明な場合は、まず適切なパターンを検索し、Id に注意してください*取得 CsInb undBlockedNumberPattern*コマンドレットを使用します。 *削除する*コマンドレットを実行し、適切な Id 値を渡します。

テストおよび検証する前にレプリケーションに要する時間を許可します。
#### <a name="view-all-number-patterns"></a>すべての番号のパターンを表示します。
このコマンドレットを実行すると、テナントのブロック、入力したすべてのリストの番号が返されます。`Get-CsInboundBlockedNumberPattern`

必要に応じて戻り値を解析するのに能力をフィルタ リングする組み込み PowerShell を使用します。

#### <a name="a-note-on-regex"></a>正規表現に関する注意
前述のように、呼び出し元をブロックするために一致するパターンは、正規表現 (regex) を使用して行われます。 複数のツール利用可能なオンラインに正規表現パターン一致の検証を支援します。 正規表現パターンに慣れていない場合は、基本を理解し、期待どおりの結果を取得するかどうかを確認するツールを使用して、テナント ブロック番号の新しいアイテムを追加する前に、パターン マッチを検証するために時間がかかることをお勧めします。 

## <a name="related-topics"></a>このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。
[Windows PowerShell を使用してビジネスのオンライン管理のための skype には、コンピューターを設定します](set-up-your-computer-for-windows-powershell.md)