---
title: (省略可能)ビジネス用の Skype のコール パーク展開を確認します。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
description: ビジネス サーバーのエンタープライズ VoIP の Skype のコール パークの展開を確認しています。
ms.openlocfilehash: da53d351acef3eb2fc7fcc1b59e24a83d0cb2495
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894669"
---
# <a name="optional-verify-call-park-deployment-in-skype-for-business"></a><span data-ttu-id="65576-103">(省略可能)ビジネス用の Skype のコール パーク展開を確認します。</span><span class="sxs-lookup"><span data-stu-id="65576-103">(Optional) Verify Call Park deployment in Skype for Business</span></span>
 
<span data-ttu-id="65576-104">ビジネス サーバーのエンタープライズ VoIP の Skype のコール パークの展開を確認しています。</span><span class="sxs-lookup"><span data-stu-id="65576-104">Verifying your deployment of Call Park in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="65576-105">インストールし、コール パークを構成した後は、駐車場との呼び出しを取得するが、期待どおりに動作するかどうかを確認する構成を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="65576-105">After you install and configure Call Park, you need to verify the configuration to make sure that parking and retrieving calls works as expected.</span></span> <span data-ttu-id="65576-106">少なくとも、以下を確認してください。</span><span class="sxs-lookup"><span data-stu-id="65576-106">At minimum, verify the following:</span></span>
  
- <span data-ttu-id="65576-107">コール パークを有効になっているを持つユーザーを呼び出すし、ユーザーの公園の呼び出しがあります。</span><span class="sxs-lookup"><span data-stu-id="65576-107">Call a user who has Call Park enabled and have the user park the call.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="65576-108">音声ポリシーでコール パークを有効に、このテストを実行する前に、ビジネス用の Skype からサインアウトして、再度サインイン、通話リストの転送では、コール パーク オプションを表示することができるようにする呼び出しは、駐車場ユーザー必要があります。</span><span class="sxs-lookup"><span data-stu-id="65576-108">If you enabled Call Park in voice policy just before performing this test, the user who is parking the call needs to sign out of Skype for Business, and then sign back in, to be able to see the Call Park option in the transfer call list.</span></span> 
  
- <span data-ttu-id="65576-109">オービット番号をダイヤルして、電話を取ります。</span><span class="sxs-lookup"><span data-stu-id="65576-109">Dial the orbit number to retrieve the call.</span></span>
    
- <span data-ttu-id="65576-p102">別の通話を保留して、保留した通話がタイムアウトするようにして、リングバックは取らないようにします。タイムアウトした通話が **OnTimeoutURI** で指定されているフォールバック宛先に正しくルーティングされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="65576-p102">Park another call, let the parked call time out, and do not pick up the ringback. Verify that the timed-out call is correctly routed to the fallback destination that is specified for **OnTimeoutURI**.</span></span>
    

