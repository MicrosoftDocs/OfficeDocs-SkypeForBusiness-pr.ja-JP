---
title: 'Lync Server 2013: ホスト SIP フェデレーション プロバイダーの作成または編集'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or edit hosted SIP federated providers
ms:assetid: 0dd6dcb6-a88d-46b8-9c96-b35967309bcd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552445(v=OCS.15)
ms:contentKeyID: 48679556
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bbdc22f2e877d7dafc8f52506d77312730ab428
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833822"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-edit-hosted-sip-federated-providers-lync-server-2013"></a><span data-ttu-id="abb6f-102">Lync Server 2013 でのホスト SIP フェデレーション プロバイダーの作成または編集</span><span class="sxs-lookup"><span data-stu-id="abb6f-102">Create or edit hosted SIP federated providers Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="abb6f-103">_**最終更新日:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="abb6f-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="abb6f-104">ホストされているプロバイダーのインスタントメッセージング (IM) 接続により、組織内のユーザーは、Microsoft Office 365 と Lync Online を含む、ホスティングプロバイダーによって提供される IM サービスのユーザーとの通信に IM を使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="abb6f-104">Hosted provider instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by hosted providers, including the Microsoft Office 365 and Lync Online.</span></span>

<span data-ttu-id="abb6f-105">ホストされる各プロバイダーは、プロバイダーのエッジサーバーの完全修飾ドメイン名で構成され、既定の認証レベルでは、**このプロバイダーを使用する連絡先リストのユーザーのみとの通信を許可**します。</span><span class="sxs-lookup"><span data-stu-id="abb6f-105">Each hosted provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="abb6f-106">ホストされるプロバイダーを作成または編集するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="abb6f-106">Use the following procedure to create or edit Hosted providers:</span></span>

<div>

## <a name="to-create-or-edit-hosted-providers"></a><span data-ttu-id="abb6f-107">ホストされているプロバイダーを作成または編集するには</span><span class="sxs-lookup"><span data-stu-id="abb6f-107">To create or edit hosted providers</span></span>

1.  <span data-ttu-id="abb6f-108">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="abb6f-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="abb6f-109">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="abb6f-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="abb6f-110">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="abb6f-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="abb6f-111">左側のナビゲーションバーで、[**フェデレーションと外部アクセス**] をクリックし、[ **SIP フェデレーションプロバイダー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="abb6f-111">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="abb6f-112">新しいホスティングプロバイダーを作成する必要がある場合は、[**新規**] をクリックし、[ホストされる**プロバイダー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="abb6f-112">If you need to create a new Hosted provider, click **New** and then click **Hosted provider**.</span></span>

5.  <span data-ttu-id="abb6f-113">ホストされているプロバイダーの一覧からエントリを編集する必要がある場合は、ホストされているプロバイダーを選択し、[**編集**] をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="abb6f-113">If you need to edit an entry from the list of Hosted providers, select a hosted provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="abb6f-114">[ **SIP フェデレーションプロバイダーの編集**] ページでは、次の設定を入力または編集できます。</span><span class="sxs-lookup"><span data-stu-id="abb6f-114">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="abb6f-115">**このプロバイダー**   との通信を有効にするこの設定をオンにすると、このプロバイダーのユーザーとの通信が有効になります。</span><span class="sxs-lookup"><span data-stu-id="abb6f-115">**Enable communications with this provider**   Selecting this setting enables communications with this provider’s users.</span></span>
    
      - <span data-ttu-id="abb6f-116">**[Provider name]:**   必要なプロパティは、SIP フェデレーションプロバイダーの一覧に反映されるプロバイダーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="abb6f-116">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="abb6f-117">**Access edge サービス (FQDN):**   必須プロパティ。構成するホストされているプロバイダーのアクセスエッジサービスの完全修飾ドメイン名を入力します。</span><span class="sxs-lookup"><span data-stu-id="abb6f-117">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the hosted provider that you are configuring.</span></span> <span data-ttu-id="abb6f-118">この情報は、ホストされたプロバイダーによって提供される必要があります。また、ホストされているプロバイダーが、ホストされているプロバイダーでアクセスエッジサービスの FQDN に変更を加えた場合にのみ変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="abb6f-118">This information should be provided by the hosted provider, and should only be changed if the hosted provider makes a change to the FQDN of the Access Edge service at the hosted provider.</span></span>
    
      - <span data-ttu-id="abb6f-119">**既定の確認レベル:**   既定の設定では、ユーザーが連絡先リストに登録されているユーザー**との通信を許可**します。このプロバイダーを使用すると、承諾した連絡先と連絡先リストに含まれている連絡先への通信が制限されます。</span><span class="sxs-lookup"><span data-stu-id="abb6f-119">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="abb6f-120">[**このプロバイダーを使用するすべてのユーザーとの通信を許可する**] を選択すると、連絡先への招待を受信して受け付けるために必要な制限が解除されます。</span><span class="sxs-lookup"><span data-stu-id="abb6f-120">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite.</span></span> <span data-ttu-id="abb6f-121">この設定では、ホストされているプロバイダーのネットワークから連絡できるユーザーを制限することはできません。</span><span class="sxs-lookup"><span data-stu-id="abb6f-121">This setting does not limit who can contact you from the hosted provider’s network.</span></span>

7.  <span data-ttu-id="abb6f-122">設定の構成が完了したら、[**確定**] をクリックするか、[**キャンセル**] をクリックして変更を破棄します。</span><span class="sxs-lookup"><span data-stu-id="abb6f-122">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="abb6f-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="abb6f-123">See Also</span></span>


[<span data-ttu-id="abb6f-124">Lync Server 2013 でのパブリック ユーザー アクセスを制御するポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="abb6f-124">Configure policies to control public user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-public-user-access.md)  
[<span data-ttu-id="abb6f-125">Lync Server 2013 でのフェデレーションおよびパブリック IM 接続の有効化または無効化</span><span class="sxs-lookup"><span data-stu-id="abb6f-125">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

