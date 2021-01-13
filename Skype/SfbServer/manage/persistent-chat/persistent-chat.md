---
title: Skype for Business Server 2015 での常設チャット サーバーの管理
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c58ee4f4-563b-4d0c-be91-c62df886caa9
description: '概要: Skype for Business Server 2015 で常設チャット サーバーを管理する方法について学習します。'
ms.openlocfilehash: 9a97511f9b4c2adae7ead816e86876f05dd39790
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832887"
---
# <a name="manage-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="20b0a-103">Skype for Business Server 2015 での常設チャット サーバーの管理</span><span class="sxs-lookup"><span data-stu-id="20b0a-103">Manage Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="20b0a-104">**概要:** Skype for Business Server 2015 で常設チャット サーバーを管理する方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="20b0a-104">**Summary:** Learn how to manage Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="20b0a-105">組織の常設チャット サーバーをセットアップするときに、展開時に初期構成を指定します。</span><span class="sxs-lookup"><span data-stu-id="20b0a-105">When you set up Persistent Chat Server for your organization, you specify the initial configuration during deployment.</span></span> <span data-ttu-id="20b0a-106">ただし、常設チャット サーバーのサポートの実装方法を変更する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="20b0a-106">However, there may be times when you want to change how you implement Persistent Chat Server support.</span></span> <span data-ttu-id="20b0a-107">たとえば、組織内の特定のチームまたはグループに対して、常設チャット サーバーのサポートと制御を異なる方法で設定する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="20b0a-107">For example you may need to set up Persistent Chat Server support and controls differently for a specific team or group within your organization.</span></span> <span data-ttu-id="20b0a-108">このセクションでは、常設チャット サーバーの展開をカスタマイズするための情報と手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="20b0a-108">This section provides information and procedures to help you customize your Persistent Chat Server deployment.</span></span> <span data-ttu-id="20b0a-109">常設チャット サーバー用に構成できる機能の詳細については [、「Plan for Persistent Chat Server in Skype for Business Server 2015」](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="20b0a-109">For details about the features and functionality that you can configure for Persistent Chat Server, see [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).</span></span> <span data-ttu-id="20b0a-110">常設チャット サーバーの展開の詳細については [、「Deploy Persistent Chat Server in Skype for Business Server 2015」](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="20b0a-110">For details about deploying Persistent Chat Server, see [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md).</span></span> 

> [!NOTE]
> <span data-ttu-id="20b0a-111">常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="20b0a-111">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="20b0a-112">Teams でも同じ機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="20b0a-112">The same functionality is available in Teams.</span></span> <span data-ttu-id="20b0a-113">詳細については、「Microsoft Teams のアップグレード [の開始」を参照してください](/microsoftteams/upgrade-start-here)。</span><span class="sxs-lookup"><span data-stu-id="20b0a-113">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="20b0a-114">常設チャットを使用する必要がある場合は、この機能を必要とするユーザーを Teams に移行するか、Skype for Business Server 2015 を引き続き使用するかのどちらかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="20b0a-114">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
  
<span data-ttu-id="20b0a-115">常設チャット サーバーは、コントロール パネルを使用するか、または次のコマンドレットをWindows PowerShellできます。</span><span class="sxs-lookup"><span data-stu-id="20b0a-115">You can manage Persistent Chat Server by using the Control Panel or by using Windows PowerShell cmdlets.</span></span> 
  
<span data-ttu-id="20b0a-116">コントロール パネルを使用するには:</span><span class="sxs-lookup"><span data-stu-id="20b0a-116">To use the Control Panel:</span></span>
  
1. <span data-ttu-id="20b0a-117">CsPersistentChatAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="20b0a-117">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="20b0a-118">[スタート **] メニューから** Skype for Business Server コントロール パネルを選択するか、ブラウザー ウィンドウを開いて管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="20b0a-118">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="20b0a-119">左側のナビゲーション バーで、[常設チャット] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="20b0a-119">In the left navigation bar, click **Persistent Chat**.</span></span>
    
<span data-ttu-id="20b0a-120">次の表に、常設チャット Windows PowerShell管理に使用できるすべてのコマンドレットの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="20b0a-120">The following table summarizes the Windows PowerShell cmdlets available to help you manage Persistent Chat Server.</span></span> <span data-ttu-id="20b0a-121">使用可能なすべてのパラメーターを含む構文の詳細については [、Skype for Business Server 2015 管理シェルを参照してください](../management-shell.md)。</span><span class="sxs-lookup"><span data-stu-id="20b0a-121">For details about syntax, including all available parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="20b0a-122">**コマンドレット**</span><span class="sxs-lookup"><span data-stu-id="20b0a-122">**Cmdlet**</span></span>|<span data-ttu-id="20b0a-123">**説明**</span><span class="sxs-lookup"><span data-stu-id="20b0a-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="20b0a-124">New-CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="20b0a-124">New-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="20b0a-125">新しいカテゴリを作成します。</span><span class="sxs-lookup"><span data-stu-id="20b0a-125">Creates a new category</span></span>  <br/> |
|<span data-ttu-id="20b0a-126">Set-CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="20b0a-126">Set-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="20b0a-127">既存のカテゴリの設定を構成します</span><span class="sxs-lookup"><span data-stu-id="20b0a-127">Configures settings for an existing category</span></span>  <br/> |
|<span data-ttu-id="20b0a-128">Get-CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="20b0a-128">Get-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="20b0a-129">カテゴリに関する情報を取得します</span><span class="sxs-lookup"><span data-stu-id="20b0a-129">Retrieves information about categories</span></span>  <br/> |
|<span data-ttu-id="20b0a-130">Remove-CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="20b0a-130">Remove-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="20b0a-131">カテゴリを削除します</span><span class="sxs-lookup"><span data-stu-id="20b0a-131">Removes a category</span></span>  <br/> |
|<span data-ttu-id="20b0a-132">New-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="20b0a-132">New-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="20b0a-133">新しいチャット ルームを作成します</span><span class="sxs-lookup"><span data-stu-id="20b0a-133">Creates a new chat room</span></span>  <br/> |
|<span data-ttu-id="20b0a-134">Set-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="20b0a-134">Set-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="20b0a-135">既存のルームの設定を構成します。ユーザーとユーザー グループをルームに割り当てる</span><span class="sxs-lookup"><span data-stu-id="20b0a-135">Configures settings for an existing room; assign users and user groups to the room</span></span>  <br/> |
|<span data-ttu-id="20b0a-136">Get-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="20b0a-136">Get-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="20b0a-137">ルームに関する情報を取得します</span><span class="sxs-lookup"><span data-stu-id="20b0a-137">Retrieves information about rooms</span></span>  <br/> |
|<span data-ttu-id="20b0a-138">Clear-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="20b0a-138">Clear-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="20b0a-139">ルームまたはメッセージをルームからクリアします</span><span class="sxs-lookup"><span data-stu-id="20b0a-139">Clears a room or messages from a room</span></span>  <br/> |
|<span data-ttu-id="20b0a-140">Remove-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="20b0a-140">Remove-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="20b0a-141">ルームを削除します</span><span class="sxs-lookup"><span data-stu-id="20b0a-141">Removes a room</span></span>  <br/> |
|<span data-ttu-id="20b0a-142">Remove-CsPersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="20b0a-142">Remove-CsPersistentChatMessage</span></span>  <br/> |<span data-ttu-id="20b0a-143">ルームからメッセージを削除します</span><span class="sxs-lookup"><span data-stu-id="20b0a-143">Removes messages from a room</span></span>  <br/> |
|<span data-ttu-id="20b0a-144">New-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="20b0a-144">New-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="20b0a-145">新しいアドインを作成します。</span><span class="sxs-lookup"><span data-stu-id="20b0a-145">Creates a new add-in</span></span>  <br/> |
|<span data-ttu-id="20b0a-146">Set-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="20b0a-146">Set-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="20b0a-147">既存のアドインの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="20b0a-147">Configures settings for an existing add-in</span></span>  <br/> |
|<span data-ttu-id="20b0a-148">Get-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="20b0a-148">Get-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="20b0a-149">アドインに関する情報を取得します</span><span class="sxs-lookup"><span data-stu-id="20b0a-149">Retrieves information about add-ins</span></span>  <br/> |
|<span data-ttu-id="20b0a-150">Remove-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="20b0a-150">Remove-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="20b0a-151">アドインを削除します</span><span class="sxs-lookup"><span data-stu-id="20b0a-151">Removes an add-in</span></span>  <br/> |
|<span data-ttu-id="20b0a-152">Set-CsPersistentChatComplianceConfiguration</span><span class="sxs-lookup"><span data-stu-id="20b0a-152">Set-CsPersistentChatComplianceConfiguration</span></span>  <br/> |<span data-ttu-id="20b0a-153">コンプライアンス構成設定の既存のコレクションを変更します</span><span class="sxs-lookup"><span data-stu-id="20b0a-153">Modifies an existing collection of compliance configuration settings</span></span>  <br/> |
|<span data-ttu-id="20b0a-154">Export-CsPersistentChatData</span><span class="sxs-lookup"><span data-stu-id="20b0a-154">Export-CsPersistentChatData</span></span>  <br/> |<span data-ttu-id="20b0a-155">常設チャット データベースからデータをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="20b0a-155">Exports data from a Persistent Chat database</span></span>  <br/> |
|<span data-ttu-id="20b0a-156">Import-CsPersistentChatData</span><span class="sxs-lookup"><span data-stu-id="20b0a-156">Import-CsPersistentChatData</span></span>  <br/> |<span data-ttu-id="20b0a-157">以前のバージョンの Lync Server からエクスポートされたデータをインポートします。</span><span class="sxs-lookup"><span data-stu-id="20b0a-157">Imports data that was exported from a previous version of Lync Server</span></span>  <br/> |
   

