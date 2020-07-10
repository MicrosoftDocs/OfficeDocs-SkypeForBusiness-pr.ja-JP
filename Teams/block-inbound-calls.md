---
title: Microsoft Teams で着信通話をブロックする
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 3bb1222f0662228e5c0de7b2253cbac162571b1e
ms.sourcegitcommit: a36514c7c8ea47bde4edb09c11ff99061b1f74c0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2020
ms.locfileid: "45094683"
---
# <a name="block-inbound-calls"></a>着信通話をブロックする

電話システムによるダイレクトルーティングと通話プランでは、公衆交換電話網 (PSTN) からの着信通話のブロックがサポートされています。 この機能によって、テナントへのすべての着信 PSTN 呼び出しの発信者番号が一致のリストに対してチェックされるように、番号パターンのテナントグローバルリストを定義できます。 一致した場合は、着信通話は拒否されます。

この着信通話ブロック機能は、PSTN から発信された着信通話でのみ機能し、テナント全体でのみ機能します。 ユーザーごとには使用できません。  

>[!NOTE]
> ブロックされた呼び出し元は、ブロックされている場合、動作がわずかに異なる場合があります。 この動作は、ブロックされた発信者のキャリアが、通話が正常に完了することができないという通知を処理する方法に基づいています。 この例には、通話を発信できない、または単に通話を発信することができないことを示すキャリアメッセージが含まれている場合があります。

## <a name="call-blocking-admin-controls-and-information"></a>通話のブロック管理コントロールと情報

ブロッキング番号の管理コントロールは、PowerShell のみを使って提供されます。 数値ブロックパターンは、正規表現パターンとして定義されます。 式の順序は重要ではありません。リスト内で一致した最初のパターンが、ブロックされている呼び出しになります。 ブロックされた発信者リストで追加または削除された新しい番号またはパターンは、そのパターンがアクティブになるまで最大24時間かかることがあります。

## <a name="call-blocking-powershell-commands"></a>通話ブロック PowerShell コマンド

数値パターンを管理するには、 **New**、 **Get**、 **Set**、 **Remove**の  - **CsInboundBlockedNumberPattern**コマンドレットを使用します。 特定のパターンのアクティブ化を切り替える機能など、これらのコマンドレットを使用して、特定のパターンを管理できます。

- [Get-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/get-csinboundblockednumberpattern)は、[名前]、[説明]、[有効 (True/False)]、[パターン] など、テナントリストに追加されたすべてのブロックされた番号のパターンのリストを返します。
- [[新規]-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/new-csinboundblockednumberpattern)は、ブロックされた番号のパターンをテナントリストに追加します。
- [CsInboundBlockedNumberPattern を削除](https://docs.microsoft.com/powershell/module/skype/remove-csinboundblockednumberpattern)すると、ブロックされた番号パターンがテナントリストから削除されます。
- [Set-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/set-csinboundblockednumberpattern)は、テナントリストでブロックされた番号パターンの1つ以上のパラメーターを変更します。

通話ブロック機能全体を表示してアクティブ化するには、 **Get**、 **Set**  - **CsTenantBlockingCallingNumbers**コマンドレットを使用します。

- [CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockedcallingnumbers)は、有効 (True/False) を含むグローバルブロック番号リストのパラメーターを返します。 グローバルテナントポリシーは1つしかありません。このポリシーは、この機能をオンまたはオフにして手動で変更することはできません。
- [Set-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockedcallingnumbers)を使用すると、テナントレベルでグローバルテナントのブロックされた通話のオン/オフを切り替えることができます。

### <a name="examples"></a>例

#### <a name="block-a-number"></a>番号をブロックする

この例では、 **Enabled**パラメーターと**Description**パラメーターは省略可能です。

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

新しいパターンを作成すると、既定では有効としてパターンが追加されます。 説明は、詳細情報を提供するオプションのフィールドです。

パターンが追加された理由を簡単に理解できるように、わかりやすい名前を指定することをお勧めします。 スパム番号をブロックするだけの場合は、一致している番号パターンと同じルールに名前を付け、必要に応じて、説明に追加情報を追加することを検討してください。

パターンは正規表現 (Regex) を使って照合されます。 テストと検証を行う前に、レプリケーションの時間を確保します。

#### <a name="allow-a-number"></a>番号を許可する

この例では、 **Identity**パラメーターが必要です。

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```
 
Id がわからない場合は、 **CsInboundBlockedNumberPattern**コマンドレットを使用して、最初に適切なパターンを特定し、id をメモします。 次に、 **CsTenantBlockedNumberPattern**コマンドレットを実行し、適切な id 値を渡します。

テストと検証を行う前に、レプリケーションの時間を確保します。

#### <a name="view-all-number-patterns"></a>すべての数値パターンを表示する

このコマンドレットを実行すると、テナントで入力されたすべてのブロックされた番号の一覧が返されます。

```powershell
Get-CsInboundBlockedNumberPattern
```

組み込みの PowerShell フィルター機能を使って、必要に応じて戻り値を解析します。

## <a name="add-number-exceptions"></a>番号の例外を追加する

ブロックされた番号のパターンに例外を追加するには、 **New**、 **Get**、 **Set**、 **Remove**の  - **CsTenantBlockNumberExceptionPattern**コマンドレットを使用します。

- [CsTenantBlockedNumberExceptionPattern によっ](https://docs.microsoft.com/powershell/module/skype/new-cstenantblockednumberexceptionpattern)て、テナントリストに番号の例外パターンが追加されます。 
- [Get-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockednumberexceptionpattern)は、テナントリストに追加されたすべての数の例外パターンの一覧を返します。
- [Set-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockednumberexceptionpattern)は、テナントリストの1つ以上のパラメーターを数値の例外パターンに変更します。
- [CsTenantBlockedNumberExceptionPattern を削除](https://docs.microsoft.com/powershell/module/skype/remove-cstenantblockednumberexceptionpattern)すると、テナントリストから番号例外パターンが削除されます。

### <a name="examples"></a>例

#### <a name="add-a-number-exception"></a>数値の例外を追加する

この例では、新しい番号の例外パターンが作成され、既定で [有効] としてパターンが追加されます。 **Enabled**パラメーターと**Description**パラメーターは省略可能です。

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"  
```

#### <a name="view-all-number-exceptions"></a>すべての数値を表示する例外

この例では、 **Identity**パラメーターは省略可能です。 **Identity**パラメーターが指定されていない場合、このコマンドレットは、テナントで入力されたすべての数の例外パターンの一覧を返します。
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a>数値の例外を変更する

この例では、 **Identity**パラメーターは必須です。 **CsTenantBlockedNumberExceptionPattern**コマンドレットを使用すると、特定の番号パターン id の1つ以上のパラメーターを変更できます。
 
```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$" 
```

#### <a name="remove-a-number-exception"></a>数値の例外を削除する

この例では、 **Identity**パラメーターが必要です。 このコマンドレットは、指定された番号パターンをテナントリストから削除します。  Id がわからない場合は、 **CsInboundBlockedNumberPattern**コマンドレットを使用して、最初に適切なパターンを特定し、id をメモします。 次に、 **CsTenantBlockedNumberExceptionPattern**コマンドレットを実行し、適切な id 値を渡します。テストと検証を行う前に、レプリケーションの時間を確保します。  

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a>数値がブロックされているかどうかをテストする

**CsInboundBlockedNumberPattern**コマンドレットを使用して、テナントで番号がブロックされているかどうかを確認します。
 
この例では、 **PhoneNumber**パラメーターと**テナント**パラメーターが必要です。 **PhoneNumber**パラメーターは、+ や-などの追加文字を含まない数字文字列である必要があります。 TRPS では、**テナントパラメーター**は省略可能です。 結果として返される**Isnumber ブロック**パラメーターは、テナントで番号がブロックされている場合は True を返し、ブロックされていない場合は False を返します。

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 4255550101
```

|httpResponseCode  |Isnumber ブロック   |errorMessage |
|---------|---------|---------|
|200    | True        |         |

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 6045550188
```

|httpResponseCode  |Isnumber ブロック   |errorMessage |
|---------|---------|---------|
|200    | False        |         |

## <a name="a-note-about-regex"></a>Regex についての注意

前に説明したように、ブロックする呼び出し元のパターンマッチングは Regex を使って行われます。 複数のツールをオンラインで使用して、正規表現のパターン一致を検証できます。 Regex のパターンに慣れていない場合は、基本的な作業を理解するために少し時間がかかることをお勧めします。 期待どおりの結果が得られるようにするには、ブロックされた新しい番号の一致をテナントに追加する前に、ツールを使用してパターンの一致を検証します。
