---
title: ビジネス サーバーの Skype 内の場所を手動で取得するためのユーザー エクスペリエンスを定義します。
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d37f67d3-e248-483b-b64c-3986559ef357
description: ビジネス サーバーのエンタープライズ VoIP の Skype で、SIP トランキング プロバイダーを使用して ~ 9-1-1 の展開でユーザーの移動を計画しています。
ms.openlocfilehash: 8682ba47e3543cc39b1fc793c587040a7821f8c7
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30891351"
---
# <a name="define-the-user-experience-for-manually-acquiring-a-location-in-skype-for-business-server"></a>ビジネス サーバーの Skype 内の場所を手動で取得するためのユーザー エクスペリエンスを定義します。
 
ビジネス サーバーのエンタープライズ VoIP の Skype で、SIP トランキング プロバイダーを使用して ~ 9-1-1 の展開でユーザーの移動を計画しています。
  
クライアントがネットワークの外部にいる場合、または定義されていないサブネットにいる場合は、ユーザーは場所を手動で入力できます。ただし緊急通報の場合の通話は、緊急情報受信センター (PSAP) にルーティングされる前に、最初に国または地域の E9-1-1 Emergency Call Response Center (ECRC) のディスパッチャーにルーティングされます。ECRC は言葉で発信者に場所を問い合わせた後、提供された情報に基づいて、適切な PSAP に通話を転送します。 
  
**位置情報サービスによって自動的にパスワードがない場合は、場所を入力するユーザーが表示されるのででしょうか。**
  
たとえば、クライアントが未定義のサブネット、自宅、ホテル、またはネットワーク外部のいずれかの場所に存在する場合は、ユーザーに場所の入力を求める必要があるでしょうか。
    
場所ポリシーの [**場所の入力を求める**] 設定を構成し、クライアントの動作を定義できます。この値を [いいえ] に設定すると、ユーザーは場所の入力を求められません。この値を [はい] に設定すると、ユーザーは場所の入力を求められますが、入力せずにプロンプトを閉じることもできます。この値を [免責事項] に設定すると、ユーザーは場所の入力を求められ、入力せずにプロンプトを閉じようとすると免責事項が表示されます。すべての場合において、ユーザーは通常どおりクライアントを使用し続けることができます。
    
ユーザーは、場所を手動で入力、場所は、クライアントのネットワークのデフォルト ゲートウェイの MAC アドレスにマップされてし、クライアント上にあるユーザーごとのテーブルに格納されます。 ユーザーは、以前に保存された任意の場所に戻ると、ビジネス クライアント用の Skype が自動的に設定自体その場所にします。 
  
> [!NOTE]
> 、クライアントの現在の位置のみを変更することができますが、ローカルのユーザーのテーブルに格納されている任意の場所を削除することもできます。 
  

