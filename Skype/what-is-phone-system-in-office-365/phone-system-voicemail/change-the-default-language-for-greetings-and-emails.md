---
title: "あいさつ文やメールの既定の言語を変更します。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 820c3892-1b7e-47d3-ae8d-6e27e7cbcf38
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Phone System
description: 'Learn how to setup Skype for Busineses to use another language for your organization''s default voicemail greeting. '
ms.openlocfilehash: cfbdcfec46a79c6fcef2aff970a05837460f6e72
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2017
---
# <a name="change-the-default-language-for-greetings-and-emails"></a><span data-ttu-id="b74f5-103">あいさつ文やメールの既定の言語を変更します。</span><span class="sxs-lookup"><span data-stu-id="b74f5-103">Change the default language for greetings and emails</span></span>

<span data-ttu-id="b74f5-104">[Office 365 のグローバル管理者](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)の場合は、あいさつ文の別の言語での既定のボイス メールを再生するのにはビジネス用の Skype を設定できます。</span><span class="sxs-lookup"><span data-stu-id="b74f5-104">If you are an [Office 365 global administrator](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d), you can set up Skype for Business to play its default voicemail greeting in another language.</span></span> <span data-ttu-id="b74f5-105">既定のシステムの応答メッセージは、次のように"John Smith には、メッセージを残すしてください。</span><span class="sxs-lookup"><span data-stu-id="b74f5-105">The default system greeting is something like, "Please leave a message for John Smith.</span></span> <span data-ttu-id="b74f5-106">トーンの後、メッセージを記録してください。</span><span class="sxs-lookup"><span data-stu-id="b74f5-106">After the tone, please record your message.</span></span> <span data-ttu-id="b74f5-107">録音が完了したら、ハングアップ、かキーを押してシャープ オプションの詳細について。」</span><span class="sxs-lookup"><span data-stu-id="b74f5-107">When you finish recording, hang up, or press the pound key for more options."</span></span> 
  
 <span data-ttu-id="b74f5-108">**最初に、次の重要な情報をお読みください。**</span><span class="sxs-lookup"><span data-stu-id="b74f5-108">**First, read this important info:**</span></span>
  
- <span data-ttu-id="b74f5-109">**使用できる言語は、組織の位置によって決まります**。</span><span class="sxs-lookup"><span data-stu-id="b74f5-109">**The languages that are available to you are determined by the location of your organization**.</span></span> <span data-ttu-id="b74f5-110">などのアメリカ合衆国では、組織が配置されている場合は、英語またはスペイン語を既定の言語を設定できます。</span><span class="sxs-lookup"><span data-stu-id="b74f5-110">For example, if your organization is located in the United States, you can set the default language to English or Spanish.</span></span> <span data-ttu-id="b74f5-111">カナダでは、組織が存在する場合は、英語とフランス語の間で選択できます。</span><span class="sxs-lookup"><span data-stu-id="b74f5-111">If your organization is located in Canada, you can choose between English and French.</span></span> <span data-ttu-id="b74f5-112">サポートされている言語のリストは、[ボイス メール応答メッセージとビジネス用の Skype からのメッセージの言語](languages-for-voicemail-greetings-and-messages.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b74f5-112">For a list of supported languages, see [Languages for voicemail greetings and messages from Skype for Business](languages-for-voicemail-greetings-and-messages.md).</span></span>
    
- <span data-ttu-id="b74f5-p103">**組織内の 1 人のユーザーのみに対してシステムの言語を変更する方法はありません。** 組織のユーザー全員に対してあいさつ文の言語を変更することのみが可能です。</span><span class="sxs-lookup"><span data-stu-id="b74f5-p103">**There's no way to change the system language for only one person in your organization.** You can only change the greeting language for everyone on your organization.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b74f5-115">ユーザーはサイン インした後に設定を操作して自身のあいさつ文の言語を変更できます。</span><span class="sxs-lookup"><span data-stu-id="b74f5-115">Users can change their own greeting language through their settings after they sign in.</span></span> 
  
- <span data-ttu-id="b74f5-116">**ボイスメール メッセージを記録しますか。**</span><span class="sxs-lookup"><span data-stu-id="b74f5-116">**Do you want to record your outgoing voicemail message?**</span></span> <span data-ttu-id="b74f5-117">[ビジネス ボイスメールおよびオプションの Skype のチェック](https://support.office.com/en-us/article/2deea7f8-831f-4e85-a0d4-b34da55945a8)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b74f5-117">See [Check Skype for Business voicemail and options](https://support.office.com/en-us/article/2deea7f8-831f-4e85-a0d4-b34da55945a8).</span></span>
    
## <a name="change-the-system-language-for-everyone-in-your-organization"></a><span data-ttu-id="b74f5-118">組織のユーザー全員に対してシステムの言語を変更する</span><span class="sxs-lookup"><span data-stu-id="b74f5-118">Change the system language for everyone in your organization</span></span>

1. <span data-ttu-id="b74f5-119">[Https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home)で[Office 365 のグローバル管理者](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)アカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="b74f5-119">Sign in with your [Office 365 global administrator](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) account at[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span> 
    
2. <span data-ttu-id="b74f5-120">管理センターの**設定**を選択します > **組織プロファイル**です。</span><span class="sxs-lookup"><span data-stu-id="b74f5-120">In the admin center, choose **Settings** > **Organization profile**.</span></span> 
    
     ![Choose Settings and then choose Organization profile.](../../images/9d9de520-bb84-409f-9417-96bd8ec86c48.png)
  
3. <span data-ttu-id="b74f5-122">[ **編集**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="b74f5-122">Choose **Edit**.</span></span>
    
    ![Choose Edit.](../../images/e4a0b09d-2b68-4bc8-a0d3-230939843ee2.png)
  
4. <span data-ttu-id="b74f5-124">[ **優先言語**] リストから、組織内のすべてのユーザーのための言語を選択します。</span><span class="sxs-lookup"><span data-stu-id="b74f5-124">Select a language from the **Preferred language** list for everyone in your organization.</span></span>
    
5. <span data-ttu-id="b74f5-125">[ **保存**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="b74f5-125">Choose **Save**.</span></span>
    
## <a name="related-articles-for-the-admin"></a><span data-ttu-id="b74f5-126">管理者向けの関連記事</span><span class="sxs-lookup"><span data-stu-id="b74f5-126">Related articles for the admin</span></span>

- [<span data-ttu-id="b74f5-127">Office 365 の通話プランについて</span><span class="sxs-lookup"><span data-stu-id="b74f5-127">What are Calling Plans in Office 365?</span></span>](../../what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365.md)
    
- [<span data-ttu-id="b74f5-128">通話プランのセットアップ</span><span class="sxs-lookup"><span data-stu-id="b74f5-128">Set up Calling Plans</span></span>](../../what-are-calling-plans-in-office-365/set-up-calling-plans.md)
    
- [<span data-ttu-id="b74f5-129">Skype for Business Server 2015 または Lync Server 2013 でオンプレミスの PSTN 接続を備えた Office 365 の電話システムを計画する</span><span class="sxs-lookup"><span data-stu-id="b74f5-129">Plan Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server 2015 or Lync Server 2013</span></span>](https://go.microsoft.com/fwlink/?LinkId=717947)
    
## <a name="related-topics"></a><span data-ttu-id="b74f5-130">関連トピック</span><span class="sxs-lookup"><span data-stu-id="b74f5-130">Related topics</span></span>

- [<span data-ttu-id="b74f5-131">一般法人向け Office 365 で表示言語とタイム ゾーンを変更する</span><span class="sxs-lookup"><span data-stu-id="b74f5-131">Change your display language and time zone in Office 365 for Business</span></span>](https://support.office.com/en-us/article/Change-your-display-language-and-time-zone-in-Office-365-for-Business-6f238bff-5252-441e-b32b-655d5d85d15b)
    
- <span data-ttu-id="b74f5-132">[言語を追加または Office 2010 およびそれ以降の言語を設定](https://support.office.com/en-us/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d))</span><span class="sxs-lookup"><span data-stu-id="b74f5-132">[Add a language or set language preferences in Office 2010 and later](https://support.office.com/en-us/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d))</span></span>
    
- [<span data-ttu-id="b74f5-133">キーボード レイアウトの言語を有効化または変更する</span><span class="sxs-lookup"><span data-stu-id="b74f5-133">Enable or change a keyboard layout language</span></span>](https://support.office.com/en-us/article/Enable-or-change-a-keyboard-layout-language-1c2242c0-fe15-4bc3-99bc-535de6f4f258)
    

