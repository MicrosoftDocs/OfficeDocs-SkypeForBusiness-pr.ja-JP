---
title: 応答メッセージとメールに使用する既定の言語を変更する
author: dstrome
ms.author: dstrome
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.assetid: 820c3892-1b7e-47d3-ae8d-6e27e7cbcf38
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-mar2020
description: 組織の既定のボイスメール応答メッセージで別の言語を使用するように Skype for Business をセットアップする方法について説明します。
ms.openlocfilehash: 988f09141913c72b9334b28d2c218b15bdbf3376
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691393"
---
# <a name="change-the-default-language-for-greetings-and-emails"></a><span data-ttu-id="3795e-103">応答メッセージとメールに使用する既定の言語を変更する</span><span class="sxs-lookup"><span data-stu-id="3795e-103">Change the default language for greetings and emails</span></span>

<span data-ttu-id="3795e-104">[グローバル管理者](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)である場合は、Skype for business で、既定のボイスメール応答メッセージを別の言語で再生するように設定できます。</span><span class="sxs-lookup"><span data-stu-id="3795e-104">If you are a [global administrator](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d), you can set up Skype for Business to play its default voicemail greeting in another language.</span></span> <span data-ttu-id="3795e-105">既定のシステム応答メッセージは、たとえば「内田です。ただいま、席を外しております。</span><span class="sxs-lookup"><span data-stu-id="3795e-105">The default system greeting is something like, "Please leave a message for John Smith.</span></span> <span data-ttu-id="3795e-106">発信音の後に、メッセージを録音してください。</span><span class="sxs-lookup"><span data-stu-id="3795e-106">After the tone, please record your message.</span></span> <span data-ttu-id="3795e-107">終わりましたら、電話を切るか、シャープを押して別のオプションを選択してください。」のようになっています。</span><span class="sxs-lookup"><span data-stu-id="3795e-107">When you finish recording, hang up, or press the pound key for more options."</span></span> 
  
 <span data-ttu-id="3795e-108">**最初に、次の重要な情報をお読みください。**</span><span class="sxs-lookup"><span data-stu-id="3795e-108">**First, read this important info:**</span></span>
  
- <span data-ttu-id="3795e-109">**利用できる言語は組織の場所によって決まります** 。</span><span class="sxs-lookup"><span data-stu-id="3795e-109">**The languages that are available to you are determined by the location of your organization**.</span></span> <span data-ttu-id="3795e-110">たとえば、組織が米国内にある場合は、既定の言語を英語またはスペイン語に設定できます。</span><span class="sxs-lookup"><span data-stu-id="3795e-110">For example, if your organization is located in the United States, you can set the default language to English or Spanish.</span></span> <span data-ttu-id="3795e-111">組織がカナダにある場合は、英語とフランス語から選べます。</span><span class="sxs-lookup"><span data-stu-id="3795e-111">If your organization is located in Canada, you can choose between English and French.</span></span> <span data-ttu-id="3795e-112">サポートされる言語のリストについては、「[Skype for Business からのボイスメールの応答メッセージに使用する言語](languages-for-voicemail-greetings-and-messages.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3795e-112">For a list of supported languages, see [Languages for voicemail greetings and messages from Skype for Business](languages-for-voicemail-greetings-and-messages.md).</span></span>
    
- <span data-ttu-id="3795e-113">**個々のユーザのボイスメールの応答メッセージとボイスメールメッセージの言語を変更します。**</span><span class="sxs-lookup"><span data-stu-id="3795e-113">**Changing languages for individual user's voicemail greeting and voicemail messages.**</span></span> <span data-ttu-id="3795e-114">ユーザーの優先 lanaguage を変更することができます。これにより、Outlook メールボックスに送信されるボイスメールの応答メッセージとボイスメールメッセージの言語が変更されます。</span><span class="sxs-lookup"><span data-stu-id="3795e-114">You can change the preferred lanaguage for users, which will change the language of the their voicemail greeting and voicemail messages sent to their Outlook mailbox.</span></span> <span data-ttu-id="3795e-115">手順については、「Microsoft 365 または Office 365 の言語と地域の設定を行う方法 (英語)」を参照してください https://docs.microsoft.com/office365/troubleshoot/access-management/set-language-and-region) 。</span><span class="sxs-lookup"><span data-stu-id="3795e-115">For instruction please see [How to set language and region settings for Microsoft 365 or Office 365] (https://docs.microsoft.com/office365/troubleshoot/access-management/set-language-and-region).</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="3795e-116">[Microsoft 365 For Business の [表示言語とタイムゾーンの変更](https://support.office.com/en-us/article/change-your-display-language-and-time-zone-in-microsoft-365-for-business-6f238bff-5252-441e-b32b-655d5d85d15b?ui=en-US&rs=en-US&ad=US)] にある手順に従って、ユーザーが自分のあいさつ文の言語を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="3795e-116">Users can change their own greeting language through their settings after they sign in by following instructions found in [Change your display language and time zone in Microsoft 365 for Business](https://support.office.com/en-us/article/change-your-display-language-and-time-zone-in-microsoft-365-for-business-6f238bff-5252-441e-b32b-655d5d85d15b?ui=en-US&rs=en-US&ad=US)</span></span>
  
- <span data-ttu-id="3795e-117">**発信ボイス メール メッセージを録音する場合は、**</span><span class="sxs-lookup"><span data-stu-id="3795e-117">**Do you want to record your outgoing voicemail message?**</span></span> <span data-ttu-id="3795e-118">「[Skype for Business ボイス メールの確認とオプション](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3795e-118">See [Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8).</span></span> <span data-ttu-id="3795e-119">Microsoft Teams の場合-ユーザーは、[ [Teams デスクトップクライアント](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)] の設定からボイスメールの設定を変更できます</span><span class="sxs-lookup"><span data-stu-id="3795e-119">For Microsoft Teams - Users can change their voicemail settings from the [Teams desktop client settings](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)</span></span>

- <span data-ttu-id="3795e-120">**ボイスメールプロンプトの言語を変更しますか?**</span><span class="sxs-lookup"><span data-stu-id="3795e-120">**Do you want to change the voicemail prompt language?**</span></span> <span data-ttu-id="3795e-121">Skype for Business につい [https://mysettings.lync.com/voicemail](https://mysettings.lync.com/voicemail) ては、[**プロンプト言語**] で新しい言語を選択します。</span><span class="sxs-lookup"><span data-stu-id="3795e-121">For Skype for Business -  [https://mysettings.lync.com/voicemail](https://mysettings.lync.com/voicemail) and choose a new language under **Prompt Language**.</span></span> <span data-ttu-id="3795e-122">Microsoft Teams の場合-ユーザーは、 [Teams のデスクトップクライアント設定](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)からボイスメールの応答メッセージを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="3795e-122">For Microsoft Teams - Users can change their voicemail greeting from the [Teams desktop client settings](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)</span></span>
    
## <a name="change-the-system-language-for-everyone-in-your-organization"></a><span data-ttu-id="3795e-123">組織のユーザー全員に対してシステムの言語を変更する</span><span class="sxs-lookup"><span data-stu-id="3795e-123">Change the system language for everyone in your organization</span></span>

1. <span data-ttu-id="3795e-124">[グローバル管理者](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)アカウントでサインイン [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) します。</span><span class="sxs-lookup"><span data-stu-id="3795e-124">Sign in with your [global administrator](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span> 
    
2. <span data-ttu-id="3795e-125">Microsoft 365 管理センターで、[**設定**の構成] の [  >  **Settings**  >  **組織プロファイル**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="3795e-125">In the Microsoft 365 admin center, choose **Settings** > **Settings** > **Organization profile**.</span></span> 
    
     ![[設定]、[組織プロファイル] の選択を示すスクリーンショット。](media/9d9de520-bb84-409f-9417-96bd8ec86c48.png)
  
3. <span data-ttu-id="3795e-127">[ **編集**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="3795e-127">Choose **Edit**.</span></span>
    
    ![[編集] オプションが表示されたスクリーンショット。](media/e4a0b09d-2b68-4bc8-a0d3-230939843ee2.png)
  
4. <span data-ttu-id="3795e-129">[ **優先言語**] リストから、組織内のすべてのユーザーのための言語を選択します。</span><span class="sxs-lookup"><span data-stu-id="3795e-129">Select a language from the **Preferred language** list for everyone in your organization.</span></span>
    
5. <span data-ttu-id="3795e-130">[ **保存**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="3795e-130">Choose **Save**.</span></span>
    
## <a name="related-articles-for-the-admin"></a><span data-ttu-id="3795e-131">管理者向けの関連記事</span><span class="sxs-lookup"><span data-stu-id="3795e-131">Related articles for the admin</span></span>

- [<span data-ttu-id="3795e-132">電話システムと通話プラン</span><span class="sxs-lookup"><span data-stu-id="3795e-132">Phone System and Calling Plans</span></span>](calling-plan-landing-page.md)
    
- [<span data-ttu-id="3795e-133">通話プランの設定</span><span class="sxs-lookup"><span data-stu-id="3795e-133">Set up Calling Plans</span></span>](set-up-calling-plans.md)
    
- [<span data-ttu-id="3795e-134">Skype for Business Server でオンプレミスの PSTN 接続を使用して Microsoft 365 または Office 365 で電話システムを計画する</span><span class="sxs-lookup"><span data-stu-id="3795e-134">Plan Phone System in Microsoft 365 or Office 365 with on-premises PSTN connectivity in Skype for Business Server</span></span>](https://go.microsoft.com/fwlink/?LinkId=717947)
    
## <a name="related-topics"></a><span data-ttu-id="3795e-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="3795e-135">Related topics</span></span>

- [<span data-ttu-id="3795e-136">Microsoft 365 または一般法人向け Office 365 の表示言語とタイムゾーンを変更する</span><span class="sxs-lookup"><span data-stu-id="3795e-136">Change your display language and time zone in Microsoft 365 or Office 365 for Business</span></span>](https://support.office.com/article/Change-your-display-language-and-time-zone-in-Office-365-for-Business-6f238bff-5252-441e-b32b-655d5d85d15b)
    
- <span data-ttu-id="3795e-137">[Office 2010 以降で別の言語を使用できるようにする](https://support.office.com/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d)</span><span class="sxs-lookup"><span data-stu-id="3795e-137">[Add a language or set language preferences in Office 2010 and later](https://support.office.com/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d))</span></span>
    
- [<span data-ttu-id="3795e-138">キーボード レイアウトの言語を有効化または変更する</span><span class="sxs-lookup"><span data-stu-id="3795e-138">Enable or change a keyboard layout language</span></span>](https://support.office.com/article/Enable-or-change-a-keyboard-layout-language-1c2242c0-fe15-4bc3-99bc-535de6f4f258)
    
  
 
