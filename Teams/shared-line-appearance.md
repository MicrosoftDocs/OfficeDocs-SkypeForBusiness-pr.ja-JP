---
title: Microsoft Teams での共有回線の外観
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 02/19/2019
ms.reviewer: jenstr
ms.topic: conceptual
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- ms.teamsadmincenter.users.voice.calldelegation.tooltip
- seo-marvel-apr2020
description: Microsoft Teams の線の外観を共有する機能について説明します。
ms.openlocfilehash: 7e3259e948e5a3443d5959eef693416ca3d754ca
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/20/2022
ms.locfileid: "68614099"
---
# <a name="shared-line-appearance-in-microsoft-teams"></a>Microsoft Teams での共有回線の外観

共有行の外観を使用すると、ユーザーは代理で呼び出しに応答または処理するデリゲートを選択できます。 この機能は、ユーザーの通話を定期的に処理する管理アシスタントがいる場合に役立ちます。 共有行の外観のコンテキストでは、マネージャーは代理人に代わって通話の発信または受信を承認するユーザーです。 代理人は、委任者に代わって呼び出しを行ったり受信したりできます。

> [!IMPORTANT]
> この機能を使用できるのは、Teams のみの展開モードだけです。 Teams 展開モードの詳細については、「[Microsoft Teams と Skype for Business の共存および相互運用性について理解する](teams-and-skypeforbusiness-coexistence-and-interoperability.md)」を参照してください。

## <a name="license-required"></a>必要なライセンス

管理者と代理人の両方に、PSTN 接続を持つ電話システム ライセンス (通話プラン、オペレーター接続、またはダイレクト ルーティング) が必要です。 共有回線エクスペリエンスは委任の一部であり、電話システムに含まれています。 ライセンスの詳細については、 [Microsoft Teams サービスの説明を](/office365/servicedescriptions/teams-service-description)参照してください。

## <a name="shared-line-appearance-feature-availability"></a>共有回線の外観機能の可用性

共有回線の外観は現在、次のアプリとデバイスでサポートされています。

| 機能 | Teams デスクトップ | Teams Mac アプリ | Teams Web アプリ (Edge) |Teams モバイル iOS/Android アプリ | Teams IP 電話 |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|
| 委任を設定する | はい | Yes | Yes | いいえ | Yes |
| 別の人に代わって電話を受ける | はい | Yes | Yes | Yes | はい |
| 別の人に代わって電話番号に電話する | はい | Yes | Yes | Yes | Yes |
| 別のユーザーに代わって Teams ユーザーに電話する | はい | Yes | Yes | はい | Yes |
| 共有行のデリゲート ビューを表示する | Yes | Yes | Yes | いいえ | Yes |
| マネージャーの通話アクティビティのデリゲート ビューを表示する | Yes | Yes | Yes | いいえ | Yes |
| 委任のマネージャー ビューを参照してください | はい | Yes | Yes | いいえ | Yes |
| 代理人またはマネージャーは、保留または再開できます | はい | Yes | はい | いいえ | Yes |

## <a name="limitations"></a>制限事項

管理者は最大 25 人の代理人を追加でき、代理人は最大 25 人の管理者を持つことができます。 テナントで作成できる委任関係の数に制限はありません。 
 
委任者と代理人が同じ地理的な場所にない場合、PSTN プロバイダーは、委任された通話の別の地理的な場所から発信者 ID を表示できるようにする必要があります。 

循環委任の構成は許可されません。 委任されたユーザーの間に委任がある場合は、最初の委任ではなく、委任のみを表示できます。

## <a name="enable-delegation-and-shared-line-appearance"></a>委任と共有行の外観を有効にする

**TeamsCallingPolicy AllowDelegation 設定を** 使用して委任を有効にします。 Teams 管理センターまたは Teamms PowerShell を使用できます。 

有効にすると、エンド ユーザーは Teams で委任関係を直接構成できます。 

> [!IMPORTANT]
> ユーザーの委任を無効にする場合は、不適切な通話ルーティングを回避するために、Teams 管理センターでそのユーザーの委任関係をクリーンアップする必要もあります。

## <a name="use-teams-admin-center"></a>Teams 管理センターを使用する

Teams 管理センターを使用して委任と共有行の外観を構成するには、「 [ユーザーの通話設定を構成する](/MicrosoftTeams/user-call-settings)」を参照してください。

## <a name="use-powershell"></a>PowerShell を使用する

Teams PowerShell を使用して委任と共有行の外観を構成するには、次のコマンドレットを使用します。

- [New-CsUserCallingDelegate](/powershell/module/teams/new-csusercallingdelegate)

- [Set-CsUserCallingDelegate](/powershell/module/teams/set-csusercallingdelegate)

- [Remove-CsUserCallingDelegate](/powershell/module/teams/remove-csusercallingdelegate)

### <a name="examples"></a>例

次の例では、user2@contoso.com は、ユーザー 1 に代わって呼び出しを行い、受信したり、他のデリゲートの設定を変更したりするためのアクセス許可を持つ user1@contoso.com のデリゲートとして追加されます。

```powershell
New-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com -MakeCalls $true -ReceiveCalls $true -ManageSettings $true
```

次の例では、代理 user2@contoso.com は、user1 の代わりに呼び出しを行うことはできません。

```powershell
Set-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com -MakeCalls $false
```

次の例では、user1@contoso.com のデリゲートとして user2@contoso.com が削除されます。

```powershell
Remove-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com
```
 
## <a name="more-information"></a>詳細情報

[電話回線を代理人と共有する](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)

[ポリシーを呼び出す Teams](/MicrosoftTeams/teams-calling-policy)

[New-CsTeamsCallingPolicy](/powershell/module/skype/new-csteamscallingpolicy)

[Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)
