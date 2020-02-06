---
title: 通話品質ダッシュボードのユーザー設定サービス (CQD)
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
ms.assetid: eafeb54a-2574-415b-b991-a0ff0470d8c3
description: '概要: 通話品質ダッシュボードのリポジトリ API の一部である、ユーザー設定サービスについて説明します。 通話品質ダッシュボードは、Skype for Business Server のツールです。'
ms.openlocfilehash: 1eef869523bf1590a00ca199727b33ec9e13ccba
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816646"
---
# <a name="user-settings-service-for-call-quality-dashboard-cqd"></a>通話品質ダッシュボードのユーザー設定サービス (CQD)
 
**概要:** 通話品質ダッシュボードのリポジトリ API の一部である、ユーザー設定サービスについて説明します。 通話品質ダッシュボードは、Skype for Business Server のツールです。
  
ユーザー設定サービスは、通話品質ダッシュボードのリポジトリ API の一部です。
  
## <a name="user-settings-service"></a>ユーザー設定サービス

ユーザー設定は、アプリケーション動作のカスタマイズなど、さまざまな目的のために、アプリケーションが使うことのできるキーと値のペアです。 各ユーザーは、ユーザー設定のためのストレージを受け取ります。 所有者のみが、ユーザー設定の追加、変更、削除を行うことができます。
  
 **グローバル設定**
  
グローバル設定とは、システムユーザーが所有するユーザー設定のことで、すべてのユーザーに読み取り専用のアクセス権があります。 グローバル設定は定数であり、リポジトリの作成時に作成され、変更されることはありません。
  
各ユーザーは、同じキーを使用してユーザー設定を作成することで、グローバル設定を上書きすることができます。 アプリケーションが実効ユーザー設定を要求すると、API は、ユーザー設定と結合された一連のグローバル設定を返し、キーが同じである場合は、各ユーザー設定がそれぞれのグローバル設定を置き換えます。 また、API では、アプリケーションがオーバーライドされた設定を確認できるように、ユーザー設定だけを返すことができます。 
  
REST 操作は、次の表に記載されています。

|**操作**|**説明**|
|:-----|:-----|
|[ユーザー設定の取得](get-user-settings.md) <br/> |ユーザー設定の取得指定したユーザーの設定のリストを返します。  <br/> |
|[ユーザー設定の取得](get-user-setting.md) <br/> |Get User Setting は、単一のユーザー設定を返します。  <br/> |
   

