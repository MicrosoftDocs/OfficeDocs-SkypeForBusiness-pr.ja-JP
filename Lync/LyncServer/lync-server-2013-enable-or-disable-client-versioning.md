---
title: 'Lync Server 2013: クライアントのバージョン管理を有効または無効にする'
description: 'Lync Server 2013: クライアントのバージョン管理を有効または無効にします。'
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
ms.openlocfilehash: 0bbd190e827e028efc37365c3cd8ecab16b35dac
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546623"
---
# <a name="enable-or-disable-client-versioning-in-lync-server-2013"></a>Lync Server 2013 でクライアントのバージョン管理を有効または無効にする

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-23_

クライアントバージョンの構成設定を使用して、クライアントバージョンの制御をグローバルに、または特定のサイトに対して有効または無効にします。 グローバルクライアントバージョン構成は、Lync Server 2013 と共にインストールされ、サーバー展開全体でクライアントバージョン管理を有効または無効にするために使用されます。 グローバル構成が有効になっている場合、ユーザーがログオンを試行すると、設定したすべてのクライアントバージョンポリシーが有効になります。 クライアントバージョン管理を行わない場合は、グローバルクライアントバージョン構成を無効にすることができます。 Lync Server 2013 コントロールパネルまたは Lync Server 2013 管理シェルから、クライアントのバージョン管理を有効または無効にすることができます。

<div>


> [!NOTE]  
> 匿名ユーザーをユーザー、サイト、またはサービスに関連付けることはできないため、匿名ユーザーが影響を受けるのはグローバル レベルのポリシーだけです。



</div>

<div>

## <a name="to-enable-or-disable-client-versioning-by-using-lync-server-control-panel"></a>Lync Server コントロールパネルを使用してクライアントのバージョン管理を有効または無効にするには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーションバーで [ **クライアント**] をクリックし、[ **クライアントバージョンの構成** ] ナビゲーションボタンをクリックします。

4.  次の操作を実行してください。
    
      - クライアントのバージョン管理をグローバルに有効または無効にするには、 **グローバル** 構成をダブルクリックし、設定を変更します。
    
      - 特定のサイトのクライアントバージョン管理を有効または無効にするには、[ **新規**] をクリックし、サイトを選択して [ **OK**] をクリックし、サイトの設定を変更します。

</div>

<div>

## <a name="enabling-or-disabling-client-versioning-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してクライアントのバージョン管理を有効または無効にする

クライアントのバージョン管理を有効または無効にするには、 **Set-CsClientVersionConfiguration** コマンドレットを使用します。 このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

<div>

## <a name="to-enable-client-versioning"></a>クライアントのバージョン管理を有効にするには

  - クライアントのバージョン管理を有効にするには、 **Enabled** プロパティを True ($True) に設定します。
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<div>

## <a name="to-disable-client-versioning"></a>クライアントのバージョン管理を無効にするには

  - **Enabled**プロパティを False ($False) に設定すると、クライアントのバージョン管理を無効にすることができます。
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

詳細については、「 [Set-CsClientVersionConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionConfiguration) コマンドレット」のヘルプトピックを参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

