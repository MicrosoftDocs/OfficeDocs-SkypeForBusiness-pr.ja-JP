---
title: 通話品質ダッシュボード (CQD) の項目サービス
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b6d7b02a-a34e-4fef-986c-ca442e18fa0c
description: '概要: 通話品質ダッシュボードのリポジトリ API の一部であるアイテムサービスについて説明します。 通話品質ダッシュボードは、Skype for Business Server のツールです。'
ms.openlocfilehash: 5fdf2aedcb1a5e8d7d1929d7af70c5911cae46f0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816716"
---
# <a name="item-service-for-call-quality-dashboard-cqd"></a>通話品質ダッシュボード (CQD) の項目サービス
 
**概要:** 通話品質ダッシュボードのリポジトリ API の一部である、アイテムサービスについて説明します。 通話品質ダッシュボードは、Skype for Business Server のツールです。
  
項目サービスは、通話品質ダッシュボードのリポジトリ API の一部です。
  
## <a name="item-service"></a>アイテムのサービス

リポジトリ API は、項目サービスと呼ばれるシンプルなコンテンツ管理サービスを提供します。これを使うと、ユーザーに対してアプリケーションで定義されたコンテンツを保存することができます。 
  
システムのコンテンツは、システムユーザーによって所有され、読み取り専用のアクセス権を持つすべてのユーザーが共有します。 専用ユーザーのコンテンツは、通常のユーザーによって所有され、所有者だけが変更または削除できますが、すべてのユーザーが引き続き読み取り専用アクセス権を持っています。
  
> [!NOTE]
> この API ドキュメントでは、リポジトリ API の読み取り専用操作について説明します。 
  
通話品質ダッシュボードは、レポートやクエリをリポジトリデータベースのアイテムとして保存します。 アイテムにはオプションのサブアイテムを含めることができ、通話品質ダッシュボードは、サブアイテム機能を使用して階層構造の構造でレポートとクエリを整理します。
  
項目サービスには、次のような概念があります。
  
- **アイテム**-リポジトリの基本要素。 各項目は、1人のユーザーによって所有されます。
    
- **サブ項目**-リポジトリの基本的な構造です。 項目には、0、1、またはそれ以上の下位項目を含めることができます。
    
- **項目の先祖**-一番上の項目 (ユーザーの既定の項目である) から始まり、特定の項目に至る項目の一覧。
    
- **項目コンテンツ**-項目に格納されているアプリケーション固有のコンテンツ。 通話品質ダッシュボードは、レポートとクエリの JSON 表現をコンテンツに保存します。
    
REST 操作は、次の表に記載されています。
  

|**操作**|**説明**|
|:-----|:-----|
|[アイテムの取得](get-items.md) <br/> |アイテムの取得リポジトリ内のすべてのアイテムを返します。  <br/> |
|[アイテムの取得](get-item.md) <br/> |項目を取得すると、特定の項目が返されます。  <br/> |
|[サブアイテムの取得](get-sub-items.md) <br/> |サブ項目の取得: 特定の項目のサブ項目を返します。  <br/> |
|[アイテムの親の取得](get-item-ancestors.md) <br/> |項目の先祖を取得すると、特定の項目の先祖が返されます。  <br/> |
|[アイテムの更新](update-item.md) <br/> |リポジトリ内の特定のアイテムを更新します。  <br/> |
   

