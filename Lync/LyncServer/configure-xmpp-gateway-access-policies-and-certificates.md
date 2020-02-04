---
title: XMPP ゲートウェイ アクセス ポリシーおよび証明書の構成
ms.reviewer: ''
ms.author: kenwith
author: kenwith
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
ms.openlocfilehash: 5b1aab41b1a9af8c7b8df888dcb3a0c8621fa44e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723237"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a><span data-ttu-id="453c7-102">XMPP ゲートウェイ アクセス ポリシーおよび証明書の構成</span><span class="sxs-lookup"><span data-stu-id="453c7-102">Configure XMPP gateway access policies and certificates</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="453c7-103">_**最終更新日:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="453c7-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="453c7-104">XMPP フェデレーションは、拡張メッセージングとプレゼンスプロトコル (XMPP) に基づいて外部展開を定義します。</span><span class="sxs-lookup"><span data-stu-id="453c7-104">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol (XMPP).</span></span> <span data-ttu-id="453c7-105">XMPP の構成により、Lync ユーザーは次の方法で XMPP ドメインユーザーにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="453c7-105">An XMPP configuration allows Lync users access to XMPP domain users by:</span></span>

  - <span data-ttu-id="453c7-106">IM とプレゼンス–人物との連絡のみ</span><span class="sxs-lookup"><span data-stu-id="453c7-106">IM and Presence – person to person only</span></span>

  - <span data-ttu-id="453c7-107">Lync クライアントでの XMPP フェデレーション連絡先の作成</span><span class="sxs-lookup"><span data-stu-id="453c7-107">Creation of XMPP federated contacts in the Lync client</span></span>

<span data-ttu-id="453c7-108">拡張メッセージングとプレゼンスプロトコル (XMPP) フェデレーションパートナーをサポートするためにポリシーを構成すると、そのポリシーは XMPP フェデレーションドメインのユーザーに適用されますが、セッション開始プロトコル (SIP) のインスタントメッセージング (IM) サービスプロバイダーのユーザーには適用されません。(たとえば、Windows Live など)、または SIP フェデレーションドメイン。</span><span class="sxs-lookup"><span data-stu-id="453c7-108">When you configure policies for support of extensible messaging and presence protocol (XMPP) federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers (for example, Windows Live), or SIP federated domains.</span></span> <span data-ttu-id="453c7-109">ユーザーが連絡先を追加して通信できるようにする、各 XMPP フェデレーションドメインに対して XMPP フェデレーションパートナーを構成します。</span><span class="sxs-lookup"><span data-stu-id="453c7-109">You configure an XMPP Federated Partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="453c7-110">ポリシーが設定されたら、XMPP ゲートウェイ証明書を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="453c7-110">Once the policies are in place, you need to configure the XMPP Gateway certificates.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="453c7-111">XMPP ゲートウェイの移行を開始するには、Lync Server 2013 XMPP ゲートウェイを展開し、アクセスポリシーを構成して、Lync Server 2013 XMPP ゲートウェイのユーザーを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="453c7-111">To begin the XMPP Gateway migration, you need to deploy the Lync Server 2013 XMPP Gateway, and configure access policies to enable users for Lync Server 2013 XMPP Gateway.</span></span> <span data-ttu-id="453c7-112">これらの手順を実行する前に、すべてのユーザーを Lync Server 2013 展開に移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="453c7-112">All users must be moved to the Lync Server 2013 deployment before you perform these steps.</span></span> <span data-ttu-id="453c7-113">詳細については、「 <A href="configure-xmpp-gateway-on-lync-server-2013.md">Lync Server 2013 での XMPP ゲートウェイの構成</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="453c7-113">For details, see <A href="configure-xmpp-gateway-on-lync-server-2013.md">Configure XMPP gateway on Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="configure-an-external-access-policy-to-enable-users-for-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="453c7-114">外部アクセスポリシーを構成して Lync Server 2013 XMPP ゲートウェイのユーザーを有効にする</span><span class="sxs-lookup"><span data-stu-id="453c7-114">Configure an External Access Policy to Enable Users for Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="453c7-115">[Lync Server コントロール パネル] を開きます。</span><span class="sxs-lookup"><span data-stu-id="453c7-115">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="453c7-116">左側のナビゲーションバーで、[**フェデレーションと外部アクセス**] をクリックし、[**外部アクセスポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="453c7-116">In the left navigation bar, click **Federation and External Access**, and then click **External Access Policy**.</span></span>

3.  <span data-ttu-id="453c7-117">[**新規作成**] をクリックし、[**ユーザーポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="453c7-117">Click **New** and then click **User policy**.</span></span>

4.  <span data-ttu-id="453c7-118">外部アクセスのユーザーポリシーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="453c7-118">Enter a name for the external access user policy.</span></span>

5.  <span data-ttu-id="453c7-119">外部アクセスユーザーポリシーの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="453c7-119">Provide a description for external access user policy.</span></span>

6.  <span data-ttu-id="453c7-120">[**フェデレーションユーザーとの通信を有効にする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="453c7-120">Select **Enable communications with federated users**.</span></span>

7.  <span data-ttu-id="453c7-121">[ **XMPP フェデレーションユーザーとの通信を有効にする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="453c7-121">Select **Enable communications with XMPP federated users**.</span></span>

8.  <span data-ttu-id="453c7-122">[**コミット**] をクリックして、サイトまたはユーザーポリシーの変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="453c7-122">Click **Commit** to save your changes to the site or user policy.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

