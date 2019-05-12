---
title: 救難用のユーザー ・ サービス
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd5c828-42dd-4f48-bf87-29993193cb3a
description: '概要: は、ユーザー サービス、品質のダッシュ ボードを呼び出すためのリポジトリ API の一部について説明します。 通話品質のダッシュ ボードは、Skype ビジネス サーバー用のツールです。'
ms.openlocfilehash: 631ccfefe7a4503f325c288ef1bf27d4366869e4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33915081"
---
# <a name="user-service-for-cqd"></a>救難用のユーザー ・ サービス
 
**の概要:** ユーザー サービスは、品質のダッシュ ボードを呼び出すためのリポジトリ API の一部について説明します。 通話品質のダッシュ ボードは、Skype ビジネス サーバー用のツールです。
  
ユーザー サービスは、品質のダッシュ ボードを呼び出すためのリポジトリ API の一部です。
  
## <a name="user-service"></a>ユーザー サービス

リポジトリ API には、ここでユーザー (新しいユーザー アカウントを作成する) のプロビジョニング、自動と暗黙の型のシンプルなユーザー管理モデルが用意されています。 ユーザーは、最初にリポジトリ API に対して要求を行い、リポジトリは、新しいユーザー レコードを作成します。 
  
品質のダッシュ ボードが自動的にユーザーを作成する呼び出しは、新しいユーザーのアイテム専用です。 新しいユーザーが専用のアイテムは、システム ユーザーのアイテムの完全なクローンです。 この方法により、ユーザーは、レポートおよびクエリは、すぐに開始することをカスタマイズするが自分のコピーを使用して起動できます。 
  
> [!NOTE]
> 品質のダッシュ ボードの呼び出しを使用すると、ユーザーはリセット専用のアイテムは、いつでも。 
  
 **特別なユーザーの Id**
  
リポジトリ API には、特定のユーザーを指定する整数値を受け取る REST API Uri が含まれています。 例: `https://<portal>/QoERepositoryService/repository/user/{userId}`。 {ユーザー Id} を整数値 0 などで置き換える必要がありますここでは、1 などです。
  
さらに、リポジトリ API は、Uri で {ユーザー Id} の 2 つの特別なユーザー Id を受け入れます。
  
-  *既定*では、API を使用して現在操作しているユーザーを表します。 これにより、アプリケーションの実際のユーザー ID の値を追跡せずに現在のユーザーのコンテンツにアクセスします。 例: ` https://<portal>/QoERepositoryService/repository/user/default`。
    
-  *システム*では、システムのユーザーを表します。 これにより、実際のユーザー ID の値を知らなくてもシステムのユーザーのコンテンツにアクセスするアプリケーションです。 例: `https://<portal>/QoERepositoryService/repository/user/system`。
    
特に断らない限りは、Uri で {ユーザー Id} にある特別なユーザ Id が使用できます。 
  
次の表には、他の操作が含まれます。
  
|**操作**|**説明**|
|:-----|:-----|
|[ユーザーの取得](get-users.md) <br/> |リポジトリ内のユーザーの一覧を返します。  <br/> |
|[ユーザーの取得](get-user.md) <br/> |ユーザー レコードを返します。  <br/> |
   

