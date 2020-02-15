---
title: 'Lync Server 2013: 共有ラインの外観の展開'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy Shared Line Appearance
ms:assetid: 6666dfef-9ecf-4834-af6a-2d5da227dfa3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Mt712152(v=OCS.15)
ms:contentKeyID: 72522137
ms.date: 06/13/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1523a48b5d9056b1cca532a7edb1c826af841b8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036899"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-shared-line-appearance-in-lync-server-2013"></a>Lync Server 2013 での共有線の外観の展開

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2016-06-13_

このトピックでは、Lync Server 2013 (累積更新プログラム4月 2016) での共有回線の外観 (SLA) の展開方法について説明します。 SLA は、共有番号と呼ばれる特定の番号で複数の通話を処理するための機能です。

この機能の詳細については、「 [Lync Server 2013 で共有線の外観を計画する](lync-server-2013-plan-for-shared-line-appearance.md)」を参照してください。

共有回線の外観 (SLA) は、Lync Server 2013 の新しい機能で、累積更新プログラムは4月2016です。 この機能を有効にするには、最初にこの累積的な更新プログラムを展開しておく必要があります。

<div>

## <a name="install-shared-line-appearance"></a>共有線の外観をインストールする

1.  Lync Server 2013 の後、累積更新プログラム (2016 年4月) は展開されますが、SLA アプリケーションは既定では有効になっていません。 アプリケーションを有効にするには、次の手順を実行します。
    
    1.  各プールに対して次のコマンドを実行して、SLA をサーバーアプリケーションとして登録します。
        ```powershell
        New-CsServerApplication -Identity
                        'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri
                        http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled
                        $true -Priority (Get-CsServerApplication -Identity
                        'Service:Registrar:%FQDN%/UserServices').Priority 
        ```
        ここで、% FQDN% はプールの完全修飾ドメイン名です。
    
    2.  次のコマンドを実行して、SLA コマンドレットの RBAC の役割を更新します。
        ```powershell
        Update-CsAdminRole 
        ```
    3.  SLA がインストールされて有効になっているすべてのプールで、すべてのフロントエンドサーバー (RTCSRV サービス) を再起動します。
        
        ```powershell 
        Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
                        
        ```

</div>

<div>

## <a name="create-an-sla-group-and-add-users-to-it"></a>SLA グループを作成してユーザーを追加する

1.  [Set-csslaconfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration)コマンドレットを使用して、SLA グループを作成します。
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup>
                -MaxNumberOfCalls <Number> -BusyOption
                <BusyOnBusy|Voicemail|Forward> [-Target
                <TargetUserOrPhoneNumber>]
    ```
    Set-csslaconfiguration コマンドレットは、エンタープライズ Voip アカウント SLAGroup1 を SLA エンティティとしてマークし、SLAGroup1 の数が SLA グループの番号になります。 SLAGroup1 へのすべての呼び出しは、SLA グループ全体を呼び出します。
    
    次の例では、既存のエンタープライズ Voip ユーザー SLAGroup1 の SLA グループを作成し、SLAGroup1 に割り当てられた番号を SLA のメインライン番号として使用します。
    
    このコマンドは、新しい SLA グループの同時呼び出しの最大数を3に設定し、それを超える通話がビジー信号を聞くことができるようにします。
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3
                -BusyOption BusyOnBusy
    ```
    Set-csslaconfiguration を使用して、新しい SLA グループを作成したり、既存のものを変更したりすることができます。
    
    <div>
    

    > [!NOTE]  
    > には、有効な既存<CODE>-Identity</CODE>のエンタープライズ voip ユーザーアカウントを指定する必要があることに注意してください。

    
    </div>

2.  [CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates)コマンドレットを使用して、グループに代理人を追加します。
    ```powershell
    Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
              <NameOfDelegate@domain>
    ```
    次の例では、ユーザーを SLA グループに追加します。 グループに追加される各ユーザーは、有効なエンタープライズ Voip が有効なユーザーである必要があります。
    ```powershell
    Add-CsSlaDelegates -Identity SLAGroup1 -Delegate
              sip:SLA_Delegate1@contoso.com
    ```
    グループに追加するユーザーごとにコマンドレットを繰り返します。 ユーザーは1つの SLA グループにのみ属することができます。

</div>

<div>

## <a name="configure-the-sla-group-busy-option"></a>SLA グループの通話中オプションを構成する

1.  [Set-csslaconfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration)コマンドレットを使用して、SLA グループの通話中オプションを構成します。
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup>
              -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
    ```
    次の例では、電話番号202-555-1234 に同時に転送される通話の最大数を超える呼び出しを設定します。 ターゲットは、電話番号ではなく、組織内のユーザーの場合があります。その場合、転送された通話を受信するユーザーの構文は、代理人`sip:<NameofDelegate@domain>`を指定した場合と同じです。 その他の使用可能`BusyOption`な`Voicemail`パラメーターは次のとおりです。
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward
              -Target tel:+2025551234]
    ```
</div>

<div>

## <a name="configure-the-sla-group-missed-call-option"></a>SLA グループの不在着信オプションを構成する

1.  [Set-csslaconfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration)コマンドレットを使用して、SLA グループの不在着信オプションを構成します。
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup> 
              -MissedCallOption <Option> -MissedCallForwardTarget
              <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
    ```
    次の例では、不在着信をという名前`sla_forward_number`のユーザーに転送するように指定します。 `-MissedCallOption`パラメーターの有効なオプションは`Forward`、 `BusySignal`、、また`Disconnect`はです。 を選択`Forward`する場合は、ユーザーまたは`-MissedCallForwardTarget`電話番号をターゲットとするパラメーターも含める必要があります。
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption
              Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com 
        -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com 
    ```
</div>

<div>

## <a name="remove-a-delegate-from-a-group"></a>グループから代理人を削除する

1.  [CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates)コマンドレットを使用して、グループから代理人を削除します。
    ```powershell
    Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
              <NameOfDelegate@domain>
    ```
    例:
    ```powershell
    Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate
              sip:SLA_Delegate3@contoso.com
    ```
</div>

<div>

## <a name="delete-an-sla-group"></a>SLA グループを削除する

1.  [Set-csslaconfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps)コマンドレットを使用して、SLA グループを削除します。
    
    ```powershell
    Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
              
    ```
    
    次に例を示します。
    ```powershell
    Remove-CsSlaConfiguration -Identity SLAGroup1 
    ```
</div>

</div>

<span> </span>

</div>

</div>

</div>

