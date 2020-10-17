---
title: 'Lync Server 2013: ユーザーごとのホストボイスメールポリシーの割り当て'
description: 'Lync Server 2013: ユーザーごとのホストボイスメールポリシーの割り当て。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user hosted voice mail policy
ms:assetid: d44c71a0-4407-4ab4-b7e0-d671dde3425f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398919(v=OCS.15)
ms:contentKeyID: 48185456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 071d504c452b4d3adb1b636cb5c4ff8835200107
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559893"
---
# <a name="assign-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="de07d-103">Lync Server 2013 でユーザーごとにホストされるボイスメールポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="de07d-103">Assign a per-user hosted voice mail policy in Lync Server 2013</span></span>

 


<span data-ttu-id="de07d-p101">ユーザー単位のホスト ボイス メール ポリシーを展開するかどうかはオプションです。 ユーザー単位のポリシーを展開する場合は、ユーザー、グループ、または連絡先オブジェクトにポリシーを明示的に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="de07d-p101">Deploying one or more per-user hosted voice mail policies is optional. If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact objects.</span></span>

<span data-ttu-id="de07d-106">ユーザー単位のホストボイスメールポリシーの割り当てまたは削除の詳細については、以下のコマンドレットの Lync Server Management Shell のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="de07d-106">For details about assigning or removing the assignment of per-user hosted voice mail policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="de07d-107">Grant-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="de07d-107">Grant-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="de07d-108">Remove-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="de07d-108">Remove-CsHostedVoicemailPolicy</span></span>

## <a name="to-assign-a-per-user-hosted-voice-mail-policy"></a><span data-ttu-id="de07d-109">ユーザー単位のホスト ボイス メール ポリシーを割り当てるには</span><span class="sxs-lookup"><span data-stu-id="de07d-109">To assign a per-user hosted voice mail policy</span></span>

1.  <span data-ttu-id="de07d-110">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="de07d-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="de07d-p102">Grant-CsHostedVoicemailPolicy コマンドレットを実行して、個々のユーザー、グループ、および連絡先オブジェクトにユーザー単位のホスト ボイス メール ポリシーを割り当てます。たとえば、以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="de07d-p102">Run the Grant-CsHostedVoicemailPolicy cmdlet to assign the per-user hosted voice mail policy to individual users, groups, and contact objects. For example, run:</span></span>
    
        Grant-CsHostedVoicemailPolicy -Identity "Ken Myer" -PolicyName ExRedmond
    
    <span data-ttu-id="de07d-113">この例では、ExRedmond ホスト ボイス メール ポリシーを Ken Myer に割り当てました。</span><span class="sxs-lookup"><span data-stu-id="de07d-113">This example assigned the ExRedmond hosted voice mail policy to user Ken Myer.</span></span>
    
    <span data-ttu-id="de07d-p103">**Identity** により、変更するユーザー アカウントを指定しています。 Identity 値は、以下の形式のいずれかで指定できます。</span><span class="sxs-lookup"><span data-stu-id="de07d-p103">**Identity** specifies the user account to be modified. The Identity value can be specified using any of the following formats:</span></span>
    
      - <span data-ttu-id="de07d-116">ユーザーの SIP アドレス</span><span class="sxs-lookup"><span data-stu-id="de07d-116">The user's SIP address</span></span>
    
      - <span data-ttu-id="de07d-117">ユーザーの Active Directory ユーザー プリンシパル名</span><span class="sxs-lookup"><span data-stu-id="de07d-117">The user's Active Directory User-Principal-Name</span></span>
    
      - <span data-ttu-id="de07d-118">ユーザーのドメイン \\ ログオン名 (たとえば、contoso \\ kenmyer)</span><span class="sxs-lookup"><span data-stu-id="de07d-118">The user's domain\\logon name (for example, contoso\\kenmyer)</span></span>
    
      - <span data-ttu-id="de07d-119">ユーザーの Active Directory ドメイン サービス表示名 (例: Ken Myer)。</span><span class="sxs-lookup"><span data-stu-id="de07d-119">The user's Active Directory Domain Services Display-Name (for example, Ken Myer).</span></span> <span data-ttu-id="de07d-120">Display-Name を Identity 値として使用する場合は、アスタリスク ( \* ) ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="de07d-120">If using the Display-Name as the Identity value, you can use the asterisk (\*) wildcard character.</span></span> <span data-ttu-id="de07d-121">たとえば、"smith" という Id は、" \* smith" という文字列値で終わる Display-Name を持つすべてのユーザーを返します。</span><span class="sxs-lookup"><span data-stu-id="de07d-121">For example, the Identity "\* Smith" returns all the users who have a Display-Name that ends with the string value "Smith".</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="de07d-122">ユーザーの Active Directory SAM アカウント名は、フォレスト内で一意の名前とは限らないため、Identity 値として使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="de07d-122">The user’s Active Directory SAM-Account-Name cannot be used as the Identity value because the SAM-Account-Name is not necessarily unique in the forest.</span></span>


