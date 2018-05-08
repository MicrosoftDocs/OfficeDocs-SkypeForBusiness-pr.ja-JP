---
title: Skype for Business Server 2015 でのセキュリティ デスクの追加
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
ms.assetid: 4b1d9125-7488-419b-85dd-a8dd3ab5add3
description: ビジネス サーバーのエンタープライズ VoIP の Skype で、~ 9-1-1 の展開で、組織のセキュリティ デスクを追加する方法を計画します。
ms.openlocfilehash: adaa1096651c5e3f86d15af1b2409a8de03e6c9c
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="include-the-security-desk-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 でのセキュリティ デスクの追加
 
ビジネス サーバーのエンタープライズ VoIP の Skype で、~ 9-1-1 の展開で、組織のセキュリティ デスクを追加する方法を計画します。
  
会社によっては、セキュリティ デスクを緊急通話と関連させる必要があるかもしれません。セキュリティ デスクを E9-1-1 の展開に統合する方法を決定するには、以下の内容を検討する必要があります。
  
**緊急電話をセキュリティ デスクに通知するか。**
  
Skype ビジネス サーバーの 1 つまたは複数のセキュリティ担当者のアドレスをビジネスの SIP の Skype にインスタント メッセージング (IM) の通知を送信できるよう、場所のポリシーを構成できます。 これらの通知には、緊急電話を発信した人物の名前、番号、および場所が含まれており、セキュリティ担当者による緊急事態の支援を容易にします。
    
**緊急電話ごとにセキュリティ デスクと協議するか。**
  
緊急サービスのサービス プロバイダーがサポートしている場合は、場所ポリシーを構成して、各緊急電話にコールバック番号を含めることができます。プロバイダーはこの番号を使用して、組織のセキュリティ担当者が緊急電話に参加できるようにします。この場合、場所ポリシーで、一方向 (聞き取りのみ) で参加するか、または両方向 (双方向) で参加するかを構成できます。
    
> [!NOTE]
> 必要に応じて、場所ポリシーごとに異なる緊急担当者を構成できます。これにより、社内の領域によって応答をカスタマイズしたり、緊急電話がネットワークの内部からのものか外部からのものであるかによって、緊急電話の動作を変えたりすることができます。配布グループを使用すると、通知する担当者を指定できます。 
  

