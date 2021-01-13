---
title: Skype for Business Server で会議サーバーの構成設定を管理する
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
ms.assetid: 36bed690-6e22-4e11-88c1-b40a20836c6a
description: '概要: Skype for Business Server で会議サーバーの構成設定を管理する方法について説明します。'
ms.openlocfilehash: 7f8714a4098285e955b559b2baf70d74957159a1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828287"
---
# <a name="manage-conferencing-server-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="35a45-103">Skype for Business Server で会議サーバーの構成設定を管理する</span><span class="sxs-lookup"><span data-stu-id="35a45-103">Manage conferencing server configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="35a45-104">**概要:** Skype for Business Server で会議サーバーの構成設定を管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="35a45-104">**Summary:** Learn how to manage conferencing server configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="35a45-105">このトピックでは、会議の構成設定を管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="35a45-105">This topic describes how to manage conferencing configuration settings.</span></span> <span data-ttu-id="35a45-106">会議を計画および展開する方法の詳細については [、「Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) での会議の計画」および「Skype for Business Server での会議の展開」を [参照してください](../../deploy/deploy-conferencing/deploy-conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="35a45-106">For more information about how to plan and deploy conferencing, see [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span></span>
  
<span data-ttu-id="35a45-107">会議の構成設定では、会議コンテンツと資料の最大許容サイズなどの決定を行います。アプリケーション共有会議サービスの最大帯域幅。ストレージの制限と有効期限サポートされているクライアントの内部および外部ダウンロードの URL。ユーザーが会議のヘルプとリソースを取得できる内部 URL および外部 URL へのポインター。アプリケーション共有、クライアント オーディオ、ファイル転送、およびメディア トラフィックに使用されるポート。</span><span class="sxs-lookup"><span data-stu-id="35a45-107">Conferencing configuration settings determine such things as the maximum allowed size for meeting content and handouts; maximum amount of bandwidth for the Application Sharing Conferencing service; storage limits and expiration periods; the URLs for the internal and external downloads of the supported client; pointers to internal and external URLs where users can obtain conferencing help and resources; and the ports used for application sharing, client audio, file transfers, and media traffic.</span></span> <span data-ttu-id="35a45-108">これらの設定を使用すると、実際のサーバー自体を管理できます。</span><span class="sxs-lookup"><span data-stu-id="35a45-108">These settings allow you to manage the actual servers themselves.</span></span> <span data-ttu-id="35a45-109">これらの設定は、Skype for Business Server 管理シェルを使用して設定できます。</span><span class="sxs-lookup"><span data-stu-id="35a45-109">These settings can be set by using Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="35a45-110">Skype for Business Server をインストールすると、会議構成設定の単一のコレクション (グローバル コレクション) がシステムによって提供されます。</span><span class="sxs-lookup"><span data-stu-id="35a45-110">When you install Skype for Business Server, the system provides you with a single collection of conferencing configuration settings (the global collection).</span></span> <span data-ttu-id="35a45-111">サイトまたはサービスに対してカスタム設定を作成する必要がある場合は、**New-CsConferencingConfiguration** コマンドレットを使用してその作業を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="35a45-111">If you need to create custom settings for a site or service, you can do so using the **New-CsConferencingConfiguration** cmdlet.</span></span> <span data-ttu-id="35a45-112">新しい設定は、サイトスコープまたはサービス スコープでのみ適用できます。会議構成設定の新しいグローバル コレクションを作成することはできませんが **、Set-CsConferencingConfiguration** コマンドレットを使用してグローバル コレクションを変更できます。</span><span class="sxs-lookup"><span data-stu-id="35a45-112">Note that new settings can be applied only at the site or service scope; you cannot create a new global collection of conferencing configuration settings, but you can modify the global collection by using the **Set-CsConferencingConfiguration** cmdlet.</span></span> <span data-ttu-id="35a45-113">また、いかなるサイトやサービスも、設定のコレクションは 1 つしかホストできません。</span><span class="sxs-lookup"><span data-stu-id="35a45-113">In addition, no site or service can host more than one collection of settings.</span></span> <span data-ttu-id="35a45-114">Redmond サイト向けの新しい設定を作成しようとしても、Redmond サイトが既に会議構成設定のコレクションをホストしている場合、そのコマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="35a45-114">If you try to create new settings for the Redmond site and the Redmond site already hosts a collection of conferencing configuration settings, then your command will fail.</span></span>
  
## <a name="manage-conferencing-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="35a45-115">Skype for Business Server 管理シェルを使用して会議の構成設定を管理する</span><span class="sxs-lookup"><span data-stu-id="35a45-115">Manage conferencing configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="35a45-116">Skype for Business Server 管理シェルを使用して会議構成設定を管理するには、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="35a45-116">To manage conferencing configuration settings by using Skype for Business Server Management Shell, use the following cmdlets:</span></span>
  
<span data-ttu-id="35a45-117">**会議の構成設定**</span><span class="sxs-lookup"><span data-stu-id="35a45-117">**Conferencing configuration settings**</span></span>

|<span data-ttu-id="35a45-118">**コマンドレット**</span><span class="sxs-lookup"><span data-stu-id="35a45-118">**Cmdlet**</span></span>|<span data-ttu-id="35a45-119">**説明**</span><span class="sxs-lookup"><span data-stu-id="35a45-119">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="35a45-120">Get-CsConferencingConfiguration</span><span class="sxs-lookup"><span data-stu-id="35a45-120">Get-CsConferencingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csconferencingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="35a45-121">組織の会議構成設定に関する情報を戻します。</span><span class="sxs-lookup"><span data-stu-id="35a45-121">Returns information about the conferencing configuration settings for your organization.</span></span>  <br/> |
|[<span data-ttu-id="35a45-122">New-CsConferencingConfiguration</span><span class="sxs-lookup"><span data-stu-id="35a45-122">New-CsConferencingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="35a45-123">会議構成設定の新しいコレクションを作成します。</span><span class="sxs-lookup"><span data-stu-id="35a45-123">Creates a new collection of conferencing configuration settings.</span></span>  <br/> |
|[<span data-ttu-id="35a45-124">Remove-CsConferencingConfiguration</span><span class="sxs-lookup"><span data-stu-id="35a45-124">Remove-CsConferencingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="35a45-125">指定された会議構成設定のコレクションを削除します。</span><span class="sxs-lookup"><span data-stu-id="35a45-125">Removes the specified collection of conferencing configuration settings.</span></span>  <br/> |
|[<span data-ttu-id="35a45-126">Set-CsConferencingConfiguration</span><span class="sxs-lookup"><span data-stu-id="35a45-126">Set-CsConferencingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="35a45-127">会議構成設定の既存のコレクションを変更します。</span><span class="sxs-lookup"><span data-stu-id="35a45-127">Modifies an existing collection of conferencing configuration settings.</span></span>  <br/> |
   
<span data-ttu-id="35a45-128">次のコマンドは、Redmond サイト (site:Redmond) の会議構成設定の新しいコレクションを作成します。</span><span class="sxs-lookup"><span data-stu-id="35a45-128">The following command creates a new collection of conferencing configuration settings for the Redmond site (site:Redmond).</span></span> <span data-ttu-id="35a45-129">この例では、Organization プロパティの値を Litwareinc に設定するために使用される追加のパラメーター (Organization) が 1 つ含まれています。</span><span class="sxs-lookup"><span data-stu-id="35a45-129">In this example, one additional parameter is included (Organization) which is used to set the value of the Organization property to Litwareinc:</span></span> 
  
```PowerShell
New-CsConferencingConfiguration -Identity site:Redmond -Organization Litwareinc
```

<span data-ttu-id="35a45-130">このようなコレクションはサイトごとに 1 つしか持てないので、Redmond サイトに会議構成設定のコレクションが既に存在する場合、このコマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="35a45-130">Note that you can have only one such collection per site, so this command would fail if the Redmond site already has a collection of conferencing configuration settings.</span></span> 
  
<span data-ttu-id="35a45-131">次の例では、最初にメモリに格納され、後で Redmond サイトに適用される会議構成設定の新しいコレクションを定義します。</span><span class="sxs-lookup"><span data-stu-id="35a45-131">The next example defines a new collection of conferencing configuration settings, which are stored in memory initially, and then applied to the Redmond site at a later time.</span></span> 
  
<span data-ttu-id="35a45-132">最初のコマンドでは **、New-CsConferencingConfiguration** コマンドレットを使用して、変数データベースに格納されている設定の新しいメモリ内コレクションを作成$x。</span><span class="sxs-lookup"><span data-stu-id="35a45-132">The first command uses the **New-CsConferencingConfiguration** cmdlet to create a new, in-memory collection of settings stored in the variable $x.</span></span> <span data-ttu-id="35a45-133">InMemory パラメーターは、Redmond サイトにすぐに適用するのではなく、メモリ内にコレクションを作成する必要を指定します。</span><span class="sxs-lookup"><span data-stu-id="35a45-133">The InMemory parameter specifies that the collection should be created in memory rather than immediately applied to the Redmond site.</span></span>
  
<span data-ttu-id="35a45-134">コレクションの作成後、2 番目のコマンドで Organization プロパティの値に Litwareinc を設定しています。</span><span class="sxs-lookup"><span data-stu-id="35a45-134">After the collection has been created, the second command sets the value of the Organization property to Litwareinc.</span></span> 
  
<span data-ttu-id="35a45-135">最後に、3 番目のコマンドで **Set-CsConferencingConfiguration** コマンドレットを使用して、新しい設定を実際に Redmond サイトに適用します。</span><span class="sxs-lookup"><span data-stu-id="35a45-135">Finally, the third command uses the **Set-CsConferencingConfiguration** cmdlet to actually apply the new settings to the Redmond site:</span></span>
  
```PowerShell
$x = New-CsConferencingConfiguration -Identity site:Redmond -InMemory
$x.Organization = "Litwareinc"
Set-CsConferencingConfiguration -Instance $x
```

<span data-ttu-id="35a45-136">**Set-CsConferencingConfiguration** コマンドレットを呼び出さない場合、新しい設定が有効になります。</span><span class="sxs-lookup"><span data-stu-id="35a45-136">If you do not call the **Set-CsConferencingConfiguration** cmdlet, the new settings will never take effect.</span></span> <span data-ttu-id="35a45-137">代わりに、セッションを終了するか、変数を削除するとすぐにWindows PowerShellに表示$x。</span><span class="sxs-lookup"><span data-stu-id="35a45-137">Instead, they will disappear as soon as you end your Windows PowerShell session or delete the variable $x.</span></span>
  

