---
title: "応答メッセージとメールに使用する既定の言語を変更する"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 820c3892-1b7e-47d3-ae8d-6e27e7cbcf38
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
description: "Skype for Busineses をセットアップして、組織のボイスメールの既定応答メッセージで別の言語を使用する方法を説明します。 "
ms.openlocfilehash: 1c311436ed9010ea20598aac6a55b4806fe18abb
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2018
---
# <a name="change-the-default-language-for-greetings-and-emails"></a><span data-ttu-id="7830d-103">応答メッセージとメールに使用する既定の言語を変更する</span><span class="sxs-lookup"><span data-stu-id="7830d-103">Change the default language for greetings and emails</span></span>

<span data-ttu-id="7830d-104">[[Office 365 のグローバル管理者](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)] の場合は、Skype for Business を設定して、別の言語で再生される既定のボイスメール応答メッセージを入れることができます。</span><span class="sxs-lookup"><span data-stu-id="7830d-104">If you are an [Office 365 global administrator](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d), you can set up Skype for Business to play its default voicemail greeting in another language.</span></span> <span data-ttu-id="7830d-105">既定のシステム応答メッセージは、たとえば「内田です。ただいま、席を外しております。</span><span class="sxs-lookup"><span data-stu-id="7830d-105">The default system greeting is something like, "Please leave a message for John Smith.</span></span> <span data-ttu-id="7830d-106">発信音の後に、メッセージを録音してください。</span><span class="sxs-lookup"><span data-stu-id="7830d-106">After the tone, please record your message.</span></span> <span data-ttu-id="7830d-107">終わりましたら、電話を切るか、シャープを押して別のオプションを選択してください。」のようになっています。</span><span class="sxs-lookup"><span data-stu-id="7830d-107">When you finish recording, hang up, or press the pound key for more options."</span></span> 
  
 <span data-ttu-id="7830d-108">**最初に、次の重要な情報をお読みください。**</span><span class="sxs-lookup"><span data-stu-id="7830d-108">**First, read this important info:**</span></span>
  
- <span data-ttu-id="7830d-109">**利用できる言語は組織の場所によって決まります** 。</span><span class="sxs-lookup"><span data-stu-id="7830d-109">**The languages that are available to you are determined by the location of your organization**.</span></span> <span data-ttu-id="7830d-110">たとえば、組織が米国内にある場合は、既定の言語を英語またはスペイン語に設定できます。</span><span class="sxs-lookup"><span data-stu-id="7830d-110">For example, if your organization is located in the United States, you can set the default language to English or Spanish.</span></span> <span data-ttu-id="7830d-111">組織がカナダにある場合は、英語とフランス語から選べます。</span><span class="sxs-lookup"><span data-stu-id="7830d-111">If your organization is located in Canada, you can choose between English and French.</span></span> <span data-ttu-id="7830d-112">サポートされる言語のリストについては、「[Skype for Business からのボイスメールの応答メッセージに使用する言語](languages-for-voicemail-greetings-and-messages.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7830d-112">For a list of supported languages, see [Languages for voicemail greetings and messages from Skype for Business](languages-for-voicemail-greetings-and-messages.md).</span></span>
    
- <span data-ttu-id="7830d-p103">**組織内の 1 人のユーザーのみに対してシステムの言語を変更する方法はありません。** 組織のユーザー全員に対してあいさつ文の言語を変更することのみが可能です。</span><span class="sxs-lookup"><span data-stu-id="7830d-p103">**There's no way to change the system language for only one person in your organization.** You can only change the greeting language for everyone on your organization.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7830d-115">ユーザーはサイン インした後に設定を操作して自身のあいさつ文の言語を変更できます。</span><span class="sxs-lookup"><span data-stu-id="7830d-115">Users can change their own greeting language through their settings after they sign in.</span></span> 
  
- <span data-ttu-id="7830d-116">**発信ボイス メール メッセージを録音する場合は、**</span><span class="sxs-lookup"><span data-stu-id="7830d-116">**Do you want to record your outgoing voicemail message?**</span></span> <span data-ttu-id="7830d-117">「[Skype for Business ボイス メールの確認とオプション](https://support.office.com/en-us/article/2deea7f8-831f-4e85-a0d4-b34da55945a8)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7830d-117">See [Check Skype for Business voicemail and options](https://support.office.com/en-us/article/2deea7f8-831f-4e85-a0d4-b34da55945a8).</span></span>
    
## <a name="change-the-system-language-for-everyone-in-your-organization"></a><span data-ttu-id="7830d-118">組織のユーザー全員に対してシステムの言語を変更する</span><span class="sxs-lookup"><span data-stu-id="7830d-118">Change the system language for everyone in your organization</span></span>

1. <span data-ttu-id="7830d-119">[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) で [Office 365 のグローバル管理者](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)アカウントを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="7830d-119">Sign in with your [Office 365 global administrator](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) account at[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span> 
    
2. <span data-ttu-id="7830d-120">管理センターで、[**設定**] > [**組織プロファイル**] の順に選びます。</span><span class="sxs-lookup"><span data-stu-id="7830d-120">In the admin center, choose **Settings** > **Organization profile**.</span></span> 
    
     ![Choose Settings and then choose Organization profile.](../../images/9d9de520-bb84-409f-9417-96bd8ec86c48.png)
  
3. <span data-ttu-id="7830d-122">[ **編集**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="7830d-122">Choose **Edit**.</span></span>
    
    ![Choose Edit.](../../images/e4a0b09d-2b68-4bc8-a0d3-230939843ee2.png)
  
4. <span data-ttu-id="7830d-124">[ **優先言語**] リストから、組織内のすべてのユーザーのための言語を選択します。</span><span class="sxs-lookup"><span data-stu-id="7830d-124">Select a language from the **Preferred language** list for everyone in your organization.</span></span>
    
5. <span data-ttu-id="7830d-125">[ **保存**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="7830d-125">Choose **Save**.</span></span>
    
## <a name="related-articles-for-the-admin"></a><span data-ttu-id="7830d-126">管理者向けの関連記事</span><span class="sxs-lookup"><span data-stu-id="7830d-126">Related articles for the admin</span></span>

- [<span data-ttu-id="7830d-127">Office 365 の通話プランについて</span><span class="sxs-lookup"><span data-stu-id="7830d-127">What are Calling Plans in Office 365?</span></span>](../../what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365.md)
    
- [<span data-ttu-id="7830d-128">通話プランのセットアップ</span><span class="sxs-lookup"><span data-stu-id="7830d-128">Set up Calling Plans</span></span>](../../what-are-calling-plans-in-office-365/set-up-calling-plans.md)
    
- [<span data-ttu-id="7830d-129">Skype for Business Server 2015 または Lync Server 2013 でオンプレミスの PSTN 接続を備えた Office 365 の電話システムを計画する</span><span class="sxs-lookup"><span data-stu-id="7830d-129">Plan Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server 2015 or Lync Server 2013</span></span>](https://go.microsoft.com/fwlink/?LinkId=717947)
    
## <a name="related-topics"></a><span data-ttu-id="7830d-130">関連トピック</span><span class="sxs-lookup"><span data-stu-id="7830d-130">Related topics</span></span>

- [<span data-ttu-id="7830d-131">一般法人向け Office 365 で表示言語とタイム ゾーンを変更する</span><span class="sxs-lookup"><span data-stu-id="7830d-131">Change your display language and time zone in Office 365 for Business</span></span>](https://support.office.com/en-us/article/Change-your-display-language-and-time-zone-in-Office-365-for-Business-6f238bff-5252-441e-b32b-655d5d85d15b)
    
- <span data-ttu-id="7830d-132">[Office 2010 以降で別の言語を使用できるようにする](https://support.office.com/en-us/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d)</span><span class="sxs-lookup"><span data-stu-id="7830d-132">[Add a language or set language preferences in Office 2010 and later](https://support.office.com/en-us/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d))</span></span>
    
- [<span data-ttu-id="7830d-133">キーボード レイアウトの言語を有効化または変更する</span><span class="sxs-lookup"><span data-stu-id="7830d-133">Enable or change a keyboard layout language</span></span>](https://support.office.com/en-us/article/Enable-or-change-a-keyboard-layout-language-1c2242c0-fe15-4bc3-99bc-535de6f4f258)
    

