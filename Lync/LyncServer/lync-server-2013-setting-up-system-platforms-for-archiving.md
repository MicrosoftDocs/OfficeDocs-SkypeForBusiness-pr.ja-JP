---
title: 'Lync Server 2013: アーカイブ用のシステムプラットフォームのセットアップ'
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
ms.openlocfilehash: 88e1a8aea999fdf134b0152a9d37b2d36fc81ee8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008669"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-system-platforms-for-archiving-in-lync-server-2013"></a>Lync Server 2013 でのアーカイブ用のシステムプラットフォームのセットアップ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-09_

アーカイブの展開を開始する前に、システム要件を満たすハードウェアに、必要なオペレーティング システムとその他の必須ソフトウェアをインストールする必要があります。

  - **Lync server 2013 プラットフォーム**   lync server 2013 展開には、アーカイブサーバーがありません。 代わりに、統合データ収集エージェントはフロントエンドサーバーと Standard Edition サーバー上で実行されてアーカイブ用のデータをキャプチャするため、アーカイブをホストするために個別のシステムプラットフォームは必要ありません。

  - **データストレージプラットフォーム**   Lync Server 2013 では、次のいずれかを使用してデータを保存できます。
    
      - **Microsoft exchange 統合**   exchange 2013 展開を使用して Lync Server 2013 アーカイブデータを保存する場合、またはアーカイブデータの格納用に別のデータベースをセットアップするのではなく、exchange 2013 を実行している必要があります。 Exchange 2013 用のシステムプラットフォームのセットアップの詳細については、「Exchange 製品のドキュメント」を参照してください。
    
      - **Sql server**   Microsoft Exchange 統合を使用するのではなく、アーカイブデータの格納に別の sql server データベースを使用する場合は、アーカイブを展開する前に、データベースのシステムプラットフォームを設定する必要があります。 特定のシステムプラットフォームの要件は、アーカイブデータベースに Microsoft SQL Server 2008 R2 と Microsoft SQL Server 2012 のどちらを使用するかによって異なります。 これらのデータベースのシステムプラットフォームの設定の詳細については、Microsoft SQL Server 2008 R2 および Microsoft SQL Server 2012 製品ドキュメントを参照してください。

  - **ファイルサーバープラットフォーム**   lync server 2013 は、フロントエンドサーバーまたは Standard Edition サーバーをセットアップするときに、ファイル記憶域に指定したのと同じ場所に lync server アーカイブファイルを格納します。 ファイル記憶域をアーカイブするために別の場所を指定することはできません。そのため、アーカイブファイルの保存には個別のシステムプラットフォームは必要ありません。 Microsoft Exchange 統合2013を使用している場合、アーカイブされた Lync コミュニケーションのファイルは exchange 2013 サーバーに格納され、これらの Exchange サーバーに所属するユーザーには保存されます。

</div>

<span> </span>

</div>

</div>

</div>

