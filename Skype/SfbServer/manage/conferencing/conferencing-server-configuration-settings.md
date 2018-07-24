---
title: 会議サーバーの構成設定で Skype のビジネス サーバーを管理します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 36bed690-6e22-4e11-88c1-b40a20836c6a
description: '概要: ビジネス サーバーの Skype で会議サーバーの構成設定を管理する方法を説明します。'
ms.openlocfilehash: ede34c37e957340f0aa01ac511378d2f4bb3a80e
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "21009895"
---
# <a name="manage-conferencing-server-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="237a0-103">会議サーバーの構成設定で Skype のビジネス サーバーを管理します。</span><span class="sxs-lookup"><span data-stu-id="237a0-103">Manage conferencing server configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="237a0-104">**の概要:** 会議サーバーの構成設定で Skype のビジネス サーバーを管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="237a0-104">**Summary:** Learn how to manage conferencing server configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="237a0-105">このトピックでは、会議サーバーの構成設定を管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="237a0-105">This topic describes how to manage conferencing configuration settings.</span></span> <span data-ttu-id="237a0-106">予定し、会議を展開する方法の詳細については、[ビジネスのサーバー用の Skype での会議の計画](../../plan-your-deployment/conferencing/conferencing.md)と[ビジネス サーバーの Skype で会議を展開](../../deploy/deploy-conferencing/deploy-conferencing.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="237a0-106">For more information about how to plan and deploy conferencing, see [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span></span>
  
<span data-ttu-id="237a0-107">会議構成設定の決定など、サイズが最大の会議の内容と配布資料です。アプリケーション共有会議サービス用の帯域幅の最大値格納域の制限と有効期限です。内部および外部の Url がサポートされているクライアントのダウンロードします。ユーザーが会議のヘルプとリソースを取得できる内部および外部の Url へのポインターアプリケーションの共有、クライアント側のオーディオ、ファイル転送、およびメディア トラフィックに使用するポートです。</span><span class="sxs-lookup"><span data-stu-id="237a0-107">Conferencing configuration settings determine such things as the maximum allowed size for meeting content and handouts; maximum amount of bandwidth for the Application Sharing Conferencing service; storage limits and expiration periods; the URLs for the internal and external downloads of the supported client; pointers to internal and external URLs where users can obtain conferencing help and resources; and the ports used for application sharing, client audio, file transfers, and media traffic.</span></span> <span data-ttu-id="237a0-108">これらの設定を使用すると、実際のサーバーそのものを管理できます。</span><span class="sxs-lookup"><span data-stu-id="237a0-108">These settings allow you to manage the actual servers themselves.</span></span> <span data-ttu-id="237a0-109">Skype ビジネス サーバー管理シェルを使用してこれらの設定を設定できます。</span><span class="sxs-lookup"><span data-stu-id="237a0-109">These settings can be set by using Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="237a0-110">ビジネス サーバーの Skype をインストールするときにシステムで会議の単一のコレクション (グローバル コレクション) の構成設定。</span><span class="sxs-lookup"><span data-stu-id="237a0-110">When you install Skype for Business Server, the system provides you with a single collection of conferencing configuration settings (the global collection).</span></span> <span data-ttu-id="237a0-111">サイトまたはサービス用のカスタム設定を作成する場合は、**新規 CsConferencingConfiguration**コマンドレットを使用してこれを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="237a0-111">If you need to create custom settings for a site or service, you can do so using the **New-CsConferencingConfiguration** cmdlet.</span></span> <span data-ttu-id="237a0-112">サイトまたはサービス スコープでのみ新しい設定を適用できることに注意してください。構成の設定、会議の新しいグローバル コレクションを作成できませんが、**セット CsConferencingConfiguration**コマンドレットを使用してグローバル コレクションを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="237a0-112">Note that new settings can be applied only at the site or service scope; you cannot create a new global collection of conferencing configuration settings, but you can modify the global collection by using the **Set-CsConferencingConfiguration** cmdlet.</span></span> <span data-ttu-id="237a0-113">さらに、サイトまたはサービスをホストできますなしの設定の 1 つ以上のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="237a0-113">In addition, no site or service can host more than one collection of settings.</span></span> <span data-ttu-id="237a0-114">しようとするとサイトと、レドモンドは、レドモンドの新しい設定を作成するサイトは既にホスト会議構成設定のコレクションから、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="237a0-114">If you try to create new settings for the Redmond site and the Redmond site already hosts a collection of conferencing configuration settings, then your command will fail.</span></span>
  
## <a name="manage-conferencing-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="237a0-115">ビジネス サーバー管理シェルの Skype を使用して、会議構成設定を管理します。</span><span class="sxs-lookup"><span data-stu-id="237a0-115">Manage conferencing configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="237a0-116">Skype ビジネス サーバー管理シェルを使用して会議の構成の設定を管理するには、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="237a0-116">To manage conferencing configuration settings by using Skype for Business Server Management Shell, use the following cmdlets:</span></span>
  
<span data-ttu-id="237a0-117">**電話会議の構成設定**</span><span class="sxs-lookup"><span data-stu-id="237a0-117">**Conferencing configuration settings**</span></span>

|<span data-ttu-id="237a0-118">**コマンドレット**</span><span class="sxs-lookup"><span data-stu-id="237a0-118">**Cmdlet**</span></span>|<span data-ttu-id="237a0-119">**説明**</span><span class="sxs-lookup"><span data-stu-id="237a0-119">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="237a0-120">Get CsConferencingConfiguration</span><span class="sxs-lookup"><span data-stu-id="237a0-120">Get-CsConferencingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csconferencingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="237a0-121">電話会議の構成設定に関する情報を戻します。</span><span class="sxs-lookup"><span data-stu-id="237a0-121">Returns information about the conferencing configuration settings for your organization.</span></span>  <br/> |
|[<span data-ttu-id="237a0-122">新しい-CsConferencingConfiguration</span><span class="sxs-lookup"><span data-stu-id="237a0-122">New-CsConferencingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="237a0-123">電話会議の構成設定の新しいコレクションを作成します。</span><span class="sxs-lookup"><span data-stu-id="237a0-123">Creates a new collection of conferencing configuration settings.</span></span>  <br/> |
|[<span data-ttu-id="237a0-124">削除 CsConferencingConfiguration</span><span class="sxs-lookup"><span data-stu-id="237a0-124">Remove-CsConferencingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="237a0-125">指定した電話会議の構成設定のコレクションを削除します。</span><span class="sxs-lookup"><span data-stu-id="237a0-125">Removes the specified collection of conferencing configuration settings.</span></span>  <br/> |
|[<span data-ttu-id="237a0-126">セット CsConferencingConfiguration</span><span class="sxs-lookup"><span data-stu-id="237a0-126">Set-CsConferencingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="237a0-127">電話会議の構成設定の既存のコレクションを変更します。</span><span class="sxs-lookup"><span data-stu-id="237a0-127">Modifies an existing collection of conferencing configuration settings.</span></span>  <br/> |
   
<span data-ttu-id="237a0-p104">例 1 に示すコマンドは、Redmond サイト (site:Redmond) の会議構成設定の新しいコレクションを作成します。この例には、Organization プロパティの値を Litwareinc に設定するために使用される追加のパラメーター (Organization) が 1 つ含まれています。</span><span class="sxs-lookup"><span data-stu-id="237a0-p104">The following command creates a new collection of conferencing configuration settings for the Redmond site (site:Redmond). In this example, one additional parameter is included (Organization) which is used to set the value of the Organization property to Litwareinc:</span></span> 
  
```
New-CsConferencingConfiguration -Identity site:Redmond -Organization Litwareinc
```

<span data-ttu-id="237a0-130">このようなコレクションは、1 サイトにつき 1 つしか存在できません。Redmond サイトに既に会議構成設定のコレクションがある場合、このコマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="237a0-130">Note that you can have only one such collection per site, so this command would fail if the Redmond site already has a collection of conferencing configuration settings.</span></span> 
  
<span data-ttu-id="237a0-131">次の例では、会議構成設定の新しいコレクションを定義します。これらの構成設定は、最初はメモリ内に格納され、後で Redmond サイトに適用されます。</span><span class="sxs-lookup"><span data-stu-id="237a0-131">The next example defines a new collection of conferencing configuration settings, which are stored in memory initially, and then applied to the Redmond site at a later time.</span></span> 
  
<span data-ttu-id="237a0-p105">最初のコマンドで **New-CsConferencingConfiguration** コマンドレットを使用して、設定に関する新しいメモリ内コレクションを作成し、変数 $x に格納します。InMemory パラメーターを使用して、コレクションを直ちに Redmond サイトに適用する代わりに、メモリ内に作成するように指定します。</span><span class="sxs-lookup"><span data-stu-id="237a0-p105">The first command uses the **New-CsConferencingConfiguration** cmdlet to create a new, in-memory collection of settings stored in the variable $x. The InMemory parameter specifies that the collection should be created in memory rather than immediately applied to the Redmond site.</span></span>
  
<span data-ttu-id="237a0-134">コレクションの作成後、2 番目のコマンドで Organization プロパティの値に Litwareinc を設定しています。</span><span class="sxs-lookup"><span data-stu-id="237a0-134">After the collection has been created, the second command sets the value of the Organization property to Litwareinc.</span></span> 
  
<span data-ttu-id="237a0-135">最後に 3 番目のコマンドで、**Set-CsConferencingConfiguration** コマンドレットを使用して新しい設定を Redmond サイトに実際に適用します。</span><span class="sxs-lookup"><span data-stu-id="237a0-135">Finally, the third command uses the **Set-CsConferencingConfiguration** cmdlet to actually apply the new settings to the Redmond site:</span></span>
  
```
$x = New-CsConferencingConfiguration -Identity site:Redmond -InMemory
$x.Organization = "Litwareinc"
Set-CsConferencingConfiguration -Instance $x
```

<span data-ttu-id="237a0-p106">**Set-CsConferencingConfiguration** コマンドレットを呼び出さない場合、変更は有効になりません。Windows PowerShell セッションの終了後または変数 $x の削除後、すぐに消滅します。</span><span class="sxs-lookup"><span data-stu-id="237a0-p106">If you do not call the **Set-CsConferencingConfiguration** cmdlet, the new settings will never take effect. Instead, they will disappear as soon as you end your Windows PowerShell session or delete the variable $x.</span></span>
  

