---
title: XMPP ゲートウェイ アクセス ポリシーおよび証明書の構成
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: XMPP フェデレーションでは、拡張可能なメッセージングおよびプレゼンス プロトコル (XMPP) に基づいて、外部の配置を定義します。 XMPP は、の構成には、XMPP ドメイン ユーザーへのユーザー アクセスができます。
ms.openlocfilehash: 65ef8904660eaa75ddd10238a6561ea91b9f7278
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32238662"
---
# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a><span data-ttu-id="63842-104">XMPP ゲートウェイ アクセス ポリシーおよび証明書の構成</span><span class="sxs-lookup"><span data-stu-id="63842-104">Configure XMPP gateway access policies and certificates</span></span>

<span data-ttu-id="63842-105">XMPP フェデレーションでは、拡張可能なメッセージングおよびプレゼンス プロトコル (XMPP) に基づいて、外部の配置を定義します。</span><span class="sxs-lookup"><span data-stu-id="63842-105">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol (XMPP).</span></span> <span data-ttu-id="63842-106">XMPP は、の構成には、XMPP ドメイン ユーザーへのユーザー アクセスができます。</span><span class="sxs-lookup"><span data-stu-id="63842-106">An XMPP configuration allows users access to XMPP domain users by:</span></span>
  
- <span data-ttu-id="63842-107">IM とプレゼンスのユーザのみ</span><span class="sxs-lookup"><span data-stu-id="63842-107">IM and Presence - person to person only</span></span>
    
- <span data-ttu-id="63842-108">作成の XMPP フェデレーションのクライアントのビジネスの Skype の連絡先</span><span class="sxs-lookup"><span data-stu-id="63842-108">Creation of XMPP federated contacts in the Skype for Business client</span></span>
    
<span data-ttu-id="63842-109">構成するときは、XMPP をサポートするためのポリシーはフェデレーション パートナーしますが、XMPP のフェデレーション ドメインのユーザーにポリシーを適用しないセッション開始プロトコル (SIP) のユーザーがインスタント メッセージング (IM) サービスのプロバイダー、または SIP フェデレーション ドメイン。</span><span class="sxs-lookup"><span data-stu-id="63842-109">When you configure policies for support of XMPP federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers, or SIP federated domains.</span></span> <span data-ttu-id="63842-110">XMPP フェデレーション ドメインごと、ユーザーが連絡先を追加するとの通信を許可するために、XMPP フェデレーション パートナーを構成するとします。</span><span class="sxs-lookup"><span data-stu-id="63842-110">You configure an XMPP federated partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="63842-111">場所のポリシーが表示されたら、XMPP ゲートウェイ証明書を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="63842-111">Once the policies are in place, you need to configure the XMPP Gateway certificates.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="63842-112">XMPP の機能は、ビジネス サーバー 2019、Skype では非推奨ですが、ビジネス サーバー 2019 の Skype との共存のレガシー サーバーで継続することができます。</span><span class="sxs-lookup"><span data-stu-id="63842-112">XMPP functionality is deprecated in Skype for Business Server 2019, but can be continued in a legacy server in coexistence with Skype for Business Server 2019.</span></span> <span data-ttu-id="63842-113">レガシ サーバーを既に展開しているかどうかを確認 (ビジネス サーバー 2015 の Skype と Lync Server 2013) XMPP ゲートウェイでは、従来の XMPP ゲートウェイに対してユーザーを有効にするアクセス ポリシーを構成し、。</span><span class="sxs-lookup"><span data-stu-id="63842-113">Make sure you have already deployed the legacy server (Skype for Business Server 2015 / Lync Server 2013) XMPP Gateway, and configured the access policies to enable users for legacy XMPP Gateway.</span></span> <span data-ttu-id="63842-114">詳細については、 [XMPP フェデレーションの移行](migrating-xmpp-federation.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63842-114">For details, see [Migrating XMPP Federation](migrating-xmpp-federation.md).</span></span> 
  
### <a name="configure-an-external-access-policy-to-enable-users-for-legacy-xmpp-gateway"></a><span data-ttu-id="63842-115">従来の XMPP ゲートウェイの外部アクセス ポリシーを有効にするユーザーを構成します。</span><span class="sxs-lookup"><span data-stu-id="63842-115">Configure an External Access Policy to Enable Users for legacy XMPP Gateway</span></span>

1. <span data-ttu-id="63842-116">ビジネス サーバーのコントロール パネルの従来の Skype を開きます。</span><span class="sxs-lookup"><span data-stu-id="63842-116">Open the legacy Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="63842-117">左側のナビゲーション ・ バーで [**フェデレーションと外部アクセス**、および**外部アクセス ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63842-117">In the left navigation bar, click **Federation and External Access**, and then click **External Access Policy**.</span></span>
    
3. <span data-ttu-id="63842-118">[**新規**] をクリックし、[**ユーザー ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63842-118">Click **New**, and then click **User policy**.</span></span>
    
4. <span data-ttu-id="63842-119">外部アクセスのユーザー ポリシーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="63842-119">Enter a name for the external access user policy.</span></span>
    
5. <span data-ttu-id="63842-120">外部アクセスのユーザー ポリシーの説明を提供します。</span><span class="sxs-lookup"><span data-stu-id="63842-120">Provide a description for external access user policy.</span></span>
    
6. <span data-ttu-id="63842-121">**フェデレーション ユーザーとの通信を有効にする**を選択します。</span><span class="sxs-lookup"><span data-stu-id="63842-121">Select **Enable communications with federated users**.</span></span>
    
7. <span data-ttu-id="63842-122">**XMPP と通信を有効にするフェデレーション ユーザー**を選択します。</span><span class="sxs-lookup"><span data-stu-id="63842-122">Select **Enable communications with XMPP federated users**.</span></span>
    
8. <span data-ttu-id="63842-123">**コミット**をサイトまたはユーザーのポリシーに変更を保存する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63842-123">Click **Commit** to save your changes to the site or user policy.</span></span> 
    

