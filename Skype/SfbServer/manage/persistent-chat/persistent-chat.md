---
title: Skype for Business Server 2015 での常設チャット サーバーの管理
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c58ee4f4-563b-4d0c-be91-c62df886caa9
description: '概要: ビジネス サーバー 2015 の Skype での永続的なチャット サーバーを管理する方法を説明します。'
ms.openlocfilehash: 294c6bcecbbfb57bb8d2a6a785cdf20775119510
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="manage-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="affb2-103">Skype for Business Server 2015 での常設チャット サーバーの管理</span><span class="sxs-lookup"><span data-stu-id="affb2-103">Manage Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="affb2-104">**の概要:**ビジネス サーバー 2015 の Skype での永続的なチャット サーバーを管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="affb2-104">**Summary:** Learn how to manage Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="affb2-105">組織の永続的なチャット サーバーを設定すると、初期展開時に構成を指定します。</span><span class="sxs-lookup"><span data-stu-id="affb2-105">When you set up Persistent Chat Server for your organization, you specify the initial configuration during deployment.</span></span> <span data-ttu-id="affb2-106">ただし、永続的なチャット サーバーのサポートを実装する方法を変更する場合があります。</span><span class="sxs-lookup"><span data-stu-id="affb2-106">However, there may be times when you want to change how you implement Persistent Chat Server support.</span></span> <span data-ttu-id="affb2-107">などの永続的なチャット サーバーのサポートと、特定のチームまたは組織内のグループに異なるコントロールを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="affb2-107">For example you may need to set up Persistent Chat Server support and controls differently for a specific team or group within your organization.</span></span> <span data-ttu-id="affb2-108">このセクションでは、情報と、永続的なチャット サーバーの展開をカスタマイズするための手順を提供します。</span><span class="sxs-lookup"><span data-stu-id="affb2-108">This section provides information and procedures to help you customize your Persistent Chat Server deployment.</span></span> <span data-ttu-id="affb2-109">永続的なチャット サーバーの構成可能な機能に関する詳細については、[ビジネス サーバー 2015 の Skype での永続的なチャット サーバーの計画](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="affb2-109">For details about the features and functionality that you can configure for Persistent Chat Server, see [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).</span></span> <span data-ttu-id="affb2-110">永続的なチャット サーバーの展開に関する詳細については、[ビジネス サーバー 2015 の Skype での永続的なのチャット サーバーの展開](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="affb2-110">For details about deploying Persistent Chat Server, see [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md).</span></span> 
  
<span data-ttu-id="affb2-111">コントロール パネルを使用するか、Windows PowerShell コマンドレットを使用して、永続的なチャット サーバーを管理できます。</span><span class="sxs-lookup"><span data-stu-id="affb2-111">You can manage Persistent Chat Server by using the Control Panel or by using Windows PowerShell cmdlets.</span></span> 
  
<span data-ttu-id="affb2-112">コントロール パネルを使用するには</span><span class="sxs-lookup"><span data-stu-id="affb2-112">To use the Control Panel:</span></span>
  
1. <span data-ttu-id="affb2-113">CsPersistentChatAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="affb2-113">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="affb2-114">**[スタート**] メニューから、Skype ビジネス サーバーのコントロール パネルのまたはブラウザー ウィンドウを開きし、管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="affb2-114">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="affb2-115">左側のナビゲーション ・ バーでは、**永続的なチャット**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="affb2-115">In the left navigation bar, click **Persistent Chat**.</span></span>
    
<span data-ttu-id="affb2-116">次の表は、永続的なチャット サーバーを管理するために利用可能な Windows PowerShell コマンドレットをまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="affb2-116">The following table summarizes the Windows PowerShell cmdlets available to help you manage Persistent Chat Server.</span></span> <span data-ttu-id="affb2-117">などのすべての利用可能なパラメーターの構文の詳細については、 [Skype ビジネス サーバー 2015 管理シェルに](../management-shell.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="affb2-117">For details about syntax, including all available parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="affb2-118">**コマンドレット**</span><span class="sxs-lookup"><span data-stu-id="affb2-118">**Cmdlet**</span></span>|<span data-ttu-id="affb2-119">**説明**</span><span class="sxs-lookup"><span data-stu-id="affb2-119">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="affb2-120">新しい-CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="affb2-120">New-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="affb2-121">新しいカテゴリを作成する</span><span class="sxs-lookup"><span data-stu-id="affb2-121">Creates a new category</span></span>  <br/> |
|<span data-ttu-id="affb2-122">セット CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="affb2-122">Set-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="affb2-123">既存のカテゴリの設定を構成する</span><span class="sxs-lookup"><span data-stu-id="affb2-123">Configures settings for an existing category</span></span>  <br/> |
|<span data-ttu-id="affb2-124">Get CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="affb2-124">Get-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="affb2-125">カテゴリに関する情報を取得する</span><span class="sxs-lookup"><span data-stu-id="affb2-125">Retrieves information about categories</span></span>  <br/> |
|<span data-ttu-id="affb2-126">削除 CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="affb2-126">Remove-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="affb2-127">カテゴリを削除する</span><span class="sxs-lookup"><span data-stu-id="affb2-127">Removes a category</span></span>  <br/> |
|<span data-ttu-id="affb2-128">新しい-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="affb2-128">New-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="affb2-129">新しいチャット ルームを作成する</span><span class="sxs-lookup"><span data-stu-id="affb2-129">Creates a new chat room</span></span>  <br/> |
|<span data-ttu-id="affb2-130">セット CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="affb2-130">Set-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="affb2-131">既存のルームの設定を構成し、ユーザーおよびユーザー グループをルームに割り当てる</span><span class="sxs-lookup"><span data-stu-id="affb2-131">Configures settings for an existing room; assign users and user groups to the room</span></span>  <br/> |
|<span data-ttu-id="affb2-132">Get CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="affb2-132">Get-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="affb2-133">ルームについての情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="affb2-133">Retrieves information about rooms</span></span>  <br/> |
|<span data-ttu-id="affb2-134">クリア CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="affb2-134">Clear-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="affb2-135">ルームをクリアするか、またはルームからメッセージをクリアする</span><span class="sxs-lookup"><span data-stu-id="affb2-135">Clears a room or messages from a room</span></span>  <br/> |
|<span data-ttu-id="affb2-136">削除 CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="affb2-136">Remove-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="affb2-137">ルームを削除する</span><span class="sxs-lookup"><span data-stu-id="affb2-137">Removes a room</span></span>  <br/> |
|<span data-ttu-id="affb2-138">削除 CsPersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="affb2-138">Remove-CsPersistentChatMessage</span></span>  <br/> |<span data-ttu-id="affb2-139">ルームからメッセージを削除する</span><span class="sxs-lookup"><span data-stu-id="affb2-139">Removes messages from a room</span></span>  <br/> |
|<span data-ttu-id="affb2-140">新しい-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="affb2-140">New-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="affb2-141">新しいアドインを作成する</span><span class="sxs-lookup"><span data-stu-id="affb2-141">Creates a new add-in</span></span>  <br/> |
|<span data-ttu-id="affb2-142">セット CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="affb2-142">Set-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="affb2-143">既存のアドインの設定を構成する</span><span class="sxs-lookup"><span data-stu-id="affb2-143">Configures settings for an existing add-in</span></span>  <br/> |
|<span data-ttu-id="affb2-144">Get CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="affb2-144">Get-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="affb2-145">アドインに関する情報を取得する</span><span class="sxs-lookup"><span data-stu-id="affb2-145">Retrieves information about add-ins</span></span>  <br/> |
|<span data-ttu-id="affb2-146">削除 CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="affb2-146">Remove-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="affb2-147">アドインを削除する</span><span class="sxs-lookup"><span data-stu-id="affb2-147">Removes an add-in</span></span>  <br/> |
|<span data-ttu-id="affb2-148">セット CsPersistentChatComplianceConfiguration</span><span class="sxs-lookup"><span data-stu-id="affb2-148">Set-CsPersistentChatComplianceConfiguration</span></span>  <br/> |<span data-ttu-id="affb2-149">コンプライアンス構成設定の既存のコレクションを変更する</span><span class="sxs-lookup"><span data-stu-id="affb2-149">Modifies an existing collection of compliance configuration settings</span></span>  <br/> |
|<span data-ttu-id="affb2-150">エクスポート CsPersistentChatData</span><span class="sxs-lookup"><span data-stu-id="affb2-150">Export-CsPersistentChatData</span></span>  <br/> |<span data-ttu-id="affb2-151">常設チャット データベースからデータをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="affb2-151">Exports data from a Persistent Chat database</span></span>  <br/> |
|<span data-ttu-id="affb2-152">インポート-CsPersistentChatData</span><span class="sxs-lookup"><span data-stu-id="affb2-152">Import-CsPersistentChatData</span></span>  <br/> |<span data-ttu-id="affb2-153">以前のバージョンの Lync Server からエクスポートされたデータをインポートする</span><span class="sxs-lookup"><span data-stu-id="affb2-153">Imports data that was exported from a previous version of Lync Server</span></span>  <br/> |
   

