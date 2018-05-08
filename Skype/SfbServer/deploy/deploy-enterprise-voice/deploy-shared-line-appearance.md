---
title: Skype for Business Server 2015 で回線共有機能を展開する
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 474a5e4a-9479-4e86-8607-b9f41a0fa648
description: ここでは、Skype for Business Server 2015 の累積的な更新プログラム (2015 年 11 月) で回線共有機能 (SLA) を展開する方法について説明します。SLA は、共有番号と呼ばれる特定の電話番号で複数の通話を処理するための機能です。
ms.openlocfilehash: b333751b5bc4e651a7f1080e459803e8ad87da80
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="deploy-shared-line-appearance-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 で回線共有機能を展開する
 
ここでは、Skype for Business Server 2015 の累積的な更新プログラム (2015 年 11 月) で回線共有機能 (SLA) を展開する方法について説明します。SLA は、共有番号と呼ばれる特定の電話番号で複数の通話を処理するための機能です。 
  
この機能の詳細については、 [Skype のビジネス サーバー 2015 の線の外観を共有の予定](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md)を参照してください。
  
2015年 11 月はビジネス サーバーでは、Skype の新機能、共有行の外観 (SLA) 累積的な更新です。 この機能を有効にするには、まずこの累積的な更新プログラムを展開しておく必要があります。
  
### <a name="install-shared-line-appearance"></a>回線共有機能のインストール

1. ビジネス サーバー、2015年 11 月累積的な更新を展開すると、Skype の後を実行、 `SkypeServerUpdateInstaller.exe` 、プール内のそれぞれのフロント エンド サーバーに修正プログラムです。
    
2. インストーラーによって SLA アプリケーションの最新バージョンが展開されますが、アプリケーションは既定で有効ではありません。以下の手順で有効にします。
    
    a. 各プールで次のコマンドを実行して、SLA をサーバー アプリケーションとして登録します。
    
   ```
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri   http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled                 $true -Priority (Get-CsServerApplication -Identity              'Service:Registrar:%FQDN%/UserServices').Priority 
   ```

   %FQDN% は、プールの完全修飾ドメイン名です。 
    
    b. 次のコマンドを実行して、SLA コマンドレッドの RBAC の役割を更新します。 
    
   ```
   Update-CsAdminRole 
   ```

    c. SLA がインストールされて有効になっているすべてのプールで、すべてのフロントエンド サーバー (RTCSRV サービス) を再起動します。
    
  ```
   Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
                
  ```

### <a name="create-an-sla-group-and-add-users-to-it"></a>SLA グループを作成してユーザーを追加する

1. [セット CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps)コマンドレットを使用して、SLA のグループを作成します。
    
  ```
  Set-CsSlaConfiguration -Identity <IdentityOfGroup>
          -MaxNumberOfCalls <Number> -BusyOption
          <BusyOnBusy|Voicemail|Forward> [-Target
          <TargetUserOrPhoneNumber>]
  ```

    Set-CsSlaConfiguration コマンドレットを実行すると、エンタープライズ VoIP アカウントである SLAGroup1 が SLA エンティティとしてマークされ、SLAGroup1 の番号が SLA グループの番号になります。SLAGroup1 に電話をかけると常に、SLA グループ全体に着信します。
    
    次の例では、既存のエンタープライズ VoIP ユーザーである SLAGroup1 の SLA グループを作成し、SLAGroup1 に割り当てられる番号を SLA の主線番号として使用します。 
    
    このコマンドを実行すると、新しい SLA グループの最大同時通話数が 3 に設定され、4 件目以上の通話に対しては話中音が流れるようになります。
    
  ```
  Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3
          -BusyOption BusyOnBusy
  ```

    Set-CsSlaConfiguration を使用して、新しい SLA グループの作成や既存の SLA グループの変更を行うことができます。
    
    > [!NOTE]
    > 何に指定することに注意してください`-Identity`既存ユーザーのエンタープライズ VoIP を有効にしたアカウントを有効にする必要があります。
  
2. グループにデリゲートを追加するには、[追加 CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates?view=skype-ps)コマンドレットを使用します。
    
  ```
  Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
          <NameOfDelegate@domain>
  ```

    次の例では、SLA グループにユーザーを追加しています。 グループに追加する各ユーザーは、有効なエンタープライズ VoIP が有効なユーザーである必要があります。
    
  ```
  Add-CsSlaDelegates -Identity SLAGroup1 -Delegate
          sip:SLA_Delegate1@contoso.com
  ```

    グループに追加したい各ユーザーについてコマンドレットを繰り返し実行します。ユーザーは、単一の SLA グループにのみ属することができます。
    
### <a name="configure-the-sla-group-busy-option"></a>SLA グループの通話中オプションの構成

- SLA が構成[セット CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps)コマンドレットを使用して、ビジー状態のオプションをグループ化します。
    
  ```
  Set-CsSlaConfiguration -Identity <IdentityOfGroup>
          -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
  ```

    電話番号 202-555-1234 に転送するのには、同時呼び出しの最大数を超える呼び出しを設定する例を次にします。 ターゲットは、電話番号の代わりに、組織内のユーザーである可能性があります。転送された呼び出しを受信する人のための構文は、代理人を指定する場合と同じ場合は、: `sip:<NameofDelegate@domain>`。 他の可能なパラメーターの`BusyOption`、 `Voicemail`。
    
  ```
  Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward
          -Target tel:+2025551234]
  ```

### <a name="configure-the-sla-group-missed-call-option"></a>SLA グループの不在着信オプションを構成する

1. [セット CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps)コマンドレットを使用して、SLA グループ喪失の呼び出しのオプションを構成します。
    
  ```
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> 
          -MissedCallOption <Option> -MissedCallForwardTarget
          <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
  ```

2. 次の例は、不在着信がという名前のユーザーに転送されることを指定します。 `sla_forward_number`。 有効なオプション、`-MissedCallOption`パラメーターは、 `Forward`、 `BusySignal`、または`Disconnect`。 選択する場合は、`Forward`も含める必要があります、 `-MissedCallForwardTarget` 、パラメーター、ユーザーまたは電話番号、ターゲットとして。
    
  ```
  Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption
          Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com 
    -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com 
  ```

### <a name="remove-a-delegate-from-a-group"></a>グループから代理人を削除する

- [削除 CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates?view=skype-ps)コマンドレットを使用してグループからデリゲートを削除します。
    
  ```
  Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
          <NameOfDelegate@domain>
  ```

    例:
    
  ```
  Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate
          sip:SLA_Delegate3@contoso.com
  ```

### <a name="delete-an-sla-group"></a>SLA グループを削除する

- [削除 CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps)コマンドレットを使用して、SLA のグループを削除します。
    
  ```
  Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
          
  ```

    例: 
    
  ```
  Remove-CsSlaConfiguration -Identity SLAGroup1 
  ```


