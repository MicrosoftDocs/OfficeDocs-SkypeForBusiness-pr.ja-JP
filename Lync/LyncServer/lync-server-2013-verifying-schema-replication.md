---
title: 'Lync Server 2013: スキーマのレプリケーションの確認'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verifying schema replication
ms:assetid: ad01a7cf-aa79-4648-ba5a-a7a09172db36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412822(v=OCS.15)
ms:contentKeyID: 48185124
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7ea90012c116bb66caf16313d930c6f05db4413
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742097"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verifying-active-directory-schema-replication-in-lync-server-2013"></a>Lync Server 2013 での Active Directory スキーマのレプリケーションの確認

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-29_

フォレストの準備を実行する前に、スキーマパーティションがレプリケートされていることを手動で確認します。

<div>

## <a name="to-manually-verify-schema-replication"></a>スキーマレプリケーションを手動で確認するには

1.  Enterprise Admins グループのメンバーとしてドメインコントローラーにログオンします。

2.  [**スタート**] をクリックし、[**管理ツール**] をクリックして、[ **adsi の編集**] をクリックして、adsi の編集を開きます。
    
    <div>
    

    > [!TIP]  
    > または、コマンドラインから<STRONG>adsiedit</STRONG>を実行することもできます。

    
    </div>

3.  Microsoft 管理コンソール (MMC) ツリーでまだ選択されていない場合は、[ **ADSI edit**] をクリックします。

4.  [**アクション**] メニューで、[**接続**] をクリックします。

5.  [**接続の設定**] ダイアログ ボックスの [**既知の名前付けコンテキストを選択する**] で、[**スキーマ**] を選択して [**OK**] をクリックします。

6.  スキーマ コンテナーで、CN=ms-RTC-SIP-SchemaVersion を検索します。 このオブジェクトが存在し、 **Rangeupper**属性の値が1150であり、 **rangeupper**属性の値が3の場合は、スキーマが正常に更新され、複製されています。 このオブジェクトが存在しない場合、または**Rangeupper**属性と**rangeupper**属性の値が指定されていない場合は、スキーマが変更されなかったか、レプリケートされませんでした。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での Active Directory スキーマの準備の実行](lync-server-2013-running-schema-preparation.md)  


[Lync Server 2013 での Active Directory スキーマの準備](lync-server-2013-preparing-the-active-directory-schema.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

