---
title: Skype for Business Server 2015 での共有線の外観の展開
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 474a5e4a-9479-4e86-8607-b9f41a0fa648
description: このトピックでは、Skype for Business Server 2015 (2015 年11月の累積的な更新プログラム) で共有回線の外観 (SLA) を展開する方法について説明します。 SLA は、共有番号と呼ばれる特定の番号で複数の通話を処理するための機能です。
ms.openlocfilehash: 2009b313b343d9746f3eeff5f53fec4899c2f9a3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42129310"
---
# <a name="deploy-shared-line-appearance-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での共有線の外観の展開

このトピックでは、Skype for Business Server 2015 (2015 年11月の累積的な更新プログラム) で共有回線の外観 (SLA) を展開する方法について説明します。 SLA は、共有番号と呼ばれる特定の番号で複数の通話を処理するための機能です。

この機能の詳細については、「 [Skype For Business Server 2015 で共有線の外観を計画する](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md)」を参照してください。

共有回線の外観 (SLA) は、Skype for Business Server の新機能 (2015 年11月の累積的な更新プログラム) です。 この機能を有効にするには、最初にこの累積的な更新プログラムを展開しておく必要があります。

### <a name="install-shared-line-appearance"></a>共有線の外観をインストールする

1. Skype for Business Server、2015年11月の累積的な更新プログラム`SkypeServerUpdateInstaller.exe`を展開した後、プール内の各フロントエンドサーバーで修正プログラムを実行します。

2. インストーラーによって、最新バージョンの SLA アプリケーションが展開されますが、既定ではアプリケーションが有効になっていません。 次の手順に従って、これを有効にします。

    a. 各プールに対して次のコマンドを実行して、SLA をサーバーアプリケーションとして登録します。

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri   https://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled                $true -Priority (Get-CsServerApplication -Identity              'Service:Registrar:%FQDN%/UserServices').Priority
   ```

   ここで、% FQDN% はプールの完全修飾ドメイン名です。

    b. 次のコマンドを実行して、SLA コマンドレットの RBAC の役割を更新します。

   ```powershell
   Update-CsAdminRole
   ```

    c. SLA がインストールされて有効になっているすべてのプールで、すべてのフロントエンドサーバー (RTCSRV サービス) を再起動します。

   ```powershell
   Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
   ```

### <a name="create-an-sla-group-and-add-users-to-it"></a>SLA グループを作成してユーザーを追加する

1. [Set-csslaconfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps)コマンドレットを使用して、SLA グループを作成します。

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MaxNumberOfCalls <Number> -BusyOption <BusyOnBusy|Voicemail|Forward> [-Target <TargetUserOrPhoneNumber>]
   ```

    Set-csslaconfiguration コマンドレットは、エンタープライズ Voip アカウント SLAGroup1 を SLA エンティティとしてマークし、SLAGroup1 の数が SLA グループの番号になります。 SLAGroup1 へのすべての呼び出しは、SLA グループ全体を呼び出します。

    次の例では、既存のエンタープライズ Voip ユーザー SLAGroup1 の SLA グループを作成し、SLAGroup1 に割り当てられた番号を SLA のメインライン番号として使用します。

    このコマンドは、新しい SLA グループの同時呼び出しの最大数を3に設定し、それを超える通話がビジー信号を聞くことができるようにします。

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3 -BusyOption BusyOnBusy
   ```

    Set-csslaconfiguration を使用して、新しい SLA グループを作成したり、既存のものを変更したりすることができます。

    > [!NOTE]
    > には、有効な既存`-Identity`のエンタープライズ voip ユーザーアカウントを指定する必要があることに注意してください。

2. [CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates?view=skype-ps)コマンドレットを使用して、グループに代理人を追加します。

   ```powershell
   Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
          <NameOfDelegate@domain>
   ```

    次の例では、ユーザーを SLA グループに追加します。 グループに追加される各ユーザーは、有効なエンタープライズ Voip が有効なユーザーである必要があります。

   ```powershell
   Add-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate1@contoso.com
   ```

    グループに追加するユーザーごとにコマンドレットを繰り返します。 ユーザーは1つの SLA グループにのみ属することができます。

### <a name="configure-the-sla-group-busy-option"></a>SLA グループの通話中オプションを構成する

- [Set-csslaconfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps)コマンドレットを使用して、SLA グループの通話中オプションを構成します。

  ```powershell
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
  ```

    次の例では、電話番号202-555-1234 に同時に転送される通話の最大数を超える呼び出しを設定します。 ターゲットは、電話番号ではなく、組織内のユーザーの場合があります。その場合、転送された通話を受信するユーザーの構文は、代理人`sip:<NameofDelegate@domain>`を指定した場合と同じです。 その他の使用可能`BusyOption`な`Voicemail`パラメーターは次のとおりです。

  ```powershell
  Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward -Target tel:+2025551234
  ```

### <a name="configure-the-sla-group-missed-call-option"></a>SLA グループの不在着信オプションを構成する

1. [Set-csslaconfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps)コマンドレットを使用して、SLA グループの不在着信オプションを構成します。

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MissedCallOption <Option> -MissedCallForwardTarget <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
   ```

2. 次の例では、不在着信をという名前`sla_forward_number`のユーザーに転送するように指定します。 `-MissedCallOption`パラメーターの有効なオプションは`Forward`、 `BusySignal`、、また`Disconnect`はです。 を選択`Forward`する場合は、ユーザーまたは`-MissedCallForwardTarget`電話番号をターゲットとするパラメーターも含める必要があります。

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com
   ```

### <a name="remove-a-delegate-from-a-group"></a>グループから代理人を削除する

- [CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates?view=skype-ps)コマンドレットを使用して、グループから代理人を削除します。

  ```powershell
  Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
  ```

    次に例を示します。

  ```powershell
  Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate3@contoso.com
  ```

### <a name="delete-an-sla-group"></a>SLA グループを削除する

- [Set-csslaconfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps)コマンドレットを使用して、SLA グループを削除します。

  ```powershell
  Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
  ```

    次に例を示します。

  ```powershell
  Remove-CsSlaConfiguration -Identity SLAGroup1
  ```


