---
title: Skype for Business Server 2015 のアーカイブに関するハードウェアおよびソフトウェア要件
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 896d60e2-be4b-462d-8357-4cd307ab7304
description: '概要: ビジネス サーバー 2015 の Skype でアーカイブ用のハードウェアおよびソフトウェアの要件の詳細については、このトピックを読みます。'
ms.openlocfilehash: d8d8039e95a3b578551d0db6ff219fe8f3c1e5c5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="hardware-and-software-requirements-for-archiving-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 のアーカイブに関するハードウェアおよびソフトウェア要件
 
**の概要:**ビジネス サーバー 2015 の Skype でアーカイブ用のハードウェアおよびソフトウェアの要件の詳細については、このトピックを参照してください。
  
ビジネス サーバー 2015 のアーカイブのための Skype が、一部のフロント エンドの役割のため、別のサーバーをインストールする必要はありません。 次の要件を考慮する必要があります、ただし。
  
- インフラストラクチャの要件
    
- 必要なソフトウェアの要件
    
- データ記憶域の要件
    
## <a name="infrastructure-requirements"></a>インフラストラクチャの要件

ビジネス ・ サーバのアーカイブのインフラストラクチャ要件の Skype は、Skype のビジネス サーバーの展開の場合と同じです。 詳細については、[ビジネス環境に、Skype の要件](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md)を参照してください。 
  
## <a name="prerequisite-software-requirements"></a>必要なソフトウェアの要件

Skype ビジネス サーバーのためのアーカイブの前提条件は次の理由により、Lync Server の以前のバージョンよりも簡単です。 
  
- アーカイブ不要になったサーバーの役割であるために、アーカイブのための別のサーバーをインストールする必要はありません。 代わりに、すべての Enterprise Edition フロントエンド プールとすべての Standard Edition サーバーで、統合データ収集エージェントが自動的にインストールされ、有効になります。 トポロジ ビルダーを使用して、アーカイブ トポロジを有効にして発行する必要があります。
    
- アーカイブ アーカイブのための別のファイル ストアを設定しないために、コンテンツ ファイルを満たすための一時的な記憶域のビジネス サーバー ファイルの記憶域、Skype を使用します。
    
- ビジネス サーバーの Skype で Microsoft メッセージ キューは必要ありません。
    
## <a name="data-storage-requirements"></a>データ記憶域の要件

アーカイブ ストレージ用のインフラストラクチャを設定する必要があります。これを行うには、次のどちらか、または両方を選択します。
  
- **Microsoft Exchange の記憶域**です。 PowerPoint プレゼンテーションなどの会議コンテンツ ファイルは、添付ファイルとしてアーカイブされます。 Exchange 対応のデータのアーカイブ データをビジネス用の Skype を格納する場合は、Exchange を使用して、Exchange を展開するため、記憶域の最大サイズがミーティングのコンテンツ ファイルのストレージをサポートしていることを確認してください。 展開して、Microsoft Exchange の統合オプションを使用してアーカイブを有効にする前に Exchange を展開する必要があります。 
    
    Exchange の記憶域を使用する場合は、する必要はありません、アーカイブの別の SQL Server データベースを展開する Exchange サーバー上にはないビジネス ユーザーに Skype がない限り。 Microsoft Exchange の統合オプションを使用してアーカイブを展開する場合、Exchange サーバーが置かれているユーザー専用の Exchange 対応のデータと Skype ビジネス アーカイブ ・ データが格納されます。 
    
- **Skype ビジネス サーバー ・ アーカイブ ・ ストレージ**です。 Exchange サーバーではないユーザーをサポートする Microsoft Exchange の統合オプションを使用しない場合は、SQL Server データベースを使用して、アーカイブ ・ ストレージに配置する必要があります。 Skype ビジネス サーバー用には、次の 64 ビット バージョンの SQL Server がサポートされています。
    
  - Microsoft SQL Server 2008 R2 エンタープライズ
    
  - Microsoft SQL Server 2008 R2 の標準
    
  - Microsoft SQL Server 2012 のエンタープライズ
    
  - Microsoft SQL Server 2012 の標準
    
  - 2014 企業の Microsoft SQL Server
    
  - 2014 標準の Microsoft SQL Server
    
    > [!NOTE]
    > アーカイブには、Microsoft SQL Server の高速バージョンはサポートされていません。 SQL Server の 32 ビット バージョンはサポートされていません。 追加の SQL Server の要件と制限は、[ビジネス環境に、Skype の要件](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md)を参照してください。 
  
    展開とアーカイブを有効にする前に SQL Server プラットフォームを設定する必要があります。 トポロジの公開に使用するアカウントに適切な管理権限とアクセス許可がある場合、トポロジを公開するときにアーカイブ データベース (LcsLog) を作成できます。 インストール手順の一部を含め、データベースを後で作成することもできます。 詳細については、SQL Server は、 [SQL Server TechCenter](https://go.microsoft.com/fwlink/p/?linkID=129045)を参照してください。
    
    アーカイブに関する負荷の増加は、重大な問題になる可能性があります。 そのため、ディスク領域は十分にフロント エンド サーバーがアーカイブを有効にすることを行う必要があります。
    

