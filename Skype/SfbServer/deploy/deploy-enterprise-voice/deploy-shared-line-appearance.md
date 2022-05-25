---
title: Skype for Business Server 2015 で共有行の外観を展開する
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 474a5e4a-9479-4e86-8607-b9f41a0fa648
description: このトピックでは、2015 年 11 月の累積的な更新プログラムSkype for Business Server共有行外観 (SLA) を展開する方法について説明します。 SLA は、共有番号と呼ばれる特定の番号で複数の呼び出しを処理するための機能です。
ms.openlocfilehash: 7f9d904de2b3348bdf8ed75b9f0df38aee252cdd
ms.sourcegitcommit: c53c22069b1babce7a2364de631057ff501ca1c0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2022
ms.locfileid: "65671593"
---
# <a name="deploy-shared-line-appearance-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 で共有行の外観を展開する

このトピックでは、2015 年 11 月の累積的な更新プログラムSkype for Business Server共有行外観 (SLA) を展開する方法について説明します。 SLA は、共有番号と呼ばれる特定の番号で複数の呼び出しを処理するための機能です。

この機能の詳細については、「[Skype for Business Server 2015 で共有線の外観を計画](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md)する」を参照してください。

Shared Line Appearance (SLA) は、2015 年 11 月の累積的な更新プログラムSkype for Business Serverの新機能です。 この機能を有効にするには、最初にこの累積的な更新プログラムを展開しておく必要があります。

## <a name="install-shared-line-appearance"></a>共有行の外観をインストールする

1. Skype for Business Server、2015 年 11 月の累積的な更新プログラムが展開されたら、プール内の`SkypeServerUpdateInstaller.exe`各フロント エンド サーバーでパッチを実行します。

2. インストーラーは最新バージョンの SLA アプリケーションをデプロイしますが、アプリケーションは既定では有効になっていません。 この機能は、次に示す手順に従って有効になります。

    a.  プールごとに次のコマンドを実行して、SLA をサーバー アプリケーションとして登録します。

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled $true -Priority (Get-CsServerApplication -Identity  'Service:Registrar:%FQDN%/UserServices').Priority
   ```

   %FQDN% はプールの完全修飾ドメイン名です。

    b. 次のコマンドを実行して、SLA コマンドレットの RBAC ロールを更新します。

   ```powershell
   Update-CsAdminRole
   ```

    c. SLA がインストールされ、有効になっているすべてのプールで、すべてのフロントエンド サーバー (RTCSRV サービス) を再起動します。

   ```powershell
   Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
   ```

## <a name="create-an-sla-group-and-add-users-to-it"></a>SLA グループを作成し、それにユーザーを追加する

1. [Set-CsSlaConfiguration](/powershell/module/skype/set-csslaconfiguration) コマンドレットを使用して SLA グループを作成します。

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MaxNumberOfCalls <Number> -BusyOption <BusyOnBusy|Voicemail|Forward> [-Target <TargetUserOrPhoneNumber>]
   ```

    Set-CsSlaConfigurationコマンドレットは、エンタープライズ VoIP アカウント SLAGroup1 を SLA エンティティとしてマークし、SLAGroup1 の数が SLA グループの番号になります。 SLAGroup1 へのすべての呼び出しは、SLA グループ全体を呼び出します。

    次の例では、既存のエンタープライズ VoIP ユーザーである SLAGroup1 の SLA グループを作成し、SLAGroup1 に割り当てられた番号を SLA メインライン番号として使用します。

    このコマンドは、新しい SLA グループの同時呼び出しの最大数を 3 に設定し、それ以上の呼び出しでビジー状態の信号を読み上げるには次のように設定します。

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3 -BusyOption BusyOnBusy
   ```

    Set-CsSlaConfigurationを使用して、新しい SLA グループを作成したり、既存の SLA グループを変更したりできます。

    > [!NOTE]
    > 指定`-Identity`する内容は、有効な既存のエンタープライズ VoIPが有効なユーザー アカウントである必要があることに注意してください。

2. [Add-CsSlaDelegates](/powershell/module/skype/add-cssladelegates) コマンドレットを使用して、グループにデリゲートを追加します。

   ```powershell
   Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
   ```

    次の例では、SLA グループにユーザーを追加します。 グループに追加される各ユーザーは、有効なエンタープライズ VoIPが有効なユーザーである必要があります。

   ```powershell
   Add-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate1@contoso.com
   ```

    グループに追加するユーザーごとにコマンドレットを繰り返します。 ユーザーは 1 つの SLA グループにのみ属することができます。

## <a name="configure-the-sla-group-busy-option"></a>SLA グループビジー オプションを構成する

- [Set-CsSlaConfiguration](/powershell/module/skype/set-csslaconfiguration) コマンドレットを使用して SLA グループビジー オプションを構成します。

  ```powershell
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
  ```

    次の例では、電話番号 202-555-1234 に転送する同時呼び出しの最大数を超える呼び出しを設定します。 ターゲットは、電話番号ではなく組織内のユーザーである可能性があります。その場合、転送された呼び出しを受け取るユーザーの構文は、デリゲート  `sip:<NameofDelegate@domain>`を指定した場合と同じです。 もう 1 つの可能な  `BusyOption` パラメーターは次のとおりです `Voicemail`。

  ```powershell
  Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward -Target tel:+2025551234
  ```

## <a name="configure-the-sla-group-missed-call-option"></a>SLA グループの不在着信オプションを構成する

1. [Set-CsSlaConfiguration](/powershell/module/skype/set-csslaconfiguration) コマンドレットを使用して、SLA グループの不在着信オプションを構成します。

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MissedCallOption <Option> -MissedCallForwardTarget <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
   ```

2. 次の例では、不在着信をという名前  `sla_forward_number`のユーザーに転送することを指定します。 パラメーターの有効なオプション  `-MissedCallOption` は `Forward`、、  `BusySignal`、または  `Disconnect`. 選択  `Forward`した場合は、ターゲットとしてユーザーまたは電話番号を  `-MissedCallForwardTarget` 含め、パラメーターも含める必要があります。

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com
   ```

## <a name="remove-a-delegate-from-a-group"></a>グループからデリゲートを削除する

- [Remove-CsSlaDelegates](/powershell/module/skype/remove-cssladelegates) コマンドレットを使用して、グループからデリゲートを削除します。

  ```powershell
  Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
  ```

    例として以下のようなものがあります。

  ```powershell
  Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate3@contoso.com
  ```

## <a name="delete-an-sla-group"></a>SLA グループを削除する

- [Remove-CsSlaConfiguration](/powershell/module/skype/remove-csslaconfiguration) コマンドレットを使用して SLA グループを削除します。

  ```powershell
  Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
  ```

    次に例を示します。

  ```powershell
  Remove-CsSlaConfiguration -Identity SLAGroup1
  ```
