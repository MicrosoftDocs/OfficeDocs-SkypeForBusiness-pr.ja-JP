---
title: オプション会議の参加と退室のアナウンスを有効または無効にする
description: オプション会議の参加と退室のアナウンスを有効または無効にします。
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
ms.openlocfilehash: 70cd6b452a44d7d40f23d5ca96b6e4b7b063d2ec
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565783"
---
# <a name="optional-enable-and-disable-conference-join-and-leave-announcements-in-lync-server-2013"></a>オプションLync Server 2013 での会議の参加と脱退のアナウンスを有効または無効にする

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-30_

ダイヤルインユーザーが会議に参加または退室したときに、電話会議アナウンスアプリケーションは、トーンを再生したり名前を言ったりすることで、開始または終了をアナウンスできます。 アナウンス方法はコマンドレットを実行することによって変更できます。 このステップはオプションです。

<div>

## <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a>会議への出退席のアナウンス方法を変更するには

1.  RTCUniversalServerAdmins グループのメンバーか、**Cs-ServerAdministrator** または **CsAdministrator** の役割のメンバーとしてコンピューターにログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

3.  コマンド プロンプトで次のコマンドを実行します。
    
        Get-CsDialinConferencingConfiguration
    
    このコマンドレットは、会議に参加するときに参加者が名前を記録する必要があるかどうか、および参加者がダイヤルイン会議に参加または退室したときに Lync Server が応答するかどうかに関する情報を取得します。

4.  コマンド プロンプトで次のコマンドを実行します。
    
        Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
        [-EnableNameRecording <$true | $false>]
        [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
        [-EntryExitAnnouncementsType <UseNames | ToneOnly]
    
    **EnableNameRecording**    匿名参加者が電話会議に入る前に名前を記録するように要求するかどうかを指定します。 既定値は "$true" で、これは、匿名参加者が会議に参加するときに名前を入力するように求められることを意味します。 (認証された参加者は、表示名が代わりに使用されるので、名前を記録しません。)
    
    **EntryExitAnnouncementsEnabledByDefault**    アナウンスを既定で有効または無効にするかどうかを示します。 既定値は "$false" で、これは既定で、参加者が会議に参加または退室したときにアナウンスがないことを意味します。 会議の開催者は、会議をスケジュールするときにこの設定を上書きすることができます。
    
    **Entryexitアナウンス Ementstype**    参加者が、アナウンスが有効になっている会議に参加または退室したときに実行されるアクションを示します。 既定値は "UseNames です。これは、アナウンスが有効になっている場合に、" Ken Myer が会議に参加しました "ということを意味します。
    
    これらの設定は、グローバル スコープまたはサイト スコープで構成できます。 サイト スコープで構成した設定は、グローバル スコープで構成した設定より優先されます。
    
    次にその例を示します。
    
        Set-CsDialinConferencingConfiguration -Identity site:Redmond
        -EnableNameRecording $false
        -EntryExitAnnouncementsEnabledByDefault $true
        -EntryExitAnnouncementsType ToneOnly
    
    この例では、設定が Redmond のサイト スコープで定義されます。 アナウンスはオンにされますが、会議に参加するときに名前を言うよう参加者が求められることはありません。 参加者が会議に出席または会議から退席するときには、トーン音が再生されます。

</div>

</div>

<span> </span>

</div>

</div>

</div>

