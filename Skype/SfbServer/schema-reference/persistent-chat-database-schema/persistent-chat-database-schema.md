---
title: 常設チャット データベース スキーマ
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
description: ここでは、Skype for Business Server の常設チャット データベースのスキーマについて説明します。
ms.openlocfilehash: ba50f4391ce35d8a938318e96e1483bbfe0e3dfa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809877"
---
# <a name="persistent-chat-database-schema"></a>常設チャット データベース スキーマ
 
ここでは、Skype for Business Server の常設チャット データベースのスキーマについて説明します。
  
常設チャット データベースは、Skype for Business Server のバック エンド サーバーの役割 **PersistentChatStore** (mgc データベースに対応) および **PersistentChatComplianceStore** (mgccomp データベースに対応) に対応するデータベースを参照します。 このスキーマを公開する目的は、クエリを作成し、チャットの使用状況、アクティブなルーム、上位のポスターなどに関する有用なレポートの作成について理解できるようにすることです。
  
> [!IMPORTANT]
> Microsoft はこのスキーマを進化させる権利があります。Microsoft では、公開されたこのスキーマとの完全な下位互換性を維持することは一切保証していません。 
  
次のベスト プラクティスに従ってください。
  
- 列の \* 一覧は拡大される可能性があります。SELECT // はサポートされていません。
    
- ユーザーが生成したスキーマの変更はサポートされません。
    
- 書き込み操作はサポートされません。
    
- 作成したクエリを標準的なサイズのデータベースでテストして、ニーズを満たすレベルでクエリを実行できることを確認してください。
    
## <a name="in-this-section"></a>このセクションの内容

- [常設チャット サーバーのテーブルのリスト](list-of-persistent-chat-server-tables.md)
    
- [Skype for Business Server の常設チャット サーバー コンプライアンス テーブルの一覧](list-of-persistent-chat-server-compliance-tables.md)
    
- [常設チャット サーバー テーブルの詳細](persistent-chat-server-table-details.md)
    
- [常設チャット データベースのクエリのサンプル](sample-persistent-chat-database-queries.md)
    

