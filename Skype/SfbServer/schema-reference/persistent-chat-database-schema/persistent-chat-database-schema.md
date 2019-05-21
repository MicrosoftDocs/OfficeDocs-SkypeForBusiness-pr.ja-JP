---
title: 常設チャット データベースのスキーマ
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
description: これは、Skype for Business Server の常設チャットデータベースのスキーマを文書化します。
ms.openlocfilehash: 9a3e09a03f764f8866865e08259cbaac12a1c554
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295616"
---
# <a name="persistent-chat-database-schema"></a>常設チャット データベースのスキーマ
 
これは、Skype for Business Server の常設チャットデータベースのスキーマを文書化します。
  
常設チャットデータベースは、Skype for Business Server のバックエンドサーバーの役割**PersistentChatStore** (行うデータベースに対応) と**PersistentChatComplianceStore**に対応しているデータベースを指します。・カンプデータベース)。 このスキーマを公開することは、お客様がクエリを作成して、チャットの利用状況、アクティブな会議室、トップ投稿などに関する有用なレポートを作成できるようにすることを目的としています。
  
> [!IMPORTANT]
> このスキーマを進化させる権利を留保します。 Microsoft は、この公開されたスキーマとの完全な下位互換性を維持する保証を行っていません。 
  
以下のベストプラクティスに従ってください。
  
- 列リスト\*のサイズが大きくなる可能性があるため、SELECT//はサポートされません。
    
- ユーザーが生成したスキーマの変更はサポートされません。
    
- 書き込み操作はサポートされていません。
    
- Representatively サイズのデータベースで作成したクエリをテストして、ニーズに合わせてクエリが確実に実行されることを確認します。
    
## <a name="in-this-section"></a>このセクションの内容

- [常設チャット サーバーのテーブルのリスト](list-of-persistent-chat-server-tables.md)
    
- [Skype for Business Server の常設チャットサーバーのコンプライアンステーブルの一覧](list-of-persistent-chat-server-compliance-tables.md)
    
- [常設チャット サーバー テーブルの詳細](persistent-chat-server-table-details.md)
    
- [常設チャット データベースのクエリのサンプル](sample-persistent-chat-database-queries.md)
    

