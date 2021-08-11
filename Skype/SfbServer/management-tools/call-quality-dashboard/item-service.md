---
title: 通話品質ダッシュボードの Item Service (CQD)
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
ms.assetid: b6d7b02a-a34e-4fef-986c-ca442e18fa0c
description: '概要: 呼び出し品質ダッシュボードのリポジトリ API の一部であるアイテム サービスについて説明します。 品質ダッシュボードの呼び出しは、ユーザーのSkype for Business Server。'
ms.openlocfilehash: 4e46cb213502e646a9fc3c750e7aeb40ffb6aff47b4d2aba0c19e04c56ce6cc0
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54331229"
---
# <a name="item-service-for-call-quality-dashboard-cqd"></a>通話品質ダッシュボードの Item Service (CQD)
 
**概要:** 呼び出し品質ダッシュボードのリポジトリ API の一部であるアイテム サービスについて説明します。 品質ダッシュボードの呼び出しは、ユーザーのSkype for Business Server。
  
Item Service は、呼び出し品質ダッシュボードのリポジトリ API の一部です。
  
## <a name="item-service"></a>アイテムのサービス

リポジトリ API は、アイテム サービスと呼ばれる単純なコンテンツ管理サービスを提供し、ユーザーに対してアプリケーション定義のコンテンツを格納するために使用できます。 
  
システムコンテンツはシステム ユーザーによって所有され、読み取り専用アクセス権を持つすべてのユーザーによって共有されます。 専用のユーザー コンテンツは通常のユーザーによって所有され、所有者だけが変更または削除できますが、すべてのユーザーは引き続き読み取り専用アクセス権を持っています。
  
> [!NOTE]
> この API ドキュメントでは、リポジトリ API の読み取り専用操作について説明します。 
  
[品質ダッシュボードの呼び出し] は、レポートとクエリをリポジトリ データベースのアイテムとして保存します。 アイテムにはオプションのサブアイテムを含め、通話品質ダッシュボードはサブアイテム機能を使用してレポートとクエリを階層構造で整理します。
  
アイテム サービスには、次の概念が含まれます。
  
- **Item** - リポジトリの基本要素。 各アイテムは、正確に 1 つのユーザーによって所有されます。
    
- **Sub-Item** - リポジトリの基本的な組織の仕組み。 アイテムには、0、1、または複数の下位アイテムを指定できます。
    
- **アイテムの先祖** - ユーザーの既定のアイテムである一番上のアイテムから始まり、特定のアイテムに至るアイテムのリスト。
    
- **アイテム コンテンツ** - アイテムに格納されているアプリケーション固有のコンテンツ。 通話品質ダッシュボードは、レポートとクエリの JSON 表記をコンテンツに保存します。
    
REST 操作は、次の表に含まれています。
  

|**操作名**|**説明**|
|:-----|:-----|
|[アイテムの取得](get-items.md) <br/> |Get Items は、リポジトリ内のすべてのアイテムを返します。  <br/> |
|[アイテムの取得](get-item.md) <br/> |Get Item は、特定の Item を返します。  <br/> |
|[サブアイテムの取得](get-sub-items.md) <br/> |Get Sub-Items特定のアイテムのサブアイテムを返します。  <br/> |
|[アイテムの親の取得](get-item-ancestors.md) <br/> |Get Item Ancestors は、特定の Item の先祖を返します。  <br/> |
|[アイテムの更新](update-item.md) <br/> |リポジトリ内の特定のアイテムを更新します。  <br/> |
   

