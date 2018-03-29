---
title: (オプション) Skype for Business 2015 でのコール パーク展開の確認
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
description: ビジネス サーバーのエンタープライズ VoIP の Skype のコール パークの展開を確認しています。
ms.openlocfilehash: e8b3b0abd06ab8dc69bbe1fbcc5f091dd1350966
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="optional-verify-call-park-deployment-in-skype-for-business-2015"></a><span data-ttu-id="3e9fb-103">(オプション) Skype for Business 2015 でのコール パーク展開の確認</span><span class="sxs-lookup"><span data-stu-id="3e9fb-103">(Optional) Verify Call Park deployment in Skype for Business 2015</span></span>
 
<span data-ttu-id="3e9fb-104">ビジネス サーバーのエンタープライズ VoIP の Skype のコール パークの展開を確認しています。</span><span class="sxs-lookup"><span data-stu-id="3e9fb-104">Verifying your deployment of Call Park in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="3e9fb-105">インストールし、コール パークを構成した後は、駐車場との呼び出しを取得するが、期待どおりに動作するかどうかを確認する構成を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e9fb-105">After you install and configure Call Park, you need to verify the configuration to make sure that parking and retrieving calls works as expected.</span></span> <span data-ttu-id="3e9fb-106">少なくとも、以下を確認してください。</span><span class="sxs-lookup"><span data-stu-id="3e9fb-106">At minimum, verify the following:</span></span>
  
- <span data-ttu-id="3e9fb-107">コール パークを有効になっているを持つユーザーを呼び出すし、ユーザーの公園の呼び出しがあります。</span><span class="sxs-lookup"><span data-stu-id="3e9fb-107">Call a user who has Call Park enabled and have the user park the call.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3e9fb-108">音声ポリシーでコール パークを有効に、このテストを実行する前に、ビジネス用の Skype からサインアウトして、再度サインイン、通話リストの転送では、コール パーク オプションを表示することができるようにする呼び出しは、駐車場ユーザー必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e9fb-108">If you enabled Call Park in voice policy just before performing this test, the user who is parking the call needs to sign out of Skype for Business, and then sign back in, to be able to see the Call Park option in the transfer call list.</span></span> 
  
- <span data-ttu-id="3e9fb-109">オービット番号をダイヤルして、電話を取ります。</span><span class="sxs-lookup"><span data-stu-id="3e9fb-109">Dial the orbit number to retrieve the call.</span></span>
    
- <span data-ttu-id="3e9fb-p102">別の通話を保留して、保留した通話がタイムアウトするようにして、リングバックは取らないようにします。タイムアウトした通話が **OnTimeoutURI** で指定されているフォールバック宛先に正しくルーティングされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3e9fb-p102">Park another call, let the parked call time out, and do not pick up the ringback. Verify that the timed-out call is correctly routed to the fallback destination that is specified for **OnTimeoutURI**.</span></span>
    

