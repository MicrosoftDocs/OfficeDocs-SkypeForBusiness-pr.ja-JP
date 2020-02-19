---
title: 'Lync Server 2013: スキーマレプリケーションの確認'
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
ms.openlocfilehash: e709e102af7b2f286361e0ad4c6323025d4a25e9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136945"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verifying-active-directory-schema-replication-in-lync-server-2013"></a>Lync Server 2013 での Active Directory スキーマのレプリケーションの確認

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-29_

フォレストの準備を実行する前に、スキーマパーティションがレプリケートされたことを手動で確認してください。

<div>

## <a name="to-manually-verify-schema-replication"></a>スキーマのレプリケーションを手動で確認するには

1.  Enterprise Admins グループのメンバーとしてドメイン コントローラーにログオンします。

2.  **[スタート]** をクリックして **[管理ツール]** をクリックし、**[ADSI エディター]** をクリックして ADSI エディターを開きます。
    
    <div>
    

    > [!TIP]  
    > または、コマンド ラインから <STRONG>adsiedit.msc</STRONG> を実行することもできます。

    
    </div>

3.  Microsoft 管理コンソール (MMC) ツリーで、まだ選択されていない場合には **[ADSI エディター]** をクリックします。

4.  **[アクション]** メニューで、**[接続]** をクリックします。

5.  **[接続の設定]** ダイアログ ボックスの **[既知の名前付けコンテキストを選択する]** で、**[スキーマ]** を選択して **[OK]** をクリックします。

6.  スキーマ コンテナーで、CN=ms-RTC-SIP-SchemaVersion を検索します。 このオブジェクトが存在し、**rangeUpper** 属性の値が 1150 で、**rangeLower** 属性の値が 3 の場合、スキーマは正しく更新され、レプリケートされています。 このオブジェクトが存在しないか、**rangeUpper** および **rangeLower** 属性の値が指定された値と異なる場合、スキーマは変更されていないか、レプリケートされていません。

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

