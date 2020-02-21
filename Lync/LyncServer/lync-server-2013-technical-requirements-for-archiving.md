---
title: 'Lync Server 2013: アーカイブの技術要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Archiving
ms:assetid: 896d60e2-be4b-462d-8357-4cd307ab7304
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205059(v=OCS.15)
ms:contentKeyID: 48184732
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d2ba284f64b311ad48191cf251d1b3d903f595a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194960"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-archiving-in-lync-server-2013"></a>Lync Server 2013 でのアーカイブの技術要件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-09_

Lync Server 2013 の技術要件は次のとおりです。

  - インフラストラクチャの要件

  - アーカイブ用にインストールする必要があるソフトウェア

  - アーカイブ用のデータ ストレージの要件

  - アーカイブ展開における拡張の要件および考慮事項

  - アーカイブ データベースのパフォーマンスの要件および考慮事項

<div>


> [!NOTE]  
> この Lync Server 2013 リリースでは、スケーリングとパフォーマンス情報は利用できません。



</div>

<div>

## <a name="infrastructure-requirements"></a>インフラストラクチャの要件

Lync Server 2013 のアーカイブインフラストラクチャの要件は、Lync Server 2013 の展開の場合と同じです。 詳細については、「計画」のドキュメントの「 [Lync Server 2013 のインフラストラクチャ要件の決定](lync-server-2013-determining-your-infrastructure-requirements.md)」を参照してください。

</div>

<div>

## <a name="archiving-prerequisites"></a>アーカイブの前提条件

Lync Server 2013 は、以下の理由からアーカイブの前提条件を合理化します。

  - サーバーの役割からアーカイブ サーバーが除外されました。代わりに、統合データ収集エージェントが、プール内のフロントエンド サーバーと Standard Edition サーバーで実行され、アーカイブ用のデータがキャプチャされます。したがって、アーカイブ用に別のシステム プラットフォームを設定する必要はありません。

  - アーカイブは、Lync Server 2013 のファイルストレージを使用して会議コンテンツファイルを一時的に保存するので、アーカイブ用に別のファイルストアを設定することはありません。

  - Lync Server 2013 では、メッセージキューは必要ありません。

</div>

<div>

## <a name="data-storage-requirements-for-archiving"></a>アーカイブ用のデータ ストレージの要件

また、アーカイブ ストレージ用のインフラストラクチャを設定する必要があります。これには、次のどちらか、または両方があります。

  - **Microsoft Exchange ストレージ** PowerPoint プレゼンテーションなどの会議コンテンツ ファイルは、添付ファイルとしてアーカイブされます。 Microsoft Exchange 統合を使用して、Lync アーカイブデータが Exchange コンプライアンスデータと共に保存されるようにするには、exchange の展開に Exchange 2013 を使用し、会議コンテンツファイルのストレージが最大の記憶域サイズでサポートされるようにする必要があります。 Microsoft Exchange 統合オプションを使用してアーカイブを展開する場合、Lync アーカイブデータは exchange 2013 サーバーに所属しているユーザーの Exchange 2013 コンプライアンスデータのみに格納されます。 Microsoft Exchange 統合オプションを使用してアーカイブを展開および有効化する前に、Exchange 2013 を展開する必要があります。 Exchange 2013 ストレージを使用することを選択した場合は、Exchange 2013 サーバーに所属していない Lync ユーザーがいない限り、アーカイブ用に個別の SQL Server データベースを展開する必要はありません。

  - **アーカイブ用の SQL Server データベースストレージ**。 Exchange 2013 サーバーに所属していないユーザーをサポートする場合、または Microsoft Exchange 統合オプションを使用しない場合は、SQL Server データベースを使用してアーカイブストレージを展開する必要があります。 Lync Server 2013 では、次の64ビットバージョンの SQL Server がサポートされています。
    
      - Microsoft SQL Server 2008 R2 Enterprise
    
      - Microsoft SQL Server 2008 R2 Standard
    
      - Microsoft SQL Server 2012 Enterprise
    
      - Microsoft SQL Server 2012 Standard
    
    <div>
    

    > [!NOTE]  
    > Microsoft SQL Server 2008 R2 Express および Microsoft SQL Server 2012 Express はアーカイブに対してサポートされていません。 32ビット版の SQL Server はサポートされていません。 SQL Server のその他の要件および制限については、「計画」のドキュメントまたは「サポート」のドキュメントの「 <A href="lync-server-2013-database-software-support.md">Lync Server 2013 のデータベースソフトウェアサポート</A>」を参照してください。

    
    </div>
    
    アーカイブを展開して有効にする前に、SQL Server プラットフォームをセットアップする必要があります。 トポロジの公開に使用するアカウントに適切な管理権限とアクセス許可がある場合、トポロジを公開するときにアーカイブ データベース (LcsLog) を作成できます。 インストール手順の一部を含め、データベースを後で作成することもできます。 SQL Server の詳細については、SQL Server TechCenter [https://go.microsoft.com/fwlink/p/?linkID=129045](https://go.microsoft.com/fwlink/p/?linkid=129045)の「」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

