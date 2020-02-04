---
title: 'Lync Server 2013: 付録 A: コマンドレットを使用した存続可能ブランチ アプライアンスの展開'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Appendix A: Using cmdlets to deploy a Survivable Branch Appliance'
ms:assetid: 796a26cf-7ec9-453b-8757-6153a6dd86c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398598(v=OCS.15)
ms:contentKeyID: 48184569
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a2da84e03cc05607a47f1fe5af4a8b7987946df
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737797"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appendix-a-using-cmdlets-to-deploy-a-survivable-branch-appliance-in-lync-server-2013"></a>付録 A: Lync Server 2013 でのコマンドレットを使用した存続可能ブランチ アプライアンスの展開

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-07_

このトピックでは、Lync Server Management Shell を使用して Survivable Branch Appliance を展開する方法について説明します。 セントラルサイトでこの手順を実行します。

<div>

## <a name="to-deploy-a-survivable-branch-appliance-remotely"></a>Survivable Branch アプライアンスをリモートで展開するには

1.  新しいブランチサイトを追加するには、「[ブランチサイトを Lync Server 2013 のトポロジに追加](lync-server-2013-add-branch-sites-to-your-topology.md)する」の手順に従います。

2.  ブランチサイトをドメインに参加します。

3.  RTCUniversalSBATechnicians グループをローカルの管理者グループに追加します。

4.  サーバーを再起動し、RTCUniversalSBATechnicians グループのメンバーとしてログオンします。

5.  Lync Server 管理シェルで、次のコマンドを入力します。プレースホルダーは組織の正しい情報で置き換えられます。
    
        Export-CsConfiguration -FileName C:\CSConfig.zip
        Import-CsConfiguration -LocalStore -FileName C:\CSConfig.zip -Verbose
        Enable-CSReplica -Verbose
        Enable-CsComputer -Verbose
        Request-CsCertificate -New -Type default -CA <YourCA> -Verbose
        Set-CsCertificate -Type Default -Thumbprint <YourCertThumbprint>
        Start-cswindowsservice -verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

