---
title: XMPP ゲートウェイ アクセス ポリシーおよび証明書の構成
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: XMPP フェデレーションは、拡張メッセージングとプレゼンスプロトコル (XMPP) に基づいて外部展開を定義します。 XMPP の構成では、ユーザーは次の方法で XMPP ドメインユーザーにアクセスできます。
ms.openlocfilehash: 01adcbe06718068e84844f704858e04198b197b2
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239292"
---
# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a><span data-ttu-id="89d0c-104">XMPP ゲートウェイ アクセス ポリシーおよび証明書の構成</span><span class="sxs-lookup"><span data-stu-id="89d0c-104">Configure XMPP gateway access policies and certificates</span></span>

<span data-ttu-id="89d0c-105">XMPP フェデレーションは、拡張メッセージングとプレゼンスプロトコル (XMPP) に基づいて外部展開を定義します。</span><span class="sxs-lookup"><span data-stu-id="89d0c-105">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol (XMPP).</span></span> <span data-ttu-id="89d0c-106">XMPP の構成では、ユーザーは次の方法で XMPP ドメインユーザーにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="89d0c-106">An XMPP configuration allows users access to XMPP domain users by:</span></span>
  
- <span data-ttu-id="89d0c-107">IM とプレゼンス-相手からのみ</span><span class="sxs-lookup"><span data-stu-id="89d0c-107">IM and Presence - person to person only</span></span>
    
- <span data-ttu-id="89d0c-108">Skype for Business クライアントでの XMPP フェデレーション連絡先の作成</span><span class="sxs-lookup"><span data-stu-id="89d0c-108">Creation of XMPP federated contacts in the Skype for Business client</span></span>
    
<span data-ttu-id="89d0c-109">XMPP フェデレーションパートナーのサポートのためにポリシーを構成すると、そのポリシーは XMPP フェデレーションドメインのユーザーに適用されますが、セッション開始プロトコル (SIP) のインスタントメッセージング (IM) サービスプロバイダー、または SIP フェデレーションドメインのユーザーには適用されません。</span><span class="sxs-lookup"><span data-stu-id="89d0c-109">When you configure policies for support of XMPP federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers, or SIP federated domains.</span></span> <span data-ttu-id="89d0c-110">ユーザーが連絡先を追加して通信できるようにする、各 XMPP フェデレーションドメインに対して XMPP フェデレーションパートナーを構成します。</span><span class="sxs-lookup"><span data-stu-id="89d0c-110">You configure an XMPP federated partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="89d0c-111">ポリシーが設定されたら、XMPP ゲートウェイ証明書を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89d0c-111">Once the policies are in place, you need to configure the XMPP Gateway certificates.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="89d0c-112">XMPP 機能は、Skype for Business Server 2019 では使われなくなりましたが、従来のサーバーでは引き続き、Skype for Business Server 2019 と共存させることができます。</span><span class="sxs-lookup"><span data-stu-id="89d0c-112">XMPP functionality is deprecated in Skype for Business Server 2019, but can be continued in a legacy server in coexistence with Skype for Business Server 2019.</span></span> <span data-ttu-id="89d0c-113">以前のバージョンのレガシサーバー (Skype for Business Server 2015/Lync Server 2013) XMPP ゲートウェイを既に展開していることを確認して、従来の XMPP ゲートウェイのユーザーを有効にするためのアクセスポリシーを構成していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="89d0c-113">Make sure you have already deployed the legacy server (Skype for Business Server 2015 / Lync Server 2013) XMPP Gateway, and configured the access policies to enable users for legacy XMPP Gateway.</span></span> <span data-ttu-id="89d0c-114">詳細については、「 [XMPP フェデレーションを移行](migrating-xmpp-federation.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89d0c-114">For details, see [Migrating XMPP Federation](migrating-xmpp-federation.md).</span></span> 
  
### <a name="configure-an-external-access-policy-to-enable-users-for-legacy-xmpp-gateway"></a><span data-ttu-id="89d0c-115">外部アクセスポリシーを構成して、レガシ XMPP ゲートウェイのユーザーを有効にする</span><span class="sxs-lookup"><span data-stu-id="89d0c-115">Configure an External Access Policy to Enable Users for legacy XMPP Gateway</span></span>

1. <span data-ttu-id="89d0c-116">従来の Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="89d0c-116">Open the legacy Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="89d0c-117">左側のナビゲーションバーで、[**フェデレーションと外部アクセス**] をクリックし、[**外部アクセスポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="89d0c-117">In the left navigation bar, click **Federation and External Access**, and then click **External Access Policy**.</span></span>
    
3. <span data-ttu-id="89d0c-118">[**新規**] をクリックし、[**ユーザー ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="89d0c-118">Click **New**, and then click **User policy**.</span></span>
    
4. <span data-ttu-id="89d0c-119">外部アクセスのユーザーポリシーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="89d0c-119">Enter a name for the external access user policy.</span></span>
    
5. <span data-ttu-id="89d0c-120">外部アクセスユーザーポリシーの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="89d0c-120">Provide a description for external access user policy.</span></span>
    
6. <span data-ttu-id="89d0c-121">[**フェデレーションユーザーとの通信を有効にする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="89d0c-121">Select **Enable communications with federated users**.</span></span>
    
7. <span data-ttu-id="89d0c-122">[ **XMPP フェデレーションユーザーとの通信を有効にする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="89d0c-122">Select **Enable communications with XMPP federated users**.</span></span>
    
8. <span data-ttu-id="89d0c-123">[**コミット**] をクリックして、サイトまたはユーザーポリシーの変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="89d0c-123">Click **Commit** to save your changes to the site or user policy.</span></span> 
    

