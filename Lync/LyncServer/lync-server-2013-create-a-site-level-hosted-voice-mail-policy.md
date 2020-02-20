---
title: 'Lync Server 2013: サイトレベルのホストボイスメールポリシーの作成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a site-level hosted voice mail policy
ms:assetid: 145892c8-a6ca-45fb-9e83-786f709dd775
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398216(v=OCS.15)
ms:contentKeyID: 48183481
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd227787ae790b280c98c73e9ca0bb516d7dc092
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145566"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-site-level-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="de8ee-102">Lync Server 2013 でサイトレベルのホストボイスメールポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="de8ee-102">Create a site-level hosted voice mail policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="de8ee-103">_**トピックの最終更新日:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="de8ee-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="de8ee-p101">\*\* サイト ポリシーは、このポリシーが定義されているサイトに所属するすべてのユーザーに影響します。 Hosted Exchange UM にアクセスできるように構成されているユーザーにユーザー単位のポリシーが割り当てられていない場合には、サイト ポリシーが適用されます。 サイト ポリシーを展開してない場合は、グローバル ポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="de8ee-p101">A *site* policy can impact all users that are homed on the site for which the policy is defined. If a user is configured for hosted Exchange UM access and has not been assigned a Per-user policy, the site policy applies. If you have not deployed a site policy, the global policy applies.</span></span>

<span data-ttu-id="de8ee-107">サイトポリシーの構成の詳細については、以下のコマンドレットの Lync Server Management Shell のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="de8ee-107">For details about configuring site policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="de8ee-108">New-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="de8ee-108">New-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="de8ee-109">Set-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="de8ee-109">Set-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="de8ee-110">Get-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="de8ee-110">Get-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-site-hosted-voice-mail-policy"></a><span data-ttu-id="de8ee-111">サイトのホスト ボイス メール ポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="de8ee-111">To create a site hosted voice mail policy</span></span>

1.  <span data-ttu-id="de8ee-112">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="de8ee-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="de8ee-p102">New-CsHostedVoicemailPolicy コマンドレットを実行して、ポリシーを作成します。 たとえば、以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="de8ee-p102">Run the New-CsHostedVoicemailPolicy cmdlet to create the policy. For example, run:</span></span>
    
        New-CsHostedVoicemailPolicy -Identity site:Redmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for the Redmond site." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    <span data-ttu-id="de8ee-115">この例では、サイト スコープを使用してホスト ボイス メール ポリシーを作成し、次のパラメーターを設定しています。</span><span class="sxs-lookup"><span data-stu-id="de8ee-115">This example creates a hosted voice mail policy with site scope, and sets the following parameters:</span></span>
    
      - <span data-ttu-id="de8ee-116">**Identity**は、スコープを含むポリシーの一意識別子を指定します。</span><span class="sxs-lookup"><span data-stu-id="de8ee-116">**Identity** specifies a unique identifier for the policy, which includes the scope.</span></span> <span data-ttu-id="de8ee-117">サイトスコープを持つポリシーの場合は、Identity パラメーターの値を形式`site:` \* \<名\>\* で指定する必要があり`site:Redmond`ます (例:)。</span><span class="sxs-lookup"><span data-stu-id="de8ee-117">For a policy with site scope, the Identity parameter value must be specified in the format `site:`*\<name\>*, for example, `site:Redmond`.</span></span>
    
      - <span data-ttu-id="de8ee-p104">**Destination** では、Hosted Exchange UM サービスの完全修飾ドメイン名 (FQDN) を指定します。このパラメーターは省略可能ですが、ユーザーに割り当てられているポリシーで送信先の値が設定されていないと、ユーザーのホスト ボイス メールを有効にしようとしても失敗します。</span><span class="sxs-lookup"><span data-stu-id="de8ee-p104">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Exchange UM service. This parameter is optional, but if you attempt to enable a user for hosted voice mail and the user’s assigned policy does not have a Destination value, the enable will fail.</span></span>
    
      - <span data-ttu-id="de8ee-120">**Description** では、ポリシーに関する説明情報を指定します (オプション)。</span><span class="sxs-lookup"><span data-stu-id="de8ee-120">**Description** provides optional descriptive information about the policy.</span></span>
    
      - <span data-ttu-id="de8ee-121">**Organization** Lync Server 2013 のホームユーザーが持つ Exchange テナントのコンマ区切りリストを指定します。</span><span class="sxs-lookup"><span data-stu-id="de8ee-121">**Organization** specifies a comma-separated list of the Exchange tenants that home Lync Server 2013 users.</span></span> <span data-ttu-id="de8ee-122">各テナントは、Hosted Exchange UM サービス上のテナントの FQDN として指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="de8ee-122">Each tenant must be specified as the FQDN of that tenant on the hosted Exchange UM service.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

