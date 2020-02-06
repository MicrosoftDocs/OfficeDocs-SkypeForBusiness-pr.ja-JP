---
title: Skype for Business Server で位置情報ポリシーのスコープを割り当てる
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e4c66517-c593-4253-b900-7b4dd8bddf2f
description: Skype for Business Server Enterprise Voice での E9 展開のための位置情報ポリシーを計画しています。
ms.openlocfilehash: 3865db146676ed64da9422d2a8731e44451ec6ac
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802757"
---
# <a name="assign-location-policy-scope-in-skype-for-business-server"></a>Skype for Business Server で位置情報ポリシーのスコープを割り当てる
 
Skype for Business Server Enterprise Voice での E9 展開のための位置情報ポリシーを計画しています。
  
他の Skype for Business Server ポリシーと同じように、場所ポリシーは、グローバル、サイト、ユーザーという複数のスコープレベルで割り当てることができます。 ただし、ユーザーレベルの位置情報ポリシーの範囲は、他の Skype for Business Server のポリシーとは少し異なる動作をします。 ユーザーごとの場所ポリシーをエンドポイントオブジェクト (ユーザー、一般的なエリア電話の連絡先オブジェクトなど) に適用できるだけでなく、Skype for Business Server ネットワークサイトにも適用することができます。 ネットワーク サイトは、地理的場所に関連付けられたクライアント サブネットをグループ化したものです (ただし、必ずしも中央サイトまたはブランチ サイト全体の中のすべてのサブネットである必要はありません)。 ネットワーク サイト内のサブネットに接続されるクライアントはすべて、そのネットワーク サイトに割り当てられた場所ポリシーを自動的に取得します。 ユーザー レベルの場所ポリシーがユーザーとネットワーク サイトの両方に割り当てられる場合、ネットワーク サイト ベースの場所ポリシーがユーザーごとのポリシー設定より優先されます。
  
各ネットワーク サイトにはそれぞれに割り当てられた場所ポリシーがあり、各ポリシーには異なる PSTN 使用法、通知 URI、および電話会議 URI の値が割り当てられます。
  
> [!NOTE]
> このようにポリシー スコープが特殊な動作をするのは、ある支店のプールに所属するユーザーが別の支店を訪れていて、緊急電話を発信する場合、ユーザーに割り当てられたプールまたはサイトに関係なく、そのネットワーク サイトに適した E9-1-1 通話ルーティング設定が適用されるようにするためです。 
  

