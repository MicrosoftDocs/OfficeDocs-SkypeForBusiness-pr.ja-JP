---
title: Lync Server 2013 への残りのユーザーの移動
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Move remaining users to Lync Server 2013
ms:assetid: 0eb990f0-f720-47a7-aaee-437fbd4c4c33
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687968(v=OCS.15)
ms:contentKeyID: 49733554
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a728afae37c2e8d317cd6c75872c75d358226475
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848036"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-remaining-users-to-lync-server-2013"></a><span data-ttu-id="6198d-102">Lync Server 2013 への残りのユーザーの移動</span><span class="sxs-lookup"><span data-stu-id="6198d-102">Move remaining users to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6198d-103">_**最終更新日:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="6198d-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="6198d-104">Lync Server コントロールパネルまたは Lync Server 管理シェルを使用して、ユーザーを新しい Lync Server 2013 の展開に移動することができます。</span><span class="sxs-lookup"><span data-stu-id="6198d-104">You can move users to the new Lync Server 2013 deployment by using either Lync Server Control Panel or Lync Server Management Shell.</span></span> <span data-ttu-id="6198d-105">Lync Server 2013 にスムーズに移行するためには、いくつかの要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6198d-105">You must meet some requirements to ensure a smooth transition to Lync Server 2013.</span></span> <span data-ttu-id="6198d-106">このトピックの手順を完了するための前提条件の詳細については、「[移行のためにクライアントを構成](configure-clients-for-migration_1.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6198d-106">For details about prerequisites to completing the procedures in this topic, see [Configure clients for migration](configure-clients-for-migration_1.md).</span></span> <span data-ttu-id="6198d-107">ユーザーの移動の詳細な手順については、「[フェーズ 6: ユーザーをパイロットプールに移動する](phase-6-move-users-to-the-pilot-pool.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6198d-107">For detailed steps about moving users, see [Phase 6: Move users to the pilot pool](phase-6-move-users-to-the-pilot-pool.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6198d-108">Active Directory ユーザーとコンピューターのスナップインまたは Microsoft Office Communications Server 2007 R2 管理ツールを使用して、ユーザーを従来の環境から Lync Server 2013 に移動することはできません。</span><span class="sxs-lookup"><span data-stu-id="6198d-108">You cannot use the Active Directory Users and Computers snap-in or the Microsoft Office Communications Server 2007 R2 administrative tools to move users from your legacy environment to Lync Server 2013.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6198d-109"><STRONG>CsLegacyUser</STRONG>コマンドレットを実行するには、ユーザー名が正しい形式であり、先頭または末尾にスペースがない必要があります。</span><span class="sxs-lookup"><span data-stu-id="6198d-109">The <STRONG>Move-CsLegacyUser</STRONG> cmdlet requires that user names are properly formed and do not have leading or trailing spaces.</span></span> <span data-ttu-id="6198d-110">先行または末尾のスペースが含まれている場合、 <STRONG>CsLegacyUser</STRONG>コマンドレットを使用してユーザーアカウントを移動することはできません。</span><span class="sxs-lookup"><span data-stu-id="6198d-110">You cannot move a user account using the <STRONG>Move-CsLegacyUser</STRONG> cmdlet if it contains leading or trailing spaces.</span></span>



</div>

<span data-ttu-id="6198d-111">ユーザーを Lync Server 2013 プールに移動すると、そのユーザーのデータは、新しいプールに関連付けられているバックエンドデータベースに移動されます。</span><span class="sxs-lookup"><span data-stu-id="6198d-111">When you move a user to an Lync Server 2013 pool, the data for the user is moved to the back-end database that is associated with the new pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6198d-112">これには、従来のユーザーによって作成されたアクティブな会議も含まれます。</span><span class="sxs-lookup"><span data-stu-id="6198d-112">This includes the active meetings created by the legacy user.</span></span> <span data-ttu-id="6198d-113">たとえば、従来のユーザーが<STRONG>会議</STRONG>用の会議を構成している場合は、ユーザーが移動された後も、新しい Lync Server 2013 プールでその会議を利用できます。</span><span class="sxs-lookup"><span data-stu-id="6198d-113">For example, if a legacy user has configured a <STRONG>my meeting</STRONG> conference, that conference will still be available in the new Lync Server 2013 pool, after the user has been moved.</span></span> <span data-ttu-id="6198d-114">会議にアクセスするための詳細は、会議の<STRONG>URL と会議 ID と</STRONG>同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="6198d-114">The details to access that meeting will still be the same <STRONG>conference URL and conference ID</STRONG>.</span></span> <span data-ttu-id="6198d-115">唯一の違いは、会議が Lync Server 2013 プールでホストされ、Office Communications Server 2007 R2 プールではホストされていないことです。</span><span class="sxs-lookup"><span data-stu-id="6198d-115">The only difference is that the conference is now hosted in the Lync Server 2013 pool, and not in Office Communications Server 2007 R2 pool.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="6198d-116">Lync Server 2013 のホームユーザーは、アップグレードされたクライアントを展開する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6198d-116">Homing users on Lync Server 2013 does not require that you deploy upgraded clients at the same time.</span></span> <span data-ttu-id="6198d-117">新しい機能は、ユーザーが新しいクライアントソフトウェアにアップグレードした場合にのみ利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="6198d-117">New functionality will be available to users only when they have upgraded to the new client software.</span></span>



</div>

<div>

## <a name="post-migration-task"></a><span data-ttu-id="6198d-118">移行後の作業</span><span class="sxs-lookup"><span data-stu-id="6198d-118">Post Migration Task</span></span>

1.  <span data-ttu-id="6198d-119">ユーザーを移動した後、それらに割り当てられている会議ポリシーを確認します。</span><span class="sxs-lookup"><span data-stu-id="6198d-119">After you move users, verify the conferencing policy that is assigned to them.</span></span>

2.  <span data-ttu-id="6198d-120">Lync Server 2013 を使っているユーザーによって開催された会議が、Office Communications Server 2007 R2 を使用しているフェデレーションユーザーとシームレスに動作するようにするには、移行したユーザーに割り当てられている会議ポリシーを使用して、匿名の参加者を許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6198d-120">To ensure that meetings organized by users homed on Lync Server 2013 work seamlessly with federated users who are homed on Office Communications Server 2007 R2, the conferencing policy assigned to the migrated users should allow anonymous participants.</span></span>

3.  <span data-ttu-id="6198d-121">匿名の参加者に許可されている会議ポリシーでは、Lync Server 2013 コントロールパネルで選択された**匿名ユーザーを招待することができ**ます。出力で**AllowAnonymousParticipantsInMeetings**を**True**に設定します。Lync Server 管理シェルの**set-csconferencingpolicy**コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="6198d-121">Conferencing policies that allow anonymous participants have **Allow participants to invite anonymous users** selected in Lync Server 2013 Control Panel and have **AllowAnonymousParticipantsInMeetings** set to **True** in the output from the **Get-CsConferencingPolicy** cmdlet in the Lync Server Management Shell.</span></span>

4.  <span data-ttu-id="6198d-122">Lync Server 管理シェルを使用して会議ポリシーを構成する方法の詳細については、「Lync Server 管理シェルドキュメントの[set-csconferencingpolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6198d-122">For details about configuring conferencing policy by using Lync Server Management Shell, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) in the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

