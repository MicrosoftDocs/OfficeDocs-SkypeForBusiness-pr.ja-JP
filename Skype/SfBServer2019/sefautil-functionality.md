---
title: Skype for Business Server 2019 での PowerShell での SEFAUtil 機能の使用に関するサポート
ms.reviewer: rogupta
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.date: 07/22/2019
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: '概要: 累積的な更新プログラム1をインストールした後、PowerShell を使用して Skype for Business Server 2019 の SEFAUtil 機能を入手する方法について説明します。'
ms.openlocfilehash: 6e0f7fc8e4bbb25564faa8107dec81ae3887b360
ms.sourcegitcommit: b914c044c43ff8147f35eea684fec1de01a7bcd2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2019
ms.locfileid: "36464552"
---
# <a name="using-sefautil-functionality-via-powershell-in-skype-for-business-server-2019"></a>Skype for Business Server 2019 の PowerShell 経由で SEFAUtil 機能を使用する

SEFAUtil (セカンダリ拡張機能のアクティブ化) では、skype for business Server の管理者およびヘルプデスクエージェントは、Skype for Business Server ユーザーの代わりに、代理人の呼び出し、着信の転送、グループ通話のピックアップの設定を構成できます。 また、管理者は特定のユーザー向けに公開されているコール ルーティング設定のクエリを実行できます。 Skype for Business Server 2019 年7月の累積更新プログラムをインストールした後、SEFAUtil を使用してのみ現在管理できる次の機能は、PowerShell を使用して管理することもできます。

- [着信の転送設定](#call-forwarding-settings)
- [委任の設定](#delegation-settings)
- [チームメンバーと関連する設定](#team-members-and-related-settings)

## <a name="call-forwarding-settings"></a>着信の転送設定

管理者は、PowerShell の次のコマンドレットを使用して、着信の転送設定を変更できます。

- `Get-CsUserForwardingSettings -Identity <UserIdParameter>`

このコマンドレットは、指定したユーザーの着信の転送設定をオブジェクトとして返し、画面でも同じように表示します。

- `Set-CsUserForwardingSettings -Identity <UserIdParameter> [Param1 <Value>] [Param2 <Value>]…`

このコマンドレットは、指定したユーザーの着信の転送設定を変更します。 このコマンドレットは、指定したユーザーの着信の転送設定をオブジェクトとして返し、正常に完了した場合は画面にも表示します。 エラーが発生した場合は、適切なエラーメッセージが表示されます。

- `Set-CsUserForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToVoicemail] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

このコマンドレットでは、ユーザーの着信の転送設定を無効にします (ここでは、2つの異なるパラメーターの例を示します)。

- `Set-CsUserForwardingSettings [-Identity] <UserIdParameter> -EnableForwarding <String> [-Delegates <PSListModifier>] [-DelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

このコマンドレットは、ユーザーの着信の転送設定を変更します。

- `Set-CsUserForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToVoicemail]  [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>] [-Team <PSListModifier>] [-TeamDelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>]  [-Team <PSListModifier>]  [-TeamDelegateRingWaitTime <TimeSpan>]  [-SettingsActiveWorkHours]`

このコマンドレットは、SimulRing の設定を変更します (1 つはボイスメールに不在着信し、2番目のパラメーターには応答しません)。

## <a name="delegation-settings"></a>委任の設定

管理者は、PowerShell の次のコマンドレットを使用して、委任設定を変更できます。

- `Get-CsuserDelegates -Identity <UserIdParameter>`

このコマンドレットは、デリゲートリストのオブジェクトを返し、指定したユーザーのデリゲートリストを、成功した場合に表示します。 エラーが発生した場合は、適切なエラーメッセージが表示されます。

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates <PSListModifier>]`

このコマンドレットは、指定したユーザーの委任設定を変更し、デリゲートリストのオブジェクトを返し、成功した場合は代理人のリストを表示します。 エラーが発生した場合は、適切なエラーメッセージが表示されます。 

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{add=[list]}] [-Delegates @{remove=[list]}]`

このコマンドレットはデリゲートを追加または削除します。

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{replace=[list]}]`

このコマンドレットは、特定のデリゲートに委任リストを設定します。

## <a name="team-members-and-related-settings"></a>チームメンバーと関連する設定

管理者は、PowerShell の次のコマンドレットを使用して、チームメンバーと関連する設定を変更できます。

- `Get-CsUserTeamMembers -Identity <UserIdParameter>`

このコマンドレットは、チームメンバーの一覧が含まれているオブジェクトを返し、成功した場合はそのオブジェクトを画面上に表示します。 エラーが発生した場合は、適切なエラーメッセージが表示されます。

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team <PSListModifier>]`

このコマンドレットは、指定したユーザーのチームメンバーリストを変更し、成功した場合は、チームメンバーリストを含むオブジェクトを返し、そのオブジェクトを画面に表示します。 エラーが発生した場合は、適切なエラーメッセージが表示されます。

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{add=[list]}] [-Team @{remove=[list]}]`

このコマンドレットは、チームメンバーを追加または削除します。

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{replace=[list]}]`

このコマンドレットは、チームリストを特定のメンバーに設定します。

## <a name="more-information"></a>詳細情報

オンプレミス展開の場合、この機能で導入されたコマンドレットは、次のように指定されたアクセスレベルごとに、次のグループのメンバーのみが実行できます。

- CsAdministrator –すべてのコマンドレットの取得と設定
- CsVoiceAdministrator-すべてのコマンドレットの取得と設定
- CsHelpDesk-すべてのコマンドレットの取得

これらの管理者ロールの詳細については、「 [Skype For Business Server コントロールパネル管理者の作成](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md)」を参照してください。 管理者は、これらのコマンドレットに直接、またはリモートでサーバーコンピューターにログオンしてアクセスできます。
ハイブリッド展開の場合、Skype for Business の管理者はすべてのコマンドレットの Get と Set を呼び出すことができます。 ロールの完全なリストの詳細については、「 [Office 365 管理者ロールについ](https://docs.microsoft.com/en-us/office365/admin/add-users/about-admin-roles)て」を参照してください。

> [!NOTE]
> サーバーの自動検出を有効にする必要があります。 コマンドレットを使用するために、追加のライセンス要件はありません。
