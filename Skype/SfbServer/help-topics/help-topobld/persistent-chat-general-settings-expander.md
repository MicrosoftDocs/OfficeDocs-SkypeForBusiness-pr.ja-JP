---
title: 常設チャット全般設定エキスパンダー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.PersistentChatGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 275ee1ae-ca58-4963-bc95-523319f90d96
description: 次のプロパティを構成または定義して、常設チャットサーバーまたは常設チャットサーバープールの全般的な設定を編集します。
ms.openlocfilehash: d44818efa1909e0fd90e4c80fcd88b3d11a616ea
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819479"
---
# <a name="persistent-chat-general-settings-expander"></a><span data-ttu-id="d549b-103">常設チャット全般設定エキスパンダー</span><span class="sxs-lookup"><span data-stu-id="d549b-103">Persistent Chat General Settings Expander</span></span>
 
<span data-ttu-id="d549b-104">次のプロパティを構成または定義して、常設チャットサーバーまたは常設チャットサーバープールの**全般的な**設定を編集します。</span><span class="sxs-lookup"><span data-stu-id="d549b-104">You edit the **General** settings for the Persistent Chat Server or Persistent Chat Server pool by configuring or defining these properties:</span></span>
  
 <span data-ttu-id="d549b-105">**[全般]**</span><span class="sxs-lookup"><span data-stu-id="d549b-105">**General**</span></span>
  
- <span data-ttu-id="d549b-106">[ **FQDN**]: 常設チャットサーバーまたは常設チャットサーバープールの完全修飾ドメイン名を定義するには、この設定を編集します。</span><span class="sxs-lookup"><span data-stu-id="d549b-106">**FQDN**: Edit this setting to define the fully qualified domain name of your Persistent Chat Server or Persistent Chat Server pool</span></span>
    
- <span data-ttu-id="d549b-107">[**常設チャット プールの名前を表示**]: この設定を定義して、ユーザーにわかりやすく読みやすい設定をサーバーまたはプールに提供します。</span><span class="sxs-lookup"><span data-stu-id="d549b-107">**Display name of the Persistent Chat pool**: Define this setting to provide a user friendly and user readable setting for the server or pool.</span></span> <span data-ttu-id="d549b-108">この設定では、完全修飾ドメイン名の理解が困難になる代わりに、表示名に基づいて、特定の常設チャットサーバーまたは常設チャットサーバープールをユーザーが簡単に関連付けられるようになります。</span><span class="sxs-lookup"><span data-stu-id="d549b-108">This setting will make it easier for your users to associate a given Persistent Chat Server or Persistent Chat Server pool based on the display name instead of a more difficult to understand fully qualified domain name.</span></span>
    
- <span data-ttu-id="d549b-109">[**常設チャットのポート**]: 常設チャットに使用するポートを指定します。</span><span class="sxs-lookup"><span data-stu-id="d549b-109">**Persistent Chat port**: Specify the port to use for Persistent Chat.</span></span>
    
<span data-ttu-id="d549b-110">次のプロパティを構成または定義して、常設チャットサーバーまたは常設チャットサーバープールの**関連付け**設定を編集します。</span><span class="sxs-lookup"><span data-stu-id="d549b-110">You edit the **Associations** settings for the Persistent Chat Server or Persistent Chat Server pool by configuring or defining these properties:</span></span>
  
 <span data-ttu-id="d549b-111">**[関連付け]**</span><span class="sxs-lookup"><span data-stu-id="d549b-111">**Associations**</span></span>
  
- <span data-ttu-id="d549b-112">[**SQL Server ストア**]: リストから SQL Server ストアおよびオプションの名前付きインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="d549b-112">**SQL Server store**: Select the SQL Server store and optional named instance from the list.</span></span>
    
    <span data-ttu-id="d549b-113">[**新規**] をクリックして、新しい SQL Server ストアとオプションのインスタンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="d549b-113">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="d549b-114">プライマリ SQL Server ストアのミラーリングを有効にする場合は、[ **Sql server ストアのミラーリングを有効**にする] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="d549b-114">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the primary SQL Server store.</span></span>
    
    <span data-ttu-id="d549b-115">SQL Server ストアのミラーリングを有効にすることを選んだ場合は、リストの**ミラーリング SQL Server ストア**からストアとインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="d549b-115">If you chose to enable SQL Server store mirroring, select the store and instance from the list **Mirroring SQL Server store**.</span></span>
    
    <span data-ttu-id="d549b-116">[**新規**] をクリックして、新しい SQL Server ストアとオプションのインスタンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="d549b-116">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="d549b-117">プライマリ SQL Server ストアの自動フェールオーバーが必要な場合は、[ **Sql server ミラーリング監視を使用して自動フェールオーバーを有効に**する] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="d549b-117">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the primary SQL Server store.</span></span>
    
    <span data-ttu-id="d549b-118">SQL Server ストアミラーリング監視を有効にして自動フェールオーバーを有効にした場合は、一覧からストアとインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="d549b-118">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="d549b-119">[**新規**] をクリックして、監視ストア用の新しい SQL Server ストアとオプションのインスタンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="d549b-119">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="d549b-120">SQL Server の障害回復を有効にする場合は、[**バックアップ Sql server ストアを使用して障害回復を有効**にする] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="d549b-120">Select the **Use backup SQL Server stores to enable disaster recovery** check box if you want to enable the use of SQL Server disaster recovery</span></span>
    
    <span data-ttu-id="d549b-121">災害復旧の有効化を選択した場合、[**バックアップ SQL Server ストア**] リストからストアおよびインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="d549b-121">If you chose to enable disaster recovery, select a store and instance from the **Backup SQL Server store** list.</span></span>
    
    <span data-ttu-id="d549b-122">[**新規**] をクリックして、新しい SQL Server ストアとオプションのインスタンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="d549b-122">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="d549b-123">バックアップ SQL Server ミラーリングストアのミラーリングを有効にする場合は、[ **Sql server ストアのミラーリングを有効**にする] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="d549b-123">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the backup SQL Server mirroring store.</span></span>
    
    <span data-ttu-id="d549b-124">SQL Server ストアのバックアップを有効にすることを選んだ場合は、[ **Sql server ストアミラー**の一覧] からストアとインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="d549b-124">If you chose to enable backup SQL Server store mirroring, select the store and instance from the list **Backup SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="d549b-125">[**新規**] をクリックして、新しい SQL Server ストアとオプションのインスタンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="d549b-125">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="d549b-126">バックアップ SQL Server ストアの自動フェールオーバーが必要な場合は、[ **Sql server ミラーリング監視を使用して自動フェールオーバーを有効に**する] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="d549b-126">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the backup SQL Server store.</span></span>
    
    <span data-ttu-id="d549b-127">SQL Server ストアミラーリング監視を有効にして自動フェールオーバーを有効にした場合は、一覧からストアとインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="d549b-127">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="d549b-128">[**新規**] をクリックして、監視ストア用の新しい SQL Server ストアとオプションのインスタンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="d549b-128">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="d549b-129">コンプライアンス データベースの使用を有効にする場合、[**コンプライアンスの有効化**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="d549b-129">Select the **Enable compliance** check box if you want to enable the use of a compliance database</span></span>
    
    <span data-ttu-id="d549b-130">コンプライアンスの有効化を選択した場合、[**コンプライアンス SQL Server ストア**] リストからストアおよびインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="d549b-130">If you chose to enable compliance, select a store and instance from the **Compliance SQL Server store** list.</span></span>
    
    <span data-ttu-id="d549b-131">[**新規**] をクリックして、新しい SQL Server ストアとオプションのインスタンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="d549b-131">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="d549b-132">コンプライアンス SQL Server ストアのミラーリングを有効にする場合は、[ **Sql server ストアのミラーリングを有効**にする] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="d549b-132">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="d549b-133">SQL Server ストアの整合性のミラーリングを有効にすることを選んだ場合は、[**コンプライアンス対応 Sql server ストアミラー**] からストアとインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="d549b-133">If you chose to enable compliance SQL Server store mirroring, select the store and instance from the list **Compliance SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="d549b-134">[**新規**] をクリックして、新しい SQL Server ストアとオプションのインスタンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="d549b-134">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="d549b-135">コンプライアンス SQL Server ストアの自動フェールオーバーが必要な場合は、[ **Sql server ミラーリング監視を使用して自動フェールオーバーを有効に**する] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="d549b-135">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="d549b-136">SQL Server ストアミラーリング監視を有効にして自動フェールオーバーを有効にした場合は、一覧からストアとインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="d549b-136">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="d549b-137">[**新規**] をクリックして、監視ストア用の新しい SQL Server ストアとオプションのインスタンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="d549b-137">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="d549b-138">コンプライアンスの有効化を選択した場合、[**バックアップ コンプライアンス SQL Server ストア**] リストからストアおよびインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="d549b-138">If you chose to enable compliance, select a store and instance from the **Backup compliance SQL Server store** list.</span></span>
    
    <span data-ttu-id="d549b-139">[**新規**] をクリックして、新しい SQL Server ストアとオプションのインスタンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="d549b-139">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="d549b-140">コンプライアンス SQL Server ストアのミラーリングを有効にする場合は、[ **Sql server ストアのミラーリングを有効**にする] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="d549b-140">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="d549b-141">SQL Server ストアの整合性のミラーリングを有効にすることを選んだ場合は、[リスト**バックアップのコンプライアンス対応 SQL Server ストアミラー**] からストアとインスタンスを選びます。</span><span class="sxs-lookup"><span data-stu-id="d549b-141">If you chose to enable compliance SQL Server store mirroring, select the store and instance from the list **Backup compliance SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="d549b-142">[**新規**] をクリックして、新しい SQL Server ストアとオプションのインスタンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="d549b-142">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="d549b-143">バックアップコンプライアンス SQL Server ストアの自動フェールオーバーが必要な場合は、[ **Sql server ミラーリング監視を使用して自動フェールオーバーを有効に**する] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="d549b-143">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the backup compliance SQL Server store.</span></span>
    
    <span data-ttu-id="d549b-144">SQL Server ストアミラーリング監視を有効にして自動フェールオーバーを有効にした場合は、一覧からストアとインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="d549b-144">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="d549b-145">[**新規**] をクリックして、監視ストア用の新しい SQL Server ストアとオプションのインスタンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="d549b-145">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="d549b-146">**ファイルストア**リストからファイルストアの場所を選ぶか、[**新規**] をクリックして新しいファイルストアを作成します。</span><span class="sxs-lookup"><span data-stu-id="d549b-146">**File store** Select a file store location from the list, or click **New** to create a new file store.</span></span>
    
  <span data-ttu-id="d549b-147">[**OK**]: ダイアログでの変更を受け入れて確定します。</span><span class="sxs-lookup"><span data-stu-id="d549b-147">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="d549b-148">[**キャンセル**]: 変更を破棄してダイアログを閉じます。</span><span class="sxs-lookup"><span data-stu-id="d549b-148">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="d549b-149">[**ヘルプ**]: このヘルプ画面を表示します。</span><span class="sxs-lookup"><span data-stu-id="d549b-149">**Help** Displays this help screen.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d549b-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="d549b-150">See also</span></span>

[<span data-ttu-id="d549b-151">Skype for Business Server 2015 の常設チャット サーバーの計画</span><span class="sxs-lookup"><span data-stu-id="d549b-151">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="d549b-152">Skype for Business Server 2015 トポロジに常設チャットサーバーを追加する</span><span class="sxs-lookup"><span data-stu-id="d549b-152">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[<span data-ttu-id="d549b-153">Skype for Business Server 2015 での常設チャット サーバーの高可用性および障害復旧の構成</span><span class="sxs-lookup"><span data-stu-id="d549b-153">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
