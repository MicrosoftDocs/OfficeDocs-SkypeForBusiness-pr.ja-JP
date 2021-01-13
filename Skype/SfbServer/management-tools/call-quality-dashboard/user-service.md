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
description: '概要: 通話品質ダッシュボードのリポジトリ API の一部であるユーザー サービスについて説明します。 通話品質ダッシュボードは、Skype for Business Server 用のツールです。'
ms.openlocfilehash: d9f4b771a1bf5efeece4f8fb87195d8567f0426e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803077"
---
# <a name="user-service-for-cqd"></a>CQD のユーザー サービス
 
**概要:** 通話品質ダッシュボードのリポジトリ API の一部であるユーザー サービスについて説明します。 通話品質ダッシュボードは、Skype for Business Server 用のツールです。
  
ユーザー サービスは、通話品質ダッシュボードのリポジトリ API の一部です。
  
## <a name="user-service"></a>ユーザー サービス

リポジトリ API は、ユーザー プロビジョニング (新しいユーザー アカウントの作成) が自動的で暗黙的である、簡略化されたユーザー管理モデルを提供します。 ユーザーがリポジトリ API に対して初めて要求を行う場合、リポジトリは新しいユーザー レコードを作成します。 
  
通話品質ダッシュボードでは、新しいユーザー専用のアイテムも自動的に作成されます。 新しいユーザー専用アイテムは、システム ユーザーのアイテムの完全な複製です。 これにより、ユーザーはレポートとクエリの独自のコピーを使用して開始し、すぐにカスタマイズを開始できます。 
  
> [!NOTE]
> 通話品質ダッシュボードを使用すると、ユーザーは専用アイテムをいつでもリセットできます。 
  
 **特別なユーザー ID**
  
リポジトリ API には、特定のユーザーを指定する整数値を期待する REST API URI が含まれています。 例: `https://<portal>/QoERepositoryService/repository/user/{userId}` ここでは、{userId} を 0、1 などの整数値に置き換える必要があります。
  
さらに、リポジトリ API は URI の {userId} で 2 つの特別なユーザー ID を受け入れる必要があります。
  
-  *default*  - 現在 API を操作しているユーザーを表します。 これにより、アプリケーションは、実際のユーザー ID 値を追跡することなく、現在のユーザーのコンテンツにアクセスできます。 例: `https://<portal>/QoERepositoryService/repository/user/default`。
    
-  *system*  - システム ユーザーを表します。 これにより、アプリケーションは、実際のユーザー ID 値を知らなくてもシステム ユーザーのコンテンツにアクセスできます。 例: `https://<portal>/QoERepositoryService/repository/user/system`。
    
特に指定がない限り、特別なユーザー ID は URI の {userId} で使用できます。 
  
REST 操作を次の表に示します。
  
|**操作**|**説明**|
|:-----|:-----|
|[ユーザーの取得](get-users.md) <br/> |リポジトリ内のユーザーのリストを返します。  <br/> |
|[ユーザーの取得](get-user.md) <br/> |ユーザー レコードを返します。  <br/> |
   

