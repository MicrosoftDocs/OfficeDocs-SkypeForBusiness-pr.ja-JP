---
title: Skype for Business Server 2015 での常設チャット サーバーの管理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c58ee4f4-563b-4d0c-be91-c62df886caa9
description: '概要: Skype for Business Server 2015 で常設チャットサーバーを管理する方法について説明します。'
ms.openlocfilehash: 97cce8adedbb4dea932084497006e3c17bfdd7d8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817323"
---
# <a name="manage-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="a6a3c-103">Skype for Business Server 2015 での常設チャット サーバーの管理</span><span class="sxs-lookup"><span data-stu-id="a6a3c-103">Manage Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="a6a3c-104">**概要:** Skype for Business Server 2015 で常設チャットサーバーを管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a6a3c-104">**Summary:** Learn how to manage Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="a6a3c-105">組織に常設チャットサーバーを設定する場合は、展開時に初期構成を指定します。</span><span class="sxs-lookup"><span data-stu-id="a6a3c-105">When you set up Persistent Chat Server for your organization, you specify the initial configuration during deployment.</span></span> <span data-ttu-id="a6a3c-106">ただし、常設チャットサーバーサポートの実装方法を変更する必要がある場合もあります。</span><span class="sxs-lookup"><span data-stu-id="a6a3c-106">However, there may be times when you want to change how you implement Persistent Chat Server support.</span></span> <span data-ttu-id="a6a3c-107">たとえば、組織内の特定のチームまたはグループに対して、常設チャットサーバーのサポートとコントロールを設定する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="a6a3c-107">For example you may need to set up Persistent Chat Server support and controls differently for a specific team or group within your organization.</span></span> <span data-ttu-id="a6a3c-108">このセクションには、常設チャットサーバーの展開をカスタマイズするための情報と手順が記載されています。</span><span class="sxs-lookup"><span data-stu-id="a6a3c-108">This section provides information and procedures to help you customize your Persistent Chat Server deployment.</span></span> <span data-ttu-id="a6a3c-109">常設チャットサーバー用に構成できる機能の詳細については、「 [Skype For Business server 2015 での常設チャットサーバーの計画](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6a3c-109">For details about the features and functionality that you can configure for Persistent Chat Server, see [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).</span></span> <span data-ttu-id="a6a3c-110">常設チャットサーバーの展開について詳しくは、「 [Skype For Business server 2015 での常設チャットサーバーの展開](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a6a3c-110">For details about deploying Persistent Chat Server, see [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md).</span></span> 

> [!NOTE]
> <span data-ttu-id="a6a3c-111">常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="a6a3c-111">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="a6a3c-112">Teams でも同じ機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a6a3c-112">The same functionality is available in Teams.</span></span> <span data-ttu-id="a6a3c-113">詳細については、「 [Microsoft Teams のアップグレードの](/microsoftteams/upgrade-start-here)概要」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6a3c-113">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="a6a3c-114">常設チャットを使用する必要がある場合は、この機能が必要なユーザーをチームに移行するか、Skype for Business Server 2015 を使い続けるかのいずれかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="a6a3c-114">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
  
<span data-ttu-id="a6a3c-115">常設チャットサーバーを管理するには、コントロールパネルを使用するか、Windows PowerShell コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="a6a3c-115">You can manage Persistent Chat Server by using the Control Panel or by using Windows PowerShell cmdlets.</span></span> 
  
<span data-ttu-id="a6a3c-116">コントロール パネルを使用するには</span><span class="sxs-lookup"><span data-stu-id="a6a3c-116">To use the Control Panel:</span></span>
  
1. <span data-ttu-id="a6a3c-117">CsPersistentChatAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="a6a3c-117">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="a6a3c-118">[**スタート**] メニューで、[Skype For business Server] コントロールパネルを選択するか、ブラウザーウィンドウを開き、管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="a6a3c-118">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="a6a3c-119">左側のナビゲーションバーで、[**常設チャット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6a3c-119">In the left navigation bar, click **Persistent Chat**.</span></span>
    
<span data-ttu-id="a6a3c-120">次の表は、常設チャットサーバーを管理するために使用できる Windows PowerShell コマンドレットをまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="a6a3c-120">The following table summarizes the Windows PowerShell cmdlets available to help you manage Persistent Chat Server.</span></span> <span data-ttu-id="a6a3c-121">使用できるすべてのパラメーターを含む構文の詳細については、「[Skype for Business Server 2015 Management Shell](../management-shell.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6a3c-121">For details about syntax, including all available parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="a6a3c-122">**コマンドレット**</span><span class="sxs-lookup"><span data-stu-id="a6a3c-122">**Cmdlet**</span></span>|<span data-ttu-id="a6a3c-123">**説明**</span><span class="sxs-lookup"><span data-stu-id="a6a3c-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a6a3c-124">New-CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="a6a3c-124">New-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="a6a3c-125">新しいカテゴリを作成する</span><span class="sxs-lookup"><span data-stu-id="a6a3c-125">Creates a new category</span></span>  <br/> |
|<span data-ttu-id="a6a3c-126">Set-CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="a6a3c-126">Set-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="a6a3c-127">既存のカテゴリの設定を構成する</span><span class="sxs-lookup"><span data-stu-id="a6a3c-127">Configures settings for an existing category</span></span>  <br/> |
|<span data-ttu-id="a6a3c-128">Get-CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="a6a3c-128">Get-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="a6a3c-129">カテゴリに関する情報を取得する</span><span class="sxs-lookup"><span data-stu-id="a6a3c-129">Retrieves information about categories</span></span>  <br/> |
|<span data-ttu-id="a6a3c-130">Remove-CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="a6a3c-130">Remove-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="a6a3c-131">カテゴリを削除する</span><span class="sxs-lookup"><span data-stu-id="a6a3c-131">Removes a category</span></span>  <br/> |
|<span data-ttu-id="a6a3c-132">New-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="a6a3c-132">New-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="a6a3c-133">新しいチャット ルームを作成する</span><span class="sxs-lookup"><span data-stu-id="a6a3c-133">Creates a new chat room</span></span>  <br/> |
|<span data-ttu-id="a6a3c-134">Set-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="a6a3c-134">Set-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="a6a3c-135">既存のルームの設定を構成し、ユーザーおよびユーザー グループをルームに割り当てる</span><span class="sxs-lookup"><span data-stu-id="a6a3c-135">Configures settings for an existing room; assign users and user groups to the room</span></span>  <br/> |
|<span data-ttu-id="a6a3c-136">Get-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="a6a3c-136">Get-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="a6a3c-137">会議室に関する情報を取得します</span><span class="sxs-lookup"><span data-stu-id="a6a3c-137">Retrieves information about rooms</span></span>  <br/> |
|<span data-ttu-id="a6a3c-138">Clear-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="a6a3c-138">Clear-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="a6a3c-139">ルームをクリアするか、またはルームからメッセージをクリアする</span><span class="sxs-lookup"><span data-stu-id="a6a3c-139">Clears a room or messages from a room</span></span>  <br/> |
|<span data-ttu-id="a6a3c-140">Remove-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="a6a3c-140">Remove-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="a6a3c-141">ルームを削除する</span><span class="sxs-lookup"><span data-stu-id="a6a3c-141">Removes a room</span></span>  <br/> |
|<span data-ttu-id="a6a3c-142">Remove-CsPersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="a6a3c-142">Remove-CsPersistentChatMessage</span></span>  <br/> |<span data-ttu-id="a6a3c-143">ルームからメッセージを削除する</span><span class="sxs-lookup"><span data-stu-id="a6a3c-143">Removes messages from a room</span></span>  <br/> |
|<span data-ttu-id="a6a3c-144">New-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="a6a3c-144">New-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="a6a3c-145">新しいアドインを作成する</span><span class="sxs-lookup"><span data-stu-id="a6a3c-145">Creates a new add-in</span></span>  <br/> |
|<span data-ttu-id="a6a3c-146">Set-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="a6a3c-146">Set-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="a6a3c-147">既存のアドインの設定を構成する</span><span class="sxs-lookup"><span data-stu-id="a6a3c-147">Configures settings for an existing add-in</span></span>  <br/> |
|<span data-ttu-id="a6a3c-148">Get-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="a6a3c-148">Get-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="a6a3c-149">アドインに関する情報を取得する</span><span class="sxs-lookup"><span data-stu-id="a6a3c-149">Retrieves information about add-ins</span></span>  <br/> |
|<span data-ttu-id="a6a3c-150">Remove-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="a6a3c-150">Remove-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="a6a3c-151">アドインを削除する</span><span class="sxs-lookup"><span data-stu-id="a6a3c-151">Removes an add-in</span></span>  <br/> |
|<span data-ttu-id="a6a3c-152">Set-CsPersistentChatComplianceConfiguration</span><span class="sxs-lookup"><span data-stu-id="a6a3c-152">Set-CsPersistentChatComplianceConfiguration</span></span>  <br/> |<span data-ttu-id="a6a3c-153">コンプライアンス構成設定の既存のコレクションを変更する</span><span class="sxs-lookup"><span data-stu-id="a6a3c-153">Modifies an existing collection of compliance configuration settings</span></span>  <br/> |
|<span data-ttu-id="a6a3c-154">Export-CsPersistentChatData</span><span class="sxs-lookup"><span data-stu-id="a6a3c-154">Export-CsPersistentChatData</span></span>  <br/> |<span data-ttu-id="a6a3c-155">常設チャット データベースからデータをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="a6a3c-155">Exports data from a Persistent Chat database</span></span>  <br/> |
|<span data-ttu-id="a6a3c-156">Import-CsPersistentChatData</span><span class="sxs-lookup"><span data-stu-id="a6a3c-156">Import-CsPersistentChatData</span></span>  <br/> |<span data-ttu-id="a6a3c-157">以前のバージョンの Lync Server からエクスポートされたデータをインポートする</span><span class="sxs-lookup"><span data-stu-id="a6a3c-157">Imports data that was exported from a previous version of Lync Server</span></span>  <br/> |
   

