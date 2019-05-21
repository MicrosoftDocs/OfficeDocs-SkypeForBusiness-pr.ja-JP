---
title: 省略Skype for Business のコールパークの展開を確認する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
description: Skype for Business Server Enterprise Voice でのコールパークの展開を確認します。
ms.openlocfilehash: 94d230491c0207c05016545de3c45cf0582ca496
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34292844"
---
# <a name="optional-verify-call-park-deployment-in-skype-for-business"></a><span data-ttu-id="ceb3f-103">省略Skype for Business のコールパークの展開を確認する</span><span class="sxs-lookup"><span data-stu-id="ceb3f-103">(Optional) Verify Call Park deployment in Skype for Business</span></span>
 
<span data-ttu-id="ceb3f-104">Skype for Business Server Enterprise Voice でのコールパークの展開を確認します。</span><span class="sxs-lookup"><span data-stu-id="ceb3f-104">Verifying your deployment of Call Park in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="ceb3f-105">コールパークのインストールと構成が完了したら、構成を確認して、パーキングと着信の取得が期待どおりに動作することを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ceb3f-105">After you install and configure Call Park, you need to verify the configuration to make sure that parking and retrieving calls works as expected.</span></span> <span data-ttu-id="ceb3f-106">少なくとも、以下を確認してください。</span><span class="sxs-lookup"><span data-stu-id="ceb3f-106">At minimum, verify the following:</span></span>
  
- <span data-ttu-id="ceb3f-107">コールパークが有効になっていて、ユーザが通話をパークしているユーザに電話をかけます。</span><span class="sxs-lookup"><span data-stu-id="ceb3f-107">Call a user who has Call Park enabled and have the user park the call.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ceb3f-108">このテストを実行する前に、音声ポリシーでコールパークを有効にしている場合は、その通話を保留にしているユーザーが Skype for Business からサインアウトしてから、もう一度サインインすると、[着信の転送] リストの [通話パーク] オプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ceb3f-108">If you enabled Call Park in voice policy just before performing this test, the user who is parking the call needs to sign out of Skype for Business, and then sign back in, to be able to see the Call Park option in the transfer call list.</span></span> 
  
- <span data-ttu-id="ceb3f-109">オービット番号をダイヤルして、電話を取ります。</span><span class="sxs-lookup"><span data-stu-id="ceb3f-109">Dial the orbit number to retrieve the call.</span></span>
    
- <span data-ttu-id="ceb3f-p102">別の通話を保留して、保留した通話がタイムアウトするようにして、リングバックは取らないようにします。タイムアウトした通話が **OnTimeoutURI** で指定されているフォールバック宛先に正しくルーティングされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ceb3f-p102">Park another call, let the parked call time out, and do not pick up the ringback. Verify that the timed-out call is correctly routed to the fallback destination that is specified for **OnTimeoutURI**.</span></span>
    

