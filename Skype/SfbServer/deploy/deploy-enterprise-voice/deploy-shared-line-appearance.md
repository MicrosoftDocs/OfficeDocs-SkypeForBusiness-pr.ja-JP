---
title: 2015 年に共有回線の外観をSkype for Business Server
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
description: このトピックでは、2015 年 11 月 2015 年 11 月の累積的な更新プログラムで共有回線の外観 (SLA) を展開するSkype for Business Server説明します。 SLA は、共有番号と呼ばれる特定の番号で複数の呼び出しを処理する機能です。
ms.openlocfilehash: 5adf5934e93bd93fe9f50c0a8e4dd790c695da57
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62397487"
---
# <a name="deploy-shared-line-appearance-in-skype-for-business-server-2015"></a>2015 年に共有回線の外観をSkype for Business Server

このトピックでは、2015 年 11 月 2015 年 11 月の累積的な更新プログラムで共有回線の外観 (SLA) を展開するSkype for Business Server説明します。 SLA は、共有番号と呼ばれる特定の番号で複数の呼び出しを処理する機能です。

この機能の詳細については、「[Plan for Shared Line appearance in Skype for Business Server 2015」を参照](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md)してください。

共有回線の外観 (SLA) は、2015 年 11 月 2015 年 11 月の累積的な更新プログラムSkype for Business Server新機能です。 この機能を有効にするには、最初にこの累積的な更新プログラムを展開している必要があります。

### <a name="install-shared-line-appearance"></a>共有行の外観をインストールする

1. 2015 Skype for Business Server 2015 `SkypeServerUpdateInstaller.exe` 年 11 月の累積的な更新プログラムが展開された後、プール内の各フロント エンド サーバーでこの更新プログラムを実行します。

2. インストーラーは SLA アプリケーションの最新バージョンを展開しますが、アプリケーションは既定では有効になっていません。 この機能は、以下に示す手順に従って有効になります。

    a. プールごとに次のコマンドを実行して、SLA をサーバー アプリケーションとして登録します。

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri   http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled $true -Priority (Get-CsServerApplication -Identity  'Service:Registrar:%FQDN%/UserServices').Priority
   ```

   ここで、%FQDN% はプールの完全修飾ドメイン名です。

    b. 次のコマンドを実行して、SLA コマンドレットの RBAC ロールを更新します。

   ```powershell
   Update-CsAdminRole
   ```

    c. SLA がインストールされ有効になっているすべてのプールで、すべてのフロントエンド サーバー (RTCSRV サービス) を再起動します。

   ```powershell
   Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
   ```

### <a name="create-an-sla-group-and-add-users-to-it"></a>SLA グループを作成し、そのグループにユーザーを追加する

1. [Set-CsSlaConfiguration コマンドレットを使用して SLA グループを作成](/powershell/module/skype/set-csslaconfiguration?view=skype-ps)します。

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MaxNumberOfCalls <Number> -BusyOption <BusyOnBusy|Voicemail|Forward> [-Target <TargetUserOrPhoneNumber>]
   ```

    このSet-CsSlaConfiguration、SLAGroup1 エンタープライズ VoIP SLAGroup1 を SLA エンティティとしてマークし、SLAGroup1 の数が SLA グループの番号になります。 SLAGroup1 へのすべての呼び出しは、SLA グループ全体を呼び出します。

    次の使用例は、既存の エンタープライズ VoIP ユーザー SLAGroup1 の SLA グループを作成し、SLAGroup1 に割り当てられた番号を SLA メインライン番号として使用します。

    このコマンドは、新しい SLA グループの同時呼び出しの最大数を 3 に設定し、それを超える通話でビジー信号を聞き取る場合に設定します。

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3 -BusyOption BusyOnBusy
   ```

    新しい SLA グループSet-CsSlaConfiguration既存の SLA グループを変更する場合は、このグループを使用します。

    > [!NOTE]
    > 指定する項目は、`-Identity`有効な既存のユーザー アカウントエンタープライズ VoIP必要があります。

2. [Add-CsSlaDelegates](/powershell/module/skype/add-cssladelegates?view=skype-ps) コマンドレットを使用してグループに代理人を追加します。

   ```powershell
   Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
          <NameOfDelegate@domain>
   ```

    次の使用例は、SLA グループにユーザーを追加します。 グループに追加する各ユーザーは、有効なユーザーエンタープライズ VoIPする必要があります。

   ```powershell
   Add-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate1@contoso.com
   ```

    グループに追加するユーザーごとにコマンドレットを繰り返します。 ユーザーは 1 つの SLA グループにのみ属できます。

### <a name="configure-the-sla-group-busy-option"></a>SLA グループのビジー オプションの構成

- [Set-CsSlaConfiguration コマンドレットを使用して SLA グループのビジー オプションを構成](/powershell/module/skype/set-csslaconfiguration?view=skype-ps)します。

  ```powershell
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
  ```

    次の使用例は、電話番号 202-555-1234 に転送する同時呼び出しの最大数を超える呼び出しを設定します。 ターゲットは、電話番号の代わりに組織内のユーザーである可能性があります。その場合、転送された呼び出しを受信するユーザーの構文は、代理人を指定した場合と同じです。 `sip:<NameofDelegate@domain>` もう 1 つのパラメーターは次  `BusyOption` の場合です `Voicemail`。

  ```powershell
  Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward -Target tel:+2025551234
  ```

### <a name="configure-the-sla-group-missed-call-option"></a>SLA グループの [通話不足] オプションを構成する

1. [Set-CsSlaConfiguration コマンドレットを使用して、SLA グループの [Missed Call Option] を構成](/powershell/module/skype/set-csslaconfiguration?view=skype-ps)します。

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MissedCallOption <Option> -MissedCallForwardTarget <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
   ```

2. 次の使用例は、呼び出しの欠落をという名前のユーザーに転送する場合に指定します  `sla_forward_number`。 パラメーターの有効なオプションは`-MissedCallOption`、`Forward``BusySignal`またはです`Disconnect`。 選択した場合は  `Forward`、ユーザーまたは  `-MissedCallForwardTarget` 電話番号をターゲットとしてパラメーターも含める必要があります。

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com
   ```

### <a name="remove-a-delegate-from-a-group"></a>グループから代理人を削除する

- [Remove-CsSlaDelegates](/powershell/module/skype/remove-cssladelegates?view=skype-ps) コマンドレットを使用して、グループから代理人を削除します。

  ```powershell
  Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
  ```

    次に例を示します。

  ```powershell
  Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate3@contoso.com
  ```

### <a name="delete-an-sla-group"></a>SLA グループを削除する

- [Remove-CsSlaConfiguration コマンドレット](/powershell/module/skype/remove-csslaconfiguration?view=skype-ps)を使用して SLA グループを削除します。

  ```powershell
  Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
  ```

    次に例を示します。

  ```powershell
  Remove-CsSlaConfiguration -Identity SLAGroup1
  ```