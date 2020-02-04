---
title: (オプション) 会議への入退出のアナウンスの有効化および無効化
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Enable and disable conference join and leave announcements
ms:assetid: c9529568-e66c-48d8-aef2-9072f9c336ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398834(v=OCS.15)
ms:contentKeyID: 48185403
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b8e75a0d2ed81a515540f2a8a1811998a85d44c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755751"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-enable-and-disable-conference-join-and-leave-announcements-in-lync-server-2013"></a><span data-ttu-id="2d62e-102">(オプション) Lync Server 2013 での会議への入退出のアナウンスの有効化および無効化</span><span class="sxs-lookup"><span data-stu-id="2d62e-102">(Optional) Enable and disable conference join and leave announcements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d62e-103">_**最終更新日:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="2d62e-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="2d62e-104">ダイヤルインユーザーが会議に参加しているとき、会議に参加しているときに、会議アナウンスメントアプリケーションは、トーンを再生したり名前を言ったりして、開始または終了することができます。</span><span class="sxs-lookup"><span data-stu-id="2d62e-104">When dial-in users join or leave a conference, the Conferencing Announcement application can announce their entrance or exit by playing a tone or saying their names.</span></span> <span data-ttu-id="2d62e-105">コマンドレットを実行することで、お知らせの動作を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="2d62e-105">You can change how announcements work by running cmdlets.</span></span> <span data-ttu-id="2d62e-106">この手順は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="2d62e-106">This step is optional.</span></span>

<div>

## <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a><span data-ttu-id="2d62e-107">会議への出退席のアナウンス方法を変更するには</span><span class="sxs-lookup"><span data-stu-id="2d62e-107">To modify the conference join and leave announcement behavior</span></span>

1.  <span data-ttu-id="2d62e-108">RTCUniversalServerAdmins グループのメンバーとして、または**Cs-serveradministrator**または**csadministrator**の役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="2d62e-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="2d62e-109">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="2d62e-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="2d62e-110">コマンド プロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2d62e-110">Run the following at the command prompt:</span></span>
    
        Get-CsDialinConferencingConfiguration
    
    <span data-ttu-id="2d62e-111">このコマンドレットは、会議に参加するときに参加者が名前を記録する必要があるかどうか、また、参加者がダイヤルイン会議に参加または退出したときに Lync Server がどのように応答するかに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="2d62e-111">This cmdlet retrieves information about whether participants are required to record their name when joining a conference and how Lync Server responds when participants join or leave a dial-in conference.</span></span>

4.  <span data-ttu-id="2d62e-112">コマンド プロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2d62e-112">Run the following at the command prompt:</span></span>
    
        Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
        [-EnableNameRecording <$true | $false>]
        [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
        [-EntryExitAnnouncementsType <UseNames | ToneOnly]
    
    <span data-ttu-id="2d62e-113">**EnableNameRecording**   は、会議に参加する前に、匿名の参加者が名前の記録を求められるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="2d62e-113">**EnableNameRecording**   Determines whether anonymous participants are asked to record their name before entering the conference.</span></span> <span data-ttu-id="2d62e-114">既定値は "$true" で、これは、会議に参加するときに、匿名の参加者に名前の入力を求めるメッセージが表示されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="2d62e-114">The default value is "$true," which means that anonymous participants are prompted to state their name when joining a conference.</span></span> <span data-ttu-id="2d62e-115">(認証済みの参加者は、表示名が代わりに使用されるため、名前を記録しません。)</span><span class="sxs-lookup"><span data-stu-id="2d62e-115">(Authenticated participants do not record their name because their display name is used instead.)</span></span>
    
    <span data-ttu-id="2d62e-116">**EntryExitAnnouncementsEnabledByDefault**   は、お知らせが既定でオンまたはオフになっているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="2d62e-116">**EntryExitAnnouncementsEnabledByDefault**   Indicates whether announcements are turned on or off by default.</span></span> <span data-ttu-id="2d62e-117">既定値は "$false" で、これは既定で、参加者が会議に出席または会議から退席するときにアナウンスが行われないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="2d62e-117">The default value is "$false," which means that by default there are no announcements when participants join or leave a conference.</span></span> <span data-ttu-id="2d62e-118">ミーティング開催者は、ミーティングをスケジュールするときにこの設定を上書きできます。</span><span class="sxs-lookup"><span data-stu-id="2d62e-118">The meeting organizer can override this setting when scheduling a meeting.</span></span>
    
    <span data-ttu-id="2d62e-119">**Entryexitアナウンス ementstype**   は、アナウンスが有効になっている会議に参加者が参加または退室したときに実行されるアクションを示します。</span><span class="sxs-lookup"><span data-stu-id="2d62e-119">**EntryExitAnnouncementsType**   Indicates the action taken whenever a participant joins or leaves a conference for which announcements are enabled.</span></span> <span data-ttu-id="2d62e-120">既定値は "UseNames" で、これは、アナウンスをオンにすると、"Ken Myer が会議に参加しました" というようなアナウンスが行われることを意味します。</span><span class="sxs-lookup"><span data-stu-id="2d62e-120">The default value is "UseNames," which means there is an announcement similar to the following: "Ken Myer has joined the conference" when announcements are turned on.</span></span>
    
    <span data-ttu-id="2d62e-p105">これらの設定は、グローバル スコープまたはサイト スコープで構成できます。サイト スコープで構成した設定は、グローバル スコープで構成した設定より優先されます。</span><span class="sxs-lookup"><span data-stu-id="2d62e-p105">You can configure these settings at the global scope or at the site scope. Settings configured at the site scope take precedence over settings configured at the global scope.</span></span>
    
    <span data-ttu-id="2d62e-123">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="2d62e-123">For example:</span></span>
    
        Set-CsDialinConferencingConfiguration -Identity site:Redmond
        -EnableNameRecording $false
        -EntryExitAnnouncementsEnabledByDefault $true
        -EntryExitAnnouncementsType ToneOnly
    
    <span data-ttu-id="2d62e-124">この例では、設定は Redmond のサイトスコープで構成されています。</span><span class="sxs-lookup"><span data-stu-id="2d62e-124">In this example, settings are configured at the site scope for Redmond.</span></span> <span data-ttu-id="2d62e-125">アナウンスはオンにされますが、会議に参加するときに名前を言うように参加者が求められることはありません。</span><span class="sxs-lookup"><span data-stu-id="2d62e-125">Announcements are turned on, but participants are not prompted to say their name when they join a conference.</span></span> <span data-ttu-id="2d62e-126">参加者が会議に参加または退出したときにトーンが再生されます。</span><span class="sxs-lookup"><span data-stu-id="2d62e-126">A tone is played when participants enter or leave a conference.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

