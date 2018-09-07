---
title: 外部の Skype for Business ユーザーに連絡できるようにする
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: b414873a-0059-4cd5-aea1-e5d0857dbc94
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
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
description: 'ユーザーが別の組織内のユーザーに問い合わせるか、外にそれらの連絡先を使用できるようにするのにはビジネス用の Skype を構成する方法を参照してください。 '
ms.openlocfilehash: 79ba0754178e3d638520c932e6288a92ddf6e857
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23854703"
---
# <a name="allow-users-to-contact-external-skype-for-business-users"></a><span data-ttu-id="97d2b-103">外部の Skype for Business ユーザーに連絡できるようにする</span><span class="sxs-lookup"><span data-stu-id="97d2b-103">Allow users to contact external Skype for Business users</span></span>

> [!NOTE]
> <span data-ttu-id="97d2b-104">ビジネス連合の Skype を 21Vianet と Office 365 のドイツの組織によって運営されて Office 365 を使用できません。</span><span class="sxs-lookup"><span data-stu-id="97d2b-104">Skype for Business federation isn't available to Office 365 operated by 21Vianet and Office 365 Germany organizations.</span></span> 
  
<span data-ttu-id="97d2b-105">記事の場合この手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="97d2b-105">Use the steps in this article when:</span></span>
  
- <span data-ttu-id="97d2b-106">ビジネスで別のドメインにユーザーがあります。</span><span class="sxs-lookup"><span data-stu-id="97d2b-106">You have users on different domains in your business.</span></span> <span data-ttu-id="97d2b-107">たとえば、Rob@ContosoEast.com と Ann@ContosoWest.com です。</span><span class="sxs-lookup"><span data-stu-id="97d2b-107">For example, Rob@ContosoEast.com and Ann@ContosoWest.com.</span></span>
    
- <span data-ttu-id="97d2b-108">ビジネス用の Skype を使用して特定の企業、組織外の人に連絡するのには、組織で人をします。</span><span class="sxs-lookup"><span data-stu-id="97d2b-108">You want the people in your organization to use Skype for Business to contact people in specific businesses outside of your organization.</span></span>
    
<span data-ttu-id="97d2b-109">-する他のユーザーを検索し、連絡先、電子メール アドレスを使用することができるビジネス用の Skype を使用している世界で。</span><span class="sxs-lookup"><span data-stu-id="97d2b-109">-You want anyone else in the world who uses Skype for Business to be able to find and contact you, using your email address.</span></span> <span data-ttu-id="97d2b-110">Skype のデフォルトを使用して、ビジネスの設定を自動的にこの動作はします。</span><span class="sxs-lookup"><span data-stu-id="97d2b-110">If you and they use the default Skype for Business settings, this will work automatically.</span></span> <span data-ttu-id="97d2b-111">しない場合は、ドメインの構成によってブロックされていないかどうかを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="97d2b-111">If they don't, then they need to make sure their configuration isn't blocking your domain.</span></span>
    
## <a name="enable-business-to-business-communications-for-your-users"></a><span data-ttu-id="97d2b-112">ユーザーの企業間の通信を有効にします。</span><span class="sxs-lookup"><span data-stu-id="97d2b-112">Enable business-to-business communications for your users</span></span>
<span data-ttu-id="97d2b-113"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="97d2b-113"></span></span>

<span data-ttu-id="97d2b-114">これを行う 2 つの組織で Office 365 の[管理者のアクセス許可](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)が必要です。</span><span class="sxs-lookup"><span data-stu-id="97d2b-114">You must have [admin permissions](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) in Office 365 in both organizations to do this.</span></span>

<span data-ttu-id="97d2b-115">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Skype for Business の管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="97d2b-115">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="97d2b-116">Office 365 管理者アカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="97d2b-116">Sign in with your Office 365 admin account.</span></span> 
    
2. <span data-ttu-id="97d2b-117">Office 365 管理センターで、[**管理センター**]  >  [**Skype for Business**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="97d2b-117">In the Office 365 admin center, go to **Admin Centers** > **Skype for Business**.</span></span>
    
    ![Choose the Skype for Business admin center.](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. <span data-ttu-id="97d2b-119">[**Skype for Business 管理センター**] で、[**組織**]  >  [**外部通信**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="97d2b-119">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span>
    
4. <span data-ttu-id="97d2b-120">設定するには、特定のビジネスで、または、ドロップ ダウン ボックスで、別のドメイン内のユーザーとの通信**にのみ許可されるドメイン**を選択します。</span><span class="sxs-lookup"><span data-stu-id="97d2b-120">To set up communication with a specific business or with users in another domain, in the drop-down box, choose **On only for allowed domains**.</span></span>
    
    <span data-ttu-id="97d2b-121">ビジネス ポリシーでは、Skype の選択を開くには世界中の他のすべてとの通信を有効にするかどうか、または、**をブロックするドメインを除く**。</span><span class="sxs-lookup"><span data-stu-id="97d2b-121">OR, if you want to enable communication with everyone else in the world who has open Skype for Business policies, choose **On except for blocked domains**.</span></span> <span data-ttu-id="97d2b-122">これは既定の設定です。</span><span class="sxs-lookup"><span data-stu-id="97d2b-122">This is the default setting.</span></span>
    
5. <span data-ttu-id="97d2b-123">[**ブロックまたは許可するドメイン**] を選択して**+** を許可するドメインの名前を追加します。</span><span class="sxs-lookup"><span data-stu-id="97d2b-123">Under **Blocked or allowed domains**, choose **+** and add the name of the domain you want to allow.</span></span>
    
6. <span data-ttu-id="97d2b-124">その他の組織の管理者には、**ビジネス管理センターの Skype**では、次の同じ手順を確認します。</span><span class="sxs-lookup"><span data-stu-id="97d2b-124">Make sure the admin in the other organization does these same steps in their **Skype for Business admin center**.</span></span> <span data-ttu-id="97d2b-125">などの**ドメインを許可する**ボックスの一覧で、管理者が自社のドメインを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="97d2b-125">For example, in their **allowed domains** list, their admin needs to enter the domain for your business.</span></span>
    
7. <span data-ttu-id="97d2b-126">Windows Firewall を使用している場合は、Skype for Business が必要なポートを自動的に開きます。</span><span class="sxs-lookup"><span data-stu-id="97d2b-126">If you're using Windows Firewall, Skype for Business opens the required ports automatically.</span></span>
    
    <span data-ttu-id="97d2b-127">組織がインターネットへの接続をネットワーク上のコンピューターを制限する別のファイアウォール ソリューションを使用している場合は、クライアント コンピューターは、次の[Office 365 の Url と IP アドレスの範囲](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges)にアクセスすることを確認します。</span><span class="sxs-lookup"><span data-stu-id="97d2b-127">If your organization is using a different firewall solution to restrict computers on your network from connecting to the Internet, ensure your client computers are able to access the following [Office 365 URLs and IP address ranges](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).</span></span> <span data-ttu-id="97d2b-128">インフラストラクチャの構成、ファイアウォールやプロキシのリストを許可する、送信する Fqdn を追加することがあります:**\*です。 api.skype.com**、 \***です。 users.storage.live.com**、と**graph.skype.com**。</span><span class="sxs-lookup"><span data-stu-id="97d2b-128">This may require adding the FQDNs to the outbound allow list in your firewall or proxy infrastructure configuration: **\*.api.skype.com**, \***.users.storage.live.com**, and **graph.skype.com**.</span></span> <span data-ttu-id="97d2b-129">お使いのファイアウォールでポートを開く方法の詳細については、それに付属のマニュアルを確認してください。</span><span class="sxs-lookup"><span data-stu-id="97d2b-129">For instructions on how to open these ports in your firewall, check the documentation that came with it.</span></span>
    
    <span data-ttu-id="97d2b-130">すべてのポートを開く必要のリストは、 [Office 365 の Url と IP アドレスの範囲](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="97d2b-130">For a list of all ports you need to open, see [Office 365 URLs and IP address ranges](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).</span></span>

8. <span data-ttu-id="97d2b-131">管理者は、組織では、次の手順の後にもことを確認します。</span><span class="sxs-lookup"><span data-stu-id="97d2b-131">Make sure that the administrator in the organization has also followed these steps.</span></span>
    
9. <span data-ttu-id="97d2b-p106">**テストのために最大 24 時間待機します** 。外部通信設定を変更したときはいつでも、変更がデータ　センター全体に行き渡るまでに最大 24 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="97d2b-p106">**WAIT UP TO 24 HOURS TO TEST**. Any time you change the external communications settings, it can take up to 24 hours for the changes to populate across all the data centers.</span></span>
    
<span data-ttu-id="97d2b-134">![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) Skype、無料のコンシューマー アプリケーションを使用して他のユーザーと IM を検索して、ユーザーを許可します。</span><span class="sxs-lookup"><span data-stu-id="97d2b-134">![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) You can allow your users to search for and IM with everyone who uses Skype, the free consumer app!</span></span> <span data-ttu-id="97d2b-135">詳細については、[ビジネス ユーザー向けの Skype は、Skype 連絡先を追加する](let-skype-for-business-users-add-skype-contacts.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="97d2b-135">To learn more, see [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span>
  
## <a name="test-and-troubleshoot"></a><span data-ttu-id="97d2b-136">テストとトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="97d2b-136">Test and troubleshoot</span></span>
<span data-ttu-id="97d2b-137"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="97d2b-137"></span></span>

 <span data-ttu-id="97d2b-138">**企業間の通信を設定する際に発生する最も一般的な問題は、取得[Office 365 の Url と IP アドレスの範囲](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges)右です。**</span><span class="sxs-lookup"><span data-stu-id="97d2b-138">**The most common issue people encounter when setting up business-to-business communication is getting their [Office 365 URLs and IP address ranges](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges) right.**</span></span>
  
<span data-ttu-id="97d2b-139">設定をテストするには、企業ファイアウォールの背後にあるではないビジネスの Skype の連絡先が必要です。</span><span class="sxs-lookup"><span data-stu-id="97d2b-139">To test your setup, you need a contact on Skype for Business who's not behind your company firewall.</span></span>
  
1. <span data-ttu-id="97d2b-140">外部通信設定を変更した後、 **テストのために最大 24 時間待機** します。</span><span class="sxs-lookup"><span data-stu-id="97d2b-140">After you change your external communications settings, **WAIT UP TO 24 HOURS TO TEST**.</span></span>
    
2. <span data-ttu-id="97d2b-141">ビジネスの Skype は、ビジネス用の Skype の連絡先の検索でチャットへの要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="97d2b-141">In Skype for Business, search for your contact in Skype for Business, and send a request to chat.</span></span>
    
    <span data-ttu-id="97d2b-142">会社のポリシーのために送信できませんでしたというメッセージが表示される場合[Office 365 の Url と IP アドレスの範囲](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges)を再確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="97d2b-142">If you get a message that it couldn't be sent due to company policy, you need to double-check your [Office 365 URLs and IP address ranges](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).</span></span>
    
3. <span data-ttu-id="97d2b-143">チャットへの要求を送信するビジネス用連絡先の Skype を依頼してください。</span><span class="sxs-lookup"><span data-stu-id="97d2b-143">Ask your Skype for Business contact to send you a request to chat.</span></span> <span data-ttu-id="97d2b-144">要求の場合、問題は、ファイアウォールの設定 (ファイアウォール設定が正しいことが既にわかっていると仮定した場合) です。</span><span class="sxs-lookup"><span data-stu-id="97d2b-144">If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span></span>
    
4. <span data-ttu-id="97d2b-145">問題がお使いのファイアウォールであるかどうかをテストする別の方法ではないファイアウォールの内側に、コーヒー ショップなどの wifi の場所に移動し、チャットする相手に要求を送信するのにはビジネス用の Skype を使用します。</span><span class="sxs-lookup"><span data-stu-id="97d2b-145">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Skype for Business to send a request to your contact to chat.</span></span> <span data-ttu-id="97d2b-146">メッセージは、そこを通過し、問題がわかっていないしたら職場場合、は、お使いのファイアウォールです。</span><span class="sxs-lookup"><span data-stu-id="97d2b-146">If the message goes through there, but not when you're at work, then you know the problem is your firewall.</span></span>
    
## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a><span data-ttu-id="97d2b-147">、他のユーザーを検索し、別のビジネスに接続するときを検出する方法</span><span class="sxs-lookup"><span data-stu-id="97d2b-147">How to find others, and be found, when connecting with another business</span></span>
<span data-ttu-id="97d2b-148"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="97d2b-148"></span></span>

<span data-ttu-id="97d2b-149">ビジネス ユーザー向けの他の Skype での外部の通信を有効にした後、ユーザーは検索できます連合 Skype ビジネス ユーザー向けのサインイン名を検索し、: 例えば、Rob@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="97d2b-149">After you enable external communication with other Skype for Business users, your users can find federated Skype for Business users by searching for their sign-in name: for example, Rob@contoso.com.</span></span> <span data-ttu-id="97d2b-150">連絡先の一覧にユーザーを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="97d2b-150">Then they will need to add the person to their list of contacts.</span></span>
  
![連合ビジネスでユーザーを検索するのには (これは、通常も、サインイン名)、電子メール アドレスを検索する必要があります。](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a><span data-ttu-id="97d2b-152">連合の企業との通信設定のヒント</span><span class="sxs-lookup"><span data-stu-id="97d2b-152">Tips on setting up communications with federated businesses</span></span>
<span data-ttu-id="97d2b-153"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="97d2b-153"></span></span>

- <span data-ttu-id="97d2b-154">ビジネス 2015年の Skype と Skype のオンライン ビジネスとの間のフェデレーションを構成するには、この資料を参照してください:[ビジネス オンラインの Skype でフェデレーションを構成](https://technet.microsoft.com/en-us/library/jj205126.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="97d2b-154">To configure federation between Skype for Business 2015 and Skype for Business Online, see this  article: [Configure federation with Skype for Business Online](https://technet.microsoft.com/en-us/library/jj205126.aspx).</span></span>
    
- <span data-ttu-id="97d2b-155">オンライン ビジネスの Lync と Skype との間のフェデレーションを構成するには、この資料を参照してください: [Lync のオンライン ・ カスタマーのフェデレーション サポートを構成します](https://technet.microsoft.com/en-us/library/hh202193.aspx)。</span><span class="sxs-lookup"><span data-stu-id="97d2b-155">To configure federation between Lync and Skype for Business Online, see this  article: [Configuring Federation Support for a Lync Online Customer](https://technet.microsoft.com/en-us/library/hh202193.aspx).</span></span>
    
- <span data-ttu-id="97d2b-156">Office 365 のビジネス ユーザー向けの 2 つの Skype は別のドメインに相互通信している場合 (たとえば、ビデオの会話またはデスクトップの共有) の両方の組織内有効になっているビジネス機能の Skype のみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="97d2b-156">When two Skype for Business users in Office 365 are communicating with each other on separate domains, they can only use Skype for Business features (for example, video conversations or desktop sharing) that are turned on in both organizations.</span></span>
    
- <span data-ttu-id="97d2b-157">埋め込みまたは証拠保全に、組織内のビジネス ユーザーは、Skype を配置すると、自分のメールボックスの**回復可能な項目**でそのユーザーとその他の Skype をビジネスまたは Skype のユーザーの間ですべての IM 会話が保存されます。</span><span class="sxs-lookup"><span data-stu-id="97d2b-157">If a Skype for Business user in your organization is put on an In-Place or Litigation Hold, any IM conversations between that user and other Skype for Business or Skype users will be saved in **Recoverable Items** in their mailbox.</span></span> <span data-ttu-id="97d2b-158">これらの会話は、自分のメールボックスの**会話履歴**フォルダーに保存されません。</span><span class="sxs-lookup"><span data-stu-id="97d2b-158">These conversations aren't saved in the **Conversations History** folder in their mailbox.</span></span>
    
## <a name="turn-off-external-communication-for-specific-individuals"></a><span data-ttu-id="97d2b-159">特定の個人の外部通信をオフにします。</span><span class="sxs-lookup"><span data-stu-id="97d2b-159">Turn off external communication for specific individuals</span></span>
<span data-ttu-id="97d2b-160"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="97d2b-160"></span></span>

<span data-ttu-id="97d2b-161">全体のビジネスでは、外部の通信を有効にした後は、特定の個人の無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="97d2b-161">After you enable external communication for your entire business, you can turn it off for only specific individuals.</span></span>
  
1. <span data-ttu-id="97d2b-162">Office 365 管理者アカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="97d2b-162">Sign in with your Office 365 admin account.</span></span>
    
2. <span data-ttu-id="97d2b-163">**ユーザー**には、Office 365 管理センターで、 > **アクティブなユーザー**です。</span><span class="sxs-lookup"><span data-stu-id="97d2b-163">In the Office 365 admin center, go to **Users** > **Active users**.</span></span>
    
3. <span data-ttu-id="97d2b-164">、ユーザーの一覧で、ユーザーの選択し、[**詳細設定**]**プロパティをビジネスの Skype を編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97d2b-164">In the list of users, choose the user, and then, under **More Settings**, click **Edit Skype for Business properties**.</span></span>
    
    ![Skype をビジネスを選択します。](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. <span data-ttu-id="97d2b-166">**ビジネス管理センターの Skype**では、**外部の通信**を選択します。</span><span class="sxs-lookup"><span data-stu-id="97d2b-166">In the **Skype for Business admin center**, choose **External communications**.</span></span>
    
    <span data-ttu-id="97d2b-167">[**オプション**] ページで、すべての選択肢が選択されます。</span><span class="sxs-lookup"><span data-stu-id="97d2b-167">On the **Options** page, all of the choices will be selected.</span></span> <span data-ttu-id="97d2b-168">通信を無効にするをオフにします。</span><span class="sxs-lookup"><span data-stu-id="97d2b-168">Clear the communications you want to disable.</span></span> <span data-ttu-id="97d2b-169">次の図は、Jakob がその他の Skype ユーザーではなく、信頼されているその他の企業のユーザーと通信できることを示しています。</span><span class="sxs-lookup"><span data-stu-id="97d2b-169">The following image shows that Jakob will be able to communicate with people in other trusted businesses, but not with other Skype users.</span></span>
    
    ![外部の連絡先を選択します。](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. <span data-ttu-id="97d2b-171">[ **保存**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="97d2b-171">Choose **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="97d2b-172">変更を有効にするには、最大で 24 時間待機する必要があります。</span><span class="sxs-lookup"><span data-stu-id="97d2b-172">You may have to wait for up to 24 hours for your changes to take effect.</span></span> 
  


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
   
## <a name="related-topics"></a><span data-ttu-id="97d2b-173">このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="97d2b-173">Related topics</span></span>
<span data-ttu-id="97d2b-174"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="97d2b-174"></span></span>

[<span data-ttu-id="97d2b-175">Skype for Business Online のセットアップ</span><span class="sxs-lookup"><span data-stu-id="97d2b-175">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)
  
[<span data-ttu-id="97d2b-176">Skype for Business ユーザーが Skype 連絡先を追加できるようにする</span><span class="sxs-lookup"><span data-stu-id="97d2b-176">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)
  
  
 
