---
title: 'Lync Server 2013: 新しいクライアントバージョンポリシーの作成または変更'
description: 'Lync Server 2013: 新しいクライアントバージョンポリシーを作成または変更します。'
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
ms.openlocfilehash: d4d100e21591a27646784161614ff6c248dc6ae6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574613"
---
# <a name="create-or-modify-a-new-client-version-policy-in-lync-server-2013"></a>Lync Server 2013 で新しいクライアントバージョンポリシーを作成または変更する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-23_

クライアントバージョンポリシーを使用して、環境でサポートされているクライアントのバージョンを指定できます。 クライアントのバージョン管理を使用すると、複数のクライアントバージョンをサポートするためのコストを削減できます。 また、クライアントの以前のバージョンとそれ以降のバージョンでは、使用可能な機能が以前のバージョンのクライアントによって制限される可能性があるため、ユーザーの全体的な操作が向上します。 Lync Server 2013 コントロールパネルまたは Lync Server 2013 管理シェルからクライアントバージョンポリシーを作成または変更することができます。

<div>

## <a name="to-create-or-modify-client-version-policies-by-using-lync-server-control-panel"></a>Lync Server コントロールパネルを使用してクライアントバージョンポリシーを作成または変更するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーションバーで [ **クライアント**] をクリックします。
    
    <div>
    

    > [!NOTE]  
    > 既定では、[ <STRONG>クライアントバージョンポリシー</STRONG> ] タブが選択されています。

    
    </div>

4.  [ **クライアントバージョンポリシー** ] ページで、次のいずれかの操作を行います。
    
      - クライアントバージョンポリシーを作成するには、[ **新規**] をクリックし、[ **サイトポリシー**]、[ **プールポリシー**]、または [ **ユーザーポリシー**] をクリックして、[ **OK**] をクリックします。
    
      - グローバルポリシーまたは既存のクライアントバージョンポリシーを変更するには、ポリシーを選択し、[ **編集**] をクリックしてから、[ **詳細の表示**] をクリックします。

5.  [ **クライアントバージョンポリシーの編集** ] ページで、「 [Lync Server 2013 の新しいクライアントバージョンポリシールールを作成または変更する](lync-server-2013-create-or-modify-a-new-client-version-policy-rule.md)」の説明に従ってルールを作成または変更します。

</div>

<div>

## <a name="creating-or-modifying-client-version-policies-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してクライアントバージョンポリシーを作成または変更する

**新しい-csclientversionpolicy**コマンドレットを使用してクライアントバージョンポリシーを作成し、それを変更するには、 **Set-csclientversionpolicy**コマンドレットを使用します。 これらのコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

<div>

## <a name="to-create-a-new-site-scoped-client-version-policy"></a>サイトスコープの新しいクライアントバージョンポリシーを作成するには

  - 次のコマンドは、Redmond サイトに適用される新しいクライアントバージョンポリシーを作成します。 追加のパラメーターは指定されていないため、新しいポリシーでは既定のクライアントバージョン設定が使用されます。
    
        New-CsClientVersionPolicy -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-per-user-client-version-policy"></a>新しいユーザーごとのクライアントバージョンポリシーを作成するには

  - ユーザーごとのポリシーを作成するには、次のようなコマンドを使用します。
    
        New-CsClientVersionPolicy -Identity "RedmondClientVersionPolicy"

</div>

詳細については、「 [New-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientVersionPolicy) コマンドレット」および「 [Set-csclientversionpolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionPolicy) コマンドレット」のヘルプトピックを参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

