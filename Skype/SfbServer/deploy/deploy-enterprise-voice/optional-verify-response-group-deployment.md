---
title: 省略Skype for Business で応答グループの展開を確認する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 202ca4ab-8e6d-44a4-b7c8-071133074feb
description: Skype for Business Server Enterprise Voice で、応答グループの展開が成功したことを確認します。
ms.openlocfilehash: e80328c2f14db4b7c9633509e36832966af5ca34
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767310"
---
# <a name="optional-verify-response-group-deployment-in-skype-for-business"></a><span data-ttu-id="1d62e-103">省略Skype for Business で応答グループの展開を確認する</span><span class="sxs-lookup"><span data-stu-id="1d62e-103">(Optional) Verify Response Group deployment in Skype for Business</span></span>
 
<span data-ttu-id="1d62e-104">Skype for Business Server Enterprise Voice で、応答グループの展開が成功したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="1d62e-104">Verify your Response Group deployment success, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="1d62e-105">応答グループを構成したら、応答グループが期待どおりに動作するように構成を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1d62e-105">After you configure Response Group, you need to verify the configuration to make sure your response groups work as expected.</span></span> <span data-ttu-id="1d62e-106">少なくとも、次の種類のユーザーを使用して以下のシナリオを検証してください。</span><span class="sxs-lookup"><span data-stu-id="1d62e-106">At minimum, verify the following scenarios by using the following types of users:</span></span>
  
 <span data-ttu-id="1d62e-107">**ユーザー**</span><span class="sxs-lookup"><span data-stu-id="1d62e-107">**Users**</span></span>
  
- <span data-ttu-id="1d62e-108">Skype for Business をホームとしているユーザー</span><span class="sxs-lookup"><span data-stu-id="1d62e-108">A user who is homed on Skype for Business</span></span>
    
- <span data-ttu-id="1d62e-109">公衆交換電話網 (PSTN) を使用する外部ユーザー</span><span class="sxs-lookup"><span data-stu-id="1d62e-109">An external user who uses the public switched telephone network (PSTN)</span></span>
    
- <span data-ttu-id="1d62e-110">Skype for Business をホームとしているエージェント</span><span class="sxs-lookup"><span data-stu-id="1d62e-110">An agent who is homed on Skype for Business</span></span>
    
  <span data-ttu-id="1d62e-111">**シナリオ**</span><span class="sxs-lookup"><span data-stu-id="1d62e-111">**Scenarios**</span></span>
  
- <span data-ttu-id="1d62e-112">Skype for Business ユーザーが応答グループを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="1d62e-112">The Skype for Business user calls the response group.</span></span>
    
- <span data-ttu-id="1d62e-113">外部ユーザーが応答グループを呼び出す。</span><span class="sxs-lookup"><span data-stu-id="1d62e-113">The external user calls the response group.</span></span>
    
- <span data-ttu-id="1d62e-114">エージェントが別の通話に応答しているときにユーザーが応答グループを呼び出し、キューに入る。</span><span class="sxs-lookup"><span data-stu-id="1d62e-114">A user calls the response group while the agent is on another call and goes to the queue.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1d62e-115">応答グループが予期したとおりに機能しない場合は、次のリンクを確認してください:https://support.office.com/en-us/article/troubleshooting-for-response-groups-ca72d8f8-4054-4974-b832-4f173611bd89</span><span class="sxs-lookup"><span data-stu-id="1d62e-115">If the response group does not work as expected please check next link: https://support.office.com/en-us/article/troubleshooting-for-response-groups-ca72d8f8-4054-4974-b832-4f173611bd89</span></span>
    

