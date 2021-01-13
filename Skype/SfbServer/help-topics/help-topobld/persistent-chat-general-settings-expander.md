---
title: 常設チャット全般設定の展開
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 常設チャット サーバーまたは常設チャット サーバー プールの全般設定を編集するには、次のプロパティを構成または定義します。
ms.openlocfilehash: 5c0884f4877e622a82b58ea914ffa934eecc3291
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823857"
---
# <a name="persistent-chat-general-settings-expander"></a><span data-ttu-id="3279f-103">常設チャット全般設定エキスパンダー</span><span class="sxs-lookup"><span data-stu-id="3279f-103">Persistent Chat General Settings Expander</span></span>
 
<span data-ttu-id="3279f-104">常設チャット サーバー **または常設** チャット サーバー プールの全般設定を編集するには、次のプロパティを構成または定義します。</span><span class="sxs-lookup"><span data-stu-id="3279f-104">You edit the **General** settings for the Persistent Chat Server or Persistent Chat Server pool by configuring or defining these properties:</span></span>
  
 <span data-ttu-id="3279f-105">**全般**</span><span class="sxs-lookup"><span data-stu-id="3279f-105">**General**</span></span>
  
- <span data-ttu-id="3279f-106">**FQDN**: この設定を編集して、常設チャット サーバーまたは常設チャット サーバー プールの完全修飾ドメイン名を定義します。</span><span class="sxs-lookup"><span data-stu-id="3279f-106">**FQDN**: Edit this setting to define the fully qualified domain name of your Persistent Chat Server or Persistent Chat Server pool</span></span>
    
- <span data-ttu-id="3279f-107">[**常設チャット プールの名前を表示**]: この設定を定義して、ユーザーにわかりやすく読みやすい設定をサーバーまたはプールに提供します。</span><span class="sxs-lookup"><span data-stu-id="3279f-107">**Display name of the Persistent Chat pool**: Define this setting to provide a user friendly and user readable setting for the server or pool.</span></span> <span data-ttu-id="3279f-108">この設定により、ユーザーは、完全修飾ドメイン名を理解するのが難しくなる代わりに、表示名に基づいて特定の常設チャット サーバーまたは常設チャット サーバー プールを簡単に関連付けやすくなります。</span><span class="sxs-lookup"><span data-stu-id="3279f-108">This setting will make it easier for your users to associate a given Persistent Chat Server or Persistent Chat Server pool based on the display name instead of a more difficult to understand fully qualified domain name.</span></span>
    
- <span data-ttu-id="3279f-109">[**常設チャットのポート**]: 常設チャットに使用するポートを指定します。</span><span class="sxs-lookup"><span data-stu-id="3279f-109">**Persistent Chat port**: Specify the port to use for Persistent Chat.</span></span>
    
<span data-ttu-id="3279f-110">常設チャット サーバー **または常設** チャット サーバー プールの関連付け設定を編集するには、次のプロパティを構成または定義します。</span><span class="sxs-lookup"><span data-stu-id="3279f-110">You edit the **Associations** settings for the Persistent Chat Server or Persistent Chat Server pool by configuring or defining these properties:</span></span>
  
 <span data-ttu-id="3279f-111">**関連付け**</span><span class="sxs-lookup"><span data-stu-id="3279f-111">**Associations**</span></span>
  
- <span data-ttu-id="3279f-112">**SQL Serverストア**: リストからSQL Serverストアとオプションの名前付きインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="3279f-112">**SQL Server store**: Select the SQL Server store and optional named instance from the list.</span></span>
    
    <span data-ttu-id="3279f-113">[**新規**] をクリックして、新しい SQL Server ストアとオプションのインスタンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="3279f-113">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="3279f-114">プライマリ ストア **のミラーリングSQL Server有効** にする場合は、[ストア ミラーリングを有効にする] SQL Serverします。</span><span class="sxs-lookup"><span data-stu-id="3279f-114">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the primary SQL Server store.</span></span>
    
    <span data-ttu-id="3279f-115">ストア ミラーリングを有効にSQL Server、リストからストアとインスタンスを選択し、ストアSQL Server **します**。</span><span class="sxs-lookup"><span data-stu-id="3279f-115">If you chose to enable SQL Server store mirroring, select the store and instance from the list **Mirroring SQL Server store**.</span></span>
    
    <span data-ttu-id="3279f-116">[**新規**] をクリックして、新しい SQL Server ストアとオプションのインスタンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="3279f-116">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="3279f-117">プライマリ ミラーリング **ストアSQL Serverフェールオーバー** を自動的に実行する場合は、[ミラーリング監視を使用して自動フェールオーバーを有効にする] チェック SQL Serverします。</span><span class="sxs-lookup"><span data-stu-id="3279f-117">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the primary SQL Server store.</span></span>
    
    <span data-ttu-id="3279f-118">自動フェールオーバーを有効にSQL Serverミラーリング監視を有効にする場合は、一覧からストアとインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="3279f-118">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="3279f-119">[**新規**] をクリックして、監視ストア用の新しい SQL Server ストアとオプションのインスタンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="3279f-119">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="3279f-120">障害復旧 **の使用をSQL Server** 場合は、[バックアップ サーバー ストアを使用して障害復旧を有効にする] SQL Serverオンにします。</span><span class="sxs-lookup"><span data-stu-id="3279f-120">Select the **Use backup SQL Server stores to enable disaster recovery** check box if you want to enable the use of SQL Server disaster recovery</span></span>
    
    <span data-ttu-id="3279f-121">災害復旧の有効化を選択した場合、[**バックアップ SQL Server ストア**] リストからストアおよびインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="3279f-121">If you chose to enable disaster recovery, select a store and instance from the **Backup SQL Server store** list.</span></span>
    
    <span data-ttu-id="3279f-122">[**新規**] をクリックして、新しい SQL Server ストアとオプションのインスタンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="3279f-122">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="3279f-123">ミラーリング ストア **のSQL Serverミラーリング** を有効にする場合は、[ストア ミラーリングを有効にする] SQL Serverオンにします。</span><span class="sxs-lookup"><span data-stu-id="3279f-123">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the backup SQL Server mirroring store.</span></span>
    
    <span data-ttu-id="3279f-124">ストア ミラーリングのバックアップを有効SQL Server場合は、リストからストアとインスタンスを選択し、SQL Server **ミラーを作成します**。</span><span class="sxs-lookup"><span data-stu-id="3279f-124">If you chose to enable backup SQL Server store mirroring, select the store and instance from the list **Backup SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="3279f-125">[**新規**] をクリックして、新しい SQL Server ストアとオプションのインスタンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="3279f-125">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="3279f-126">バックアップ サーバー **ストアSQL Serverフェールオーバー** を自動的に実行する場合は、[ミラーリング監視を使用して自動フェールオーバーを有効にする] チェック SQL Serverします。</span><span class="sxs-lookup"><span data-stu-id="3279f-126">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the backup SQL Server store.</span></span>
    
    <span data-ttu-id="3279f-127">自動フェールオーバーを有効にSQL Serverミラーリング監視を有効にする場合は、一覧からストアとインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="3279f-127">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="3279f-128">[**新規**] をクリックして、監視ストア用の新しい SQL Server ストアとオプションのインスタンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="3279f-128">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="3279f-129">コンプライアンス データベースの使用を有効にする場合、[**コンプライアンスの有効化**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="3279f-129">Select the **Enable compliance** check box if you want to enable the use of a compliance database</span></span>
    
    <span data-ttu-id="3279f-130">コンプライアンスの有効化を選択した場合、[**コンプライアンス SQL Server ストア**] リストからストアおよびインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="3279f-130">If you chose to enable compliance, select a store and instance from the **Compliance SQL Server store** list.</span></span>
    
    <span data-ttu-id="3279f-131">[**新規**] をクリックして、新しい SQL Server ストアとオプションのインスタンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="3279f-131">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="3279f-132">コンプライアンス ストア **のミラーリングSQL Server有効** にする場合は、[ストアミラーリングを有効にする] SQL Serverします。</span><span class="sxs-lookup"><span data-stu-id="3279f-132">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="3279f-133">ストア のミラーリングに関するコンプライアンスSQL Server選択した場合は、[コンプライアンス] リストからストアとインスタンスSQL Server **選択します**。</span><span class="sxs-lookup"><span data-stu-id="3279f-133">If you chose to enable compliance SQL Server store mirroring, select the store and instance from the list **Compliance SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="3279f-134">[**新規**] をクリックして、新しい SQL Server ストアとオプションのインスタンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="3279f-134">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="3279f-135">コンプライアンス ポリシー **ストアのSQL Server** フェールオーバーを有効にする場合は、[ミラーリング監視を使用して自動フェールオーバーを有効にする] SQL Serverします。</span><span class="sxs-lookup"><span data-stu-id="3279f-135">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="3279f-136">自動フェールオーバーを有効にSQL Serverミラーリング監視を有効にする場合は、一覧からストアとインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="3279f-136">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="3279f-137">[**新規**] をクリックして、監視ストア用の新しい SQL Server ストアとオプションのインスタンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="3279f-137">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="3279f-138">コンプライアンスの有効化を選択した場合、[**バックアップ コンプライアンス SQL Server ストア**] リストからストアおよびインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="3279f-138">If you chose to enable compliance, select a store and instance from the **Backup compliance SQL Server store** list.</span></span>
    
    <span data-ttu-id="3279f-139">[**新規**] をクリックして、新しい SQL Server ストアとオプションのインスタンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="3279f-139">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="3279f-140">コンプライアンス ストア **のミラーリングSQL Server有効** にする場合は、[ストアミラーリングを有効にする] SQL Serverします。</span><span class="sxs-lookup"><span data-stu-id="3279f-140">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="3279f-141">ストア ミラーリングに関するコンプライアンスSQL Server選択した場合は、[バックアップ コンプライアンス] リストからストアとインスタンスSQL Server **選択します**。</span><span class="sxs-lookup"><span data-stu-id="3279f-141">If you chose to enable compliance SQL Server store mirroring, select the store and instance from the list **Backup compliance SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="3279f-142">[**新規**] をクリックして、新しい SQL Server ストアとオプションのインスタンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="3279f-142">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="3279f-143">バックアップ コンプライアンス **監視ストアSQL Serverフェールオーバー** を自動的に実行する場合は、[ミラーリング監視を使用して自動フェールオーバーを有効にする] SQL Serverします。</span><span class="sxs-lookup"><span data-stu-id="3279f-143">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the backup compliance SQL Server store.</span></span>
    
    <span data-ttu-id="3279f-144">自動フェールオーバーを有効にSQL Serverミラーリング監視を有効にする場合は、一覧からストアとインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="3279f-144">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="3279f-145">[**新規**] をクリックして、監視ストア用の新しい SQL Server ストアとオプションのインスタンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="3279f-145">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="3279f-146">**ファイル ストア** 一覧からファイル ストアの場所を選択するか、[新規] **をクリックして** 新しいファイル ストアを作成します。</span><span class="sxs-lookup"><span data-stu-id="3279f-146">**File store** Select a file store location from the list, or click **New** to create a new file store.</span></span>
    
  <span data-ttu-id="3279f-147">[**OK**]: ダイアログでの変更を受け入れて確定します。</span><span class="sxs-lookup"><span data-stu-id="3279f-147">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="3279f-148">[**キャンセル**]: 変更を破棄してダイアログを閉じます。</span><span class="sxs-lookup"><span data-stu-id="3279f-148">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="3279f-149">[**ヘルプ**]: このヘルプ画面を表示します。</span><span class="sxs-lookup"><span data-stu-id="3279f-149">**Help** Displays this help screen.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3279f-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="3279f-150">See also</span></span>

[<span data-ttu-id="3279f-151">Skype for Business Server 2015 での常設チャット サーバーの計画</span><span class="sxs-lookup"><span data-stu-id="3279f-151">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="3279f-152">Skype for Business Server 2015 トポロジへの常設チャット サーバーの追加</span><span class="sxs-lookup"><span data-stu-id="3279f-152">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[<span data-ttu-id="3279f-153">Skype for Business Server 2015 での常設チャット サーバーの高可用性と障害復旧の構成</span><span class="sxs-lookup"><span data-stu-id="3279f-153">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
