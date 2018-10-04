---
title: 会議を構成する結合のページ
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: End User
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ユーザーが会議出席依頼、会議の会議のリンクをクリックすると結合のページは、どのクライアントがユーザーのコンピューターに既にインストールされているを検出します。 クライアントが既にインストールされている場合、そのクライアントは開き、ミーティングに参加します。 クライアントがインストールされていない場合は、既定で Web アプリケーションを開きます。
ms.openlocfilehash: f7c66b7e7171e9d7f0dc39f30a7e99059e53a0c2
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "25374063"
---
# <a name="configure-the-meeting-join-page"></a><span data-ttu-id="97632-105">会議を構成する結合のページ</span><span class="sxs-lookup"><span data-stu-id="97632-105">Configure the meeting join page</span></span>

<span data-ttu-id="97632-106">ユーザーが会議出席依頼、会議の会議のリンクをクリックすると結合のページは、どのクライアントがユーザーのコンピューターに既にインストールされているを検出します。</span><span class="sxs-lookup"><span data-stu-id="97632-106">When a user clicks a meeting link in a meeting request, the meeting join page detects which client is already installed on the user's computer.</span></span> <span data-ttu-id="97632-107">クライアントが既にインストールされている場合、そのクライアントは開き、ミーティングに参加します。</span><span class="sxs-lookup"><span data-stu-id="97632-107">If a client is already installed, that client opens and joins the meeting.</span></span> <span data-ttu-id="97632-108">クライアントがインストールされていない場合は、既定で Web アプリケーションを開きます。</span><span class="sxs-lookup"><span data-stu-id="97632-108">If a client is not installed, by default the Web App opens.</span></span>
  
<span data-ttu-id="97632-109">会議の結合の動作を変更することができますページの会議に参加するユーザーを許可する場合。</span><span class="sxs-lookup"><span data-stu-id="97632-109">You can modify the behavior of the meeting join page if you want to allow users to join meetings.</span></span> <span data-ttu-id="97632-110">これらの構成オプションは、[コントロール パネル] から削除されたが、CsWebServiceConfiguration コマンドレットを使用して、それらを構成します。</span><span class="sxs-lookup"><span data-stu-id="97632-110">These configuration options have been removed from the Control Panel, but you configure them by using the CsWebServiceConfiguration cmdlet.</span></span>
  
<span data-ttu-id="97632-111">**ミーティング参加ページの CsWebServiceConfiguration のパラメーター**</span><span class="sxs-lookup"><span data-stu-id="97632-111">**Meeting Join Page CsWebServiceConfiguration Parameters**</span></span>

|<span data-ttu-id="97632-112">**CsWebServiceConfiguration パラメーター**</span><span class="sxs-lookup"><span data-stu-id="97632-112">**CsWebServiceConfiguration Parameter**</span></span>|<span data-ttu-id="97632-113">**説明**</span><span class="sxs-lookup"><span data-stu-id="97632-113">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="97632-114">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="97632-114">ShowJoinUsingLegacyClientLink</span></span>  <br/> |<span data-ttu-id="97632-115">かどうかに True を設定する以外は、Lync クライアント アプリケーションを使用してミーティングに参加するユーザーが与えられますミーティングに参加することです。</span><span class="sxs-lookup"><span data-stu-id="97632-115">If set to True, users joining a meeting by using a client application other than Lync will be given the opportunity to join the meeting.</span></span> <span data-ttu-id="97632-116">既定値は False です。</span><span class="sxs-lookup"><span data-stu-id="97632-116">The default value is False.</span></span>  <br/> |
|<span data-ttu-id="97632-117">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="97632-117">ShowAlternateJoinOptionsExpanded</span></span>  <br/> |<span data-ttu-id="97632-118">True の場合、別のオプションのオンライン会議に参加するに自動的に展開されユーザーに表示されるのです。</span><span class="sxs-lookup"><span data-stu-id="97632-118">When set to True, alternate options for joining an online conference will automatically be expanded and shown to users.</span></span> <span data-ttu-id="97632-119">False (既定値) に設定すると、これらのオプションを使用できるが、ユーザー自身でオプションの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="97632-119">When set to False (the default value), these options will be available, but the user will have to display the list of options for themselves.</span></span>  <br/> |
   
### <a name="to-configure-the-meeting-join-page-by-using-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="97632-120">会議を構成するのにはビジネス サーバー 2019 管理シェルには、Skype を使用して結合ページ</span><span class="sxs-lookup"><span data-stu-id="97632-120">To configure the meeting join page by using Skype for Business Server 2019 Management Shell</span></span>

1. <span data-ttu-id="97632-121">ビジネス サーバー 2019 管理シェルには、Skype を起動する: [**スタート**] ボタン、[**すべてのプログラム**] をクリックして、**ビジネス サーバー 2019 の Skype をマイクロソフト**をクリック**ビジネス サーバー管理シェルの Skype**です。</span><span class="sxs-lookup"><span data-stu-id="97632-121">Start the Skype for Business Server 2019 Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="97632-122">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="97632-122">Run the following cmdlet:</span></span> 
    
   ```
   Get-CsWebServiceConfiguration
   ```

    <span data-ttu-id="97632-123">このコマンドレットは、web サービスの構成設定を返します。</span><span class="sxs-lookup"><span data-stu-id="97632-123">This cmdlet returns the web service configuration settings.</span></span>
    
3. <span data-ttu-id="97632-124">パラメーターに設定する場合は True または False で、好みに応じて次のコマンドを実行 (このコマンドレットのパラメーターの詳細については、 [Skype](../../SfbServer/manage/management-shell.md)ビジネス サーバー管理シェルのマニュアルを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="97632-124">Run the following command, with the parameters set to True or False, depending on your preference (for details about the parameters for this cmdlet, see the [Skype for Business Server Management Shell](../../SfbServer/manage/management-shell.md) documentation):</span></span>
    
   ```
   Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True
   ```


