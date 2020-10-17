---
title: 'Lync Server 2013: ダイヤルイン会議アクセス番号の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure dial-in conferencing access numbers
ms:assetid: d8a18030-f318-43dd-834d-70e5014b5e8a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398952(v=OCS.15)
ms:contentKeyID: 48185623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83c7069db95d36e79d74cea81faf3aa98685832f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504774"
---
# <a name="configure-dial-in-conferencing-access-numbers-in-lync-server-2013"></a><span data-ttu-id="d642b-102">Lync Server 2013 でのダイヤルイン会議アクセス番号の構成</span><span class="sxs-lookup"><span data-stu-id="d642b-102">Configure dial-in conferencing access numbers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d642b-103">_**トピックの最終更新日:** 2011-07-17_</span><span class="sxs-lookup"><span data-stu-id="d642b-103">_**Topic Last Modified:** 2011-07-17_</span></span>

<span data-ttu-id="d642b-p101">ダイヤルイン会議を展開するときには、ユーザーが公衆交換電話網 (PSTN) からダイヤルして電話会議のオーディオ部分に参加するための電話番号を設定する必要があります。 それらのダイヤルイン アクセス番号は、ミーティングの招待状と [ダイヤルイン会議の設定] Web ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d642b-p101">When you deploy dial-in conferencing, you need to set up phone numbers that users can dial from the public switched telephone network (PSTN) to join the audio portion of conferences. These dial-in access numbers appear in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>

<span data-ttu-id="d642b-106">ダイヤルイン アクセス番号を作成する前に、まずダイヤルイン会議の域を計画し、その地域のダイヤル プランを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d642b-106">Before you can create dial-in access numbers, you must first plan your dial-in conferencing regions and then configure dial plans with the regions.</span></span> <span data-ttu-id="d642b-107">地域の詳細については、「計画」のドキュメントの「 [Lync Server 2013 のダイヤルイン会議の要件](lync-server-2013-dial-in-conferencing-requirements.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d642b-107">For details about regions, see [Dial-in conferencing requirements in Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) in the Planning documentation.</span></span> <span data-ttu-id="d642b-108">ダイヤルイン会議のダイヤルプランの構成の詳細については、「 [Lync Server 2013 のダイヤルイン会議のダイヤルプランの構成](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d642b-108">For details about configuring dial plans for dial-in conferencing, see [Configure dial plans for dial-in conferencing in Lync Server 2013](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d642b-109">そのアクセス番号の Active Directory ドメインサービス (AD &nbsp; DS) レプリケーションが完了するまで、新しいダイヤルインアクセス番号を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="d642b-109">You cannot use a new dial-in access number until Active Directory Domain Services (AD&nbsp;DS) replication of that access number is complete.</span></span> <span data-ttu-id="d642b-110">レプリケーションが完了するまでに数時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="d642b-110">Replication can take several hours to complete.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="d642b-111">ダイヤルイン アクセス番号を作成した後は、Active Directory の連絡先オブジェクトの表示名を変更し、ユーザーが正しいアクセス番号を識別しやすくすることができます。</span><span class="sxs-lookup"><span data-stu-id="d642b-111">After you create dial-in access numbers, you can modify the display name for the Active Directory contact objects so that users can more easily identify the correct access number.</span></span> <span data-ttu-id="d642b-112">表示名を変更するには、<STRONG>Set-CsDialInConferencingAccessNumber</STRONG> コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="d642b-112">Use the <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> cmdlet to modify the display name.</span></span> <span data-ttu-id="d642b-113">Active Directory のオブジェクトは手動で変更しないでください。</span><span class="sxs-lookup"><span data-stu-id="d642b-113">You should not modify Active Directory objects manually.</span></span> <span data-ttu-id="d642b-114">アクセス番号の変更の詳細については、「Lync Server Management Shell documentation for <STRONG>get-csdialinconferencingaccessnumber</STRONG> コマンドレット」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d642b-114">For details about modifying an access number, see Lync Server Management Shell documentation for the <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> cmdlet.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d642b-115">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="d642b-115">In This Section</span></span>

[<span data-ttu-id="d642b-116">Lync Server 2013 でダイヤルイン会議アクセス番号を作成または変更する</span><span class="sxs-lookup"><span data-stu-id="d642b-116">Create or modify a dial-in conferencing access number in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-dial-in-conferencing-access-number.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d642b-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="d642b-117">See Also</span></span>


[<span data-ttu-id="d642b-118">Lync Server 2013 でのダイヤルイン会議の要件</span><span class="sxs-lookup"><span data-stu-id="d642b-118">Dial-in conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-requirements.md)  


[<span data-ttu-id="d642b-119">Lync Server 2013 でダイヤルイン会議のダイヤルプランを構成する</span><span class="sxs-lookup"><span data-stu-id="d642b-119">Configure dial plans for dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

