---
title: 'Lync Server 2013: ダイヤルイン会議アクセス番号の表示'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View dial-in conferencing access numbers
ms:assetid: 41a7dfb4-0c89-4650-b61b-0e1bf875c62b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688037(v=OCS.15)
ms:contentKeyID: 49733628
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 851ac4d48a5242355baa1f25499dcaf26e8ef099
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043739"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-dial-in-conferencing-access-numbers-in-lync-server-2013"></a>Lync Server 2013 でのダイヤルイン会議アクセス番号の表示

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-23_

Lync Server 2013 コントロールパネルでは、ユーザーがダイヤルインアクセス番号を提供して、外部に会議に参加できるようにします。

<div>

## <a name="to-view-dial-in-access-numbers"></a>ダイヤルイン アクセス番号を表示するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**会議**] をクリックし、[**ダイヤルイン アクセス番号**] をクリックします。

4.  [**ダイヤルイン アクセス番号**] ページで、表示するアクセス番号をクリックします。

5.  [**編集**] で、[**詳細の表示**] チェック ボックスをオンにします。

</div>

<div>

## <a name="viewing-dial-in-conferencing-access-numbers-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してダイヤルイン会議アクセス番号を表示する

ダイヤルイン会議アクセス番号は、Windows PowerShell と Get-csdialinconferencingaccessnumber コマンドレットを使用して表示できます。 このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

<div>

## <a name="to-view-dial-in-conferencing-access-numbers"></a>ダイヤルイン会議アクセス番号を表示するには

  - すべてのダイヤルイン会議アクセス番号に関する情報を表示するには、Lync Server 管理シェルで次のコマンドを入力し、ENTER キーを押します。
    
        Get-CsDialInConferencingAccessNumber
    
    次のような情報が表示されます。
    
        Identity           : CN={20ca8dc8-5ff8-41f4-b5bb-22ba9972ae2e},
                             CN=Application Contacts,CN=RTCService=Services,
                             CN=Configuration,DC=litwareinc,DC=com
        PrimaryUri         : sip:testnumber@litwareinc.com
        DisplayName        : Test
        DisplayNumber      : 1-425-555-1019
        LineUri            : tel:+14255551019
        PrimaryLanguage    : en-US
        SecondaryLanguages : {}
        Pool               : atl-cs-001.litwareinc.com
        HostingProvider    :
        Regions            : {US}

</div>

詳細については、 [get-csdialinconferencingaccessnumber](https://docs.microsoft.com/powershell/module/skype/Get-CsDialInConferencingAccessNumber)コマンドレットのヘルプトピックを参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

