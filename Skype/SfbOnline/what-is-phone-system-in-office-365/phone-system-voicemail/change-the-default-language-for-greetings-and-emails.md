---
title: "あいさつ文とメールの既定の言語を変更します。"
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
description: "組織の既定のボイス メールに別の言語を使用する Busineses の Skype をセットアップする方法について説明あいさちます。 "
ms.openlocfilehash: 1c311436ed9010ea20598aac6a55b4806fe18abb
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="change-the-default-language-for-greetings-and-emails"></a><span data-ttu-id="09211-103">あいさつ文とメールの既定の言語を変更します。</span><span class="sxs-lookup"><span data-stu-id="09211-103">Change the default language for greetings and emails</span></span>

<span data-ttu-id="09211-p101">[Office 365 グローバル管理者](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)の場合は、Skype for Business にあいさつ文の別の言語での既定のボイスメールの再生を設定できます。既定のシステムのあいさつ文は、次のように"John Smith は、メッセージを残すしてください。トーンの後に、メッセージを記録してください。レコーディングが終了したら、ハングする、かキーを押してシャープの他のオプション。"</span><span class="sxs-lookup"><span data-stu-id="09211-p101">If you are an [Office 365 global administrator](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d), you can set up Skype for Business to play its default voicemail greeting in another language. The default system greeting is something like, "Please leave a message for John Smith. After the tone, please record your message. When you finish recording, hang up, or press the pound key for more options."</span></span> 
  
 <span data-ttu-id="09211-108">**まず、この重要な情報を確認します。**</span><span class="sxs-lookup"><span data-stu-id="09211-108">**First, read this important info:**</span></span>
  
- <span data-ttu-id="09211-p102">**利用できる言語は、組織の場所によって決まります**。たとえば、米国では、組織が存在する場合は、英語やスペイン語に、既定の言語を設定できます。カナダでは、組織が存在する場合は、英語、フランス語の間で選択できます。サポートされる言語のリストは、[ボイス メールのあいさつ文と Skype for Business からのメッセージの言語](languages-for-voicemail-greetings-and-messages.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09211-p102">**The languages that are available to you are determined by the location of your organization**. For example, if your organization is located in the United States, you can set the default language to English or Spanish. If your organization is located in Canada, you can choose between English and French. For a list of supported languages, see [Languages for voicemail greetings and messages from Skype for Business](languages-for-voicemail-greetings-and-messages.md).</span></span>
    
- <span data-ttu-id="09211-p103">**の組織内の 1 つだけのユーザーのシステムの言語を変更する方法はありません**。組織のすべてのユーザーに対してのみあいさつ文の言語を変更できます。</span><span class="sxs-lookup"><span data-stu-id="09211-p103">**There's no way to change the system language for only one person in your organization.** You can only change the greeting language for everyone on your organization.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="09211-115">ユーザーが自分のサインイン後にあいさつ文の記述する言語の設定の変更できます。</span><span class="sxs-lookup"><span data-stu-id="09211-115">Users can change their own greeting language through their settings after they sign in.</span></span> 
  
- <span data-ttu-id="09211-p104">**、ボイス メールの送信メッセージを記録することですか?**[Skype for Business ボイス メールとオプションにチェック](https://support.office.com/en-us/article/2deea7f8-831f-4e85-a0d4-b34da55945a8)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09211-p104">**Do you want to record your outgoing voicemail message?** See [Check Skype for Business voicemail and options](https://support.office.com/en-us/article/2deea7f8-831f-4e85-a0d4-b34da55945a8).</span></span>
    
## <a name="change-the-system-language-for-everyone-in-your-organization"></a><span data-ttu-id="09211-118">組織内のすべてのユーザーに対してシステムの言語を変更します。</span><span class="sxs-lookup"><span data-stu-id="09211-118">Change the system language for everyone in your organization</span></span>

1. <span data-ttu-id="09211-119">[Https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home)で自分の[Office 365 グローバル管理者](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)アカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="09211-119">Sign in with your [Office 365 global administrator](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) account at[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span> 
    
2. <span data-ttu-id="09211-120">管理センターで、[**設定**] を選びます > **組織プロファイル**します。</span><span class="sxs-lookup"><span data-stu-id="09211-120">In the admin center, choose **Settings** > **Organization profile**.</span></span> 
    
     ![設定を選択し、[組織のプロファイルを選択します。](../../images/9d9de520-bb84-409f-9417-96bd8ec86c48.png)
  
3. <span data-ttu-id="09211-122">[**編集**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="09211-122">Choose **Edit**.</span></span>
    
    ![[編集] を選びます。](../../images/e4a0b09d-2b68-4bc8-a0d3-230939843ee2.png)
  
4. <span data-ttu-id="09211-124">組織内のすべてのユーザーに対して、**優先言語**の一覧から言語を選択します。</span><span class="sxs-lookup"><span data-stu-id="09211-124">Select a language from the **Preferred language** list for everyone in your organization.</span></span>
    
5. <span data-ttu-id="09211-125">[**保存**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="09211-125">Choose **Save**.</span></span>
    
## <a name="related-articles-for-the-admin"></a><span data-ttu-id="09211-126">管理者は、関連記事</span><span class="sxs-lookup"><span data-stu-id="09211-126">Related articles for the admin</span></span>

- [<span data-ttu-id="09211-127">Office 365 のプランの呼び出しとは</span><span class="sxs-lookup"><span data-stu-id="09211-127">What are Calling Plans in Office 365?</span></span>](../../what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365.md)
    
- [<span data-ttu-id="09211-128">プランの呼び出しを設定します。</span><span class="sxs-lookup"><span data-stu-id="09211-128">Set up Calling Plans</span></span>](../../what-are-calling-plans-in-office-365/set-up-calling-plans.md)
    
- [<span data-ttu-id="09211-129">Skype for Business Server 2015 または Lync Server 2013 での PSTN への接続をオンプレミスで Office 365 で電話システムで計画</span><span class="sxs-lookup"><span data-stu-id="09211-129">Plan Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server 2015 or Lync Server 2013</span></span>](https://go.microsoft.com/fwlink/?LinkId=717947)
    
## <a name="related-topics"></a><span data-ttu-id="09211-130">関連トピック</span><span class="sxs-lookup"><span data-stu-id="09211-130">Related topics</span></span>

- [<span data-ttu-id="09211-131">一般法人向け Office 365 でのタイム ゾーン、表示言語を変更します。</span><span class="sxs-lookup"><span data-stu-id="09211-131">Change your display language and time zone in Office 365 for Business</span></span>](https://support.office.com/en-us/article/Change-your-display-language-and-time-zone-in-Office-365-for-Business-6f238bff-5252-441e-b32b-655d5d85d15b)
    
- <span data-ttu-id="09211-132">[言語を追加するか Office 2010 以降での言語を設定](https://support.office.com/en-us/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d))</span><span class="sxs-lookup"><span data-stu-id="09211-132">[Add a language or set language preferences in Office 2010 and later](https://support.office.com/en-us/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d))</span></span>
    
- [<span data-ttu-id="09211-133">有効にするか、キーボード レイアウトの言語を変更します。</span><span class="sxs-lookup"><span data-stu-id="09211-133">Enable or change a keyboard layout language</span></span>](https://support.office.com/en-us/article/Enable-or-change-a-keyboard-layout-language-1c2242c0-fe15-4bc3-99bc-535de6f4f258)
    

