---
title: (省略可能)Skype for Business でのコール パーク展開の確認
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
description: Skype for Business Server エンタープライズ VoIP でのコール パークの展開のエンタープライズ VoIP。
ms.openlocfilehash: a7edb9f47610bf7cdae068ca789670ab4048bb9c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830897"
---
# <a name="optional-verify-call-park-deployment-in-skype-for-business"></a><span data-ttu-id="302a4-103">(省略可能)Skype for Business でのコール パーク展開の確認</span><span class="sxs-lookup"><span data-stu-id="302a4-103">(Optional) Verify Call Park deployment in Skype for Business</span></span>
 
<span data-ttu-id="302a4-104">Skype for Business Server サービスでのコール パークの展開エンタープライズ VoIP。</span><span class="sxs-lookup"><span data-stu-id="302a4-104">Verifying your deployment of Call Park in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="302a4-105">コール パークをインストールして構成した後、構成を確認して、通話のパークと取得が期待通り動作する必要があります。</span><span class="sxs-lookup"><span data-stu-id="302a4-105">After you install and configure Call Park, you need to verify the configuration to make sure that parking and retrieving calls works as expected.</span></span> <span data-ttu-id="302a4-106">少なくとも、以下を確認してください。</span><span class="sxs-lookup"><span data-stu-id="302a4-106">At minimum, verify the following:</span></span>
  
- <span data-ttu-id="302a4-107">コール パークが有効になっているユーザーを呼び出し、そのユーザーに通話をパークします。</span><span class="sxs-lookup"><span data-stu-id="302a4-107">Call a user who has Call Park enabled and have the user park the call.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="302a4-108">このテストを実行する直前に音声ポリシーでコール パークを有効にした場合、通話をパークしているユーザーは、転送通話リストにコール パーク オプションを表示するために、Skype for Business からサインアウトしてからサインインし戻す必要があります。</span><span class="sxs-lookup"><span data-stu-id="302a4-108">If you enabled Call Park in voice policy just before performing this test, the user who is parking the call needs to sign out of Skype for Business, and then sign back in, to be able to see the Call Park option in the transfer call list.</span></span> 
  
- <span data-ttu-id="302a4-109">オービット番号をダイヤルして、電話を取ります。</span><span class="sxs-lookup"><span data-stu-id="302a4-109">Dial the orbit number to retrieve the call.</span></span>
    
- <span data-ttu-id="302a4-p102">別の通話を保留して、保留した通話がタイムアウトするようにして、リングバックは取らないようにします。タイムアウトした通話が **OnTimeoutURI** で指定されているフォールバック宛先に正しくルーティングされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="302a4-p102">Park another call, let the parked call time out, and do not pick up the ringback. Verify that the timed-out call is correctly routed to the fallback destination that is specified for **OnTimeoutURI**.</span></span>
    

