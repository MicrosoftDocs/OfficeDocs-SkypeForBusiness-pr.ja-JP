---
title: Skype for Business Server 2015 での常設チャット サーバーの管理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c58ee4f4-563b-4d0c-be91-c62df886caa9
description: '概要: ビジネス サーバー 2015 の Skype での永続的なチャット サーバーを管理する方法を説明します。'
ms.openlocfilehash: 27405be6d209089c670aa117838e959bae64d9e5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33910222"
---
# <a name="manage-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="0d743-103">Skype for Business Server 2015 での常設チャット サーバーの管理</span><span class="sxs-lookup"><span data-stu-id="0d743-103">Manage Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="0d743-104">**の概要:** ビジネス サーバー 2015 の Skype での永続的なチャット サーバーを管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0d743-104">**Summary:** Learn how to manage Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="0d743-105">組織の永続的なチャット サーバーを設定すると、初期展開時に構成を指定します。</span><span class="sxs-lookup"><span data-stu-id="0d743-105">When you set up Persistent Chat Server for your organization, you specify the initial configuration during deployment.</span></span> <span data-ttu-id="0d743-106">ただし、永続的なチャット サーバーのサポートを実装する方法を変更する場合があります。</span><span class="sxs-lookup"><span data-stu-id="0d743-106">However, there may be times when you want to change how you implement Persistent Chat Server support.</span></span> <span data-ttu-id="0d743-107">などの永続的なチャット サーバーのサポートと、特定のチームまたは組織内のグループに異なるコントロールを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d743-107">For example you may need to set up Persistent Chat Server support and controls differently for a specific team or group within your organization.</span></span> <span data-ttu-id="0d743-108">このセクションでは、情報と、永続的なチャット サーバーの展開をカスタマイズするための手順を提供します。</span><span class="sxs-lookup"><span data-stu-id="0d743-108">This section provides information and procedures to help you customize your Persistent Chat Server deployment.</span></span> <span data-ttu-id="0d743-109">永続的なチャット サーバーの構成可能な機能に関する詳細については、[ビジネス サーバー 2015 の Skype での永続的なチャット サーバーの計画](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d743-109">For details about the features and functionality that you can configure for Persistent Chat Server, see [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).</span></span> <span data-ttu-id="0d743-110">永続的なチャット サーバーの展開に関する詳細については、[ビジネス サーバー 2015 の Skype での永続的なのチャット サーバーの展開](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d743-110">For details about deploying Persistent Chat Server, see [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md).</span></span> 

> [!NOTE]
> <span data-ttu-id="0d743-111">永続的なチャットですがビジネス サーバー 2015 の Skype で利用可能なビジネス サーバー 2019 の Skype でサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="0d743-111">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="0d743-112">同じ機能は、チームで使用できます。</span><span class="sxs-lookup"><span data-stu-id="0d743-112">The same functionality is available in Teams.</span></span> <span data-ttu-id="0d743-113">詳細については、[マイクロソフトのチームにビジネス用の Skype からの旅](/microsoftteams/journey-skypeforbusiness-teams)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d743-113">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="0d743-114">永続的なチャットを使用する場合は、選択肢は、いずれかをチームでは、この機能を必要とするユーザーを移行するまたはビジネス サーバー 2015 の Skype を使用し続ける。</span><span class="sxs-lookup"><span data-stu-id="0d743-114">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
  
<span data-ttu-id="0d743-115">コントロール パネルを使用するか、Windows PowerShell コマンドレットを使用して、永続的なチャット サーバーを管理できます。</span><span class="sxs-lookup"><span data-stu-id="0d743-115">You can manage Persistent Chat Server by using the Control Panel or by using Windows PowerShell cmdlets.</span></span> 
  
<span data-ttu-id="0d743-116">コントロール パネルを使用するには</span><span class="sxs-lookup"><span data-stu-id="0d743-116">To use the Control Panel:</span></span>
  
1. <span data-ttu-id="0d743-117">CsPersistentChatAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="0d743-117">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="0d743-118">**[スタート**] メニューから、Skype ビジネス サーバーのコントロール パネルのまたはブラウザー ウィンドウを開きし、管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="0d743-118">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="0d743-119">左側のナビゲーション ・ バーでは、**永続的なチャット**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0d743-119">In the left navigation bar, click **Persistent Chat**.</span></span>
    
<span data-ttu-id="0d743-120">次の表は、永続的なチャット サーバーを管理するために利用可能な Windows PowerShell コマンドレットをまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="0d743-120">The following table summarizes the Windows PowerShell cmdlets available to help you manage Persistent Chat Server.</span></span> <span data-ttu-id="0d743-121">使用できるすべてのパラメーターを含む構文の詳細については、「[Skype for Business Server 2015 Management Shell](../management-shell.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d743-121">For details about syntax, including all available parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="0d743-122">**コマンドレット**</span><span class="sxs-lookup"><span data-stu-id="0d743-122">**Cmdlet**</span></span>|<span data-ttu-id="0d743-123">**説明**</span><span class="sxs-lookup"><span data-stu-id="0d743-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0d743-124">New-CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="0d743-124">New-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="0d743-125">新しいカテゴリを作成する</span><span class="sxs-lookup"><span data-stu-id="0d743-125">Creates a new category</span></span>  <br/> |
|<span data-ttu-id="0d743-126">Set-CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="0d743-126">Set-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="0d743-127">既存のカテゴリの設定を構成する</span><span class="sxs-lookup"><span data-stu-id="0d743-127">Configures settings for an existing category</span></span>  <br/> |
|<span data-ttu-id="0d743-128">Get-CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="0d743-128">Get-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="0d743-129">カテゴリに関する情報を取得する</span><span class="sxs-lookup"><span data-stu-id="0d743-129">Retrieves information about categories</span></span>  <br/> |
|<span data-ttu-id="0d743-130">Remove-CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="0d743-130">Remove-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="0d743-131">カテゴリを削除する</span><span class="sxs-lookup"><span data-stu-id="0d743-131">Removes a category</span></span>  <br/> |
|<span data-ttu-id="0d743-132">New-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="0d743-132">New-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="0d743-133">新しいチャット ルームを作成する</span><span class="sxs-lookup"><span data-stu-id="0d743-133">Creates a new chat room</span></span>  <br/> |
|<span data-ttu-id="0d743-134">Set-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="0d743-134">Set-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="0d743-135">既存のルームの設定を構成し、ユーザーおよびユーザー グループをルームに割り当てる</span><span class="sxs-lookup"><span data-stu-id="0d743-135">Configures settings for an existing room; assign users and user groups to the room</span></span>  <br/> |
|<span data-ttu-id="0d743-136">Get-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="0d743-136">Get-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="0d743-137">ルームについての情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="0d743-137">Retrieves information about rooms</span></span>  <br/> |
|<span data-ttu-id="0d743-138">Clear-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="0d743-138">Clear-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="0d743-139">ルームをクリアするか、またはルームからメッセージをクリアする</span><span class="sxs-lookup"><span data-stu-id="0d743-139">Clears a room or messages from a room</span></span>  <br/> |
|<span data-ttu-id="0d743-140">Remove-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="0d743-140">Remove-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="0d743-141">ルームを削除する</span><span class="sxs-lookup"><span data-stu-id="0d743-141">Removes a room</span></span>  <br/> |
|<span data-ttu-id="0d743-142">Remove-CsPersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="0d743-142">Remove-CsPersistentChatMessage</span></span>  <br/> |<span data-ttu-id="0d743-143">ルームからメッセージを削除する</span><span class="sxs-lookup"><span data-stu-id="0d743-143">Removes messages from a room</span></span>  <br/> |
|<span data-ttu-id="0d743-144">New-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="0d743-144">New-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="0d743-145">新しいアドインを作成する</span><span class="sxs-lookup"><span data-stu-id="0d743-145">Creates a new add-in</span></span>  <br/> |
|<span data-ttu-id="0d743-146">Set-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="0d743-146">Set-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="0d743-147">既存のアドインの設定を構成する</span><span class="sxs-lookup"><span data-stu-id="0d743-147">Configures settings for an existing add-in</span></span>  <br/> |
|<span data-ttu-id="0d743-148">Get-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="0d743-148">Get-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="0d743-149">アドインに関する情報を取得する</span><span class="sxs-lookup"><span data-stu-id="0d743-149">Retrieves information about add-ins</span></span>  <br/> |
|<span data-ttu-id="0d743-150">Remove-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="0d743-150">Remove-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="0d743-151">アドインを削除する</span><span class="sxs-lookup"><span data-stu-id="0d743-151">Removes an add-in</span></span>  <br/> |
|<span data-ttu-id="0d743-152">Set-CsPersistentChatComplianceConfiguration</span><span class="sxs-lookup"><span data-stu-id="0d743-152">Set-CsPersistentChatComplianceConfiguration</span></span>  <br/> |<span data-ttu-id="0d743-153">コンプライアンス構成設定の既存のコレクションを変更する</span><span class="sxs-lookup"><span data-stu-id="0d743-153">Modifies an existing collection of compliance configuration settings</span></span>  <br/> |
|<span data-ttu-id="0d743-154">Export-CsPersistentChatData</span><span class="sxs-lookup"><span data-stu-id="0d743-154">Export-CsPersistentChatData</span></span>  <br/> |<span data-ttu-id="0d743-155">常設チャット データベースからデータをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="0d743-155">Exports data from a Persistent Chat database</span></span>  <br/> |
|<span data-ttu-id="0d743-156">Import-CsPersistentChatData</span><span class="sxs-lookup"><span data-stu-id="0d743-156">Import-CsPersistentChatData</span></span>  <br/> |<span data-ttu-id="0d743-157">以前のバージョンの Lync Server からエクスポートされたデータをインポートする</span><span class="sxs-lookup"><span data-stu-id="0d743-157">Imports data that was exported from a previous version of Lync Server</span></span>  <br/> |
   

