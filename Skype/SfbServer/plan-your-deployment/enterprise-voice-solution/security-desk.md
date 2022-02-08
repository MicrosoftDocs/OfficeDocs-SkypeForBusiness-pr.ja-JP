---
title: セキュリティ デスクを [セキュリティ デスク] にSkype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
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
ms.assetid: 4b1d9125-7488-419b-85dd-a8dd3ab5add3
description: E9-1-1 展開に組織のセキュリティ デスクを含める方法を計画Skype for Business Server エンタープライズ VoIP。
ms.openlocfilehash: 0b0e6049bb8b25753f62c7a926985fb2fad79b47
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62389109"
---
# <a name="include-the-security-desk-in-skype-for-business-server"></a>セキュリティ デスクを [セキュリティ デスク] にSkype for Business Server
 
E9-1-1 展開に組織のセキュリティ デスクを含める方法を計画Skype for Business Server エンタープライズ VoIP。
  
会社では、セキュリティ デスクが緊急電話に参加する必要がある場合があります。 セキュリティ デスクを E9-1-1 展開に統合する方法を決定するには、次の質問に答える必要があります。
  
**緊急電話が発生したときにセキュリティ デスクに通知を受け取りますか?**
  
1 人または複数のセキュリティ担当者の Skype for Business Server SIP アドレスにインスタント メッセージング (IM) Skype for Businessを送信する場所ポリシーを構成できます。 これらのアラートには、緊急電話をかかえる人の名前、番号、場所が含まれているので、セキュリティ担当者が緊急事態を支援できます。
    
**各緊急通話でセキュリティ デスクを会議しますか?**
  
緊急サービス サービス プロバイダーによってサポートされている場合は、各緊急通話にコールバック番号を含める場所ポリシーを構成できます。 この番号は、プロバイダーが組織のセキュリティ担当者を緊急通話に電話会議するために使用します。 この会議は、場所ポリシーで一方向 (リッスンのみ) または双方向 (双方向) に構成できます。
    
> [!NOTE]
> 必要に応じて、場所ポリシーごとに異なる緊急担当者を構成できます。 これにより、会社内の異なる領域に対する応答をカスタマイズしたり、ネットワークの外部ではなく内部から発信される緊急通話に対して異なる動作を作成することができます。 配布グループを使用して、通知する担当者を指定できます。 
  

