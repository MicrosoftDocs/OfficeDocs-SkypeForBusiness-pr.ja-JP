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
description: '概要: 累積的な更新プログラム 1 をインストールした後、PowerShell を使用して Skype for Business Server 2019 で SEFAUtil 機能を取得する方法について説明します。'
ms.openlocfilehash: d97dd84a3d05cf18752e40dd73a8c5f7e9752d3d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120508"
---
# <a name="using-sefautil-functionality-via-powershell-in-skype-for-business-server-2019"></a>Skype for Business Server 2019 で PowerShell 経由で SEFAUtil 機能を使用する

SEFAUtil (Secondary Extension Feature Activation) を使用すると、Skype for Business Server 管理者およびヘルプデスク エージェントは、Skype for Business Server ユーザーに代わって代理呼び出し、通話転送、およびグループ通話ピックアップの設定を構成できます。 また、このツールを使用すると、管理者は特定のユーザーに対して発行された通話ルーティング設定を照会できます。 Skype for Business Server 2019 7 月の累積的な更新プログラムをインストールすると、現在 SEFAUtil を通じてのみ管理できる次の機能も PowerShell で管理できます。

- [通話転送の設定](#call-forwarding-settings)
- [委任の設定](#delegation-settings)
- [チーム メンバーと関連する設定](#team-members-and-related-settings)

## <a name="call-forwarding-settings"></a>通話転送の設定

管理者は、PowerShell で次のコマンドレットを使用して、通話転送設定を変更できます。

- `Get-CsUserCallForwardingSettings -Identity <UserIdParameter>`

このコマンドレットは、指定したユーザーの呼び出し転送設定をオブジェクトとして返し、同じ設定を画面に表示します。

- `Set-CsUserCallForwardingSettings -Identity <UserIdParameter> [Param1 <Value>] [Param2 <Value>]…`

このコマンドレットは、指定したユーザーの通話転送設定を変更します。 このコマンドレットは、指定したユーザーの呼び出し転送設定をオブジェクトとして返し、成功した場合は画面に同じ設定を表示します。 エラーが発生した場合は、適切なエラー メッセージが表示されます。

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToVoicemail] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

このコマンドレットは、ユーザーの通話転送設定を無効にします (ここでは、2 つの異なるパラメーター例を示します)。

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableForwarding <String> [-Delegates <PSListModifier>] [-DelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

このコマンドレットは、ユーザーの通話転送設定を変更します。

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToVoicemail]  [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>] [-Team <PSListModifier>] [-TeamDelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>]  [-Team <PSListModifier>]  [-TeamDelegateRingWaitTime <TimeSpan>]  [-SettingsActiveWorkHours]`

このコマンドレットは、SimulRing 設定を変更します (もう一度、2 つのパラメーター例を使用します。1 つはボイスメールに応答しない場合と、もう 1 つは他のパラメーターの例に応答しません)。

## <a name="delegation-settings"></a>委任の設定

管理者は、PowerShell で次のコマンドレットを使用して委任設定を変更できます。

- `Get-CsuserDelegates -Identity <UserIdParameter>`

このコマンドレットは、代理人リストのオブジェクトを返し、成功した場合に指定したユーザーの代理人リストを表示します。 エラーが発生した場合は、適切なエラー メッセージが表示されます。

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates <PSListModifier>]`

このコマンドレットは、指定したユーザーの委任設定を変更し、代理人リストのオブジェクトを返し、成功した場合に代理人の一覧を表示します。 エラーが発生した場合は、適切なエラー メッセージが表示されます。 

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{add=[list]}] [-Delegates @{remove=[list]}]`

このコマンドレットは、代理人を追加または削除します。

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{replace=[list]}]`

このコマンドレットは、代理人リストを特定の代理人に設定します。

## <a name="team-members-and-related-settings"></a>チーム メンバーと関連する設定

管理者は、PowerShell で次のコマンドレットを使用して、チーム メンバーと関連する設定を変更できます。

- `Get-CsUserTeamMembers -Identity <UserIdParameter>`

このコマンドレットは、チーム メンバーの一覧を含むオブジェクトを返し、成功した場合にオブジェクトを画面に表示します。 エラーが発生した場合は、適切なエラー メッセージが表示されます。

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team <PSListModifier>]`

このコマンドレットは、指定したユーザーのチーム メンバーリストを変更し、チーム メンバーリストを含むオブジェクトを返し、成功した場合は、そのオブジェクトを画面に表示します。 エラーが発生した場合は、適切なエラー メッセージが表示されます。

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{add=[list]}] [-Team @{remove=[list]}]`

このコマンドレットは、チーム メンバーを追加または削除します。

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{replace=[list]}]`

このコマンドレットは、チーム リストを特定のメンバーに設定します。

## <a name="more-information"></a>詳細

オンプレミス展開の場合、この機能で導入されたコマンドレットを実行できるのは、次に示すアクセス レベルに従って、次のグループのメンバーのみです。

- CsAdministrator – すべてのコマンドレットの取得と設定
- CsVoiceAdministrator - すべてのコマンドレットの取得と設定
- CsHelpDesk - すべてのコマンドレットを取得する

これらの管理者の役割の詳細については [、「Create Skype for Business Server コントロール パネル管理者」を参照してください](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md)。 管理者は、サーバー コンピューターに直接またはリモートでログオンすることで、これらのコマンドレットにアクセスできます。
ハイブリッド展開の場合、Skype for Business 管理者は、すべてのコマンドレットに対して Get と Set を呼び出すことができます。 役割の完全な一覧の詳細については、「管理者の役割について [」を参照してください](/microsoft-365/admin/add-users/about-admin-roles)。

> [!NOTE]
> サーバーの自動検出を有効にする必要があります。 コマンドレットを使用するために追加のライセンス要件は導入されません。