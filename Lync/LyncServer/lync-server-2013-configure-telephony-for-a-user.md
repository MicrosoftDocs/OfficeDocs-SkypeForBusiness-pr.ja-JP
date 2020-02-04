---
title: 'Lync Server 2013: ユーザーのテレフォニーを構成する'
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
ms.openlocfilehash: d57c4799c0fe9bb9dc698c3e0e74a9d73cbde524
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740007"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-telephony-for-a-user-in-lync-server-2013"></a><span data-ttu-id="42f36-102">Lync Server 2013 でユーザーのテレフォニーを構成する</span><span class="sxs-lookup"><span data-stu-id="42f36-102">Configure telephony for a user in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="42f36-103">_**最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="42f36-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="42f36-104">[テレフォニー設定] は、ユーザーの Lync Server コントロールパネルで構成できるユーザーアカウントの個々の設定の一部です (つまり、個々のユーザーが Lync Server 2013 に対して有効になっていて、組織がテレフォニーをサポートしている場合)。</span><span class="sxs-lookup"><span data-stu-id="42f36-104">Telephony settings are some of the individual settings of a user account that can be configured in Lync Server Control Panel for the user (that is, if the individual user has been enabled for Lync Server 2013 and the organization supports telephony).</span></span>

<span data-ttu-id="42f36-105">Lync Server のユーザーテレフォニーオプションには、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="42f36-105">Lync Server user telephony options include the following:</span></span>

  - <span data-ttu-id="42f36-106">**音声/ビデオを無効**   にすると、ユーザーは音声とビデオを使って通話を発信できなくなります。</span><span class="sxs-lookup"><span data-stu-id="42f36-106">**Audio/video disabled**   The user cannot make calls with audio and video.</span></span>

  - <span data-ttu-id="42f36-107">\*\*\*\*   Pc 間の音声通話またはビデオ通話は、ユーザーのみが実行できます。</span><span class="sxs-lookup"><span data-stu-id="42f36-107">**PC-to-PC only**   The user can make only PC-to-PC audio or video calls.</span></span>

  - <span data-ttu-id="42f36-108">**エンタープライズ voip**   ユーザーは、Lync Server 2013 インフラストラクチャを使用して、すべての着信通話と発信通話をルーティングすることができます。</span><span class="sxs-lookup"><span data-stu-id="42f36-108">**Enterprise Voice**   The user can use the Lync Server 2013 infrastructure to route all incoming and outgoing calls.</span></span> <span data-ttu-id="42f36-109">ユーザーは PC 間の通話を発信することもできます。</span><span class="sxs-lookup"><span data-stu-id="42f36-109">The user can also make PC-to-PC calls.</span></span>

  - <span data-ttu-id="42f36-110">**リモート通話コントロール**   ユーザーは Lync Server 2013 を使ってデスクトップ電話を制御できます。また、pc 間通話もできます。</span><span class="sxs-lookup"><span data-stu-id="42f36-110">**Remote call control**   The user can use Lync Server 2013 to control the desktop phone, and can also make PC-to-PC calls.</span></span>

<span data-ttu-id="42f36-111">組織のテレフォニーの構成の詳細については、展開ドキュメントの「lync server [2013 でユーザーのテレフォニーを構成する](lync-server-2013-configure-telephony-for-a-user.md)」および「[エンタープライズ Voip を lync Server 2013 で展開](lync-server-2013-deploying-enterprise-voice.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="42f36-111">For details about configuring telephony for an organization, see [Configure telephony for a user in Lync Server 2013](lync-server-2013-configure-telephony-for-a-user.md) and [Deploying Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) in the Deployment documentation.</span></span>

<div>

## <a name="to-configure-telephony-for-a-specific-user-account"></a><span data-ttu-id="42f36-112">特定のユーザーアカウントのテレフォニーを構成するには</span><span class="sxs-lookup"><span data-stu-id="42f36-112">To configure telephony for a specific user account</span></span>

1.  <span data-ttu-id="42f36-113">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="42f36-113">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="42f36-114">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="42f36-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="42f36-115">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="42f36-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="42f36-116">左側のナビゲーション バーで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="42f36-116">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="42f36-117">[**ユーザーの検索**] ボックスに、表示名、名、姓、セキュリティアカウントマネージャー (SAM) アカウント名、SIP アドレス、または必要なユーザーアカウントの行の Uniform resource IDENTIFIER (URI) の最初の部分を入力し、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="42f36-117">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>

5.  <span data-ttu-id="42f36-118">表で、変更するユーザーアカウントをクリックします。</span><span class="sxs-lookup"><span data-stu-id="42f36-118">In the table, click the user account that you want to modify.</span></span>

6.  <span data-ttu-id="42f36-119">[**編集**] メニューの [**変更**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="42f36-119">On the **Edit** menu, click **Modify**.</span></span>

7.  <span data-ttu-id="42f36-120">[**テレフォニー**] で、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="42f36-120">In **Telephony**, do the following:</span></span>
    
      - <span data-ttu-id="42f36-121">ユーザーの音声通話とビデオ通話を無効にするには、[**オーディオ/ビデオを無効**にする] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="42f36-121">To disable audio and video calls for the user, click **Audio/video disabled**.</span></span>
    
      - <span data-ttu-id="42f36-122">ユーザーに対して PC 間音声通信を有効にしますが、リモート通話コントロールまたはエンタープライズボイスでは使用できないようにするには、[ **pc 間のみ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="42f36-122">To enable PC-to-PC audio communications for the user, but not remote call control or Enterprise Voice, click **PC-to-PC only**.</span></span> <span data-ttu-id="42f36-123">ユーザーが PC 間の音声通信に使用する電話の**ライン URI**の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="42f36-123">Specify a value for **Line URI** for the telephone that the user uses for PC-to-PC audio communications.</span></span>
    
      - <span data-ttu-id="42f36-124">PC 間の音声通信など、サービスポリシーのクラスに従って Lync Server 2010 インフラストラクチャを使用して、ユーザーの電話をルーティングするには、[**エンタープライズ voip**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="42f36-124">To route the user's phone calls by using the Lync Server 2010 infrastructure in accordance with the class of service policy, including PC-to-PC audio communication, click **Enterprise Voice**.</span></span> <span data-ttu-id="42f36-125">[**行の URI**] で、エンタープライズ voip の電話番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="42f36-125">In **Line URI**, specify the telephone number for Enterprise Voice.</span></span> <span data-ttu-id="42f36-126">[**ダイヤルプランポリシー** ] と [**ボイスポリシー**] で、ユーザーに適したポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="42f36-126">In **Dial plan policy** and **Voice policy**, specify the appropriate policies for the user.</span></span> <span data-ttu-id="42f36-127">ユーザーがダイヤルした電話番号を E-164 形式で翻訳するための正規化ルールを指定するには、**場所のポリシー**で適切な場所のプロファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="42f36-127">To specify the normalization rules for translating phone numbers dialed by the user to the E.164 format, select the appropriate location profile in **Location policy**.</span></span>
    
      - <span data-ttu-id="42f36-128">ユーザーが Lync Server 2013 からデスクトップ電話回線を制御できるようにするリモート通話コントロールを有効にするには、[**リモート通話コントロール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="42f36-128">To enable remote call control, which enables users to control their desktop phone line from Lync Server 2013 to make PC-to-PC calls and PC-to-phone calls, click **Remote call control**.</span></span> <span data-ttu-id="42f36-129">[**行の URI**] で、リモート通話コントロール用の電話番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="42f36-129">In **Line URI**, specify the telephone number for remote call control.</span></span> <span data-ttu-id="42f36-130">ユーザーは、通話ルーティング用に、デスクトップ電話と構内交換機 (PBX) 接続を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="42f36-130">The user must have a desktop phone and private branch exchange (PBX) connection for call routing.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="42f36-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="42f36-131">See Also</span></span>


[<span data-ttu-id="42f36-132">Lync Server 2013 でユーザーアカウントのプロパティを変更する</span><span class="sxs-lookup"><span data-stu-id="42f36-132">Modifying user account properties in Lync Server 2013</span></span>](lync-server-2013-modifying-user-account-properties.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

