---
title: ユーザーが外部の Skype for Business ユーザーに連絡できるようにする
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: b414873a-0059-4cd5-aea1-e5d0857dbc94
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Setup
- For O365M_ShareLync
- ms.lync.lac.OrgExternalAccess
- ms.lync.lac.skypefederation
- O365E_HRCLYNC _ SipFederationSrvRecordVerified_FL312122
- O365E_ShareLync
- O365M_ShareLync
- O365P_ExternalCommDesc
- O365P_ShareLync
- LIL_Placement
description: 'ユーザーが別の組織のユーザーと話すことができるように Skype for Business を構成する方法、または外部の連絡先と連絡を取り合ってもらう方法について説明します。 '
ms.openlocfilehash: d9b3be381432fa95962df7a5a58ea9d81e223fc4
ms.sourcegitcommit: 619b68d28b4fbf8b5296d95bbc7ed566f839f1db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/20/2020
ms.locfileid: "48625053"
---
# <a name="allow-users-to-contact-external-skype-for-business-users"></a><span data-ttu-id="f05bd-103">ユーザーが外部の Skype for Business ユーザーに連絡できるようにする</span><span class="sxs-lookup"><span data-stu-id="f05bd-103">Allow users to contact external Skype for Business users</span></span>
  
<span data-ttu-id="f05bd-104">次の場合、この記事で説明する手順をご利用ください。</span><span class="sxs-lookup"><span data-stu-id="f05bd-104">Use the steps in this article when:</span></span>
  
- <span data-ttu-id="f05bd-105">会社のさまざまなドメインにユーザーがいる。</span><span class="sxs-lookup"><span data-stu-id="f05bd-105">You have users on different domains in your business.</span></span> <span data-ttu-id="f05bd-106">たとえば、Rob@ContosoEast.com と Ann@ContosoWest.com のような場合。</span><span class="sxs-lookup"><span data-stu-id="f05bd-106">For example, Rob@ContosoEast.com and Ann@ContosoWest.com.</span></span>

- <span data-ttu-id="f05bd-107">組織内のユーザーが Skype for Business を使用して、組織外の特定の企業のユーザーに連絡できるようにする場合。</span><span class="sxs-lookup"><span data-stu-id="f05bd-107">You want the people in your organization to use Skype for Business to contact people in specific businesses outside of your organization.</span></span>

- <span data-ttu-id="f05bd-108">Skype for Business を使用する世界中の他のユーザーが、自分のメールアドレスを使ってあなたを見つけて連絡できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f05bd-108">You want anyone else in the world who uses Skype for Business to be able to find and contact you using your email address.</span></span> <span data-ttu-id="f05bd-109">Skype for Business の既定の設定を使用している場合は、これが自動的に有効になります。</span><span class="sxs-lookup"><span data-stu-id="f05bd-109">If you and they use the default Skype for Business settings, this will work automatically.</span></span> <span data-ttu-id="f05bd-110">そうでない場合は、その構成でドメインがブロックされていないことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f05bd-110">If they don't, then they need to make sure their configuration isn't blocking your domain.</span></span>

## <a name="enable-business-to-business-communications-for-your-users"></a><span data-ttu-id="f05bd-111">ユーザーに対する企業間の通信を有効にする</span><span class="sxs-lookup"><span data-stu-id="f05bd-111">Enable business-to-business communications for your users</span></span>

<span data-ttu-id="f05bd-112"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="f05bd-112"><a name="bk_preview"> </a></span></span>

<span data-ttu-id="f05bd-113">この通信を行うには、両方の組織で Microsoft 365 または Office 365 の [管理者権限](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) が必要です。</span><span class="sxs-lookup"><span data-stu-id="f05bd-113">You must have [admin permissions](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) in Microsoft 365 or Office 365 in both organizations to do this communication.</span></span>

<span data-ttu-id="f05bd-114">![](../images/teams-logo-30x30.png) **Teams 管理センターを使用し**た Microsoft Teams ロゴを示すアイコン</span><span class="sxs-lookup"><span data-stu-id="f05bd-114">![An icon showing the Microsoft Teams logo](../images/teams-logo-30x30.png) **Using the Teams admin center**</span></span>
  
1. <span data-ttu-id="f05bd-115">Microsoft 365 または Office 365 管理者アカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="f05bd-115">Sign in with your Microsoft 365 or Office 365 admin account.</span></span>

2. <span data-ttu-id="f05bd-116">管理センターで、[**管理センター**  >  **チーム**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="f05bd-116">In the admin center, go to **Admin Centers** > **Teams**.</span></span>

    ![Teams 管理者を選びます。](../images/MS-Teams-Admin.png)
  
3. <span data-ttu-id="f05bd-118">**Teams センター**で、「 **Skype** > **レガシーポータル**」「 
  ![ sfb レガシーポータルを選択」を選択します。](../images/SFBlegacy-size65.png)</span><span class="sxs-lookup"><span data-stu-id="f05bd-118">In the **Teams center**, choose **Skype** > **Legacy Portal**
![Choose the SfB Legacy Portal.](../images/SFBlegacy-size65.png)</span></span>

4. <span data-ttu-id="f05bd-119">**Skype for Business 管理センター**で、[**組織**]  >  [**外部通信**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="f05bd-119">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span>
5. <span data-ttu-id="f05bd-120">特定の会社や別のドメインのユーザーとの通信を設定するには、ドロップダウン ボックスで [**許可したドメインに対してのみオンにする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f05bd-120">To set up communication with a specific business or with users in another domain, in the drop-down box, choose **On only for allowed domains**.</span></span>

    <span data-ttu-id="f05bd-121">または、Skype for Business のポリシーを開いている世界中のすべてのユーザーとの通信を有効にする場合は、 **[禁止したドメインを除いてオンに**する] を選びます。</span><span class="sxs-lookup"><span data-stu-id="f05bd-121">OR, if you want to enable communication with everyone else in the world who has open Skype for Business policies, choose **On except for blocked domains**.</span></span> <span data-ttu-id="f05bd-122">これは、既定の設定です。</span><span class="sxs-lookup"><span data-stu-id="f05bd-122">This is the default setting.</span></span>

6. <span data-ttu-id="f05bd-123">[**禁止したドメインまたは許可したドメイン**] の下で [**+**] を選択し、許可するドメイン名を追加します。</span><span class="sxs-lookup"><span data-stu-id="f05bd-123">Under **Blocked or allowed domains**, choose **+** and add the name of the domain you want to allow.</span></span>

7. <span data-ttu-id="f05bd-124">他の組織の管理者が、 **Skype For business 管理センター**でこれらと同じ手順を実行していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f05bd-124">Make sure the admin in the other organization does these same steps in their **Skype for Business admin center**.</span></span> <span data-ttu-id="f05bd-125">たとえば、相手の組織の管理者は、その組織の**許可されたドメイン** のリストにお客様の会社のドメインを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f05bd-125">For example, in their **allowed domains** list, their admin needs to enter the domain for your business.</span></span>

8. <span data-ttu-id="f05bd-126">Windows ファイアウォールを使用している場合、Skype for Business は必要なポートを自動的に開きます。</span><span class="sxs-lookup"><span data-stu-id="f05bd-126">If you're using Windows Firewall, Skype for Business opens the required ports automatically.</span></span>

    <span data-ttu-id="f05bd-127">組織で別のファイアウォールソリューションを使用していて、ネットワーク上のコンピューターがインターネットに接続されないように制限する場合は、クライアントコンピューターが次の [Office 365 url と IP アドレス範囲](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges)にアクセスできることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f05bd-127">If your organization is using a different firewall solution to restrict computers on your network from connecting to the Internet, ensure your client computers are able to access the following [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).</span></span> <span data-ttu-id="f05bd-128">ファイアウォールまたはプロキシインフラストラクチャ構成の送信許可リストに fqdn を追加する必要がある場合があります。 \*\* \* api.skype.com\*\*、 \* **users.storage.live.com**、 **graph.skype.com**。</span><span class="sxs-lookup"><span data-stu-id="f05bd-128">This may require adding the FQDNs to the outbound allow list in your firewall or proxy infrastructure configuration: **\*.api.skype.com**, \***.users.storage.live.com**, and **graph.skype.com**.</span></span> <span data-ttu-id="f05bd-129">ファイアウォールでこれらのポートを開く方法については、付属のマニュアルを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f05bd-129">For instructions on how to open these ports in your firewall, check the documentation that came with it.</span></span>

    <span data-ttu-id="f05bd-130">開く必要があるすべてのポートの一覧については、「 [Office 365 の url と IP アドレスの範囲](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f05bd-130">For a list of all ports you need to open, see [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).</span></span>

9. <span data-ttu-id="f05bd-131">組織の管理者が次の手順も実行していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f05bd-131">Make sure that the administrator in the organization has also followed these steps.</span></span>

10. <span data-ttu-id="f05bd-132">**テストに最大24時間待機**します。</span><span class="sxs-lookup"><span data-stu-id="f05bd-132">**WAIT UP TO 24 HOURS TO TEST**.</span></span> <span data-ttu-id="f05bd-133">外部通信設定を変更すると、変更がすべてのデータセンターに反映されるまでに最大24時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="f05bd-133">When you change the external communications settings, it can take up to 24 hours for the changes to populate across all the data centers.</span></span>

<span data-ttu-id="f05bd-134">![Skype では、 ](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) 無料のコンシューマーアプリである skype を使用しているすべてのユーザーに対して、検索と IM を許可することができます。</span><span class="sxs-lookup"><span data-stu-id="f05bd-134">![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) You can allow your users to search for and IM with everyone who uses Skype, the free consumer app!</span></span> <span data-ttu-id="f05bd-135">詳細については、「 [skype For business ユーザーが skype の連絡先を追加できる](let-skype-for-business-users-add-skype-contacts.md)ようにする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f05bd-135">To learn more, see [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span>
  
## <a name="test-and-troubleshoot"></a><span data-ttu-id="f05bd-136">テストとトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="f05bd-136">Test and troubleshoot</span></span>

<span data-ttu-id="f05bd-137"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="f05bd-137"><a name="bk_preview"> </a></span></span>

 <span data-ttu-id="f05bd-138">**企業間の通信を設定する場合に最もよく発生する問題は、[Office 365 の URL と IP アドレスの範囲](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges)の設定ミスによるものです。**</span><span class="sxs-lookup"><span data-stu-id="f05bd-138">**The most common issue people encounter when setting up business-to-business communication is getting their [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) right.**</span></span>
  
<span data-ttu-id="f05bd-139">セットアップをテストするには、会社のファイアウォールの背後にない Skype for Business の連絡先が必要です。</span><span class="sxs-lookup"><span data-stu-id="f05bd-139">To test your setup, you need a contact on Skype for Business who's not behind your company firewall.</span></span>
  
1. <span data-ttu-id="f05bd-140">外部通信設定を変更したら、 **最大24時間待機**してテストします。</span><span class="sxs-lookup"><span data-stu-id="f05bd-140">After you change your external communications settings, **WAIT UP TO 24 HOURS TO TEST**.</span></span>

2. <span data-ttu-id="f05bd-141">Skype for Business で、Skype for Business で連絡先を検索し、チャットのリクエストを送信します。</span><span class="sxs-lookup"><span data-stu-id="f05bd-141">In Skype for Business, search for your contact in Skype for Business, and send a request to chat.</span></span>

    <span data-ttu-id="f05bd-142">会社のポリシーのために送信できなかったというメッセージが表示された場合は、 [Office 365 の url と IP アドレスの範囲](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges)を再確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f05bd-142">If you get a message that it couldn't be sent due to company policy, you need to double-check your [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).</span></span>

3. <span data-ttu-id="f05bd-143">Skype for Business の連絡先に、チャットのリクエストを送信するように依頼します。</span><span class="sxs-lookup"><span data-stu-id="f05bd-143">Ask your Skype for Business contact to send you a request to chat.</span></span> <span data-ttu-id="f05bd-144">相手からの要求を受信できない場合は、お客様のファイアウォールの設定に問題があります (相手のファイアウォールの設定が正しいことが確認済みであることが前提)。</span><span class="sxs-lookup"><span data-stu-id="f05bd-144">If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span></span>

4. <span data-ttu-id="f05bd-145">ファイアウォールで問題が発生しているかどうかをテストするもう1つの方法は、コーヒーショップなど、ファイアウォールを隔てた wifi サイトに移行することです。</span><span class="sxs-lookup"><span data-stu-id="f05bd-145">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall, such as a coffee shop.</span></span> <span data-ttu-id="f05bd-146">Skype for Business を使用して、連絡先に依頼を送信してチャットします。</span><span class="sxs-lookup"><span data-stu-id="f05bd-146">Use Skype for Business to send a request to your contact to chat.</span></span> <span data-ttu-id="f05bd-147">メッセージをその場所からは送信できる一方、職場からは送信できない場合は、問題の原因は職場のファイアウォールであることが特定できます。</span><span class="sxs-lookup"><span data-stu-id="f05bd-147">If the message goes through there, but not when you're at work, then you know the problem is your firewall.</span></span>

## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a><span data-ttu-id="f05bd-148">他のビジネスに接続しているときに、他のユーザーを検索して見つける方法</span><span class="sxs-lookup"><span data-stu-id="f05bd-148">How to find others, and be found, when connecting with another business</span></span>

<span data-ttu-id="f05bd-149"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="f05bd-149"><a name="bk_preview"> </a></span></span>

<span data-ttu-id="f05bd-150">他の Skype for Business ユーザーとの外部通信を有効にすると、ユーザーはサインイン名を検索して、フェデレーションされた Skype for Business ユーザーを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="f05bd-150">After you enable external communication with other Skype for Business users, your users can find federated Skype for Business users by searching for their sign-in names.</span></span> <span data-ttu-id="f05bd-151">例として、Rob@contoso.com があります。</span><span class="sxs-lookup"><span data-stu-id="f05bd-151">An example is Rob@contoso.com.</span></span> <span data-ttu-id="f05bd-152">次に、ユーザーを連絡先リストに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f05bd-152">Then they will need to add the person to their list of contacts.</span></span>
  
![フェデレーションされたビジネスでユーザーを検索するには、メールアドレスを検索する必要があります (通常、サインイン名でもあります)。](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a><span data-ttu-id="f05bd-154">フェデレーションされたビジネスとの通信をセットアップするためのヒント</span><span class="sxs-lookup"><span data-stu-id="f05bd-154">Tips on setting up communications with federated businesses</span></span>

<span data-ttu-id="f05bd-155"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="f05bd-155"><a name="bk_preview"> </a></span></span>

- <span data-ttu-id="f05bd-156">Skype for Business 2015 と Skype for Business Online の間のフェデレーションを構成するには、「 [skype For Business online とのフェデレーションを構成](https://technet.microsoft.com/library/jj205126.aspx)する」の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f05bd-156">To configure federation between Skype for Business 2015 and Skype for Business Online, see this  article: [Configure federation with Skype for Business Online](https://technet.microsoft.com/library/jj205126.aspx).</span></span>

- <span data-ttu-id="f05bd-157">Lync と Skype for Business Online の間のフェデレーションを構成するには、次の記事を参照してください。 [Lync online の顧客のためのフェデレーションサポートの構成](https://technet.microsoft.com/library/hh202193.aspx)</span><span class="sxs-lookup"><span data-stu-id="f05bd-157">To configure federation between Lync and Skype for Business Online, see this  article: [Configuring Federation Support for a Lync Online Customer](https://technet.microsoft.com/library/hh202193.aspx).</span></span>

- <span data-ttu-id="f05bd-158">Microsoft 365 または Office 365 の2つの Skype for Business ユーザーが別々のドメインで相互に通信している場合は、両方の組織でオンになっている Skype for Business の機能 (たとえば、ビデオの会話やデスクトップ共有など) のみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f05bd-158">When two Skype for Business users in Microsoft 365 or Office 365 are communicating with each other on separate domains, they can only use Skype for Business features (for example, video conversations or desktop sharing) that are turned on in both organizations.</span></span>

- <span data-ttu-id="f05bd-159">組織内の Skype for Business ユーザーが In-Place または訴訟ホールドに設定されている場合、そのユーザーと他の Skype for Business または Skype ユーザー間の IM 会話は、そのユーザーのメールボックスの **回復可能なアイテム** に保存されます。</span><span class="sxs-lookup"><span data-stu-id="f05bd-159">If a Skype for Business user in your organization is put on an In-Place or Litigation Hold, any IM conversations between that user and other Skype for Business or Skype users will be saved in **Recoverable Items** in their mailbox.</span></span> <span data-ttu-id="f05bd-160">これらの会話は、自分のメールボックスの [ **会話履歴** ] フォルダーには保存されません。</span><span class="sxs-lookup"><span data-stu-id="f05bd-160">These conversations aren't saved in the **Conversations History** folder in their mailbox.</span></span>

## <a name="turn-off-external-communication-for-specific-individuals"></a><span data-ttu-id="f05bd-161">特定の個人の外部通信をオフにする</span><span class="sxs-lookup"><span data-stu-id="f05bd-161">Turn off external communication for specific individuals</span></span>

<span data-ttu-id="f05bd-162"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="f05bd-162"><a name="bk_preview"> </a></span></span>

<span data-ttu-id="f05bd-163">組織全体の外部通信を有効にした後は、特定の個人に対してのみオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="f05bd-163">After you enable external communication for your entire business, you can turn it off for only specific individuals.</span></span>
  
1. <span data-ttu-id="f05bd-164">Microsoft 365 または Office 365 管理者アカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="f05bd-164">Sign in with your Microsoft 365 or Office 365 admin account.</span></span>

2. <span data-ttu-id="f05bd-165">管理センターで、[アクティブな**ユーザー**] に移動  >  **Active users**します。</span><span class="sxs-lookup"><span data-stu-id="f05bd-165">In the admin center, go to **Users** > **Active users**.</span></span>

3. <span data-ttu-id="f05bd-166">ユーザーの一覧でユーザーを選び、[ **詳細設定**] で [ **Skype for business のプロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f05bd-166">In the list of users, choose the user, and then, under **More Settings**, click **Edit Skype for Business properties**.</span></span>

    ![Skype for Business を選ぶ](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. <span data-ttu-id="f05bd-168">**Skype For business 管理センター**で、[**外部通信**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="f05bd-168">In the **Skype for Business admin center**, choose **External communications**.</span></span>

    <span data-ttu-id="f05bd-169">[ **オプション** ] ページで、すべての選択肢が選択されます。</span><span class="sxs-lookup"><span data-stu-id="f05bd-169">On the **Options** page, all of the choices will be selected.</span></span> <span data-ttu-id="f05bd-170">無効にする通信をオフにします。</span><span class="sxs-lookup"><span data-stu-id="f05bd-170">Clear the communications you want to disable.</span></span> <span data-ttu-id="f05bd-171">次の画像は、Jakob が他の Skype ユーザとは関係なく、他の信頼できる会社のユーザと通信できることを示しています。</span><span class="sxs-lookup"><span data-stu-id="f05bd-171">The following image shows that Jakob will be able to communicate with people in other trusted businesses, but not with other Skype users.</span></span>

    ![外部連絡先を選ぶ](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. <span data-ttu-id="f05bd-173">[ **保存**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="f05bd-173">Choose **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="f05bd-174">変更が有効になるまで最長で24時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="f05bd-174">You may have to wait for up to 24 hours for your changes to take effect.</span></span>
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]

## <a name="related-topics"></a><span data-ttu-id="f05bd-175">関連トピック</span><span class="sxs-lookup"><span data-stu-id="f05bd-175">Related topics</span></span>

<span data-ttu-id="f05bd-176"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="f05bd-176"><a name="bk_preview"> </a></span></span>

[<span data-ttu-id="f05bd-177">Skype for Business Online をセットアップする</span><span class="sxs-lookup"><span data-stu-id="f05bd-177">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)
  
[<span data-ttu-id="f05bd-178">Skype for Business ユーザーが Skype の連絡先を追加できるようにする</span><span class="sxs-lookup"><span data-stu-id="f05bd-178">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)
  