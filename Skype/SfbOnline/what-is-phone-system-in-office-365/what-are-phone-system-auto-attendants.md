---
title: "電話システムでの自動応答を挙げてください。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: makolomi
ms.date: 01/22/2018
ms.topic: article
ms.assetid: ab9f05a2-22cb-4692-a585-27f82d1b37c7
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
- Strat_SB_PSTN
description: "電話システムで (クラウド PBX) の自動応答の意味と使用する方法について説明します。 "
ms.openlocfilehash: 0c2478be3256d63a80263f70a1a70e6f2eaef3b3
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="what-are-phone-system-auto-attendants"></a><span data-ttu-id="b8a8b-103">電話システムでの自動応答を挙げてください。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-103">What are Phone System auto attendants?</span></span>

<span data-ttu-id="b8a8b-104">Office 365 の自動応答を使用して、内部および外部の発信者に応答する組織のメニュー システムを作成することで、電話システムを探し、配置、会社のユーザーや、組織内の部門に通話を転送するメニュー システムを移動します。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-104">Phone System in Office 365 auto attendants can be used to create a menu system for your organization that lets external and internal callers move through a menu system to locate and place or transfer calls to company users or departments in your organization.</span></span>
  
<span data-ttu-id="b8a8b-p101">連絡先を呼び出すと、一連のユーザーに電話をかけるや、組織内の他のユーザーを検索し、そのユーザーに電話をかけることを促すボイス メッセージが表示されます。自動応答では、一連を促すボイス メッセージまたはオーディオ ファイルを組織にコールインする場合に、発信者がオペレーターではなく聞くです。自動応答には、メニュー システムを移動する、通話、または電話のキーパッド (DTMF) を使用してユーザーを検索または音声認識を使って入力を音声に発信者ことができます。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-p101">When people call, they are presented with a series of voice prompts that help them place a call to a user or locate someone in your organization and then place a call to that user. An auto attendant is a series of voice prompts or an audio file that callers hear instead of a human operator when they call in to an organization. An auto attendant lets callers move through the menu system, place calls, or locate users by using a phone keypad (DTMF) or voice inputs using speech recognition.</span></span> 
  
<span data-ttu-id="b8a8b-108">Office 365 で電話システムの自動応答を設定するには、[電話システムでの自動応答を設定する](set-up-a-phone-system-auto-attendant.md)を移動します。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-108">To set up an auto attendant for the Phone System in Office 365, go [Set up a Phone System auto attendant](set-up-a-phone-system-auto-attendant.md).</span></span>
  
<span data-ttu-id="b8a8b-109">電話システムでの自動応答では、次の機能があります。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-109">A Phone System auto attendant has the following features:</span></span>
  
- <span data-ttu-id="b8a8b-110">組織または情報提供の案内応答を提供できます。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-110">It can provide corporate or informational greetings.</span></span>
    
- <span data-ttu-id="b8a8b-p102">社内のユーザー設定のメニューを提供できます。これらのメニューには、複数のレベルをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-p102">It can provide custom corporate menus. You can customize these menus to have more than one level.</span></span>
    
- <span data-ttu-id="b8a8b-113">ディレクトリの検索できるように、組織のディレクトリから名前を検索する電話の発信元のユーザーが用意されています。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-113">It provides directory search that enables people who call in to search the organization's directory for a name.</span></span>
    
- <span data-ttu-id="b8a8b-114">メッセージの送信または組織のユーザーのメッセージを残すに通話しているユーザーができるようにします。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-114">It enables someone who calls in to reach or leave a message for a person in your organization.</span></span>
    
## <a name="getting-started"></a><span data-ttu-id="b8a8b-115">はじめに</span><span class="sxs-lookup"><span data-stu-id="b8a8b-115">Getting started</span></span>

<span data-ttu-id="b8a8b-116">自動応答を使用を開始することが重要ことを忘れないでください。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-116">To get started using auto attendants, it's important to remember that:</span></span>
  
- <span data-ttu-id="b8a8b-p103">組織は、Enterprise E3 および**電話システム**のライセンスまたは Enterprise E5 ライセンス (最低) が必要です。サービスの数の数値の影響を割り当てられている**電話システムで**ユーザーのライセンスの数の自動応答のために利用できます。した自動応答の数は、組織内で割り当てられている番号の**電話システム**と**電話会議**ライセンスとは異なります。ライセンスの詳細については、 [Skype for Business や Microsoft チーム アドオンのライセンス](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)を移動します。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-p103">Your organization must have (at a minimum) an Enterprise E3 plus **Phone System** license or an Enterprise E5 license. The number of **Phone System** user licenses that are assigned impacts the number of service numbers that are available to be used for auto attendants. The number of auto attendants you can have is dependent on the number **Phone System** and **Audio Conferencing** licenses that are assigned in your organization. To learn more about licensing, go [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
    > [!TIP]
    > <span data-ttu-id="b8a8b-p104">演算子または**電話システムで**ライセンスを使って、オンラインのユーザーである] メニューのオプションに通話をリダイレクトするには、エンタープライズ ボイスを有効にする、またはにプランの呼び出しを割り当てる必要があります。[ビジネスや Microsoft チームのライセンスを割り当てる Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)を参照してください。Windows PowerShell を使用することもできます。例を実行します。`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="b8a8b-p104">To redirect calls to an operator or a menu option that is an Online user with a **Phone System** license, you will need to enable them for Enterprise Voice or assign Calling Plans to them. See[Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). You can also use Windows PowerShell. For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>
  
- <span data-ttu-id="b8a8b-p105">サービスのフリー ダイヤル番号を自動応答の使用をするには、クレジットの通信を設定する必要があります。これを行うには、次を参照してください。[通信を加算したものは何ですか?](../skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits.md)し、[組織の通信クレジットを設定](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md)します。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-p105">To get and use toll-free service numbers for your auto attendants, you need to set up Communications Credits. To do this, see [What are Communications Credits?](../skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits.md) and [Set up Communications Credits for your organization](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md).</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="b8a8b-127">自動応答するユーザー (サブスクライバー) の電話番号を割り当てることができません - サービスの有料またはフリー ダイヤル電話番号のみを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-127">User (subscriber) phone numbers can't be assigned to auto attendants - only service toll or toll-free phone numbers can be used.</span></span> 
  
## <a name="feature-overview"></a><span data-ttu-id="b8a8b-128">機能の概要</span><span class="sxs-lookup"><span data-stu-id="b8a8b-128">Feature overview</span></span>

### <a name="dial-by-name"></a><span data-ttu-id="b8a8b-129">名前をダイヤルします。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-129">Dial by Name</span></span>

<span data-ttu-id="b8a8b-p106">ダイヤル名では、ディレクトリの検索と呼ばれる自動応答の機能です。会社のディレクトリを検索、そのユーザーを検索しに通話を転送全体または一部の名前を入力する音声 (音声) または (DTMF)、電話のキーパッドを使用するには、自動応答に参加するユーザーができるようにします。ある場合は Skype for Business Online ユーザー**これらは必要ありませんが、電話番号またはには、プランの呼び出しを割り当てるが電話システムでのライセンスが必要**にダイヤル名を使用して検索するときに到達します。名前でダイヤルを検索して、skype for Business Online のユーザーが異なる国や地域多国籍の組織でホストされている着信転送もできます。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-p106">Dial by Name is a feature of an auto attendant that is known as directory search. It enables the people who call in to your auto attendant to use voice (speech recognition) or their phone keypad (DTMF) to enter a full or partial name to search company's directory, locate the person, and then have the call transferred to them. If you have Skype for Business Online users, **they aren't required to have a phone number or have Calling Plans assigned to them, but they must have a Phone System license** for them to be reachable when they search using Dial by Name. Dial by Name will even be able to find and transfer calls to Skype for Business Online users who are hosted in different countries or regions for multi-national organizations.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="b8a8b-134">それらのユーザーを検索するとき、Lync Server 2010 のユーザーの内部設置型の展開をディレクトリに表示されません。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-134">On-premises deployments of Lync Server 2010 users won't be listed in the directory when someone searches for them.</span></span> 
  
### <a name="maximum-directory-size"></a><span data-ttu-id="b8a8b-135">ディレクトリの最大サイズ</span><span class="sxs-lookup"><span data-stu-id="b8a8b-135">Maximum directory size</span></span>

<span data-ttu-id="b8a8b-p107">一部または全部の名前 (FirstName、LastName とも LastName + FirstName) を入力するための検索する電話のキーパッドを使用する場合の名前でダイヤルがサポートされて Active Directory のサイズの制限はありません。ただし、名前の最大リストのサイズが音声で名前認識を使用する 1 つの自動応答をサポートすることは、80,000 ユーザーです。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-p107">There is no limit on the Active Directory size for which Dial by Name is supported when using the phone keypad to search for entering partial or full names (FirstName + LastName, and also LastName + FirstName). However, the maximum name list size that a single auto attendant can support using name recognition with speech is 80,000 users.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="b8a8b-138">**入力の種類**</span><span class="sxs-lookup"><span data-stu-id="b8a8b-138">**Input type**</span></span> <br/> |<span data-ttu-id="b8a8b-139">**検索の書式設定**</span><span class="sxs-lookup"><span data-stu-id="b8a8b-139">**Search format**</span></span> <br/> |<span data-ttu-id="b8a8b-140">**組織内のユーザーの最大数**</span><span class="sxs-lookup"><span data-stu-id="b8a8b-140">**Maximum number of users in an organization**</span></span> <br/> |
|<span data-ttu-id="b8a8b-141">DTMF (キーパッド登録)</span><span class="sxs-lookup"><span data-stu-id="b8a8b-141">DTMF (keypad entry)</span></span>  <br/> |<span data-ttu-id="b8a8b-142">部分的</span><span class="sxs-lookup"><span data-stu-id="b8a8b-142">Partial</span></span>  <br/> <span data-ttu-id="b8a8b-143">FirstName + LastName</span><span class="sxs-lookup"><span data-stu-id="b8a8b-143">FirstName + LastName</span></span>  <br/> <span data-ttu-id="b8a8b-144">[氏名] + FirstName</span><span class="sxs-lookup"><span data-stu-id="b8a8b-144">LastName + FirstName</span></span>  <br/> |<span data-ttu-id="b8a8b-145">ハード制限なし</span><span class="sxs-lookup"><span data-stu-id="b8a8b-145">No hard limit</span></span>  <br/> |
|<span data-ttu-id="b8a8b-146">音声 (音声入力)</span><span class="sxs-lookup"><span data-stu-id="b8a8b-146">Speech (voice input)</span></span>  <br/> |<span data-ttu-id="b8a8b-147">{FirstName}</span><span class="sxs-lookup"><span data-stu-id="b8a8b-147">FirstName</span></span>  <br/> <span data-ttu-id="b8a8b-148">LastName</span><span class="sxs-lookup"><span data-stu-id="b8a8b-148">LastName</span></span>  <br/> <span data-ttu-id="b8a8b-149">FirstName + LastName</span><span class="sxs-lookup"><span data-stu-id="b8a8b-149">FirstName + LastName</span></span>  <br/> <span data-ttu-id="b8a8b-150">[氏名] + FirstName</span><span class="sxs-lookup"><span data-stu-id="b8a8b-150">LastName + FirstName</span></span>  <br/> |<span data-ttu-id="b8a8b-151">80,000 ユーザー</span><span class="sxs-lookup"><span data-stu-id="b8a8b-151">80,000 users</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="b8a8b-p108">音声認識機能は、組織の Active Directory は、80,000 ユーザーよりも大きいとダイヤル スコープ機能を使用して名前でダイヤルの範囲を限定していない、電話のキーパッドを使用して、発信者の名前でダイヤルが引き続きダイヤル名を使用している場合、、その他のすべてのシナリオを利用できる音声入力します。ダイヤルする特定の自動応答の名前の範囲を変更することによって到達可能な名前を絞り込むダイヤル スコープ機能を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-p108">If you are using Dial by Name with speech recognition, but your organization's Active Directory is bigger than 80,000 users and you haven't limited the scope of Dial by Name using Dial Scope feature, Dial by Name will still work for your callers using a phone keypad, and voice inputs will be available for all other scenarios. You can use the Dial Scope feature to narrow down the names that are reachable by changing the scope of Dial by Name for a particular auto attendant.</span></span> 
  
### <a name="dial-by-name---keypad-dtmf-entry"></a><span data-ttu-id="b8a8b-154">名前のキーパッド (DTMF) エントリをダイヤルします。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-154">Dial by Name - Keypad (DTMF) entry</span></span>

<span data-ttu-id="b8a8b-p109">人数では、いずれかに到達しようとしているユーザーのすべてまたは一部の名前を指定してユーザーに到達するのに名前でダイヤルを使用できます。良いことは、名前を入力するときに使用できるさまざまな形式があります。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-p109">People calling in can use Dial by Name to reach users by specifying either the full or partial name of the person they are trying to reach. The good thing is that there are various formats that can be used when the name is entered.</span></span>
  
<span data-ttu-id="b8a8b-p110">組織のディレクトリを検索するには、ユーザー キーを使って「0」(ゼロ)、名と姓と間スペースを示すまたは最後の名前とします。名前を入力しているときに # (ポンド) キーを使用して、キーパッドのエントリを終了するように要求されます。たとえば、「到達しようとしている人の名前を入力したら、キーを押して #。」呼び出し先の人、検出された複数の名前がある場合にから選択する名前のリストを与えられます。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-p110">When searching your organization's directory, people can use the '0' (zero) key to indicate a space between the first name and last or last name and first. When they are entering the name, they will be asked to terminate their keypad entry with the # (pound) key. For example, "After you enter the name of the person you are trying to reach, press #." If there are multiple names that are found, the person calling will be given a list of names to select from.</span></span>
  
<span data-ttu-id="b8a8b-161">ユーザーは、電話のキーパッドの検索の次の形式を使用して、組織の名前を検索できます。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-161">People can search for names in your organization using the following search formats on their phone keypad:</span></span>
  
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b8a8b-162">**名前の形式**</span><span class="sxs-lookup"><span data-stu-id="b8a8b-162">**Name format**</span></span> <br/> |<span data-ttu-id="b8a8b-163">**検索の種類**</span><span class="sxs-lookup"><span data-stu-id="b8a8b-163">**Search type**</span></span> <br/> |<span data-ttu-id="b8a8b-164">**{例}**</span><span class="sxs-lookup"><span data-stu-id="b8a8b-164">**Example**</span></span> <br/> |<span data-ttu-id="b8a8b-165">**検索結果**</span><span class="sxs-lookup"><span data-stu-id="b8a8b-165">**Search result**</span></span> <br/> |
|<span data-ttu-id="b8a8b-166">FirstName + LastName</span><span class="sxs-lookup"><span data-stu-id="b8a8b-166">FirstName + LastName</span></span>  <br/> |<span data-ttu-id="b8a8b-167">完全です</span><span class="sxs-lookup"><span data-stu-id="b8a8b-167">Full</span></span>  <br/> |<span data-ttu-id="b8a8b-168">Amos0Marble #</span><span class="sxs-lookup"><span data-stu-id="b8a8b-168">Amos0Marble#</span></span>  <br/> |<span data-ttu-id="b8a8b-169">Amos 大理石</span><span class="sxs-lookup"><span data-stu-id="b8a8b-169">Amos Marble</span></span>  <br/> |
|<span data-ttu-id="b8a8b-170">[氏名] + FirstName</span><span class="sxs-lookup"><span data-stu-id="b8a8b-170">LastName + FirstName</span></span>  <br/> |<span data-ttu-id="b8a8b-171">完全です</span><span class="sxs-lookup"><span data-stu-id="b8a8b-171">Full</span></span>  <br/> |<span data-ttu-id="b8a8b-172">Marble0Amos #</span><span class="sxs-lookup"><span data-stu-id="b8a8b-172">Marble0Amos#</span></span>  <br/> |<span data-ttu-id="b8a8b-173">Amos 大理石</span><span class="sxs-lookup"><span data-stu-id="b8a8b-173">Amos Marble</span></span>  <br/> |
|<span data-ttu-id="b8a8b-174">{FirstName}</span><span class="sxs-lookup"><span data-stu-id="b8a8b-174">FirstName</span></span>  <br/> |<span data-ttu-id="b8a8b-175">完全です</span><span class="sxs-lookup"><span data-stu-id="b8a8b-175">Full</span></span>  <br/> |<span data-ttu-id="b8a8b-176">Amos #</span><span class="sxs-lookup"><span data-stu-id="b8a8b-176">Amos#</span></span>  <br/> |<span data-ttu-id="b8a8b-177">Amos 大理石 1 を押す</span><span class="sxs-lookup"><span data-stu-id="b8a8b-177">Press 1 for Amos Marble</span></span>  <br/> <span data-ttu-id="b8a8b-178">Amos Marcus の 2 キーを押します</span><span class="sxs-lookup"><span data-stu-id="b8a8b-178">Press 2 for Amos Marcus</span></span>  <br/> |
|<span data-ttu-id="b8a8b-179">LastName</span><span class="sxs-lookup"><span data-stu-id="b8a8b-179">LastName</span></span>  <br/> |<span data-ttu-id="b8a8b-180">完全です</span><span class="sxs-lookup"><span data-stu-id="b8a8b-180">Full</span></span>  <br/> |<span data-ttu-id="b8a8b-181">大理石 #</span><span class="sxs-lookup"><span data-stu-id="b8a8b-181">Marble#</span></span>  <br/> |<span data-ttu-id="b8a8b-182">Amos 大理石 1 を押す</span><span class="sxs-lookup"><span data-stu-id="b8a8b-182">Press 1 for Amos Marble</span></span>  <br/> <span data-ttu-id="b8a8b-183">Mary 大理石の 2 キーを押します</span><span class="sxs-lookup"><span data-stu-id="b8a8b-183">Press 2 for Mary Marble</span></span>  <br/> |
|<span data-ttu-id="b8a8b-184">FirstName、LastName または</span><span class="sxs-lookup"><span data-stu-id="b8a8b-184">FirstName or LastName</span></span>  <br/> |<span data-ttu-id="b8a8b-185">部分的</span><span class="sxs-lookup"><span data-stu-id="b8a8b-185">Partial</span></span>  <br/> |<span data-ttu-id="b8a8b-186">3 月 #</span><span class="sxs-lookup"><span data-stu-id="b8a8b-186">Mar#</span></span>  <br/> |<span data-ttu-id="b8a8b-187">Mary 大理石 1 を押す</span><span class="sxs-lookup"><span data-stu-id="b8a8b-187">Press 1 for Mary Marble</span></span>  <br/> <span data-ttu-id="b8a8b-188">Mary 平均の 2 キーを押します</span><span class="sxs-lookup"><span data-stu-id="b8a8b-188">Press 2 for Mary Jones</span></span>  <br/> <span data-ttu-id="b8a8b-189">Amos Marcus の 3 キーを押します</span><span class="sxs-lookup"><span data-stu-id="b8a8b-189">Press 3 for Amos Marcus</span></span>  <br/> |
|<span data-ttu-id="b8a8b-190">FirsName + LastName</span><span class="sxs-lookup"><span data-stu-id="b8a8b-190">FirsName + LastName</span></span>  <br/> |<span data-ttu-id="b8a8b-191">部分的</span><span class="sxs-lookup"><span data-stu-id="b8a8b-191">Partial</span></span>  <br/> |<span data-ttu-id="b8a8b-192">Mar0Amos #</span><span class="sxs-lookup"><span data-stu-id="b8a8b-192">Mar0Amos#</span></span>  <br/> |<span data-ttu-id="b8a8b-193">Amos 大理石 1 を押す</span><span class="sxs-lookup"><span data-stu-id="b8a8b-193">Press 1 for Amos Marble</span></span>  <br/> <span data-ttu-id="b8a8b-194">Amos Marcus の 2 キーを押します</span><span class="sxs-lookup"><span data-stu-id="b8a8b-194">Press 2 for Amos Marcus</span></span>  <br/> |
|<span data-ttu-id="b8a8b-195">[氏名] + FirstName</span><span class="sxs-lookup"><span data-stu-id="b8a8b-195">LastName + FirstName</span></span>  <br/> |<span data-ttu-id="b8a8b-196">部分的</span><span class="sxs-lookup"><span data-stu-id="b8a8b-196">Partial</span></span>  <br/> |<span data-ttu-id="b8a8b-197">Mar0Am #</span><span class="sxs-lookup"><span data-stu-id="b8a8b-197">Mar0Am#</span></span>  <br/> |<span data-ttu-id="b8a8b-198">Amos 大理石 1 を押す</span><span class="sxs-lookup"><span data-stu-id="b8a8b-198">Press 1 for Amos Marble</span></span>  <br/> <span data-ttu-id="b8a8b-199">Amos Marcus の 2 キーを押します</span><span class="sxs-lookup"><span data-stu-id="b8a8b-199">Press 2 for Amos Marcus</span></span>  <br/> |
   
<span data-ttu-id="b8a8b-p111">電話のキーパッドを使っているユーザーを検索するときに使用される、いくつかの特殊文字があります。たとえば、ユーザーは、シャープ キーを使用するように求められます (#)、名前の間にスペースがゼロ (0) キーを使用します。スター キー (\*) を押すと、一致するユーザーの名前のリストを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-p111">There are several special characters that are used when searching for people using a phone keypad. For example, the person will be asked to use the pound key (#), while the zero (0) key is used for a space between names. Pressing the star key (\*) will repeat the list of matching names to the person.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="b8a8b-203">**電話のキーパッドの文字**</span><span class="sxs-lookup"><span data-stu-id="b8a8b-203">**Special phone keypad character**</span></span> <br/> |<span data-ttu-id="b8a8b-204">**意味**</span><span class="sxs-lookup"><span data-stu-id="b8a8b-204">**What it means**</span></span> <br/> |
|<span data-ttu-id="b8a8b-205"># (ポンド キー)</span><span class="sxs-lookup"><span data-stu-id="b8a8b-205"># (pound key)</span></span>  <br/> |<span data-ttu-id="b8a8b-206">名前を入力するときに、文字を終了します。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-206">End character when entering a name.</span></span>  <br/> |
|<span data-ttu-id="b8a8b-207">0 (ゼロ)</span><span class="sxs-lookup"><span data-stu-id="b8a8b-207">0 (zero)</span></span>  <br/> |<span data-ttu-id="b8a8b-208">名前の間のスペースです。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-208">Space between names.</span></span>  <br/> |
|<span data-ttu-id="b8a8b-209">\* (アスタリスク キー)</span><span class="sxs-lookup"><span data-stu-id="b8a8b-209">\* (star key)</span></span>  <br/> |<span data-ttu-id="b8a8b-210">同じ名前のリストを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-210">Repeat the list of matching names.</span></span>  <br/> |
   
### <a name="dial-by-name---name-recognition-with-speech"></a><span data-ttu-id="b8a8b-211">名前の音声と名前認識ダイヤルします。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-211">Dial by Name - Name recognition with speech</span></span>

<span data-ttu-id="b8a8b-p112">(音声認識)、音声を使用して、組織の他のユーザーを検索できます。検索しようとしている人の名前を示す到達する会社の Active Directory でユーザーもことができます。音声入力を使用すると、FirstName、LastName、FirstName、LastName LastName + または FirstName など、さまざまな形式の名前が認識することができます。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-p112">People can search for others in their organization using their voice (speech recognition). They can also reach anyone in the company's Active Directory by saying the name of the person they are trying to locate. Using voice inputs can recognize names in various formats, including FirstName, LastName, FirstName + LastName, or LastName + FirstName.</span></span>
  
<span data-ttu-id="b8a8b-p113">自動応答の音声認識を有効にすると電話のキーパッドのエントリ (DTMF) されません無効にする、両方の種類の入力を使用できるようにします。電話のキーパッドのエントリは無効にすることはできず、自動応答の音声認識機能が有効になっている場合でも、任意の時点で使用することができます。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-p113">When you enable speech recognition for an auto attendant, phone keypad entry (DTMF) won't be disabled, so both types of input can be used. Phone keypad entry can't be disabled and can be used at any time, even if speech recognition is enabled on the auto attendant.</span></span>
  
<span data-ttu-id="b8a8b-217">として、電話のキーパッドのエントリに複数の名前が見つかった場合、呼び出し先の人が表示されますから選択する名前のリストを含む。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-217">As with phone keypad entry, if multiple names are found, the person calling will be presented with a list of names to select from.</span></span>
  
<span data-ttu-id="b8a8b-218">ユーザーが電話には、次の形式で名前を可能です。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-218">People calling in can say names in the following formats:</span></span>
  
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b8a8b-219">**音声認識で名前を付ける**</span><span class="sxs-lookup"><span data-stu-id="b8a8b-219">**Name with speech**</span></span> <br/> |<span data-ttu-id="b8a8b-220">**検索の種類**</span><span class="sxs-lookup"><span data-stu-id="b8a8b-220">**Search type**</span></span> <br/> |<span data-ttu-id="b8a8b-221">**{例}**</span><span class="sxs-lookup"><span data-stu-id="b8a8b-221">**Example**</span></span> <br/> |<span data-ttu-id="b8a8b-222">**検索結果**</span><span class="sxs-lookup"><span data-stu-id="b8a8b-222">**Search result**</span></span> <br/> |
|<span data-ttu-id="b8a8b-223">FirstName + LastName</span><span class="sxs-lookup"><span data-stu-id="b8a8b-223">FirstName + LastName</span></span>  <br/> |<span data-ttu-id="b8a8b-224">完全です</span><span class="sxs-lookup"><span data-stu-id="b8a8b-224">Full</span></span>  <br/> |<span data-ttu-id="b8a8b-225">Amos 大理石</span><span class="sxs-lookup"><span data-stu-id="b8a8b-225">Amos Marble</span></span>  <br/> |<span data-ttu-id="b8a8b-226">Amos 大理石</span><span class="sxs-lookup"><span data-stu-id="b8a8b-226">Amos Marble</span></span>  <br/> |
|<span data-ttu-id="b8a8b-227">[氏名] + FirstName</span><span class="sxs-lookup"><span data-stu-id="b8a8b-227">LastName + FirstName</span></span>  <br/> |<span data-ttu-id="b8a8b-228">完全です</span><span class="sxs-lookup"><span data-stu-id="b8a8b-228">Full</span></span>  <br/> |<span data-ttu-id="b8a8b-229">大理石 Amos</span><span class="sxs-lookup"><span data-stu-id="b8a8b-229">Marble Amos</span></span>  <br/> |<span data-ttu-id="b8a8b-230">Amos 大理石</span><span class="sxs-lookup"><span data-stu-id="b8a8b-230">Amos Marble</span></span>  <br/> |
|<span data-ttu-id="b8a8b-231">{FirstName}</span><span class="sxs-lookup"><span data-stu-id="b8a8b-231">FirstName</span></span>  <br/> |<span data-ttu-id="b8a8b-232">完全です</span><span class="sxs-lookup"><span data-stu-id="b8a8b-232">Full</span></span>  <br/> |<span data-ttu-id="b8a8b-233">Amos</span><span class="sxs-lookup"><span data-stu-id="b8a8b-233">Amos</span></span>  <br/> |<span data-ttu-id="b8a8b-234">キーを押すか、Amos 大理石と 1</span><span class="sxs-lookup"><span data-stu-id="b8a8b-234">Press or say 1 for Amos Marble</span></span>  <br/> <span data-ttu-id="b8a8b-235">キーを押すか、Amos 平均と 2</span><span class="sxs-lookup"><span data-stu-id="b8a8b-235">Press or say 2 for Amos Jones</span></span>  <br/> |
|<span data-ttu-id="b8a8b-236">LastName</span><span class="sxs-lookup"><span data-stu-id="b8a8b-236">LastName</span></span>  <br/> |<span data-ttu-id="b8a8b-237">完全です</span><span class="sxs-lookup"><span data-stu-id="b8a8b-237">Full</span></span>  <br/> |<span data-ttu-id="b8a8b-238">大理石</span><span class="sxs-lookup"><span data-stu-id="b8a8b-238">Marble</span></span>  <br/> |<span data-ttu-id="b8a8b-239">キーを押すか、Amos 大理石と 1</span><span class="sxs-lookup"><span data-stu-id="b8a8b-239">Press or say 1 for Amos Marble</span></span>  <br/> <span data-ttu-id="b8a8b-240">キーを押すか、佐藤大理石と 2</span><span class="sxs-lookup"><span data-stu-id="b8a8b-240">Press or say 2 for Ben Marble</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="b8a8b-241">音声認識を名前でダイヤルのディレクトリに表示する相手の名前を使用して新しいユーザーの最大 36 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-241">It might take up to 36 hours for a new user to have their name listed in the directory for Dial by Name with speech recognition.</span></span> 
  
### <a name="language-support"></a><span data-ttu-id="b8a8b-242">言語のサポート</span><span class="sxs-lookup"><span data-stu-id="b8a8b-242">Language support</span></span>

<span data-ttu-id="b8a8b-243">以下の言語で音声合成機能利用できます。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-243">The following languages are available for text-to-speech:</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="b8a8b-244">アラビア語 (EG)</span><span class="sxs-lookup"><span data-stu-id="b8a8b-244">Arabic (EG)</span></span>  <br/> |<span data-ttu-id="b8a8b-245">英語 (ニュージーランド)</span><span class="sxs-lookup"><span data-stu-id="b8a8b-245">English (NZ)</span></span>  <br/> |<span data-ttu-id="b8a8b-246">韓国語 (KO)</span><span class="sxs-lookup"><span data-stu-id="b8a8b-246">Korean (KO)</span></span>  <br/> |
|<span data-ttu-id="b8a8b-247">中国語 (香港)</span><span class="sxs-lookup"><span data-stu-id="b8a8b-247">Chinese (HK)</span></span>  <br/> |<span data-ttu-id="b8a8b-248">英語 (英国)</span><span class="sxs-lookup"><span data-stu-id="b8a8b-248">English (UK)</span></span>  <br/> |<span data-ttu-id="b8a8b-249">ノルウェー語 (なし)</span><span class="sxs-lookup"><span data-stu-id="b8a8b-249">Norwegian (NO)</span></span>  <br/> |
|<span data-ttu-id="b8a8b-250">中国語 (TW)</span><span class="sxs-lookup"><span data-stu-id="b8a8b-250">Chinese (TW)</span></span>  <br/> |<span data-ttu-id="b8a8b-251">英語 (米国)</span><span class="sxs-lookup"><span data-stu-id="b8a8b-251">English (US)</span></span>  <br/> |<span data-ttu-id="b8a8b-252">ポーランド語 (PL)</span><span class="sxs-lookup"><span data-stu-id="b8a8b-252">Polish (PL)</span></span>  <br/> |
|<span data-ttu-id="b8a8b-253">中国語 (ZH)</span><span class="sxs-lookup"><span data-stu-id="b8a8b-253">Chinese (ZH)</span></span>  <br/> |<span data-ttu-id="b8a8b-254">フィンランド語 (など)</span><span class="sxs-lookup"><span data-stu-id="b8a8b-254">Finnish (FI)</span></span>  <br/> |<span data-ttu-id="b8a8b-255">ポルトガル語 (BR)</span><span class="sxs-lookup"><span data-stu-id="b8a8b-255">Portuguese (BR)</span></span>  <br/> |
|<span data-ttu-id="b8a8b-256">デンマーク語 (DA)</span><span class="sxs-lookup"><span data-stu-id="b8a8b-256">Danish (DA)</span></span>  <br/> |<span data-ttu-id="b8a8b-257">フランス語 (CA)</span><span class="sxs-lookup"><span data-stu-id="b8a8b-257">French (CA)</span></span>  <br/> |<span data-ttu-id="b8a8b-258">ポルトガル語 (PT)</span><span class="sxs-lookup"><span data-stu-id="b8a8b-258">Portuguese (PT)</span></span>  <br/> |
|<span data-ttu-id="b8a8b-259">オランダ語 (NL)</span><span class="sxs-lookup"><span data-stu-id="b8a8b-259">Dutch (NL)</span></span>  <br/> |<span data-ttu-id="b8a8b-260">フランス語 (FR)</span><span class="sxs-lookup"><span data-stu-id="b8a8b-260">French (FR)</span></span>  <br/> |<span data-ttu-id="b8a8b-261">ロシア語 (RU)</span><span class="sxs-lookup"><span data-stu-id="b8a8b-261">Russian (RU)</span></span>  <br/> |
|<span data-ttu-id="b8a8b-262">英語 (AU)</span><span class="sxs-lookup"><span data-stu-id="b8a8b-262">English (AU)</span></span>  <br/> |<span data-ttu-id="b8a8b-263">ドイツ語 (DE)</span><span class="sxs-lookup"><span data-stu-id="b8a8b-263">German (DE)</span></span>  <br/> |<span data-ttu-id="b8a8b-264">スペイン語 (ES)</span><span class="sxs-lookup"><span data-stu-id="b8a8b-264">Spanish (ES)</span></span>  <br/> |
|<span data-ttu-id="b8a8b-265">英語 (CA)</span><span class="sxs-lookup"><span data-stu-id="b8a8b-265">English (CA)</span></span>  <br/> |<span data-ttu-id="b8a8b-266">イタリア語 (IT)</span><span class="sxs-lookup"><span data-stu-id="b8a8b-266">Italian (IT)</span></span>  <br/> |<span data-ttu-id="b8a8b-267">スペイン語 (MX)</span><span class="sxs-lookup"><span data-stu-id="b8a8b-267">Spanish (MX)</span></span>  <br/> |
|<span data-ttu-id="b8a8b-268">英語 (IN)</span><span class="sxs-lookup"><span data-stu-id="b8a8b-268">English (IN)</span></span>  <br/> |<span data-ttu-id="b8a8b-269">日本語 (日本)</span><span class="sxs-lookup"><span data-stu-id="b8a8b-269">Japanese (JP)</span></span>  <br/> |<span data-ttu-id="b8a8b-270">スウェーデン語 (SV)</span><span class="sxs-lookup"><span data-stu-id="b8a8b-270">Swedish (SV)</span></span>  <br/> |
   
<span data-ttu-id="b8a8b-271">自動応答の音声認識は、以下の言語で利用できます。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-271">Speech recognition for auto attendants is available in the following languages:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="b8a8b-272">中国語 (ZH)</span><span class="sxs-lookup"><span data-stu-id="b8a8b-272">Chinese (ZH)</span></span>  <br/> |<span data-ttu-id="b8a8b-273">フランス語 (FR)</span><span class="sxs-lookup"><span data-stu-id="b8a8b-273">French (FR)</span></span>  <br/> |
|<span data-ttu-id="b8a8b-274">英語 (AU)</span><span class="sxs-lookup"><span data-stu-id="b8a8b-274">English (AU)</span></span>  <br/> |<span data-ttu-id="b8a8b-275">ドイツ語 (DE)</span><span class="sxs-lookup"><span data-stu-id="b8a8b-275">German (DE)</span></span>  <br/> |
|<span data-ttu-id="b8a8b-276">英語 (CA)</span><span class="sxs-lookup"><span data-stu-id="b8a8b-276">English (CA)</span></span>  <br/> |<span data-ttu-id="b8a8b-277">イタリア語 (IT)</span><span class="sxs-lookup"><span data-stu-id="b8a8b-277">Italian (IT)</span></span>  <br/> |
|<span data-ttu-id="b8a8b-278">英語 (IN)</span><span class="sxs-lookup"><span data-stu-id="b8a8b-278">English (IN)</span></span>  <br/> |<span data-ttu-id="b8a8b-279">日本語 (日本)</span><span class="sxs-lookup"><span data-stu-id="b8a8b-279">Japanese (JP)</span></span>  <br/> |
|<span data-ttu-id="b8a8b-280">英語 (英国)</span><span class="sxs-lookup"><span data-stu-id="b8a8b-280">English (UK)</span></span>  <br/> |<span data-ttu-id="b8a8b-281">ポルトガル語 (BR)</span><span class="sxs-lookup"><span data-stu-id="b8a8b-281">Portuguese (BR)</span></span>  <br/> |
|<span data-ttu-id="b8a8b-282">英語 (米国)</span><span class="sxs-lookup"><span data-stu-id="b8a8b-282">English (US)</span></span>  <br/> |<span data-ttu-id="b8a8b-283">スペイン語 (ES)</span><span class="sxs-lookup"><span data-stu-id="b8a8b-283">Spanish (ES)</span></span>  <br/> |
|<span data-ttu-id="b8a8b-284">フランス語 (CA)</span><span class="sxs-lookup"><span data-stu-id="b8a8b-284">French (CA)</span></span>  <br/> |<span data-ttu-id="b8a8b-285">スペイン語 (MX)</span><span class="sxs-lookup"><span data-stu-id="b8a8b-285">Spanish (MX)</span></span>  <br/> |
   
<span data-ttu-id="b8a8b-286">次の音声コマンド音声認識をサポートする 14 言語で利用できます。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-286">The following voice commands are available in the fourteen (14) languages supported for speech recognition:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="b8a8b-287">**音声コマンド**</span><span class="sxs-lookup"><span data-stu-id="b8a8b-287">**Voice command**</span></span> <br/> |<span data-ttu-id="b8a8b-288">**意味**</span><span class="sxs-lookup"><span data-stu-id="b8a8b-288">**Meaning**</span></span> <br/> |
|<span data-ttu-id="b8a8b-289">○</span><span class="sxs-lookup"><span data-stu-id="b8a8b-289">Yes</span></span>  <br/> |<span data-ttu-id="b8a8b-290">[はい] - 1 を押すと [はい] に対応しています。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-290">Yes - corresponds to pressing 1 for Yes.</span></span>  <br/> |
|<span data-ttu-id="b8a8b-291">×</span><span class="sxs-lookup"><span data-stu-id="b8a8b-291">No</span></span>  <br/> |<span data-ttu-id="b8a8b-292">2 を押すと [いいえ] に対応するいいえ</span><span class="sxs-lookup"><span data-stu-id="b8a8b-292">No - corresponds to pressing 2 for No.</span></span>  <br/> |
|<span data-ttu-id="b8a8b-293">この手順を繰り返します</span><span class="sxs-lookup"><span data-stu-id="b8a8b-293">Repeat</span></span>  <br/> |<span data-ttu-id="b8a8b-294">オプションの一覧を繰り返す - キーを押すことに対応する \* オプションの一覧を繰り返す。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-294">Repeats the list of options - corresponds to pressing \* to repeat the list of options.</span></span>  <br/> |
|<span data-ttu-id="b8a8b-295">演算子</span><span class="sxs-lookup"><span data-stu-id="b8a8b-295">Operator</span></span>  <br/> |<span data-ttu-id="b8a8b-296">ブレーク アウト - 演算子には、「演算子の」0 キーを押してに対応します。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-296">Breakout to operator - corresponds to pressing 0 for "Operator".</span></span>  <br/> |
|<span data-ttu-id="b8a8b-297">メイン メニュー</span><span class="sxs-lookup"><span data-stu-id="b8a8b-297">Main Menu</span></span>  <br/> |<span data-ttu-id="b8a8b-298">自動応答のメイン メニューに、発信者が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-298">Brings the caller to the main menu of the auto attendant.</span></span>  <br/> |
|<span data-ttu-id="b8a8b-299">ゼロ</span><span class="sxs-lookup"><span data-stu-id="b8a8b-299">Zero</span></span>  <br/> |<span data-ttu-id="b8a8b-300">0 (既定では「演算子」と同じ) キーを押してに対応します。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-300">Corresponds to pressing 0 (by default, same as "Operator").</span></span>  <br/> |
|<span data-ttu-id="b8a8b-301">   One  </span><span class="sxs-lookup"><span data-stu-id="b8a8b-301">One</span></span>  <br/> |<span data-ttu-id="b8a8b-302">1 キーを押してに対応します。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-302">Corresponds to pressing 1.</span></span>  <br/> |
|<span data-ttu-id="b8a8b-303">2 つ</span><span class="sxs-lookup"><span data-stu-id="b8a8b-303">Two</span></span>  <br/> |<span data-ttu-id="b8a8b-304">2 キーを押してに対応します。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-304">Corresponds to pressing 2.</span></span>  <br/> |
|<span data-ttu-id="b8a8b-305">次の 3 つ</span><span class="sxs-lookup"><span data-stu-id="b8a8b-305">Three</span></span>  <br/> |<span data-ttu-id="b8a8b-306">3 キーを押してに対応します。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-306">Corresponds to pressing 3.</span></span>  <br/> |
|<span data-ttu-id="b8a8b-307">4 つ</span><span class="sxs-lookup"><span data-stu-id="b8a8b-307">Four</span></span>  <br/> |<span data-ttu-id="b8a8b-308">4 キーを押してに対応します。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-308">Corresponds to pressing 4.</span></span>  <br/> |
|<span data-ttu-id="b8a8b-309">5</span><span class="sxs-lookup"><span data-stu-id="b8a8b-309">Five</span></span>  <br/> |<span data-ttu-id="b8a8b-310">5 キーを押してに対応します。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-310">Corresponds to pressing 5.</span></span>  <br/> |
|<span data-ttu-id="b8a8b-311">6</span><span class="sxs-lookup"><span data-stu-id="b8a8b-311">Six</span></span>  <br/> |<span data-ttu-id="b8a8b-312">6 キーを押してに対応します。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-312">Corresponds to pressing 6.</span></span>  <br/> |
|<span data-ttu-id="b8a8b-313">7</span><span class="sxs-lookup"><span data-stu-id="b8a8b-313">Seven</span></span>  <br/> |<span data-ttu-id="b8a8b-314">7 キーを押してに対応します。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-314">Corresponds to pressing 7.</span></span>  <br/> |
|<span data-ttu-id="b8a8b-315">8</span><span class="sxs-lookup"><span data-stu-id="b8a8b-315">Eight</span></span>  <br/> |<span data-ttu-id="b8a8b-316">8 キーを押してに対応します。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-316">Corresponds to pressing 8.</span></span>  <br/> |
|<span data-ttu-id="b8a8b-317">9</span><span class="sxs-lookup"><span data-stu-id="b8a8b-317">Nine</span></span>  <br/> |<span data-ttu-id="b8a8b-318">9 キーを押してに対応します。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-318">Corresponds to pressing 9.</span></span>  <br/> |
   
### <a name="using-the-operator-option"></a><span data-ttu-id="b8a8b-319">[演算子] オプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-319">Using the operator option</span></span>

<span data-ttu-id="b8a8b-320">ライブ人に読み上げ機能をオプションで、呼び出し先の人を提供するオプションの設定は、自動応答用に演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-320">Using the operator for an auto attendant is an optional setting that provides the person calling with an option to speak to a live person.</span></span>
  
<span data-ttu-id="b8a8b-321">既定では、キー 0 と、音声コマンド「演算子」(音声認識のサポートされているすべての言語) では、演算子に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-321">Key 0 and the voice command "Operator" (in all the languages supported for speech recognition) are assigned to operator by default.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b8a8b-322">**メニュー オプション**を使用して、**演算子**として別のキーに転送される] ボタンを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-322">You can set the button that is pushed for the **Operator** to a different key by using **Menu Options**.</span></span> 
  
<span data-ttu-id="b8a8b-323">演算子と、次を設定できます。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-323">You can set the following as the operator:</span></span>
  
- <span data-ttu-id="b8a8b-p114">Skype for Business Online のユーザー ライセンスを**電話システム**を持つエンタープライズ ボイスを有効にしたかに割り当てたプランの呼び出し。相手呼び出しをボイス メールを送信できないようにする設定ことができます。これを行うには、**社内のユーザー**を選択しが直接ボイス メールに自動的に転送するこのユーザーの呼び出しを設定します。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-p114">A Skype for Business Online user who has a **Phone System** license that is Enterprise Voice-enabled or has Calling Plans assigned to them. You can set it up so the person calling in can be sent to voicemail. To do this, select a **Person in your company** and set this person's calls to be automatically forwarded directly to voicemail.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b8a8b-327">ユーザーが内部設置型にホストされている演算子として使用する Lync Server 2010 を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-327">Users hosted on-premises using Lync Server 2010 can't be used as an Operator.</span></span> 
  
- <span data-ttu-id="b8a8b-328">組織用に設定されている他の自動応答します。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-328">Another auto attendant that's set up for your organization.</span></span>
    
- <span data-ttu-id="b8a8b-p115">組織で設定されて、既存通話キューです。通話キューの詳細を表示するには、[電話システムで通話キューを作成する](create-a-phone-system-call-queue.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-p115">Any existing call queue that's set up in your organization. To see more about call queues, see [Create a Phone System call queue](create-a-phone-system-call-queue.md).</span></span>
    
### <a name="business-hours-and-call-handling"></a><span data-ttu-id="b8a8b-331">営業時間と通話処理</span><span class="sxs-lookup"><span data-stu-id="b8a8b-331">Business hours and call handling</span></span>

<span data-ttu-id="b8a8b-p116">各自動応答の勤務時間が設定されています。営業時間が設定されていない場合は、すべての日と、その日のすべての稼働時間と見なされます勤務時間既定では、24 時間体制が設定されているため。日、およびすべての営業時間が時間外と見なされるように設定されていない時間中に区切りを設定した勤務時間を設定できます。別の着信通話処理オプションと (これは省略可能) 別のあいさつ文を設定して時間外し、営業時間の両方を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-p116">Business hours are set on each auto attendant. If business hours aren't set, all days and all hours in the day are considered business hours because a 24/7 schedule is set by default. Business hours can be set with breaks in time during the day, and all of the hours that are not set as business hours are considered after-hours. You can set different incoming call-handling options and different greetings (which are optional), and Both can be set for business hours and after-hours.</span></span>
  
<span data-ttu-id="b8a8b-336">各自動応答では、設定できる通話処理オプションがあります。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-336">Each auto attendant has call-handling options that can be set:</span></span>
  
- <span data-ttu-id="b8a8b-337">通話のあいさつ文の後に切断したことができます。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-337">You can have the call just disconnect after greeting.</span></span>
    
- <span data-ttu-id="b8a8b-338">次の操作も実行できます。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-338">You can also:</span></span>
    
  - <span data-ttu-id="b8a8b-p117">Skype for Business Online のユーザーがエンタープライズ ボイスが有効なライセンスが**電話システム**に通話をリダイレクトするかに割り当てたプランの呼び出しします。相手呼び出しをボイス メールを送信できないようにする設定ことができます。これを行うには、**社内のユーザー**を選択しが直接ボイス メールに自動的に転送するこのユーザーの呼び出しを設定します。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-p117">Redirect the call to a Skype for Business Online user who has a **Phone System** license that is Enterprise Voice-enabled or has Calling Plans assigned to them. You can set it up so the person calling in can be sent to voicemail. To do this, select a **Person in your company** and set this person's calls to be automatically forwarded directly to voicemail.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b8a8b-342">ユーザーが内部設置型にホストされている Lync Server 2010 の使用はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-342">Users hosted on-premises using Lync Server 2010 aren't supported.</span></span> 
  
  - <span data-ttu-id="b8a8b-p118">通話キューに通話をリダイレクトします。通話キューの詳細を表示するには、[電話システムで通話キューを作成する](create-a-phone-system-call-queue.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-p118">Redirect the call to a call queue. To see more about call queues, see [Create a Phone System call queue](create-a-phone-system-call-queue.md).</span></span>
    
  - <span data-ttu-id="b8a8b-345">セットアップした別の自動応答の呼び出しをリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-345">Redirect the call to another auto attendant that you have set up.</span></span>
    
- <span data-ttu-id="b8a8b-p119">メニュー オプションを作成して、呼び出し先の人を確認する] メニューの [メッセージを再生します。例:"販売、サービスのためには、キーを押して 2 の 1 を押します。演算子に読み上げ機能をキーを押します 0 いつでも。"</span><span class="sxs-lookup"><span data-stu-id="b8a8b-p119">Create menu options and play a menu prompt for the person calling. For example: "Press 1 for Sales, Press 2 for Services. To speak to the operator, press 0 at any time."</span></span>
    
### <a name="menu-options"></a><span data-ttu-id="b8a8b-349">メニュー オプション</span><span class="sxs-lookup"><span data-stu-id="b8a8b-349">Menu Options</span></span>

<span data-ttu-id="b8a8b-p120">電話システムの自動応答を使用すると] メニューの [画面の指示 (「売上キーを押します 1、サービスのためのキーを押して 2」) を作成して、ユーザーの選択に基づいてルーティングの着信] メニューのオプションを設定することができます。自動応答メニュー オプションを設定すると、オペレーターによる着信電話の処理に関係なく、高速で、宛先にユーザーを取得する対話型のガイダンスを提供する組織が使用できます。音声合成 (システムによって生成されるプロンプト) を使用するかが記録されているオーディオ ファイルをアップロード] メニューの [画面の指示を作成できます。音声認識を自在に移動できる、音声コマンドを使用してがユーザーの電話も使えます電話のキーパッドのメニューを移動します。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-p120">Phone System auto attendants allow you to create menu prompts ("Press 1 for Sales, Press 2 for Services") and set up menu options to route calls based on what the user selects. Setting up menu options for an auto attendant enables an organization to provide interactive guidance to get the person to their destination faster, without relying on a human operator to handle the incoming calls. Menu prompts can be created by using text-to-speech (system-generated prompts) or by uploading an audio file that has been recorded. Speech recognition uses voice commands for hands-free navigation, but people calling in can also use the phone keypad to navigate menus.</span></span>
  
<span data-ttu-id="b8a8b-p121">Skype を使用して、Business 管理センターの自動応答キー 0 ~ 9 **] メニューの [オプション**] を割り当てることができます。別の勤務時間と、時間後に、メニュー オプションのセットを作成できると有効にするまたはダイヤル**] メニューの [オプション**] で名前を無効にすることができます。着信を転送する、キーをマップすることができます。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-p121">Keys 0 through 9 can be assigned to **Menu Options** in an auto attendant using the Skype for Business admin center. Different sets of menu options can be created for business hours and after hours, and you can enable or disable Dial by Name in the **Menu Options**. Keys can be mapped to transfer the calls to:</span></span>
  
- <span data-ttu-id="b8a8b-p122">既定では、0 をキーにマップされている演算子です。ただし、その他のキーに再割り当てしたりできるメニューから削除します。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-p122">An operator, which is mapped to key 0 by default. However, it can be re-assigned to any other key, or removed from the menu.</span></span>
    
- <span data-ttu-id="b8a8b-359">通話キューです。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-359">A call queue.</span></span>
    
- <span data-ttu-id="b8a8b-p123">他の自動応答します。複数レベルのメニューは**メニュー オプション**の 1 つの自動応答] をポイントして独自のセット] メニューの [オプション] と呼ばれるを「入れ子になった」の自動応答の他の自動応答を設定できます。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-p123">Another auto attendant. Multi-level menus can be set up by pointing a **Menu Option** in one auto attendant to another auto attendant with its own set of Menu Options, which is called a "nested" auto attendant.</span></span>
    
- <span data-ttu-id="b8a8b-p124">Skype for Business Online のユーザー ライセンスを**電話システム**を持つエンタープライズ ボイスを有効にしたかに割り当てたプランの呼び出し。相手呼び出しをボイス メールを送信できないようにする設定ことができます。これを行うには、**社内のユーザー**を選択しが直接ボイス メールに自動的に転送するこのユーザーの呼び出しを設定します。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-p124">A Skype for Business Online user who has a **Phone System** license that is Enterprise Voice-enabled or has Calling Plans assigned to them. You can set it up so the person calling in can be sent to voicemail. To do this, select a **Person in your company** and set this person's calls to be automatically forwarded directly to voicemail.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b8a8b-365">ユーザーが内部設置型にホストされている**メニュー オプション**で Lync Server 2010 の使用は使用できません。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-365">Users hosted on-premises using Lync Server 2010 can't be used in **Menu Options**.</span></span> 
  
<span data-ttu-id="b8a8b-p125">すべてのメニュー オプションの名前は音声認識を有効になっている場合は、音声認識のキーワードになります。たとえば、発信者と「1」キー 1, にマッピングされているメニュー オプションを選択またはが単に"Sales"という同じメニュー オプションを選択するには、「売上」を求められてことができます。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-p125">The name of every menu option becomes a speech-recognition keyword if speech recognition has been enabled. For example, callers can say "One" to select the menu option mapped to key 1, or they can simply say "Sales" to select the same menu option named "Sales."</span></span>
  
<span data-ttu-id="b8a8b-368">自動応答し、メニュー オプションを設定するには、[電話システムでの自動応答のセットアップ](set-up-a-phone-system-auto-attendant.md)を移動します。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-368">To set up an auto attendant and the menu options, go [Set up a Phone System auto attendant](set-up-a-phone-system-auto-attendant.md).</span></span>
  
### <a name="getting-service-numbers-for-an-auto-attendant"></a><span data-ttu-id="b8a8b-369">自動応答サービス番号を取得</span><span class="sxs-lookup"><span data-stu-id="b8a8b-369">Getting service numbers for an auto attendant</span></span>

<span data-ttu-id="b8a8b-p126">作成して、自動応答を設定する、前にしたり、既存の有料またはフリー ダイヤルのサービスに転送する必要があります。 数値。**Skype for Business 管理センター**で表示されますが、有料またはフリー ダイヤルのサービスの電話番号を取得する > **音声** > **電話番号**、およびとして登録されている**サービス - 無料**数値型**の一覧に表示されます。**.サービス番号を移動するには、 [Skype for Business とチームの Microsoft の取得サービスの電話番号](getting-service-phone-numbers.md)を参照してください。 または、転送と既存のサービスの番号にする場合は、 [Office 365 への電話番号に転送](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-p126">Before you can create and set up your auto attendants, you will need to get or transfer your existing toll or toll-free service numbers. Once you get the toll or toll-free service phone numbers, they will show up in the **Skype for Business admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**. To get your service numbers, see [Getting service phone numbers for Skype for Business and Microsoft Teams](getting-service-phone-numbers.md) or, if you want to transfer and existing service number, see [Transfer phone numbers to Office 365](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="b8a8b-p127">米国外の場合は、Skype for Business 管理センターを使ってサービス番号を取得することはできません。その方法を表示する代わりに[、組織の管理の電話番号](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)を移動します。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-p127">If you are outside the United States, you can't use the Skype for Business admin center to get service numbers. Go [Manage phone numbers for your organization](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it.</span></span>
  
## <a name="changing-the-users-caller-id-to-be-a-call-queues-phone-number"></a><span data-ttu-id="b8a8b-375">ユーザーの発信者番号に通話キューの電話番号を変更します。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-375">Changing the user's Caller ID to be a call queue's phone number</span></span>

<span data-ttu-id="b8a8b-376">ユーザーの代わりに**新しい CallingLineIdentity**コマンドレットを使用してポリシーを作成して、発信者番号の呼び出しキューに発信を変更することによって保護できます。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-376">You can protect a user's identity by changing their caller ID for the outbound calls to a call queue instead by creating a policy using the **New-CallingLineIdentity** cmdlet.</span></span>
  
<span data-ttu-id="b8a8b-377">これを行うには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-377">To do this, run:</span></span>
  
```
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

<span data-ttu-id="b8a8b-p128">**許可を付与する CallingLineIdentity**コマンドレットを使用してユーザーにポリシーを適用します。これを行うには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-p128">Then apply the policy to the user using the **Grant-CallingLineIdentity** cmdlet. To do this, run:</span></span>
  
```
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

<span data-ttu-id="b8a8b-380">[発信者の使い方組織内で](../what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization.md)、組織内の発信者 ID の設定を変更する方法の詳細を取得できます。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-380">You can get more information on how to make changes to caller ID settings in your organization [How can caller ID be used in your organization](../what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="b8a8b-381">関連トピック</span><span class="sxs-lookup"><span data-stu-id="b8a8b-381">Related topics</span></span>
[<span data-ttu-id="b8a8b-382">ここではされた電話システムで Office 365 での表示</span><span class="sxs-lookup"><span data-stu-id="b8a8b-382">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="b8a8b-383">Skype for Business とチームの Microsoft サービスの電話番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="b8a8b-383">Getting service phone numbers for Skype for Business and Microsoft Teams</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="b8a8b-384">電話会議とプランの呼び出しの国と地域の空き時間情報</span><span class="sxs-lookup"><span data-stu-id="b8a8b-384">Country and region availability for Audio Conferencing and Calling Plans</span></span>](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)