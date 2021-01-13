---
title: 通話品質ダッシュボード (CQD) のユーザー設定サービス
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
description: '概要: 通話品質ダッシュボードのリポジトリ API の一部である User Settings Service について説明します。 通話品質ダッシュボードは、Skype for Business Server 用のツールです。'
ms.openlocfilehash: 2b2fc9810f1eceb74974dc105263b0bdcf37ae01
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803038"
---
# <a name="user-settings-service-for-call-quality-dashboard-cqd"></a>通話品質ダッシュボード (CQD) のユーザー設定サービス
 
**概要:** 通話品質ダッシュボードのリポジトリ API の一部である User Settings Service について説明します。 通話品質ダッシュボードは、Skype for Business Server 用のツールです。
  
ユーザー設定サービスは、通話品質ダッシュボードのリポジトリ API の一部です。
  
## <a name="user-settings-service"></a>ユーザー設定サービス

ユーザー設定は、アプリケーションがさまざまな目的でメタデータを格納するために使用できるキーと値のペアです。ユーザー単位でのアプリケーション動作のカスタマイズも含まれます。 各ユーザーは、ユーザー設定用の記憶域を受け取ります。 ユーザー設定を追加、変更、削除できるのは所有者のみです。
  
 **グローバル設定**
  
グローバル設定は、システム ユーザーが所有するユーザー設定であり、すべてのユーザーが読み取り専用でアクセスできます。 グローバル設定は定数であり、リポジトリの作成時に作成され、変更されません。
  
各ユーザーは、同じキーでユーザー設定を作成することで、グローバル設定を上書きできます。 アプリケーションが有効なユーザー設定を要求すると、API はユーザー設定とマージされた一連のグローバル設定を返し、キーが同じ場合は各ユーザー設定がそれぞれのグローバル設定に取って適用されます。 また、API はユーザー設定を返すだけで、どの設定が上書きされるのかアプリケーションが確認できます。 
  
REST 操作を次の表に示します。

|**操作**|**説明**|
|:-----|:-----|
|[ユーザー設定の取得](get-user-settings.md) <br/> |ユーザー設定を取得すると、指定したユーザーの設定の一覧が返されます。  <br/> |
|[ユーザー設定の取得](get-user-setting.md) <br/> |ユーザー設定を取得すると、1 つのユーザー設定が返されます。  <br/> |
   

