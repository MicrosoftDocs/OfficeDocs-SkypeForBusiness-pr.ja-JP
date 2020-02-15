---
title: 'Lync Server 2013: ユーザーごとのホストボイスメールポリシーの作成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a per-user hosted voice mail policy
ms:assetid: 39018a7c-e0c3-46a2-be4e-05604ec67a50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425867(v=OCS.15)
ms:contentKeyID: 48183902
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 055d65fe691d99c8b960ebed088ba47cbcb2f988
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034879"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="4cb44-102">Lync Server 2013 でユーザーごとのホストボイスメールポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="4cb44-102">Create a per-user hosted voice mail policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4cb44-103">_**トピックの最終更新日:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="4cb44-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="4cb44-104">\*\* ユーザー単位のポリシーは、個々のユーザー、グループ、および連絡先オブジェクトにのみ影響します。</span><span class="sxs-lookup"><span data-stu-id="4cb44-104">A *per-user* policy can only impact individual users, groups, and contact objects.</span></span> <span data-ttu-id="4cb44-105">ユーザー単位のポリシーを展開するには、ポリシーを 1 つ以上のユーザー、グループ、または連絡先オブジェクトに明示的に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="4cb44-105">To deploy a per-user policy, you must explicitly assign the policy to one or more users, groups, or contact objects.</span></span> <span data-ttu-id="4cb44-106">詳細については、「 [Lync Server 2013 でユーザーごとにホストされるボイスメールポリシーを割り当てる](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4cb44-106">For details, see [Assign a per-user hosted voice mail policy in Lync Server 2013](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md).</span></span>

<span data-ttu-id="4cb44-107">ユーザー単位のホストボイスメールポリシーの使用の詳細については、以下のコマンドレットについて、「Lync Server Management Shell」のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4cb44-107">For details about working with per-user hosted voice mail policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="4cb44-108">Set-cshostedvoicemailpolicy</span><span class="sxs-lookup"><span data-stu-id="4cb44-108">New-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="4cb44-109">Set-cshostedvoicemailpolicy</span><span class="sxs-lookup"><span data-stu-id="4cb44-109">Set-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="4cb44-110">Get-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="4cb44-110">Get-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-per-user-hosted-voice-mail-policy"></a><span data-ttu-id="4cb44-111">ユーザー単位のホスト ボイス メール ポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="4cb44-111">To create a per-user hosted voice mail policy</span></span>

1.  <span data-ttu-id="4cb44-112">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="4cb44-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="4cb44-p102">New-CsHostedVoicemailPolicy コマンドレットを実行して、ポリシーを作成します。たとえば、以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="4cb44-p102">Run the New-CsHostedVoicemailPolicy cmdlet to create the policy. For example, run:</span></span>
    
        New-CsHostedVoicemailPolicy -Identity ExRedmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for Redmond users." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    <span data-ttu-id="4cb44-115">前の例では、ユーザー単位のスコープを使用してホスト ボイス メール ポリシーを作成し、次のパラメーターを設定しています。</span><span class="sxs-lookup"><span data-stu-id="4cb44-115">The previous example creates a hosted voice mail policy with per-user scope, and sets the following parameters:</span></span>
    
      - <span data-ttu-id="4cb44-p103">**Identity** では、ポリシーの一意の識別子を指定します。これにはスコープも含まれます。 ユーザー単位のスコープを使用するポリシーの場合、このパラメーター値には単純な文字列 (ExRedmond など) を指定します。</span><span class="sxs-lookup"><span data-stu-id="4cb44-p103">**Identity** specifies a unique identifier for the policy, which includes the scope. For a policy with per-user scope, this parameter value is specified as a simple string, for example, ExRedmond.</span></span>
    
      - <span data-ttu-id="4cb44-p104">**Destination** では、Hosted Exchange UM サービスの完全修飾ドメイン名 (FQDN) を指定します。このパラメーターは省略可能ですが、ユーザーに割り当てられているポリシーで送信先の値が設定されていないと、ユーザーのホスト ボイス メールを有効にしようとしても失敗します。</span><span class="sxs-lookup"><span data-stu-id="4cb44-p104">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Exchange UM service. This parameter is optional, but if you attempt to enable a user for hosted voice mail and the user’s assigned policy does not have a Destination value, the enable will fail.</span></span>
    
      - <span data-ttu-id="4cb44-120">**Description** では、ポリシーに関する説明情報を指定します (オプション)。</span><span class="sxs-lookup"><span data-stu-id="4cb44-120">**Description** provides optional descriptive information about the policy.</span></span>
    
      - <span data-ttu-id="4cb44-121">**Organization** Lync Server 2013 のホームユーザーが持つ Exchange テナントのコンマ区切りリストを指定します。</span><span class="sxs-lookup"><span data-stu-id="4cb44-121">**Organization** specifies a comma-separated list of the Exchange tenants that home Lync Server 2013 users.</span></span> <span data-ttu-id="4cb44-122">各テナントは、Hosted Exchange UM サービス上のテナントの FQDN として指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4cb44-122">Each tenant must be specified as the FQDN of that tenant on the hosted Exchange UM service.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4cb44-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="4cb44-123">See Also</span></span>


[<span data-ttu-id="4cb44-124">Lync Server 2013 でユーザーごとにホストされるボイスメールポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="4cb44-124">Assign a per-user hosted voice mail policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

