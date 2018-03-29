---
title: 常設チャット データベースのスキーマ
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
description: これは、ビジネス サーバーの Skype で永続的なチャット データベースのスキーマについて説明します。
ms.openlocfilehash: 1c78ea53438484fb0ad573a815c10ad76f08edca
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="persistent-chat-database-schema"></a>常設チャット データベースのスキーマ
 
これは、ビジネス サーバーの Skype で永続的なチャット データベースのスキーマについて説明します。
  
ビジネス サーバー バック エンド サーバーの役割 (mgc データベースに対応する) **PersistentChatStore**と**PersistentChatComplianceStore**の Skype に対応するデータベースを参照して、永続的なチャットのデータベース (に対応する、mgccomp データベースの場合)。 使用すると、クエリを作成して、チャットの使用方法、アクティブな会議室、トップの投稿者などの周りの便利なレポートを作成するいくつかの洞察を得るには、このスキーマを発行するための目標です。
  
> [!IMPORTANT]
> マイクロソフトは、このスキーマを拡張する権利を持ちます。 マイクロソフトでは、公開されたこのスキーマの完全な下位互換性を維持するために保証をことはありません。 
  
これらのベスト プラクティスに従います。
  
- なし] を選択\*//列] ボックスの一覧を拡張できるためにサポートされています。
    
- ユーザーによって生成されたスキーマの変更はサポートされていません。
    
- 書き込み操作はサポートされていません。
    
- お客様のニーズを満たすレベルでクエリを実行できることを確認するデータベースのサイズの representatively をビルドするすべてのクエリをテストします。
    
## <a name="in-this-section"></a>このセクションの内容

- [永続的なチャット サーバーのテーブルの一覧](list-of-persistent-chat-server-tables.md)
    
- [ビジネス サーバーの Skype での永続的なチャット サーバー コンプライアンス テーブルの一覧](list-of-persistent-chat-server-compliance-tables.md)
    
- [永続的なチャット サーバー テーブルの詳細](persistent-chat-server-table-details.md)
    
- [永続的なチャット データベースのクエリのサンプル](sample-persistent-chat-database-queries.md)
    

