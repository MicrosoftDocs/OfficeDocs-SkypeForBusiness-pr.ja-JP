---
title: CQD のユーザー サービス
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd5c828-42dd-4f48-bf87-29993193cb3a
description: '概要: 呼び出し品質ダッシュボードのリポジトリ API の一部である User Service について説明します。 品質ダッシュボードの呼び出しは、ユーザーのSkype for Business Server。'
ms.openlocfilehash: 412f7b17e6190a35e79998d47a0d5cfa8459f6934d19761f5d0b5d65e5e91ba2
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54324196"
---
# <a name="user-service-for-cqd"></a>CQD のユーザー サービス
 
**概要:** 呼び出し品質ダッシュボードのリポジトリ API の一部である User Service について説明します。 品質ダッシュボードの呼び出しは、ユーザーのSkype for Business Server。
  
User Service は、呼び出し品質ダッシュボードのリポジトリ API の一部です。
  
## <a name="user-service"></a>ユーザー サービス

リポジトリ API は、ユーザー プロビジョニング (新しいユーザー アカウントの作成) が自動的で暗黙的である簡略化されたユーザー管理モデルを提供します。 ユーザーが初めてリポジトリ API に対して要求を行った場合、リポジトリは新しい User レコードを作成します。 
  
通話品質ダッシュボードでは、新しいユーザーのユーザー専用アイテムも自動的に作成されます。 新しいユーザー専用アイテムは、システム ユーザーのアイテムの完全な複製です。 これにより、ユーザーはレポートとクエリの独自のコピーから開始し、すぐにカスタマイズを開始できます。 
  
> [!NOTE]
> 通話品質ダッシュボードを使用すると、ユーザーは専用のアイテムをいつでもリセットできます。 
  
 **特別なユーザー ID**
  
リポジトリ API には、特定のユーザーを指定する整数値を期待する REST API URI が含まれています。 例:  `https://<portal>/QoERepositoryService/repository/user/{userId}` . ここでは、{userId} を 0、1 などの整数値に置き換える必要があります。
  
さらに、リポジトリ API は URI の {userId} で 2 つの特別なユーザー ID を受け入れる。
  
-  *default*  - 現在 API を操作しているユーザーを表します。 これにより、アプリケーションは実際のユーザー ID 値を追跡することなく、現在のユーザーのコンテンツにアクセスできます。 例: `https://<portal>/QoERepositoryService/repository/user/default`。
    
-  *system*  - システム ユーザーを表します。 これにより、アプリケーションは、実際のユーザー ID 値を知らなくても、システム ユーザーのコンテンツにアクセスできます。 例: `https://<portal>/QoERepositoryService/repository/user/system`。
    
特に指定しない限り、URI の {userId} で特別なユーザー ID を使用できます。 
  
REST 操作は、次の表に含まれています。
  
|**操作名**|**説明**|
|:-----|:-----|
|[ユーザーの取得](get-users.md) <br/> |リポジトリ内のユーザーの一覧を返します。  <br/> |
|[ユーザーの取得](get-user.md) <br/> |ユーザー レコードを返します。  <br/> |
   

