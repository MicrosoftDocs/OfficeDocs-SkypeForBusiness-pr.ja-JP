---
title: 'Lync Server 2013: クライアントバージョン構成設定の表示'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View client version configuration settings
ms:assetid: c72df4e6-a889-4cb6-86f7-8334d7774c6e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ923062(v=OCS.15)
ms:contentKeyID: 50675353
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1ec472bff967bc2a8ffb75d09e3515654487be41
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506604"
---
# <a name="view-client-version-configuration-settings-in-lync-server-2013"></a>Lync Server 2013 でクライアントバージョンの構成設定を表示する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-23_

クライアント バージョンの構成設定は、クライアント バージョンの制御を有効または無効にするために使用します。 グローバルクライアントバージョン構成は、Lync Server 2013 と共にインストールされ、サーバー展開全体でクライアントバージョン管理を有効または無効にするために使用されます。 グローバル構成を有効にすると、ユーザーがログオンを試みたときに、適用されているすべてのクライアント バージョン ポリシーが有効になります。 Lync Server 2013 コントロールパネルまたは Lync Server 2013 管理シェルから、クライアントバージョン構成設定を表示できます。

<div>


> [!NOTE]  
> 匿名ユーザーをユーザー、サイト、またはサービスに関連付けることはできないため、匿名ユーザーが影響を受けるのはグローバル レベルのポリシーだけです。



</div>

<div>

## <a name="to-view-client-version-configuration-settings-by-using-lync-server-control-panel"></a>Lync Server コントロールパネルを使用してクライアントバージョンの構成設定を表示するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーションバーで [ **クライアント**] をクリックし、[ **クライアントバージョンの構成** ] ナビゲーションボタンをクリックします。

4.  表示するクライアントバージョン構成の名前をダブルクリックします。

</div>

<div>

## <a name="viewing-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してクライアントバージョン構成設定を表示する

クライアントバージョンの構成設定を表示するには、 **get-help** コマンドレットを使用します。 このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

<div>

## <a name="to-view-client-version-configuration-information"></a>クライアントバージョン構成情報を表示するには

  - すべてのクライアントバージョン構成設定に関する情報を表示するには、Lync Server 管理シェルで次のコマンドを入力し、ENTER キーを押します。
    
        Get-CsClientVersionConfiguration
    
    次のような情報が表示されます。
    
        Identity      : Global
        DefaultAction : Allow
        DefaultURL    :
        Enabled       : True

</div>

詳細については、「Get-help for [CsClientVersionConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsClientVersionConfiguration) コマンドレット」のヘルプトピックを参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

