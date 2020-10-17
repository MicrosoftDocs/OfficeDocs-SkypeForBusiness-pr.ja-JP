---
title: 'Lync Server 2013: アーカイブ用のシステムプラットフォームのセットアップ'
description: 'Lync Server 2013: アーカイブ用のシステムプラットフォームのセットアップ。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up system platforms for Archiving
ms:assetid: 2df40fdf-0e32-46d4-9fb2-1ce1d7bfa328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204768(v=OCS.15)
ms:contentKeyID: 48183716
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f210083451ae8fcb87c53e52b5512de6f1f18d0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554183"
---
# <a name="setting-up-system-platforms-for-archiving-in-lync-server-2013"></a>Lync Server 2013 でのアーカイブ用のシステムプラットフォームのセットアップ

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-09_

アーカイブの展開を開始する前に、システム要件を満たすハードウェアに、必要なオペレーティング システムとその他の必須ソフトウェアをインストールする必要があります。

  - **Lync Server 2013 プラットフォーム**    Lync Server 2013 の展開には、アーカイブサーバーがありません。 代わりに、統合データ収集エージェントはフロントエンドサーバーと Standard Edition サーバー上で実行されてアーカイブ用のデータをキャプチャするため、アーカイブをホストするために個別のシステムプラットフォームは必要ありません。

  - **データストレージプラットフォーム**    Lync Server 2013 では、次のいずれかを使用してデータを保存できます。
    
      - **Microsoft Exchange 統合**    アーカイブデータを格納するために別のデータベースをセットアップするのではなく、Exchange 2013 展開を使用して Lync Server 2013 アーカイブデータを保存する場合は、exchange の展開で Exchange 2013 を実行している必要があります。 Exchange 2013 用のシステムプラットフォームのセットアップの詳細については、「Exchange 製品のドキュメント」を参照してください。
    
      - **SQL Server**    アーカイブデータの保存に別の SQL Server データベースを使用する場合は、Microsoft Exchange 統合を使用するのではなく、アーカイブを展開する前にデータベースのシステムプラットフォームを設定する必要があります。 特定のシステムプラットフォームの要件は、アーカイブデータベースに Microsoft SQL Server 2008 R2 と Microsoft SQL Server 2012 のどちらを使用するかによって異なります。 これらのデータベースのシステムプラットフォームの設定の詳細については、Microsoft SQL Server 2008 R2 および Microsoft SQL Server 2012 製品ドキュメントを参照してください。

  - **ファイルサーバープラットフォーム**    Lync Server 2013 では、フロントエンドサーバーまたは Standard Edition サーバーをセットアップするときに、ファイル記憶域として指定したのと同じ場所に Lync Server アーカイブファイルが保存されます。 ファイル記憶域をアーカイブするために別の場所を指定することはできません。そのため、アーカイブファイルの保存には個別のシステムプラットフォームは必要ありません。 Microsoft Exchange 統合2013を使用している場合、アーカイブされた Lync コミュニケーションのファイルは exchange 2013 サーバーに格納され、これらの Exchange サーバーに所属するユーザーには保存されます。

</div>

<span> </span>

</div>

</div>

</div>

