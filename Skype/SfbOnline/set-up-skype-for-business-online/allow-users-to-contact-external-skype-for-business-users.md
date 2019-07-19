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
f1_keywords:
- For O365M_ShareLync
- ms.lync.lac.OrgExternalAccess
- ms.lync.lac.skypefederation
- O365E_HRCLYNC _ SipFederationSrvRecordVerified_FL312122
- O365E_ShareLync
- O365M_ShareLync
- O365P_ExternalCommDesc
- O365P_ShareLync
ms.custom:
- Setup
- LIL_Placement
description: 'ユーザーが別の組織のユーザーと会話したり、外部からの連絡をしたりできるように Skype for Business を構成する方法について説明します。 '
ms.openlocfilehash: 570861f532371dc8eca253956ffdd200e60f5990
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/18/2019
ms.locfileid: "35792686"
---
# <a name="allow-users-to-contact-external-skype-for-business-users"></a><span data-ttu-id="07e05-103">ユーザーが外部の Skype for Business ユーザーに連絡できるようにする</span><span class="sxs-lookup"><span data-stu-id="07e05-103">Allow users to contact external Skype for Business users</span></span>

> [!NOTE]
> <span data-ttu-id="07e05-104">Skype for Business のフェデレーションは、21Vianet および Office 365 ドイツの組織が運用している Office 365 では使用できません。</span><span class="sxs-lookup"><span data-stu-id="07e05-104">Skype for Business federation isn't available to Office 365 operated by 21Vianet and Office 365 Germany organizations.</span></span> 
  
<span data-ttu-id="07e05-105">次の場合、この記事で説明する手順をご利用ください。</span><span class="sxs-lookup"><span data-stu-id="07e05-105">Use the steps in this article when:</span></span>
  
- <span data-ttu-id="07e05-106">会社のさまざまなドメインにユーザーがいる。</span><span class="sxs-lookup"><span data-stu-id="07e05-106">You have users on different domains in your business.</span></span> <span data-ttu-id="07e05-107">たとえば、Rob@ContosoEast.com と Ann@ContosoWest.com のような場合。</span><span class="sxs-lookup"><span data-stu-id="07e05-107">For example, Rob@ContosoEast.com and Ann@ContosoWest.com.</span></span>
    
- <span data-ttu-id="07e05-108">組織内のユーザーが Skype for Business を使用して、組織外の特定の企業のユーザーに連絡できるようにする場合。</span><span class="sxs-lookup"><span data-stu-id="07e05-108">You want the people in your organization to use Skype for Business to contact people in specific businesses outside of your organization.</span></span>
    
- <span data-ttu-id="07e05-109">Skype for Business を使用している他のユーザーが、自分のメールアドレスを使用して、あなたを検索して連絡できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="07e05-109">You want anyone else in the world who uses Skype for Business to be able to find and contact you, using your email address.</span></span> <span data-ttu-id="07e05-110">Skype for Business の既定の設定を使用している場合は、これが自動的に有効になります。</span><span class="sxs-lookup"><span data-stu-id="07e05-110">If you and they use the default Skype for Business settings, this will work automatically.</span></span> <span data-ttu-id="07e05-111">そうでない場合は、その構成でドメインがブロックされていないことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07e05-111">If they don't, then they need to make sure their configuration isn't blocking your domain.</span></span>
    
## <a name="enable-business-to-business-communications-for-your-users"></a><span data-ttu-id="07e05-112">ユーザーに対する企業間の通信を有効にする</span><span class="sxs-lookup"><span data-stu-id="07e05-112">Enable business-to-business communications for your users</span></span>
<span data-ttu-id="07e05-113"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="07e05-113"></span></span>

<span data-ttu-id="07e05-114">この操作を行うには、両方の組織の Office 365 で[管理者権限](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="07e05-114">You must have [admin permissions](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) in Office 365 in both organizations to do this.</span></span>

<span data-ttu-id="07e05-115">![](../images/teams-logo-30x30.png) **Teams 管理センターを使用し**た Microsoft Teams ロゴを示すアイコン</span><span class="sxs-lookup"><span data-stu-id="07e05-115">![An icon showing the Microsoft Teams logo](../images/teams-logo-30x30.png) **Using the Teams admin center**</span></span>
  
1. <span data-ttu-id="07e05-116">Office 365 管理者アカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="07e05-116">Sign in with your Office 365 admin account.</span></span> 
    
2. <span data-ttu-id="07e05-117">管理センターで、[**管理センター** > **チーム**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="07e05-117">In the admin center, go to **Admin Centers** > **Teams**.</span></span>
    
    ![Teams 管理者を選びます。](../images/MS-Teams-Admin.png)
  
3. <span data-ttu-id="07e05-119">**Teams センター**で、「 **Skype** > **レガシーポータル** 
 ![」「sfb レガシーポータルを選択」を選択します。](../images/SFBlegacy-size65.png)</span><span class="sxs-lookup"><span data-stu-id="07e05-119">In the **Teams center**, choose **Skype** > **Legacy Portal** 
![Choose the SfB Legacy Portal.](../images/SFBlegacy-size65.png)</span></span>
 
4. <span data-ttu-id="07e05-120">**Skype for business 管理センター**で、[**組織** > の**外部通信**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="07e05-120">In the **Skype for Business admin center** , choose **Organization** > **External communications**.</span></span>
5. <span data-ttu-id="07e05-121">特定の会社や別のドメインのユーザーとの通信を設定するには、ドロップダウン ボックスで [**許可したドメインに対してのみオンにする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="07e05-121">To set up communication with a specific business or with users in another domain, in the drop-down box, choose **On only for allowed domains**.</span></span>
    
    <span data-ttu-id="07e05-122">または、Skype for Business のポリシーを開いている世界中のすべてのユーザーとの通信を有効にする場合は、 **[禁止したドメインを除いてオンに**する] を選びます。</span><span class="sxs-lookup"><span data-stu-id="07e05-122">OR, if you want to enable communication with everyone else in the world who has open Skype for Business policies, choose **On except for blocked domains**.</span></span> <span data-ttu-id="07e05-123">これは、既定の設定です。</span><span class="sxs-lookup"><span data-stu-id="07e05-123">This is the default setting.</span></span>
    
6. <span data-ttu-id="07e05-124">[**禁止したドメインまたは許可したドメイン**] の下で [**+**] を選択し、許可するドメイン名を追加します。</span><span class="sxs-lookup"><span data-stu-id="07e05-124">Under **Blocked or allowed domains**, choose **+** and add the name of the domain you want to allow.</span></span>
    
7. <span data-ttu-id="07e05-125">他の組織の管理者が、 **Skype For business 管理センター**でこれらと同じ手順を実行していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="07e05-125">Make sure the admin in the other organization does these same steps in their **Skype for Business admin center**.</span></span> <span data-ttu-id="07e05-126">たとえば、相手の組織の管理者は、その組織の**許可されたドメイン** のリストにお客様の会社のドメインを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07e05-126">For example, in their **allowed domains** list, their admin needs to enter the domain for your business.</span></span>
    
8. <span data-ttu-id="07e05-127">Windows ファイアウォールを使用している場合、Skype for Business は必要なポートを自動的に開きます。</span><span class="sxs-lookup"><span data-stu-id="07e05-127">If you're using Windows Firewall, Skype for Business opens the required ports automatically.</span></span>
    
    <span data-ttu-id="07e05-128">組織で別のファイアウォールソリューションを使用していて、ネットワーク上のコンピューターがインターネットに接続されないように制限する場合は、クライアントコンピューターが次の[Office 365 url と IP アドレス範囲](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges)にアクセスできることを確認します。</span><span class="sxs-lookup"><span data-stu-id="07e05-128">If your organization is using a different firewall solution to restrict computers on your network from connecting to the Internet, ensure your client computers are able to access the following [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).</span></span> <span data-ttu-id="07e05-129">ファイアウォールまたは\*プロキシインフラストラクチャ構成\*\* \*\*\* の送信許可リストに fqdn を追加する必要がある場合があります。 api.skype.com、 **users.storage.live.com**、 **graph.skype.com**。</span><span class="sxs-lookup"><span data-stu-id="07e05-129">This may require adding the FQDNs to the outbound allow list in your firewall or proxy infrastructure configuration: **\*.api.skype.com**, \***.users.storage.live.com**, and **graph.skype.com**.</span></span> <span data-ttu-id="07e05-130">ファイアウォールでこれらのポートを開く方法については、付属のマニュアルを確認してください。</span><span class="sxs-lookup"><span data-stu-id="07e05-130">For instructions on how to open these ports in your firewall, check the documentation that came with it.</span></span>
    
    <span data-ttu-id="07e05-131">開く必要があるすべてのポートの一覧については、「 [Office 365 の url と IP アドレスの範囲](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07e05-131">For a list of all ports you need to open, see [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).</span></span>

9. <span data-ttu-id="07e05-132">組織の管理者が次の手順も実行していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="07e05-132">Make sure that the administrator in the organization has also followed these steps.</span></span>
    
10. <span data-ttu-id="07e05-133">**テストに最大24時間待機**します。</span><span class="sxs-lookup"><span data-stu-id="07e05-133">**WAIT UP TO 24 HOURS TO TEST**.</span></span> <span data-ttu-id="07e05-134">外部通信設定を変更すると、すべてのデータセンターに変更が反映されるまでに最大24時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="07e05-134">Any time you change the external communications settings, it can take up to 24 hours for the changes to populate across all the data centers.</span></span>
    
<span data-ttu-id="07e05-135">![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png)では、無料のコンシューマーアプリである skype を使用しているすべてのユーザーに対して、検索と IM を許可することができます。</span><span class="sxs-lookup"><span data-stu-id="07e05-135">![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) You can allow your users to search for and IM with everyone who uses Skype, the free consumer app!</span></span> <span data-ttu-id="07e05-136">詳細については、「 [skype For business ユーザーが skype の連絡先を追加できる](let-skype-for-business-users-add-skype-contacts.md)ようにする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07e05-136">To learn more, see [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span>
  
## <a name="test-and-troubleshoot"></a><span data-ttu-id="07e05-137">テストとトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="07e05-137">Test and troubleshoot</span></span>
<span data-ttu-id="07e05-138"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="07e05-138"></span></span>

 <span data-ttu-id="07e05-139">**企業間の通信を設定する場合に最もよく発生する問題は、[Office 365 の URL と IP アドレスの範囲](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges)の設定ミスによるものです。**</span><span class="sxs-lookup"><span data-stu-id="07e05-139">**The most common issue people encounter when setting up business-to-business communication is getting their [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) right.**</span></span>
  
<span data-ttu-id="07e05-140">セットアップをテストするには、会社のファイアウォールの背後にない Skype for Business の連絡先が必要です。</span><span class="sxs-lookup"><span data-stu-id="07e05-140">To test your setup, you need a contact on Skype for Business who's not behind your company firewall.</span></span>
  
1. <span data-ttu-id="07e05-141">外部通信設定を変更したら、**最大24時間待機**してテストします。</span><span class="sxs-lookup"><span data-stu-id="07e05-141">After you change your external communications settings, **WAIT UP TO 24 HOURS TO TEST**.</span></span>
    
2. <span data-ttu-id="07e05-142">Skype for Business で、Skype for Business で連絡先を検索し、チャットのリクエストを送信します。</span><span class="sxs-lookup"><span data-stu-id="07e05-142">In Skype for Business, search for your contact in Skype for Business, and send a request to chat.</span></span>
    
    <span data-ttu-id="07e05-143">会社のポリシーのために送信できなかったというメッセージが表示された場合は、 [Office 365 の url と IP アドレスの範囲](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges)を再確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07e05-143">If you get a message that it couldn't be sent due to company policy, you need to double-check your [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).</span></span>
    
3. <span data-ttu-id="07e05-144">Skype for Business の連絡先に、チャットのリクエストを送信するように依頼します。</span><span class="sxs-lookup"><span data-stu-id="07e05-144">Ask your Skype for Business contact to send you a request to chat.</span></span> <span data-ttu-id="07e05-145">相手からの要求を受信できない場合は、お客様のファイアウォールの設定に問題があります (相手のファイアウォールの設定が正しいことが確認済みであることが前提)。</span><span class="sxs-lookup"><span data-stu-id="07e05-145">If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span></span>
    
4. <span data-ttu-id="07e05-146">ファイアウォールで問題があるかどうかをテストするには、喫茶店など、ファイアウォールの背後にない wifi 上の場所にアクセスすることと、Skype for Business を使って、コンタクトに要求を送信してチャットする方法もあります。</span><span class="sxs-lookup"><span data-stu-id="07e05-146">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Skype for Business to send a request to your contact to chat.</span></span> <span data-ttu-id="07e05-147">メッセージをその場所からは送信できる一方、職場からは送信できない場合は、問題の原因は職場のファイアウォールであることが特定できます。</span><span class="sxs-lookup"><span data-stu-id="07e05-147">If the message goes through there, but not when you're at work, then you know the problem is your firewall.</span></span>
    
## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a><span data-ttu-id="07e05-148">他のビジネスに接続しているときに、他のユーザーを検索して見つける方法</span><span class="sxs-lookup"><span data-stu-id="07e05-148">How to find others, and be found, when connecting with another business</span></span>
<span data-ttu-id="07e05-149"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="07e05-149"></span></span>

<span data-ttu-id="07e05-150">他の Skype for Business ユーザーとの外部通信を有効にすると、ユーザーはサインイン名 (たとえば、Rob@contoso.com) を検索して、フェデレーションされた Skype for Business ユーザーを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="07e05-150">After you enable external communication with other Skype for Business users, your users can find federated Skype for Business users by searching for their sign-in name: for example, Rob@contoso.com.</span></span> <span data-ttu-id="07e05-151">次に、ユーザーを連絡先リストに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07e05-151">Then they will need to add the person to their list of contacts.</span></span>
  
![フェデレーションされたビジネスでユーザーを検索するには、メールアドレスを検索する必要があります (通常、サインイン名でもあります)。](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a><span data-ttu-id="07e05-153">フェデレーションされたビジネスとの通信をセットアップするためのヒント</span><span class="sxs-lookup"><span data-stu-id="07e05-153">Tips on setting up communications with federated businesses</span></span>
<span data-ttu-id="07e05-154"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="07e05-154"></span></span>

- <span data-ttu-id="07e05-155">Skype for Business 2015 と Skype for Business Online の間のフェデレーションを構成するには、「 [skype For Business online とのフェデレーションを構成](https://technet.microsoft.com/en-us/library/jj205126.aspx)する」の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07e05-155">To configure federation between Skype for Business 2015 and Skype for Business Online, see this  article: [Configure federation with Skype for Business Online](https://technet.microsoft.com/en-us/library/jj205126.aspx).</span></span>
    
- <span data-ttu-id="07e05-156">Lync と Skype for Business Online の間のフェデレーションを構成するには、次の記事を参照してください。 [Lync online の顧客のためのフェデレーションサポートの構成](https://technet.microsoft.com/en-us/library/hh202193.aspx)</span><span class="sxs-lookup"><span data-stu-id="07e05-156">To configure federation between Lync and Skype for Business Online, see this  article: [Configuring Federation Support for a Lync Online Customer](https://technet.microsoft.com/en-us/library/hh202193.aspx).</span></span>
    
- <span data-ttu-id="07e05-157">Office 365 の2つの Skype for Business ユーザーが別々のドメインで相互に通信している場合は、両方の組織でオンになっている Skype for Business の機能 (たとえば、ビデオの会話やデスクトップ共有など) のみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="07e05-157">When two Skype for Business users in Office 365 are communicating with each other on separate domains, they can only use Skype for Business features (for example, video conversations or desktop sharing) that are turned on in both organizations.</span></span>
    
- <span data-ttu-id="07e05-158">組織内の Skype for Business ユーザーがインプレースまたは訴訟ホールドに設定されている場合、そのユーザーと他の Skype for Business または Skype ユーザー間の IM 会話は、そのユーザーのメールボックスの**回復可能なアイテム**に保存されます。</span><span class="sxs-lookup"><span data-stu-id="07e05-158">If a Skype for Business user in your organization is put on an In-Place or Litigation Hold, any IM conversations between that user and other Skype for Business or Skype users will be saved in **Recoverable Items** in their mailbox.</span></span> <span data-ttu-id="07e05-159">これらの会話は、自分のメールボックスの [**会話履歴**] フォルダーには保存されません。</span><span class="sxs-lookup"><span data-stu-id="07e05-159">These conversations aren't saved in the **Conversations History** folder in their mailbox.</span></span>
    
## <a name="turn-off-external-communication-for-specific-individuals"></a><span data-ttu-id="07e05-160">特定の個人の外部通信をオフにする</span><span class="sxs-lookup"><span data-stu-id="07e05-160">Turn off external communication for specific individuals</span></span>
<span data-ttu-id="07e05-161"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="07e05-161"></span></span>

<span data-ttu-id="07e05-162">組織全体の外部通信を有効にした後は、特定の個人に対してのみオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="07e05-162">After you enable external communication for your entire business, you can turn it off for only specific individuals.</span></span>
  
1. <span data-ttu-id="07e05-163">Office 365 管理者アカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="07e05-163">Sign in with your Office 365 admin account.</span></span>
    
2. <span data-ttu-id="07e05-164">管理センターで、[**アクティブな\*\*\*\*ユーザー** > ] に移動します。</span><span class="sxs-lookup"><span data-stu-id="07e05-164">In the admin center, go to **Users** > **Active users**.</span></span>
    
3. <span data-ttu-id="07e05-165">ユーザーの一覧でユーザーを選び、[**詳細設定**] で [ **Skype for business のプロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="07e05-165">In the list of users, choose the user, and then, under **More Settings**, click **Edit Skype for Business properties**.</span></span>
    
    ![Skype for Business を選ぶ](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. <span data-ttu-id="07e05-167">**Skype For business 管理センター**で、[**外部通信**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="07e05-167">In the **Skype for Business admin center**, choose **External communications**.</span></span>
    
    <span data-ttu-id="07e05-168">[**オプション**] ページで、すべての選択肢が選択されます。</span><span class="sxs-lookup"><span data-stu-id="07e05-168">On the **Options** page, all of the choices will be selected.</span></span> <span data-ttu-id="07e05-169">無効にする通信をオフにします。</span><span class="sxs-lookup"><span data-stu-id="07e05-169">Clear the communications you want to disable.</span></span> <span data-ttu-id="07e05-170">次の画像は、Jakob が他の Skype ユーザとは関係なく、他の信頼できる会社のユーザと通信できることを示しています。</span><span class="sxs-lookup"><span data-stu-id="07e05-170">The following image shows that Jakob will be able to communicate with people in other trusted businesses, but not with other Skype users.</span></span>
    
    ![外部連絡先を選ぶ](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. <span data-ttu-id="07e05-172">[ **保存**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="07e05-172">Choose **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="07e05-173">変更が有効になるまで最長で24時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="07e05-173">You may have to wait for up to 24 hours for your changes to take effect.</span></span> 
  


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
   
## <a name="related-topics"></a><span data-ttu-id="07e05-174">関連トピック</span><span class="sxs-lookup"><span data-stu-id="07e05-174">Related topics</span></span>
<span data-ttu-id="07e05-175"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="07e05-175"></span></span>

[<span data-ttu-id="07e05-176">Skype for Business Online のセットアップ</span><span class="sxs-lookup"><span data-stu-id="07e05-176">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)
  
[<span data-ttu-id="07e05-177">Skype for Business ユーザーが Skype の連絡先を追加できるようにする</span><span class="sxs-lookup"><span data-stu-id="07e05-177">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)
  
  
 
