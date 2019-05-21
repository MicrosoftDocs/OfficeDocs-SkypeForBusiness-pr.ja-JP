---
title: Skype for Business Server にセキュリティデスクを追加する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b1d9125-7488-419b-85dd-a8dd3ab5add3
description: Skype for Business Server Enterprise Voice で、組織のセキュリティデスクを E9 の展開に含める方法を計画しています。
ms.openlocfilehash: 7be3533879f36c897d148194345e1496945359b6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276455"
---
# <a name="include-the-security-desk-in-skype-for-business-server"></a><span data-ttu-id="663d1-103">Skype for Business Server にセキュリティデスクを追加する</span><span class="sxs-lookup"><span data-stu-id="663d1-103">Include the security desk in Skype for Business Server</span></span>
 
<span data-ttu-id="663d1-104">Skype for Business Server Enterprise Voice で、組織のセキュリティデスクを E9 の展開に含める方法を計画しています。</span><span class="sxs-lookup"><span data-stu-id="663d1-104">Planning how to include your organization's security desk in an E9-1-1 deployment, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="663d1-p101">会社によっては、セキュリティ デスクを緊急通話と関連させる必要があるかもしれません。セキュリティ デスクを E9-1-1 の展開に統合する方法を決定するには、以下の内容を検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="663d1-p101">Your company may require the security desk to become involved in an emergency call. To help decide how to integrate the Security Desk into you E9-1-1 deployment, you should answer the following questions.</span></span>
  
<span data-ttu-id="663d1-107">**緊急電話をセキュリティ デスクに通知するか。**</span><span class="sxs-lookup"><span data-stu-id="663d1-107">**Do you want the security desk to be notified when there is an emergency call?**</span></span>
  
<span data-ttu-id="663d1-108">Skype for Business Server がインスタントメッセージ (IM) の通知を Skype for Business SIP アドレスに送信するように、場所のポリシーを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="663d1-108">You can configure the location policy so that Skype for Business Server sends instant messaging (IM) alerts to the Skype for Business SIP addresses of one or more security personnel.</span></span> <span data-ttu-id="663d1-109">これらの通知には、緊急電話を発信した人物の名前、番号、および場所が含まれており、セキュリティ担当者による緊急事態の支援を容易にします。</span><span class="sxs-lookup"><span data-stu-id="663d1-109">These alerts contain the name, number, and location of the person placing the emergency call, and facilitate security personnel in assisting with the emergency situation.</span></span>
    
<span data-ttu-id="663d1-110">**緊急電話ごとにセキュリティ デスクと協議するか。**</span><span class="sxs-lookup"><span data-stu-id="663d1-110">**Do you want to conference the security desk in on each emergency call?**</span></span>
  
<span data-ttu-id="663d1-p103">緊急サービスのサービス プロバイダーがサポートしている場合は、場所ポリシーを構成して、各緊急電話にコールバック番号を含めることができます。プロバイダーはこの番号を使用して、組織のセキュリティ担当者が緊急電話に参加できるようにします。この場合、場所ポリシーで、一方向 (聞き取りのみ) で参加するか、または両方向 (双方向) で参加するかを構成できます。</span><span class="sxs-lookup"><span data-stu-id="663d1-p103">If supported by the emergency services service provider, you can configure the location policy to include a callback number with each emergency call. This number is then used by the provider to conference your organization's security personnel into emergency calls. This conferencing can be configured in the location policy to be one-way (listen-only) or two-way (bidirectional).</span></span>
    
> [!NOTE]
> <span data-ttu-id="663d1-p104">必要に応じて、場所ポリシーごとに異なる緊急担当者を構成できます。これにより、社内の領域によって応答をカスタマイズしたり、緊急電話がネットワークの内部からのものか外部からのものであるかによって、緊急電話の動作を変えたりすることができます。配布グループを使用すると、通知する担当者を指定できます。</span><span class="sxs-lookup"><span data-stu-id="663d1-p104">If desired, you can configure different emergency personnel for each location policy. This allows you to customize the response for different areas within your company, or create different behavior for emergency calls that originate from inside as opposed to outside the network. You can use distribution groups to specify the personnel you want to notify.</span></span> 
  

