---
title: 'Lync Server 2013: Hosted Exchange ユーザー管理'
description: 'Lync Server 2013: Hosted Exchange ユーザー管理。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange user management
ms:assetid: e8723af5-0604-4d7d-bad2-463a9832efb4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399037(v=OCS.15)
ms:contentKeyID: 48185887
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ceda9352fc627fc7b762b5995d788ffafa159ae
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550113"
---
# <a name="hosted-exchange-user-management-in-lync-server-2013"></a><span data-ttu-id="640a0-103">Lync Server 2013 での Hosted Exchange ユーザー管理</span><span class="sxs-lookup"><span data-stu-id="640a0-103">Hosted Exchange user management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="640a0-104">_**トピックの最終更新日:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="640a0-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="640a0-105">ホストされた Exchange サービスにメールボックスがある Lync Server 2013 ユーザーにボイスメールサービスを提供するには、ホストボイスメールに対して自分のユーザーアカウントを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="640a0-105">To provide voice mail services for Lync Server 2013 users whose mailboxes are located on a hosted Exchange service, you must enable their user accounts for hosted voice mail.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="640a0-106">ホストボイスメールに対して Lync Server 2013 ユーザーを有効にするには、対応するユーザーアカウントに適用されるホストボイスメールポリシーを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="640a0-106">Before a Lync Server 2013 user can be enabled for hosted voice mail, a hosted voice mail policy that applies to the corresponding user account must be deployed.</span></span> <span data-ttu-id="640a0-107">ここで展開するポリシーは、有効化するユーザーに適用するのであれば、そのスコープがグローバルなものでも、サイト レベルのものでも、ユーザー単位のものでもかまいません。</span><span class="sxs-lookup"><span data-stu-id="640a0-107">The policy can be global, site, or per-user in scope, as long as it applies to the user whom you want to enable.</span></span> <span data-ttu-id="640a0-108">詳細については、「 <A href="lync-server-2013-hosted-voice-mail-policies.md">Lync Server 2013 のホストボイスメールポリシー</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="640a0-108">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="the-msexchucvoicemailsettings-attribute"></a><span data-ttu-id="640a0-109">msExchUCVoiceMailSettings 属性</span><span class="sxs-lookup"><span data-stu-id="640a0-109">The msExchUCVoiceMailSettings Attribute</span></span>

<span data-ttu-id="640a0-110">Lync Server 2013 は、 **msExchUCVoiceMailSettings**という名前の新しいユーザー属性を導入しています。これは、lync Server 2013 Active Directory スキーマの準備の一部として作成されます。</span><span class="sxs-lookup"><span data-stu-id="640a0-110">Lync Server 2013 introduces a new user attribute named **msExchUCVoiceMailSettings**, which is created as part of the Lync Server 2013 Active Directory schema preparation.</span></span> <span data-ttu-id="640a0-111">この複数値属性は、Lync Server 2013 と hosted Exchange サービスで共有されるボイスメール設定を保持します。</span><span class="sxs-lookup"><span data-stu-id="640a0-111">This multivalued attribute holds voice mail settings that are shared by Lync Server 2013 and the hosted Exchange service.</span></span>

<span data-ttu-id="640a0-112">Hosted Exchange サービスでは、Exchange UM の有効化プロセス、または Hosted Exchange Server へのメールボックスの転送プロセス中に、msExchUCVoiceMailSettings 属性の値が設定されることがあります。</span><span class="sxs-lookup"><span data-stu-id="640a0-112">The hosted Exchange service may in some cases set the value of the msExchUCVoiceMailSettings attribute in the process of enabling Exchange UM, or during the process of transferring mailboxes to a hosted Exchange Server.</span></span> <span data-ttu-id="640a0-113">この属性が Exchange によって設定されていない場合は、このトピックで前述したように、Lync Server 2013 管理者が Set-CsUser コマンドレットを実行して設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="640a0-113">If this attribute is not set by Exchange, the Lync Server 2013 administrator must set it by running the Set-CsUser cmdlet, as described earlier in this topic.</span></span>

<span data-ttu-id="640a0-114">次の表では、属性のキー/値ペアとその設定元について説明します。</span><span class="sxs-lookup"><span data-stu-id="640a0-114">The attribute’s key/value pairs and their authors are shown in the following table.</span></span>

### <a name="the-msexchucvoicemailsettings-attribute-keyvalue-pairs"></a><span data-ttu-id="640a0-115">msExchUCVoiceMailSettings 属性のキー/値ペア</span><span class="sxs-lookup"><span data-stu-id="640a0-115">The msExchUCVoiceMailSettings Attribute Key/Value Pairs</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="640a0-116">値</span><span class="sxs-lookup"><span data-stu-id="640a0-116">Value</span></span></th>
<th><span data-ttu-id="640a0-117">設定元</span><span class="sxs-lookup"><span data-stu-id="640a0-117">Author</span></span></th>
<th><span data-ttu-id="640a0-118">意味</span><span class="sxs-lookup"><span data-stu-id="640a0-118">Meaning</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="640a0-119">ExchangeHostedVoiceMail = 1</span><span class="sxs-lookup"><span data-stu-id="640a0-119">ExchangeHostedVoiceMail=1</span></span></p></td>
<td><p><span data-ttu-id="640a0-120">Exchange</span><span class="sxs-lookup"><span data-stu-id="640a0-120">Exchange</span></span></p></td>
<td><p><span data-ttu-id="640a0-121">ユーザーによるホスト型 UM へのアクセスは Exchange Server によって有効化されています。</span><span class="sxs-lookup"><span data-stu-id="640a0-121">User has been enabled for hosted UM access by Exchange Server.</span></span> <span data-ttu-id="640a0-122">Exchange UM ルーティングアプリケーションは、ルーティングの詳細について、ユーザーのホストボイスメールポリシーをチェックします。</span><span class="sxs-lookup"><span data-stu-id="640a0-122">The Exchange UM Routing application will check the user’s hosted voice mail policy for routing details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="640a0-123">ExchangeHostedVoiceMail = 0</span><span class="sxs-lookup"><span data-stu-id="640a0-123">ExchangeHostedVoiceMail=0</span></span></p></td>
<td><p><span data-ttu-id="640a0-124">Exchange</span><span class="sxs-lookup"><span data-stu-id="640a0-124">Exchange</span></span></p></td>
<td><p><span data-ttu-id="640a0-125">ユーザーによるホスト型 UM へのアクセスは Exchange Server によって無効化されています。</span><span class="sxs-lookup"><span data-stu-id="640a0-125">User has been disabled for hosted UM access by Exchange Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="640a0-126">CsHostedVoiceMail = 1</span><span class="sxs-lookup"><span data-stu-id="640a0-126">CsHostedVoiceMail=1</span></span></p></td>
<td><p><span data-ttu-id="640a0-127">Lync Server</span><span class="sxs-lookup"><span data-stu-id="640a0-127">Lync Server</span></span></p></td>
<td><p><span data-ttu-id="640a0-128">ユーザーが Lync Server 2013 によってホストされた UM アクセスが有効になっている。</span><span class="sxs-lookup"><span data-stu-id="640a0-128">User has been enabled for hosted UM access by Lync Server 2013.</span></span> <span data-ttu-id="640a0-129">Lync Server 2013 ExUM ルーティングアプリケーションは、ルーティングの詳細についてユーザーのホストボイスメールポリシーをチェックします。</span><span class="sxs-lookup"><span data-stu-id="640a0-129">The Lync Server 2013 ExUM Routing application will check the user’s hosted voice mail policy for routing details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="640a0-130">CsHostedVoiceMail = 0</span><span class="sxs-lookup"><span data-stu-id="640a0-130">CsHostedVoiceMail=0</span></span></p></td>
<td><p><span data-ttu-id="640a0-131">Lync Server</span><span class="sxs-lookup"><span data-stu-id="640a0-131">Lync Server</span></span></p></td>
<td><p><span data-ttu-id="640a0-132">Lync Server 2013 によるホスト型 UM へのアクセスがユーザーに対して無効になっています。</span><span class="sxs-lookup"><span data-stu-id="640a0-132">User has been disabled for hosted UM access by Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="640a0-133">属性に既に Lync Server 2013 のキー/値ペア (CSHostedVoiceMail = 0 または CSHostedVoiceMail = 1) 以外の値が設定されている場合は、その属性が別のアプリケーションによって管理されている可能性があることを示す警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="640a0-133">If the attribute already has values other than one of the Lync Server 2013 key/value pairs (CSHostedVoiceMail=0 or CSHostedVoiceMail=1), a warning will indicate that the attribute may be managed by a different application.</span></span> <span data-ttu-id="640a0-134">たとえば、キー/値ペア ExchangeHostedVoiceMail=0 または ExchangeHostedVoiceMail=1 がすでに存在している場合には、警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="640a0-134">For example, a warning is displayed if the key/value pair ExchangeHostedVoiceMail=0 or ExchangeHostedVoiceMail=1 is already present.</span></span> <span data-ttu-id="640a0-135">そのようなときには、Active Directory で値を変更するか、または次のコマンドレットを実行して、値を Null に設定します。</span><span class="sxs-lookup"><span data-stu-id="640a0-135">In that case, you can change the value by editing it the Active Directory, or run the following cmdlet to set the value to null:</span></span><BR><span data-ttu-id="640a0-136">Set-CsUser –identity user –HostedVoicemail $null</span><span class="sxs-lookup"><span data-stu-id="640a0-136">Set-CsUser –identity user –HostedVoicemail $null</span></span>



</div>

</div>

<div>

## <a name="enabling-users-for-hosted-voice-mail"></a><span data-ttu-id="640a0-137">ユーザーによるホスト ボイス メールの有効化</span><span class="sxs-lookup"><span data-stu-id="640a0-137">Enabling Users for Hosted Voice Mail</span></span>

<span data-ttu-id="640a0-138">ユーザーのボイス メール通話が Hosted Exchange UM へルーティングされるようにするには、Set-CsUser コマンドレットを実行して、*HostedVoiceMail* パラメーターの値を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="640a0-138">To enable a user’s voice mail calls to be routed to hosted Exchange UM, you must run the Set-CsUser cmdlet to set the value of the *HostedVoiceMail* parameter.</span></span> <span data-ttu-id="640a0-139">また、このパラメーターは Lync Server 2013 に通知して、"ボイスメールの呼び出し" インジケーターを明るくします。</span><span class="sxs-lookup"><span data-stu-id="640a0-139">This parameter also signals Lync Server 2013 to light up the “call voice mail” indicator.</span></span>

  - <span data-ttu-id="640a0-140">次の例では、Pilar Ackerman のユーザー アカウントでホスト ボイス メールを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="640a0-140">The following example enables Pilar Ackerman’s user account for hosted voice mail:</span></span>
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $True
    
    <span data-ttu-id="640a0-p108">これは、ホスト ボイス メールのポリシー (グローバル、サイトレベル、またはユーザー単位) がこのユーザーに適用されていることを確認するコマンドレットです。 適用されるポリシーがない場合には、このコマンドレットは失敗します。</span><span class="sxs-lookup"><span data-stu-id="640a0-p108">The cmdlet verifies that a hosted voice mail policy (global, site-level or per-user) applies to this user. If no policy applies, the cmdlet fails.</span></span>

  - <span data-ttu-id="640a0-143">次の例では、Pilar Ackerman のユーザー アカウントでホスト ボイス メールを使用できないようにします。</span><span class="sxs-lookup"><span data-stu-id="640a0-143">The following example disables Pilar Ackerman’s user account for hosted voice mail:</span></span>
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $False
    
    <span data-ttu-id="640a0-p109">これは、ホスト ボイス メールのポリシー (グローバル、サイトレベル、またはユーザー単位) がこのユーザーに適用されていないことを確認するコマンドレットです。 適用されるポリシーがある場合には、このコマンドレットは失敗します。</span><span class="sxs-lookup"><span data-stu-id="640a0-p109">The cmdlet verifies that no hosted voice mail policy (global, site-level or per-user) applies to this user. If a policy does apply, the cmdlet fails.</span></span>

<span data-ttu-id="640a0-146">Set-CsUser コマンドレットの使用の詳細については、「Lync Server Management Shell」のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="640a0-146">For details about using the Set-CsUser cmdlet, see the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

