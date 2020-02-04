---
title: 'Lync Server 2013: 新しいクライアントのバージョンポリシーを作成または変更する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a new client version policy
ms:assetid: 4be6e449-aa82-4b46-abb1-d31281573a72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898476(v=OCS.15)
ms:contentKeyID: 50873756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1469bb017f9597bcd1fffba54f39e62dc0bd6e96
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722437"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-new-client-version-policy-in-lync-server-2013"></a>Lync Server 2013 で新しいクライアントのバージョンポリシーを作成または変更する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-23_

クライアントバージョンポリシーを使って、環境でサポートされているクライアントのバージョンを指定することができます。 クライアントのバージョン管理を使用すると、複数のクライアントバージョンのサポートに関連するコストを削減することができます。 また、以前のバージョンのクライアントが動作している場合、使用可能な機能は以前のバージョンのクライアントで制限される可能性があるため、全体的なユーザーエクスペリエンスを向上させることができます。 Lync Server 2013 コントロールパネルまたは Lync Server 2013 Management Shell からクライアントのバージョンポリシーを作成または変更することができます。

<div>

## <a name="to-create-or-modify-client-version-policies-by-using-lync-server-control-panel"></a>Lync Server コントロールパネルを使用してクライアントのバージョンポリシーを作成または変更するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで、[**クライアント**] をクリックします。
    
    <div>
    

    > [!NOTE]  
    > 既定では、[<STRONG>クライアントのバージョンポリシー</STRONG> ] タブが選択されています。

    
    </div>

4.  [**クライアントのバージョンポリシー** ] ページで、次のいずれかの操作を行います。
    
      - クライアントのバージョンポリシーを作成するには、[**新規**] をクリックし、[**サイトポリシー**]、[**プールポリシー**]、または [**ユーザーポリシー**] を選択して、[ **OK**] をクリックします。
    
      - グローバルポリシーまたは別の既存のクライアントのバージョンポリシーを変更するには、ポリシーを選択し、[**編集**] をクリックして、[**詳細の表示**] をクリックします。

5.  [**クライアントバージョンポリシーの編集**] ページで、「[新しいクライアントのバージョンポリシールールを作成または変更する」の「Lync Server 2013 で](lync-server-2013-create-or-modify-a-new-client-version-policy-rule.md)ルールを作成または変更する」を参照してください。

</div>

<div>

## <a name="creating-or-modifying-client-version-policies-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してクライアントのバージョンポリシーを作成または変更する

クライアントバージョンポリシーを作成するには、**新しい-csclientversionpolicy**コマンドレットを使用し、 **Set-csclientversionpolicy**コマンドレットを使用してそれらを変更します。 これらのコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

<div>

## <a name="to-create-a-new-site-scoped-client-version-policy"></a>新しいサイトスコープのクライアントバージョンポリシーを作成するには

  - 次のコマンドは、Redmond サイトに適用される新しいクライアントバージョンのポリシーを作成します。 追加のパラメーターを指定しないため、新しいポリシーでは既定のクライアントバージョンの設定が使用されます。
    
        New-CsClientVersionPolicy -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-per-user-client-version-policy"></a>新しいユーザーごとのクライアントバージョンポリシーを作成するには

  - ユーザーごとのポリシーを作成するには、次のようなコマンドを使用します。
    
        New-CsClientVersionPolicy -Identity "RedmondClientVersionPolicy"

</div>

詳細については、[新しい-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientVersionPolicy)コマンドレットと[Set-csclientversionpolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionPolicy)コマンドレットのヘルプトピックを参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

