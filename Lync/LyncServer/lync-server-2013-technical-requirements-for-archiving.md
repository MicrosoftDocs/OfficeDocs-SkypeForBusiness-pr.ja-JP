---
title: 'Lync Server 2013: アーカイブの技術要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for Archiving
ms:assetid: 896d60e2-be4b-462d-8357-4cd307ab7304
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205059(v=OCS.15)
ms:contentKeyID: 48184732
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e4847815f10a48b954d3d83348d95cc137f4b39
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848559"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-archiving-in-lync-server-2013"></a>Lync Server 2013 でのアーカイブの技術要件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-09_

Lync Server 2013 の技術要件には、次のようなものがあります。

  - インフラストラクチャの要件。

  - アーカイブ用にインストールする必要がある必須ソフトウェア。

  - アーカイブのためのデータストレージ要件。

  - アーカイブの展開に必要なスケーリングと考慮事項。

  - アーカイブデータベースのパフォーマンス要件と考慮事項。

<div>


> [!NOTE]  
> スケーリングとパフォーマンスに関する情報は、この Lync Server 2013 リリースでは利用できません。



</div>

<div>

## <a name="infrastructure-requirements"></a>インフラストラクチャの要件

Lync Server 2013 アーカイブインフラストラクチャの要件は、Lync Server 2013 の展開の場合と同じです。 詳細については、計画ドキュメントで「 [Lync Server 2013 のインフラストラクチャ要件を決定](lync-server-2013-determining-your-infrastructure-requirements.md)する」を参照してください。

</div>

<div>

## <a name="archiving-prerequisites"></a>アーカイブの前提条件

Lync Server 2013 は、次の理由によりアーカイブの前提条件を合理化します。

  - アーカイブサーバーは、サーバーの役割ではなくなりました。 代わりに、統合されたデータ収集エージェントは、アーカイブ用のデータをキャプチャするために、プールのフロントエンドサーバーと標準エディションのサーバーで実行されるため、アーカイブ用に個別のシステムプラットフォームを設定する必要はありません。

  - アーカイブでは、会議コンテンツファイルの一時的なストレージとして Lync Server 2013 ファイルストレージが使用されるため、アーカイブ用に別のファイルストアを設定する必要はありません。

  - Lync Server 2013 では、メッセージキューは必要ありません。

</div>

<div>

## <a name="data-storage-requirements-for-archiving"></a>アーカイブのためのデータストレージ要件

さらに、アーカイブストレージ用のインフラストラクチャを設定する必要があります。 これには、次のいずれかまたは両方が含まれます。

  - **Microsoft Exchange ストレージ**。 Meeting content files, such as PowerPoint presentations, are archived as attachments. Microsoft Exchange の統合を使用して、Lync アーカイブデータが Exchange のコンプライアンスデータと共に保存されるようにするには、exchange 2013 を Exchange の展開に使用し、最大記憶域サイズが会議コンテンツファイルの記憶域をサポートしていることを確認する必要があります。 [Microsoft Exchange 統合] オプションを使用してアーカイブを展開する場合、Lync アーカイブデータは exchange 2013 サーバーをホームとしているユーザーに対してのみ Exchange 2013 のコンプライアンスデータと共に保存されます。 Microsoft Exchange 統合オプションを使用してアーカイブを展開して有効にする前に、Exchange 2013 を展開する必要があります。 Exchange 2013 ストレージを使用する場合は、Exchange 2013 サーバーをホームにしていない Lync ユーザーがいない限り、アーカイブ用に個別の SQL Server データベースを展開する必要はありません。

  - **アーカイブ用の SQL Server データベースストレージ**。 Exchange 2013 サーバーを使っていないユーザーをサポートする場合、または Microsoft Exchange の統合オプションを使用しない場合は、SQL Server データベースを使ってアーカイブストレージを展開する必要があります。 Lync Server 2013 では、次の64ビットバージョンの SQL Server がサポートされています。
    
      - Microsoft SQL Server 2008 R2 Enterprise
    
      - Microsoft SQL Server 2008 R2 Standard
    
      - Microsoft SQL Server 2012 Enterprise
    
      - Microsoft SQL Server 2012 標準
    
    <div>
    

    > [!NOTE]  
    > Microsoft SQL Server 2008 R2 Express および Microsoft SQL Server 2012 Express はアーカイブに対応していません。 32ビット版の SQL Server はサポートされていません。 SQL Server のその他の要件と制限については、計画ドキュメントまたはサポートサポートドキュメントの「 <A href="lync-server-2013-database-software-support.md">Lync Server 2013 でのデータベースソフトウェアのサポート</A>」を参照してください。

    
    </div>
    
    アーカイブを展開して有効にする前に、SQL Server プラットフォームをセットアップする必要があります。 トポロジの公開に使用するアカウントに適切な管理権限とアクセス許可がある場合、トポロジを公開するときにアーカイブ データベース (LcsLog) を作成できます。 また、インストール手順の一部として、後でデータベースを作成することもできます。 SQL Server の詳細については、SQL Server の[http://go.microsoft.com/fwlink/p/?linkID=129045](http://go.microsoft.com/fwlink/p/?linkid=129045)TechCenter を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

