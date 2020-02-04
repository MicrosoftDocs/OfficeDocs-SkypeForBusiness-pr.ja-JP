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

# <a name="deploy-shared-line-appearance-in-lync-server-2013"></a><span data-ttu-id="2e437-102">Lync Server 2013 での共有線の外観の展開</span><span class="sxs-lookup"><span data-stu-id="2e437-102">Deploy Shared Line Appearance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2e437-103">_**最終更新日:** 2016-06-13_</span><span class="sxs-lookup"><span data-stu-id="2e437-103">_**Topic Last Modified:** 2016-06-13_</span></span>

<span data-ttu-id="2e437-104">このトピックでは、共有線の外観 (SLA) を Lync Server 2013 で展開する方法について説明し、2016年4月の累積更新プログラムについて説明します。</span><span class="sxs-lookup"><span data-stu-id="2e437-104">Read this topic to learn how to deploy Shared Line Appearance (SLA) in Lync Server 2013, Cumulative Update April 2016.</span></span> <span data-ttu-id="2e437-105">SLA は、共有番号と呼ばれる特定の電話番号で複数の通話を処理するための機能です。</span><span class="sxs-lookup"><span data-stu-id="2e437-105">SLA is a feature for handling multiple calls on a specific number called a shared number.</span></span>

<span data-ttu-id="2e437-106">この機能の詳細については、「 [Lync Server 2013 で共有線の外観を計画する](lync-server-2013-plan-for-shared-line-appearance.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e437-106">For more information about this feature, see [Plan for Shared Line Appearance in Lync Server 2013](lync-server-2013-plan-for-shared-line-appearance.md).</span></span>

<span data-ttu-id="2e437-107">共有線の外観 (SLA) は、Lync Server 2013 の累積更新プログラム (2016 年4月) の新機能です。</span><span class="sxs-lookup"><span data-stu-id="2e437-107">Shared Line Appearance (SLA) is a new feature in Lync Server 2013, Cumulative Update April 2016.</span></span> <span data-ttu-id="2e437-108">この機能を有効にするには、まずこの累積的な更新プログラムを展開しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e437-108">To enable this feature, you must have first deployed this cumulative update.</span></span>

<div>

## <a name="install-shared-line-appearance"></a><span data-ttu-id="2e437-109">回線共有機能のインストール</span><span class="sxs-lookup"><span data-stu-id="2e437-109">Install Shared Line Appearance</span></span>

1.  <span data-ttu-id="2e437-110">Lync Server 2013 では、2016年4月の累積更新プログラムが展開されますが、SLA アプリケーションは既定で有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="2e437-110">After Lync Server 2013, Cumulative Update April 2016 is deployed, the SLA application is not enabled by default.</span></span> <span data-ttu-id="2e437-111">アプリケーションを有効にするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="2e437-111">To enable the application, follow the steps below:</span></span>
    
    1.  <span data-ttu-id="2e437-112">各プールで次のコマンドを実行して、SLA をサーバー アプリケーションとして登録します。</span><span class="sxs-lookup"><span data-stu-id="2e437-112">Register SLA as a server application by running the following command for each pool:</span></span>
        ```powershell
        New-CsServerApplication -Identity
                        'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri
                        http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled
                        $true -Priority (Get-CsServerApplication -Identity
                        'Service:Registrar:%FQDN%/UserServices').Priority 
        ```
        <span data-ttu-id="2e437-113">%FQDN% は、プールの完全修飾ドメイン名です。</span><span class="sxs-lookup"><span data-stu-id="2e437-113">where %FQDN% is the fully qualified domain name of the pool.</span></span>
    
    2.  <span data-ttu-id="2e437-114">次のコマンドを実行して、SLA コマンドレッドの RBAC の役割を更新します。</span><span class="sxs-lookup"><span data-stu-id="2e437-114">Run the following command to update the RBAC roles for the SLA cmdlets:</span></span>
        ```powershell
        Update-CsAdminRole 
        ```
    3.  <span data-ttu-id="2e437-115">SLA がインストールされて有効になっているすべてのプールで、すべてのフロントエンド サーバー (RTCSRV サービス) を再起動します。</span><span class="sxs-lookup"><span data-stu-id="2e437-115">Restart all the Front End Servers (RTCSRV service) in all the pools where SLA was installed and enabled:</span></span>
        
        ```powershell 
        Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
                        
        ```

</div>

<div>

## <a name="create-an-sla-group-and-add-users-to-it"></a><span data-ttu-id="2e437-116">SLA グループを作成してユーザーを追加する</span><span class="sxs-lookup"><span data-stu-id="2e437-116">Create an SLA group and add users to it</span></span>

1.  <span data-ttu-id="2e437-117">[Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) コマンドレットを使用して、SLA グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="2e437-117">Create the SLA group by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) cmdlet:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup>
                -MaxNumberOfCalls <Number> -BusyOption
                <BusyOnBusy|Voicemail|Forward> [-Target
                <TargetUserOrPhoneNumber>]
    ```
    <span data-ttu-id="2e437-p104">Set-CsSlaConfiguration コマンドレットを実行すると、エンタープライズ VoIP アカウントである SLAGroup1 が SLA エンティティとしてマークされ、SLAGroup1 の番号が SLA グループの番号になります。SLAGroup1 に電話をかけると常に、SLA グループ全体に着信します。</span><span class="sxs-lookup"><span data-stu-id="2e437-p104">The Set-CsSlaConfiguration cmdlet marks the Enterprise Voice account SLAGroup1 as an SLA entity, and the number of SLAGroup1 becomes the number for the SLA group. All calls to SLAGroup1 will ring the entire SLA group.</span></span>
    
    <span data-ttu-id="2e437-120">次の例では、既存のエンタープライズ VoIP ユーザーである SLAGroup1 の SLA グループを作成し、SLAGroup1 に割り当てられる番号を SLA の主線番号として使用します。</span><span class="sxs-lookup"><span data-stu-id="2e437-120">The following example creates an SLA group for an existing Enterprise Voice user, SLAGroup1, and uses the number assigned for SLAGroup1 as the SLA mainline number.</span></span>
    
    <span data-ttu-id="2e437-121">このコマンドを実行すると、新しい SLA グループの最大同時通話数が 3 に設定され、4 件目以上の通話に対しては話中音が流れるようになります。</span><span class="sxs-lookup"><span data-stu-id="2e437-121">The command sets the maximum number of concurrent calls for the new SLA group to 3, and for calls in excess of that to hear a busy signal:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3
                -BusyOption BusyOnBusy
    ```
    <span data-ttu-id="2e437-122">Set-CsSlaConfiguration を使用して、新しい SLA グループの作成や既存の SLA グループの変更を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="2e437-122">You can use Set-CsSlaConfiguration to create a new SLA group or modify an existing one.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2e437-123">指定する対象は、有効<CODE>-Identity</CODE>な既存のエンタープライズボイス対応ユーザーアカウントである必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="2e437-123">Note that what you specify for <CODE>-Identity</CODE> must be a valid existing Enterprise Voice-enabled user account.</span></span>

    
    </div>

2.  <span data-ttu-id="2e437-124">[Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates) コマンドレットを使用して、グループに代理人を追加します。</span><span class="sxs-lookup"><span data-stu-id="2e437-124">Add delegates to the group by using the [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates) cmdlet:</span></span>
    ```powershell
    Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
              <NameOfDelegate@domain>
    ```
    <span data-ttu-id="2e437-125">次の例では、SLA グループにユーザーを追加しています。</span><span class="sxs-lookup"><span data-stu-id="2e437-125">The following example adds a user to the SLA group.</span></span> <span data-ttu-id="2e437-126">グループに追加される各ユーザーは、有効なエンタープライズボイス対応ユーザーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e437-126">Each user added to the group must be a valid Enterprise Voice-enabled user:</span></span>
    ```powershell
    Add-CsSlaDelegates -Identity SLAGroup1 -Delegate
              sip:SLA_Delegate1@contoso.com
    ```
    <span data-ttu-id="2e437-p106">グループに追加したい各ユーザーについてコマンドレットを繰り返し実行します。ユーザーは、単一の SLA グループにのみ属することができます。</span><span class="sxs-lookup"><span data-stu-id="2e437-p106">Repeat the cmdlet for each user you want to add to the group. Users can only belong to a single SLA group.</span></span>

</div>

<div>

## <a name="configure-the-sla-group-busy-option"></a><span data-ttu-id="2e437-129">SLA グループの通話中オプションの構成</span><span class="sxs-lookup"><span data-stu-id="2e437-129">Configure the SLA group Busy Option</span></span>

1.  <span data-ttu-id="2e437-130">[Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) コマンドレットを使用して、SLA グループの通話中オプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="2e437-130">Configure the SLA group Busy Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) cmdlet:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup>
              -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
    ```
    <span data-ttu-id="2e437-131">次の例では、電話番号202-555-1234 に転送される同時通話の最大数を超える通話を設定します。</span><span class="sxs-lookup"><span data-stu-id="2e437-131">The following example sets calls that exceed the maximum number of concurrent calls to be forwarded to the telephone number 202-555-1234.</span></span> <span data-ttu-id="2e437-132">ターゲットは、電話番号ではなく組織内のユーザーの場合もあります。この場合、転送された通話を受け取るユーザーの構文は、代理人`sip:<NameofDelegate@domain>`を指定した場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="2e437-132">The target could be a user in your organization instead of a phone number; in that case, the syntax for the person to receive the forwarded calls is the same as when you specify a delegate: `sip:<NameofDelegate@domain>`.</span></span> <span data-ttu-id="2e437-133">その他のパラメーターに`BusyOption`は`Voicemail`、次のパラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="2e437-133">The other possible parameter for `BusyOption` is `Voicemail`:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward
              -Target tel:+2025551234]
    ```
</div>

<div>

## <a name="configure-the-sla-group-missed-call-option"></a><span data-ttu-id="2e437-134">SLA グループの不在着信オプションを構成する</span><span class="sxs-lookup"><span data-stu-id="2e437-134">Configure the SLA group Missed Call Option</span></span>

1.  <span data-ttu-id="2e437-135">[Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) コマンドレットを使用して、SLA グループの不在着信オプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="2e437-135">Configure the SLA group Missed Call Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) cmdlet:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup> 
              -MissedCallOption <Option> -MissedCallForwardTarget
              <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
    ```
    <span data-ttu-id="2e437-136">次の例では、不在着信を、という名前`sla_forward_number`のユーザーに転送することを指定します。</span><span class="sxs-lookup"><span data-stu-id="2e437-136">The following example specifies that missed calls are to be forwarded to the user named `sla_forward_number`.</span></span> <span data-ttu-id="2e437-137">`-MissedCallOption`パラメーターの有効なオプションは`Forward`、、 `BusySignal`、また`Disconnect`はです。</span><span class="sxs-lookup"><span data-stu-id="2e437-137">The valid options for the `-MissedCallOption` parameter are `Forward`, `BusySignal`, or `Disconnect`.</span></span> <span data-ttu-id="2e437-138">を選択`Forward`した場合は、次の`-MissedCallForwardTarget`ように、ユーザーまたは電話番号のパラメーターも指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e437-138">If you choose `Forward`, you must also include the `-MissedCallForwardTarget` parameter, with a user or phone number as the target:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption
              Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com 
        -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com 
    ```
</div>

<div>

## <a name="remove-a-delegate-from-a-group"></a><span data-ttu-id="2e437-139">グループから代理人を削除する</span><span class="sxs-lookup"><span data-stu-id="2e437-139">Remove a delegate from a group</span></span>

1.  <span data-ttu-id="2e437-140">[Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates) コマンドレットを使用して、グループから代理人を削除します。</span><span class="sxs-lookup"><span data-stu-id="2e437-140">Remove a delegate from a group by using the [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates) cmdlet:</span></span>
    ```powershell
    Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
              <NameOfDelegate@domain>
    ```
    <span data-ttu-id="2e437-141">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="2e437-141">For example:</span></span>
    ```powershell
    Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate
              sip:SLA_Delegate3@contoso.com
    ```
</div>

<div>

## <a name="delete-an-sla-group"></a><span data-ttu-id="2e437-142">SLA グループを削除する</span><span class="sxs-lookup"><span data-stu-id="2e437-142">Delete an SLA group</span></span>

1.  <span data-ttu-id="2e437-143">[Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) コマンドレットを使用して、SLA グループを削除します。</span><span class="sxs-lookup"><span data-stu-id="2e437-143">Delete an SLA group by using the [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) cmdlet:</span></span>
    
    ```powershell
    Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
              
    ```
    
    <span data-ttu-id="2e437-144">例:</span><span class="sxs-lookup"><span data-stu-id="2e437-144">For example:</span></span>
    ```powershell
    Remove-CsSlaConfiguration -Identity SLAGroup1 
    ```
</div>

</div>

<span> </span>

</div>

</div>

</div>

