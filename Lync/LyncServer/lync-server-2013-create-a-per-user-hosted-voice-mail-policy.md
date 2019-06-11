---
title: 'Lync Server 2013: ユーザーごとにホストされるボイスメールポリシーを作成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a per-user hosted voice mail policy
ms:assetid: 39018a7c-e0c3-46a2-be4e-05604ec67a50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425867(v=OCS.15)
ms:contentKeyID: 48183902
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d09638c28c1cbd2b068972aff169376508325885
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840077"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="5e557-102">Lync Server 2013 でユーザーごとにホストされるボイスメールのポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="5e557-102">Create a per-user hosted voice mail policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5e557-103">_**最終更新日:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="5e557-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="5e557-104">*ユーザーごと*のポリシーは、個々のユーザー、グループ、連絡先オブジェクトにのみ影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5e557-104">A *per-user* policy can only impact individual users, groups, and contact objects.</span></span> <span data-ttu-id="5e557-105">ユーザーごとのポリシーを展開するには、ポリシーを1つ以上のユーザー、グループ、または連絡先オブジェクトに明示的に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e557-105">To deploy a per-user policy, you must explicitly assign the policy to one or more users, groups, or contact objects.</span></span> <span data-ttu-id="5e557-106">詳細については、「 [Lync Server 2013 でユーザーごとにホストされるボイスメールのポリシーを割り当てる](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e557-106">For details, see [Assign a per-user hosted voice mail policy in Lync Server 2013](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md).</span></span>

<span data-ttu-id="5e557-107">ユーザーごとにホストされるボイスメールポリシーの使用について詳しくは、次のコマンドレットの Lync Server 管理シェルに関するドキュメントをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5e557-107">For details about working with per-user hosted voice mail policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="5e557-108">新規-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="5e557-108">New-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="5e557-109">Set-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="5e557-109">Set-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="5e557-110">Get-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="5e557-110">Get-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-per-user-hosted-voice-mail-policy"></a><span data-ttu-id="5e557-111">ユーザーごとにホストされるボイスメールポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="5e557-111">To create a per-user hosted voice mail policy</span></span>

1.  <span data-ttu-id="5e557-112">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="5e557-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="5e557-113">CsHostedVoicemailPolicy コマンドレットを実行して、ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="5e557-113">Run the New-CsHostedVoicemailPolicy cmdlet to create the policy.</span></span> <span data-ttu-id="5e557-114">たとえば、以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="5e557-114">For example, run:</span></span>
    
        New-CsHostedVoicemailPolicy -Identity ExRedmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for Redmond users." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    <span data-ttu-id="5e557-115">上の例では、ホストされたボイスメールポリシーをユーザーごとのスコープで作成し、次のパラメーターを設定します。</span><span class="sxs-lookup"><span data-stu-id="5e557-115">The previous example creates a hosted voice mail policy with per-user scope, and sets the following parameters:</span></span>
    
      - <span data-ttu-id="5e557-116">**Id**は、スコープを含むポリシーの一意の識別子を指定します。</span><span class="sxs-lookup"><span data-stu-id="5e557-116">**Identity** specifies a unique identifier for the policy, which includes the scope.</span></span> <span data-ttu-id="5e557-117">ユーザーごとのスコープを持つポリシーの場合、このパラメーター値は単純な文字列 (ExRedmond など) として指定されます。</span><span class="sxs-lookup"><span data-stu-id="5e557-117">For a policy with per-user scope, this parameter value is specified as a simple string, for example, ExRedmond.</span></span>
    
      - <span data-ttu-id="5e557-118">[ **Destination** ] は、ホストされた Exchange UM サービスの完全修飾ドメイン名 (FQDN) を指定します。</span><span class="sxs-lookup"><span data-stu-id="5e557-118">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Exchange UM service.</span></span> <span data-ttu-id="5e557-119">このパラメーターは省略可能ですが、ホストされたボイスメールに対してユーザーを有効にしようとしても、ユーザーに割り当てられているポリシーに送信先の値がない場合、有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="5e557-119">This parameter is optional, but if you attempt to enable a user for hosted voice mail and the user’s assigned policy does not have a Destination value, the enable will fail.</span></span>
    
      - <span data-ttu-id="5e557-120">**説明**ポリシーに関するオプションの説明情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="5e557-120">**Description** provides optional descriptive information about the policy.</span></span>
    
      - <span data-ttu-id="5e557-121">[**組織**] は、Lync Server 2013 のホームユーザーである Exchange テナントのコンマ区切りリストを指定します。</span><span class="sxs-lookup"><span data-stu-id="5e557-121">**Organization** specifies a comma-separated list of the Exchange tenants that home Lync Server 2013 users.</span></span> <span data-ttu-id="5e557-122">各テナントは、ホストされた Exchange UM サービスでそのテナントの FQDN として指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e557-122">Each tenant must be specified as the FQDN of that tenant on the hosted Exchange UM service.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5e557-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="5e557-123">See Also</span></span>


[<span data-ttu-id="5e557-124">Lync Server 2013 でユーザーごとにホストされるボイスメールのポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="5e557-124">Assign a per-user hosted voice mail policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

