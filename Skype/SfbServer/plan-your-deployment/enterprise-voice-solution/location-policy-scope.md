---
title: Skype for Business Server 2015 での場所ポリシーのスコープの割り当て
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e4c66517-c593-4253-b900-7b4dd8bddf2f
description: ~ 9-1-1 展開のビジネス サーバーのエンタープライズ VoIP の Skype の場所のポリシーを計画します。
ms.openlocfilehash: 745151092f0bc17abdfff2d26dd0186f24b8d038
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="assign-location-policy-scope-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での場所ポリシーのスコープの割り当て
 
~ 9-1-1 展開のビジネス サーバーのエンタープライズ VoIP の Skype の場所のポリシーを計画します。
  
ビジネス サーバー ポリシーの他の Skype で、複数のスコープ レベルでの場所のポリシーを割り当てることができるよう: グローバル、サイト、およびユーザーです。 ただし、ユーザー レベルの場所のポリシーのスコープの動作とは異なるビジネス サーバー ポリシーの他の Skype でのビット。 だけでなく、ユーザーごとの場所のポリシー適用できます (ユーザー、共通領域電話の連絡先オブジェクトなど) は、エンドポイントのオブジェクトにも適用できます Skype をビジネス サーバー ネットワークのサイトです。 ネットワーク サイトは、地理的場所に関連付けられたクライアント サブネットをグループ化したものです (ただし、必ずしも中央サイトまたはブランチ サイト全体の中のすべてのサブネットである必要はありません)。 ネットワーク サイト内のサブネットに接続されるクライアントはすべて、そのネットワーク サイトに割り当てられた場所ポリシーを自動的に取得します。 ユーザー レベルの場所ポリシーがユーザーとネットワーク サイトの両方に割り当てられる場合、ネットワーク サイト ベースの場所ポリシーがユーザーごとのポリシー設定より優先されます。
  
各ネットワーク サイトにはそれぞれに割り当てられた場所ポリシーがあり、各ポリシーには異なる PSTN 使用法、通知 URI、および電話会議 URI の値が割り当てられます。
  
> [!NOTE]
> このようにポリシー スコープが特殊な動作をするのは、ある支店のプールに所属するユーザーが別の支店を訪れていて、緊急電話を発信する場合、ユーザーに割り当てられたプールまたはサイトに関係なく、そのネットワーク サイトに適した E9-1-1 通話ルーティング設定が適用されるようにするためです。 
  

