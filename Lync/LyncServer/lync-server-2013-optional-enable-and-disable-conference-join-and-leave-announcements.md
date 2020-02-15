---
title: オプション会議の参加と退室のアナウンスを有効または無効にする
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
ms.openlocfilehash: 6b18dadbb4b7dc5a35f8688c46f2836b46cb55a5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051149"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-enable-and-disable-conference-join-and-leave-announcements-in-lync-server-2013"></a><span data-ttu-id="8d2e4-102">オプションLync Server 2013 での会議の参加と脱退のアナウンスを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="8d2e4-102">(Optional) Enable and disable conference join and leave announcements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8d2e4-103">_**トピックの最終更新日:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="8d2e4-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="8d2e4-104">ダイヤルインユーザーが会議に参加または退室したときに、電話会議アナウンスアプリケーションは、トーンを再生したり名前を言ったりすることで、開始または終了をアナウンスできます。</span><span class="sxs-lookup"><span data-stu-id="8d2e4-104">When dial-in users join or leave a conference, the Conferencing Announcement application can announce their entrance or exit by playing a tone or saying their names.</span></span> <span data-ttu-id="8d2e4-105">アナウンス方法はコマンドレットを実行することによって変更できます。</span><span class="sxs-lookup"><span data-stu-id="8d2e4-105">You can change how announcements work by running cmdlets.</span></span> <span data-ttu-id="8d2e4-106">このステップはオプションです。</span><span class="sxs-lookup"><span data-stu-id="8d2e4-106">This step is optional.</span></span>

<div>

## <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a><span data-ttu-id="8d2e4-107">会議への出退席のアナウンス方法を変更するには</span><span class="sxs-lookup"><span data-stu-id="8d2e4-107">To modify the conference join and leave announcement behavior</span></span>

1.  <span data-ttu-id="8d2e4-108">RTCUniversalServerAdmins グループのメンバーか、**Cs-ServerAdministrator** または **CsAdministrator** の役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="8d2e4-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="8d2e4-109">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="8d2e4-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="8d2e4-110">コマンド プロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="8d2e4-110">Run the following at the command prompt:</span></span>
    
        Get-CsDialinConferencingConfiguration
    
    <span data-ttu-id="8d2e4-111">このコマンドレットは、会議に参加するときに参加者が名前を記録する必要があるかどうか、および参加者がダイヤルイン会議に参加または退室したときに Lync Server が応答するかどうかに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="8d2e4-111">This cmdlet retrieves information about whether participants are required to record their name when joining a conference and how Lync Server responds when participants join or leave a dial-in conference.</span></span>

4.  <span data-ttu-id="8d2e4-112">コマンド プロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="8d2e4-112">Run the following at the command prompt:</span></span>
    
        Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
        [-EnableNameRecording <$true | $false>]
        [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
        [-EntryExitAnnouncementsType <UseNames | ToneOnly]
    
    <span data-ttu-id="8d2e4-113">**EnableNameRecording**   は、会議に入る前に、匿名の参加者が名前を記録するように要求するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="8d2e4-113">**EnableNameRecording**   Determines whether anonymous participants are asked to record their name before entering the conference.</span></span> <span data-ttu-id="8d2e4-114">既定値は "$true" で、これは、匿名参加者が会議に参加するときに名前を入力するように求められることを意味します。</span><span class="sxs-lookup"><span data-stu-id="8d2e4-114">The default value is "$true," which means that anonymous participants are prompted to state their name when joining a conference.</span></span> <span data-ttu-id="8d2e4-115">(認証された参加者は、表示名が代わりに使用されるので、名前を記録しません。)</span><span class="sxs-lookup"><span data-stu-id="8d2e4-115">(Authenticated participants do not record their name because their display name is used instead.)</span></span>
    
    <span data-ttu-id="8d2e4-116">**EntryExitAnnouncementsEnabledByDefault**   は、アナウンスが既定でオンまたはオフにされているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="8d2e4-116">**EntryExitAnnouncementsEnabledByDefault**   Indicates whether announcements are turned on or off by default.</span></span> <span data-ttu-id="8d2e4-117">既定値は "$false" で、これは既定で、参加者が会議に参加または退室したときにアナウンスがないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="8d2e4-117">The default value is "$false," which means that by default there are no announcements when participants join or leave a conference.</span></span> <span data-ttu-id="8d2e4-118">会議の開催者は、会議をスケジュールするときにこの設定を上書きすることができます。</span><span class="sxs-lookup"><span data-stu-id="8d2e4-118">The meeting organizer can override this setting when scheduling a meeting.</span></span>
    
    <span data-ttu-id="8d2e4-119">**Entryexitアナウンス ementstype**   は、参加者がアナウンスが有効になっている会議に参加または退室したときに実行されるアクションを示します。</span><span class="sxs-lookup"><span data-stu-id="8d2e4-119">**EntryExitAnnouncementsType**   Indicates the action taken whenever a participant joins or leaves a conference for which announcements are enabled.</span></span> <span data-ttu-id="8d2e4-120">既定値は "UseNames です。これは、アナウンスが有効になっている場合に、" Ken Myer が会議に参加しました "ということを意味します。</span><span class="sxs-lookup"><span data-stu-id="8d2e4-120">The default value is "UseNames," which means there is an announcement similar to the following: "Ken Myer has joined the conference" when announcements are turned on.</span></span>
    
    <span data-ttu-id="8d2e4-p105">これらの設定は、グローバル スコープまたはサイト スコープで構成できます。 サイト スコープで構成した設定は、グローバル スコープで構成した設定より優先されます。</span><span class="sxs-lookup"><span data-stu-id="8d2e4-p105">You can configure these settings at the global scope or at the site scope. Settings configured at the site scope take precedence over settings configured at the global scope.</span></span>
    
    <span data-ttu-id="8d2e4-123">次にその例を示します。</span><span class="sxs-lookup"><span data-stu-id="8d2e4-123">For example:</span></span>
    
        Set-CsDialinConferencingConfiguration -Identity site:Redmond
        -EnableNameRecording $false
        -EntryExitAnnouncementsEnabledByDefault $true
        -EntryExitAnnouncementsType ToneOnly
    
    <span data-ttu-id="8d2e4-p106">この例では、設定が Redmond のサイト スコープで定義されます。 アナウンスはオンにされますが、会議に参加するときに名前を言うよう参加者が求められることはありません。 参加者が会議に出席または会議から退席するときには、トーン音が再生されます。</span><span class="sxs-lookup"><span data-stu-id="8d2e4-p106">In this example, settings are configured at the site scope for Redmond. Announcements are turned on, but participants are not prompted to say their name when they join a conference. A tone is played when participants enter or leave a conference.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

