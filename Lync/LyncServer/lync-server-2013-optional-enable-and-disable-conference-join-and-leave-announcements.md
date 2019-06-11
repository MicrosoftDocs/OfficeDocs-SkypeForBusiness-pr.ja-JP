---
title: (オプション) 会議への入退出のアナウンスの有効化および無効化
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: (Optional) Enable and disable conference join and leave announcements
ms:assetid: c9529568-e66c-48d8-aef2-9072f9c336ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398834(v=OCS.15)
ms:contentKeyID: 48185403
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 778969dfa5ed6b84fdbcd2b204e497f8d649f1a6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825794"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-enable-and-disable-conference-join-and-leave-announcements-in-lync-server-2013"></a>(オプション) Lync Server 2013 での会議への入退出のアナウンスの有効化および無効化

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-30_

ダイヤルインユーザーが会議に参加しているとき、会議に参加しているときに、会議アナウンスメントアプリケーションは、トーンを再生したり名前を言ったりして、開始または終了することができます。 コマンドレットを実行することで、お知らせの動作を変更することができます。 この手順は省略可能です。

<div>

## <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a>会議への出退席のアナウンス方法を変更するには

1.  RTCUniversalServerAdmins グループのメンバーとして、または**Cs-serveradministrator**または**csadministrator**の役割のメンバーとしてコンピューターにログオンします。

2.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

3.  コマンド プロンプトで次のコマンドを実行します。
    
        Get-CsDialinConferencingConfiguration
    
    このコマンドレットは、会議に参加するときに参加者が名前を記録する必要があるかどうか、また、参加者がダイヤルイン会議に参加または退出したときに Lync Server がどのように応答するかに関する情報を取得します。

4.  コマンド プロンプトで次のコマンドを実行します。
    
        Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
        [-EnableNameRecording <$true | $false>]
        [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
        [-EntryExitAnnouncementsType <UseNames | ToneOnly]
    
    **EnableNameRecording**   は、会議に参加する前に、匿名の参加者が名前の記録を求められるかどうかを決定します。 既定値は "$true" で、これは、会議に参加するときに、匿名の参加者に名前の入力を求めるメッセージが表示されることを意味します。 (認証済みの参加者は、表示名が代わりに使用されるため、名前を記録しません。)
    
    **EntryExitAnnouncementsEnabledByDefault**   は、お知らせが既定でオンまたはオフになっているかどうかを示します。 既定値は "$false" で、これは既定で、参加者が会議に出席または会議から退席するときにアナウンスが行われないことを意味します。 ミーティング開催者は、ミーティングをスケジュールするときにこの設定を上書きできます。
    
    **Entryexitアナウンス ementstype**   は、アナウンスが有効になっている会議に参加者が参加または退室したときに実行されるアクションを示します。 既定値は "UseNames" で、これは、アナウンスをオンにすると、"Ken Myer が会議に参加しました" というようなアナウンスが行われることを意味します。
    
    これらの設定は、グローバル スコープまたはサイト スコープで構成できます。サイト スコープで構成した設定は、グローバル スコープで構成した設定より優先されます。
    
    次に例を示します。
    
        Set-CsDialinConferencingConfiguration -Identity site:Redmond
        -EnableNameRecording $false
        -EntryExitAnnouncementsEnabledByDefault $true
        -EntryExitAnnouncementsType ToneOnly
    
    この例では、設定は Redmond のサイトスコープで構成されています。 アナウンスはオンにされますが、会議に参加するときに名前を言うように参加者が求められることはありません。 参加者が会議に参加または退出したときにトーンが再生されます。

</div>

</div>

<span> </span>

</div>

</div>

</div>

