---
title: Skype for Business Server で場所を手動で取得するためのユーザーエクスペリエンスを定義する
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
ms.assetid: d37f67d3-e248-483b-b64c-3986559ef357
description: Skype for Business Server Enterprise Voice での SIP トランクプロバイダーを使用した E9 展開でのローミングユーザーの計画。
ms.openlocfilehash: 221c123c9630996d487644d0f5358b95d65fe1a6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276720"
---
# <a name="define-the-user-experience-for-manually-acquiring-a-location-in-skype-for-business-server"></a><span data-ttu-id="10984-103">Skype for Business Server で場所を手動で取得するためのユーザーエクスペリエンスを定義する</span><span class="sxs-lookup"><span data-stu-id="10984-103">Define the user experience for manually acquiring a location in Skype for Business Server</span></span>
 
<span data-ttu-id="10984-104">Skype for Business Server Enterprise Voice での SIP トランクプロバイダーを使用した E9 展開でのローミングユーザーの計画。</span><span class="sxs-lookup"><span data-stu-id="10984-104">Planning for roaming users in an E9-1-1 deployment using SIP trunking providers, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="10984-p101">クライアントがネットワークの外部にいる場合、または定義されていないサブネットにいる場合は、ユーザーは場所を手動で入力できます。ただし緊急通報の場合の通話は、緊急情報受信センター (PSAP) にルーティングされる前に、最初に国または地域の E9-1-1 Emergency Call Response Center (ECRC) のディスパッチャーにルーティングされます。ECRC は言葉で発信者に場所を問い合わせた後、提供された情報に基づいて、適切な PSAP に通話を転送します。</span><span class="sxs-lookup"><span data-stu-id="10984-p101">If a client is located outside the network, or in an undefined subnet, the user can manually enter a location. But during an emergency call, the call will first be routed to a national/regional E9-1-1 Emergency Call Response Center (ECRC) dispatcher before being routed to a Public Safety Answering Point (PSAP). The ECRC will verbally query the caller for a location and then forward the call to the appropriate PSAP, based on the information provided.</span></span> 
  
<span data-ttu-id="10984-108">**場所情報サービスによって自動的に指定されていない場合に、場所の入力を求めるメッセージが表示されるようにしますか?**</span><span class="sxs-lookup"><span data-stu-id="10984-108">**Should users be prompted to enter a location when one is not automatically provided by the Location Information service?**</span></span>
  
<span data-ttu-id="10984-109">たとえば、クライアントが未定義のサブネット、自宅、ホテル、またはネットワーク外部のいずれかの場所に存在する場合は、ユーザーに場所の入力を求める必要があるでしょうか。</span><span class="sxs-lookup"><span data-stu-id="10984-109">For example, if a client is located in an undefined subnet, at home, in a hotel, or anywhere else outside the network, should the user be required to enter a location?</span></span>
    
<span data-ttu-id="10984-p102">場所ポリシーの [**場所の入力を求める**] 設定を構成し、クライアントの動作を定義できます。この値を [いいえ] に設定すると、ユーザーは場所の入力を求められません。この値を [はい] に設定すると、ユーザーは場所の入力を求められますが、入力せずにプロンプトを閉じることもできます。この値を [免責事項] に設定すると、ユーザーは場所の入力を求められ、入力せずにプロンプトを閉じようとすると免責事項が表示されます。すべての場合において、ユーザーは通常どおりクライアントを使用し続けることができます。</span><span class="sxs-lookup"><span data-stu-id="10984-p102">You can configure the **Location Required** setting in the location policy to define the client behavior. Setting this value to No means that the user will not be prompted for a location. Setting this value to Yes means that the user will be prompted for a location, but can dismiss the prompt. Setting this value to Disclaimer means that the user will be prompted for a location, and will be shown a disclaimer if they try to dismiss the prompt. In all cases, the user can continue to use the client as usual.</span></span>
    
<span data-ttu-id="10984-115">ユーザーが手動で場所を入力すると、その場所はクライアントのネットワークの既定のゲートウェイの MAC アドレスにマップされ、クライアント上のユーザーごとのテーブルに格納されます。</span><span class="sxs-lookup"><span data-stu-id="10984-115">When a user manually enters a location, the location is mapped to the MAC address of the default gateway of the client's network, and is stored in a per-user table located on the client.</span></span> <span data-ttu-id="10984-116">ユーザーが既に保存されている場所に戻ると、Skype for Business クライアントは自動的にその場所に設定します。</span><span class="sxs-lookup"><span data-stu-id="10984-116">When the user returns to any previously stored location, the Skype for Business client automatically sets itself to that location.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="10984-117">クライアントの現在の場所のみを変更できますが、ローカルユーザーのテーブルに格納されている任意の場所を削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="10984-117">You can modify only the current location of your client, but you can also delete any location stored in the local user's table.</span></span> 
  

