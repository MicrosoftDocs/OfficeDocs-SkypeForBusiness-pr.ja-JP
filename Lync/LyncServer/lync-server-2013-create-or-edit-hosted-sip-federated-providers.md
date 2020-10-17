---
title: 'Lync Server 2013: ホストされた SIP フェデレーションプロバイダーの作成または編集'
description: 'Lync Server 2013: ホストされた SIP フェデレーションプロバイダーを作成または編集します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or edit hosted SIP federated providers
ms:assetid: 0dd6dcb6-a88d-46b8-9c96-b35967309bcd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552445(v=OCS.15)
ms:contentKeyID: 48679556
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aaaa1b29b9a85332b85dfb7a1f258503fa4e9c77
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553883"
---
# <a name="create-or-edit-hosted-sip-federated-providers-lync-server-2013"></a><span data-ttu-id="e1d17-103">ホスト SIP フェデレーションプロバイダー Lync Server 2013 を作成または編集する</span><span class="sxs-lookup"><span data-stu-id="e1d17-103">Create or edit hosted SIP federated providers Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e1d17-104">_**トピックの最終更新日:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="e1d17-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="e1d17-105">ホストされるプロバイダーのインスタントメッセージング (IM) 接続により、組織内のユーザーは IM を使用して、ホストされたプロバイダーが提供する IM サービス (Microsoft 365 と Lync Online など) のユーザーと通信できるようになります。</span><span class="sxs-lookup"><span data-stu-id="e1d17-105">Hosted provider instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by hosted providers, including Microsoft 365 and Lync Online.</span></span>

<span data-ttu-id="e1d17-106">各ホストされるプロバイダーは、プロバイダーのエッジ サーバーの完全修飾ドメイン名と、既定の確認レベルである [**連絡先リストのユーザーのうち、このプロバイダーを使うユーザーとの通信のみを許可する**] によって構成されます。</span><span class="sxs-lookup"><span data-stu-id="e1d17-106">Each hosted provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="e1d17-107">ホストされるプロバイダーを作成または編集するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="e1d17-107">Use the following procedure to create or edit Hosted providers:</span></span>

<div>

## <a name="to-create-or-edit-hosted-providers"></a><span data-ttu-id="e1d17-108">ホストされるプロバイダーを作成または編集するには</span><span class="sxs-lookup"><span data-stu-id="e1d17-108">To create or edit hosted providers</span></span>

1.  <span data-ttu-id="e1d17-109">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="e1d17-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e1d17-110">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="e1d17-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e1d17-111">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1d17-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e1d17-112">左側のナビゲーション バーで [**フェデレーションと外部アクセス**] をクリックし、[**SIP フェデレーション プロバイダー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e1d17-112">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="e1d17-113">新しいホストされるプロバイダーを作成するには、[**新規**] をクリックし、[**ホストされるプロバイダー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e1d17-113">If you need to create a new Hosted provider, click **New** and then click **Hosted provider**.</span></span>

5.  <span data-ttu-id="e1d17-114">ホストされるプロバイダーの一覧に示されるプロバイダーを編集する必要がある場合は、編集するプロバイダーを選択し、[**編集**]、[**編集の表示**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="e1d17-114">If you need to edit an entry from the list of Hosted providers, select a hosted provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="e1d17-115">[**編集 SIP フェデレーション プロバイダー**] ページで、次の設定を入力または編集できます。</span><span class="sxs-lookup"><span data-stu-id="e1d17-115">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="e1d17-116">**このプロバイダー**     との通信を有効にするこの設定を選択すると、このプロバイダーのユーザーとの通信が有効になります。</span><span class="sxs-lookup"><span data-stu-id="e1d17-116">**Enable communications with this provider**   Selecting this setting enables communications with this provider’s users.</span></span>
    
      - <span data-ttu-id="e1d17-117">**プロバイダー名:**    必要なプロパティ。プロバイダーの名前を入力します。これは、SIP フェデレーションプロバイダーの一覧に反映されます。</span><span class="sxs-lookup"><span data-stu-id="e1d17-117">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="e1d17-118">**アクセスエッジサービス (FQDN):**    必要なプロパティ。構成するホストされるプロバイダーのアクセスエッジサービスの完全修飾ドメイン名を入力します。</span><span class="sxs-lookup"><span data-stu-id="e1d17-118">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the hosted provider that you are configuring.</span></span> <span data-ttu-id="e1d17-119">この情報は、ホストされているプロバイダーによって提供される必要があります。ホストされているプロバイダーがアクセスエッジサービスの FQDN に変更を加える場合にのみ変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1d17-119">This information should be provided by the hosted provider, and should only be changed if the hosted provider makes a change to the FQDN of the Access Edge service at the hosted provider.</span></span>
    
      - <span data-ttu-id="e1d17-120">**既定の確認レベル:**    既定の設定では、**このプロバイダーを使用するユーザーが連絡先リストにあるユーザーとの通信を許可すること**で、承諾した連絡先リストに含まれる連絡先へのコミュニケーションを制限します。</span><span class="sxs-lookup"><span data-stu-id="e1d17-120">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="e1d17-p103">[**このプロバイダーを使うすべてのユーザーとの通信を許可する**] を選択すると、連絡先に対する制限が削除されます。この設定は、ホストされるプロバイダーのネットワークからの通信を制限しません。</span><span class="sxs-lookup"><span data-stu-id="e1d17-p103">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite. This setting does not limit who can contact you from the hosted provider’s network.</span></span>

7.  <span data-ttu-id="e1d17-123">設定の構成が終了したら、[**コミット**] をクリックして保存するか、[**キャンセル**] をクリックして変更を破棄します。</span><span class="sxs-lookup"><span data-stu-id="e1d17-123">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e1d17-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="e1d17-124">See Also</span></span>


[<span data-ttu-id="e1d17-125">Lync Server 2013 でのパブリックユーザーアクセスを制御するポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="e1d17-125">Configure policies to control public user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-public-user-access.md)  
[<span data-ttu-id="e1d17-126">Lync Server 2013 でフェデレーションとパブリック IM 接続を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="e1d17-126">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

