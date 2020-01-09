---
title: 会議参加ページの構成
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: End User
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ユーザーが会議出席依頼の会議リンクをクリックすると、[会議の参加] ページによって、ユーザーのコンピューターに既にインストールされているクライアントが検出されます。 クライアントが既にインストールされている場合は、そのクライアントが開き、会議に参加します。 クライアントがインストールされていない場合は、既定で Web アプリが開きます。
ms.openlocfilehash: 5c9e6653783d90411e0f701b5d3395c569d8bdff
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40989562"
---
# <a name="configure-the-meeting-join-page"></a><span data-ttu-id="14d66-105">会議参加ページの構成</span><span class="sxs-lookup"><span data-stu-id="14d66-105">Configure the meeting join page</span></span>

<span data-ttu-id="14d66-106">ユーザーが会議出席依頼の会議リンクをクリックすると、[会議の参加] ページによって、ユーザーのコンピューターに既にインストールされているクライアントが検出されます。</span><span class="sxs-lookup"><span data-stu-id="14d66-106">When a user clicks a meeting link in a meeting request, the meeting join page detects which client is already installed on the user's computer.</span></span> <span data-ttu-id="14d66-107">クライアントが既にインストールされている場合は、そのクライアントが開き、会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="14d66-107">If a client is already installed, that client opens and joins the meeting.</span></span> <span data-ttu-id="14d66-108">クライアントがインストールされていない場合は、既定で Web アプリが開きます。</span><span class="sxs-lookup"><span data-stu-id="14d66-108">If a client is not installed, by default the Web App opens.</span></span>
  
<span data-ttu-id="14d66-109">ユーザーが会議に参加できるようにする場合は、[会議参加] ページの動作を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="14d66-109">You can modify the behavior of the meeting join page if you want to allow users to join meetings.</span></span> <span data-ttu-id="14d66-110">これらの構成オプションはコントロールパネルから削除されていますが、CsWebServiceConfiguration コマンドレットを使用して設定します。</span><span class="sxs-lookup"><span data-stu-id="14d66-110">These configuration options have been removed from the Control Panel, but you configure them by using the CsWebServiceConfiguration cmdlet.</span></span>
  
<span data-ttu-id="14d66-111">**会議の参加ページの CsWebServiceConfiguration パラメーター**</span><span class="sxs-lookup"><span data-stu-id="14d66-111">**Meeting Join Page CsWebServiceConfiguration Parameters**</span></span>

|<span data-ttu-id="14d66-112">**CsWebServiceConfiguration パラメーター**</span><span class="sxs-lookup"><span data-stu-id="14d66-112">**CsWebServiceConfiguration Parameter**</span></span>|<span data-ttu-id="14d66-113">**説明**</span><span class="sxs-lookup"><span data-stu-id="14d66-113">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="14d66-114">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="14d66-114">ShowJoinUsingLegacyClientLink</span></span>  <br/> |<span data-ttu-id="14d66-115">True に設定すると、Lync 以外のクライアントアプリケーションを使用して会議に参加するユーザーには、会議への参加の機会が与えられます。</span><span class="sxs-lookup"><span data-stu-id="14d66-115">If set to True, users joining a meeting by using a client application other than Lync will be given the opportunity to join the meeting.</span></span> <span data-ttu-id="14d66-116">既定値は False です。</span><span class="sxs-lookup"><span data-stu-id="14d66-116">The default value is False.</span></span>  <br/> |
|<span data-ttu-id="14d66-117">Showalternatejoinoptionている</span><span class="sxs-lookup"><span data-stu-id="14d66-117">ShowAlternateJoinOptionsExpanded</span></span>  <br/> |<span data-ttu-id="14d66-118">True に設定すると、オンライン会議に参加するための代替オプションが自動的に展開され、ユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="14d66-118">When set to True, alternate options for joining an online conference will automatically be expanded and shown to users.</span></span> <span data-ttu-id="14d66-119">False (既定値) に設定した場合、これらのオプションは使用できますが、ユーザーは独自のオプションの一覧を表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="14d66-119">When set to False (the default value), these options will be available, but the user will have to display the list of options for themselves.</span></span>  <br/> |
   
### <a name="to-configure-the-meeting-join-page-by-using-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="14d66-120">Skype for Business Server 2019 管理シェルを使用して会議の参加ページを構成するには</span><span class="sxs-lookup"><span data-stu-id="14d66-120">To configure the meeting join page by using Skype for Business Server 2019 Management Shell</span></span>

1. <span data-ttu-id="14d66-121">Skype for Business Server 2019 管理シェルを起動します。 [**スタート**]、[**すべてのプログラム**]、[ **Microsoft skype for business Server 2019**]、[ **skype for business server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="14d66-121">Start the Skype for Business Server 2019 Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="14d66-122">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="14d66-122">Run the following cmdlet:</span></span> 
    
   ```PowerShell
   Get-CsWebServiceConfiguration
   ```

    <span data-ttu-id="14d66-123">このコマンドレットは、web サービスの構成設定を返します。</span><span class="sxs-lookup"><span data-stu-id="14d66-123">This cmdlet returns the web service configuration settings.</span></span>
    
3. <span data-ttu-id="14d66-124">次のコマンドを実行します。設定に応じてパラメーターが True または False に設定されています (このコマンドレットのパラメーターの詳細については、「 [Skype For Business Server 管理シェル](../../SfbServer/manage/management-shell.md)のドキュメント」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="14d66-124">Run the following command, with the parameters set to True or False, depending on your preference (for details about the parameters for this cmdlet, see the [Skype for Business Server Management Shell](../../SfbServer/manage/management-shell.md) documentation):</span></span>
    
   ```PowerShell
   Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True
   ```


