---
title: 'Lync Server 2013: サイトレベルでホストされるボイスメールポリシーを作成する'
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
ms.openlocfilehash: 6aeae2e533bd62cf1f3e24e7ceff69b870ebc7b3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740367"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-site-level-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="bbce3-102">Lync Server 2013 でサイトレベルでホストされるボイスメールのポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="bbce3-102">Create a site-level hosted voice mail policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bbce3-103">_**最終更新日:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="bbce3-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="bbce3-104">*サイト*ポリシーは、ポリシーが定義されているサイトをホームにしているすべてのユーザーに影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bbce3-104">A *site* policy can impact all users that are homed on the site for which the policy is defined.</span></span> <span data-ttu-id="bbce3-105">ユーザーがホストされた Exchange UM アクセス用に構成されていて、ユーザーごとのポリシーが割り当てられていない場合は、サイトポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="bbce3-105">If a user is configured for hosted Exchange UM access and has not been assigned a Per-user policy, the site policy applies.</span></span> <span data-ttu-id="bbce3-106">サイトポリシーを展開していない場合は、グローバルポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="bbce3-106">If you have not deployed a site policy, the global policy applies.</span></span>

<span data-ttu-id="bbce3-107">サイトポリシーの構成の詳細については、次のコマンドレットの Lync Server 管理シェルに関するドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bbce3-107">For details about configuring site policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="bbce3-108">New-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="bbce3-108">New-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="bbce3-109">Set-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="bbce3-109">Set-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="bbce3-110">Get-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="bbce3-110">Get-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-site-hosted-voice-mail-policy"></a><span data-ttu-id="bbce3-111">サイトでホストされているボイスメールポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="bbce3-111">To create a site hosted voice mail policy</span></span>

1.  <span data-ttu-id="bbce3-112">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="bbce3-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="bbce3-113">CsHostedVoicemailPolicy コマンドレットを実行して、ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="bbce3-113">Run the New-CsHostedVoicemailPolicy cmdlet to create the policy.</span></span> <span data-ttu-id="bbce3-114">たとえば、以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="bbce3-114">For example, run:</span></span>
    
        New-CsHostedVoicemailPolicy -Identity site:Redmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for the Redmond site." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    <span data-ttu-id="bbce3-115">この例では、サイトのスコープを持つホストされたボイスメールのポリシーを作成し、次のパラメーターを設定します。</span><span class="sxs-lookup"><span data-stu-id="bbce3-115">This example creates a hosted voice mail policy with site scope, and sets the following parameters:</span></span>
    
      - <span data-ttu-id="bbce3-116">**Id**は、スコープを含むポリシーの一意の識別子を指定します。</span><span class="sxs-lookup"><span data-stu-id="bbce3-116">**Identity** specifies a unique identifier for the policy, which includes the scope.</span></span> <span data-ttu-id="bbce3-117">サイトスコープを持つポリシーの場合、id パラメーター値は形式`site:` \* \<名\>\* で指定する必要があります。 `site:Redmond`たとえば、などです。</span><span class="sxs-lookup"><span data-stu-id="bbce3-117">For a policy with site scope, the Identity parameter value must be specified in the format `site:`*\<name\>*, for example, `site:Redmond`.</span></span>
    
      - <span data-ttu-id="bbce3-118">[ **Destination** ] は、ホストされた Exchange UM サービスの完全修飾ドメイン名 (FQDN) を指定します。</span><span class="sxs-lookup"><span data-stu-id="bbce3-118">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Exchange UM service.</span></span> <span data-ttu-id="bbce3-119">このパラメーターは省略可能ですが、ホストされたボイスメールに対してユーザーを有効にしようとしても、ユーザーに割り当てられているポリシーに送信先の値がない場合、有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="bbce3-119">This parameter is optional, but if you attempt to enable a user for hosted voice mail and the user’s assigned policy does not have a Destination value, the enable will fail.</span></span>
    
      - <span data-ttu-id="bbce3-120">**説明**ポリシーに関するオプションの説明情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="bbce3-120">**Description** provides optional descriptive information about the policy.</span></span>
    
      - <span data-ttu-id="bbce3-121">[**組織**] は、Lync Server 2013 のホームユーザーである Exchange テナントのコンマ区切りリストを指定します。</span><span class="sxs-lookup"><span data-stu-id="bbce3-121">**Organization** specifies a comma-separated list of the Exchange tenants that home Lync Server 2013 users.</span></span> <span data-ttu-id="bbce3-122">各テナントは、ホストされた Exchange UM サービスでそのテナントの FQDN として指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bbce3-122">Each tenant must be specified as the FQDN of that tenant on the hosted Exchange UM service.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

