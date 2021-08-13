---
title: ユーザー 設定 サービス for 通話品質ダッシュボード (CQD)
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
ms.assetid: eafeb54a-2574-415b-b991-a0ff0470d8c3
description: '概要: 呼び出し品質ダッシュボード設定リポジトリ API の一部である User 設定 サービスについて説明します。 品質ダッシュボードの呼び出しは、ユーザーのSkype for Business Server。'
ms.openlocfilehash: c037024c8fe336c3614dd9daf6ee02370337ad5c6c44b45c783044cc421f626f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54315563"
---
# <a name="user-settings-service-for-call-quality-dashboard-cqd"></a>ユーザー 設定 サービス for 通話品質ダッシュボード (CQD)
 
**概要:** 呼び出し品質ダッシュボード設定リポジトリ API の一部である User 設定 サービスについて説明します。 品質ダッシュボードの呼び出しは、ユーザーのSkype for Business Server。
  
User 設定サービスは、呼び出し品質ダッシュボードのリポジトリ API の一部です。
  
## <a name="user-settings-service"></a>ユーザー設定サービス

ユーザー設定は、アプリケーションがユーザーごとのアプリケーション動作のカスタマイズなど、さまざまな目的でメタデータを格納するために使用できるキーと値のペアです。 各ユーザーは、ユーザー設定用の記憶域を受け取ります。 ユーザー設定を追加、変更、および削除できるのは所有者のみです。
  
 **グローバル 設定**
  
グローバル設定は、システム ユーザーが所有するユーザー設定であり、すべてのユーザーが読み取り専用アクセス権を持っています。 グローバル設定は定数です。リポジトリの作成時に作成され、変更されません。
  
各ユーザーは、同じキーを使用してユーザー設定を作成することで、グローバル設定を上書きできます。 アプリケーションが有効なユーザー設定を要求すると、API はユーザー設定と結合された一連のグローバル設定を返します。キーが同じ場合、各ユーザー設定はそれぞれのグローバル設定に取ってかかっています。 また、API はユーザー設定を返すだけで、どの設定が上書きされるのかアプリケーションが確認できます。 
  
REST 操作は、次の表に含まれています。

|**操作名**|**説明**|
|:-----|:-----|
|[ユーザー設定の取得](get-user-settings.md) <br/> |Get User 設定指定したユーザーの設定の一覧を返します。  <br/> |
|[ユーザー設定の取得](get-user-setting.md) <br/> |ユーザー設定を取得すると、1 つのユーザー設定が返されます。  <br/> |
   

