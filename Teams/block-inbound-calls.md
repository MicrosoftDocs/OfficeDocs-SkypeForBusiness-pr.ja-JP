---
title: Microsoft Teams で受信通話をブロックする
ms.author: v-cichur
author: cichur
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
localization_priority: Normal
ms.custom: Learn how to use PowerShell to manage inbound call blocking.
ms.openlocfilehash: e584e9f0c16ef77424121c37ce87c6d63afb4b92
ms.sourcegitcommit: 17e34d2de3d10f1d04929a695e301127db7014bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689765"
---
# <a name="block-inbound-calls"></a>受信通話をブロックする

Microsoft 通話プラン、直接ルーティング、およびオペレーター Connect公衆交換電話網 (PSTN) からの着信通話のブロックをサポートしています。 この機能を使用すると、管理者はテナント グローバル レベルで番号パターンのリストを定義して、テナントに対するすべての着信 PSTN 呼び出しの発信者番号を一致のリストに対して確認できます。 一致した場合、着信は拒否されます。

この着信呼び出しブロック機能は、PSTN から発信され、テナント グローバル レベルでのみ機能する受信呼び出しでのみ機能します。 個々Teamsユーザーは、このリストを操作できない。 このTeamsでは、個々のユーザーが PSTN 通話をブロックできます。 エンド ユーザーが通話ブロックを実装する方法については、「通話の設定を管理する」を参照[Teams。](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)

>[!NOTE]
> ブロックされた発信者は、ブロックされたときにわずかに異なる動作を経験する可能性があります。 この動作は、ブロックされた発信者の通信事業者が、通話を正常に完了できないという通知をどのように処理するかに基づいています。 例としては、ダイヤルされたとおりに通話を完了できないことを案内するキャリアのメッセージや、通話の切断などが含まれます。

## <a name="call-blocking-admin-controls-and-information"></a>通話ブロックの管理コントロールおよび情報

ブロックする番号の管理コントロールは、PowerShell を使用してのみ提供されます。 番号の禁止パターンは、正規の式パターンとして定義されます。 式の順序は重要ではありません。リストで最初に一致したパターンにより、呼び出しがブロックされます。 ブロックされた発信者リストに追加または削除された新しい番号またはパターンは、アクティブになるまでに最大 24 時間かかる場合があります。

## <a name="call-blocking-powershell-commands"></a>ブロッキング PowerShell コマンドの呼び出し

番号パターンは **、New-** **、Get-** **、Set-** **、Remove-CsInboundBlockedNumberPattern** コマンドレットを使用して管理します。 これらのコマンドレットを使用して、アクティブ化を切り替える機能などを含む、指定されたパターンを管理できます。

- [Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) それぞれの名前、説明、Enabled (True/False)、およびパターンを含む、テナント リストに追加されたすべてのブロックされた番号パターンのリストを返します。
- [New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) ブロックされた番号パターンをテナント リストに追加します。
- [Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) ブロックされた番号パターンをテナント リストから削除します。
- [Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) テナント リスト内のブロックされた番号パターンの 1 つ以上のパラメーターを変更します。

呼び出しブロック機能全体の表示とアクティブ化は **、Get および** **Set-CsTenantBlockingCallingNumbers** コマンドレットを使用して管理されます。

- [Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) は、グローバルブロック番号リストの受信ブロック番号パターンと受信除外番号パターン パラメーターを返します。 このコマンドレットは、ブロックが有効になっている (True または False) も返します。 機能をオンまたはオフにする以外に、手動で変更できない単一のグローバル テナント ポリシーがあります。
- [Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) グローバル テナントのブロックされたコールを変更して、テナント レベルでオンとオフを切り替えることができます。

### <a name="examples"></a>例

#### <a name="block-a-number"></a>番号をブロックする

次の例では、テナント管理者は、番号範囲 1 (312) 555-0000 から 1 (312) 555-9999 へのすべての呼び出しをブロックしたいと考っています。 番号パターンが作成され、+ プレフィックスが付く範囲内の数値と、+ プレフィックスのない範囲内の数値の両方が一致します。 システムが一致する前にこれらの記号を取り除くので、電話番号に記号と () を含める必要はない。  数値パターンを有効にするために **、Enabled パラメーター** を True に設定します。 この特定の番号パターンを無効にするには、 パラメーターを False に設定します。

```PowerShell
New-CsInboundBlockedNumberPattern -Name "BlockRange1" -Enabled $True -Description "Block Contoso" -Pattern "^\+?1312555\d{4}$"
```

次の例では、テナント管理者は、番号 1 (412) 555-1234 からのすべての呼び出しをブロックする必要があります。 数値パターンを有効にするために **、Enabled パラメーター** を True に設定します。

```PowerShell
New-CsInboundBlockedNumberPattern -Name "BlockNumber1" -Enabled $True -Description "Block Fabrikam" -Pattern "^\+?14125551234$"
```

新しいパターンを作成すると、既定で有効になっているパターンが追加されます。 Descriptionは、詳細情報を提供するためのオプションのフィールドです。

パターンが追加された理由を簡単に理解できるように、意味のある名前を付けることをお勧めします。 単にスパム番号をブロックする場合は、一致する番号パターンと同じようにルールに名前を付け、必要に応じて説明に追加情報を追加することを検討してください。

パターンは、正規表現 (Regex) を使用して照合されます。 詳細については、正規表現の使用に関 [するページを参照してください](#using-regex)。

テストと検証を行う前に、レプリケーションの時間を確保してください。 

#### <a name="allow-a-number"></a>番号を許可する

ブロックされた番号パターンを削除することで、番号の呼び出しを許可できます。 次の例では、テナント管理者は、1 (412) 555-1234 が再度呼び出しを行うのを許可します。

```PowerShell
Remove-CsInboundBlockedNumberPattern -Identity "BlockNumber1"
```
 
IDがわからない場合は、**Get-CsInboundBlockedNumberPattern** コマンドレットを使用して、最初に適切なパターンを見つけ、ID をメモします。 次に **、Remove-CsInboundBlockedNumberPattern** コマンドレットを実行し、適切な ID 値を渡します。

テストと検証を行う前に、レプリケーションの時間を確保してください。

#### <a name="view-all-number-patterns"></a>すべての番号パターンを表示

このコマンドレットを実行すると、テナントに入力されたすべてのブロックされた番号のリストが返されます。

```powershell
Get-CsInboundBlockedNumberPattern
```

組み込みの PowerShell フィルタリング機能を使用して、必要に応じて戻り値を解析します。

## <a name="add-number-exceptions"></a>番号の例外を追加する

**New-** **、Get-** **、Set-** **、Remove-CsInboundExemptNumberPattern** コマンドレットを使用して、ブロックされた番号パターンに例外を追加できます。

- [New-CsInboundExemptNumberPattern](/powershell/module/skype/New-CsInboundExemptNumberPattern) は、テナントリストに数例外パターンを追加します。 
- [Get-CsInboundExemptNumberPattern](/powershell/module/skype/Get-CsInboundExemptNumberPattern) は、テナント リストに追加された例外パターンの一覧を返します。
- [Set-CsInboundExemptNumberPattern](/powershell/module/skype/Set-CsInboundExemptNumberPattern) は、テナントリスト内の 1 つ以上のパラメーターを数値例外パターンに変更します。
- [Remove-CsInboundExemptNumberPattern](/powershell/module/skype/Remove-CsInboundExemptNumberPattern) は、テナントリストから数値例外パターンを削除します。

### <a name="examples"></a>例

#### <a name="add-a-number-exception"></a>番号の例外を追加する

次の例では、テナント管理者は、1 (312) 555-8882 と 1 (312) 555-8883 の電話番号を、上記の例でブロックされている範囲内にある場合でも、テナントへの呼び出しを許可したいとします。 これを有効にするには、次のように新しい数値例外パターンが作成されます。

```PowerShell
New-CsInboundExemptNumberPattern  -Identity "AllowContoso1" -Pattern "^\+?1312555888[2|3]$" -Description "Allow Contoso helpdesk" -Enabled $True
```

数値パターンを有効にするために **、Enabled パラメーター** を True に設定します。 この特定の番号パターンを無効にするには、 パラメーターを False に設定します。


#### <a name="view-all-number-exceptions"></a>番号の例外をすべて表示する

この例では、**Identity** パラメーターはオプションです。 **Identity** パラメーターが指定されていない場合、このコマンドレットは、テナントに入力されたすべての番号例外パターンのリストを返します。
 
```powershell
Get-CsInboundExemptNumberPattern -Identity <String>
```
 
```powershell
Get-CsInboundExemptNumberPattern 
```

#### <a name="modify-a-number-exception"></a>番号の例外を変更する

**Set-CsInboundExemptNumberPattern** コマンドレットを使用すると、特定の番号パターン ID の 1 つ以上のパラメーターを変更できます。 この例では、**Identity** パラメーターが必要です。
 
```powershell
Set-CsInboundExemptNumberPattern -Identity <String> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsInboundExemptNumberPattern -Identity "AllowContoso1" -Enabled $False
```

#### <a name="remove-a-number-exception"></a>番号の例外を削除する

**Remove-CsInboundExemptNumberPattern** コマンドレットは、指定された番号パターンをテナントリストから削除します。 この例では、**Identity** パラメーターが必要です。 

ID が知られていない場合は **、Get-CsInboundExemptNumberPattern** コマンドレットを使用して、最初に適切なパターンを見つけて ID をメモします。 次に **、Remove-CsInboundExemptNumberPattern** コマンドレットを実行し、適切な ID 値を渡します。テストと検証を行う前に、レプリケーションの時間を確保してください。  

```powershell
Remove-CsInboundExemptNumberPattern -Identity <String>
```

```powershell
Remove-CsInboundExemptNumberPattern -Identity "AllowContoso1"
```

## <a name="test-whether-a-number-is-blocked"></a>番号がブロックされているかどうかをテストする

**Test-CsInboundBlockedNumberPattern** コマンドレットを使用して、テナントで番号がブロックされているかどうかを確認します。
 
**PhoneNumber パラメーターは** 必須であり、+、- 、() などの追加の文字を含めずに数値文字列である必要があります。 結果の **IsNumberBlocked** パラメーターは、テナントで数値がブロックされている場合は True の値を返します。パラメーターがブロックされていない場合は False を返します。

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

### <a name="examples"></a>例

これらの例では、電話番号 1 (312) 555-8884 が上記のブロック範囲にある必要があるのに対し、電話番号 1 (312) 555-8883 は、上記で作成した例外に基づいて、通話を許可されています。

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

## <a name="using-regex"></a>Regex の使用

ブロッキング呼び出し元のパターン マッチングは、Regex を使用して行われます。 RegEx パターンの一致を検証するのに役立つ複数のツールがオンラインで利用できます。 RegEx パターンに慣れていない場合は、時間をとって基本を理解することをお勧めします。 期待どおりの結果が得られるようにするには、ブロックされた新しい番号の一致をテナントに追加する前に、パターンの一致を検証するためのツールを使用してください。