---
title: 手動で場所を取得するためのユーザー エクスペリエンスを定義Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
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
ms.assetid: d37f67d3-e248-483b-b64c-3986559ef357
description: SIP トランキング プロバイダーを使用した E9-1-1 展開でのローミング ユーザー Skype for Business Server エンタープライズ VoIP。
ms.openlocfilehash: 263c2e79e340492b27d196f73373505f7c1e4f66
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60770115"
---
# <a name="define-the-user-experience-for-manually-acquiring-a-location-in-skype-for-business-server"></a>手動で場所を取得するためのユーザー エクスペリエンスを定義Skype for Business Server
 
SIP トランキング プロバイダーを使用した E9-1-1 展開でのローミング ユーザー Skype for Business Server エンタープライズ VoIP。
  
クライアントがネットワークの外部にいる場合、または定義されていないサブネットにいる場合は、ユーザーは場所を手入力できます。ただし緊急通報の際の通話は、緊急情報受信センター (PSAP) にルーティングされる前に、最初に国または地域の E9-1-1 Emergency Call Response Center (ECRC) のディスパッチャーにルーティングされます。ECRC は言葉で発信者に場所を問い合わせた後、提供された情報に基づいて、適切な PSAP に通話を転送します。 
  
**位置情報サービスによって自動的に提供されない場合、ユーザーに場所の入力を求めるメッセージが表示される必要がありますか?**
  
たとえば、クライアントが未定義のサブネット、自宅、ホテル、またはどこであれネットワークの外部に存在する場合は、ユーザーに場所の入力を求める必要があるでしょうか。
    
場所ポリシーの [**場所の入力を求める**] 設定を構成し、クライアントの動作を定義できます。この値を [いいえ] に設定すると、ユーザーは場所の入力を求められません。この値を [はい] に設定すると、ユーザーは場所の入力を求められますが、入力せずにプロンプトを閉じることもできます。この値を [免責事項] に設定すると、ユーザーは場所の入力を求められ、入力せずにプロンプトを閉ようとすると免責事項が表示されます。すべての場合において、ユーザーは通常どおりクライアントを使用し続けることができます。
    
ユーザーが手動で場所を入力すると、その場所はクライアントのネットワークの既定のゲートウェイの MAC アドレスにマップされ、クライアント上にあるユーザーごとのテーブルに格納されます。 ユーザーが以前に保存した場所に戻った場合、Skype for Businessクライアントは自動的にその場所に自分自身を設定します。 
  
> [!NOTE]
> クライアントの現在の場所のみを変更できますが、ローカル ユーザーのテーブルに格納されている任意の場所を削除できます。 
  

