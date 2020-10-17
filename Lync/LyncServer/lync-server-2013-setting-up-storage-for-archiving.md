---
title: 'Lync Server 2013: アーカイブ用のストレージのセットアップ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up storage for Archiving
ms:assetid: f751245c-743e-454f-8325-968ae5e3de71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205392(v=OCS.15)
ms:contentKeyID: 48185858
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ab7e22d4ff0e34d903fa0306d971705c5455b2f6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521784"
---
# <a name="setting-up-storage-for-archiving-in-lync-server-2013"></a>Lync Server 2013 でのアーカイブ用の記憶域のセットアップ

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-12-17_

Lync Server 2013 のアーカイブ記憶域には次のものが含まれます。

  - **データストレージ**    データストレージは IM コンテンツを格納するために必要です。

  - **ファイル記憶域**    会議 (会議) コンテンツのデータストレージおよびファイルストレージを保存するには、ファイルストレージが必要です。

<div>

## <a name="setting-up-data-storage"></a>データ ストレージのセットアップ

Lync Server 2013 でアーカイブ用のデータストレージをセットアップするための要件は、アーカイブデータの保存方法によって異なります。

  - Exchange ストレージを使用してアーカイブデータを保存するために、Lync Server 2013 アーカイブを Exchange 展開と統合します。

  - アーカイブデータを格納する個別の SQL Server データベースサーバーをセットアップします。

<div>

## <a name="setting-up-exchange-storage-for-archiving-data"></a>アーカイブ データ用の Exchange ストレージのセットアップ

アーカイブデータのストレージ用に Exchange をセットアップするには、exchange の展開で Exchange 2013 を実行している必要があります。 さらに、ユーザーメールボックスは Exchange 2013 サーバー上に配置されている必要があり、メールボックスが In-Place ホールドに設定されている必要があります。 Exchange 2013 の構成の詳細については、「Exchange 製品のドキュメント」を参照してください。

</div>

<div>

## <a name="setting-up-sql-server-database-servers-for-storage-of-archiving-data"></a>アーカイブ データのストレージ用 SQL Server データベースのセットアップ

Lync Server 2013 のアーカイブには、展開と Exchange を統合しない限り、アーカイブされたデータを格納するための SQL Server データベースソフトウェアが必要です。

SQL Server アーカイブデータベースの場合は、アーカイブデータベースをホストするコンピューターに SQL Server をインストールする必要があります。 フロントエンド プールのバックエンド データベースに使用するものと同じ SQL インスタンスを使用できます。 パフォーマンスを最大限に高めるために、中央管理ストアとは別のコンピューター上にアーカイブ データベースを展開する必要があります。 Lync server 2013 コンポーネントの併置の詳細については、「サポート」のドキュメントの「supported [server 併置する in lync server 2013](lync-server-2013-supported-server-collocation.md) 」を参照してください。

各データベースサーバーは、サポートされているバージョンの SQL Server を実行している必要があります。 サポートされているバージョンの詳細については、「計画」のドキュメントの「 [Lync Server 2013 でのアーカイブの技術要件](lync-server-2013-technical-requirements-for-archiving.md) 」を参照してください。

アーカイブを展開して有効にする前に、SQL Server プラットフォームをセットアップする必要があります。 トポロジの公開に使用するアカウントに適切な管理権限とアクセス許可がある場合、トポロジを公開するときにアーカイブ データベース (LcsLog) を作成できます。 インストール手順の一部を含め、データベースを後で作成することもできます。 SQL Server の詳細については、SQL Server TechCenter の「」を参照してください [https://go.microsoft.com/fwlink/p/?linkID=129045](https://go.microsoft.com/fwlink/p/?linkid=129045) 。

<div>


> [!NOTE]  
> Sql server エージェントサービスのスタートアップの種類が自動で、アーカイブデータベースを保持している SQL インスタンスに対して SQL Server エージェントサービスが実行されていることを確認します。これにより、sql server エージェントサービスの制御下で、既定のアーカイブ SQL Server メンテナンスジョブをスケジュールに従って実行できるようになります。



</div>

</div>

</div>

<div>

## <a name="setting-up-file-storage"></a>ファイル ストレージのセットアップ

アーカイブでは、フロントエンドプールまたは Standard Edition サーバーをセットアップするときに指定した Lync Server 2013 ファイル共有を使用します。 アーカイブに使用するファイル共有を変更することはできません。 サポートされているファイルストレージシステムの詳細については、「サポート」のドキュメントの「 [Lync Server 2013 のファイルストレージサポート](lync-server-2013-file-storage-support.md) 」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

