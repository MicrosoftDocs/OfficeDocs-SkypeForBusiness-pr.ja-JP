---
title: 'Lync Server 2013: ファイルストアの復元'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a file store
ms:assetid: 89916fc6-31d3-4c7f-9eaf-c02584761ef4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202180(v=OCS.15)
ms:contentKeyID: 51541491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b73ba97ccadcc5cb34a5dbc3963d80620da8e516
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214823"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-a-file-store-in-lync-server-2013"></a>Lync Server 2013 でのファイルストアの復元

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-18_

Standard Edition のファイルストアは、通常、Standard Edition サーバーにあります。 Enterprise Edition のファイル ストアは、通常、ファイル サーバーまたはクラスター上に配置されています。 次の手順では、ファイルストアを復元する方法について説明します。

<div>

## <a name="to-restore-a-file-store"></a>ファイル ストアを復元するには

1.  ファイルストアが失敗した場合は、適切なファイルストア\\を $Backup からファイルサーバーまたは Standard Edition サーバー上のファイルストアの場所にコピーして、そのフォルダーを共有します。
    
    <div>
    

    > [!IMPORTANT]  
    > 復元されたファイルストアのパスおよびファイル名は、バックアップされたファイルストアと正確に一致する必要があるため、ファイルを使用するコンポーネントはそれらにアクセスできます。

    
    </div>

2.  必要に応じて、ファイルストアのアクセス制御リスト (Acl) を設定します。 コマンドラインで、次のように入力します。
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > この手順は、復元処理中にトポロジビルダーを実行しない場合にのみ実行する必要があります。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

