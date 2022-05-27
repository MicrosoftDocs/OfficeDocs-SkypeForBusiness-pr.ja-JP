---
title: Skype for Business Server 2019 の Skype PowerShell での SEFAUtil 機能の使用のサポート
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
ms.localizationpriority: medium
ms.collection: IT_Skype16
description: '概要: PowerShell を使用して、累積的な更新プログラム 1 をインストールした後、Skype for Business Server 2019 で SEFAUtil 機能を取得する方法について説明します。'
ms.openlocfilehash: 07d05ef1687fa9ca14f7e90108ae8b5c0e7e3bb9
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676539"
---
# <a name="using-sefautil-functionality-via-powershell-in-skype-for-business-server-2019"></a>Skype for Business Server 2019 で PowerShell 経由で SEFAUtil 機能を使用する

SEFAUtil (セカンダリ拡張機能のアクティブ化) を使用すると、Skype for Business Server管理者とヘルプ デスク エージェントは、Skype for Business Server ユーザーに代わって代理呼び出し、通話転送、およびグループ通話ピックアップの設定を構成できます。 SEFAUtil を使用すると、管理者は特定のユーザーの呼び出しルーティング設定に対してクエリを実行することもできます。

Skype for Business Server 2019 7 月の累積的な更新プログラムをインストールした後、SEFAUtil でのみ使用できた次の機能は、Skype PowerShell でも使用できます。

- [通話転送設定](#call-forwarding-settings)
- [委任設定](#delegation-settings)
- [チーム メンバーと関連する設定](#team-members-and-related-settings)

## <a name="call-forwarding-settings"></a>通話転送設定

管理者は、PowerShell で次のコマンドを使用して、通話転送設定を変更できます。

```powershell
Get-CsUserCallForwardingSettings -Identity <UserIdParameter>
```

このコマンドは、指定したユーザーの通話転送設定をオブジェクトとして返し、画面に同じ内容を表示します。

```powershell
Set-CsUserCallForwardingSettings -Identity <UserIdParameter> [Param1 <Value>] [Param2 <Value>]...
```

このコマンドは、指定したユーザーの通話転送設定を変更します。 このコマンドは、指定したユーザーの呼び出し転送設定をオブジェクトとして返し、画面に同じ内容を表示します。 コマンドが成功しなかった場合は、適切なエラー メッセージが表示されます。

```powershell
Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToVoicemail] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]
```

```powershell
Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]
```

このコマンドは、ユーザーの通話転送設定を無効にします (ここでは、2 つの異なるパラメーター例を示します)。

```powershell
Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableForwarding <String> [-Delegates <PSListModifier>] [-DelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]
```

このコマンドは、ユーザーの通話転送設定を変更します。

```powershell
Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToVoicemail]  [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>] [-Team <PSListModifier>] [-TeamDelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]
```

```powershell
Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>]  [-Team <PSListModifier>]  [-TeamDelegateRingWaitTime <TimeSpan>]  [-SettingsActiveWorkHours]
```

このコマンドは、同時リング設定を変更します (もう一度、2 つのパラメーター例を使用します。1 つはボイスメールに応答されず、もう 1 つは他のパラメーターに対して応答されません)。

## <a name="delegation-settings"></a>委任設定

管理者は、PowerShell で次のコマンドを使用して委任設定を変更できます。

```powershell
Get-CsuserDelegates -Identity <UserIdParameter>
```

このコマンドは、デリゲート リストのオブジェクトを返し、指定したユーザーのデリゲート リストを表示します。 コマンドが成功しなかった場合は、適切なエラー メッセージが表示されます。

```powershell
Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates <PSListModifier>]
```

このコマンドは、指定したユーザーの委任設定を変更し、デリゲートリストのオブジェクトを返し、デリゲートの一覧を表示します。 コマンドが成功しなかった場合は、適切なエラー メッセージが表示されます。

```powershell
Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{add=[list]}] [-Delegates @{remove=[list]}]
```

このコマンドは、デリゲートを追加または削除します。

```powershell
Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{replace=[list]}]
```

このコマンドは、デリゲート リストを特定のデリゲートに設定します。

## <a name="team-members-and-related-settings"></a>チーム メンバーと関連する設定

管理者は、PowerShell で次のコマンドを使用して、チーム メンバーと関連する設定を変更できます。

```powershell
Get-CsUserTeamMembers -Identity <UserIdParameter>
```

このコマンドは、チーム メンバーの一覧を含むオブジェクトを返し、そのオブジェクトを画面に表示します。 コマンドが成功しなかった場合は、適切なエラー メッセージが表示されます。

```powershell
Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team <PSListModifier>]
```

このコマンドは、指定したユーザーのチーム メンバーリストを変更し、チーム メンバーリストを含むオブジェクトを返し、そのオブジェクトを画面に表示します。 コマンドが成功しなかった場合は、適切なエラー メッセージが表示されます。

```powershell
Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{add=[list]}] [-Team @{remove=[list]}]
```

このコマンドは、チーム メンバーを追加または削除します。

```powershell
Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{replace=[list]}]
```

このコマンドは、チーム リストを特定のメンバーに設定します。

## <a name="more-information"></a>詳細

オンプレミスのデプロイの場合、この機能で導入されたコマンドレットは、次に示すアクセス レベルに従って、次のグループのメンバーのみが実行できます。

- CsAdministrator – すべてのコマンドレットの取得と設定
- CsVoiceAdministrator - すべてのコマンドレットの取得と設定
- CsHelpDesk - すべてのコマンドレットを取得する

これらの管理者ロールの詳細については、「[Skype for Business Server コントロール パネル管理者の作成](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md)」を参照してください。 管理者は、サーバー コンピューターに直接またはリモートでログオンすることで、これらのコマンドレットにアクセスできます。
ハイブリッド展開の場合、Skype for Business管理者はすべてのコマンドレットに対して Get と Set を呼び出すことができる必要があります。 ロールの完全な一覧の詳細については、「 [管理者ロールについて](/microsoft-365/admin/add-users/about-admin-roles)」を参照してください。

> [!NOTE]
> サーバーの自動検出を有効にする必要があります。 コマンドレットを使用するための追加のライセンス要件は導入されません。
