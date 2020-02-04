---
title: 'Lync Server 2013: クライアントのバージョン構成の設定を表示する'
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
ms.openlocfilehash: b6c789275cf33b48e27d60de9a9f9846fc230276
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731117"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-client-version-configuration-settings-in-lync-server-2013"></a>Lync Server 2013 でクライアントのバージョン構成の設定を表示する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-23_

クライアント バージョンの構成設定は、クライアント バージョンの制御を有効または無効にするために使用します。 グローバルクライアントバージョンの構成は、Lync Server 2013 と共にインストールされ、サーバー展開全体でクライアントのバージョン管理を有効または無効にするために使用されます。 グローバル構成を有効にすると、ユーザーがログオンを試みたときに、適用されているすべてのクライアント バージョン ポリシーが有効になります。 クライアントバージョンの構成設定は、Lync Server 2013 コントロールパネルまたは Lync Server 2013 Management Shell で確認できます。

<div>


> [!NOTE]  
> 匿名ユーザーをユーザー、サイト、またはサービスに関連付けることはできないため、匿名ユーザーが影響を受けるのはグローバル レベルのポリシーだけです。



</div>

<div>

## <a name="to-view-client-version-configuration-settings-by-using-lync-server-control-panel"></a>Lync Server コントロールパネルを使用してクライアントのバージョン設定を表示するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで、[**クライアント**] をクリックし、[**クライアントバージョンの構成**] ナビゲーションボタンをクリックします。

4.  表示するクライアントバージョン構成の名前をダブルクリックします。

</div>

<div>

## <a name="viewing-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してクライアントのバージョン構成設定を表示する

クライアントのバージョン構成設定は、「 **CsClientVersionConfiguration**コマンドレット」で確認できます。 このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

<div>

## <a name="to-view-client-version-configuration-information"></a>クライアントのバージョン構成情報を表示するには

  - すべてのクライアントバージョンの構成設定に関する情報を表示するには、Lync Server 管理シェルで次のコマンドを入力し、enter キーを押します。
    
        Get-CsClientVersionConfiguration
    
    次のような情報が表示されます。
    
        Identity      : Global
        DefaultAction : Allow
        DefaultURL    :
        Enabled       : True

</div>

詳細については、「 [CsClientVersionConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsClientVersionConfiguration)コマンドレットのヘルプ」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

