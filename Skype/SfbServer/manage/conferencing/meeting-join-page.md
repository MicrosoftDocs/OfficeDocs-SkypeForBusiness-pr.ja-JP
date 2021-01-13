---
title: Skype for Business Server で会議参加ページを構成する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6537765e-4384-416f-92f1-a7f3b39ebe56
description: '概要: Skype for Business Server で会議参加ページを構成する方法について学習します。'
ms.openlocfilehash: 247664a3ff4bbc4ee055775d26f1d077b662752b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828037"
---
# <a name="configure-the-meeting-join-page-in-skype-for-business-server"></a><span data-ttu-id="8739d-103">Skype for Business Server で会議参加ページを構成する</span><span class="sxs-lookup"><span data-stu-id="8739d-103">Configure the meeting join page in Skype for Business Server</span></span>
 
<span data-ttu-id="8739d-104">**概要:** Skype for Business Server で会議参加ページを構成する方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="8739d-104">**Summary:** Learn how to configure the meeting join page in Skype for Business Server.</span></span>
  
<span data-ttu-id="8739d-105">ユーザーが会議出席依頼の会議リンクをクリックすると、会議参加ページは、Skype for Business クライアントがユーザーのコンピューターに既にインストールされているかどうかを検出します。</span><span class="sxs-lookup"><span data-stu-id="8739d-105">When a user clicks a meeting link in a meeting request, the meeting join page detects whether a Skype for Business client is already installed on the user's computer.</span></span> <span data-ttu-id="8739d-106">クライアントがすでにインストールされている場合、クライアントがミーティングを開き、参加します。</span><span class="sxs-lookup"><span data-stu-id="8739d-106">If a client is already installed, the client opens and joins the meeting.</span></span> <span data-ttu-id="8739d-107">クライアントがインストールされていない場合は、既定で Skype for Business クライアントが開きます。</span><span class="sxs-lookup"><span data-stu-id="8739d-107">If a client is not installed, by default the Skype for Business client opens.</span></span> 
  
## <a name="configure-the-meeting-join-page"></a><span data-ttu-id="8739d-108">会議参加ページの構成</span><span class="sxs-lookup"><span data-stu-id="8739d-108">Configure the meeting join page</span></span>

<span data-ttu-id="8739d-109">ユーザーが他のバージョンのクライアントとの会議に参加できる場合は、会議参加ページの動作を変更できます。</span><span class="sxs-lookup"><span data-stu-id="8739d-109">You can modify the behavior of the meeting join page if you want to allow users to join meetings with other versions of the client.</span></span> <span data-ttu-id="8739d-110">これらの構成オプションは Skype for Business Server コントロール パネルから削除されましたが、次のコマンドレットを使用して構成Set-CsWebServiceConfigurationします。</span><span class="sxs-lookup"><span data-stu-id="8739d-110">These configuration options have been removed from the Skype for Business Server Control Panel, but you configure them by using the Set-CsWebServiceConfiguration cmdlet.</span></span>
  
<span data-ttu-id="8739d-111">**会議参加ページのSet-CsWebServiceConfigurationパラメーター**</span><span class="sxs-lookup"><span data-stu-id="8739d-111">**Meeting Join Page Set-CsWebServiceConfiguration parameters**</span></span>

|<span data-ttu-id="8739d-112">**Set-CsWebServiceConfiguration パラメーター**</span><span class="sxs-lookup"><span data-stu-id="8739d-112">**Set-CsWebServiceConfiguration parameter**</span></span>|<span data-ttu-id="8739d-113">**説明**</span><span class="sxs-lookup"><span data-stu-id="8739d-113">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8739d-114">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="8739d-114">ShowJoinUsingLegacyClientLink</span></span>  <br/> |<span data-ttu-id="8739d-115">このパラメーターは、Skype for Business Server のオンプレミス バージョンで使用するために廃止されました。</span><span class="sxs-lookup"><span data-stu-id="8739d-115">This parameter has been deprecated for use with the on-premises version of Skype for Business Server.</span></span>  <br/> <span data-ttu-id="8739d-116">True に設定されている場合、Skype for Business 以外のクライアント アプリケーションを使用して会議に参加するユーザーには、現在のクライアント アプリケーションを使用して会議に参加する機会が与えられる。</span><span class="sxs-lookup"><span data-stu-id="8739d-116">If set to True, users joining a meeting by using a client application other than Skype for Business will be given the opportunity to join the meeting by using their current client application.</span></span> <span data-ttu-id="8739d-117">既定値は False です。</span><span class="sxs-lookup"><span data-stu-id="8739d-117">The default value is False.</span></span>  <br/> |
|<span data-ttu-id="8739d-118">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="8739d-118">ShowAlternateJoinOptionsExpanded</span></span>  <br/> |<span data-ttu-id="8739d-119">このパラメーターは、Skype for Business Server のオンプレミス バージョンで使用するために廃止されました。</span><span class="sxs-lookup"><span data-stu-id="8739d-119">This parameter has been deprecated for use with the on-premises version of Skype for Business Server.</span></span>  <br/>  <span data-ttu-id="8739d-120">True に設定すると、オンライン会議に参加するための代替オプションが自動的に展開され、ユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="8739d-120">If set to True, alternate options for joining an online conference are automatically expanded and shown to users.</span></span> <span data-ttu-id="8739d-121">False (既定値) に設定すると、これらのオプションを使用できますが、ユーザーは自分でオプションの一覧を表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8739d-121">If set to False (the default value), these options will be available, but the user will have to display the list of options for themselves.</span></span>  <br/> |
   

