---
title: 'Lync Server 2013: アーカイブ用に記憶域を設定する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up storage for Archiving
ms:assetid: f751245c-743e-454f-8325-968ae5e3de71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205392(v=OCS.15)
ms:contentKeyID: 48185858
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6728c02e9aa73faceaa8b3e681a5cf9cc4c700cd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848733"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-storage-for-archiving-in-lync-server-2013"></a>Lync Server 2013 でアーカイブ用に記憶域を設定する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-12-17_

Lync Server 2013 のアーカイブストレージには、次のものが含まれます。

  - ****   IM コンテンツを保存するには、データストレージデータストレージが必要です。

  - ****   会議 (会議) コンテンツデータストレージとファイルストレージを保存するには、ファイルストレージファイルストレージが必要です。

<div>

## <a name="setting-up-data-storage"></a>データストレージのセットアップ

Lync Server 2013 でアーカイブ用にデータストレージを設定するための要件は、アーカイブデータの保存方法によって異なります。

  - Lync Server 2013 アーカイブを Exchange の展開と統合して、Exchange ストレージを使ってアーカイブデータを保存します。

  - アーカイブデータを格納するために、個別の SQL Server データベースサーバーをセットアップします。

<div>

## <a name="setting-up-exchange-storage-for-archiving-data"></a>データをアーカイブするための Exchange ストレージのセットアップ

アーカイブデータの保存用に Exchange をセットアップするには、exchange の展開で Exchange 2013 が実行されている必要があります。 さらに、ユーザーのメールボックスは Exchange 2013 サーバー上にある必要があり、そのメールボックスはインプレースホールドに配置されている必要があります。 Exchange 2013 の構成の詳細については、Exchange の製品に関するドキュメントを参照してください。

</div>

<div>

## <a name="setting-up-sql-server-database-servers-for-storage-of-archiving-data"></a>アーカイブデータを保存するための SQL Server データベースサーバーのセットアップ

展開を Exchange と統合しない限り、Lync Server 2013 でアーカイブするには、アーカイブされたデータを格納するための SQL Server データベースソフトウェアが必要です。

SQL Server アーカイブデータベースの場合は、アーカイブデータベースをホストするコンピューターに SQL Server をインストールする必要があります。 フロントエンドプールのバックエンドデータベースに使用するのと同じ SQL インスタンスを使用できます。 最高のパフォーマンスを得るには、一元管理ストアとは別のコンピューターにアーカイブデータベースを展開する必要があります。 Lync Server の2013コンポーネントの詳細について詳しくは、「[サポートされている2013サーバー](lync-server-2013-supported-server-collocation.md)の検索 (サポート対象ドキュメント)」をご覧ください。

各データベースサーバーでは、サポートされているバージョンの SQL Server が実行されている必要があります。 サポートされているバージョンの詳細については、計画ドキュメントの「 [Lync Server 2013 でのアーカイブの技術要件](lync-server-2013-technical-requirements-for-archiving.md)」を参照してください。

アーカイブを展開して有効にする前に、SQL Server プラットフォームをセットアップする必要があります。 トポロジの公開に使用するアカウントに適切な管理権限とアクセス許可がある場合、トポロジを公開するときにアーカイブ データベース (LcsLog) を作成できます。 また、インストール手順の一部として、後でデータベースを作成することもできます。 SQL Server の詳細については、SQL Server の[http://go.microsoft.com/fwlink/p/?linkID=129045](http://go.microsoft.com/fwlink/p/?linkid=129045)TechCenter を参照してください。

<div>


> [!NOTE]  
> 既定のアーカイブ SQL Server メンテナンスジョブが、アーカイブデータベースを保持している SQL インスタンスで実行されていることを確認します。これにより、既定のアーカイブ SQL Server メンテナンスジョブは、SQL Server エージェントサービスの制御。



</div>

</div>

</div>

<div>

## <a name="setting-up-file-storage"></a>ファイルストレージを設定する

アーカイブでは、フロントエンドプールまたは Standard Edition サーバーのセットアップ時に指定した Lync Server 2013 ファイル共有が使用されます。 アーカイブに使用するファイル共有を変更することはできません。 サポートされているファイルストレージシステムの詳細については、サポートドキュメントの「 [Lync Server 2013 でのファイルストレージのサポート](lync-server-2013-file-storage-support.md)」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

