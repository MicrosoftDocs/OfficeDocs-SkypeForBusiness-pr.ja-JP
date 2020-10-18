---
title: 'Lync Server 2013: ユーザーのテレフォニーの構成'
description: 'Lync Server 2013: ユーザーのテレフォニーを構成します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure telephony for a user
ms:assetid: 4546432e-c839-4517-a2c5-bc0d4d8c6a03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520988(v=OCS.15)
ms:contentKeyID: 48183987
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b82cecb67ea11928d187bd2a4a00625fbca7b23e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576653"
---
# <a name="configure-telephony-for-a-user-in-lync-server-2013"></a><span data-ttu-id="c60bb-103">Lync Server 2013 でユーザーのテレフォニーを構成する</span><span class="sxs-lookup"><span data-stu-id="c60bb-103">Configure telephony for a user in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c60bb-104">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="c60bb-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="c60bb-105">テレフォニーの設定は、ユーザーの Lync Server コントロールパネルで構成できるユーザーアカウントの個別の設定です (つまり、個々のユーザーが Lync Server 2013 に対して有効になっており、組織がテレフォニーをサポートしている場合)。</span><span class="sxs-lookup"><span data-stu-id="c60bb-105">Telephony settings are some of the individual settings of a user account that can be configured in Lync Server Control Panel for the user (that is, if the individual user has been enabled for Lync Server 2013 and the organization supports telephony).</span></span>

<span data-ttu-id="c60bb-106">Lync Server ユーザーテレフォニーオプションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c60bb-106">Lync Server user telephony options include the following:</span></span>

  - <span data-ttu-id="c60bb-107">**音声/ビデオが無効**    ユーザーは、音声とビデオで電話をかけることができません。</span><span class="sxs-lookup"><span data-stu-id="c60bb-107">**Audio/video disabled**   The user cannot make calls with audio and video.</span></span>

  - <span data-ttu-id="c60bb-108">**Pc 間のみ**    ユーザーは PC 間の音声通話またはビデオ通話のみを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c60bb-108">**PC-to-PC only**   The user can make only PC-to-PC audio or video calls.</span></span>

  - <span data-ttu-id="c60bb-109">**エンタープライズ voip**    ユーザーは、Lync Server 2013 インフラストラクチャを使用して、すべての着信および発信通話をルーティングできます。</span><span class="sxs-lookup"><span data-stu-id="c60bb-109">**Enterprise Voice**   The user can use the Lync Server 2013 infrastructure to route all incoming and outgoing calls.</span></span> <span data-ttu-id="c60bb-110">また、PC 間の通話も可能です。</span><span class="sxs-lookup"><span data-stu-id="c60bb-110">The user can also make PC-to-PC calls.</span></span>

  - <span data-ttu-id="c60bb-111">**リモート通話コントロール**    ユーザーは、Lync Server 2013 を使用してデスクトップ電話を制御でき、PC から PC への通話を行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="c60bb-111">**Remote call control**   The user can use Lync Server 2013 to control the desktop phone, and can also make PC-to-PC calls.</span></span>

<span data-ttu-id="c60bb-112">組織のテレフォニーの構成の詳細については、「展開」のドキュメントの「 [Configure telephony for a lync server 2013](lync-server-2013-configure-telephony-for-a-user.md) 」および「 [lync server 2013 でのエンタープライズ voip の展開](lync-server-2013-deploying-enterprise-voice.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c60bb-112">For details about configuring telephony for an organization, see [Configure telephony for a user in Lync Server 2013](lync-server-2013-configure-telephony-for-a-user.md) and [Deploying Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) in the Deployment documentation.</span></span>

<div>

## <a name="to-configure-telephony-for-a-specific-user-account"></a><span data-ttu-id="c60bb-113">特定のユーザー アカウントのテレフォニーを構成するには</span><span class="sxs-lookup"><span data-stu-id="c60bb-113">To configure telephony for a specific user account</span></span>

1.  <span data-ttu-id="c60bb-114">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="c60bb-114">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c60bb-115">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="c60bb-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c60bb-116">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c60bb-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c60bb-117">左側のナビゲーション バーで **[ユーザー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c60bb-117">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="c60bb-118">**[ユーザーの検索]** ボックスに、検索するユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) の全部または最初の一部を入力して、**[検索]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c60bb-118">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>

5.  <span data-ttu-id="c60bb-119">表中の変更するユーザー アカウントをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c60bb-119">In the table, click the user account that you want to modify.</span></span>

6.  <span data-ttu-id="c60bb-120">[**編集**] メニューの [**変更**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c60bb-120">On the **Edit** menu, click **Modify**.</span></span>

7.  <span data-ttu-id="c60bb-121">[**テレフォニー**] で次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c60bb-121">In **Telephony**, do the following:</span></span>
    
      - <span data-ttu-id="c60bb-122">ユーザーの音声通話およびビデオ通話を無効にするには、**[音声ビデオを無効にする]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c60bb-122">To disable audio and video calls for the user, click **Audio/video disabled**.</span></span>
    
      - <span data-ttu-id="c60bb-p103">ユーザーの PC 間の音声通信を有効にするが、リモート通話コントロールやエンタープライズ VoIP は有効にしない場合は、[**PC 間のみ**] をクリックします。 ユーザーが PC 間の音声通信に使用する電話の [**回線 URI**] の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="c60bb-p103">To enable PC-to-PC audio communications for the user, but not remote call control or Enterprise Voice, click **PC-to-PC only**. Specify a value for **Line URI** for the telephone that the user uses for PC-to-PC audio communications.</span></span>
    
      - <span data-ttu-id="c60bb-125">PC 間の音声通信を含む、サービスポリシーのクラスに従って Lync Server 2010 インフラストラクチャを使用してユーザーの電話をルーティングするには、[ **エンタープライズ voip**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c60bb-125">To route the user's phone calls by using the Lync Server 2010 infrastructure in accordance with the class of service policy, including PC-to-PC audio communication, click **Enterprise Voice**.</span></span> <span data-ttu-id="c60bb-126">[**回線 URI**] でエンタープライズ VoIP の電話番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="c60bb-126">In **Line URI**, specify the telephone number for Enterprise Voice.</span></span> <span data-ttu-id="c60bb-127">[**ダイヤル プラン ポリシー**] と [**音声ポリシー**] で、ユーザーの適切なポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="c60bb-127">In **Dial plan policy** and **Voice policy**, specify the appropriate policies for the user.</span></span> <span data-ttu-id="c60bb-128">ユーザーのダイヤルした電話番号を E.164 形式に変換するための正規化ルールを指定するには、[**場所のポリシー**] で適切な場所のプロファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="c60bb-128">To specify the normalization rules for translating phone numbers dialed by the user to the E.164 format, select the appropriate location profile in **Location policy**.</span></span>
    
      - <span data-ttu-id="c60bb-129">リモート通話コントロールを有効にするには、ユーザーが Lync Server 2013 のデスクトップ電話回線を制御して、PC 間通話と PC 間通話を行うことができるようにします。そのためには、[ **リモート通話コントロール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c60bb-129">To enable remote call control, which enables users to control their desktop phone line from Lync Server 2013 to make PC-to-PC calls and PC-to-phone calls, click **Remote call control**.</span></span> <span data-ttu-id="c60bb-130">[**回線 URI**] でリモート通話コントロールの電話番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="c60bb-130">In **Line URI**, specify the telephone number for remote call control.</span></span> <span data-ttu-id="c60bb-131">通話ルーティングを行うには、ユーザーがデスクトップ電話と構内交換機 (PBX) を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c60bb-131">The user must have a desktop phone and private branch exchange (PBX) connection for call routing.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c60bb-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="c60bb-132">See Also</span></span>


[<span data-ttu-id="c60bb-133">Lync Server 2013 でユーザーアカウントのプロパティを変更する</span><span class="sxs-lookup"><span data-stu-id="c60bb-133">Modifying user account properties in Lync Server 2013</span></span>](lync-server-2013-modifying-user-account-properties.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

