---
title: Skype for Business Server 2015 で手動で場所を取得する場合のユーザー エクスペリエンスの定義
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d37f67d3-e248-483b-b64c-3986559ef357
description: ビジネス サーバーのエンタープライズ VoIP の Skype で、SIP トランキング プロバイダーを使用して ~ 9-1-1 の展開でユーザーの移動を計画しています。
ms.openlocfilehash: 3e5c8776768212c6be179700a33261382949deee
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="define-the-user-experience-for-manually-acquiring-a-location-in-skype-for-business-server-2015"></a><span data-ttu-id="f02e1-103">Skype for Business Server 2015 で手動で場所を取得する場合のユーザー エクスペリエンスの定義</span><span class="sxs-lookup"><span data-stu-id="f02e1-103">Define the user experience for manually acquiring a location in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="f02e1-104">ビジネス サーバーのエンタープライズ VoIP の Skype で、SIP トランキング プロバイダーを使用して ~ 9-1-1 の展開でユーザーの移動を計画しています。</span><span class="sxs-lookup"><span data-stu-id="f02e1-104">Planning for roaming users in an E9-1-1 deployment using SIP trunking providers, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="f02e1-p101">クライアントがネットワークの外部にいる場合、または定義されていないサブネットにいる場合は、ユーザーは場所を手動で入力できます。ただし緊急通報の場合の通話は、緊急情報受信センター (PSAP) にルーティングされる前に、最初に国または地域の E9-1-1 Emergency Call Response Center (ECRC) のディスパッチャーにルーティングされます。ECRC は言葉で発信者に場所を問い合わせた後、提供された情報に基づいて、適切な PSAP に通話を転送します。</span><span class="sxs-lookup"><span data-stu-id="f02e1-p101">If a client is located outside the network, or in an undefined subnet, the user can manually enter a location. But during an emergency call, the call will first be routed to a national/regional E9-1-1 Emergency Call Response Center (ECRC) dispatcher before being routed to a Public Safety Answering Point (PSAP). The ECRC will verbally query the caller for a location and then forward the call to the appropriate PSAP, based on the information provided.</span></span> 
  
<span data-ttu-id="f02e1-108">**位置情報サービスによって自動的にパスワードがない場合は、場所を入力するユーザーが表示されるのででしょうか。**</span><span class="sxs-lookup"><span data-stu-id="f02e1-108">**Should users be prompted to enter a location when one is not automatically provided by the Location Information service?**</span></span>
  
<span data-ttu-id="f02e1-109">たとえば、クライアントが未定義のサブネット、自宅、ホテル、またはネットワーク外部のいずれかの場所に存在する場合は、ユーザーに場所の入力を求める必要があるでしょうか。</span><span class="sxs-lookup"><span data-stu-id="f02e1-109">For example, if a client is located in an undefined subnet, at home, in a hotel, or anywhere else outside the network, should the user be required to enter a location?</span></span>
    
<span data-ttu-id="f02e1-p102">場所ポリシーの [**場所の入力を求める**] 設定を構成し、クライアントの動作を定義できます。この値を [いいえ] に設定すると、ユーザーは場所の入力を求められません。この値を [はい] に設定すると、ユーザーは場所の入力を求められますが、入力せずにプロンプトを閉じることもできます。この値を [免責事項] に設定すると、ユーザーは場所の入力を求められ、入力せずにプロンプトを閉じようとすると免責事項が表示されます。すべての場合において、ユーザーは通常どおりクライアントを使用し続けることができます。</span><span class="sxs-lookup"><span data-stu-id="f02e1-p102">You can configure the **Location Required** setting in the location policy to define the client behavior. Setting this value to No means that the user will not be prompted for a location. Setting this value to Yes means that the user will be prompted for a location, but can dismiss the prompt. Setting this value to Disclaimer means that the user will be prompted for a location, and will be shown a disclaimer if they try to dismiss the prompt. In all cases, the user can continue to use the client as usual.</span></span>
    
<span data-ttu-id="f02e1-115">ユーザーは、場所を手動で入力、場所は、クライアントのネットワークのデフォルト ゲートウェイの MAC アドレスにマップされてし、クライアント上にあるユーザーごとのテーブルに格納されます。</span><span class="sxs-lookup"><span data-stu-id="f02e1-115">When a user manually enters a location, the location is mapped to the MAC address of the default gateway of the client's network, and is stored in a per-user table located on the client.</span></span> <span data-ttu-id="f02e1-116">ユーザーは、以前に保存された任意の場所に戻ると、ビジネス クライアント用の Skype が自動的に設定自体その場所にします。</span><span class="sxs-lookup"><span data-stu-id="f02e1-116">When the user returns to any previously stored location, the Skype for Business client automatically sets itself to that location.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="f02e1-117">、クライアントの現在の位置のみを変更することができますが、ローカルのユーザーのテーブルに格納されている任意の場所を削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="f02e1-117">You can modify only the current location of your client, but you can also delete any location stored in the local user's table.</span></span> 
  

