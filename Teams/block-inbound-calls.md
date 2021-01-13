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
ms.openlocfilehash: ca2f8de5962572a08ab2a0ae7127446d14334c83
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799907"
---
# <a name="block-inbound-calls"></a>受信通話をブロックする

電話システムの直接ルーティングおよび通話プランは、公衆交換電話網 (PSTN) からの受信通話のブロックをサポートします。 この機能を使用すると、番号パターンのテナント グローバル リストを定義できるため、テナントへのすべての着信 PSTN コールの発信者 ID をリストと照合して、一致するかどうかを確認できます。 一致した場合、着信は拒否されます。

この受信通話ブロッキング機能は、PSTN から発信された受信通話でのみ機能し、テナント グローバル ベースでのみ機能します。 ユーザーごとには利用できません。  

>[!NOTE]
> ブロックされた発信者は、ブロックされたときにわずかに異なる動作を経験する可能性があります。 この動作は、ブロックされた発信者の通信事業者が、通話を正常に完了できないという通知をどのように処理するかに基づいています。 例としては、ダイヤルされたとおりに通話を完了できないことを案内するキャリアのメッセージや、通話の切断などが含まれます。

## <a name="call-blocking-admin-controls-and-information"></a>通話ブロックの管理コントロールおよび情報

ブロックする番号の管理コントロールは、PowerShell を使用してのみ提供されます。 番号の禁止パターンは、正規の式パターンとして定義されます。 式の順序は重要ではありません。リストで最初に一致したパターンにより、呼び出しがブロックされます。 ブロックされた発信者リストに追加または削除された新しい番号またはパターンは、アクティブになるまでに最大 24 時間かかる場合があります。

## <a name="call-blocking-powershell-commands"></a>ブロッキング PowerShell コマンドの呼び出し

**New**、**Get**、**Set**、**Remove** -**CsInboundBlockedNumberPattern** コマンドレットを使用して、番号パターンを管理します。 これらのコマンドレットを使用して、アクティブ化を切り替える機能などを含む、指定されたパターンを管理できます。

- [Get-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/get-csinboundblockednumberpattern) それぞれの名前、説明、Enabled (True/False)、およびパターンを含む、テナント リストに追加されたすべてのブロックされた番号パターンのリストを返します。
- [New-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/new-csinboundblockednumberpattern) ブロックされた番号パターンをテナント リストに追加します。
- [Remove-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/remove-csinboundblockednumberpattern) ブロックされた番号パターンをテナント リストから削除します。
- [Set-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/set-csinboundblockednumberpattern) テナント リスト内のブロックされた番号パターンの 1 つ以上のパラメーターを変更します。

着信ブロック機能全体の表示およびアクティブ化は、**Get**、**Set** -**CsTenantBlockingCallingNumbers** コマンドレットを通して管理されます。

- [Get-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockedcallingnumbers) Enabled (True/False) を含むグローバル ブロック番号リストのパラメーターを返します。 機能をオンまたはオフにする以外に、手動で変更できない単一のグローバル テナント ポリシーがあります。
- [Set-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockedcallingnumbers) グローバル テナントのブロックされたコールを変更して、テナント レベルでオンとオフを切り替えることができます。

### <a name="examples"></a>例

#### <a name="block-a-number"></a>番号をブロックする

この例では、**Enabled** パラメーターと **Description** パラメーターはオプションです。

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

新しいパターンを作成すると、既定で有効になっているパターンが追加されます。 Descriptionは、詳細情報を提供するためのオプションのフィールドです。

パターンが追加された理由を簡単に理解できるように、意味のある名前を付けることをお勧めします。 単にスパム番号をブロックする場合は、一致する番号パターンと同じようにルールに名前を付け、必要に応じて説明に追加情報を追加することを検討してください。

パターンは、正規表現 (Regex) を使用して照合されます。 テストと検証を行う前に、レプリケーションの時間を確保してください。

#### <a name="allow-a-number"></a>番号を許可する

この例では、**Identity** パラメーターが必要です。

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```
 
IDがわからない場合は、**Get-CsInboundBlockedNumberPattern** コマンドレットを使用して、最初に適切なパターンを見つけ、ID をメモします。 次に、**Remove-CsTenantBlockedNumberPattern** コマンドレットを実行し、適切な ID 値を渡します。

テストと検証を行う前に、レプリケーションの時間を確保してください。

#### <a name="view-all-number-patterns"></a>すべての番号パターンを表示

このコマンドレットを実行すると、テナントに入力されたすべてのブロックされた番号のリストが返されます。

```powershell
Get-CsInboundBlockedNumberPattern
```

組み込みの PowerShell フィルタリング機能を使用して、必要に応じて戻り値を解析します。

## <a name="add-number-exceptions"></a>番号の例外を追加する

**New**、**Ge** t、**Set**、**Remove** -**CsTenantBlockNumberExceptionPattern** コマンドレットを使用して、ブロックされた番号パターンに例外を追加できます。

- [New-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/new-cstenantblockednumberexceptionpattern) テナント リストに番号例外パターンを追加します。 
- [Get-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockednumberexceptionpattern) テナント リストに追加されたすべての番号例外パターンのリストを返します。
- [Set-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockednumberexceptionpattern) 1 つ以上のパラメーターをテナント リストの番号例外パターンに変更します。
- [Remove-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) テナント リストから番号例外パターンを削除します。

### <a name="examples"></a>例

#### <a name="add-a-number-exception"></a>番号の例外を追加する

この例では、新しい番号例外パターンが作成され、既定で有効として追加されます。 **Enabled** パラメーターと **Description** パラメーターはオプションです。

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"  
```

#### <a name="view-all-number-exceptions"></a>番号の例外をすべて表示する

この例では、**Identity** パラメーターはオプションです。 **Identity** パラメーターが指定されていない場合、このコマンドレットは、テナントに入力されたすべての番号例外パターンのリストを返します。
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a>番号の例外を変更する

この例では、**Identity** パラメーターは必須です。 **Set-CsTenantBlockedNumberExceptionPattern** コマンドレットを使用すると、特定の番号パターンIDの1つ以上のパラメーターを変更できます。
 
```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$" 
```

#### <a name="remove-a-number-exception"></a>番号の例外を削除する

この例では、**Identity** パラメーターが必要です。 このコマンドレットは、指定された番号パターンをテナント リストから削除します。  IDがわからない場合は、**Get-CsInboundBlockedNumberPattern** コマンドレットを使用して、最初に適切なパターンを見つけ、ID をメモします。 次に、**Remove-CsTenantBlockedNumberExceptionPattern** コマンドレットを実行し、適切な ID 値を渡します。テストと検証を行う前に、レプリケーションの時間を確保してください。  

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a>番号がブロックされているかどうかをテストする

**Test-CsInboundBlockedNumberPattern** コマンドレットを使用して、テナントで番号がブロックされているかどうかを確認します。
 
この例では、**PhoneNumber** パラメーターと **Tenant** パラメーターが必要です。 **PhoneNumber** パラメーターは、+ や - などの追加文字を含まない数値文字列である必要があります。 TRPSでは、**Tenant パラメーター** はオプションです。 結果の **isNumberBlocked** パラメーターは、テナントで番号がブロックされている場合は True の値を返し、ブロックされていない場合は False の値を返します。

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
