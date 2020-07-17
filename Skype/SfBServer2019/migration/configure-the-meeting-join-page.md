---
title: 会議参加ページの構成
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: End User
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ユーザーが会議出席依頼の会議リンクをクリックすると、会議参加ページがユーザーのコンピューターに既にインストールされているクライアントを検出します。 クライアントがすでにインストールされている場合、そのクライアントが会議を開き、参加します。 クライアントがインストールされていない場合は、既定で Web アプリが開きます。
ms.openlocfilehash: a7bb0983438708bbc0d30cd527eb494491c3cbf2
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754027"
---
# <a name="configure-the-meeting-join-page"></a><span data-ttu-id="ecc28-105">会議参加ページの構成</span><span class="sxs-lookup"><span data-stu-id="ecc28-105">Configure the meeting join page</span></span>

<span data-ttu-id="ecc28-106">ユーザーが会議出席依頼の会議リンクをクリックすると、会議参加ページがユーザーのコンピューターに既にインストールされているクライアントを検出します。</span><span class="sxs-lookup"><span data-stu-id="ecc28-106">When a user clicks a meeting link in a meeting request, the meeting join page detects which client is already installed on the user's computer.</span></span> <span data-ttu-id="ecc28-107">クライアントがすでにインストールされている場合、そのクライアントが会議を開き、参加します。</span><span class="sxs-lookup"><span data-stu-id="ecc28-107">If a client is already installed, that client opens and joins the meeting.</span></span> <span data-ttu-id="ecc28-108">クライアントがインストールされていない場合は、既定で Web アプリが開きます。</span><span class="sxs-lookup"><span data-stu-id="ecc28-108">If a client is not installed, by default the Web App opens.</span></span>
  
<span data-ttu-id="ecc28-109">ユーザーが会議に参加できるようにする場合は、会議参加ページの動作を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="ecc28-109">You can modify the behavior of the meeting join page if you want to allow users to join meetings.</span></span> <span data-ttu-id="ecc28-110">これらの構成オプションは、コントロールパネルから削除されましたが、Set-cswebserviceconfiguration コマンドレットを使用して構成します。</span><span class="sxs-lookup"><span data-stu-id="ecc28-110">These configuration options have been removed from the Control Panel, but you configure them by using the CsWebServiceConfiguration cmdlet.</span></span>
  
<span data-ttu-id="ecc28-111">**会議参加ページの CsWebServiceConfiguration のパラメーター**</span><span class="sxs-lookup"><span data-stu-id="ecc28-111">**Meeting Join Page CsWebServiceConfiguration Parameters**</span></span>

|<span data-ttu-id="ecc28-112">**CsWebServiceConfiguration のパラメーター**</span><span class="sxs-lookup"><span data-stu-id="ecc28-112">**CsWebServiceConfiguration Parameter**</span></span>|<span data-ttu-id="ecc28-113">**説明**</span><span class="sxs-lookup"><span data-stu-id="ecc28-113">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ecc28-114">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="ecc28-114">ShowJoinUsingLegacyClientLink</span></span>  <br/> |<span data-ttu-id="ecc28-115">True に設定すると、Lync 以外のクライアントアプリケーションを使用して会議に参加しているユーザーには、会議に参加する機会が与えられます。</span><span class="sxs-lookup"><span data-stu-id="ecc28-115">If set to True, users joining a meeting by using a client application other than Lync will be given the opportunity to join the meeting.</span></span> <span data-ttu-id="ecc28-116">既定値は False です。</span><span class="sxs-lookup"><span data-stu-id="ecc28-116">The default value is False.</span></span>  <br/> |
|<span data-ttu-id="ecc28-117">Showalternatejoinoptionsexpan</span><span class="sxs-lookup"><span data-stu-id="ecc28-117">ShowAlternateJoinOptionsExpanded</span></span>  <br/> |<span data-ttu-id="ecc28-118">True に設定すると、オンライン会議への代替オプションが自動的に展開され、ユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="ecc28-118">When set to True, alternate options for joining an online conference will automatically be expanded and shown to users.</span></span> <span data-ttu-id="ecc28-119">False (既定値) に設定すると、これらのオプションは使用可能になりますが、ユーザーは自分のオプションの一覧を表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ecc28-119">When set to False (the default value), these options will be available, but the user will have to display the list of options for themselves.</span></span>  <br/> |
   
### <a name="to-configure-the-meeting-join-page-by-using-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="ecc28-120">Skype for Business Server 2019 管理シェルを使用して会議参加ページを構成するには</span><span class="sxs-lookup"><span data-stu-id="ecc28-120">To configure the meeting join page by using Skype for Business Server 2019 Management Shell</span></span>

1. <span data-ttu-id="ecc28-121">Skype for Business Server 2019 管理シェルを起動します。 [**スタート**]、[**すべてのプログラム**]、[ **Microsoft Skype for business Server 2019**]、[ **skype for business server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="ecc28-121">Start the Skype for Business Server 2019 Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="ecc28-122">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="ecc28-122">Run the following cmdlet:</span></span> 
    
   ```PowerShell
   Get-CsWebServiceConfiguration
   ```

    <span data-ttu-id="ecc28-123">このコマンドレットは、Web サービス構成設定を返します。</span><span class="sxs-lookup"><span data-stu-id="ecc28-123">This cmdlet returns the web service configuration settings.</span></span>
    
3. <span data-ttu-id="ecc28-124">ユーザーの設定に応じて、パラメーターを True または False に設定して、次のコマンドを実行します (このコマンドレットのパラメーターの詳細については、「 [Skype For Business Server Management Shell](../../SfbServer/manage/management-shell.md) 」のドキュメントを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="ecc28-124">Run the following command, with the parameters set to True or False, depending on your preference (for details about the parameters for this cmdlet, see the [Skype for Business Server Management Shell](../../SfbServer/manage/management-shell.md) documentation):</span></span>
    
   ```PowerShell
   Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True
   ```


