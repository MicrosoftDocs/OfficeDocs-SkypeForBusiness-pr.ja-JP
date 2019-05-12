---
title: 会議を構成するビジネス サーバーの Skype での参加のページ
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6537765e-4384-416f-92f1-a7f3b39ebe56
description: '概要: 会議を構成する方法を学習する Skype ビジネス サーバー用のページを結合します。'
ms.openlocfilehash: 4ed89d07b85072ba86fc89db33e4902b97373d11
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33913336"
---
# <a name="configure-the-meeting-join-page-in-skype-for-business-server"></a><span data-ttu-id="84143-103">会議を構成するビジネス サーバーの Skype での参加のページ</span><span class="sxs-lookup"><span data-stu-id="84143-103">Configure the meeting join page in Skype for Business Server</span></span>
 
<span data-ttu-id="84143-104">**の概要:** 会議を構成する方法については Skype ビジネス サーバー用のページを結合します。</span><span class="sxs-lookup"><span data-stu-id="84143-104">**Summary:** Learn how to configure the meeting join page in Skype for Business Server.</span></span>
  
<span data-ttu-id="84143-105">ユーザーが会議出席依頼、会議の会議のリンクをクリックすると結合のページは、ユーザーのコンピューターで、Skype のビジネスのクライアントが既にインストールされているかどうかを検出します。</span><span class="sxs-lookup"><span data-stu-id="84143-105">When a user clicks a meeting link in a meeting request, the meeting join page detects whether a Skype for Business client is already installed on the user's computer.</span></span> <span data-ttu-id="84143-106">クライアントが既にインストールされている場合、クライアントが開き、ミーティングに参加します。</span><span class="sxs-lookup"><span data-stu-id="84143-106">If a client is already installed, the client opens and joins the meeting.</span></span> <span data-ttu-id="84143-107">クライアントがインストールされていない場合既定ではビジネスの Skype クライアントを開きます。</span><span class="sxs-lookup"><span data-stu-id="84143-107">If a client is not installed, by default the Skype for Business client opens.</span></span> 
  
## <a name="configure-the-meeting-join-page"></a><span data-ttu-id="84143-108">会議参加ページの構成</span><span class="sxs-lookup"><span data-stu-id="84143-108">Configure the meeting join page</span></span>

<span data-ttu-id="84143-109">会議の結合の動作を変更するページの他のバージョンのクライアントとの会議に参加するユーザーを許可する場合。</span><span class="sxs-lookup"><span data-stu-id="84143-109">You can modify the behavior of the meeting join page if you want to allow users to join meetings with other versions of the client.</span></span> <span data-ttu-id="84143-110">これらの構成オプションは、ビジネス サーバーのコントロール パネルの Skype から削除されていますが、セット CsWebServiceConfiguration コマンドレットを使用して、それらを構成します。</span><span class="sxs-lookup"><span data-stu-id="84143-110">These configuration options have been removed from the Skype for Business Server Control Panel, but you configure them by using the Set-CsWebServiceConfiguration cmdlet.</span></span>
  
<span data-ttu-id="84143-111">**ミーティング参加ページ セットの CsWebServiceConfiguration のパラメーター**</span><span class="sxs-lookup"><span data-stu-id="84143-111">**Meeting Join Page Set-CsWebServiceConfiguration parameters**</span></span>

|<span data-ttu-id="84143-112">**パラメーターのセット CsWebServiceConfiguration**</span><span class="sxs-lookup"><span data-stu-id="84143-112">**Set-CsWebServiceConfiguration parameter**</span></span>|<span data-ttu-id="84143-113">**説明**</span><span class="sxs-lookup"><span data-stu-id="84143-113">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="84143-114">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="84143-114">ShowJoinUsingLegacyClientLink</span></span>  <br/> |<span data-ttu-id="84143-115">ビジネス サーバーの設置型バージョンの Skype を使用するため、このパラメーターは廃止されました。</span><span class="sxs-lookup"><span data-stu-id="84143-115">This parameter has been deprecated for use with the on-premises version of Skype for Business Server.</span></span>  <br/> <span data-ttu-id="84143-116">かどうか True に設定する、以外のクライアント アプリケーションを使用してミーティングに参加するユーザー ビジネス用の Skype は機会がある、現在のクライアント アプリケーションを使用してミーティングに参加します。</span><span class="sxs-lookup"><span data-stu-id="84143-116">If set to True, users joining a meeting by using a client application other than Skype for Business will be given the opportunity to join the meeting by using their current client application.</span></span> <span data-ttu-id="84143-117">既定値は False です。</span><span class="sxs-lookup"><span data-stu-id="84143-117">The default value is False.</span></span>  <br/> |
|<span data-ttu-id="84143-118">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="84143-118">ShowAlternateJoinOptionsExpanded</span></span>  <br/> |<span data-ttu-id="84143-119">ビジネス サーバーの設置型バージョンの Skype を使用するため、このパラメーターは廃止されました。</span><span class="sxs-lookup"><span data-stu-id="84143-119">This parameter has been deprecated for use with the on-premises version of Skype for Business Server.</span></span>  <br/>  <span data-ttu-id="84143-120">かどうかは True に設定すると、代替オプションのオンライン会議に参加するため自動的に展開され、ユーザーに表示します。</span><span class="sxs-lookup"><span data-stu-id="84143-120">If set to True, alternate options for joining an online conference are automatically expanded and shown to users.</span></span> <span data-ttu-id="84143-121">場合は False (既定値) に設定すると、これらのオプションを使用できるがユーザー自身でオプションの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="84143-121">If set to False (the default value), these options will be available, but the user will have to display the list of options for themselves.</span></span>  <br/> |
   

