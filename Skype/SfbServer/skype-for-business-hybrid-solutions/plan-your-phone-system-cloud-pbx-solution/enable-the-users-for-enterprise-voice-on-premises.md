---
title: オンプレミスでユーザーエンタープライズ VoIP有効にする
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
description: ユーザーが電話システム (Cloud PBX) を使用するには、最初に電話システムで有効にしエンタープライズ VoIP電話番号を割り当てる必要があります。 これは、ユーザーがオンプレミス展開にまだ存在している間に、オンプレミス展開を使用して行います。
ms.openlocfilehash: b26e51ba316c63e0f992b843a7763586d7e9b575
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098593"
---
# <a name="enable-the-users-for-enterprise-voice-on-premises"></a><span data-ttu-id="34c92-104">オンプレミスでユーザーエンタープライズ VoIP有効にする</span><span class="sxs-lookup"><span data-stu-id="34c92-104">Enable the users for Enterprise Voice on premises</span></span>
 
<span data-ttu-id="34c92-105">ユーザーが電話システム (Cloud PBX) を使用するには、最初に電話システムで有効にしエンタープライズ VoIP電話番号を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="34c92-105">For a user to use Phone System (Cloud PBX), you must first enable them for Enterprise Voice and assign them a phone number.</span></span> <span data-ttu-id="34c92-106">これは、ユーザーがオンプレミス展開にまだ存在している間に、オンプレミス展開を使用して行います。</span><span class="sxs-lookup"><span data-stu-id="34c92-106">You do this using your on-premises deployment while the user is still homed in the on-premises deployment.</span></span>

> [!Important]
> <span data-ttu-id="34c92-107">Skype for Business Online は 2021 年 7 月 31 日に廃止され、その後サービスにアクセスできなくなりました。</span><span class="sxs-lookup"><span data-stu-id="34c92-107">Skype for Business Online will be retired on July 31, 2021 after which the service will no longer be accessible.</span></span>  <span data-ttu-id="34c92-108">さらに、Skype for Business Server または Cloud Connector Edition と Skype for Business Online を介したオンプレミス環境間の PSTN 接続はサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="34c92-108">In addition, PSTN connectivity between your on-premises environment whether through Skype for Business Server or Cloud Connector Edition and Skype for Business Online will no longer be supported.</span></span>  <span data-ttu-id="34c92-109">直接ルーティングを使用してオンプレミスのテレフォニー ネットワークを Teams に接続する方法 [について説明します](/MicrosoftTeams/direct-routing-landing-page)。</span><span class="sxs-lookup"><span data-stu-id="34c92-109">Learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>
  
### <a name="to-enable-a-user-for-enterprise-voice-on-premises-and-assign-a-phone-number"></a><span data-ttu-id="34c92-110">オンプレミスのユーザーを有効エンタープライズ VoIP電話番号を割り当てるには</span><span class="sxs-lookup"><span data-stu-id="34c92-110">To enable a user for Enterprise Voice on premises and assign a phone number</span></span>

1. <span data-ttu-id="34c92-111">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="34c92-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="34c92-112">[スタート] メニューまたはデスクトップ ショートカットを使用して、Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="34c92-112">Use the Start menu or desktop shortcut to open the Skype for Business Server Control Panel.</span></span>
    
    <span data-ttu-id="34c92-113">ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開く方法もできます。</span><span class="sxs-lookup"><span data-stu-id="34c92-113">You can also open a browser window, and then enter the Administrator URL to open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="34c92-114">左側のナビゲーション バーで **[ユーザー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34c92-114">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="34c92-115">**[ユーザーの検索]** ボックスに、有効にするユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) の全体か最初の一部の文字列を入力して、**[検索]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34c92-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="34c92-116">表で、Skype for Business Online ユーザー アカウントをクリックして、このユーザー アカウントを有効エンタープライズ VoIP。</span><span class="sxs-lookup"><span data-stu-id="34c92-116">In the table, click the Skype for Business Online user account that you want to enable for Enterprise Voice.</span></span>
    
6. <span data-ttu-id="34c92-117">[編集] **メニューの** [詳細の表示 **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="34c92-117">On the **Edit** menu, click **Show Details**.</span></span>
    
7. <span data-ttu-id="34c92-118">[ **テレフォニー] の** 下の [エンタープライズ VoIP] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="34c92-118">Under **Telephony**, click **Enterprise Voice**.</span></span>
    
8. <span data-ttu-id="34c92-119">[ **回線 URI]** をクリックし、正規化された一意の電話番号 (tel:+14255550200 など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="34c92-119">Click **Line URI**, and type a unique, normalized phone number (for example, tel:+14255550200).</span></span> <span data-ttu-id="34c92-120">次に、[ **コミット] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="34c92-120">Then click **Commit**.</span></span>
    
## <a name="special-considerations-when-enabling-users-for-enterprise-voice-on-premises"></a><span data-ttu-id="34c92-121">オンプレミスでユーザーを有効にする場合のエンタープライズ VoIP考慮事項</span><span class="sxs-lookup"><span data-stu-id="34c92-121">Special considerations when enabling users for Enterprise Voice on premises</span></span>

<span data-ttu-id="34c92-122">場合によっては、ユーザーが通話を正常に行って受信エンタープライズ VoIPを有効にする方法を変更する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="34c92-122">In some cases, you may need to modify the way you enable users for Enterprise Voice to make sure that they can successfully make and receive calls.</span></span> <span data-ttu-id="34c92-123">展開内に次の条件を満たすユーザーが含まれている場合は、含まれる手順を実行して、ユーザーが次の条件を満たエンタープライズ VoIP。</span><span class="sxs-lookup"><span data-stu-id="34c92-123">If you have users in your deployment that meet the following conditions, perform the steps included to enable the user for Enterprise Voice.</span></span>
  
- <span data-ttu-id="34c92-124">ユーザーがオンプレミス AD で作成され、Skype for Business または エンタープライズ VoIP で有効にせずに Skype for Business Online と同期され、LineURI セットがない場合は、影響を受ける各ユーザーに対して次のコマンドレットを実行し、環境の実際の値で値を置き換えます \< \> 。</span><span class="sxs-lookup"><span data-stu-id="34c92-124">If a user is created in your on-premises AD and then synchronized with Skype for Business Online without being enabled for Skype for Business or for Enterprise Voice and do not have a LineURI set, run the following cmdlets for each affected user, replacing the values in \< \> with actual values for your environment:</span></span>
    
  ```powershell
  Enable-CsUser $username -HostingProvider sipfed.online.lync.com -SipAddress sip:<UserName>@<SIP Domain>
  ```

  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- <span data-ttu-id="34c92-125">ユーザーがオンプレミスの Skype for Business で既に有効になっているが、エンタープライズ VoIP で有効になっていないか、Skype for Business Online に移動する前に LineURI が割り当てられていない場合は、各ユーザーに対して次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="34c92-125">If a user is already enabled for Skype for Business on premises, but was not enabled for Enterprise Voice or assigned a LineURI before being moved to Skype for Business Online, run the following cmdlet for each user:</span></span>
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- <span data-ttu-id="34c92-126">ユーザーがオンプレミスの Skype for Business で既に有効になっているが、エンタープライズ VoIP に対して有効になっていない場合は、LineURI が既に割り当てられている場合でも、影響を受ける各ユーザーに対して次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="34c92-126">If a user is already enabled in Skype for Business on premises but not enabled for Enterprise Voice, even if already assigned a LineURI, run the following cmdlet for each affected user:</span></span>
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true
  ```