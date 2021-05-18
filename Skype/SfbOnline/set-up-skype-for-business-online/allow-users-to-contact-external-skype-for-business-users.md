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
description: 'ユーザーが別の組織Skype for Businessユーザーと話したり、外部の連絡先がユーザーと話し合うのを許可したりするために、ユーザーを構成する方法を参照してください。 '
ms.openlocfilehash: 3b4aeb2b40cf34579d3d584a50664550cd34038c
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240005"
---
# <a name="allow-users-to-contact-external-skype-for-business-users"></a><span data-ttu-id="28266-103">ユーザーが外部の Skype for Business ユーザーに連絡できるようにする</span><span class="sxs-lookup"><span data-stu-id="28266-103">Allow users to contact external Skype for Business users</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]
  
<span data-ttu-id="28266-104">次の場合、この記事で説明する手順をご利用ください。</span><span class="sxs-lookup"><span data-stu-id="28266-104">Use the steps in this article when:</span></span>
  
- <span data-ttu-id="28266-105">ビジネスの異なるドメインにユーザーがいます。</span><span class="sxs-lookup"><span data-stu-id="28266-105">You have users on different domains in your business.</span></span> <span data-ttu-id="28266-106">たとえば、Rob@ContosoEast.com と Ann@ContosoWest.com のような場合。</span><span class="sxs-lookup"><span data-stu-id="28266-106">For example, Rob@ContosoEast.com and Ann@ContosoWest.com.</span></span>

- <span data-ttu-id="28266-107">組織内のユーザーが組織外の特定のSkype for Businessのユーザーに連絡するために、ユーザーを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="28266-107">You want the people in your organization to use Skype for Business to contact people in specific businesses outside of your organization.</span></span>

- <span data-ttu-id="28266-108">世界中のユーザーがメール アドレスを使用してSkype for Businessを見つけて連絡したい場合。</span><span class="sxs-lookup"><span data-stu-id="28266-108">You want anyone else in the world who uses Skype for Business to be able to find and contact you using your email address.</span></span> <span data-ttu-id="28266-109">ユーザーとユーザーが既定の設定を使用Skype for Business、この設定は自動的に機能します。</span><span class="sxs-lookup"><span data-stu-id="28266-109">If you and they use the default Skype for Business settings, this will work automatically.</span></span> <span data-ttu-id="28266-110">ブロックされていない場合は、構成によってドメインがブロックされていないことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="28266-110">If they don't, then they need to make sure their configuration isn't blocking your domain.</span></span>

## <a name="enable-business-to-business-communications-for-your-users"></a><span data-ttu-id="28266-111">ユーザーの企業間通信を有効にする</span><span class="sxs-lookup"><span data-stu-id="28266-111">Enable business-to-business communications for your users</span></span>

<span data-ttu-id="28266-112"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="28266-112"><a name="bk_preview"> </a></span></span>

<span data-ttu-id="28266-113">この通信を[行うには、](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)両方の組織Microsoft 365またはOffice 365管理者アクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="28266-113">You must have [admin permissions](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) in Microsoft 365 or Office 365 in both organizations to do this communication.</span></span>

<span data-ttu-id="28266-114">![管理センターを使用Microsoft Teams ](../images/teams-logo-30x30.png) **ロゴをTeamsアイコン**</span><span class="sxs-lookup"><span data-stu-id="28266-114">![An icon showing the Microsoft Teams logo](../images/teams-logo-30x30.png) **Using the Teams admin center**</span></span>
  
1. <span data-ttu-id="28266-115">管理者アカウントを使用Microsoft 365またはOffice 365サインインします。</span><span class="sxs-lookup"><span data-stu-id="28266-115">Sign in with your Microsoft 365 or Office 365 admin account.</span></span>

2. <span data-ttu-id="28266-116">管理センターで、[管理センター] に **移動Teams。**  >  </span><span class="sxs-lookup"><span data-stu-id="28266-116">In the admin center, go to **Admin Centers** > **Teams**.</span></span>

    ![[管理者] Teams選択します。](../images/MS-Teams-Admin.png)
  
3. <span data-ttu-id="28266-118">[Teams **センターで、[レガ** シ **ポータルSkype** SfB レガシ ポータルの選択 >  
  ![ ] を選択します。](../images/SFBlegacy-size65.png)</span><span class="sxs-lookup"><span data-stu-id="28266-118">In the **Teams center**, choose **Skype** > **Legacy Portal**
![Choose the SfB Legacy Portal.](../images/SFBlegacy-size65.png)</span></span>

4. <span data-ttu-id="28266-119">**Skype for Business 管理センター** で、[**組織**]  >  [**外部通信**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="28266-119">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span>
5. <span data-ttu-id="28266-120">特定の会社や別のドメインのユーザーとの通信を設定するには、ドロップダウン ボックスで [**許可したドメインに対してのみオンにする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="28266-120">To set up communication with a specific business or with users in another domain, in the drop-down box, choose **On only for allowed domains**.</span></span>

    <span data-ttu-id="28266-121">または、Skype for Business ポリシーを開いている世界中の他のすべてのユーザーとの通信を有効にする場合は、ブロックされているドメインを除いて [オン] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="28266-121">OR, if you want to enable communication with everyone else in the world who has open Skype for Business policies, choose **On except for blocked domains**.</span></span> <span data-ttu-id="28266-122">これは、既定の設定です。</span><span class="sxs-lookup"><span data-stu-id="28266-122">This is the default setting.</span></span>

6. <span data-ttu-id="28266-123">[**禁止したドメインまたは許可したドメイン**] の下で [**+**] を選択し、許可するドメイン名を追加します。</span><span class="sxs-lookup"><span data-stu-id="28266-123">Under **Blocked or allowed domains**, choose **+** and add the name of the domain you want to allow.</span></span>

7. <span data-ttu-id="28266-124">他の組織の管理者が、管理センター で同じ手順 **を実行Skype for Business確認します**。</span><span class="sxs-lookup"><span data-stu-id="28266-124">Make sure the admin in the other organization does these same steps in their **Skype for Business admin center**.</span></span> <span data-ttu-id="28266-125">たとえば、相手の組織の管理者は、その組織の **許可されたドメイン** のリストにお客様の会社のドメインを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="28266-125">For example, in their **allowed domains** list, their admin needs to enter the domain for your business.</span></span>

8. <span data-ttu-id="28266-126">ファイアウォールを使用している場合Windows必要Skype for Businessポートが自動的に開きます。</span><span class="sxs-lookup"><span data-stu-id="28266-126">If you're using Windows Firewall, Skype for Business opens the required ports automatically.</span></span>

    <span data-ttu-id="28266-127">組織が別のファイアウォール ソリューションを使用してネットワーク上のコンピューターがインターネットに接続されるのを制限している場合は、クライアント コンピューターが次の Office 365 URL と[IP](/microsoftteams/office-365-urls-ip-address-ranges)アドレス範囲 にアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="28266-127">If your organization is using a different firewall solution to restrict computers on your network from connecting to the Internet, ensure your client computers are able to access the following [Office 365 URLs and IP address ranges](/microsoftteams/office-365-urls-ip-address-ranges).</span></span> <span data-ttu-id="28266-128">これには、ファイアウォールまたはプロキシ インフラストラクチャの構成 **\* (.api.skype.com、.users.storage.live.com、** および の送信許可リストに FQDN を追加する必要 \* \*\*\*\*graph.skype.com。\*\*</span><span class="sxs-lookup"><span data-stu-id="28266-128">This may require adding the FQDNs to the outbound allow list in your firewall or proxy infrastructure configuration: **\*.api.skype.com**, \**_.users.storage.live.com_*, and **graph.skype.com**.</span></span> <span data-ttu-id="28266-129">これらのポートをファイアウォールで開く方法については、ファイアウォールに付属のドキュメントを確認してください。</span><span class="sxs-lookup"><span data-stu-id="28266-129">For instructions on how to open these ports in your firewall, check the documentation that came with it.</span></span>

    <span data-ttu-id="28266-130">開く必要があるすべてのポートの一覧については、「URL と IP アドレス範囲Office 365[を参照してください](/microsoftteams/office-365-urls-ip-address-ranges)。</span><span class="sxs-lookup"><span data-stu-id="28266-130">For a list of all ports you need to open, see [Office 365 URLs and IP address ranges](/microsoftteams/office-365-urls-ip-address-ranges).</span></span>

9. <span data-ttu-id="28266-131">組織の管理者もこれらの手順に従っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="28266-131">Make sure that the administrator in the organization has also followed these steps.</span></span>

10. <span data-ttu-id="28266-132">**テストするには、最大 24 時間待機します**。</span><span class="sxs-lookup"><span data-stu-id="28266-132">**WAIT UP TO 24 HOURS TO TEST**.</span></span> <span data-ttu-id="28266-133">外部通信設定を変更すると、変更がすべてのデータ センターに設定されるのに最大 24 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="28266-133">When you change the external communications settings, it can take up to 24 hours for the changes to populate across all the data centers.</span></span>

<span data-ttu-id="28266-134">![](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png)Skype無料のコンシューマー アプリである Skype を使用しているすべてのユーザーと IM を検索および IM することができます。</span><span class="sxs-lookup"><span data-stu-id="28266-134">![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) You can allow your users to search for and IM with everyone who uses Skype, the free consumer app!</span></span> <span data-ttu-id="28266-135">詳細については、「ユーザーが連絡先を[追加Skype for Businessする」Skype参照してください](let-skype-for-business-users-add-skype-contacts.md)。</span><span class="sxs-lookup"><span data-stu-id="28266-135">To learn more, see [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span>
  
## <a name="test-and-troubleshoot"></a><span data-ttu-id="28266-136">テストとトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="28266-136">Test and troubleshoot</span></span>

<span data-ttu-id="28266-137"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="28266-137"><a name="bk_preview"> </a></span></span>

 <span data-ttu-id="28266-138">**企業間の通信を設定する場合に最もよく発生する問題は、[Office 365 の URL と IP アドレスの範囲](/microsoftteams/office-365-urls-ip-address-ranges)の設定ミスによるものです。**</span><span class="sxs-lookup"><span data-stu-id="28266-138">**The most common issue people encounter when setting up business-to-business communication is getting their [Office 365 URLs and IP address ranges](/microsoftteams/office-365-urls-ip-address-ranges) right.**</span></span>
  
<span data-ttu-id="28266-139">セットアップをテストするには、会社のファイアウォールの背後にSkype for Businessの連絡先が必要です。</span><span class="sxs-lookup"><span data-stu-id="28266-139">To test your setup, you need a contact on Skype for Business who's not behind your company firewall.</span></span>
  
1. <span data-ttu-id="28266-140">外部通信の設定を変更した後、テスト **するまで最大 24 時間待ちます**。</span><span class="sxs-lookup"><span data-stu-id="28266-140">After you change your external communications settings, **WAIT UP TO 24 HOURS TO TEST**.</span></span>

2. <span data-ttu-id="28266-141">このSkype for Businessで連絡先を検索しSkype for Businessチャットに要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="28266-141">In Skype for Business, search for your contact in Skype for Business, and send a request to chat.</span></span>

    <span data-ttu-id="28266-142">会社のポリシーが原因で送信できなかったというメッセージが表示された場合は、OFFICE 365 URL と IP アドレス範囲を確認[する必要があります](/microsoftteams/office-365-urls-ip-address-ranges)。</span><span class="sxs-lookup"><span data-stu-id="28266-142">If you get a message that it couldn't be sent due to company policy, you need to double-check your [Office 365 URLs and IP address ranges](/microsoftteams/office-365-urls-ip-address-ranges).</span></span>

3. <span data-ttu-id="28266-143">他のSkype for Businessに、チャットのリクエストを送信してください。</span><span class="sxs-lookup"><span data-stu-id="28266-143">Ask your Skype for Business contact to send you a request to chat.</span></span> <span data-ttu-id="28266-144">相手からの要求を受信できない場合は、お客様のファイアウォールの設定に問題があります (相手のファイアウォールの設定が正しいことが確認済みであることが前提)。</span><span class="sxs-lookup"><span data-stu-id="28266-144">If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span></span>

4. <span data-ttu-id="28266-145">問題がファイアウォールであるかどうかをテストするもう 1 つの方法は、コーヒー ショップなどのファイアウォールの背後ではない Wi-Fi の場所に移動する方法です。</span><span class="sxs-lookup"><span data-stu-id="28266-145">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall, such as a coffee shop.</span></span> <span data-ttu-id="28266-146">[Skype for Businessを使用して、連絡先にチャットに要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="28266-146">Use Skype for Business to send a request to your contact to chat.</span></span> <span data-ttu-id="28266-147">メッセージをその場所からは送信できる一方、職場からは送信できない場合は、問題の原因は職場のファイアウォールであることが特定できます。</span><span class="sxs-lookup"><span data-stu-id="28266-147">If the message goes through there, but not when you're at work, then you know the problem is your firewall.</span></span>

## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a><span data-ttu-id="28266-148">別のビジネスに接続するときに、他のユーザーを見つけて見つける方法</span><span class="sxs-lookup"><span data-stu-id="28266-148">How to find others, and be found, when connecting with another business</span></span>

<span data-ttu-id="28266-149"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="28266-149"><a name="bk_preview"> </a></span></span>

<span data-ttu-id="28266-150">他のユーザーとの外部通信を有効Skype for Business、ユーザーはサインイン名を検索Skype for Businessフェデレーション ユーザーを検索できます。</span><span class="sxs-lookup"><span data-stu-id="28266-150">After you enable external communication with other Skype for Business users, your users can find federated Skype for Business users by searching for their sign-in names.</span></span> <span data-ttu-id="28266-151">たとえば、次 Rob@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="28266-151">An example is Rob@contoso.com.</span></span> <span data-ttu-id="28266-152">その後、連絡先のリストにユーザーを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="28266-152">Then they will need to add the person to their list of contacts.</span></span>
  
![フェデレーションビジネスのユーザーを見つけるには、そのユーザーのメール アドレスを検索する必要があります (通常はサインイン名です)。](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a><span data-ttu-id="28266-154">ヒントとの通信の設定に関する詳細</span><span class="sxs-lookup"><span data-stu-id="28266-154">Tips on setting up communications with federated businesses</span></span>

<span data-ttu-id="28266-155"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="28266-155"><a name="bk_preview"> </a></span></span>

- <span data-ttu-id="28266-156">Skype for Business 2015 と Skype for Business Online の間のフェデレーションを構成するには、「Skype for Business Online とのフェデレーション[の構成」を参照してください](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)。</span><span class="sxs-lookup"><span data-stu-id="28266-156">To configure federation between Skype for Business 2015 and Skype for Business Online, see this  article: [Configure federation with Skype for Business Online](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json).</span></span>

- <span data-ttu-id="28266-157">Lync と Skype for Business Online の間のフェデレーションを構成するには、「Lync Online 顧客のフェデレーション サポートの[構成」を参照してください](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-federation-support-for-a-lync-online-customer)。</span><span class="sxs-lookup"><span data-stu-id="28266-157">To configure federation between Lync and Skype for Business Online, see this  article: [Configuring Federation Support for a Lync Online Customer](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-federation-support-for-a-lync-online-customer).</span></span>

- <span data-ttu-id="28266-158">Microsoft 365 または Office 365 の 2 人のユーザーが別々のドメインで互いに通信している場合、両方の組織で有効になっている Skype for Business 機能 (ビデオ会話やデスクトップ共有など) のみを使用できます。 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="28266-158">When two Skype for Business users in Microsoft 365 or Office 365 are communicating with each other on separate domains, they can only use Skype for Business features (for example, video conversations or desktop sharing) that are turned on in both organizations.</span></span>

- <span data-ttu-id="28266-159">組織内の Skype for Business ユーザーが In-Place または訴訟ホールドに設定されている場合、そのユーザーと他の Skype for Business または Skype ユーザーの間の IM 会話は、メールボックスの回復可能なアイテムに保存されます。</span><span class="sxs-lookup"><span data-stu-id="28266-159">If a Skype for Business user in your organization is put on an In-Place or Litigation Hold, any IM conversations between that user and other Skype for Business or Skype users will be saved in **Recoverable Items** in their mailbox.</span></span> <span data-ttu-id="28266-160">これらの会話は、メールボックスの **[会話履歴]** フォルダーには保存されません。</span><span class="sxs-lookup"><span data-stu-id="28266-160">These conversations aren't saved in the **Conversations History** folder in their mailbox.</span></span>

## <a name="turn-off-external-communication-for-specific-individuals"></a><span data-ttu-id="28266-161">特定の個人の外部通信をオフにする</span><span class="sxs-lookup"><span data-stu-id="28266-161">Turn off external communication for specific individuals</span></span>

<span data-ttu-id="28266-162"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="28266-162"><a name="bk_preview"> </a></span></span>

<span data-ttu-id="28266-163">ビジネス全体の外部通信を有効にした後は、特定の個人に対してオフにできます。</span><span class="sxs-lookup"><span data-stu-id="28266-163">After you enable external communication for your entire business, you can turn it off for only specific individuals.</span></span>
  
1. <span data-ttu-id="28266-164">管理者アカウントを使用Microsoft 365またはOffice 365サインインします。</span><span class="sxs-lookup"><span data-stu-id="28266-164">Sign in with your Microsoft 365 or Office 365 admin account.</span></span>

2. <span data-ttu-id="28266-165">管理センターで、[ユーザー] [アクティブな **ユーザー]**  >  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="28266-165">In the admin center, go to **Users** > **Active users**.</span></span>

3. <span data-ttu-id="28266-166">ユーザーの一覧でユーザーを選択し、[その他の設定] で 、[プロパティの設定を **クリックSkype for Businessします**。</span><span class="sxs-lookup"><span data-stu-id="28266-166">In the list of users, choose the user, and then, under **More Settings**, click **Edit Skype for Business properties**.</span></span>

    ![[Skype for Business](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. <span data-ttu-id="28266-168">[管理 **センター] Skype for Business、[外部** 通信]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="28266-168">In the **Skype for Business admin center**, choose **External communications**.</span></span>

    <span data-ttu-id="28266-169">[オプション **] ページ** で、すべての選択肢が選択されます。</span><span class="sxs-lookup"><span data-stu-id="28266-169">On the **Options** page, all of the choices will be selected.</span></span> <span data-ttu-id="28266-170">無効にする通信をクリアします。</span><span class="sxs-lookup"><span data-stu-id="28266-170">Clear the communications you want to disable.</span></span> <span data-ttu-id="28266-171">次の図は、Jakob が他の信頼できる企業のユーザーと通信できますが、他のユーザーと通信Skype示しています。</span><span class="sxs-lookup"><span data-stu-id="28266-171">The following image shows that Jakob will be able to communicate with people in other trusted businesses, but not with other Skype users.</span></span>

    ![[外部連絡先] を選択する](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. <span data-ttu-id="28266-173">[ **保存**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="28266-173">Choose **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="28266-174">変更が有効なまで最大 24 時間待機する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="28266-174">You may have to wait for up to 24 hours for your changes to take effect.</span></span>
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]

## <a name="related-topics"></a><span data-ttu-id="28266-175">関連項目</span><span class="sxs-lookup"><span data-stu-id="28266-175">Related topics</span></span>

<span data-ttu-id="28266-176"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="28266-176"><a name="bk_preview"> </a></span></span>

[<span data-ttu-id="28266-177">Skype for Business Online をセットアップする</span><span class="sxs-lookup"><span data-stu-id="28266-177">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)
  
[<span data-ttu-id="28266-178">Skype for Business ユーザーが Skype の連絡先を追加できるようにする</span><span class="sxs-lookup"><span data-stu-id="28266-178">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)
