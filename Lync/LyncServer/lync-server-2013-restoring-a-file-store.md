---
title: 'Lync Server 2013: ファイルストアを復元する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring a file store
ms:assetid: 89916fc6-31d3-4c7f-9eaf-c02584761ef4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202180(v=OCS.15)
ms:contentKeyID: 51541491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc9f1bae4e1a9a84815e576267a15155bec227da
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823085"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-file-store-in-lync-server-2013"></a>Lync Server 2013 でのファイルストアの復元

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-18_

標準エディション用のファイルストアは、通常 Standard Edition サーバーにあります。 Enterprise Edition のファイルストアは、通常はファイルサーバーまたはクラスターにあります。 次の手順では、ファイルストアを復元する方法について説明します。

<div>

## <a name="to-restore-a-file-store"></a>ファイルストアを復元するには

1.  ファイルストアに障害が発生した場合は、該当する\\ファイルストアを $Backup からファイルサーバーまたは Standard Edition サーバー上のファイルストアの場所にコピーして、フォルダーを共有します。
    
    <div>
    

    > [!IMPORTANT]  
    > 復元されたファイルストアのパスとファイル名は、バックアップされたファイルストアとまったく同じである必要があります。これにより、ファイルを使用するコンポーネントがアクセスできるようになります。

    
    </div>

2.  必要に応じて、ファイルストアのアクセス制御リスト (Acl) を設定します。 コマンド ラインで次を入力します。
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > この手順を実行する必要があるのは、復元プロセスでトポロジビルダーを実行していない場合のみです。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

