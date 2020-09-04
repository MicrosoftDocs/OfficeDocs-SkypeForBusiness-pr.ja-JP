---
title: エンタープライズ Voip オンプレミスのユーザーを有効にする
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 4598565a-c228-4265-ad03-d2aef95b31a0
description: ユーザーが電話システム (クラウド PBX) を使用するには、最初にエンタープライズ Voip に対して有効にし、電話番号を割り当てる必要があります。 これは、ユーザーがオンプレミス展開に所属している間に、オンプレミス展開を使用して実行します。
ms.openlocfilehash: 7fc629114900cb9f4d825bd8fdc8e946e6c63880
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359193"
---
# <a name="enable-the-users-for-enterprise-voice-on-premises"></a><span data-ttu-id="6a66a-104">エンタープライズ Voip オンプレミスのユーザーを有効にする</span><span class="sxs-lookup"><span data-stu-id="6a66a-104">Enable the users for Enterprise Voice on premises</span></span>
 
<span data-ttu-id="6a66a-105">ユーザーが電話システム (クラウド PBX) を使用するには、最初にエンタープライズ Voip に対して有効にし、電話番号を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a66a-105">For a user to use Phone System (Cloud PBX), you must first enable them for Enterprise Voice and assign them a phone number.</span></span> <span data-ttu-id="6a66a-106">これは、ユーザーがオンプレミス展開に所属している間に、オンプレミス展開を使用して実行します。</span><span class="sxs-lookup"><span data-stu-id="6a66a-106">You do this using your on-premises deployment while the user is still homed in the on-premises deployment.</span></span>

> [!Important]
> <span data-ttu-id="6a66a-107">Skype for Business Online は、2021年7月31日に廃止されます。その後、サービスにアクセスできなくなります。</span><span class="sxs-lookup"><span data-stu-id="6a66a-107">Skype for Business Online will be retired on July 31, 2021 after which the service will no longer be accessible.</span></span>  <span data-ttu-id="6a66a-108">さらに、Skype for Business Server または Cloud Connector Edition と Skype for Business Online のどちらを使用しても、オンプレミス環境との間の PSTN 接続がサポートされなくなります。</span><span class="sxs-lookup"><span data-stu-id="6a66a-108">In addition, PSTN connectivity between your on-premises environment whether through Skype for Business Server or Cloud Connector Edition and Skype for Business Online will no longer be supported.</span></span>  <span data-ttu-id="6a66a-109">[直接ルーティング](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)を使用してオンプレミスのテレフォニーネットワークを Teams に接続する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6a66a-109">Learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>
  
### <a name="to-enable-a-user-for-enterprise-voice-on-premises-and-assign-a-phone-number"></a><span data-ttu-id="6a66a-110">エンタープライズ Voip オンプレミスでユーザーを有効にし、電話番号を割り当てるには</span><span class="sxs-lookup"><span data-stu-id="6a66a-110">To enable a user for Enterprise Voice on premises and assign a phone number</span></span>

1. <span data-ttu-id="6a66a-111">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="6a66a-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="6a66a-112">[スタート] メニューまたはデスクトップショートカットを使用して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="6a66a-112">Use the Start menu or desktop shortcut to open the Skype for Business Server Control Panel.</span></span>
    
    <span data-ttu-id="6a66a-113">ブラウザーウィンドウを開き、管理者の URL を入力して Skype for Business Server コントロールパネルを開くこともできます。</span><span class="sxs-lookup"><span data-stu-id="6a66a-113">You can also open a browser window, and then enter the Administrator URL to open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="6a66a-114">左側のナビゲーション バーで **[ユーザー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6a66a-114">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="6a66a-115">**[ユーザーの検索]** ボックスに、有効にするユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) の全体か最初の一部の文字列を入力して、**[検索]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6a66a-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="6a66a-116">表で、エンタープライズ Voip を有効にする Skype for Business Online ユーザーアカウントをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6a66a-116">In the table, click the Skype for Business Online user account that you want to enable for Enterprise Voice.</span></span>
    
6. <span data-ttu-id="6a66a-117">[ **編集** ] メニューの [ **詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6a66a-117">On the **Edit** menu, click **Show Details**.</span></span>
    
7. <span data-ttu-id="6a66a-118">[ **テレフォニー**] で、[ **エンタープライズ voip**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6a66a-118">Under **Telephony**, click **Enterprise Voice**.</span></span>
    
8. <span data-ttu-id="6a66a-119">[ **回線 URI**] をクリックし、正規化された一意の電話番号 (たとえば、tel: + 14255550200) を入力します。</span><span class="sxs-lookup"><span data-stu-id="6a66a-119">Click **Line URI**, and type a unique, normalized phone number (for example, tel:+14255550200).</span></span> <span data-ttu-id="6a66a-120">[ **確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6a66a-120">Then click **Commit**.</span></span>
    
## <a name="special-considerations-when-enabling-users-for-enterprise-voice-on-premises"></a><span data-ttu-id="6a66a-121">エンタープライズ Voip オンプレミスでユーザーを有効にするときの特別な考慮事項</span><span class="sxs-lookup"><span data-stu-id="6a66a-121">Special considerations when enabling users for Enterprise Voice on premises</span></span>

<span data-ttu-id="6a66a-122">場合によっては、エンタープライズ Voip でユーザーを有効にする方法を変更して、確実に通話を発信および受信できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a66a-122">In some cases, you may need to modify the way you enable users for Enterprise Voice to make sure that they can successfully make and receive calls.</span></span> <span data-ttu-id="6a66a-123">次の条件を満たすユーザーが展開に含まれている場合は、そのユーザーのエンタープライズ Voip を有効にするための手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="6a66a-123">If you have users in your deployment that meet the following conditions, perform the steps included to enable the user for Enterprise Voice.</span></span>
  
- <span data-ttu-id="6a66a-124">オンプレミスの AD でユーザーが作成されていて、skype for business または Enterprise Voice が有効になっていない状態で Skype for Business Online と同期されており、LineURI が設定されていない場合は、影響を受けるユーザーごとに次のコマンドレットを実行し、その値を \< \> 環境の実際の値に置き換えます</span><span class="sxs-lookup"><span data-stu-id="6a66a-124">If a user is created in your on-premises AD and then synchronized with Skype for Business Online without being enabled for Skype for Business or for Enterprise Voice and do not have a LineURI set, run the following cmdlets for each affected user, replacing the values in \< \> with actual values for your environment:</span></span>
    
  ```powershell
  Enable-CsUser $username -HostingProvider sipfed.online.lync.com -SipAddress sip:<UserName>@<SIP Domain>
  ```

  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- <span data-ttu-id="6a66a-125">ユーザーが既にオンプレミスの Skype for business に対して有効になっているが、エンタープライズ Voip が有効になっていない場合、または Skype for Business Online に移動する前に LineURI が割り当てられている場合は、ユーザーごとに次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="6a66a-125">If a user is already enabled for Skype for Business on premises, but was not enabled for Enterprise Voice or assigned a LineURI before being moved to Skype for Business Online, run the following cmdlet for each user:</span></span>
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- <span data-ttu-id="6a66a-126">LineURI が既に割り当てられている場合でも、ユーザーがオンプレミスの Skype for Business で既に有効になっているが、エンタープライズ Voip が有効になっていない場合は、影響を受けるユーザーごとに次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="6a66a-126">If a user is already enabled in Skype for Business on premises but not enabled for Enterprise Voice, even if already assigned a LineURI, run the following cmdlet for each affected user:</span></span>
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true
  ```


