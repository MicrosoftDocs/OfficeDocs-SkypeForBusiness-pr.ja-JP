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
# <a name="include-the-security-desk-in-skype-for-business-server"></a><span data-ttu-id="ac3ff-103">Skype for Business Server にセキュリティ デスクを含める</span><span class="sxs-lookup"><span data-stu-id="ac3ff-103">Include the security desk in Skype for Business Server</span></span>
 
<span data-ttu-id="ac3ff-104">Skype for Business Server エンタープライズ VoIP で E9-1-1 展開に組織のセキュリティ デスクを含める方法を計画します。</span><span class="sxs-lookup"><span data-stu-id="ac3ff-104">Planning how to include your organization's security desk in an E9-1-1 deployment, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="ac3ff-105">会社によっては、セキュリティ デスクが緊急電話に参加する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="ac3ff-105">Your company may require the security desk to become involved in an emergency call.</span></span> <span data-ttu-id="ac3ff-106">セキュリティ デスクを E9-1-1 展開に統合する方法を決定するには、次の質問に答える必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac3ff-106">To help decide how to integrate the Security Desk into you E9-1-1 deployment, you should answer the following questions.</span></span>
  
<span data-ttu-id="ac3ff-107">**緊急電話がある場合にセキュリティ デスクに通知を受け取りますか?**</span><span class="sxs-lookup"><span data-stu-id="ac3ff-107">**Do you want the security desk to be notified when there is an emergency call?**</span></span>
  
<span data-ttu-id="ac3ff-108">場所ポリシーを構成して、Skype for Business Server が 1 人または複数のセキュリティ担当者の Skype for Business SIP アドレスにインスタント メッセージング (IM) 通知を送信できます。</span><span class="sxs-lookup"><span data-stu-id="ac3ff-108">You can configure the location policy so that Skype for Business Server sends instant messaging (IM) alerts to the Skype for Business SIP addresses of one or more security personnel.</span></span> <span data-ttu-id="ac3ff-109">これらのアラートには、緊急電話をかかえた人の名前、番号、場所が含まれているので、セキュリティ担当者は緊急対応を支援できます。</span><span class="sxs-lookup"><span data-stu-id="ac3ff-109">These alerts contain the name, number, and location of the person placing the emergency call, and facilitate security personnel in assisting with the emergency situation.</span></span>
    
<span data-ttu-id="ac3ff-110">**各緊急電話でセキュリティ デスクを会議しますか?**</span><span class="sxs-lookup"><span data-stu-id="ac3ff-110">**Do you want to conference the security desk in on each emergency call?**</span></span>
  
<span data-ttu-id="ac3ff-111">緊急サービス サービス プロバイダーによってサポートされている場合は、場所ポリシーを構成して、各緊急電話にコールバック番号を含めできます。</span><span class="sxs-lookup"><span data-stu-id="ac3ff-111">If supported by the emergency services service provider, you can configure the location policy to include a callback number with each emergency call.</span></span> <span data-ttu-id="ac3ff-112">この番号は、プロバイダーが組織のセキュリティ担当者を緊急電話会議に参加するために使用します。</span><span class="sxs-lookup"><span data-stu-id="ac3ff-112">This number is then used by the provider to conference your organization's security personnel into emergency calls.</span></span> <span data-ttu-id="ac3ff-113">この会議は、場所ポリシーで一方向 (リッスンのみ) または双方向 (双方向) に構成できます。</span><span class="sxs-lookup"><span data-stu-id="ac3ff-113">This conferencing can be configured in the location policy to be one-way (listen-only) or two-way (bidirectional).</span></span>
    
> [!NOTE]
> <span data-ttu-id="ac3ff-114">必要に応じて、場所ポリシーごとに異なる緊急担当者を構成できます。</span><span class="sxs-lookup"><span data-stu-id="ac3ff-114">If desired, you can configure different emergency personnel for each location policy.</span></span> <span data-ttu-id="ac3ff-115">これにより、会社内の異なる領域の応答をカスタマイズしたり、ネットワークの外部ではなく内部から発信される緊急電話に対して異なる動作を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="ac3ff-115">This allows you to customize the response for different areas within your company, or create different behavior for emergency calls that originate from inside as opposed to outside the network.</span></span> <span data-ttu-id="ac3ff-116">配布グループを使用して、通知する担当者を指定できます。</span><span class="sxs-lookup"><span data-stu-id="ac3ff-116">You can use distribution groups to specify the personnel you want to notify.</span></span> 
  

