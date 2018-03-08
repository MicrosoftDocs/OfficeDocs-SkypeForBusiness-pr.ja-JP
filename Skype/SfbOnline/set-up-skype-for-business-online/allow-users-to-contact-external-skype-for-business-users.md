---
title: "ビジネス ユーザー向けの Skype の外部の連絡先にユーザーを許可します。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: b414873a-0059-4cd5-aea1-e5d0857dbc94
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
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
description: "Skype for Business にユーザーが、別の組織内のユーザーに問い合わせるか、外部連絡先に使用できるように構成する方法を参照してください。 "
ms.openlocfilehash: 89db09b5bb31712d465e07e4abb3775fe31648e9
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="allow-users-to-contact-external-skype-for-business-users"></a><span data-ttu-id="befd0-103">ビジネス ユーザー向けの Skype の外部の連絡先にユーザーを許可します。</span><span class="sxs-lookup"><span data-stu-id="befd0-103">Allow users to contact external Skype for Business users</span></span>

> [!NOTE]
> <span data-ttu-id="befd0-104">Skype for Business フェデレーションのは Office 365 ドイツの組織と 21 vianet が運営する Office 365 を利用できません。</span><span class="sxs-lookup"><span data-stu-id="befd0-104">Skype for Business federation isn't available to Office 365 operated by 21Vianet and Office 365 Germany organizations.</span></span> 
  
<span data-ttu-id="befd0-105">ときの記事: 次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="befd0-105">Use the steps in this article when:</span></span>
  
- <span data-ttu-id="befd0-p101">ビジネスに別のドメインでユーザーがあります。たとえば、Rob@ContosoEast.com と Ann@ContosoWest.com します。</span><span class="sxs-lookup"><span data-stu-id="befd0-p101">You have users on different domains in your business. For example, Rob@ContosoEast.com and Ann@ContosoWest.com.</span></span>
    
- <span data-ttu-id="befd0-108">組織外の特定の企業内のユーザーに連絡する Skype for Business を使用する組織の他のユーザーしたいです。</span><span class="sxs-lookup"><span data-stu-id="befd0-108">You want the people in your organization to use Skype for Business to contact people in specific businesses outside of your organization.</span></span>
    
<span data-ttu-id="befd0-p102">見つけて、メール アドレスを使用して、あなたに連絡できる Skype for Business を使用している、世界中で、他のユーザー-します。既定の Skype for Business 設定を使う場合は、このが自動的に実行されます。しない場合は、自分のドメインの構成によってブロックされていないことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="befd0-p102">-You want anyone else in the world who uses Skype for Business to be able to find and contact you, using your email address. If you and they use the default Skype for Business settings, this will work automatically. If they don't, then they need to make sure their configuration isn't blocking your domain.</span></span>
    
## <a name="enable-business-to-business-communications-for-your-users"></a><span data-ttu-id="befd0-112">ユーザーの企業との通信を有効にします。</span><span class="sxs-lookup"><span data-stu-id="befd0-112">Enable business-to-business communications for your users</span></span>
<span data-ttu-id="befd0-113"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="befd0-113"></span></span>

<span data-ttu-id="befd0-114">これを行う Office 365 の[管理者権限](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)が必要です。</span><span class="sxs-lookup"><span data-stu-id="befd0-114">You must have [admin permissions](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) in Office 365 to do this.</span></span>
  
1. <span data-ttu-id="befd0-115">Office 365 の管理者アカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="befd0-115">Sign in with your Office 365 admin account.</span></span> 
    
2. <span data-ttu-id="befd0-116">Office 365 管理センターで、**管理センター**に移動 > **Skype for Business**します。</span><span class="sxs-lookup"><span data-stu-id="befd0-116">In the Office 365 admin center, go to **Admin Centers** > **Skype for Business**.</span></span>
    
    ![Skype for Business 管理センター] を選びます。](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. <span data-ttu-id="befd0-118">**Skype for Business 管理センター**で、[**組織**] を選びます > **外部通信**します。</span><span class="sxs-lookup"><span data-stu-id="befd0-118">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span>
    
4. <span data-ttu-id="befd0-119">設定するのには、特定のビジネスまたは、ドロップ ダウン ボックスで、別のドメインのユーザーとの通信は、 **[許可ドメインのみ**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="befd0-119">To set up communication with a specific business or with users in another domain, in the drop-down box, choose **On only for allowed domains**.</span></span>
    
    <span data-ttu-id="befd0-p103">または、Skype for Business のポリシーの選択を開くには、世界中に他のすべてのユーザーとの通信を有効にするかどうかは**の禁止ドメイン以外**します。これは、既定の設定です。</span><span class="sxs-lookup"><span data-stu-id="befd0-p103">OR, if you want to enable communication with everyone else in the world who has open Skype for Business policies, choose **On except for blocked domains**. This is the default setting.</span></span>
    
5. <span data-ttu-id="befd0-122">[**ブロックまたは許可ドメイン**] で選択**+**入力できるようにするドメインの名前を追加します。</span><span class="sxs-lookup"><span data-stu-id="befd0-122">Under **Blocked or allowed domains**, choose **+** and add the name of the domain you want to allow.</span></span>
    
6. <span data-ttu-id="befd0-p104">その他の組織の管理者は、 **Skype for Business 管理センター**で同じ手順を確認します。たとえば、 **[許可ドメイン**リスト管理者は、業務用のドメインを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="befd0-p104">Make sure the admin in the other organization does these same steps in their **Skype for Business admin center**. For example, in their **allowed domains** list, their admin needs to enter the domain for your business.</span></span>
    
7. <span data-ttu-id="befd0-125">Windows ファイアウォールを使っている場合は、Skype for Business が自動的に必要なポートを開きます。</span><span class="sxs-lookup"><span data-stu-id="befd0-125">If you're using Windows Firewall, Skype for Business opens the required ports automatically.</span></span>
    
    <span data-ttu-id="befd0-p105">組織がインターネットに接続するネットワーク上のコンピューターを制限するソリューションを別のファイアウォールを使用している場合は、クライアント コンピューターは、次の[Office 365 の Url と IP アドレスの範囲](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges)にアクセスできるようにことを確認します。Fqdn、送信を許可する、ファイアウォールまたはプロキシのリスト インフラストラクチャ構成の追加が必要: ** \*. api.skype.com**、 \* **. users.storage.live.com**、 **graph.skype.com**とします。ファイアウォールでこれらのポートを開く方法については、それに付属しているドキュメントを確認してください。</span><span class="sxs-lookup"><span data-stu-id="befd0-p105">If your organization is using a different firewall solution to restrict computers on your network from connecting to the Internet, ensure your client computers are able to access the following [Office 365 URLs and IP address ranges](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges). This may require adding the FQDNs to the outbound allow list in your firewall or proxy infrastructure configuration: **\*.api.skype.com**, \***.users.storage.live.com**, and **graph.skype.com**. For instructions on how to open these ports in your firewall, check the documentation that came with it.</span></span>
    
    <span data-ttu-id="befd0-128">すべてのポートを開きたいのリストは、 [Office 365 の Url と IP アドレスの範囲](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="befd0-128">For a list of all ports you need to open, see [Office 365 URLs and IP address ranges](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).</span></span>
    
8. <span data-ttu-id="befd0-p106">**テストするのには、最大 24 時間かかる**。外部通信] 設定を変更するには、すべてのデータ センターで設定を変更するには、最大 24 時間がかかることができます。</span><span class="sxs-lookup"><span data-stu-id="befd0-p106">**WAIT UP TO 24 HOURS TO TEST**. Any time you change the external communications settings, it can take up to 24 hours for the changes to populate across all the data centers.</span></span>
    
<span data-ttu-id="befd0-p107">![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) Skype、無料のコンシューマー アプリを使用しているすべてのユーザーとユーザーを検索して IM を許可していることができます。詳細については、 [Skype for Business ユーザーに許可 Skype の連絡先を追加する](let-skype-for-business-users-add-skype-contacts.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="befd0-p107">![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) You can allow your users to search for and IM with everyone who uses Skype, the free consumer app! To learn more, see [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span>
  
## <a name="test-and-troubleshoot"></a><span data-ttu-id="befd0-133">テスト、トラブルシューティングする.</span><span class="sxs-lookup"><span data-stu-id="befd0-133">Test and troubleshoot</span></span>
<span data-ttu-id="befd0-134"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="befd0-134"></span></span>

 <span data-ttu-id="befd0-135">**企業間の通信を設定する際に発生する最も一般的な問題は、作業[Office 365 の Url と IP アドレスの範囲](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges)右します。**</span><span class="sxs-lookup"><span data-stu-id="befd0-135">**The most common issue people encounter when setting up business-to-business communication is getting their [Office 365 URLs and IP address ranges](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges) right.**</span></span>
  
<span data-ttu-id="befd0-136">設定をテストするには、ビジネス、会社のファイアウォールの背後にない人の Skype の連絡先が必要です。</span><span class="sxs-lookup"><span data-stu-id="befd0-136">To test your setup, you need a contact on Skype for Business who's not behind your company firewall.</span></span>
  
1. <span data-ttu-id="befd0-137">した後、 **24 まで待機する時間にテスト**の外部通信設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="befd0-137">After you change your external communications settings, **WAIT UP TO 24 HOURS TO TEST**.</span></span>
    
2. <span data-ttu-id="befd0-138">Skype for Business] では、Skype for Business] で、連絡先を検索し、チャット出席依頼を送信します。</span><span class="sxs-lookup"><span data-stu-id="befd0-138">In Skype for Business, search for your contact in Skype for Business, and send a request to chat.</span></span>
    
    <span data-ttu-id="befd0-139">会社のポリシーが原因で送信できなかったことをメッセージが表示される場合[Office 365 の Url と IP アドレスの範囲](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges)を再確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="befd0-139">If you get a message that it couldn't be sent due to company policy, you need to double-check your [Office 365 URLs and IP address ranges](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).</span></span>
    
3. <span data-ttu-id="befd0-p108">チャットの出席依頼を送信するビジネス用連絡先の Skype を依頼します。場合は、出席依頼を受信していない、問題は、(そのファイアウォール設定が正しいが既にわかっている場合)、ファイアウォールの設定です。</span><span class="sxs-lookup"><span data-stu-id="befd0-p108">Ask your Skype for Business contact to send you a request to chat. If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span></span>
    
4. <span data-ttu-id="befd0-p109">問題が、ファイアウォールであるかどうかをテストする別の方法では、: 喫茶店など、ファイアウォールの背後にない wifi 場所に移動し、Skype for Business を使ってチャットするのには、連絡先に、出席依頼を送信します。メッセージを通過のにいないしたら職場で、[問題の場合は、ファイアウォールです。</span><span class="sxs-lookup"><span data-stu-id="befd0-p109">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Skype for Business to send a request to your contact to chat. If the message goes through there, but not when you're at work, then you know the problem is your firewall.</span></span>
    
## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a><span data-ttu-id="befd0-144">他のユーザーを検索し、別のビジネスに接続しているときに検出する方法</span><span class="sxs-lookup"><span data-stu-id="befd0-144">How to find others, and be found, when connecting with another business</span></span>
<span data-ttu-id="befd0-145"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="befd0-145"></span></span>

<span data-ttu-id="befd0-146">他の Skype for Business ユーザーとの外部通信を有効にした後にユーザーくださいフェデレーション Skype ビジネス ユーザーのサインイン名を検索して: Rob@contoso.com などです。な連絡先リストにユーザーを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="befd0-146">After you enable external communication with other Skype for Business users, your users can find federated Skype for Business users by searching for their sign-in name: for example, Rob@contoso.com. Then they will need to add the person to their list of contacts.</span></span>
  
![フェデレーション business でユーザーを検索するには、ユーザーのメール アドレスを (通常はも、サインイン名) を検索する必要があります。](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a><span data-ttu-id="befd0-148">フェデレーション企業との通信設定のヒント</span><span class="sxs-lookup"><span data-stu-id="befd0-148">Tips on setting up communications with federated businesses</span></span>
<span data-ttu-id="befd0-149"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="befd0-149"></span></span>

- <span data-ttu-id="befd0-150">Skype for Business 2015 と Skype for Business Online のフェデレーションを構成するには、この TechNet の記事を参照してください: [Skype for Business Online のフェデレーションを構成](https://technet.microsoft.com/en-us/library/jj205126.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="befd0-150">To configure federation between Skype for Business 2015 and Skype for Business Online, see this TechNet article: [Configure federation with Skype for Business Online](https://technet.microsoft.com/en-us/library/jj205126.aspx).</span></span>
    
- <span data-ttu-id="befd0-151">Lync と Skype for Business Online のフェデレーションを構成するには、この TechNet 記事を参照してください: [Lync Online の顧客のためのフェデレーション サポートの構成](https://technet.microsoft.com/en-us/library/hh202193.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="befd0-151">To configure federation between Lync and Skype for Business Online, see this TechNet article: [Configuring Federation Support for a Lync Online Customer](https://technet.microsoft.com/en-us/library/hh202193.aspx).</span></span>
    
- <span data-ttu-id="befd0-152">2 つの Skype for Office 365 のビジネス ユーザーが別のドメインの相互通信している場合は、両方の組織でオンになっているビジネス機能 (たとえば、ビデオによる会話やデスクトップ共有) Skype のみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="befd0-152">When two Skype for Business users in Office 365 are communicating with each other on separate domains, they can only use Skype for Business features (for example, video conversations or desktop sharing) that are turned on in both organizations.</span></span>
    
- <span data-ttu-id="befd0-p110">場合は、組織内のビジネス ユーザーの Skype がインプレースまたは訴訟したままで、そのユーザーと他の Skype for Business または Skype のユーザーの IM 会話を自分のメールボックスで**回復できるアイテム**に保存されます。これらの会話は、自分のメールボックスで**の会話履歴**] フォルダーに保存されていません。</span><span class="sxs-lookup"><span data-stu-id="befd0-p110">If a Skype for Business user in your organization is put on an In-Place or Litigation Hold, any IM conversations between that user and other Skype for Business or Skype users will be saved in **Recoverable Items** in their mailbox. These conversations aren't saved in the **Conversations History** folder in their mailbox.</span></span>
    
## <a name="turn-off-external-communication-for-specific-individuals"></a><span data-ttu-id="befd0-155">特定のユーザーに対して外部通信をオフにします。</span><span class="sxs-lookup"><span data-stu-id="befd0-155">Turn off external communication for specific individuals</span></span>
<span data-ttu-id="befd0-156"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="befd0-156"></span></span>

<span data-ttu-id="befd0-157">全体向けの外部通信を有効にした後は、のみ具体的な個人の無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="befd0-157">After you enable external communication for your entire business, you can turn it off for only specific individuals.</span></span>
  
1. <span data-ttu-id="befd0-158">Office 365 の管理者アカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="befd0-158">Sign in with your Office 365 admin account.</span></span>
    
2. <span data-ttu-id="befd0-159">Office 365 管理センターで、[**ユーザー**] に移動 > **アクティブなユーザー**。</span><span class="sxs-lookup"><span data-stu-id="befd0-159">In the Office 365 admin center, go to **Users** > **Active users**.</span></span>
    
3. <span data-ttu-id="befd0-160">、ユーザーの一覧で、ユーザーを選択し、[**詳細設定**] で**ビジネスのプロパティの Skype の編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="befd0-160">In the list of users, choose the user, and then, under **More Settings**, click **Edit Skype for Business properties**.</span></span>
    
    ![ビジネス向けの Skype を選択します。](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. <span data-ttu-id="befd0-162">**Skype for Business 管理センター**で、[**外部通信**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="befd0-162">In the **Skype for Business admin center**, choose **External communications**.</span></span>
    
    <span data-ttu-id="befd0-p111">[**オプション**] ページで、すべての選択肢が選択されます。無効に通信をオフにします。次の図は、Jakob が他の Skype ユーザーではなく、信頼できる企業他のユーザーと通信できることを示しています。</span><span class="sxs-lookup"><span data-stu-id="befd0-p111">On the **Options** page, all of the choices will be selected. Clear the communications you want to disable. The following image shows that Jakob will be able to communicate with people in other trusted businesses, but not with other Skype users.</span></span>
    
    ![外部の連絡先を選択します。](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. <span data-ttu-id="befd0-167">[**保存**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="befd0-167">Choose **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="befd0-168">最大 24 時間、変更内容を有効になるまで待つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="befd0-168">You may have to wait for up to 24 hours for your changes to take effect.</span></span> 
  


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
   
## <a name="related-topics"></a><span data-ttu-id="befd0-169">関連トピック</span><span class="sxs-lookup"><span data-stu-id="befd0-169">Related topics</span></span>
<span data-ttu-id="befd0-170"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="befd0-170"></span></span>

[<span data-ttu-id="befd0-171">Skype for Business Online をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="befd0-171">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)
  
[<span data-ttu-id="befd0-172">ビジネス ユーザー向けの Skype Skype の連絡先を追加できるようにします。</span><span class="sxs-lookup"><span data-stu-id="befd0-172">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)
  

