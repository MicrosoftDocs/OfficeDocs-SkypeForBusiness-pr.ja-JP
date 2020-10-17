---
title: 残りのユーザーを Lync Server 2013 に移動する
description: 残りのユーザーを Lync Server 2013 に移動します。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move remaining users to Lync Server 2013
ms:assetid: 72025e1b-97d1-40e9-8a98-28c018942b48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688090(v=OCS.15)
ms:contentKeyID: 49733689
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 291b58d6644f9ac8f10c63f6585ba865602580df
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571313"
---
# <a name="move-remaining-users-to-lync-server-2013"></a><span data-ttu-id="7e00b-103">残りのユーザーを Lync Server 2013 に移動する</span><span class="sxs-lookup"><span data-stu-id="7e00b-103">Move remaining users to Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7e00b-104">_**トピックの最終更新日:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="7e00b-104">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="7e00b-105">Lync Server コントロールパネルまたは Lync Server 管理シェルを使用して、ユーザーを新しい Lync Server 2013 展開に移動することができます。</span><span class="sxs-lookup"><span data-stu-id="7e00b-105">You can move users to the new Lync Server 2013 deployment by using either Lync Server Control Panel or Lync Server Management Shell.</span></span> <span data-ttu-id="7e00b-106">Lync Server 2013 にスムーズに移行できるようにするには、いくつかの要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e00b-106">You must meet some requirements to ensure a smooth transition to Lync Server 2013.</span></span> <span data-ttu-id="7e00b-107">このトピックの手順を完了するための前提条件の詳細については、「 [Configure clients for migration](configure-clients-for-migration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e00b-107">For details about prerequisites to completing the procedures in this topic, see [Configure clients for migration](configure-clients-for-migration.md).</span></span> <span data-ttu-id="7e00b-108">ユーザーの移動の詳細な手順については、「 [フェーズ 4: テストユーザーをパイロットプールに移動する](phase-4-move-test-users-to-the-pilot-pool.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e00b-108">For detailed steps about moving users, see [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="7e00b-109">Active Directory ユーザーとコンピュータースナップインまたは Lync Server 2010 管理ツールを使用して、レガシ環境から Lync Server 2013 にユーザーを移動することはできません。</span><span class="sxs-lookup"><span data-stu-id="7e00b-109">You cannot use the Active Directory Users and Computers snap-in or the Lync Server 2010 administrative tools to move users from your legacy environment to Lync Server 2013.</span></span>



</div>

<span data-ttu-id="7e00b-110">ユーザーを Lync Server 2013 プールに移動すると、そのユーザーのデータは、新しいプールに関連付けられたバックエンドデータベースに移動されます。</span><span class="sxs-lookup"><span data-stu-id="7e00b-110">When you move a user to an Lync Server 2013 pool, the data for the user is moved to the back-end database that is associated with the new pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="7e00b-111">これには、レガシ ユーザーによって作成されたアクティブな会議が含まれます。</span><span class="sxs-lookup"><span data-stu-id="7e00b-111">This includes the active meetings created by the legacy user.</span></span> <span data-ttu-id="7e00b-112">たとえば、従来のユーザーが <STRONG>会議</STRONG> の会議を構成している場合は、ユーザーが移動された後も、新しい Lync Server 2013 プールでその会議を利用できます。</span><span class="sxs-lookup"><span data-stu-id="7e00b-112">For example, if a legacy user has configured a <STRONG>my meeting</STRONG> conference, that conference will still be available in the new Lync Server 2013 pool after the user has been moved.</span></span> <span data-ttu-id="7e00b-113">会議へのアクセスに使用する<STRONG>会議 URL と電話会議 ID</STRONG> も同じです。</span><span class="sxs-lookup"><span data-stu-id="7e00b-113">The details to access that meeting will still be the same <STRONG>conference URL and conference ID</STRONG>.</span></span> <span data-ttu-id="7e00b-114">唯一の違いは、会議が lync server 2010 プールではなく Lync Server 2013 プールでホストされるようになったことです。</span><span class="sxs-lookup"><span data-stu-id="7e00b-114">The only difference is that the conference is now hosted in the Lync Server 2013 pool, and not in the Lync Server 2010 pool.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="7e00b-115">Lync Server 2013 上のホームユーザーは、アップグレードされたクライアントを同時に展開する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="7e00b-115">Homing users on Lync Server 2013 does not require that you deploy upgraded clients at the same time.</span></span> <span data-ttu-id="7e00b-116">クライアントが新しいクライアント ソフトウェアにアップグレードされている場合に限り、ユーザーは新しい機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="7e00b-116">New functionality will be available to users only when they have upgraded to the new client software.</span></span>



</div>

<div>

## <a name="post-migration-task"></a><span data-ttu-id="7e00b-117">移行後のタスク</span><span class="sxs-lookup"><span data-stu-id="7e00b-117">Post Migration Task</span></span>

1.  <span data-ttu-id="7e00b-118">ユーザーを移動した後、ユーザーに割り当てられている会議ポリシーを確認します。</span><span class="sxs-lookup"><span data-stu-id="7e00b-118">After you move users, verify the conferencing policy that is assigned to them.</span></span>

2.  <span data-ttu-id="7e00b-119">Lync server 2013 に所属するユーザーによって開催された会議が、Lync Server 2010 に所属しているフェデレーションユーザーとシームレスに機能するようにするには、移行したユーザーに割り当てられている会議ポリシーで匿名の参加者を許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e00b-119">To ensure that meetings organized by users homed on Lync Server 2013 work seamlessly with federated users who are homed on Lync Server 2010, the conferencing policy assigned to the migrated users should allow anonymous participants.</span></span>

3.  <span data-ttu-id="7e00b-120">匿名参加者に許可されている会議ポリシーによって、Lync server 2013 コントロールパネルで選択した**匿名ユーザーの招待を参加者に許可**し、Lync Server 管理シェルの**get-csconferencingpolicy**コマンドレットの出力で**AllowAnonymousParticipantsInMeetings**を**True**に設定しました。</span><span class="sxs-lookup"><span data-stu-id="7e00b-120">Conferencing policies that allow anonymous participants have **Allow participants to invite anonymous users** selected in Lync Server 2013 Control Panel and have **AllowAnonymousParticipantsInMeetings** set to **True** in the output from the **Get-CsConferencingPolicy** cmdlet in the Lync Server Management Shell.</span></span>

4.  <span data-ttu-id="7e00b-121">Lync Server 管理シェルを使用した会議ポリシーの構成の詳細については、「Lync Server Management Shell」のドキュメントの「 [get-csconferencingpolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e00b-121">For details about configuring conferencing policy by using Lync Server Management Shell, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) in the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

