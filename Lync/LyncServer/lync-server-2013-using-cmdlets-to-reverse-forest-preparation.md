---
title: 'Lync Server 2013: コマンドレットの使用によるフォレストの準備のリバース'
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
ms.openlocfilehash: 2b893eb79cb19856572e90bd449b315f0ade803c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744187"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-cmdlets-to-reverse-forest-preparation-for-lync-server-2013"></a>コマンドレットの使用による Lync Server 2013 のフォレストの準備のリバース

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-06-19_

[**無効化-CsAdForest** ] コマンドレットを使用して、フォレストの準備手順を逆にします。

<div>


> [!WARNING]  
> 以前のバージョンの Lync Server が展開されている環境で、 <STRONG>CsAdForest</STRONG>コマンドレットを無効にすると、以前のバージョンのグローバル設定も削除されます。



</div>

<div>

## <a name="to-use-cmdlets-to-reverse-forest-preparation"></a>コマンドレットを使用してフォレストの準備を逆にするには

1.  フォレストルートドメインの Domain Admins グループのメンバーとしてドメインに参加しているコンピューターにログオンします。

2.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

3.  次のコマンドレットを実行します。
    
        Disable-CsAdForest [-Force] [-GroupDomain <FQDN of the domain in which universal groups were created>]
    
    次に例を示します。
    
        Disable-CsAdForest -Force -GroupDomain contoso.net
    
    Force パラメーターは、タスクを強制的に実行するかどうかを指定します。 このパラメーターが存在しない場合は、フォレスト内の1つのドメインがまだ Lync Server 2013 用に準備されている場合、コマンドは実行されません。 Force パラメーターを指定した場合、フォレスト内の他のドメインの状態に関係なく、操作は続行されます。
    
    GroupDomain パラメーターを指定しない場合、既定値はローカルドメインです。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのフォレストの準備の実行](lync-server-2013-running-forest-preparation.md)  


[Lync Server 2013 でのフォレストの準備](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

