---
title: Microsoft Teams で受信通話をブロックする
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
audience: Admin
ms.reviewer: roykuntz
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.custom: ''
description: PowerShell を使用して受信通話のブロックを管理する方法について説明します。
ms.openlocfilehash: 01d1fb08d0b0cca4bc0a35ca77109e976d63a1f0
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/20/2022
ms.locfileid: "68614430"
---
# <a name="block-inbound-calls"></a>受信通話をブロックする

Microsoft 通話プラン、ダイレクト ルーティング、オペレーター接続はすべて、公衆交換電話網 (PSTN) からの着信通話のブロックをサポートします。 この機能を使用すると、管理者は、テナントに対するすべての着信 PSTN 通話の発信者 ID を一致のリストと照合できるように、テナント グローバル レベルで番号パターンと例外の一覧を定義できます。 一致した場合、着信は拒否されます。

この受信通話ブロック機能は、PSTN から発信された受信通話でのみ機能し、テナントグローバル レベルでのみ機能します。 個々の Teams ユーザーはこのリストを操作できません。 Teams クライアントでは、個々のユーザーが PSTN 通話をブロックできます。 エンド ユーザーが通話ブロックを実装する方法については、「 [Teams での通話設定の管理](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)」を参照してください。

> [!NOTE]
> ブロックされた発信者は、ブロックされたときにわずかに異なる動作を経験する可能性があります。 この動作は、ブロックされた呼び出し元のキャリアが、通話が正常に完了できないという通知を処理する方法に基づいています。 例としては、ダイヤルされたとおりに通話を完了できないことを案内するキャリアのメッセージや、通話の切断などが含まれます。

現時点では、Teams 管理センターを使用して通話ブロックを管理することはできません。

## <a name="manage-call-blocking-by-using-powershell"></a>PowerShell を使用して通話ブロックを管理する

通話ブロックを管理するには、呼び出しをブロックする 1 つ以上の番号パターンを定義し、番号パターンに対する例外を定義し、通話ブロック機能を有効にする必要があります。

番号の禁止パターンは、正規の式パターンとして定義されます。 式の順序は重要ではありません。リストで一致した最初のパターンでは、呼び出しがブロックされます。 ブロックされた発信者リストに追加または削除された新しい番号またはパターンは、アクティブになるまでに最大 24 時間かかる場合があります。

### <a name="activate-the-call-blocking-feature"></a>通話ブロック機能をアクティブ化する

呼び出しブロック機能を表示してアクティブ化するには、 **Get-** および **Set-CsTenantBlockingCallingNumbers** Teams PowerShell Module コマンドレットを使用します。

- [Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) は、受信ブロック番号パターンと、グローバルブロック番号リストの受信除外番号パターン パラメーターを返します。 このコマンドレットは、ブロックが有効になっているかどうかも返します (True または False)。 

- [Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) を使用すると、グローバル テナントでブロックされた呼び出しをテナント レベルでオンまたはオフにするかどうかを指定できます。

### <a name="manage-block-number-patterns"></a>ブロック番号パターンを管理する

番号パターンを管理するには、 **New-**、 **Get-**、 **Set-**、 **Test-**、 **Remove-CsInboundBlockedNumberPattern** Teams PowerShell Module コマンドレットを使用します。 

- [Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) は、名前、説明、有効 (True/False)、パターンなど、テナントリストに追加されたすべてのブロックされた番号パターンの一覧を返します。

- [New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) ブロックされた番号パターンをテナント リストに追加します。

- [Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) ブロックされた番号パターンをテナント リストから削除します。

- [Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) テナント リスト内のブロックされた番号パターンの 1 つ以上のパラメーターを変更します。

- [Test-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) は、特定の電話番号からの呼び出しがブロックされるかどうかをテストします。


### <a name="examples"></a>例

#### <a name="block-a-number"></a>番号をブロックする

次の例では、テナント管理者は、番号範囲 1 (312) 555-0000 から 1 (312) 555-9999 までのすべての呼び出しをブロックする必要があります。 番号パターンが作成され、+プレフィックスが付いた範囲内の数値と、+ プレフィックスが付いてない範囲内の数字の両方が一致するようにします。 一致する前にこれらの記号が削除されるため、電話番号に記号と () を含める必要はありません。  数値パターンを有効にするには、 **Enabled** パラメーターを True に設定します。 この特定の数値パターンを無効にするには、パラメーターを False に設定します。

```PowerShell
New-CsInboundBlockedNumberPattern -Name "BlockRange1" -Enabled $True -Description "Block Contoso" -Pattern "^\+?1312555\d{4}$"
```

次の例では、テナント管理者は、番号 1 (412) 555- 1234 からのすべての呼び出しをブロックする必要があります。 数値パターンを有効にするには、 **Enabled** パラメーターが True に設定されます。

```PowerShell
New-CsInboundBlockedNumberPattern -Name "BlockNumber1" -Enabled $True -Description "Block Fabrikam" -Pattern "^\+?14125551234$"
```

新しいパターンを作成すると、既定で有効になっているパターンが追加されます。 Descriptionは、詳細情報を提供するためのオプションのフィールドです。

パターンが追加された理由を簡単に理解できるように、意味のある名前を付けることをお勧めします。 スパム番号をブロックするには、ルールに一致する番号パターンと同じ名前を付けることを検討し、必要に応じて説明に追加情報を追加します。

パターンは、正規表現 (Regex) を使用して照合されます。 詳細については、「Regex の [使用](#using-regex)」を参照してください。

テストと検証を行う前に、レプリケーションの時間を確保してください。

#### <a name="allow-a-number"></a>番号を許可する

ブロックされた番号パターンを削除することで、番号の呼び出しを許可できます。 次の例では、テナント管理者は、1 (412) 555- 1234 が再び呼び出しを行うことを許可する必要があります。

```PowerShell
Remove-CsInboundBlockedNumberPattern -Identity "BlockNumber1"
```

IDがわからない場合は、**Get-CsInboundBlockedNumberPattern** コマンドレットを使用して、最初に適切なパターンを見つけ、ID をメモします。 次に、 **Remove-CsInboundBlockedNumberPattern** コマンドレットを実行し、適切な ID 値を渡します。

テストと検証を行う前に、レプリケーションの時間を確保してください。

#### <a name="view-all-number-patterns"></a>すべての番号パターンを表示

次のコマンドレットは、テナントに入力されたすべてのブロックされた番号の一覧を返します。

```powershell
Get-CsInboundBlockedNumberPattern
```

組み込みの PowerShell フィルタリング機能を使用して、必要に応じて戻り値を解析します。

#### <a name="test-whether-a-number-is-blocked"></a>番号がブロックされているかどうかをテストする

テナントで番号がブロックされているかどうかを確認するには、 **Test-CsInboundBlockedNumberPattern** コマンドレットを使用します。

**PhoneNumber** パラメーターは必須であり、+、-、() などの追加の文字を含まない数値文字列にする必要があります。 結果の **IsNumberBlocked** パラメーターは、テナントで番号がブロックされている場合は True の値を返します。パラメーターは、ブロックされていない場合は False を返します。

次の例では、電話番号 1 (312) 555 から 8884 がブロックされていることがわかります。これは、上記のブロック範囲内にあるためです。 電話番号 1 (312) 555-8883 は、以下に作成された除外に基づいて許可されます。

```PowerShell
Test-CsInboundBlockedNumberPattern -PhoneNumber 13125558884

RunspaceId      : 09537e45-6f0c-4001-8b85-a79002707b0c
httpStatusCode  : NoContent
IsNumberBlocked : True
errorMessage    :

Test-CsInboundBlockedNumberPattern -PhoneNumber 13125558883

RunspaceId      : 09537e45-6f0c-4001-8b85-a79002707b0c
httpStatusCode  : NoContent
IsNumberBlocked : False
errorMessage    :
```

### <a name="manage-number-exceptions"></a>番号の例外を管理する

ブロックされた番号パターンに例外を追加するには、 **New-**、 **Get-**、 **Set-**、 **Remove-CsInboundExemptNumberPattern** コマンドレットを使用します。

- [New-CsInboundExemptNumberPattern](/powershell/module/skype/New-CsInboundExemptNumberPattern) は、テナントリストに番号例外パターンを追加します。

- [Get-CsInboundExemptNumberPattern](/powershell/module/skype/Get-CsInboundExemptNumberPattern) は、テナント リストに追加されたすべての番号例外パターンの一覧を返します。

- [Set-CsInboundExemptNumberPattern](/powershell/module/skype/Set-CsInboundExemptNumberPattern) は、1 つ以上のパラメーターをテナント リスト内の番号例外パターンに変更します。

- [Remove-CsInboundExemptNumberPattern](/powershell/module/skype/Remove-CsInboundExemptNumberPattern) は、テナントリストから番号の例外パターンを削除します。

### <a name="examples"></a>例

#### <a name="add-a-number-exception"></a>番号の例外を追加する

次の例では、テナント管理者は、1 (312) 555-8882 と 1 (312) 555-8883 の電話番号をテナントに対して呼び出しを許可する必要があります。この 2 つの電話番号が上記の例でブロックされている範囲内にある場合でも、テナントに対する呼び出しを行います。 これを有効にするには、次のように新しい番号例外パターンが作成されます。

```PowerShell
New-CsInboundExemptNumberPattern  -Identity "AllowContoso1" -Pattern "^\+?1312555888[2|3]$" -Description "Allow Contoso helpdesk" -Enabled $True
```

数値パターンを有効にするには、 **Enabled** パラメーターが True に設定されます。 この特定の数値パターンを無効にするには、パラメーターを False に設定します。

#### <a name="view-all-number-exceptions"></a>番号の例外をすべて表示する

この例では、**Identity** パラメーターはオプションです。 **Identity** パラメーターが指定されていない場合、このコマンドレットは、テナントに入力されたすべての番号例外パターンのリストを返します。

```powershell
Get-CsInboundExemptNumberPattern -Identity <String>
```

```powershell
Get-CsInboundExemptNumberPattern
```

#### <a name="modify-a-number-exception"></a>番号の例外を変更する

**Set-CsInboundExemptNumberPattern** コマンドレットを使用すると、特定の数値パターン ID の 1 つ以上のパラメーターを変更できます。 この例では、**Identity** パラメーターが必要です。

```powershell
Set-CsInboundExemptNumberPattern -Identity <String> -Enabled <bool> -Description <string> -Pattern <string>
```

```powershell
Set-CsInboundExemptNumberPattern -Identity "AllowContoso1" -Enabled $False
```

#### <a name="remove-a-number-exception"></a>番号の例外を削除する

**Remove-CsInboundExemptNumberPattern** コマンドレットは、テナントリストから指定された番号パターンを削除します。 この例では、**Identity** パラメーターが必要です。

ID が不明な場合は、 **Get-CsInboundExemptNumberPattern** コマンドレットを使用して、最初に適切なパターンを見つけて ID をメモします。 次に、 **Remove-CsInboundExemptNumberPattern** コマンドレットを実行し、適切な ID 値を渡します。 テストと検証を行う前に、レプリケーションの時間を確保してください。

```powershell
Remove-CsInboundExemptNumberPattern -Identity <String>
```

```powershell
Remove-CsInboundExemptNumberPattern -Identity "AllowContoso1"
```

## <a name="using-regex"></a>Regex の使用

呼び出し元をブロックするためのパターン マッチングは、Regex を使用して行われます。 RegEx パターンの一致を検証するのに役立つ複数のツールがオンラインで利用できます。 RegEx パターンに慣れていない場合は、時間をとって基本を理解することをお勧めします。 期待どおりの結果が得られるようにするには、ブロックされた新しい番号の一致をテナントに追加する前に、パターンの一致を検証するためのツールを使用してください。
