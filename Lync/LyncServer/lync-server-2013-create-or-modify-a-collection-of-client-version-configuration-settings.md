---
title: クライアントバージョン構成設定のコレクションを作成または変更する
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
ms.openlocfilehash: 4d4a3b270ecf35d9fbc33accd8c46909a6e8755b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151899"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-client-version-configuration-settings-in-lync-server-2013"></a>Lync Server 2013 でクライアントバージョン構成設定のコレクションを作成または変更する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-23_

クライアント バージョンの構成設定は、クライアント バージョンの制御を有効または無効にするために使用します。 グローバルクライアントバージョン構成は Lync Server と共にインストールされ、サーバー展開全体に対してクライアントバージョン制御を有効または無効にするために使用されます。 また、個々のサイトのクライアントバージョン構成設定を構成することもできます。 Lync Server 2013 コントロールパネルまたは Lync Server 2013 管理シェルから、クライアントバージョン構成設定を作成または変更することができます。

<div>


> [!NOTE]
> 匿名ユーザーをユーザー、サイト、またはサービスに関連付けることはできないため、匿名ユーザーが影響を受けるのはグローバル レベルのポリシーだけです。



</div>

<div>

## <a name="to-create-or-modify-client-version-configuration-settings-by-using-lync-server-control-panel"></a>Lync Server コントロールパネルを使用してクライアントバージョン構成設定を作成または変更するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーションバーで [**クライアント**] をクリックし、[**クライアントバージョンの構成**] ナビゲーションボタンをクリックします。

4.  [**クライアントバージョン構成**] ページで、次の操作を行います。
    
      - 新しい構成を作成するには、[**新規**] をクリックし、サイトを選択して [ **OK]** をクリックし、設定を更新します。
    
      - 構成を変更するには、構成を選択し、[**編集**]、[**詳細の表示**] の順にクリックし、設定を変更します。

</div>

<div>

## <a name="creating-or-modifying-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してクライアントバージョン構成設定を作成または変更する

クライアントバージョン構成設定を作成するには、**新しい-CsClientVersionConfiguration**コマンドレットを使用し、これらを変更するには、 **Set-csclientversionconfiguration**コマンドレットを使用します。 これらのコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

<div>

## <a name="to-create-a-new-collection-of-client-version-configuration-settings"></a>クライアントバージョン構成設定の新しいコレクションを作成するには

  - 次のコマンドは、Redmond サイトに適用されるクライアントバージョン構成設定の新しいコレクションを作成します。 この例では、Redmond サイトのクライアントバージョン管理は無効になっています。
    
        New-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $False

</div>

<div>

## <a name="to-enable-client-versioning-for-a-site"></a>サイトのクライアントバージョン管理を有効にするには

  - このコマンドは、Redmond サイトのクライアントバージョン管理を有効にします。
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<div>

## <a name="to-disable-client-versioning-throughout-the-organization"></a>組織全体でクライアントのバージョン管理を無効にするには

  - この例では、組織で使用されているすべてのクライアントバージョン構成設定についてクライアントバージョン管理が無効になります。
    
        Get-CsClientVersionConfiguration | Set-CsClientVersionConfiguration  -Enabled $False

</div>

詳細については、ヘルプトピックの「[新しい-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg399029(v=OCS.15)) 」と「 [Set-csclientversionconfiguration](https://technet.microsoft.com/library/Gg398623(v=OCS.15))コマンドレット」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

