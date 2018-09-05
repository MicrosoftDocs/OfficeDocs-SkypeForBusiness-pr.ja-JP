---
title: 携帯電話の通知をオンまたはオフにする
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 2de47013-4f09-493c-abc5-372f56ad69e3
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords:
- ms.lync.lac.OrgMobileNotification
ms.custom:
- Setup
description: ユーザーが着信、ボイス メール、インスタント メッセージの未読通知を受信するために携帯電話の通知をオンまたはオフにする方法を説明します。
ms.openlocfilehash: 98e46cae258d6ca0d90e6e1cb96c3eeb724c31ee
ms.sourcegitcommit: dbef8028cb7f8c6366e0fdb34f5f2e2a30d8c32a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "19500410"
---
# <a name="turn-on-or-off-mobile-phone-notifications"></a><span data-ttu-id="06808-103">携帯電話の通知をオンまたはオフにする</span><span class="sxs-lookup"><span data-stu-id="06808-103">Turn on or off mobile phone notifications</span></span>

<span data-ttu-id="06808-104">組織で「 **[一般法人向け Office 365 で管理者ロールを割り当てる](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)** 」場合、携帯電話やタブレットで Skype for Business を使用しているユーザーがインスタント メッセージの着信通知や未読通知を受信するか選択できます。</span><span class="sxs-lookup"><span data-stu-id="06808-104">As the **[Assign admin roles in Office 365 for business](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)** for your organization, you can choose whether your Skype for Business users receive alerts about incoming and missed instant messages when they are on their mobile phones or tablets.</span></span>
  
<span data-ttu-id="06808-105">Android と Windows Phone の Skype for Business では、通知はリアル タイムにポップ アップ表示されます。</span><span class="sxs-lookup"><span data-stu-id="06808-105">On Android and Windows Phones, Skype for Business notifications pop up in real time.</span></span> <span data-ttu-id="06808-106">Windows Phone、iPhone、iPad デバイスでは、携帯電話やタブレットで Skype for Business を頻繁に使用していない場合は、プッシュ通知でアラートを表示します。</span><span class="sxs-lookup"><span data-stu-id="06808-106">For Windows Phone, iPhone, and iPad devices, however, push notification is used to show the alerts whenever you're not actively using Skype for Business on your phone or tablet.</span></span>
  
## <a name="turn-push-notifications-off-for-all-the-windows-phone-or-apple-devices-in-your-organization"></a><span data-ttu-id="06808-107">組織内のすべての Windows Phone や Apple デバイスのプッシュ通知をオフにする</span><span class="sxs-lookup"><span data-stu-id="06808-107">Turn push notifications off for all the Windows Phone or Apple devices in your organization</span></span>
<span data-ttu-id="06808-108"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="06808-108"></span></span>

<span data-ttu-id="06808-109">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Skype for Business の管理センターを使用します**</span><span class="sxs-lookup"><span data-stu-id="06808-109">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="06808-110">Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="06808-110">Sign in to Office 365</span></span>
    
2. <span data-ttu-id="06808-111">** [Office 365 Admin センター] ** > ** [Skype for Business]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="06808-111">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="06808-112"> **[組織]** > **[全般]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="06808-112">Go to **Organization** > **General**.</span></span> 
    
4. <span data-ttu-id="06808-113">**[携帯電話の通知]** で無効にしたい通知サービスの横のボックスのチェックを外し、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="06808-113">Under **Mobile phone notifications**, clear the box next to the notification service you want to disable, and then click **Save**.</span></span>
    
<span data-ttu-id="06808-114">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="06808-114">Keep in mind:</span></span> 
  
- <span data-ttu-id="06808-115">プッシュ通知をオフにした場合でも、モバイル デバイスで Skype for Business を再起動するとすべての通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="06808-115">If you turn off push notifications, users still receive all alerts when they start up Skype for Business again on their mobile device.</span></span>
    
- <span data-ttu-id="06808-116">プッシュ通知は、デフォルトでオンになっています。</span><span class="sxs-lookup"><span data-stu-id="06808-116">Push notifications are turned on by default.</span></span> <span data-ttu-id="06808-117">個々 のユーザーは、使用しているモバイル デバイス上の Skype for Business で適切なオプションを選択することによりプッシュ通知をオフにできます。</span><span class="sxs-lookup"><span data-stu-id="06808-117">Individual users can turn them off by choosing the appropriate Skype for Business option on their mobile device.</span></span>
    
- <span data-ttu-id="06808-118">管理者がプッシュ通知を無効にした場合、ユーザーはオンに戻すことができません。</span><span class="sxs-lookup"><span data-stu-id="06808-118">When you turn off push notifications, users can't turn them back on.</span></span>
    
> [!IMPORTANT]
>  <span data-ttu-id="06808-119">マイクロソフトは、他の企業を使用して Windows Phone、iPhone、iPad のユーザー向けにリアルタイムな Skype for Business モバイル通知を提供しています。</span><span class="sxs-lookup"><span data-stu-id="06808-119">Microsoft uses other companies to provide real-time Skype for Business mobile notifications for Windows Phone, iPhone, and iPad users.</span></span> <span data-ttu-id="06808-120">「 [Microsoft Skype for Business 製品のプライバシーに関する声明](https://go.microsoft.com/fwlink/p/?linkid=247732)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="06808-120">See the [Privacy Statement for Microsoft Skype for Business Products](https://go.microsoft.com/fwlink/p/?linkid=247732).</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="06808-121">関連トピック</span><span class="sxs-lookup"><span data-stu-id="06808-121">Related topics</span></span>

[<span data-ttu-id="06808-122">Skype for Business Online のセットアップ</span><span class="sxs-lookup"><span data-stu-id="06808-122">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

  
 