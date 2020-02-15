---
title: Skype for Business Server 2019 での PowerShell での SEFAUtil 機能の使用のサポート
ms.reviewer: rogupta
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.date: 07/22/2019
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: '概要: 累積的な更新プログラム1をインストールした後、PowerShell を使用して Skype for Business Server 2019 の SEFAUtil 機能を取得する方法について説明します。'
ms.openlocfilehash: 1a18a954e40ba7a0c72e4d87b4b3c943e827f2a1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049139"
---
# <a name="using-sefautil-functionality-via-powershell-in-skype-for-business-server-2019"></a>Skype for Business Server 2019 での PowerShell による SEFAUtil 機能の使用

SEFAUtil (セカンダリ拡張機能のアクティブ化) を使用すると、Skype for business Server の管理者とヘルプデスク担当者は、Skype for Business Server ユーザーに代わって、代理人の呼び出し、着信の転送、グループ通話ピックアップの設定を構成できます。 また、このツールを使用すると、管理者は特定のユーザーに対して公開されている呼び出しルーティング設定を照会することができます。 Skype for Business Server 2019 7 月の累積的な更新プログラムをインストールした後は、SEFAUtil を使用してのみ管理できる次の機能も、PowerShell を使用して管理することができます。

- [着信の転送設定](#call-forwarding-settings)
- [委任の設定](#delegation-settings)
- [チームメンバーおよび関連する設定](#team-members-and-related-settings)

## <a name="call-forwarding-settings"></a>着信の転送設定

管理者は、PowerShell で次のコマンドレットを使用して、着信転送の設定を変更できます。

- `Get-CsUserCallForwardingSettings -Identity <UserIdParameter>`

このコマンドレットは、指定されたユーザーの着信の転送設定をオブジェクトとして返し、画面に同じように表示します。

- `Set-CsUserCallForwardingSettings -Identity <UserIdParameter> [Param1 <Value>] [Param2 <Value>]…`

このコマンドレットは、指定したユーザーの着信転送設定を変更します。 このコマンドレットは、指定されたユーザーの着信の転送設定をオブジェクトとして返し、成功した場合には画面にも同じように表示します。 障害が発生した場合は、適切なエラーメッセージが表示されます。

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToVoicemail] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

このコマンドレットは、ユーザーの着信転送設定を無効にします (ここでは2つの異なるパラメーターの例を示します)。

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableForwarding <String> [-Delegates <PSListModifier>] [-DelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

このコマンドレットは、ユーザーの着信転送設定を変更します。

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToVoicemail]  [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>] [-Team <PSListModifier>] [-TeamDelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>]  [-Team <PSListModifier>]  [-TeamDelegateRingWaitTime <TimeSpan>]  [-SettingsActiveWorkHours]`

このコマンドレットでは、切り替わりの設定を変更します (2 つのパラメーター例があります。1つはボイスメールに応答しないため、もう一方には応答しません)。

## <a name="delegation-settings"></a>委任の設定

管理者は、PowerShell で次のコマンドレットを使用して委任設定を変更できます。

- `Get-CsuserDelegates -Identity <UserIdParameter>`

このコマンドレットは、デリゲートリストのオブジェクトを返し、指定されたユーザーの委任リストを表示します (成功した場合)。 障害が発生した場合は、適切なエラーメッセージが表示されます。

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates <PSListModifier>]`

このコマンドレットは、指定したユーザーの委任設定を変更して、代理人の一覧を返し、代理人の一覧を表示します (成功した場合)。 障害が発生した場合は、適切なエラーメッセージが表示されます。 

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{add=[list]}] [-Delegates @{remove=[list]}]`

このコマンドレットは、代理人を追加または削除します。

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{replace=[list]}]`

このコマンドレットは、代理人の一覧を特定の代理人に設定します。

## <a name="team-members-and-related-settings"></a>チームメンバーおよび関連する設定

管理者は、PowerShell で次のコマンドレットを使用して、チームメンバーおよび関連する設定を変更できます。

- `Get-CsUserTeamMembers -Identity <UserIdParameter>`

このコマンドレットは、チームメンバーのリストを含むオブジェクトを取得し、成功した場合はそのオブジェクトを画面に表示します。 障害が発生した場合は、適切なエラーメッセージが表示されます。

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team <PSListModifier>]`

このコマンドレットは、指定したユーザーのチームメンバーリストを変更し、チームメンバーリストを含むオブジェクトを返し、成功した場合はそのオブジェクトを画面に表示します。 障害が発生した場合は、適切なエラーメッセージが表示されます。

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{add=[list]}] [-Team @{remove=[list]}]`

このコマンドレットは、チームメンバーを追加または削除します。

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{replace=[list]}]`

このコマンドレットは、チームリストを特定のメンバーに設定します。

## <a name="more-information"></a>詳細情報

オンプレミス展開の場合、この機能で導入されたコマンドレットは、次のグループのメンバーのみが実行できます。以下に指定するアクセスレベルごとに、

- CsAdministrator –すべてのコマンドレットの取得と設定
- CsVoiceAdministrator-すべてのコマンドレットの取得と設定
- CsHelpDesk-すべてのコマンドレットの取得

これらの管理者ロールの詳細については、「 [Skype For Business Server コントロールパネル管理者の作成](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md)」を参照してください。 管理者は、サーバーコンピューターに直接またはリモートでログオンして、これらのコマンドレットにアクセスできます。
ハイブリッド展開の場合、Skype for Business 管理者は Get を呼び出してすべてのコマンドレットに設定できます。 役割の完全な一覧の詳細については、「 [Office 365 管理者の役割につい](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)て」を参照してください。

> [!NOTE]
> サーバーの自動検出を有効にする必要があります。 コマンドレットを使用するために、追加のライセンス要件は導入されていません。
