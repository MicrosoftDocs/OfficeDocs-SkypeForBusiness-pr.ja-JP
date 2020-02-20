---
title: 'Lync Server 2013: Hosted Exchange ユーザー管理'
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
ms.openlocfilehash: 6ab62a60bcaf78cbbefc69aa754587237da0916d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154919"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-user-management-in-lync-server-2013"></a><span data-ttu-id="0b990-102">Lync Server 2013 での Hosted Exchange ユーザー管理</span><span class="sxs-lookup"><span data-stu-id="0b990-102">Hosted Exchange user management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0b990-103">_**トピックの最終更新日:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="0b990-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="0b990-104">ホストされた Exchange サービスにメールボックスがある Lync Server 2013 ユーザーにボイスメールサービスを提供するには、ホストボイスメールに対して自分のユーザーアカウントを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b990-104">To provide voice mail services for Lync Server 2013 users whose mailboxes are located on a hosted Exchange service, you must enable their user accounts for hosted voice mail.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0b990-105">ホストボイスメールに対して Lync Server 2013 ユーザーを有効にするには、対応するユーザーアカウントに適用されるホストボイスメールポリシーを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b990-105">Before a Lync Server 2013 user can be enabled for hosted voice mail, a hosted voice mail policy that applies to the corresponding user account must be deployed.</span></span> <span data-ttu-id="0b990-106">ここで展開するポリシーは、有効化するユーザーに適用するのであれば、そのスコープがグローバルなものでも、サイト レベルのものでも、ユーザー単位のものでもかまいません。</span><span class="sxs-lookup"><span data-stu-id="0b990-106">The policy can be global, site, or per-user in scope, as long as it applies to the user whom you want to enable.</span></span> <span data-ttu-id="0b990-107">詳細については、「 <A href="lync-server-2013-hosted-voice-mail-policies.md">Lync Server 2013 のホストボイスメールポリシー</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b990-107">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="the-msexchucvoicemailsettings-attribute"></a><span data-ttu-id="0b990-108">msExchUCVoiceMailSettings 属性</span><span class="sxs-lookup"><span data-stu-id="0b990-108">The msExchUCVoiceMailSettings Attribute</span></span>

<span data-ttu-id="0b990-109">Lync Server 2013 は、 **msExchUCVoiceMailSettings**という名前の新しいユーザー属性を導入しています。これは、lync Server 2013 Active Directory スキーマの準備の一部として作成されます。</span><span class="sxs-lookup"><span data-stu-id="0b990-109">Lync Server 2013 introduces a new user attribute named **msExchUCVoiceMailSettings**, which is created as part of the Lync Server 2013 Active Directory schema preparation.</span></span> <span data-ttu-id="0b990-110">この複数値属性は、Lync Server 2013 と hosted Exchange サービスで共有されるボイスメール設定を保持します。</span><span class="sxs-lookup"><span data-stu-id="0b990-110">This multivalued attribute holds voice mail settings that are shared by Lync Server 2013 and the hosted Exchange service.</span></span>

<span data-ttu-id="0b990-111">Hosted Exchange サービスでは、Exchange UM の有効化プロセス、または Hosted Exchange Server へのメールボックスの転送プロセス中に、msExchUCVoiceMailSettings 属性の値が設定されることがあります。</span><span class="sxs-lookup"><span data-stu-id="0b990-111">The hosted Exchange service may in some cases set the value of the msExchUCVoiceMailSettings attribute in the process of enabling Exchange UM, or during the process of transferring mailboxes to a hosted Exchange Server.</span></span> <span data-ttu-id="0b990-112">この属性が Exchange によって設定されていない場合、Lync Server 2013 管理者は、このトピックで前述したように、Set-CsUser コマンドレットを実行して設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b990-112">If this attribute is not set by Exchange, the Lync Server 2013 administrator must set it by running the Set-CsUser cmdlet, as described earlier in this topic.</span></span>

<span data-ttu-id="0b990-113">次の表では、属性のキー/値ペアとその設定元について説明します。</span><span class="sxs-lookup"><span data-stu-id="0b990-113">The attribute’s key/value pairs and their authors are shown in the following table.</span></span>

### <a name="the-msexchucvoicemailsettings-attribute-keyvalue-pairs"></a><span data-ttu-id="0b990-114">msExchUCVoiceMailSettings 属性のキー/値ペア</span><span class="sxs-lookup"><span data-stu-id="0b990-114">The msExchUCVoiceMailSettings Attribute Key/Value Pairs</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0b990-115">値</span><span class="sxs-lookup"><span data-stu-id="0b990-115">Value</span></span></th>
<th><span data-ttu-id="0b990-116">設定元</span><span class="sxs-lookup"><span data-stu-id="0b990-116">Author</span></span></th>
<th><span data-ttu-id="0b990-117">意味</span><span class="sxs-lookup"><span data-stu-id="0b990-117">Meaning</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0b990-118">ExchangeHostedVoiceMail = 1</span><span class="sxs-lookup"><span data-stu-id="0b990-118">ExchangeHostedVoiceMail=1</span></span></p></td>
<td><p><span data-ttu-id="0b990-119">Exchange</span><span class="sxs-lookup"><span data-stu-id="0b990-119">Exchange</span></span></p></td>
<td><p><span data-ttu-id="0b990-120">ユーザーによるホスト型 UM へのアクセスは Exchange Server によって有効化されています。</span><span class="sxs-lookup"><span data-stu-id="0b990-120">User has been enabled for hosted UM access by Exchange Server.</span></span> <span data-ttu-id="0b990-121">Exchange UM ルーティングアプリケーションは、ルーティングの詳細について、ユーザーのホストボイスメールポリシーをチェックします。</span><span class="sxs-lookup"><span data-stu-id="0b990-121">The Exchange UM Routing application will check the user’s hosted voice mail policy for routing details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b990-122">ExchangeHostedVoiceMail = 0</span><span class="sxs-lookup"><span data-stu-id="0b990-122">ExchangeHostedVoiceMail=0</span></span></p></td>
<td><p><span data-ttu-id="0b990-123">Exchange</span><span class="sxs-lookup"><span data-stu-id="0b990-123">Exchange</span></span></p></td>
<td><p><span data-ttu-id="0b990-124">ユーザーによるホスト型 UM へのアクセスは Exchange Server によって無効化されています。</span><span class="sxs-lookup"><span data-stu-id="0b990-124">User has been disabled for hosted UM access by Exchange Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b990-125">CsHostedVoiceMail = 1</span><span class="sxs-lookup"><span data-stu-id="0b990-125">CsHostedVoiceMail=1</span></span></p></td>
<td><p><span data-ttu-id="0b990-126">Lync Server</span><span class="sxs-lookup"><span data-stu-id="0b990-126">Lync Server</span></span></p></td>
<td><p><span data-ttu-id="0b990-127">ユーザーが Lync Server 2013 によってホストされた UM アクセスが有効になっている。</span><span class="sxs-lookup"><span data-stu-id="0b990-127">User has been enabled for hosted UM access by Lync Server 2013.</span></span> <span data-ttu-id="0b990-128">Lync Server 2013 ExUM ルーティングアプリケーションは、ルーティングの詳細についてユーザーのホストボイスメールポリシーをチェックします。</span><span class="sxs-lookup"><span data-stu-id="0b990-128">The Lync Server 2013 ExUM Routing application will check the user’s hosted voice mail policy for routing details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b990-129">CsHostedVoiceMail = 0</span><span class="sxs-lookup"><span data-stu-id="0b990-129">CsHostedVoiceMail=0</span></span></p></td>
<td><p><span data-ttu-id="0b990-130">Lync Server</span><span class="sxs-lookup"><span data-stu-id="0b990-130">Lync Server</span></span></p></td>
<td><p><span data-ttu-id="0b990-131">Lync Server 2013 によるホスト型 UM へのアクセスがユーザーに対して無効になっています。</span><span class="sxs-lookup"><span data-stu-id="0b990-131">User has been disabled for hosted UM access by Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="0b990-132">属性に既に Lync Server 2013 のキー/値ペア (CSHostedVoiceMail = 0 または CSHostedVoiceMail = 1) 以外の値が設定されている場合は、その属性が別のアプリケーションによって管理されている可能性があることを示す警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0b990-132">If the attribute already has values other than one of the Lync Server 2013 key/value pairs (CSHostedVoiceMail=0 or CSHostedVoiceMail=1), a warning will indicate that the attribute may be managed by a different application.</span></span> <span data-ttu-id="0b990-133">たとえば、キー/値ペア ExchangeHostedVoiceMail=0 または ExchangeHostedVoiceMail=1 がすでに存在している場合には、警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0b990-133">For example, a warning is displayed if the key/value pair ExchangeHostedVoiceMail=0 or ExchangeHostedVoiceMail=1 is already present.</span></span> <span data-ttu-id="0b990-134">そのようなときには、Active Directory で値を変更するか、または次のコマンドレットを実行して、値を Null に設定します。</span><span class="sxs-lookup"><span data-stu-id="0b990-134">In that case, you can change the value by editing it the Active Directory, or run the following cmdlet to set the value to null:</span></span><BR><span data-ttu-id="0b990-135">Set-CsUser –identity user –HostedVoicemail $null</span><span class="sxs-lookup"><span data-stu-id="0b990-135">Set-CsUser –identity user –HostedVoicemail $null</span></span>



</div>

</div>

<div>

## <a name="enabling-users-for-hosted-voice-mail"></a><span data-ttu-id="0b990-136">ユーザーによるホスト ボイス メールの有効化</span><span class="sxs-lookup"><span data-stu-id="0b990-136">Enabling Users for Hosted Voice Mail</span></span>

<span data-ttu-id="0b990-137">ユーザーのボイス メール通話が Hosted Exchange UM へルーティングされるようにするには、Set-CsUser コマンドレットを実行して、*HostedVoiceMail* パラメーターの値を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b990-137">To enable a user’s voice mail calls to be routed to hosted Exchange UM, you must run the Set-CsUser cmdlet to set the value of the *HostedVoiceMail* parameter.</span></span> <span data-ttu-id="0b990-138">また、このパラメーターは Lync Server 2013 に通知して、"ボイスメールの呼び出し" インジケーターを明るくします。</span><span class="sxs-lookup"><span data-stu-id="0b990-138">This parameter also signals Lync Server 2013 to light up the “call voice mail” indicator.</span></span>

  - <span data-ttu-id="0b990-139">次の例では、Pilar Ackerman のユーザー アカウントでホスト ボイス メールを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="0b990-139">The following example enables Pilar Ackerman’s user account for hosted voice mail:</span></span>
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $True
    
    <span data-ttu-id="0b990-p108">これは、ホスト ボイス メールのポリシー (グローバル、サイトレベル、またはユーザー単位) がこのユーザーに適用されていることを確認するコマンドレットです。 適用されるポリシーがない場合には、このコマンドレットは失敗します。</span><span class="sxs-lookup"><span data-stu-id="0b990-p108">The cmdlet verifies that a hosted voice mail policy (global, site-level or per-user) applies to this user. If no policy applies, the cmdlet fails.</span></span>

  - <span data-ttu-id="0b990-142">次の例では、Pilar Ackerman のユーザー アカウントでホスト ボイス メールを使用できないようにします。</span><span class="sxs-lookup"><span data-stu-id="0b990-142">The following example disables Pilar Ackerman’s user account for hosted voice mail:</span></span>
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $False
    
    <span data-ttu-id="0b990-p109">これは、ホスト ボイス メールのポリシー (グローバル、サイトレベル、またはユーザー単位) がこのユーザーに適用されていないことを確認するコマンドレットです。 適用されるポリシーがある場合には、このコマンドレットは失敗します。</span><span class="sxs-lookup"><span data-stu-id="0b990-p109">The cmdlet verifies that no hosted voice mail policy (global, site-level or per-user) applies to this user. If a policy does apply, the cmdlet fails.</span></span>

<span data-ttu-id="0b990-145">Set-CsUser コマンドレットの使用の詳細については、「Lync Server Management Shell」のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b990-145">For details about using the Set-CsUser cmdlet, see the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

