---
title: 'Lync Server 2013: クライアントバージョンポリシールールの表示'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View client version policy rules
ms:assetid: f3a0215f-f72f-4e9b-a07b-25858dc4203a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ923060(v=OCS.15)
ms:contentKeyID: 50675350
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa0b6166a3bf8c21c6d2eddcd9152c9c7d4efc37
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136825"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-client-version-policy-rules-in-lync-server-2013"></a>Lync Server 2013 でクライアントバージョンポリシールールを表示する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-23_

クライアントバージョンポリシーは、一連のクライアントバージョンポリシールールで構成されています。 これらのルールでは、ユーザーが特定のクライアントおよびクライアント バージョンでログオンしようとしたときに実行するアクションが定義されています。 Lync Server 2013 コントロールパネルまたは Lync Server 2013 管理シェルからクライアントバージョンポリシールールを表示できます。

<div>

## <a name="to-view-client-version-policy-rules-by-using-lync-server-control-panel"></a>Lync Server コントロールパネルを使用してクライアントバージョンポリシールールを表示するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーションバーで [**クライアント**] をクリックし、[**クライアントバージョンポリシー** ] ナビゲーションボタンをクリックします。

4.  [**クライアントバージョンポリシー** ] ページで、表示するクライアントバージョンポリシーをダブルクリックします。

5.  ルールは [**クライアントバージョンポリシーの編集**] ページに表示されます。 ルールの詳細を表示するには、ルールを選択し、[**詳細の表示**] をクリックします。

</div>

<div>

## <a name="viewing-client-version-policy-rules-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してクライアントバージョンポリシールールを表示する

Lync Server 管理シェルと**Get-CsClientVersionPolicyRule**コマンドレットを使用して、クライアントバージョンポリシールールを表示できます。 このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

<div>

## <a name="to-view-client-version-policy-rules"></a>クライアントバージョンポリシールールを表示するには

  - クライアントバージョンポリシールールを表示するには、Lync Server 管理シェルで次のコマンドを入力し、ENTER キーを押します。
    
        Get-CsClientVersionPolicyRule
    
    これにより、構成済みの各ルールについて次のような情報が返されます。
    
        Identity          : Global/2336c611-a243-4c5d-994b-eea8a524d0e4
        Priority          : 0
        RuleId            : 2336c611-a243-4c5d-994b-eea8a524d0e4
        Description       :
        Action            : Block
        ActionUrl         :
        MajorVersion      : 1
        MinorVersion      : 3
        BuildNumber       :
        QfeNumber         :
        UserAgent         : RTC
        UserAgentFullName :
        Enabled           : True
        CompareOp         : LEQ

</div>

詳細については、「 [get-help](https://docs.microsoft.com/powershell/module/skype/Get-CsClientVersionPolicyRule) 」というヘルプトピックを参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

