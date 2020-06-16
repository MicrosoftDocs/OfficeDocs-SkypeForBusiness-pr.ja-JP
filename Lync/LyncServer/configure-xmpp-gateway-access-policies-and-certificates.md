---
title: XMPP ゲートウェイ アクセス ポリシーおよび証明書の構成
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure XMPP gateway access policies and certificates
ms:assetid: fac02f4e-d14d-4be3-b53c-74c82436fd93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721945(v=OCS.15)
ms:contentKeyID: 49733882
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d7353d6bfdd4c045d9d592ababf92f2aaaec2365
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754475"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a><span data-ttu-id="c59ae-102">XMPP ゲートウェイ アクセス ポリシーおよび証明書の構成</span><span class="sxs-lookup"><span data-stu-id="c59ae-102">Configure XMPP gateway access policies and certificates</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c59ae-103">_**トピックの最終更新日:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="c59ae-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="c59ae-104">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol (XMPP).</span><span class="sxs-lookup"><span data-stu-id="c59ae-104">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol (XMPP).</span></span> <span data-ttu-id="c59ae-105">An XMPP configuration allows Lync users access to XMPP domain users by:</span><span class="sxs-lookup"><span data-stu-id="c59ae-105">An XMPP configuration allows Lync users access to XMPP domain users by:</span></span>

  - <span data-ttu-id="c59ae-106">IM およびプレゼンス (1 対 1 のみ)</span><span class="sxs-lookup"><span data-stu-id="c59ae-106">IM and Presence – person to person only</span></span>

  - <span data-ttu-id="c59ae-107">XMPP フェデレーションからの連絡先を Lync クライアントに作成</span><span class="sxs-lookup"><span data-stu-id="c59ae-107">Creation of XMPP federated contacts in the Lync client</span></span>

<span data-ttu-id="c59ae-108">When you configure policies for support of extensible messaging and presence protocol (XMPP) federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers (for example, Windows Live), or SIP federated domains.</span><span class="sxs-lookup"><span data-stu-id="c59ae-108">When you configure policies for support of extensible messaging and presence protocol (XMPP) federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers (for example, Windows Live), or SIP federated domains.</span></span> <span data-ttu-id="c59ae-109">You configure an XMPP Federated Partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span><span class="sxs-lookup"><span data-stu-id="c59ae-109">You configure an XMPP Federated Partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="c59ae-110">Once the policies are in place, you need to configure the XMPP Gateway certificates.</span><span class="sxs-lookup"><span data-stu-id="c59ae-110">Once the policies are in place, you need to configure the XMPP Gateway certificates.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c59ae-111">XMPP ゲートウェイの移行を開始するには、Lync Server 2013 XMPP ゲートウェイを展開し、Lync Server 2013 XMPP ゲートウェイのユーザーを有効にするためのアクセスポリシーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c59ae-111">To begin the XMPP Gateway migration, you need to deploy the Lync Server 2013 XMPP Gateway, and configure access policies to enable users for Lync Server 2013 XMPP Gateway.</span></span> <span data-ttu-id="c59ae-112">これらの手順を実行する前に、すべてのユーザーを Lync Server 2013 展開に移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c59ae-112">All users must be moved to the Lync Server 2013 deployment before you perform these steps.</span></span> <span data-ttu-id="c59ae-113">詳細については、「 <A href="configure-xmpp-gateway-on-lync-server-2013.md">Configure XMPP gateway On Lync Server 2013</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c59ae-113">For details, see <A href="configure-xmpp-gateway-on-lync-server-2013.md">Configure XMPP gateway on Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="configure-an-external-access-policy-to-enable-users-for-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="c59ae-114">Lync Server 2013 XMPP ゲートウェイに対してユーザーを有効にする外部アクセス ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="c59ae-114">Configure an External Access Policy to Enable Users for Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="c59ae-115">[Lync Server コントロール パネル] を開きます。</span><span class="sxs-lookup"><span data-stu-id="c59ae-115">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="c59ae-116">左側のナビゲーション バーで [**フェデレーションと外部アクセス**] をクリックし、[**外部アクセス ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c59ae-116">In the left navigation bar, click **Federation and External Access**, and then click **External Access Policy**.</span></span>

3.  <span data-ttu-id="c59ae-117">[**新規**] をクリックし、[**ユーザー ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c59ae-117">Click **New** and then click **User policy**.</span></span>

4.  <span data-ttu-id="c59ae-118">外部アクセス ユーザー ポリシーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="c59ae-118">Enter a name for the external access user policy.</span></span>

5.  <span data-ttu-id="c59ae-119">外部アクセス ユーザー ポリシーの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="c59ae-119">Provide a description for external access user policy.</span></span>

6.  <span data-ttu-id="c59ae-120">[**フェデレーション ユーザーとの通信を有効にする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c59ae-120">Select **Enable communications with federated users**.</span></span>

7.  <span data-ttu-id="c59ae-121">[**XMPP フェデレーション ユーザーとの通信を有効にする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c59ae-121">Select **Enable communications with XMPP federated users**.</span></span>

8.  <span data-ttu-id="c59ae-122">[**確定**] をクリックして、サイトまたはユーザー ポリシーへの変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="c59ae-122">Click **Commit** to save your changes to the site or user policy.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

