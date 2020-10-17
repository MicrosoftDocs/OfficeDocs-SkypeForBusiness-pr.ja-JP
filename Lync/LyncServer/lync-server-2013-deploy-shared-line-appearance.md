---
title: 'Lync Server 2013: 共有ラインの外観の展開'
description: 'Lync Server 2013: 共有線の外観を展開します。'
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
ms.openlocfilehash: c83c06bbc9b91e11cabc0abee20de28fc7281205
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558623"
---
# <a name="deploy-shared-line-appearance-in-lync-server-2013"></a><span data-ttu-id="2cb71-103">Lync Server 2013 での共有線の外観の展開</span><span class="sxs-lookup"><span data-stu-id="2cb71-103">Deploy Shared Line Appearance in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2cb71-104">_**トピックの最終更新日:** 2016-06-13_</span><span class="sxs-lookup"><span data-stu-id="2cb71-104">_**Topic Last Modified:** 2016-06-13_</span></span>

<span data-ttu-id="2cb71-105">このトピックでは、Lync Server 2013 (累積更新プログラム4月 2016) での共有回線の外観 (SLA) の展開方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2cb71-105">Read this topic to learn how to deploy Shared Line Appearance (SLA) in Lync Server 2013, Cumulative Update April 2016.</span></span> <span data-ttu-id="2cb71-106">SLA は、共有番号と呼ばれる特定の番号で複数の通話を処理するための機能です。</span><span class="sxs-lookup"><span data-stu-id="2cb71-106">SLA is a feature for handling multiple calls on a specific number called a shared number.</span></span>

<span data-ttu-id="2cb71-107">この機能の詳細については、「 [Lync Server 2013 で共有線の外観を計画する](lync-server-2013-plan-for-shared-line-appearance.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2cb71-107">For more information about this feature, see [Plan for Shared Line Appearance in Lync Server 2013](lync-server-2013-plan-for-shared-line-appearance.md).</span></span>

<span data-ttu-id="2cb71-108">共有回線の外観 (SLA) は、Lync Server 2013 の新しい機能で、累積更新プログラムは4月2016です。</span><span class="sxs-lookup"><span data-stu-id="2cb71-108">Shared Line Appearance (SLA) is a new feature in Lync Server 2013, Cumulative Update April 2016.</span></span> <span data-ttu-id="2cb71-109">この機能を有効にするには、最初にこの累積的な更新プログラムを展開しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="2cb71-109">To enable this feature, you must have first deployed this cumulative update.</span></span>

<div>

## <a name="install-shared-line-appearance"></a><span data-ttu-id="2cb71-110">共有線の外観をインストールする</span><span class="sxs-lookup"><span data-stu-id="2cb71-110">Install Shared Line Appearance</span></span>

1.  <span data-ttu-id="2cb71-111">Lync Server 2013 の後、累積更新プログラム (2016 年4月) は展開されますが、SLA アプリケーションは既定では有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="2cb71-111">After Lync Server 2013, Cumulative Update April 2016 is deployed, the SLA application is not enabled by default.</span></span> <span data-ttu-id="2cb71-112">アプリケーションを有効にするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="2cb71-112">To enable the application, follow the steps below:</span></span>
    
    1.  <span data-ttu-id="2cb71-113">各プールに対して次のコマンドを実行して、SLA をサーバーアプリケーションとして登録します。</span><span class="sxs-lookup"><span data-stu-id="2cb71-113">Register SLA as a server application by running the following command for each pool:</span></span>
        ```powershell
        New-CsServerApplication -Identity
                        'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri
                        http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled
                        $true -Priority (Get-CsServerApplication -Identity
                        'Service:Registrar:%FQDN%/UserServices').Priority 
        ```
        <span data-ttu-id="2cb71-114">ここで、% FQDN% はプールの完全修飾ドメイン名です。</span><span class="sxs-lookup"><span data-stu-id="2cb71-114">where %FQDN% is the fully qualified domain name of the pool.</span></span>
    
    2.  <span data-ttu-id="2cb71-115">次のコマンドを実行して、SLA コマンドレットの RBAC の役割を更新します。</span><span class="sxs-lookup"><span data-stu-id="2cb71-115">Run the following command to update the RBAC roles for the SLA cmdlets:</span></span>
        ```powershell
        Update-CsAdminRole 
        ```
    3.  <span data-ttu-id="2cb71-116">SLA がインストールされて有効になっているすべてのプールで、すべてのフロントエンドサーバー (RTCSRV サービス) を再起動します。</span><span class="sxs-lookup"><span data-stu-id="2cb71-116">Restart all the Front End Servers (RTCSRV service) in all the pools where SLA was installed and enabled:</span></span>
        
        ```powershell 
        Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
                        
        ```

</div>

<div>

## <a name="create-an-sla-group-and-add-users-to-it"></a><span data-ttu-id="2cb71-117">SLA グループを作成してユーザーを追加する</span><span class="sxs-lookup"><span data-stu-id="2cb71-117">Create an SLA group and add users to it</span></span>

1.  <span data-ttu-id="2cb71-118">[Set-csslaconfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration)コマンドレットを使用して、SLA グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="2cb71-118">Create the SLA group by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) cmdlet:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup>
                -MaxNumberOfCalls <Number> -BusyOption
                <BusyOnBusy|Voicemail|Forward> [-Target
                <TargetUserOrPhoneNumber>]
    ```
    <span data-ttu-id="2cb71-119">Set-CsSlaConfiguration コマンドレットは、エンタープライズ Voip アカウント SLAGroup1 を SLA エンティティとしてマークし、SLAGroup1 数が SLA グループの番号になります。</span><span class="sxs-lookup"><span data-stu-id="2cb71-119">The Set-CsSlaConfiguration cmdlet marks the Enterprise Voice account SLAGroup1 as an SLA entity, and the number of SLAGroup1 becomes the number for the SLA group.</span></span> <span data-ttu-id="2cb71-120">SLAGroup1 へのすべての呼び出しは、SLA グループ全体を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="2cb71-120">All calls to SLAGroup1 will ring the entire SLA group.</span></span>
    
    <span data-ttu-id="2cb71-121">次の例では、既存のエンタープライズ Voip ユーザー SLAGroup1 の SLA グループを作成し、SLAGroup1 に割り当てられた番号を SLA のメインライン番号として使用します。</span><span class="sxs-lookup"><span data-stu-id="2cb71-121">The following example creates an SLA group for an existing Enterprise Voice user, SLAGroup1, and uses the number assigned for SLAGroup1 as the SLA mainline number.</span></span>
    
    <span data-ttu-id="2cb71-122">このコマンドは、新しい SLA グループの同時呼び出しの最大数を3に設定し、それを超える通話がビジー信号を聞くことができるようにします。</span><span class="sxs-lookup"><span data-stu-id="2cb71-122">The command sets the maximum number of concurrent calls for the new SLA group to 3, and for calls in excess of that to hear a busy signal:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3
                -BusyOption BusyOnBusy
    ```
    <span data-ttu-id="2cb71-123">Set-CsSlaConfiguration を使用して、新しい SLA グループを作成したり、既存のものを変更したりできます。</span><span class="sxs-lookup"><span data-stu-id="2cb71-123">You can use Set-CsSlaConfiguration to create a new SLA group or modify an existing one.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2cb71-124">には、 <CODE>-Identity</CODE> 有効な既存のエンタープライズ voip ユーザーアカウントを指定する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="2cb71-124">Note that what you specify for <CODE>-Identity</CODE> must be a valid existing Enterprise Voice-enabled user account.</span></span>

    
    </div>

2.  <span data-ttu-id="2cb71-125">[CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates)コマンドレットを使用して、グループに代理人を追加します。</span><span class="sxs-lookup"><span data-stu-id="2cb71-125">Add delegates to the group by using the [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates) cmdlet:</span></span>
    ```powershell
    Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
              <NameOfDelegate@domain>
    ```
    <span data-ttu-id="2cb71-126">次の例では、ユーザーを SLA グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="2cb71-126">The following example adds a user to the SLA group.</span></span> <span data-ttu-id="2cb71-127">グループに追加される各ユーザーは、有効なエンタープライズ Voip が有効なユーザーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="2cb71-127">Each user added to the group must be a valid Enterprise Voice-enabled user:</span></span>
    ```powershell
    Add-CsSlaDelegates -Identity SLAGroup1 -Delegate
              sip:SLA_Delegate1@contoso.com
    ```
    <span data-ttu-id="2cb71-128">グループに追加するユーザーごとにコマンドレットを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="2cb71-128">Repeat the cmdlet for each user you want to add to the group.</span></span> <span data-ttu-id="2cb71-129">ユーザーは1つの SLA グループにのみ属することができます。</span><span class="sxs-lookup"><span data-stu-id="2cb71-129">Users can only belong to a single SLA group.</span></span>

</div>

<div>

## <a name="configure-the-sla-group-busy-option"></a><span data-ttu-id="2cb71-130">SLA グループの通話中オプションを構成する</span><span class="sxs-lookup"><span data-stu-id="2cb71-130">Configure the SLA group Busy Option</span></span>

1.  <span data-ttu-id="2cb71-131">[Set-csslaconfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration)コマンドレットを使用して、SLA グループの通話中オプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="2cb71-131">Configure the SLA group Busy Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) cmdlet:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup>
              -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
    ```
    <span data-ttu-id="2cb71-132">次の例では、電話番号202-555-1234 に同時に転送される通話の最大数を超える呼び出しを設定します。</span><span class="sxs-lookup"><span data-stu-id="2cb71-132">The following example sets calls that exceed the maximum number of concurrent calls to be forwarded to the telephone number 202-555-1234.</span></span> <span data-ttu-id="2cb71-133">ターゲットは、電話番号ではなく、組織内のユーザーの場合があります。その場合、転送された通話を受信するユーザーの構文は、代理人を指定した場合と同じ `sip:<NameofDelegate@domain>` です。</span><span class="sxs-lookup"><span data-stu-id="2cb71-133">The target could be a user in your organization instead of a phone number; in that case, the syntax for the person to receive the forwarded calls is the same as when you specify a delegate: `sip:<NameofDelegate@domain>`.</span></span> <span data-ttu-id="2cb71-134">その他の使用可能なパラメーター `BusyOption` は `Voicemail` 次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2cb71-134">The other possible parameter for `BusyOption` is `Voicemail`:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward
              -Target tel:+2025551234]
    ```
</div>

<div>

## <a name="configure-the-sla-group-missed-call-option"></a><span data-ttu-id="2cb71-135">SLA グループの不在着信オプションを構成する</span><span class="sxs-lookup"><span data-stu-id="2cb71-135">Configure the SLA group Missed Call Option</span></span>

1.  <span data-ttu-id="2cb71-136">[Set-csslaconfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration)コマンドレットを使用して、SLA グループの不在着信オプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="2cb71-136">Configure the SLA group Missed Call Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) cmdlet:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup> 
              -MissedCallOption <Option> -MissedCallForwardTarget
              <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
    ```
    <span data-ttu-id="2cb71-137">次の例では、不在着信をという名前のユーザーに転送するように指定し `sla_forward_number` ます。</span><span class="sxs-lookup"><span data-stu-id="2cb71-137">The following example specifies that missed calls are to be forwarded to the user named `sla_forward_number`.</span></span> <span data-ttu-id="2cb71-138">パラメーターの有効なオプション `-MissedCallOption` は、、、 `Forward` `BusySignal` または `Disconnect` です。</span><span class="sxs-lookup"><span data-stu-id="2cb71-138">The valid options for the `-MissedCallOption` parameter are `Forward`, `BusySignal`, or `Disconnect`.</span></span> <span data-ttu-id="2cb71-139">を選択する場合は、 `Forward` `-MissedCallForwardTarget` ユーザーまたは電話番号をターゲットとするパラメーターも含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="2cb71-139">If you choose `Forward`, you must also include the `-MissedCallForwardTarget` parameter, with a user or phone number as the target:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption
              Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com 
        -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com 
    ```
</div>

<div>

## <a name="remove-a-delegate-from-a-group"></a><span data-ttu-id="2cb71-140">グループから代理人を削除する</span><span class="sxs-lookup"><span data-stu-id="2cb71-140">Remove a delegate from a group</span></span>

1.  <span data-ttu-id="2cb71-141">[CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates)コマンドレットを使用して、グループから代理人を削除します。</span><span class="sxs-lookup"><span data-stu-id="2cb71-141">Remove a delegate from a group by using the [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates) cmdlet:</span></span>
    ```powershell
    Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
              <NameOfDelegate@domain>
    ```
    <span data-ttu-id="2cb71-142">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="2cb71-142">For example:</span></span>
    ```powershell
    Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate
              sip:SLA_Delegate3@contoso.com
    ```
</div>

<div>

## <a name="delete-an-sla-group"></a><span data-ttu-id="2cb71-143">SLA グループを削除する</span><span class="sxs-lookup"><span data-stu-id="2cb71-143">Delete an SLA group</span></span>

1.  <span data-ttu-id="2cb71-144">[Set-csslaconfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps)コマンドレットを使用して、SLA グループを削除します。</span><span class="sxs-lookup"><span data-stu-id="2cb71-144">Delete an SLA group by using the [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) cmdlet:</span></span>
    
    ```powershell
    Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
              
    ```
    
    <span data-ttu-id="2cb71-145">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="2cb71-145">For example:</span></span>
    ```powershell
    Remove-CsSlaConfiguration -Identity SLAGroup1 
    ```
</div>

</div>

<span> </span>

</div>

</div>

</div>

