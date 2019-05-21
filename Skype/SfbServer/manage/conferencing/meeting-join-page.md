---
title: Skype for Business Server で会議の参加ページを構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6537765e-4384-416f-92f1-a7f3b39ebe56
description: '概要: Skype for Business Server で会議の参加ページを構成する方法について説明します。'
ms.openlocfilehash: 30e220f2a1745aea0a77e3ec3ff491b842a2b221
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34283726"
---
# <a name="configure-the-meeting-join-page-in-skype-for-business-server"></a><span data-ttu-id="4d749-103">Skype for Business Server で会議の参加ページを構成する</span><span class="sxs-lookup"><span data-stu-id="4d749-103">Configure the meeting join page in Skype for Business Server</span></span>
 
<span data-ttu-id="4d749-104">**概要:** Skype for Business Server で会議の参加ページを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4d749-104">**Summary:** Learn how to configure the meeting join page in Skype for Business Server.</span></span>
  
<span data-ttu-id="4d749-105">ユーザーが会議出席依頼の会議リンクをクリックすると、[会議の参加] ページによって、ユーザーのコンピューターに Skype for Business クライアントが既にインストールされているかどうかが検出されます。</span><span class="sxs-lookup"><span data-stu-id="4d749-105">When a user clicks a meeting link in a meeting request, the meeting join page detects whether a Skype for Business client is already installed on the user's computer.</span></span> <span data-ttu-id="4d749-106">クライアントが既にインストールされている場合は、クライアントが開き、会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="4d749-106">If a client is already installed, the client opens and joins the meeting.</span></span> <span data-ttu-id="4d749-107">クライアントがインストールされていない場合、既定では、Skype for Business クライアントが開きます。</span><span class="sxs-lookup"><span data-stu-id="4d749-107">If a client is not installed, by default the Skype for Business client opens.</span></span> 
  
## <a name="configure-the-meeting-join-page"></a><span data-ttu-id="4d749-108">会議参加ページの構成</span><span class="sxs-lookup"><span data-stu-id="4d749-108">Configure the meeting join page</span></span>

<span data-ttu-id="4d749-109">ユーザーが他のバージョンのクライアントと会議に参加できるようにする場合は、[会議参加] ページの動作を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="4d749-109">You can modify the behavior of the meeting join page if you want to allow users to join meetings with other versions of the client.</span></span> <span data-ttu-id="4d749-110">これらの構成オプションは、Skype for Business Server コントロールパネルから削除されていますが、CsWebServiceConfiguration コマンドレットを使用して設定します。</span><span class="sxs-lookup"><span data-stu-id="4d749-110">These configuration options have been removed from the Skype for Business Server Control Panel, but you configure them by using the Set-CsWebServiceConfiguration cmdlet.</span></span>
  
<span data-ttu-id="4d749-111">**会議の参加ページの設定-CsWebServiceConfiguration パラメーター**</span><span class="sxs-lookup"><span data-stu-id="4d749-111">**Meeting Join Page Set-CsWebServiceConfiguration parameters**</span></span>

|<span data-ttu-id="4d749-112">**CsWebServiceConfiguration パラメーター**</span><span class="sxs-lookup"><span data-stu-id="4d749-112">**Set-CsWebServiceConfiguration parameter**</span></span>|<span data-ttu-id="4d749-113">**説明**</span><span class="sxs-lookup"><span data-stu-id="4d749-113">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4d749-114">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="4d749-114">ShowJoinUsingLegacyClientLink</span></span>  <br/> |<span data-ttu-id="4d749-115">このパラメーターは、Skype for Business Server のオンプレミスバージョンで使用するために廃止されました。</span><span class="sxs-lookup"><span data-stu-id="4d749-115">This parameter has been deprecated for use with the on-premises version of Skype for Business Server.</span></span>  <br/> <span data-ttu-id="4d749-116">True に設定すると、Skype for Business 以外のクライアントアプリケーションを使用して会議に参加するユーザーには、現在のクライアントアプリケーションを使用して会議に参加する機会が与えられます。</span><span class="sxs-lookup"><span data-stu-id="4d749-116">If set to True, users joining a meeting by using a client application other than Skype for Business will be given the opportunity to join the meeting by using their current client application.</span></span> <span data-ttu-id="4d749-117">既定値は False です。</span><span class="sxs-lookup"><span data-stu-id="4d749-117">The default value is False.</span></span>  <br/> |
|<span data-ttu-id="4d749-118">Showalternatejoinoptionている</span><span class="sxs-lookup"><span data-stu-id="4d749-118">ShowAlternateJoinOptionsExpanded</span></span>  <br/> |<span data-ttu-id="4d749-119">このパラメーターは、Skype for Business Server のオンプレミスバージョンで使用するために廃止されました。</span><span class="sxs-lookup"><span data-stu-id="4d749-119">This parameter has been deprecated for use with the on-premises version of Skype for Business Server.</span></span>  <br/>  <span data-ttu-id="4d749-120">True に設定すると、オンライン会議に参加するための代替オプションが自動的に展開され、ユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="4d749-120">If set to True, alternate options for joining an online conference are automatically expanded and shown to users.</span></span> <span data-ttu-id="4d749-121">False (既定値) に設定した場合、これらのオプションは使用できますが、ユーザーは独自のオプションの一覧を表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d749-121">If set to False (the default value), these options will be available, but the user will have to display the list of options for themselves.</span></span>  <br/> |
   

