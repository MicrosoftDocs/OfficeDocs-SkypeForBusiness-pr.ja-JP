---
title: 常設チャット全般設定エキスパンダー
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PersistentChatGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 275ee1ae-ca58-4963-bc95-523319f90d96
description: 構成するか、これらのプロパティを定義することによって、永続的なチャット サーバーまたはプールの永続的なチャット サーバーの全般的な設定を編集します。
ms.openlocfilehash: 7e9f71cc1c26c30d60674e229627fd75964648ec
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2018
ms.locfileid: "19505049"
---
# <a name="persistent-chat-general-settings-expander"></a><span data-ttu-id="06116-103">常設チャット全般設定エキスパンダー</span><span class="sxs-lookup"><span data-stu-id="06116-103">Persistent Chat General Settings Expander</span></span>
 
<span data-ttu-id="06116-104">構成するか、これらのプロパティを定義することによって、永続的なチャット サーバーまたはプールの永続的なチャット サーバーの**全般的な**設定を編集します。</span><span class="sxs-lookup"><span data-stu-id="06116-104">You edit the **General** settings for the Persistent Chat Server or Persistent Chat Server pool by configuring or defining these properties:</span></span>
  
 <span data-ttu-id="06116-105">**[全般]**</span><span class="sxs-lookup"><span data-stu-id="06116-105">**General**</span></span>
  
- <span data-ttu-id="06116-106">**FQDN**: 永続的なチャット サーバーまたは永続的なチャット サーバー プールの完全修飾ドメイン名を定義するのにはこの設定を編集します。</span><span class="sxs-lookup"><span data-stu-id="06116-106">**FQDN**: Edit this setting to define the fully qualified domain name of your Persistent Chat Server or Persistent Chat Server pool</span></span>
    
- <span data-ttu-id="06116-107">[**常設チャット プールの名前を表示**]: この設定を定義して、ユーザーにわかりやすく読みやすい設定をサーバーまたはプールに提供します。</span><span class="sxs-lookup"><span data-stu-id="06116-107">**Display name of the Persistent Chat pool**: Define this setting to provide a user friendly and user readable setting for the server or pool.</span></span> <span data-ttu-id="06116-108">この設定は簡単に永続的なチャット サーバー プールの完全修飾ドメイン名を理解する困難なのではなく表示名に基づいて、特定の永続的なチャット サーバーを関連付けるには、ユーザーにします。</span><span class="sxs-lookup"><span data-stu-id="06116-108">This setting will make it easier for your users to associate a given Persistent Chat Server or Persistent Chat Server pool based on the display name instead of a more difficult to understand fully qualified domain name.</span></span>
    
- <span data-ttu-id="06116-109">[**常設チャットのポート**]: 常設チャットに使用するポートを指定します。</span><span class="sxs-lookup"><span data-stu-id="06116-109">**Persistent Chat port**: Specify the port to use for Persistent Chat.</span></span>
    
<span data-ttu-id="06116-110">構成するか、これらのプロパティを定義することによって、永続的なチャット サーバーまたは永続的なチャット サーバー プールの**関連付け**の設定を編集します。</span><span class="sxs-lookup"><span data-stu-id="06116-110">You edit the **Associations** settings for the Persistent Chat Server or Persistent Chat Server pool by configuring or defining these properties:</span></span>
  
 <span data-ttu-id="06116-111">**[関連付け]**</span><span class="sxs-lookup"><span data-stu-id="06116-111">**Associations**</span></span>
  
- <span data-ttu-id="06116-112">[**SQL Server ストア**]: リストから SQL Server ストアおよびオプションの名前付きインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="06116-112">**SQL Server store**: Select the SQL Server store and optional named instance from the list.</span></span>
    
    <span data-ttu-id="06116-113">[**新規**] をクリックして、新しい SQL Server ストアとオプションのインスタンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="06116-113">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="06116-114">プライマリ SQL Server ストアのミラーリングを有効にする場合は、**ストアを有効にする SQL Server のミラー化**] チェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="06116-114">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the primary SQL Server store.</span></span>
    
    <span data-ttu-id="06116-115">SQL Server ストアのミラーリングを有効にする] を選択した場合、 **SQL Server のミラーを格納**するリストから、ストアおよびインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="06116-115">If you chose to enable SQL Server store mirroring, select the store and instance from the list **Mirroring SQL Server store**.</span></span>
    
    <span data-ttu-id="06116-116">[**新規**] をクリックして、新しい SQL Server ストアとオプションのインスタンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="06116-116">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="06116-117">プライマリ SQL Server ストアの自動フェイル オーバーする場合は、**使用して SQL Server の自動フェイル オーバー機能を有効にする補助をミラー化**する] チェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="06116-117">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the primary SQL Server store.</span></span>
    
    <span data-ttu-id="06116-118">SQL Server ストアの自動フェイル オーバー機能を有効にするのには、ミラーリング監視をミラーリングを有効にする] を選択した場合は、ボックスの一覧からストアとインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="06116-118">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="06116-119">[**新規**] をクリックして、監視ストア用の新しい SQL Server ストアとオプションのインスタンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="06116-119">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="06116-120">SQL Server の災害復旧の使用を有効にする場合、**災害復旧を有効にするのにはバックアップの SQL Server ストアを使用する**] チェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="06116-120">Select the **Use backup SQL Server stores to enable disaster recovery** check box if you want to enable the use of SQL Server disaster recovery</span></span>
    
    <span data-ttu-id="06116-121">災害復旧の有効化を選択した場合、[**バックアップ SQL Server ストア**] リストからストアおよびインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="06116-121">If you chose to enable disaster recovery, select a store and instance from the **Backup SQL Server store** list.</span></span>
    
    <span data-ttu-id="06116-122">[**新規**] をクリックして、新しい SQL Server ストアとオプションのインスタンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="06116-122">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="06116-123">ストアをミラー化バックアップの SQL Server のミラーリングを有効にする場合は、**ストアを有効にする SQL Server のミラー化**] チェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="06116-123">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the backup SQL Server mirroring store.</span></span>
    
    <span data-ttu-id="06116-124">バックアップ SQL Server ストアのミラーリングを有効にする] を選択した場合は、**ミラーを格納する SQL Server のバックアップの**一覧から、ストアおよびインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="06116-124">If you chose to enable backup SQL Server store mirroring, select the store and instance from the list **Backup SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="06116-125">[**新規**] をクリックして、新しい SQL Server ストアとオプションのインスタンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="06116-125">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="06116-126">SQL Server のバックアップ ストアの自動フェイル オーバーする場合は、**使用して SQL Server の自動フェイル オーバー機能を有効にする補助をミラー化**する] チェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="06116-126">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the backup SQL Server store.</span></span>
    
    <span data-ttu-id="06116-127">SQL Server ストアの自動フェイル オーバー機能を有効にするのには、ミラーリング監視をミラーリングを有効にする] を選択した場合は、ボックスの一覧からストアとインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="06116-127">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="06116-128">[**新規**] をクリックして、監視ストア用の新しい SQL Server ストアとオプションのインスタンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="06116-128">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="06116-129">コンプライアンス データベースの使用を有効にする場合、[**コンプライアンスの有効化**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="06116-129">Select the **Enable compliance** check box if you want to enable the use of a compliance database</span></span>
    
    <span data-ttu-id="06116-130">コンプライアンスの有効化を選択した場合、[**コンプライアンス SQL Server ストア**] リストからストアおよびインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="06116-130">If you chose to enable compliance, select a store and instance from the **Compliance SQL Server store** list.</span></span>
    
    <span data-ttu-id="06116-131">[**新規**] をクリックして、新しい SQL Server ストアとオプションのインスタンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="06116-131">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="06116-132">準拠の SQL Server ストアのミラーリングを有効にする場合は、**ストアを有効にする SQL Server のミラー化**] チェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="06116-132">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="06116-133">準拠の SQL Server ストアのミラーリングを有効にする] を選択した場合は、**準拠の SQL Server のミラーを格納する**ボックスの一覧からストアとインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="06116-133">If you chose to enable compliance SQL Server store mirroring, select the store and instance from the list **Compliance SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="06116-134">[**新規**] をクリックして、新しい SQL Server ストアとオプションのインスタンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="06116-134">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="06116-135">準拠の SQL Server ストアの自動フェイル オーバーする場合は、**使用して SQL Server の自動フェイル オーバー機能を有効にする補助をミラー化**する] チェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="06116-135">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="06116-136">SQL Server ストアの自動フェイル オーバー機能を有効にするのには、ミラーリング監視をミラーリングを有効にする] を選択した場合は、ボックスの一覧からストアとインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="06116-136">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="06116-137">[**新規**] をクリックして、監視ストア用の新しい SQL Server ストアとオプションのインスタンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="06116-137">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="06116-138">コンプライアンスの有効化を選択した場合、[**バックアップ コンプライアンス SQL Server ストア**] リストからストアおよびインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="06116-138">If you chose to enable compliance, select a store and instance from the **Backup compliance SQL Server store** list.</span></span>
    
    <span data-ttu-id="06116-139">[**新規**] をクリックして、新しい SQL Server ストアとオプションのインスタンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="06116-139">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="06116-140">準拠の SQL Server ストアのミラーリングを有効にする場合は、**ストアを有効にする SQL Server のミラー化**] チェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="06116-140">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="06116-141">準拠の SQL Server ストアのミラーリングを有効にする] を選択した場合は、**ミラーを格納する SQL Server のバックアップ コンプライアンス**リストからストアとインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="06116-141">If you chose to enable compliance SQL Server store mirroring, select the store and instance from the list **Backup compliance SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="06116-142">[**新規**] をクリックして、新しい SQL Server ストアとオプションのインスタンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="06116-142">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="06116-143">バックアップ コンプライアンスの SQL Server ストアの自動フェイル オーバーする場合は、**使用して SQL Server の自動フェイル オーバー機能を有効にする補助をミラー化**する] チェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="06116-143">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the backup compliance SQL Server store.</span></span>
    
    <span data-ttu-id="06116-144">SQL Server ストアの自動フェイル オーバー機能を有効にするのには、ミラーリング監視をミラーリングを有効にする] を選択した場合は、ボックスの一覧からストアとインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="06116-144">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="06116-145">[**新規**] をクリックして、監視ストア用の新しい SQL Server ストアとオプションのインスタンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="06116-145">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="06116-146">**ファイルの保存**リストからファイルの保存場所を選択するか、新しいファイル ストアを作成する**新規**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="06116-146">**File store** Select a file store location from the list, or click **New** to create a new file store.</span></span>
    
 <span data-ttu-id="06116-147">[**OK**]: ダイアログでの変更を受け入れて確定します。</span><span class="sxs-lookup"><span data-stu-id="06116-147">**OK** Accepts and commits changes to the dialog.</span></span>
  
 <span data-ttu-id="06116-148">[**キャンセル**]: 変更を破棄してダイアログを閉じます。</span><span class="sxs-lookup"><span data-stu-id="06116-148">**Cancel** Discards changes and closes the dialog.</span></span>
  
 <span data-ttu-id="06116-149">[**ヘルプ**]: このヘルプ画面を表示します。</span><span class="sxs-lookup"><span data-stu-id="06116-149">**Help** Displays this help screen.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="06116-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="06116-150">See also</span></span>

[<span data-ttu-id="06116-151">Skype for Business Server 2015 の常設チャット サーバーの計画</span><span class="sxs-lookup"><span data-stu-id="06116-151">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="06116-152">ビジネス サーバー 2015 トポロジの場合、Skype に永続的なチャット サーバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="06116-152">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[<span data-ttu-id="06116-153">Skype for Business Server 2015 での常設チャット サーバーの高可用性および障害復旧の構成</span><span class="sxs-lookup"><span data-stu-id="06116-153">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)