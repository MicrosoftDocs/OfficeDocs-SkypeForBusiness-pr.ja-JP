---
title: Skype for Business Online で受信呼び出しをブロックする
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
audience: Admin
ms.reviewer: roykuntz
appliesto:
- Skype for Business
ms.localizationpriority: medium
ms.custom: Learn how to use PowerShell to manage inbound call blocking in Skype for Business Online.
description: 管理者は、Skype for Business Online で受信通話をブロックする方法について説明します。
ms.openlocfilehash: 40b43f669ededf7ac334c25c79b5af09140c075d
ms.sourcegitcommit: c53c22069b1babce7a2364de631057ff501ca1c0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2022
ms.locfileid: "65671653"
---
# <a name="block-inbound-calls"></a>受信通話をブロックする

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

オンライン通話プランSkype for Business、公衆交換電話網 (PSTN) からの着信通話のブロックがサポートされるようになりました。 この機能を使用すると、番号パターンのテナント グローバル リストを定義できるため、テナントへのすべての着信 PSTN コールの発信者 ID をリストと照合して、一致するかどうかを確認できます。 一致した場合、着信は拒否されます。

この受信通話ブロッキング機能は、PSTN から発信された受信通話でのみ機能し、テナント グローバル ベースでのみ機能します。 ユーザーごとには利用できません。

この機能は、直接ルーティングではまだ使用できません。

>[!NOTE]
> ブロックされた呼び出し元は、ブロックされたときに動作が若干異なる場合があります。 この動作は、ブロックされた発信者の通信事業者が、通話を正常に完了できないという通知をどのように処理するかに基づいています。 例としては、ダイヤルされたとおりに通話を完了できないことを案内するキャリアのメッセージや、通話の切断などが含まれます。

## <a name="call-blocking-admin-controls-and-information"></a>通話ブロックの管理コントロールおよび情報

ブロックする番号の管理コントロールは、PowerShell を使用してのみ提供されます。 番号の禁止パターンは、正規の式パターンとして定義されます。 式の順序は重要ではありません。リストで最初に一致したパターンにより、呼び出しがブロックされます。 ブロックされた発信者リストに追加または削除された新しい番号またはパターンは、アクティブになるまでに最大 24 時間かかる場合があります。

## <a name="call-blocking-powershell-commands"></a>ブロッキング PowerShell コマンドの呼び出し

番号パターンは、コマンド、、```Get```、```Set```および```Remove```コマンド```New```を```CsInboundBlockedNumberPattern```使用して管理されます。 これらのコマンドレットを使用して、アクティブ化を切り替える機能などを含む、指定されたパターンを管理できます。
- [Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) それぞれの名前、説明、Enabled (True/False)、およびパターンを含む、テナント リストに追加されたすべてのブロックされた番号パターンのリストを返します。
- [New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) ブロックされた番号パターンをテナント リストに追加します。
- [Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) ブロックされた番号パターンをテナント リストから削除します。
- [Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) テナント リスト内のブロックされた番号パターンの 1 つ以上のパラメーターを変更します。

呼び出しブロック機能全体の表示とアクティブ化は、 ```CsTenantBlockingCallingNumbers``` コマンド ```Get``` と ```Set```.

- [Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) Enabled (True/False) を含むグローバル ブロック番号リストのパラメーターを返します。 機能をオンまたはオフにする以外に、手動で変更できない単一のグローバル テナント ポリシーがあります。
- [Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) グローバル テナントのブロックされたコールを変更して、テナント レベルでオンとオフを切り替えることができます。

### <a name="examples"></a>例

#### <a name="block-a-number"></a>番号をブロックする

この例では、 ```-Enabled``` パラメーターと ```-Description``` パラメーターは省略可能です。

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

新しいパターンを作成すると、既定で有効になっているパターンが追加されます。 Descriptionは、詳細情報を提供するためのオプションのフィールドです。

パターンが追加された理由を簡単に理解できるように、意味のある名前を付けることをお勧めします。 単にスパム番号をブロックする場合は、一致する番号パターンと同じようにルールに名前を付け、必要に応じて説明に追加情報を追加することを検討してください。

パターンは、正規表現 (Regex) を使用して照合されます。
テストと検証を行う前に、レプリケーションの時間を確保してください。

#### <a name="allow-a-number"></a>番号を許可する

この例では、パラメーターが ```-Identity``` 必要です。

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```

ID が不明な場合は、最初にコマンドレットを ```Get-CsInboundBlockedNumberPattern``` 使用して適切なパターンを見つけ、ID をメモします。 次に、コマンドレットを ```Remove-CsTenantBlockedNumberPattern``` 実行し、適切な ID 値を渡します。

テストと検証を行う前に、レプリケーションの時間を確保してください。

#### <a name="view-all-number-patterns"></a>すべての番号パターンを表示

このコマンドレットを実行すると、テナントに入力されたすべてのブロックされた番号のリストが返されます。

```powershell
Get-CsInboundBlockedNumberPattern
```

組み込みの PowerShell フィルタリング機能を使用して、必要に応じて戻り値を解析します。

## <a name="add-number-exceptions"></a>番号の例外を追加する

ブロックされた番号パターンに例外を追加するには、コマンド、```Set``````New``````Get```および```Remove```コマンドを```CsTenantBlockNumberExceptionPattern```使用します。

- [New-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/new-cstenantblockednumberexceptionpattern) テナント リストに番号例外パターンを追加します。
- [Get-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/get-cstenantblockednumberexceptionpattern) テナント リストに追加されたすべての番号例外パターンのリストを返します。
- [Set-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/set-cstenantblockednumberexceptionpattern) 1 つ以上のパラメーターをテナント リストの番号例外パターンに変更します。
- [Remove-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) テナント リストから番号例外パターンを削除します。

### <a name="examples"></a>例

#### <a name="add-a-number-exception"></a>番号の例外を追加する

この例では、新しい番号例外パターンが作成され、既定で有効として追加されます。 パラメーターと```-Description```パラメーターは```-Enabled```省略可能です。

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"
```

#### <a name="view-all-number-exceptions"></a>番号の例外をすべて表示する

この例では、-Identity パラメーターは省略可能です。 パラメーターが ```-Identity``` 指定されていない場合、このコマンドレットは、テナントに入力されたすべての番号例外パターンの一覧を返します。

```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a>番号の例外を変更する

この例では、-Identity パラメーターは必須です。 ```Set-CsTenantBlockedNumberExceptionPattern```このコマンドレットを使用すると、特定の番号パターン ID の 1 つ以上のパラメーターを変更できます。

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string>
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$"
```

#### <a name="remove-a-number-exception"></a>番号の例外を削除する

この例では、パラメーターが ```-Identity``` 必要です。 このコマンドレットは、指定された番号パターンをテナント リストから削除します。  ID が不明な場合は、最初にコマンドレットを ```Get-CsInboundBlockedNumberPattern``` 使用して適切なパターンを見つけ、ID をメモします。 次に、コマンドレットを ```Remove-CsTenantBlockedNumberExceptionPattern``` 実行し、適切な ID 値を渡します。 テストと検証を行う前に、レプリケーションの時間を確保してください。

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a>番号がブロックされているかどうかをテストする

このコマンドレットを ```Test-CsInboundBlockedNumberPattern``` 使用して、テナントで番号がブロックされているかどうかを確認します。

この例では、パラメーターと```-Tenant```パラメーターが```-Phonenumber```必要です。 パラメーターは ```-PhoneNumber``` 、+ や -などの追加の文字を含まない数値文字列にする必要があります。 TRPS では、これは ```-Tenant parameter``` 省略可能です。 結果の ```isNumberBlocked``` パラメーターは、テナントで番号がブロックされている場合は True、ブロックされていない場合は False の値を返します。

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 4255550101
```

|httpResponseCode  |isNumberBlocked   |errorMessage |
|---------|---------|---------|
|200    | True        |         |

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 6045550188
```

|httpResponseCode  |isNumberBlocked   |errorMessage |
|---------|---------|---------|
|200    | False        |         |

## <a name="a-note-about-regex"></a>RegEx に関するメモ

前述のように、発信者をブロックするためのパターン マッチングは、RegEx を使用して行われます。 RegEx パターンの一致を検証するのに役立つ複数のツールがオンラインで利用できます。 RegEx パターンに慣れていない場合は、時間をとって基本を理解することをお勧めします。 期待どおりの結果が得られるようにするには、ブロックされた新しい番号の一致をテナントに追加する前に、パターンの一致を検証するためのツールを使用してください。

## <a name="related-topics"></a>関連項目

- [Windows PowerShellを使用してSkype for Business Online を管理するようにコンピューターを設定する](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
