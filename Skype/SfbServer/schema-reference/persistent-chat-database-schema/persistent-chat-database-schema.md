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
description: このドキュメントでは、常設チャット データベースのスキーマをドキュメント化Skype for Business Server。
ms.openlocfilehash: bc314413d2bb7a3d5916396f1e8f281d2217e9058d087dcec8bcc486ee7f172f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54280930"
---
# <a name="persistent-chat-database-schema"></a>常設チャット データベース スキーマ
 
このドキュメントでは、常設チャット データベースのスキーマをドキュメント化Skype for Business Server。
  
常設チャット データベースは、Skype for Business Server Back End Server の役割 **PersistentChatStore** (mgc データベースに対応) と **PersistentChatComplianceStore** (mgccomp データベースに対応) に対応するデータベースを参照します。 このスキーマを公開する目的は、クエリを作成し、チャットの使用状況、アクティブなルーム、上位のポスターなどに関する有用なレポートの作成について理解できるようにすることです。
  
> [!IMPORTANT]
> Microsoft はこのスキーマを進化させる権利があります。Microsoft では、公開されたこのスキーマとの完全な下位互換性を維持することは一切保証していません。 
  
次のベスト プラクティスに従ってください。
  
- 列一 \* 覧が拡大する可能性があるため、SELECT // はサポートされていません。
    
- ユーザーが生成したスキーマの変更はサポートされません。
    
- 書き込み操作はサポートされません。
    
- 作成したクエリを標準的なサイズのデータベースでテストして、ニーズを満たすレベルでクエリを実行できることを確認してください。
    
## <a name="in-this-section"></a>このセクションの内容

- [常設チャット サーバーのテーブルのリスト](list-of-persistent-chat-server-tables.md)
    
- [[常設チャット サーバーのコンプライアンス テーブルの一覧] Skype for Business Server](list-of-persistent-chat-server-compliance-tables.md)
    
- [常設チャット サーバー テーブルの詳細](persistent-chat-server-table-details.md)
    
- [常設チャット データベースのクエリのサンプル](sample-persistent-chat-database-queries.md)
    

