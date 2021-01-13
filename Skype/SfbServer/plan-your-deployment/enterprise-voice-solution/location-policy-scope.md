---
title: Skype for Business Server で場所ポリシースコープを割り当てる
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Skype for Business Server 展開環境での E9-1-1 展開の場所ポリシーのエンタープライズ VoIP。
ms.openlocfilehash: 586aabe919ea4236dc724446da717b5f300d88e9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825527"
---
# <a name="assign-location-policy-scope-in-skype-for-business-server"></a>Skype for Business Server で場所ポリシースコープを割り当てる
 
Skype for Business Server 展開環境での E9-1-1 展開の場所ポリシーのエンタープライズ VoIP。
  
他の Skype for Business Server ポリシーと同様に、場所ポリシーは、グローバル、サイト、ユーザーの複数のスコープ レベルで割り当てることができます。 ただし、ユーザー レベルの場所ポリシーのスコープの動作は、他の Skype for Business Server ポリシーとは少し異なります。 ユーザー単位の場所ポリシーをエンドポイント オブジェクト (ユーザーや共通領域電話の連絡先オブジェクトなど) に適用できるだけでなく、Skype for Business Server ネットワーク サイトにも適用できます。 ネットワーク サイトは、地理的場所に関連付けられたクライアント サブネットをグループ化したものです (ただし、必ずしも中央サイトまたはブランチ サイト全体の中のすべてのサブネットである必要はありません)。 ネットワーク サイト内のサブネットに接続されるクライアントはすべて、そのネットワーク サイトに割り当てられた場所ポリシーを自動的に取得します。 ユーザー レベルの場所ポリシーがユーザーとネットワーク サイトの両方に割り当てられる場合、ネットワーク サイト ベースの場所ポリシーがユーザーごとのポリシー設定より優先されます。
  
各ネットワーク サイトにはそれぞれに割り当てられた場所ポリシーがあり、各ポリシーには異なる PSTN 使用法、通知 URI、および電話会議 URI の値が割り当てられます。
  
> [!NOTE]
> このようにポリシー スコープが特殊な動作をするのは、ある支店のプールに所属するユーザーが別の支店を訪れていて、緊急電話を発信する場合、ユーザーに割り当てられたプールまたはサイトに関係なく、そのネットワーク サイトに適した E9-1-1 通話ルーティング設定が適用されるようにするためです。 
  

