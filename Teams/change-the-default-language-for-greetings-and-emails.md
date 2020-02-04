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
- NOCSH
ms.custom:
- Phone System
description: '組織の既定のボイスメール応答メッセージで別の言語を使用するように Skype for Business をセットアップする方法について説明します。 '
ms.openlocfilehash: 39c790a4a2e1085b20a3aed82d7f971e4fad6694
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41695522"
---
# <a name="change-the-default-language-for-greetings-and-emails"></a><span data-ttu-id="9aa23-103">応答メッセージとメールに使用する既定の言語を変更する</span><span class="sxs-lookup"><span data-stu-id="9aa23-103">Change the default language for greetings and emails</span></span>

<span data-ttu-id="9aa23-104">[[Office 365 のグローバル管理者](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)] の場合は、Skype for Business を設定して、別の言語で再生される既定のボイスメール応答メッセージを入れることができます。</span><span class="sxs-lookup"><span data-stu-id="9aa23-104">If you are an [Office 365 global administrator](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d), you can set up Skype for Business to play its default voicemail greeting in another language.</span></span> <span data-ttu-id="9aa23-105">既定のシステム応答メッセージは、たとえば「内田です。ただいま、席を外しております。</span><span class="sxs-lookup"><span data-stu-id="9aa23-105">The default system greeting is something like, "Please leave a message for John Smith.</span></span> <span data-ttu-id="9aa23-106">発信音の後に、メッセージを録音してください。</span><span class="sxs-lookup"><span data-stu-id="9aa23-106">After the tone, please record your message.</span></span> <span data-ttu-id="9aa23-107">終わりましたら、電話を切るか、シャープを押して別のオプションを選択してください。」のようになっています。</span><span class="sxs-lookup"><span data-stu-id="9aa23-107">When you finish recording, hang up, or press the pound key for more options."</span></span> 
  
 <span data-ttu-id="9aa23-108">**最初に、次の重要な情報をお読みください。**</span><span class="sxs-lookup"><span data-stu-id="9aa23-108">**First, read this important info:**</span></span>
  
- <span data-ttu-id="9aa23-109">**利用できる言語は組織の場所によって決まります** 。</span><span class="sxs-lookup"><span data-stu-id="9aa23-109">**The languages that are available to you are determined by the location of your organization**.</span></span> <span data-ttu-id="9aa23-110">たとえば、組織が米国内にある場合は、既定の言語を英語またはスペイン語に設定できます。</span><span class="sxs-lookup"><span data-stu-id="9aa23-110">For example, if your organization is located in the United States, you can set the default language to English or Spanish.</span></span> <span data-ttu-id="9aa23-111">組織がカナダにある場合は、英語とフランス語から選べます。</span><span class="sxs-lookup"><span data-stu-id="9aa23-111">If your organization is located in Canada, you can choose between English and French.</span></span> <span data-ttu-id="9aa23-112">サポートされる言語のリストについては、「[Skype for Business からのボイスメールの応答メッセージに使用する言語](languages-for-voicemail-greetings-and-messages.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9aa23-112">For a list of supported languages, see [Languages for voicemail greetings and messages from Skype for Business](languages-for-voicemail-greetings-and-messages.md).</span></span>
    
- <span data-ttu-id="9aa23-p103">**組織内の 1 人のユーザーのみに対してシステムの言語を変更する方法はありません。** 組織のユーザー全員に対してあいさつ文の言語を変更することのみが可能です。</span><span class="sxs-lookup"><span data-stu-id="9aa23-p103">**There's no way to change the system language for only one person in your organization.** You can only change the greeting language for everyone on your organization.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9aa23-115">ユーザーはサイン インした後に設定を操作して自身のあいさつ文の言語を変更できます。</span><span class="sxs-lookup"><span data-stu-id="9aa23-115">Users can change their own greeting language through their settings after they sign in.</span></span> 
  
- <span data-ttu-id="9aa23-116">**発信ボイス メール メッセージを録音する場合は、**</span><span class="sxs-lookup"><span data-stu-id="9aa23-116">**Do you want to record your outgoing voicemail message?**</span></span> <span data-ttu-id="9aa23-117">「[Skype for Business ボイス メールの確認とオプション](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9aa23-117">See [Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8).</span></span> <span data-ttu-id="9aa23-118">Microsoft Teams の場合-ユーザーは、[ [Teams デスクトップクライアント](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)] の設定からボイスメールの設定を変更できます</span><span class="sxs-lookup"><span data-stu-id="9aa23-118">For Microsoft Teams - Users can change their voicemail settings from the [Teams desktop client settings](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)</span></span>

- <span data-ttu-id="9aa23-119">**ボイスメールプロンプトの言語を変更しますか?**</span><span class="sxs-lookup"><span data-stu-id="9aa23-119">**Do you want to change the voicemail prompt language?**</span></span> <span data-ttu-id="9aa23-120">Skype for Business につい[https://mysettings.lync.com/voicemail](https://mysettings.lync.com/voicemail)ては、[**プロンプト言語**] で新しい言語を選択します。</span><span class="sxs-lookup"><span data-stu-id="9aa23-120">For Skype for Business -  [https://mysettings.lync.com/voicemail](https://mysettings.lync.com/voicemail) and choose a new language under **Prompt Language**.</span></span> <span data-ttu-id="9aa23-121">Microsoft Teams の場合-ユーザーは、[ [Teams デスクトップクライアント](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)] の設定からボイスメールの設定を変更できます</span><span class="sxs-lookup"><span data-stu-id="9aa23-121">For Microsoft Teams - Users can change their voicemail settings from the [Teams desktop client settings](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)</span></span>
    
## <a name="change-the-system-language-for-everyone-in-your-organization"></a><span data-ttu-id="9aa23-122">組織のユーザー全員に対してシステムの言語を変更する</span><span class="sxs-lookup"><span data-stu-id="9aa23-122">Change the system language for everyone in your organization</span></span>

1. <span data-ttu-id="9aa23-123">[Office 365 グローバル管理者](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)アカウントでサインイン[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home)します。</span><span class="sxs-lookup"><span data-stu-id="9aa23-123">Sign in with your [Office 365 global administrator](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) account at[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span> 
    
2. <span data-ttu-id="9aa23-124">Microsoft 365 管理センターで、[**組織プロファイル**の**設定** > ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9aa23-124">In the Microsoft 365 admin center, choose **Settings** > **Organization profile**.</span></span> 
    
     ![[設定]、[組織プロファイル] の選択を示すスクリーンショット。](media/9d9de520-bb84-409f-9417-96bd8ec86c48.png)
  
3. <span data-ttu-id="9aa23-126">[ **編集**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="9aa23-126">Choose **Edit**.</span></span>
    
    ![[編集] オプションが表示されたスクリーンショット。](media/e4a0b09d-2b68-4bc8-a0d3-230939843ee2.png)
  
4. <span data-ttu-id="9aa23-128">[ **優先言語**] リストから、組織内のすべてのユーザーのための言語を選択します。</span><span class="sxs-lookup"><span data-stu-id="9aa23-128">Select a language from the **Preferred language** list for everyone in your organization.</span></span>
    
5. <span data-ttu-id="9aa23-129">[ **保存**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="9aa23-129">Choose **Save**.</span></span>
    
## <a name="related-articles-for-the-admin"></a><span data-ttu-id="9aa23-130">管理者向けの関連記事</span><span class="sxs-lookup"><span data-stu-id="9aa23-130">Related articles for the admin</span></span>

- [<span data-ttu-id="9aa23-131">電話システムと通話プラン</span><span class="sxs-lookup"><span data-stu-id="9aa23-131">Phone System and Calling Plans</span></span>](calling-plan-landing-page.md)
    
- [<span data-ttu-id="9aa23-132">通話プランの設定</span><span class="sxs-lookup"><span data-stu-id="9aa23-132">Set up Calling Plans</span></span>](set-up-calling-plans.md)
    
- [<span data-ttu-id="9aa23-133">Skype for Business Server でオンプレミスの PSTN 接続を使用して、Office 365 で電話システムを計画する</span><span class="sxs-lookup"><span data-stu-id="9aa23-133">Plan Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server</span></span>](https://go.microsoft.com/fwlink/?LinkId=717947)
    
## <a name="related-topics"></a><span data-ttu-id="9aa23-134">関連トピック</span><span class="sxs-lookup"><span data-stu-id="9aa23-134">Related topics</span></span>

- [<span data-ttu-id="9aa23-135">一般法人向け Office 365 で表示言語とタイム ゾーンを変更する</span><span class="sxs-lookup"><span data-stu-id="9aa23-135">Change your display language and time zone in Office 365 for Business</span></span>](https://support.office.com/article/Change-your-display-language-and-time-zone-in-Office-365-for-Business-6f238bff-5252-441e-b32b-655d5d85d15b)
    
- <span data-ttu-id="9aa23-136">[Office 2010 以降で別の言語を使用できるようにする](https://support.office.com/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d)</span><span class="sxs-lookup"><span data-stu-id="9aa23-136">[Add a language or set language preferences in Office 2010 and later](https://support.office.com/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d))</span></span>
    
- [<span data-ttu-id="9aa23-137">キーボード レイアウトの言語を有効化または変更する</span><span class="sxs-lookup"><span data-stu-id="9aa23-137">Enable or change a keyboard layout language</span></span>](https://support.office.com/article/Enable-or-change-a-keyboard-layout-language-1c2242c0-fe15-4bc3-99bc-535de6f4f258)
    
  
 
