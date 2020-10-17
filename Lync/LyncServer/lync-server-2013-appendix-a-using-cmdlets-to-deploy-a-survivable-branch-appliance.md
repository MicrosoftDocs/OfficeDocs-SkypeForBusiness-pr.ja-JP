---
title: 'Lync Server 2013: 付録 A: コマンドレットを使用した存続可能ブランチアプライアンスの展開'
description: 'Lync Server 2013: 付録 A: コマンドレットを使用して存続可能ブランチアプライアンスを展開する。'
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
ms.openlocfilehash: 6bf1fe5d86900ec5da95ed9020720149a5015f19
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561873"
---
# <a name="appendix-a-using-cmdlets-to-deploy-a-survivable-branch-appliance-in-lync-server-2013"></a>付録 A: コマンドレットを使用して Lync Server 2013 で存続可能ブランチアプライアンスを展開する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-07_

このトピックでは、Lync Server 管理シェルを使用して存続可能ブランチアプライアンスを展開する方法について説明します。 中央サイトでこの手順を実行します。

<div>

## <a name="to-deploy-a-survivable-branch-appliance-remotely"></a>存続可能 Branch アプライアンスをリモートで展開するには

1.  新しいブランチサイトを追加するには、「 [Lync Server 2013 でブランチサイトをトポロジに追加](lync-server-2013-add-branch-sites-to-your-topology.md) する」の手順に従ってください。

2.  ブランチ サイトをドメインに参加させます。

3.  RTCUniversalSBATechnicians グループをローカルの Administrators グループに追加します。

4.  サーバーを再起動し、RTCUniversalSBATechnicians グループのメンバーとしてサーバーにログオンします。

5.  Lync Server 管理シェルで、次のコマンドを入力します。プレースホルダーは、組織の正しい情報に置き換えられます。
    
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

