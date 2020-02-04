---
title: Lync Server 2013 への残りのユーザーの移動
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
ms.openlocfilehash: 4d60b3ba622e88978a8bbf555972c95979e8f8c3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743757"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-remaining-users-to-lync-server-2013"></a><span data-ttu-id="8bae9-102">Lync Server 2013 への残りのユーザーの移動</span><span class="sxs-lookup"><span data-stu-id="8bae9-102">Move remaining users to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8bae9-103">_**最終更新日:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="8bae9-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="8bae9-104">Lync Server コントロールパネルまたは Lync Server 管理シェルを使用して、ユーザーを新しい Lync Server 2013 の展開に移動することができます。</span><span class="sxs-lookup"><span data-stu-id="8bae9-104">You can move users to the new Lync Server 2013 deployment by using either Lync Server Control Panel or Lync Server Management Shell.</span></span> <span data-ttu-id="8bae9-105">Lync Server 2013 にスムーズに移行するためには、いくつかの要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8bae9-105">You must meet some requirements to ensure a smooth transition to Lync Server 2013.</span></span> <span data-ttu-id="8bae9-106">このトピックの手順を完了するための前提条件の詳細については、「[移行のためにクライアントを構成](configure-clients-for-migration.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8bae9-106">For details about prerequisites to completing the procedures in this topic, see [Configure clients for migration](configure-clients-for-migration.md).</span></span> <span data-ttu-id="8bae9-107">ユーザーの移動の詳細な手順については、「[フェーズ 4: テストユーザーをパイロットプールに移動する](phase-4-move-test-users-to-the-pilot-pool.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8bae9-107">For detailed steps about moving users, see [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8bae9-108">Active Directory ユーザーとコンピューターのスナップインまたは Lync Server 2010 管理ツールを使用して、ユーザーを従来の環境から Lync Server 2013 に移動することはできません。</span><span class="sxs-lookup"><span data-stu-id="8bae9-108">You cannot use the Active Directory Users and Computers snap-in or the Lync Server 2010 administrative tools to move users from your legacy environment to Lync Server 2013.</span></span>



</div>

<span data-ttu-id="8bae9-109">ユーザーを Lync Server 2013 プールに移動すると、そのユーザーのデータは、新しいプールに関連付けられているバックエンドデータベースに移動されます。</span><span class="sxs-lookup"><span data-stu-id="8bae9-109">When you move a user to an Lync Server 2013 pool, the data for the user is moved to the back-end database that is associated with the new pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8bae9-110">これには、従来のユーザーによって作成されたアクティブな会議も含まれます。</span><span class="sxs-lookup"><span data-stu-id="8bae9-110">This includes the active meetings created by the legacy user.</span></span> <span data-ttu-id="8bae9-111">たとえば、従来のユーザーが<STRONG>会議</STRONG>用の会議を構成している場合は、ユーザーが移動された後も、新しい Lync Server 2013 プールでその会議を利用できます。</span><span class="sxs-lookup"><span data-stu-id="8bae9-111">For example, if a legacy user has configured a <STRONG>my meeting</STRONG> conference, that conference will still be available in the new Lync Server 2013 pool after the user has been moved.</span></span> <span data-ttu-id="8bae9-112">会議にアクセスするための詳細は、会議の<STRONG>URL と会議 ID と</STRONG>同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="8bae9-112">The details to access that meeting will still be the same <STRONG>conference URL and conference ID</STRONG>.</span></span> <span data-ttu-id="8bae9-113">唯一の違いは、会議が lync server 2013 プールでホストされており、Lync Server 2010 プールではホストされていないことです。</span><span class="sxs-lookup"><span data-stu-id="8bae9-113">The only difference is that the conference is now hosted in the Lync Server 2013 pool, and not in the Lync Server 2010 pool.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="8bae9-114">Lync Server 2013 のホームユーザーは、アップグレードされたクライアントを展開する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="8bae9-114">Homing users on Lync Server 2013 does not require that you deploy upgraded clients at the same time.</span></span> <span data-ttu-id="8bae9-115">新しい機能は、ユーザーが新しいクライアントソフトウェアにアップグレードした場合にのみ利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="8bae9-115">New functionality will be available to users only when they have upgraded to the new client software.</span></span>



</div>

<div>

## <a name="post-migration-task"></a><span data-ttu-id="8bae9-116">移行後の作業</span><span class="sxs-lookup"><span data-stu-id="8bae9-116">Post Migration Task</span></span>

1.  <span data-ttu-id="8bae9-117">ユーザーを移動した後、それらに割り当てられている会議ポリシーを確認します。</span><span class="sxs-lookup"><span data-stu-id="8bae9-117">After you move users, verify the conferencing policy that is assigned to them.</span></span>

2.  <span data-ttu-id="8bae9-118">Lync Server 2013 を使っているユーザーによって開催された会議が、Lync Server 2010 を使用しているフェデレーションユーザーとシームレスに動作するようにするには、移行したユーザーに割り当てられている会議ポリシーで、匿名の参加者を許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8bae9-118">To ensure that meetings organized by users homed on Lync Server 2013 work seamlessly with federated users who are homed on Lync Server 2010, the conferencing policy assigned to the migrated users should allow anonymous participants.</span></span>

3.  <span data-ttu-id="8bae9-119">匿名の参加者を許可する会議ポリシーでは、Lync server 2013 コントロールパネルで選択された**匿名ユーザーの招待を許可**することができます。また、Lync Server 管理シェルの**set-csconferencingpolicy**コマンドレットの出力で**AllowAnonymousParticipantsInMeetings**を**True**に設定します。</span><span class="sxs-lookup"><span data-stu-id="8bae9-119">Conferencing policies that allow anonymous participants have **Allow participants to invite anonymous users** selected in Lync Server 2013 Control Panel and have **AllowAnonymousParticipantsInMeetings** set to **True** in the output from the **Get-CsConferencingPolicy** cmdlet in the Lync Server Management Shell.</span></span>

4.  <span data-ttu-id="8bae9-120">Lync Server 管理シェルを使用して会議ポリシーを構成する方法の詳細については、「Lync Server 管理シェルドキュメントの[set-csconferencingpolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8bae9-120">For details about configuring conferencing policy by using Lync Server Management Shell, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) in the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

