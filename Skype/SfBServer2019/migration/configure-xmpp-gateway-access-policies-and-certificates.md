---
title: XMPP ゲートウェイ アクセス ポリシーおよび証明書の構成
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: XMPP フェデレーションは、XMPP (eXtensible Messaging and Presence Protocol) に基づいて外部展開を定義します。 XMPP 構成を使用すると、ユーザーは次の方法で XMPP ドメインユーザーにアクセスできます。
ms.openlocfilehash: f94cd3bc0a769165f6ffe8ecabea8b7f48a1ff07
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753937"
---
# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a><span data-ttu-id="885b9-104">XMPP ゲートウェイ アクセス ポリシーおよび証明書の構成</span><span class="sxs-lookup"><span data-stu-id="885b9-104">Configure XMPP gateway access policies and certificates</span></span>

<span data-ttu-id="885b9-105">XMPP フェデレーションは、XMPP (eXtensible Messaging and Presence Protocol) に基づいて外部展開を定義します。</span><span class="sxs-lookup"><span data-stu-id="885b9-105">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol (XMPP).</span></span> <span data-ttu-id="885b9-106">XMPP 構成を使用すると、ユーザーは次の方法で XMPP ドメインユーザーにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="885b9-106">An XMPP configuration allows users access to XMPP domain users by:</span></span>
  
- <span data-ttu-id="885b9-107">IM とプレゼンス-ユーザーからのみ</span><span class="sxs-lookup"><span data-stu-id="885b9-107">IM and Presence - person to person only</span></span>
    
- <span data-ttu-id="885b9-108">Skype for Business クライアントでの XMPP フェデレーション連絡先の作成</span><span class="sxs-lookup"><span data-stu-id="885b9-108">Creation of XMPP federated contacts in the Skype for Business client</span></span>
    
<span data-ttu-id="885b9-109">XMPP フェデレーションパートナーのサポートのためのポリシーを構成する場合、ポリシーは XMPP フェデレーションドメインのユーザーに適用されますが、セッション開始プロトコル (SIP) インスタントメッセージング (IM) サービスプロバイダーまたは SIP フェデレーションドメインのユーザーには適用されません。</span><span class="sxs-lookup"><span data-stu-id="885b9-109">When you configure policies for support of XMPP federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers, or SIP federated domains.</span></span> <span data-ttu-id="885b9-110">ユーザーが連絡先を追加して通信できるようにする XMPP フェデレーションドメインごとに XMPP フェデレーションパートナーを構成します。</span><span class="sxs-lookup"><span data-stu-id="885b9-110">You configure an XMPP federated partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="885b9-111">ポリシーを設定したら、XMPP ゲートウェイ証明書を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="885b9-111">Once the policies are in place, you need to configure the XMPP Gateway certificates.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="885b9-112">XMPP 機能は、Skype for Business Server 2019 では廃止されましたが、従来のサーバーで Skype for business Server 2019 と共存させることができます。</span><span class="sxs-lookup"><span data-stu-id="885b9-112">XMPP functionality is deprecated in Skype for Business Server 2019, but can be continued in a legacy server in coexistence with Skype for Business Server 2019.</span></span> <span data-ttu-id="885b9-113">従来のサーバー (Skype for Business Server 2015/Lync Server 2013) XMPP ゲートウェイを既に展開していること、および従来の XMPP ゲートウェイをユーザーが使用できるようにアクセスポリシーを構成していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="885b9-113">Make sure you have already deployed the legacy server (Skype for Business Server 2015 / Lync Server 2013) XMPP Gateway, and configured the access policies to enable users for legacy XMPP Gateway.</span></span> <span data-ttu-id="885b9-114">詳細については、「 [XMPP フェデレーションを移行](migrating-xmpp-federation.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="885b9-114">For details, see [Migrating XMPP Federation](migrating-xmpp-federation.md).</span></span> 
  
### <a name="configure-an-external-access-policy-to-enable-users-for-legacy-xmpp-gateway"></a><span data-ttu-id="885b9-115">従来の XMPP ゲートウェイでユーザーを有効にするための外部アクセスポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="885b9-115">Configure an External Access Policy to Enable Users for legacy XMPP Gateway</span></span>

1. <span data-ttu-id="885b9-116">従来の Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="885b9-116">Open the legacy Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="885b9-117">左側のナビゲーション バーで [**フェデレーションと外部アクセス**] をクリックし、[**外部アクセス ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="885b9-117">In the left navigation bar, click **Federation and External Access**, and then click **External Access Policy**.</span></span>
    
3. <span data-ttu-id="885b9-118">[**新規**] をクリックし、[**ユーザー ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="885b9-118">Click **New**, and then click **User policy**.</span></span>
    
4. <span data-ttu-id="885b9-119">外部アクセス ユーザー ポリシーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="885b9-119">Enter a name for the external access user policy.</span></span>
    
5. <span data-ttu-id="885b9-120">外部アクセス ユーザー ポリシーの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="885b9-120">Provide a description for external access user policy.</span></span>
    
6. <span data-ttu-id="885b9-121">[**フェデレーション ユーザーとの通信を有効にする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="885b9-121">Select **Enable communications with federated users**.</span></span>
    
7. <span data-ttu-id="885b9-122">[**XMPP フェデレーション ユーザーとの通信を有効にする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="885b9-122">Select **Enable communications with XMPP federated users**.</span></span>
    
8. <span data-ttu-id="885b9-123">[**確定**] をクリックして、サイトまたはユーザー ポリシーへの変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="885b9-123">Click **Commit** to save your changes to the site or user policy.</span></span> 
    

