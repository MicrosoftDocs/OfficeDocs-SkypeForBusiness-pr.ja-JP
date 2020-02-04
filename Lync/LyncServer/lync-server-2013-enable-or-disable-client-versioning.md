---
title: 'Lync Server 2013: クライアントのバージョン管理を有効または無効にする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable client versioning
ms:assetid: 33a98cb9-a979-4bb6-afb2-512f601d7ac5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898475(v=OCS.15)
ms:contentKeyID: 50873755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f413df3ec1d35438155492a32d9fdff449aec3c3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736197"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-client-versioning-in-lync-server-2013"></a>Lync Server 2013 でクライアントのバージョン管理を有効または無効にする

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-23_

クライアントバージョンの構成設定は、グローバルに、または特定のサイトに対して、クライアントのバージョン管理をオンまたはオフにするために使用されます。 グローバルクライアントバージョンの構成は、Lync Server 2013 と共にインストールされ、サーバー展開全体でクライアントのバージョン管理を有効または無効にするために使用されます。 グローバル構成が有効になっている場合は、ユーザーがログオンしようとしたときに、使用しているクライアントバージョンポリシーが有効になります。 クライアントのバージョン管理を行わない場合は、グローバルクライアントのバージョン設定を無効にすることができます。 Lync Server 2013 コントロールパネルまたは Lync Server 2013 Management Shell からクライアントのバージョン管理を有効または無効にすることができます。

<div>


> [!NOTE]  
> 匿名ユーザーをユーザー、サイト、またはサービスに関連付けることはできないため、匿名ユーザーが影響を受けるのはグローバル レベルのポリシーだけです。



</div>

<div>

## <a name="to-enable-or-disable-client-versioning-by-using-lync-server-control-panel"></a>Lync Server コントロールパネルを使用してクライアントのバージョン管理を有効または無効にするには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで、[**クライアント**] をクリックし、[**クライアントバージョンの構成**] ナビゲーションボタンをクリックします。

4.  次の手順を実行します。
    
      - クライアントのバージョン管理をグローバルに有効または無効にするには、**グローバル**構成をダブルクリックして、設定を変更します。
    
      - 特定のサイトのクライアントのバージョン管理を有効または無効にするには、[**新規**] をクリックし、サイトを選択し、[ **OK**] をクリックして、サイトの設定を変更します。

</div>

<div>

## <a name="enabling-or-disabling-client-versioning-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してクライアントのバージョン管理を有効または無効にする

クライアントのバージョン管理を有効または無効にするには、 **Set-CsClientVersionConfiguration**コマンドレットを使用します。 このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

<div>

## <a name="to-enable-client-versioning"></a>クライアントのバージョン管理を有効にするには

  - クライアントのバージョン管理を有効にするには、 **Enabled**プロパティを True ($True) に設定します。
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<div>

## <a name="to-disable-client-versioning"></a>クライアントのバージョン管理を無効にするには

  - クライアントのバージョン管理を無効にするには、 **Enabled**プロパティを False ($False) に設定します。
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

詳細については、「 [Set-CsClientVersionConfiguration)](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionConfiguration)コマンドレットのヘルプトピックを参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

