---
title: '[場所ポリシーのスコープを割り当てる] Skype for Business Server'
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e4c66517-c593-4253-b900-7b4dd8bddf2f
description: E9-1-1 展開の場所ポリシーを計画Skype for Business Server エンタープライズ VoIP。
ms.openlocfilehash: 1e87998946c5161bd6670bf767c6b83a55dbec39
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58628579"
---
# <a name="assign-location-policy-scope-in-skype-for-business-server"></a>[場所ポリシーのスコープを割り当てる] Skype for Business Server
 
E9-1-1 展開の場所ポリシーを計画Skype for Business Server エンタープライズ VoIP。
  
他のポリシー Skype for Business Serverと同様に、場所ポリシーはグローバル、サイト、およびユーザーの複数のスコープ レベルで割り当てることができます。 ただし、ユーザー レベルの場所ポリシーの範囲は、他の場所の場所ポリシーとは少Skype for Business Server動作します。 ユーザーごとの場所ポリシーをエンドポイント オブジェクト (User や Common Area 電話 連絡先オブジェクトなど) に適用できるだけでなく、ユーザーごとの場所ポリシーをネットワーク サイトSkype for Business Serverすることもできます。 ネットワーク サイトは、地理的場所に関連付けられたクライアント サブネットをグループ化したものです (ただし、必ずしも中央サイトまたはブランチ サイト全体の中のすべてのサブネットである必要はありません)。 ネットワーク サイト内のサブネットに接続されるクライアントはすべて、そのネットワーク サイトに割り当てられた場所ポリシーを自動的に取得します。 ユーザー レベルの場所ポリシーがユーザーとネットワーク サイトの両方に割り当てられる場合、ネットワーク サイト ベースの場所ポリシーがユーザーごとのポリシー設定より優先されます。
  
各ネットワーク サイトにはそれぞれに割り当てられた場所ポリシーがあり、各ポリシーには異なる PSTN 使用法、通知 URI、および電話会議 URI の値が割り当てられます。
  
> [!NOTE]
> このようにポリシー スコープが特殊な動作をするのは、ある支店のプールに所属するユーザーが別の支店を訪れていて、緊急電話を発信する場合、ユーザーに割り当てられたプールまたはサイトに関係なく、そのネットワーク サイトに適した E9-1-1 通話ルーティング設定が適用されるようにするためです。 
  

