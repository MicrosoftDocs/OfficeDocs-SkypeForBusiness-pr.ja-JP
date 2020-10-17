---
title: 'Lync Server 2013: パブリック SIP フェデレーションプロバイダーの作成または編集'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or edit public SIP federated providers
ms:assetid: 5321598c-1ab1-40e3-b739-4b2e6d0a3a3b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398349(v=OCS.15)
ms:contentKeyID: 48184167
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 58b0ffdc009d48ef82d1bdf3ba8662cd4072ea1c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514854"
---
# <a name="create-or-edit-public-sip-federated-providers-in-lync-server-2013"></a><span data-ttu-id="7210b-102">Lync Server 2013 でのパブリック SIP フェデレーションプロバイダーの作成または編集</span><span class="sxs-lookup"><span data-stu-id="7210b-102">Create or edit public SIP federated providers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7210b-103">_**トピックの最終更新日:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="7210b-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="7210b-104">パブリックインスタントメッセージング (IM) 接続を使用すると、組織内のユーザーは IM を使用して、パブリック IM サービスプロバイダーが提供する IM サービス (Windows Live Messenger、Yahoo、AOL など) のユーザーと通信することができ \! ます。</span><span class="sxs-lookup"><span data-stu-id="7210b-104">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public IM service providers, including the Windows Live Messenger, Yahoo\!, and AOL.</span></span>

<span data-ttu-id="7210b-105">Lync Server 2013 には、America Online、Windows Live、Yahoo 用のパブリックプロバイダー構成があります。\!</span><span class="sxs-lookup"><span data-stu-id="7210b-105">Lync Server 2013 has public provider configurations for America Online, Windows Live and Yahoo\!</span></span> <span data-ttu-id="7210b-106">の各インスタント メッセージングのパブリック プロバイダー構成が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7210b-106">instant messaging.</span></span> <span data-ttu-id="7210b-107">各パブリック プロバイダーは、そのプロバイダーのエッジ サーバーの完全修飾ドメイン名と、既定の確認レベルである [**Allow users to communicate only with people on their Contacts list who use this provider**] を指定して構成されています。</span><span class="sxs-lookup"><span data-stu-id="7210b-107">Each public provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="7210b-108">既定の設定では、パブリック プロバイダーはいずれも無効になっています。</span><span class="sxs-lookup"><span data-stu-id="7210b-108">As a default setting, none of the public providers are enabled.</span></span> <span data-ttu-id="7210b-109">パブリック プロバイダーを有効にする前に、使用許諾契約とプロビジョニング作業を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7210b-109">You should complete license agreement and provisioning work before enabling the public providers.</span></span> <span data-ttu-id="7210b-110">ライセンスとプロビジョニングの作業を完了する前にプロバイダーを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="7210b-110">You can enable the provider before completing the licensing and provisioning work.</span></span> <span data-ttu-id="7210b-111">前提条件となる作業を完了するまで、ユーザーはそのプロバイダーで連絡先と通信することはできません。</span><span class="sxs-lookup"><span data-stu-id="7210b-111">Users will not be able to communicate with contacts on those providers until the pre-requisite work is completed.</span></span> <span data-ttu-id="7210b-112">パブリックプロバイダーのライセンスとプロビジョニングの詳細については、「 [Configure policies to control public user access In Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7210b-112">For details on licensing and provisioning of public providers, see [Configure policies to control public user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md).</span></span>

<span data-ttu-id="7210b-113">次の手順を使用して、パブリック プロバイダーを作成または編集します。</span><span class="sxs-lookup"><span data-stu-id="7210b-113">Use the following procedure to create or edit Public providers:</span></span>

<div>

## <a name="to-create-or-edit-public-providers"></a><span data-ttu-id="7210b-114">パブリック プロバイダーを作成または編集するには</span><span class="sxs-lookup"><span data-stu-id="7210b-114">To create or edit public providers</span></span>

1.  <span data-ttu-id="7210b-115">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="7210b-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7210b-116">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="7210b-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7210b-117">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7210b-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7210b-118">左側のナビゲーション バーで、[**フェデレーションと外部アクセス**] をクリックし、[**SIP フェデレーション プロバイダー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7210b-118">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="7210b-119">新しいパブリック プロバイダーを作成する必要がある場合は、[**新規作成**] をクリックし、[**パブリック プロバイダー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7210b-119">If you need to create a new Public provider, click **New** and then click **Public provider**.</span></span>

5.  <span data-ttu-id="7210b-120">パブリック プロバイダーの一覧のエントリを編集する必要がある場合は、パブリック プロバイダーを選択し、[**編集**] をクリックして [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7210b-120">If you need to edit an entry from the list of Public providers, select a public provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="7210b-121">[**編集 SIP フェデレーション プロバイダー**] ページでは、次の設定を入力または編集できます。</span><span class="sxs-lookup"><span data-stu-id="7210b-121">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="7210b-122">**このプロバイダー**     との通信を有効にするこの設定を選択すると、このプロバイダーのユーザーとの IM が有効になります。</span><span class="sxs-lookup"><span data-stu-id="7210b-122">**Enable communications with this provider**   Selecting this setting enables IM with this provider’s users.</span></span>
    
      - <span data-ttu-id="7210b-123">**プロバイダー名:**    必要なプロパティ。プロバイダーの名前を入力します。これは、SIP フェデレーションプロバイダーの一覧に反映されます。</span><span class="sxs-lookup"><span data-stu-id="7210b-123">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="7210b-124">**アクセスエッジサービス (FQDN):**    必要なプロパティ。構成するプロバイダーのアクセスエッジサービスの完全修飾ドメイン名を入力します。</span><span class="sxs-lookup"><span data-stu-id="7210b-124">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the provider that you are configuring.</span></span> <span data-ttu-id="7210b-125">この情報は既定のアイテムとして提供され、パブリックプロバイダがパブリックプロバイダのアクセスエッジサービスの FQDN に変更を加える場合にのみ変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7210b-125">This information is provided as a default item, and should only be changed if the public provider makes a change to the FQDN of the Access Edge service at the public provider.</span></span>
    
      - <span data-ttu-id="7210b-126">**既定の確認レベル:**    既定の設定では、**このプロバイダーを使用するユーザーが連絡先リストにあるユーザーとの通信を許可すること**で、承諾した連絡先リストに含まれる連絡先へのコミュニケーションを制限します。</span><span class="sxs-lookup"><span data-stu-id="7210b-126">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="7210b-p105">[**Allow users to communicate with everyone using this provider**] を選択すると、連絡先からの招待を受け取って承認しておく必要があるという制限がなくなります。この設定では、パブリック プロバイダーのネットワークからユーザーに連絡できる相手先は制限されません。</span><span class="sxs-lookup"><span data-stu-id="7210b-p105">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite. This setting does not limit who can contact you from the public provider’s network.</span></span>

7.  <span data-ttu-id="7210b-129">設定の構成が完了したら、[**コミット**] をクリックして保存するか、[**キャンセル**] をクリックして変更を破棄します。</span><span class="sxs-lookup"><span data-stu-id="7210b-129">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7210b-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="7210b-130">See Also</span></span>


[<span data-ttu-id="7210b-131">Lync Server 2013 でのパブリックユーザーアクセスを制御するポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="7210b-131">Configure policies to control public user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-public-user-access.md)  
[<span data-ttu-id="7210b-132">Lync Server 2013 でフェデレーションとパブリック IM 接続を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="7210b-132">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

