---
title: 'Lync Server 2013: 共有の線の外観を展開する'
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
ms.openlocfilehash: 5e0f6aeb7d235ea7691c6878a4f21e6ec98f531e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729647"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-shared-line-appearance-in-lync-server-2013"></a>Lync Server 2013 での共有線の外観の展開

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2016-06-13_

このトピックでは、共有線の外観 (SLA) を Lync Server 2013 で展開する方法について説明し、2016年4月の累積更新プログラムについて説明します。 SLA は、共有番号と呼ばれる特定の電話番号で複数の通話を処理するための機能です。

この機能の詳細については、「 [Lync Server 2013 で共有線の外観を計画する](lync-server-2013-plan-for-shared-line-appearance.md)」を参照してください。

共有線の外観 (SLA) は、Lync Server 2013 の累積更新プログラム (2016 年4月) の新機能です。 この機能を有効にするには、まずこの累積的な更新プログラムを展開しておく必要があります。

<div>

## <a name="install-shared-line-appearance"></a>回線共有機能のインストール

1.  Lync Server 2013 では、2016年4月の累積更新プログラムが展開されますが、SLA アプリケーションは既定で有効になっていません。 アプリケーションを有効にするには、次の手順を実行します。
    
    1.  各プールで次のコマンドを実行して、SLA をサーバー アプリケーションとして登録します。
        ```powershell
        New-CsServerApplication -Identity
                        'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri
                        http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled
                        $true -Priority (Get-CsServerApplication -Identity
                        'Service:Registrar:%FQDN%/UserServices').Priority 
        ```
        %FQDN% は、プールの完全修飾ドメイン名です。
    
    2.  次のコマンドを実行して、SLA コマンドレッドの RBAC の役割を更新します。
        ```powershell
        Update-CsAdminRole 
        ```
    3.  SLA がインストールされて有効になっているすべてのプールで、すべてのフロントエンド サーバー (RTCSRV サービス) を再起動します。
        
        ```powershell 
        Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
                        
        ```

</div>

<div>

## <a name="create-an-sla-group-and-add-users-to-it"></a>SLA グループを作成してユーザーを追加する

1.  [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) コマンドレットを使用して、SLA グループを作成します。
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup>
                -MaxNumberOfCalls <Number> -BusyOption
                <BusyOnBusy|Voicemail|Forward> [-Target
                <TargetUserOrPhoneNumber>]
    ```
    Set-CsSlaConfiguration コマンドレットを実行すると、エンタープライズ VoIP アカウントである SLAGroup1 が SLA エンティティとしてマークされ、SLAGroup1 の番号が SLA グループの番号になります。SLAGroup1 に電話をかけると常に、SLA グループ全体に着信します。
    
    次の例では、既存のエンタープライズ VoIP ユーザーである SLAGroup1 の SLA グループを作成し、SLAGroup1 に割り当てられる番号を SLA の主線番号として使用します。
    
    このコマンドを実行すると、新しい SLA グループの最大同時通話数が 3 に設定され、4 件目以上の通話に対しては話中音が流れるようになります。
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3
                -BusyOption BusyOnBusy
    ```
    Set-CsSlaConfiguration を使用して、新しい SLA グループの作成や既存の SLA グループの変更を行うことができます。
    
    <div>
    

    > [!NOTE]  
    > 指定する対象は、有効<CODE>-Identity</CODE>な既存のエンタープライズボイス対応ユーザーアカウントである必要があることに注意してください。

    
    </div>

2.  [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates) コマンドレットを使用して、グループに代理人を追加します。
    ```powershell
    Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
              <NameOfDelegate@domain>
    ```
    次の例では、SLA グループにユーザーを追加しています。 グループに追加される各ユーザーは、有効なエンタープライズボイス対応ユーザーである必要があります。
    ```powershell
    Add-CsSlaDelegates -Identity SLAGroup1 -Delegate
              sip:SLA_Delegate1@contoso.com
    ```
    グループに追加したい各ユーザーについてコマンドレットを繰り返し実行します。ユーザーは、単一の SLA グループにのみ属することができます。

</div>

<div>

## <a name="configure-the-sla-group-busy-option"></a>SLA グループの通話中オプションの構成

1.  [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) コマンドレットを使用して、SLA グループの通話中オプションを構成します。
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup>
              -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
    ```
    次の例では、電話番号202-555-1234 に転送される同時通話の最大数を超える通話を設定します。 ターゲットは、電話番号ではなく組織内のユーザーの場合もあります。この場合、転送された通話を受け取るユーザーの構文は、代理人`sip:<NameofDelegate@domain>`を指定した場合と同じです。 その他のパラメーターに`BusyOption`は`Voicemail`、次のパラメーターがあります。
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward
              -Target tel:+2025551234]
    ```
</div>

<div>

## <a name="configure-the-sla-group-missed-call-option"></a>SLA グループの不在着信オプションを構成する

1.  [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) コマンドレットを使用して、SLA グループの不在着信オプションを構成します。
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup> 
              -MissedCallOption <Option> -MissedCallForwardTarget
              <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
    ```
    次の例では、不在着信を、という名前`sla_forward_number`のユーザーに転送することを指定します。 `-MissedCallOption`パラメーターの有効なオプションは`Forward`、、 `BusySignal`、また`Disconnect`はです。 を選択`Forward`した場合は、次の`-MissedCallForwardTarget`ように、ユーザーまたは電話番号のパラメーターも指定する必要があります。
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption
              Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com 
        -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com 
    ```
</div>

<div>

## <a name="remove-a-delegate-from-a-group"></a>グループから代理人を削除する

1.  [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates) コマンドレットを使用して、グループから代理人を削除します。
    ```powershell
    Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
              <NameOfDelegate@domain>
    ```
    次に例を示します。
    ```powershell
    Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate
              sip:SLA_Delegate3@contoso.com
    ```
</div>

<div>

## <a name="delete-an-sla-group"></a>SLA グループを削除する

1.  [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) コマンドレットを使用して、SLA グループを削除します。
    
    ```powershell
    Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
              
    ```
    
    例:
    ```powershell
    Remove-CsSlaConfiguration -Identity SLAGroup1 
    ```
</div>

</div>

<span> </span>

</div>

</div>

</div>

