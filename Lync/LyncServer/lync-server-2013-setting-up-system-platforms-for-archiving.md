---
title: 'Lync Server 2013: アーカイブのためにシステムプラットフォームを設定する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up system platforms for Archiving
ms:assetid: 2df40fdf-0e32-46d4-9fb2-1ce1d7bfa328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204768(v=OCS.15)
ms:contentKeyID: 48183716
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d8d9499d68bcca3848e1e069b4962bb7526091d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848758"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-system-platforms-for-archiving-in-lync-server-2013"></a>Lync Server 2013 でアーカイブするためのシステムプラットフォームを設定する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-09_

アーカイブの展開を開始する前に、システム要件を満たすハードウェアに必要なオペレーティングシステムとその他の必須ソフトウェアをインストールする必要があります。

  - **Lync server 2013 platform**   lync server 2013 の展開には、アーカイブサーバーがありません。 代わりに、統合されたデータ収集エージェントは、アーカイブのためにデータを取得するためにフロントエンドサーバーと標準エディションのサーバー上で実行されるため、アーカイブをホストするために別個のシステムプラットフォームは必要ありません。

  - **データストレージプラットフォーム**   Lync Server 2013 では、次のいずれかを使用してデータを保存できます。
    
      - **Microsoft exchange**   との統合 exchange 2013 の展開を使用して Lync Server 2013 アーカイブデータを保存する必要がある場合、またはアーカイブデータを格納するために別のデータベースを設定するのではなく、exchange の展開を行う必要があります。Exchange 2013 を実行している。 Exchange 2013 のシステムプラットフォームのセットアップの詳細については、Exchange の製品に関するドキュメントを参照してください。
    
      - **Sql server**   Microsoft Exchange 統合の代わりに、または Microsoft Exchange 統合の使用に加えて、アーカイブデータの保存用に別の sql server データベースを使用する場合は、アーカイブの展開前にデータベースのシステムプラットフォームを設定する必要があります。 特定のシステムプラットフォーム要件は、アーカイブデータベース用に Microsoft SQL Server 2008 R2 と Microsoft SQL Server 2012 のどちらを使用するかによって異なります。 これらのデータベースのシステムプラットフォームのセットアップの詳細については、Microsoft SQL Server 2008 R2 および Microsoft SQL Server 2012 の製品に関するドキュメントを参照してください。

  - **ファイルサーバープラットフォーム**   lync server 2013 は、フロントエンドサーバーまたは Standard Edition サーバーのセットアップ時に、ファイルストレージとして指定した場所に lync server のアーカイブファイルを保存します。 アーカイブファイルの保存場所を個別に指定することはできません。そのため、ファイルストレージをアーカイブするために個別のシステムプラットフォームは必要ありません。 Microsoft Exchange 統合2013を使用している場合、アーカイブされた Lync 通信用のファイルは exchange 2013 サーバーに保存され、それらの Exchange サーバー上のユーザーが使用できます。

</div>

<span> </span>

</div>

</div>

</div>

