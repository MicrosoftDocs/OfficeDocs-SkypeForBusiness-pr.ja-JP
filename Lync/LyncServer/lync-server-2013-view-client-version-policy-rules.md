---
title: 'Lync Server 2013: クライアントのバージョンポリシールールを表示する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View client version policy rules
ms:assetid: f3a0215f-f72f-4e9b-a07b-25858dc4203a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ923060(v=OCS.15)
ms:contentKeyID: 50675350
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2f4bf9d60d9f99addffed25a87b05ea91650294
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848218"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-client-version-policy-rules-in-lync-server-2013"></a>Lync Server 2013 でクライアントのバージョンポリシールールを表示する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-23_

クライアントのバージョンポリシーは、一連のクライアントバージョンポリシールールで構成されています。 これらのルールでは、ユーザーが特定のクライアントおよびクライアント バージョンでログオンしようとしたときに実行するアクションが定義されています。 Lync Server 2013 コントロールパネルまたは Lync Server 2013 管理シェルからクライアントのバージョンポリシールールを表示できます。

<div>

## <a name="to-view-client-version-policy-rules-by-using-lync-server-control-panel"></a>Lync Server コントロールパネルを使用してクライアントのバージョンポリシールールを表示するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで、[**クライアント**] をクリックし、[**クライアントバージョンポリシー** ] ナビゲーションボタンをクリックします。

4.  [**クライアントのバージョンポリシー** ] ページで、表示するクライアントのバージョンポリシーをダブルクリックします。

5.  [**クライアントのバージョンポリシーの編集**] ページにルールが表示されます。 ルールの詳細を表示するには、ルールを選択し、[**詳細の表示**] をクリックします。

</div>

<div>

## <a name="viewing-client-version-policy-rules-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してクライアントのバージョンポリシールールを表示する

Lync Server 管理シェルと、 **CsClientVersionPolicyRule rule**コマンドレットを使用して、クライアントのバージョンポリシールールを表示できます。 このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。

<div>

## <a name="to-view-client-version-policy-rules"></a>クライアントのバージョンポリシールールを表示するには

  - クライアントのバージョンポリシールールを表示するには、Lync Server 管理シェルで次のコマンドを入力し、enter キーを押します。
    
        Get-CsClientVersionPolicyRule
    
    これは、構成されている各ルールについて、次のような情報を返します。
    
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

詳細については、「 [CsClientVersionPolicyRule rule](https://docs.microsoft.com/powershell/module/skype/Get-CsClientVersionPolicyRule) 」コマンドレットのヘルプトピックを参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

