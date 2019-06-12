---
title: 'Lync Server 2013: ユーザーごとにホストされるボイスメールポリシーを割り当てる'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a per-user hosted voice mail policy
ms:assetid: d44c71a0-4407-4ab4-b7e0-d671dde3425f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398919(v=OCS.15)
ms:contentKeyID: 48185456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2202e1b4c03eb25d12e46c3a533313a54bc76c4f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848844"
---
# <a name="assign-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="cb9da-102">Lync Server 2013 でユーザーごとにホストされるボイスメールのポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="cb9da-102">Assign a per-user hosted voice mail policy in Lync Server 2013</span></span>

 


<span data-ttu-id="cb9da-103">ユーザーごとにホストされるボイスメールのポリシーを1つ以上展開することは任意です。</span><span class="sxs-lookup"><span data-stu-id="cb9da-103">Deploying one or more per-user hosted voice mail policies is optional.</span></span> <span data-ttu-id="cb9da-104">ユーザーごとのポリシーを展開する場合は、ユーザー、グループ、または連絡先オブジェクトに明示的に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb9da-104">If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact objects.</span></span>

<span data-ttu-id="cb9da-105">ユーザーごとにホストされるボイスメールポリシーの割り当てまたは削除の詳細については、次のコマンドレットの Lync Server 管理シェルに関するドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb9da-105">For details about assigning or removing the assignment of per-user hosted voice mail policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="cb9da-106">Grant-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="cb9da-106">Grant-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="cb9da-107">Remove-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="cb9da-107">Remove-CsHostedVoicemailPolicy</span></span>

## <a name="to-assign-a-per-user-hosted-voice-mail-policy"></a><span data-ttu-id="cb9da-108">ユーザーごとにホストされるボイスメールのポリシーを割り当てるには</span><span class="sxs-lookup"><span data-stu-id="cb9da-108">To assign a per-user hosted voice mail policy</span></span>

1.  <span data-ttu-id="cb9da-109">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb9da-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="cb9da-110">CsHostedVoicemailPolicy コマンドレットを実行して、ユーザーごとにホストされるボイスメールポリシーを個々のユーザー、グループ、連絡先オブジェクトに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="cb9da-110">Run the Grant-CsHostedVoicemailPolicy cmdlet to assign the per-user hosted voice mail policy to individual users, groups, and contact objects.</span></span> <span data-ttu-id="cb9da-111">たとえば、以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="cb9da-111">For example, run:</span></span>
    
        Grant-CsHostedVoicemailPolicy -Identity "Ken Myer" -PolicyName ExRedmond
    
    <span data-ttu-id="cb9da-112">この例では、ユーザー Ken Myer に ExRedmond でホストされるボイスメールポリシーを割り当てました。</span><span class="sxs-lookup"><span data-stu-id="cb9da-112">This example assigned the ExRedmond hosted voice mail policy to user Ken Myer.</span></span>
    
    <span data-ttu-id="cb9da-113">**Id**は、変更するユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="cb9da-113">**Identity** specifies the user account to be modified.</span></span> <span data-ttu-id="cb9da-114">Id 値は、次の形式のいずれかを使用して指定できます。</span><span class="sxs-lookup"><span data-stu-id="cb9da-114">The Identity value can be specified using any of the following formats:</span></span>
    
      - <span data-ttu-id="cb9da-115">ユーザーの SIP アドレス</span><span class="sxs-lookup"><span data-stu-id="cb9da-115">The user's SIP address</span></span>
    
      - <span data-ttu-id="cb9da-116">ユーザーの Active Directory ユーザープリンシパル名</span><span class="sxs-lookup"><span data-stu-id="cb9da-116">The user's Active Directory User-Principal-Name</span></span>
    
      - <span data-ttu-id="cb9da-117">ユーザーのドメイン\\ログオン名 (たとえば、contoso\\kenmyer)</span><span class="sxs-lookup"><span data-stu-id="cb9da-117">The user's domain\\logon name (for example, contoso\\kenmyer)</span></span>
    
      - <span data-ttu-id="cb9da-118">ユーザーの Active Directory ドメインサービスの表示名 (Ken Myer など)</span><span class="sxs-lookup"><span data-stu-id="cb9da-118">The user's Active Directory Domain Services Display-Name (for example, Ken Myer).</span></span> <span data-ttu-id="cb9da-119">Id 値として表示名を使用している場合は、アスタリスク (\*) ワイルドカード文字を使うことができます。</span><span class="sxs-lookup"><span data-stu-id="cb9da-119">If using the Display-Name as the Identity value, you can use the asterisk (\*) wildcard character.</span></span> <span data-ttu-id="cb9da-120">たとえば、"\* smith" という id を指定すると、"smith" という文字列で終わる表示名を持つすべてのユーザーが返されます。</span><span class="sxs-lookup"><span data-stu-id="cb9da-120">For example, the Identity "\* Smith" returns all the users who have a Display-Name that ends with the string value "Smith".</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="cb9da-121">SAM アカウント名はフォレスト内で必ずしも一意ではないため、ユーザーの Active Directory SAM アカウント名を Id 値として使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="cb9da-121">The user’s Active Directory SAM-Account-Name cannot be used as the Identity value because the SAM-Account-Name is not necessarily unique in the forest.</span></span>


