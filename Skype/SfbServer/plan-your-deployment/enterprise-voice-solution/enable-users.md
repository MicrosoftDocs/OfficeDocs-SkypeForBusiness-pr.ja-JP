---
title: ~ 9-1-1 では、Skype のビジネス サーバーに対してユーザーを有効にします。
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
description: 決定を下す ~ 9-1-1 展開の Skype での場所のポリシーに必要なビジネス サーバー エンタープライズ VoIP を有効にするには、どのユーザーも含めて、移動ユーザーをサポートする方法です。
ms.openlocfilehash: 57a84d18bec0547f1179e62013c9b957afdd2c53
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879308"
---
# <a name="enable-users-for-e9-1-1-in-skype-for-business-server"></a><span data-ttu-id="71e50-103">~ 9-1-1 では、Skype のビジネス サーバーに対してユーザーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="71e50-103">Enable users for E9-1-1 in Skype for Business Server</span></span>
 
<span data-ttu-id="71e50-104">決定を下す ~ 9-1-1 展開の Skype での場所のポリシーに必要なビジネス サーバー エンタープライズ VoIP を有効にするには、どのユーザーも含めて、移動ユーザーをサポートする方法です。</span><span class="sxs-lookup"><span data-stu-id="71e50-104">Decisions necessary for the location policy for an E9-1-1 deployment in Skype for Business Server Enterprise Voice, including which users to enable and how to support roaming users.</span></span>
  
<span data-ttu-id="71e50-105">クライアント登録の際に、Skype ビジネス サーバーは、エンタープライズ VoIP が有効なユーザー ~ 9-1-1 のプロパティを構成するのに場所のポリシーを使用します。</span><span class="sxs-lookup"><span data-stu-id="71e50-105">During client registration, Skype for Business Server uses a location policy to configure the E9-1-1 properties for Enterprise Voice-enabled users.</span></span> <span data-ttu-id="71e50-106">このポリシーには、E9-1-1 の実装方法を定義する設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="71e50-106">This policy contains the settings that define how E9-1-1 is implemented.</span></span> <span data-ttu-id="71e50-107">などの場所のポリシーには、緊急ダイヤル文字列の場合は、自動的に位置情報サービスの場所を手動で入力する必要があるかどうかのいずれかの提供など、情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="71e50-107">For example, the location policy contains information such as the emergency dial string, and whether or not a user is required to manually enter a location if the Location Information service does not automatically provide one.</span></span> <span data-ttu-id="71e50-108">場所ポリシーの完全な定義は、「 [Skype ビジネス サーバーの場所のポリシーを計画する](location-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71e50-108">For a complete definition of a location policy, see [Plan location policies for Skype for Business Server](location-policies.md).</span></span>
  
<span data-ttu-id="71e50-109">Skype ビジネス サーバーはサブネットに基づいてクライアントまたはユーザーに基づいて、グローバルの場所のポリシーを割り当てることができます、サイトごとまたはユーザーごとのポリシーです。</span><span class="sxs-lookup"><span data-stu-id="71e50-109">Skype for Business Server can assign a location policy to clients based on subnet, or to users based on a global, per-site, or per-user policy.</span></span> <span data-ttu-id="71e50-110">ユーザーを有効にする方法を決定するには、まず、次の情報を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="71e50-110">To help decide how you will enable users, you should first answer the following questions.</span></span>
  
 <span data-ttu-id="71e50-111">**すべてのユーザーを有効にするか、またはエンタープライズの特定の地理的領域にサポートを限定するか。**</span><span class="sxs-lookup"><span data-stu-id="71e50-111">**Do you plan to enable all users, or limit support to specific geographic areas of the enterprise?**</span></span>
  
> <span data-ttu-id="71e50-112">グローバルな場所ポリシーを使用することで、エンタープライズ内のすべてのユーザーに場所を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="71e50-112">You can assign a location to all users in your enterprise by using a global location policy.</span></span> <span data-ttu-id="71e50-113">ただし、ビジネス サーバー ネットワークのサイトの Skype に場所のポリシーを割り当てることと、サブネットをサイトに追加する、エンタープライズ内で選択したロケーションに ~ 9-1-1 のサポートの対象としてサイトごとの ~ 9-1-1 のルーティング動作を指定できます。</span><span class="sxs-lookup"><span data-stu-id="71e50-113">However, by assigning a location policy to a Skype for Business Server network site and then adding subnets to the site, you can limit E9-1-1 support to selected locations within the enterprise and specify E9-1-1 routing behavior on a per-site basis.</span></span> 
    
 <span data-ttu-id="71e50-114">**ユーザー ポリシーを使用して個々のユーザーを有効にするか。**</span><span class="sxs-lookup"><span data-stu-id="71e50-114">**Do you plan to enable individual users through a user policy?**</span></span>
  
> <span data-ttu-id="71e50-115">E9-1-1 サポートをカスタマイズする必要がある場合は、場所ポリシーを特定のユーザーまたは共通領域電話の連絡先オブジェクトに直接割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="71e50-115">You can assign location policies directly to specific users or common area phone contact objects if you want to customize their E9-1-1 support.</span></span>
    
 <span data-ttu-id="71e50-116">**クライアントがネットワーク外を移動している場合、または定義されていないサブネットから接続されている場合、そのクライアントでも E9-1-1 を有効にするか。**</span><span class="sxs-lookup"><span data-stu-id="71e50-116">**When clients roam outside the network or connect from an undefined subnet, should the clients still be enabled for E9-1-1?**</span></span>
  
> <span data-ttu-id="71e50-117">ユーザーは、グローバルに割り当てられている場合、は、以下のサイト、またはユーザーごとの場所のポリシーをクライアントがない場合に定義されたサブネット内にあるまたは場所が見つかりませんでした、位置情報サービスでは、クライアントに場所を手動で入力するために必要です。</span><span class="sxs-lookup"><span data-stu-id="71e50-117">If users are assigned a global, site, or per-user location policy, they can be required to manually enter a location into the client if the client is not located within a defined subnet or no location has been found by the Location Information service.</span></span> <span data-ttu-id="71e50-118">詳細については、 [Skype のビジネス サーバー内の場所を手動で取得するためのユーザー エクスペリエンスを定義する](manually-acquiring-a-location.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71e50-118">For details, see [Define the user experience for manually acquiring a location in Skype for Business Server](manually-acquiring-a-location.md).</span></span>
    

