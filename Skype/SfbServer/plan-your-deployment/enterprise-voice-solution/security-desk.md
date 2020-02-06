---
title: Skype for Business Server にセキュリティデスクを追加する
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
ms.assetid: 4b1d9125-7488-419b-85dd-a8dd3ab5add3
description: Skype for Business Server Enterprise Voice で、組織のセキュリティデスクを E9 の展開に含める方法を計画しています。
ms.openlocfilehash: 19fc8a01fcb51be3ce36435a5a657c3253716b2c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802457"
---
# <a name="include-the-security-desk-in-skype-for-business-server"></a>Skype for Business Server にセキュリティデスクを追加する
 
Skype for Business Server Enterprise Voice で、組織のセキュリティデスクを E9 の展開に含める方法を計画しています。
  
会社によっては、セキュリティ デスクを緊急通話と関連させる必要があるかもしれません。セキュリティ デスクを E9-1-1 の展開に統合する方法を決定するには、以下の内容を検討する必要があります。
  
**緊急電話をセキュリティ デスクに通知するか。**
  
Skype for Business Server がインスタントメッセージ (IM) の通知を Skype for Business SIP アドレスに送信するように、場所のポリシーを構成することができます。 これらの通知には、緊急電話を発信した人物の名前、番号、および場所が含まれており、セキュリティ担当者による緊急事態の支援を容易にします。
    
**緊急電話ごとにセキュリティ デスクと協議するか。**
  
緊急サービスのサービス プロバイダーがサポートしている場合は、場所ポリシーを構成して、各緊急電話にコールバック番号を含めることができます。プロバイダーはこの番号を使用して、組織のセキュリティ担当者が緊急電話に参加できるようにします。この場合、場所ポリシーで、一方向 (聞き取りのみ) で参加するか、または両方向 (双方向) で参加するかを構成できます。
    
> [!NOTE]
> 必要に応じて、場所ポリシーごとに異なる緊急担当者を構成できます。これにより、社内の領域によって応答をカスタマイズしたり、緊急電話がネットワークの内部からのものか外部からのものであるかによって、緊急電話の動作を変えたりすることができます。配布グループを使用すると、通知する担当者を指定できます。 
  

