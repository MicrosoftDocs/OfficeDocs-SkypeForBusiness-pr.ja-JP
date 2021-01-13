---
title: Skype for Business Server にセキュリティ デスクを含める
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
ms.assetid: 4b1d9125-7488-419b-85dd-a8dd3ab5add3
description: Skype for Business Server エンタープライズ VoIP で E9-1-1 展開に組織のセキュリティ デスクを含める方法を計画します。
ms.openlocfilehash: 756af940eb327bc4744454e9ed9ef7a7fbfd517d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813407"
---
# <a name="include-the-security-desk-in-skype-for-business-server"></a>Skype for Business Server にセキュリティ デスクを含める
 
Skype for Business Server エンタープライズ VoIP で E9-1-1 展開に組織のセキュリティ デスクを含める方法を計画します。
  
会社によっては、セキュリティ デスクが緊急電話に参加する必要がある場合があります。 セキュリティ デスクを E9-1-1 展開に統合する方法を決定するには、次の質問に答える必要があります。
  
**緊急電話がある場合にセキュリティ デスクに通知を受け取りますか?**
  
場所ポリシーを構成して、Skype for Business Server が 1 人または複数のセキュリティ担当者の Skype for Business SIP アドレスにインスタント メッセージング (IM) 通知を送信できます。 これらのアラートには、緊急電話をかかえた人の名前、番号、場所が含まれているので、セキュリティ担当者は緊急対応を支援できます。
    
**各緊急電話でセキュリティ デスクを会議しますか?**
  
緊急サービス サービス プロバイダーによってサポートされている場合は、場所ポリシーを構成して、各緊急電話にコールバック番号を含めできます。 この番号は、プロバイダーが組織のセキュリティ担当者を緊急電話会議に参加するために使用します。 この会議は、場所ポリシーで一方向 (リッスンのみ) または双方向 (双方向) に構成できます。
    
> [!NOTE]
> 必要に応じて、場所ポリシーごとに異なる緊急担当者を構成できます。 これにより、会社内の異なる領域の応答をカスタマイズしたり、ネットワークの外部ではなく内部から発信される緊急電話に対して異なる動作を作成することができます。 配布グループを使用して、通知する担当者を指定できます。 
  

