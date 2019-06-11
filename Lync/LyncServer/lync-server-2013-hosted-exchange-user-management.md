---
title: 'Lync Server 2013: Hosted Exchange ユーザー管理'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hosted Exchange user management
ms:assetid: e8723af5-0604-4d7d-bad2-463a9832efb4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399037(v=OCS.15)
ms:contentKeyID: 48185887
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ead9762c67f3239f84cc1290b4ff2e9acc976318
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833063"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-user-management-in-lync-server-2013"></a><span data-ttu-id="db1be-102">Lync Server 2013 の Hosted Exchange ユーザー管理</span><span class="sxs-lookup"><span data-stu-id="db1be-102">Hosted Exchange user management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="db1be-103">_**最終更新日:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="db1be-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="db1be-104">ホストされている Exchange サービス上にメールボックスがある Lync Server 2013 ユーザー用のボイスメールサービスを提供するには、ホストされているボイスメールに対してユーザーアカウントを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="db1be-104">To provide voice mail services for Lync Server 2013 users whose mailboxes are located on a hosted Exchange service, you must enable their user accounts for hosted voice mail.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="db1be-105">ホストされているボイスメールに対して Lync Server 2013 ユーザーを有効にするには、対応するユーザーアカウントに適用されるホストされたボイスメールポリシーを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="db1be-105">Before a Lync Server 2013 user can be enabled for hosted voice mail, a hosted voice mail policy that applies to the corresponding user account must be deployed.</span></span> <span data-ttu-id="db1be-106">ポリシーは、有効にするユーザーに適用される限り、スコープ内でグローバル、サイト、またはユーザーごとに設定できます。</span><span class="sxs-lookup"><span data-stu-id="db1be-106">The policy can be global, site, or per-user in scope, as long as it applies to the user whom you want to enable.</span></span> <span data-ttu-id="db1be-107">詳細については、「 <A href="lync-server-2013-hosted-voice-mail-policies.md">Lync Server 2013 のホスト型ボイスメールポリシー</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db1be-107">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="the-msexchucvoicemailsettings-attribute"></a><span data-ttu-id="db1be-108">MsExchUCVoiceMailSettings 属性</span><span class="sxs-lookup"><span data-stu-id="db1be-108">The msExchUCVoiceMailSettings Attribute</span></span>

<span data-ttu-id="db1be-109">Lync Server 2013 には、Lync Server 2013 Active Directory スキーマの準備の一部として作成された**msExchUCVoiceMailSettings**という新しいユーザー属性が導入されています。</span><span class="sxs-lookup"><span data-stu-id="db1be-109">Lync Server 2013 introduces a new user attribute named **msExchUCVoiceMailSettings**, which is created as part of the Lync Server 2013 Active Directory schema preparation.</span></span> <span data-ttu-id="db1be-110">この複数値属性は、Lync Server 2013 とホストされる Exchange サービスで共有されるボイスメール設定を保持します。</span><span class="sxs-lookup"><span data-stu-id="db1be-110">This multivalued attribute holds voice mail settings that are shared by Lync Server 2013 and the hosted Exchange service.</span></span>

<span data-ttu-id="db1be-111">ホストされた Exchange サービスは、Exchange UM を有効にするプロセス、またはメールボックスをホストされた Exchange サーバーに移行するプロセスで、msExchUCVoiceMailSettings 属性の値を設定する場合があります。</span><span class="sxs-lookup"><span data-stu-id="db1be-111">The hosted Exchange service may in some cases set the value of the msExchUCVoiceMailSettings attribute in the process of enabling Exchange UM, or during the process of transferring mailboxes to a hosted Exchange Server.</span></span> <span data-ttu-id="db1be-112">この属性が Exchange によって設定されていない場合は、このトピックで前に説明したように、Set-CsUser コマンドレットを実行して Lync Server 2013 管理者が設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="db1be-112">If this attribute is not set by Exchange, the Lync Server 2013 administrator must set it by running the Set-CsUser cmdlet, as described earlier in this topic.</span></span>

<span data-ttu-id="db1be-113">属性のキー/値ペアとその作成者を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="db1be-113">The attribute’s key/value pairs and their authors are shown in the following table.</span></span>

### <a name="the-msexchucvoicemailsettings-attribute-keyvalue-pairs"></a><span data-ttu-id="db1be-114">MsExchUCVoiceMailSettings 属性のキーと値のペア</span><span class="sxs-lookup"><span data-stu-id="db1be-114">The msExchUCVoiceMailSettings Attribute Key/Value Pairs</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="db1be-115">値</span><span class="sxs-lookup"><span data-stu-id="db1be-115">Value</span></span></th>
<th><span data-ttu-id="db1be-116">著作者</span><span class="sxs-lookup"><span data-stu-id="db1be-116">Author</span></span></th>
<th><span data-ttu-id="db1be-117">意味</span><span class="sxs-lookup"><span data-stu-id="db1be-117">Meaning</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="db1be-118">ExchangeHostedVoiceMail = 1</span><span class="sxs-lookup"><span data-stu-id="db1be-118">ExchangeHostedVoiceMail=1</span></span></p></td>
<td><p><span data-ttu-id="db1be-119">Exchange</span><span class="sxs-lookup"><span data-stu-id="db1be-119">Exchange</span></span></p></td>
<td><p><span data-ttu-id="db1be-120">ユーザーは Exchange Server によってホストされた UM アクセスが有効になっています。</span><span class="sxs-lookup"><span data-stu-id="db1be-120">User has been enabled for hosted UM access by Exchange Server.</span></span> <span data-ttu-id="db1be-121">Exchange UM ルーティングアプリケーションは、ルーティングの詳細についてユーザーのホストされるボイスメールポリシーを確認します。</span><span class="sxs-lookup"><span data-stu-id="db1be-121">The Exchange UM Routing application will check the user’s hosted voice mail policy for routing details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db1be-122">ExchangeHostedVoiceMail = 0</span><span class="sxs-lookup"><span data-stu-id="db1be-122">ExchangeHostedVoiceMail=0</span></span></p></td>
<td><p><span data-ttu-id="db1be-123">Exchange</span><span class="sxs-lookup"><span data-stu-id="db1be-123">Exchange</span></span></p></td>
<td><p><span data-ttu-id="db1be-124">Exchange Server でホストされている UM アクセスのユーザーが無効になっています。</span><span class="sxs-lookup"><span data-stu-id="db1be-124">User has been disabled for hosted UM access by Exchange Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db1be-125">CsHostedVoiceMail = 1</span><span class="sxs-lookup"><span data-stu-id="db1be-125">CsHostedVoiceMail=1</span></span></p></td>
<td><p><span data-ttu-id="db1be-126">Lync Server</span><span class="sxs-lookup"><span data-stu-id="db1be-126">Lync Server</span></span></p></td>
<td><p><span data-ttu-id="db1be-127">ユーザーが Lync Server 2013 によってホストされた UM アクセスが有効になっている。</span><span class="sxs-lookup"><span data-stu-id="db1be-127">User has been enabled for hosted UM access by Lync Server 2013.</span></span> <span data-ttu-id="db1be-128">Lync Server 2013 ExUM ルーティングアプリケーションは、ルーティングの詳細について、ユーザーのホストされるボイスメールポリシーを確認します。</span><span class="sxs-lookup"><span data-stu-id="db1be-128">The Lync Server 2013 ExUM Routing application will check the user’s hosted voice mail policy for routing details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db1be-129">CsHostedVoiceMail = 0</span><span class="sxs-lookup"><span data-stu-id="db1be-129">CsHostedVoiceMail=0</span></span></p></td>
<td><p><span data-ttu-id="db1be-130">Lync Server</span><span class="sxs-lookup"><span data-stu-id="db1be-130">Lync Server</span></span></p></td>
<td><p><span data-ttu-id="db1be-131">Lync Server 2013 でホストされている UM アクセスのユーザーが無効になっている。</span><span class="sxs-lookup"><span data-stu-id="db1be-131">User has been disabled for hosted UM access by Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="db1be-132">属性に既に、Lync Server 2013 の1つ以外の値 (CSHostedVoiceMail = 0 または CSHostedVoiceMail = 1) 以外の値が含まれている場合、その属性は別のアプリケーションによって管理されている可能性があることを示す警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="db1be-132">If the attribute already has values other than one of the Lync Server 2013 key/value pairs (CSHostedVoiceMail=0 or CSHostedVoiceMail=1), a warning will indicate that the attribute may be managed by a different application.</span></span> <span data-ttu-id="db1be-133">たとえば、キー/値のペア ExchangeHostedVoiceMail = 0 または ExchangeHostedVoiceMail = 1 が既に存在する場合、警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="db1be-133">For example, a warning is displayed if the key/value pair ExchangeHostedVoiceMail=0 or ExchangeHostedVoiceMail=1 is already present.</span></span> <span data-ttu-id="db1be-134">この場合、値を変更するには、Active Directory を編集するか、次のコマンドレットを実行して値を null に設定します。</span><span class="sxs-lookup"><span data-stu-id="db1be-134">In that case, you can change the value by editing it the Active Directory, or run the following cmdlet to set the value to null:</span></span><BR><span data-ttu-id="db1be-135">Set-CsUser – identity user – HostedVoicemail $null</span><span class="sxs-lookup"><span data-stu-id="db1be-135">Set-CsUser –identity user –HostedVoicemail $null</span></span>



</div>

</div>

<div>

## <a name="enabling-users-for-hosted-voice-mail"></a><span data-ttu-id="db1be-136">ホストされたボイスメール用にユーザーを有効にする</span><span class="sxs-lookup"><span data-stu-id="db1be-136">Enabling Users for Hosted Voice Mail</span></span>

<span data-ttu-id="db1be-137">ユーザーのボイスメールの呼び出しをホストされた Exchange UM にルーティングできるようにするには、 *HostedVoiceMail*パラメーターの値を設定するために、Set-csuser コマンドレットを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="db1be-137">To enable a user’s voice mail calls to be routed to hosted Exchange UM, you must run the Set-CsUser cmdlet to set the value of the *HostedVoiceMail* parameter.</span></span> <span data-ttu-id="db1be-138">また、このパラメーターは、"ボイスメールの呼び出し" インジケーターを明るくするために、Lync Server 2013 にも通知します。</span><span class="sxs-lookup"><span data-stu-id="db1be-138">This parameter also signals Lync Server 2013 to light up the “call voice mail” indicator.</span></span>

  - <span data-ttu-id="db1be-139">次の例では、ホストされているボイスメールに対して Pilar Ackerman のユーザーアカウントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="db1be-139">The following example enables Pilar Ackerman’s user account for hosted voice mail:</span></span>
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $True
    
    <span data-ttu-id="db1be-140">このコマンドレットは、ホストされたボイスメールポリシー (グローバル、サイトレベル、またはユーザーごと) がこのユーザーに適用されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="db1be-140">The cmdlet verifies that a hosted voice mail policy (global, site-level or per-user) applies to this user.</span></span> <span data-ttu-id="db1be-141">ポリシーが適用されない場合、コマンドレットは失敗します。</span><span class="sxs-lookup"><span data-stu-id="db1be-141">If no policy applies, the cmdlet fails.</span></span>

  - <span data-ttu-id="db1be-142">次の例では、ホストされているボイスメールの Pilar Ackerman のユーザーアカウントを無効にします。</span><span class="sxs-lookup"><span data-stu-id="db1be-142">The following example disables Pilar Ackerman’s user account for hosted voice mail:</span></span>
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $False
    
    <span data-ttu-id="db1be-143">このコマンドレットは、ホストされているボイスメールポリシー (グローバル、サイトレベル、またはユーザーごと) がこのユーザーに適用されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="db1be-143">The cmdlet verifies that no hosted voice mail policy (global, site-level or per-user) applies to this user.</span></span> <span data-ttu-id="db1be-144">ポリシーが適用されると、コマンドレットは失敗します。</span><span class="sxs-lookup"><span data-stu-id="db1be-144">If a policy does apply, the cmdlet fails.</span></span>

<span data-ttu-id="db1be-145">Set-CsUser コマンドレットの使い方の詳細については、「Lync Server 管理シェルのドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db1be-145">For details about using the Set-CsUser cmdlet, see the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

