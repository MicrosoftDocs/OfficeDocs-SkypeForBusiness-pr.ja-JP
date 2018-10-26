---
title: 'Lync Server 2013: アーカイブの技術要件'
TOCTitle: アーカイブの技術要件
ms:assetid: 896d60e2-be4b-462d-8357-4cd307ab7304
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205059(v=OCS.15)
ms:contentKeyID: 48272805
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 のアーカイブの技術要件

 

_**トピックの最終更新日:** 2016-12-08_

Lync Server 2013 の技術上の要件を次に示します。

  - インフラストラクチャの要件

  - アーカイブ用にインストールする必要があるソフトウェア

  - アーカイブ用のデータ ストレージの要件

  - アーカイブ展開における拡張の要件および考慮事項

  - アーカイブ データベースのパフォーマンスの要件および考慮事項

> [!NOTE]
> この Lync Server 2013 リリースでは、拡張およびパフォーマンス情報は使用できません。


## インフラストラクチャの要件

Lync Server 2013 アーカイブ インフラストラクチャの要件は、 Lync Server 2013 の展開と同じです。詳細については、「計画」のドキュメントの「[Lync Server 2013 に関するインフラストラクチャ要件の決定](lync-server-2013-determining-your-infrastructure-requirements.md)」を参照してください。

## アーカイブの前提条件

Lync Server 2013 では、アーカイブの前提条件が簡素化されています。理由は次のとおりです。

  - サーバーの役割からアーカイブ サーバーが除外されました。代わりに、統合データ収集エージェントが、プール内のフロントエンド サーバーと Standard Edition サーバーで実行され、アーカイブ用のデータがキャプチャされます。したがって、アーカイブ用に別のシステム プラットフォームを設定する必要はありません。

  - アーカイブに会議コンテンツの一時記憶域として Lync Server 2013 ファイル ストレージを使用するため、アーカイブ用に別のファイル ストアを設定する必要はありません。

  - Lync Server 2013 では、メッセージ キューは不要です。

## アーカイブ用のデータ ストレージの要件

また、アーカイブ ストレージ用のインフラストラクチャを設定する必要があります。これには、次のどちらか、または両方があります。

  - **Microsoft Exchange ストレージ**。PowerPoint プレゼンテーションなどの会議コンテンツ ファイルは、添付ファイルとしてアーカイブされます。 Microsoft Exchange 統合を使用して Lync アーカイブ データを Exchange コンプライアンス データと共に格納する場合は、 Exchange 展開に Exchange 2013 を使用し、最大ストレージ サイズで会議コンテンツ ファイルのストレージがサポートされていることを確認する必要があります。 Microsoft Exchange 統合オプションを使用してアーカイブを展開する場合は、 Lync アーカイブ データを、 Exchange 2013 サーバーに所属するユーザーの Exchange 2013 コンプライアンス データとのみ格納します。 Exchange 2013 は、 Microsoft Exchange 統合オプションを使用してアーカイブを展開および有効にする前に展開する必要があります。 Exchange 2013 ストレージの使用を選択する場合は、 Exchange 2013 サーバーに所属しない Lync ユーザーが存在しない限り、アーカイブ用に別の SQL Server データベースを展開する必要はありません。

  - **アーカイブ用の SQL Server データベース ストレージ**。Exchange 2013 サーバーに所属しないユーザーをサポートする場合、または Microsoft Exchange 統合オプションを使用しない場合は、SQL Server データベースを使用したアーカイブ ストレージを展開する必要があります。Lync Server 2013 は、次の 64 ビット版 SQL Server をサポートします。
    
      - Microsoft SQL Server 2008 R2 Enterprise
    
      - Microsoft SQL Server 2008 R2 Standard
    
      - Microsoft SQL Server 2012 Enterprise
    
      - Microsoft SQL Server 2012 Standard
    
    > [!NOTE]
    > Microsoft SQL Server 2008 R2 Express と Microsoft SQL Server 2012 Express をアーカイブに使用することはできません。32 ビット版 SQL Server はサポートされません。SQL Server の要件と制限の関連情報については、「計画」のドキュメントまたは「サポート」のドキュメントの「<a href="lync-server-2013-database-software-support.md">Lync Server 2013 でのデータベース ソフトウェアのサポート</a>」を参照してください。
    
    アーカイブを展開し、有効化する前に、 SQL Server プラットフォームを設定する必要があります。トポロジの公開に使用するアカウントに適切な管理権限とアクセス許可がある場合、トポロジを公開するときにアーカイブ データベース (LcsLog) を作成できます。インストール手順の一部を含め、データベースを後で作成することもできます。 SQL Server の詳細については、SQL Server TechCenter ( [http://go.microsoft.com/fwlink/?linkid=129045\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=129045%26clcid=0x411)) を参照してください。

