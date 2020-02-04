---
title: クライアントバージョンの構成設定のコレクションを作成または変更する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of client version configuration settings
ms:assetid: 4e6faffd-a36f-40f1-8734-78d84b7df921
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898477(v=OCS.15)
ms:contentKeyID: 50873757
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7fc50696444ddd0602bbf21fd9e05b5bba6eddde
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722567"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-client-version-configuration-settings-in-lync-server-2013"></a>Lync Server 2013 でクライアントのバージョン構成設定のコレクションを作成または変更する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-23_

クライアント バージョンの構成設定は、クライアント バージョンの制御を有効または無効にするために使用します。 グローバルクライアントバージョンの構成は Lync Server と共にインストールされ、サーバーの展開全体に対してクライアントのバージョン管理を有効または無効にするために使用されます。 個々のサイトのクライアントのバージョン構成設定を構成することもできます。 Lync Server 2013 コントロールパネルまたは Lync Server 2013 Management Shell からクライアントバージョンの構成設定を作成または変更することができます。

<div>


> [!NOTE]
> 匿名ユーザーをユーザー、サイト、またはサービスに関連付けることはできないため、匿名ユーザーが影響を受けるのはグローバル レベルのポリシーだけです。



</div>

<div>

## <a name="to-create-or-modify-client-version-configuration-settings-by-using-lync-server-control-panel"></a>Lync Server コントロールパネルを使用してクライアントのバージョン設定を作成または変更するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで、[**クライアント**] をクリックし、[**クライアントバージョンの構成**] ナビゲーションボタンをクリックします。

4.  [**クライアントのバージョン設定**] ページで、次の操作を行います。
    
      - 新しい構成を作成するには、[**新規**] をクリックし、サイトを選択して、[ **OK]** をクリックし、設定を更新します。
    
      - 構成を変更するには、構成を選択し、[**編集**] をクリックし、[**詳細の表示**] をクリックして、設定を変更します。

</div>

<div>

## <a name="creating-or-modifying-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してクライアントのバージョン構成設定を作成または変更する

**新しい-CsClientVersionConfiguration**コマンドレットを使用してクライアントバージョンの構成設定を作成し、**その設定を**変更することができます。 これらのコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

<div>

## <a name="to-create-a-new-collection-of-client-version-configuration-settings"></a>クライアントのバージョン構成設定の新しいコレクションを作成するには

  - 次のコマンドは、Redmond サイトに適用されるクライアントのバージョン構成設定の新しいコレクションを作成します。 この例では、レドモンドサイトのクライアントバージョン管理が無効になっています。
    
        New-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $False

</div>

<div>

## <a name="to-enable-client-versioning-for-a-site"></a>サイトのクライアントのバージョン管理を有効にするには

  - このコマンドにより、レドモンドサイトのクライアントのバージョン管理が有効になります。
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<div>

## <a name="to-disable-client-versioning-throughout-the-organization"></a>組織全体でクライアントのバージョン管理を無効にするには

  - この例では、組織で使用されているすべてのクライアントバージョンの構成設定について、クライアントのバージョン管理が無効になっています。
    
        Get-CsClientVersionConfiguration | Set-CsClientVersionConfiguration  -Enabled $False

</div>

詳細については、「[新しい-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg399029(v=OCS.15)) ()」と「 [csclientversionconfiguration](https://technet.microsoft.com/en-us/library/Gg398623(v=OCS.15))コマンドレットを設定する」のヘルプトピックを参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

