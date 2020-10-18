---
title: 'Lync Server 2013: コマンドレットを使用してフォレストの準備を元に戻す'
description: 'Lync Server 2013: コマンドレットを使用してフォレストの準備を元に戻します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using cmdlets to reverse forest preparation
ms:assetid: f48c7eb3-ccb0-48e6-ac79-ab7c7062b9d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413024(v=OCS.15)
ms:contentKeyID: 48185822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: acac87bdaeb7e730f93401fa62ea2678a713bb8f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580393"
---
# <a name="using-cmdlets-to-reverse-forest-preparation-for-lync-server-2013"></a>コマンドレットを使用して Lync Server 2013 のフォレストの準備を元に戻す

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-06-19_

フォレストの準備手順を元に戻すには、 **Disable-CsAdForest** コマンドレットを使用します。

<div>


> [!WARNING]  
> 以前のバージョンの Lync Server が展開されている環境で、 <STRONG>Disable-CsAdForest</STRONG> コマンドレットを実行すると、以前のバージョンのグローバル設定も削除されます。



</div>

<div>

## <a name="to-use-cmdlets-to-reverse-forest-preparation"></a>コマンドレットを使用してフォレストの準備を元に戻すには

1.  ドメインに参加しているコンピューターに、フォレストのルート ドメインの Domain Admins グループ メンバーとしてログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

3.  実行
    
        Disable-CsAdForest [-Force] [-GroupDomain <FQDN of the domain in which universal groups were created>]
    
    次に例を示します。
    
        Disable-CsAdForest -Force -GroupDomain contoso.net
    
    Force パラメーターは、タスクを強制的に実行するかどうかを指定します。 このパラメーターが存在しない場合、フォレスト内の1つのドメインが Lync Server 2013 に対してまだ準備されている場合、コマンドは実行されません。 Force パラメーターが指定されている場合、フォレスト内の他のドメインの状態に関係なく、アクションは続行されます。
    
    GroupDomain パラメーターを指定しない場合、既定値はローカル ドメインになります。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 のフォレストの準備の実行](lync-server-2013-running-forest-preparation.md)  


[Lync Server 2013 のフォレストの準備](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

