---
title: CQD のユーザーサービス
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd5c828-42dd-4f48-bf87-29993193cb3a
description: '概要: 通話品質ダッシュボードのリポジトリ API の一部であるユーザーサービスについて説明します。 通話品質ダッシュボードは、Skype for Business Server のツールです。'
ms.openlocfilehash: 6e0a6a58be98469458a8c8e7063402ff6477c35f
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2019
ms.locfileid: "35221311"
---
# <a name="user-service-for-cqd"></a>CQD のユーザーサービス
 
**概要:** 通話品質ダッシュボードのリポジトリ API の一部であるユーザーサービスについて説明します。 通話品質ダッシュボードは、Skype for Business Server のツールです。
  
ユーザーサービスは、通話品質ダッシュボードのリポジトリ API の一部です。
  
## <a name="user-service"></a>ユーザー サービス

リポジトリ API は、ユーザープロビジョニング (新規ユーザーアカウントの作成) が自動的かつ暗黙的なものである簡素化されたユーザー管理モデルを提供します。 ユーザーが初めてリポジトリ API に対する要求を行うと、リポジトリは新しいユーザーレコードを作成します。 
  
通話品質ダッシュボードでは、新規ユーザーのユーザー専用項目も自動的に作成されます。 新しいユーザー専用項目は、システムユーザーの項目の完全な複製です。 こうすることで、ユーザーはレポートやクエリの独自のコピーから開始し、すぐにカスタマイズを開始できるようになります。 
  
> [!NOTE]
> 通話品質ダッシュボードを使用すると、ユーザーはいつでも専用のアイテムをリセットできます。 
  
 **特殊なユーザー Id**
  
リポジトリ API には、特定のユーザーを指定する整数値を受け取る REST API Uri が含まれています。 例: `https://<portal>/QoERepositoryService/repository/user/{userId}`。 {UserId} は、0、1などの整数値で置き換える必要があります。
  
さらに、リポジトリ API は、Uri の {userId} で2つの特殊なユーザー Id を受け取ります。
  
-  *default* -API を現在操作しているユーザーを表します。 これにより、アプリケーションは実際のユーザー ID の値を追跡しなくても、現在のユーザーのコンテンツにアクセスできます。 例: `https://<portal>/QoERepositoryService/repository/user/default`。
    
-  *システム*-システムユーザーを表します。 これにより、アプリケーションは実際のユーザー ID 値を知らなくても、システムユーザーのコンテンツにアクセスできます。 例: `https://<portal>/QoERepositoryService/repository/user/system`。
    
特に注記がない限り、特殊なユーザー Id は、Uri の {userId} で使用できます。 
  
REST 操作は、次の表に記載されています。
  
|**操作**|**説明**|
|:-----|:-----|
|[ユーザーの取得](get-users.md) <br/> |リポジトリ内のユーザーのリストを返します。  <br/> |
|[ユーザーの取得](get-user.md) <br/> |ユーザーレコードを返します。  <br/> |
   

