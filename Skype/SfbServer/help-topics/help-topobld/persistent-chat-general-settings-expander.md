---
title: 常設チャット全般設定の展開
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PersistentChatGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 275ee1ae-ca58-4963-bc95-523319f90d96
description: 次のプロパティを構成または定義することによって、常設チャットサーバーまたは常設チャットサーバープールの全般設定を編集します。
ms.openlocfilehash: aae63b2d736f02b717b47aeff5fccb9b676daf99
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215998"
---
# <a name="persistent-chat-general-settings-expander"></a><span data-ttu-id="29fb8-103">常設チャット全般設定の展開</span><span class="sxs-lookup"><span data-stu-id="29fb8-103">Persistent Chat General Settings Expander</span></span>
 
<span data-ttu-id="29fb8-104">次のプロパティを構成または定義することによって、常設チャットサーバーまたは常設チャットサーバープールの **全般** 設定を編集します。</span><span class="sxs-lookup"><span data-stu-id="29fb8-104">You edit the **General** settings for the Persistent Chat Server or Persistent Chat Server pool by configuring or defining these properties:</span></span>
  
 <span data-ttu-id="29fb8-105">**全般**</span><span class="sxs-lookup"><span data-stu-id="29fb8-105">**General**</span></span>
  
- <span data-ttu-id="29fb8-106">[ **FQDN**]: この設定を編集して、常設チャットサーバーまたは常設チャットサーバープールの完全修飾ドメイン名を定義します。</span><span class="sxs-lookup"><span data-stu-id="29fb8-106">**FQDN**: Edit this setting to define the fully qualified domain name of your Persistent Chat Server or Persistent Chat Server pool</span></span>
    
- <span data-ttu-id="29fb8-107">[**常設チャット プールの名前を表示**]: この設定を定義して、ユーザーにわかりやすく読みやすい設定をサーバーまたはプールに提供します。</span><span class="sxs-lookup"><span data-stu-id="29fb8-107">**Display name of the Persistent Chat pool**: Define this setting to provide a user friendly and user readable setting for the server or pool.</span></span> <span data-ttu-id="29fb8-108">この設定により、ユーザーは、完全修飾ドメイン名の理解が困難になる代わりに、表示名に基づいて特定の常設チャットサーバーまたは常設チャットサーバープールを容易に関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="29fb8-108">This setting will make it easier for your users to associate a given Persistent Chat Server or Persistent Chat Server pool based on the display name instead of a more difficult to understand fully qualified domain name.</span></span>
    
- <span data-ttu-id="29fb8-109">[**常設チャットのポート**]: 常設チャットに使用するポートを指定します。</span><span class="sxs-lookup"><span data-stu-id="29fb8-109">**Persistent Chat port**: Specify the port to use for Persistent Chat.</span></span>
    
<span data-ttu-id="29fb8-110">次のプロパティを構成または定義することによって、常設チャットサーバーまたは常設チャットサーバープールの **関連付け** 設定を編集します。</span><span class="sxs-lookup"><span data-stu-id="29fb8-110">You edit the **Associations** settings for the Persistent Chat Server or Persistent Chat Server pool by configuring or defining these properties:</span></span>
  
 <span data-ttu-id="29fb8-111">**連盟**</span><span class="sxs-lookup"><span data-stu-id="29fb8-111">**Associations**</span></span>
  
- <span data-ttu-id="29fb8-112">[ **Sql server ストア**]: リストから sql server ストアおよびオプションの名前付きインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="29fb8-112">**SQL Server store**: Select the SQL Server store and optional named instance from the list.</span></span>
    
    <span data-ttu-id="29fb8-113">[**新規**] をクリックして、新しい SQL Server ストアとオプションのインスタンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="29fb8-113">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="29fb8-114">プライマリ SQL Server ストアのミラーリングを有効にする場合は、[ **Sql server ストアミラーリングの有効化** ] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="29fb8-114">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the primary SQL Server store.</span></span>
    
    <span data-ttu-id="29fb8-115">[SQL Server ストアミラーリングの有効化] を選択した場合は、[ **ミラーリング Sql Server ストア**] の一覧からストアとインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="29fb8-115">If you chose to enable SQL Server store mirroring, select the store and instance from the list **Mirroring SQL Server store**.</span></span>
    
    <span data-ttu-id="29fb8-116">[**新規**] をクリックして、新しい SQL Server ストアとオプションのインスタンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="29fb8-116">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="29fb8-117">プライマリ SQL Server ストアの自動フェールオーバーを使用する場合は、[ **Sql server ミラーリング監視を自動フェールオーバーの有効化のために使用する** ] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="29fb8-117">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the primary SQL Server store.</span></span>
    
    <span data-ttu-id="29fb8-118">SQL Server ストアミラーリング監視を有効にして自動フェールオーバーを有効にすることを選択した場合は、一覧からストアとインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="29fb8-118">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="29fb8-119">[**新規**] をクリックして、監視ストア用の新しい SQL Server ストアとオプションのインスタンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="29fb8-119">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="29fb8-120">SQL Server の障害復旧の使用を有効にする場合は、[ **バックアップ Sql server ストアを使用して障害復旧を有効** にする] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="29fb8-120">Select the **Use backup SQL Server stores to enable disaster recovery** check box if you want to enable the use of SQL Server disaster recovery</span></span>
    
    <span data-ttu-id="29fb8-121">災害復旧の有効化を選択した場合、[**バックアップ SQL Server ストア**] リストからストアおよびインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="29fb8-121">If you chose to enable disaster recovery, select a store and instance from the **Backup SQL Server store** list.</span></span>
    
    <span data-ttu-id="29fb8-122">[**新規**] をクリックして、新しい SQL Server ストアとオプションのインスタンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="29fb8-122">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="29fb8-123">バックアップ SQL Server ミラーリングストアのミラーリングを有効にする場合は、[ **Sql server ストアミラーリングの有効化** ] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="29fb8-123">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the backup SQL Server mirroring store.</span></span>
    
    <span data-ttu-id="29fb8-124">バックアップ SQL Server ストアミラーリングの有効化を選択した場合は、[ **バックアップ Sql server ストアミラー**] の一覧からストアおよびインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="29fb8-124">If you chose to enable backup SQL Server store mirroring, select the store and instance from the list **Backup SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="29fb8-125">[**新規**] をクリックして、新しい SQL Server ストアとオプションのインスタンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="29fb8-125">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="29fb8-126">バックアップ SQL Server ストアの自動フェールオーバーを使用する場合は、[ **Sql server ミラーリング監視を自動フェールオーバーの有効化のために使用する** ] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="29fb8-126">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the backup SQL Server store.</span></span>
    
    <span data-ttu-id="29fb8-127">SQL Server ストアミラーリング監視を有効にして自動フェールオーバーを有効にすることを選択した場合は、一覧からストアとインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="29fb8-127">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="29fb8-128">[**新規**] をクリックして、監視ストア用の新しい SQL Server ストアとオプションのインスタンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="29fb8-128">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="29fb8-129">コンプライアンス データベースの使用を有効にする場合、[**コンプライアンスの有効化**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="29fb8-129">Select the **Enable compliance** check box if you want to enable the use of a compliance database</span></span>
    
    <span data-ttu-id="29fb8-130">コンプライアンスの有効化を選択した場合、[**コンプライアンス SQL Server ストア**] リストからストアおよびインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="29fb8-130">If you chose to enable compliance, select a store and instance from the **Compliance SQL Server store** list.</span></span>
    
    <span data-ttu-id="29fb8-131">[**新規**] をクリックして、新しい SQL Server ストアとオプションのインスタンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="29fb8-131">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="29fb8-132">コンプライアンス SQL Server ストアのミラーリングを有効にする場合は、[ **Sql server ストアミラーリングの有効化** ] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="29fb8-132">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="29fb8-133">SQL Server ストアミラーリングのコンプライアンスを有効にすることを選択した場合は、[ **コンプライアンス Sql server ストアミラー**] の一覧からストアとインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="29fb8-133">If you chose to enable compliance SQL Server store mirroring, select the store and instance from the list **Compliance SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="29fb8-134">[**新規**] をクリックして、新しい SQL Server ストアとオプションのインスタンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="29fb8-134">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="29fb8-135">コンプライアンス SQL Server ストアの自動フェールオーバーを使用する場合は、[ **Sql server ミラーリング監視を自動フェールオーバーの有効化のために使用する** ] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="29fb8-135">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="29fb8-136">SQL Server ストアミラーリング監視を有効にして自動フェールオーバーを有効にすることを選択した場合は、一覧からストアとインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="29fb8-136">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="29fb8-137">[**新規**] をクリックして、監視ストア用の新しい SQL Server ストアとオプションのインスタンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="29fb8-137">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="29fb8-138">コンプライアンスの有効化を選択した場合、[**バックアップ コンプライアンス SQL Server ストア**] リストからストアおよびインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="29fb8-138">If you chose to enable compliance, select a store and instance from the **Backup compliance SQL Server store** list.</span></span>
    
    <span data-ttu-id="29fb8-139">[**新規**] をクリックして、新しい SQL Server ストアとオプションのインスタンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="29fb8-139">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="29fb8-140">コンプライアンス SQL Server ストアのミラーリングを有効にする場合は、[ **Sql server ストアミラーリングの有効化** ] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="29fb8-140">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="29fb8-141">SQL Server ストアのコンプライアンスを有効にすることを選択した場合は、[ **バックアップコンプライアンス Sql Server ストアのミラー**] の一覧からストアとインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="29fb8-141">If you chose to enable compliance SQL Server store mirroring, select the store and instance from the list **Backup compliance SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="29fb8-142">[**新規**] をクリックして、新しい SQL Server ストアとオプションのインスタンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="29fb8-142">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="29fb8-143">バックアップコンプライアンス SQL Server ストアの自動フェールオーバーを使用する場合は、[ **Sql server ミラーリング監視を自動フェールオーバーの有効化のために使用する** ] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="29fb8-143">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the backup compliance SQL Server store.</span></span>
    
    <span data-ttu-id="29fb8-144">SQL Server ストアミラーリング監視を有効にして自動フェールオーバーを有効にすることを選択した場合は、一覧からストアとインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="29fb8-144">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="29fb8-145">[**新規**] をクリックして、監視ストア用の新しい SQL Server ストアとオプションのインスタンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="29fb8-145">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="29fb8-146">**ファイルストア** リストからファイルストアの場所を選択するか、[ **新規** ] をクリックして新しいファイルストアを作成します。</span><span class="sxs-lookup"><span data-stu-id="29fb8-146">**File store** Select a file store location from the list, or click **New** to create a new file store.</span></span>
    
  <span data-ttu-id="29fb8-147">[**OK**]: ダイアログでの変更を受け入れて確定します。</span><span class="sxs-lookup"><span data-stu-id="29fb8-147">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="29fb8-148">[**キャンセル**]: 変更を破棄してダイアログを閉じます。</span><span class="sxs-lookup"><span data-stu-id="29fb8-148">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="29fb8-149">[**ヘルプ**]: このヘルプ画面を表示します。</span><span class="sxs-lookup"><span data-stu-id="29fb8-149">**Help** Displays this help screen.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="29fb8-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="29fb8-150">See also</span></span>

[<span data-ttu-id="29fb8-151">Skype for Business Server 2015 での常設チャットサーバーの計画</span><span class="sxs-lookup"><span data-stu-id="29fb8-151">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="29fb8-152">常設チャットサーバーを Skype for Business Server 2015 トポロジに追加する</span><span class="sxs-lookup"><span data-stu-id="29fb8-152">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[<span data-ttu-id="29fb8-153">Skype for Business Server 2015 での常設チャットサーバーの高可用性および障害復旧の構成</span><span class="sxs-lookup"><span data-stu-id="29fb8-153">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
