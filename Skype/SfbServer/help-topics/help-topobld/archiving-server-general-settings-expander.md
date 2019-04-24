---
title: アーカイブ サーバーの全般設定エキスパンダー
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/25/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.ArchivingGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b820af7-8d00-42e2-979c-dbae17159a08
description: トポロジ ビルダーでは、アーカイブを実行している個々のサーバーのプロパティを編集できます。そのためには、アーカイブを実行しているサーバーをコンソール ツリーで右クリックし、ツール バーの [アクション] をクリックするか、[アクション] ウィンドウでタスクをクリックしたうえで、[プロパティの編集] をクリックして以下のオプションのいずれかを変更します。
ms.openlocfilehash: 21b067e3a97e6c53ba51f4949385532a840d282e
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32250138"
---
# <a name="archiving-server-general-settings-expander"></a><span data-ttu-id="d9e83-103">アーカイブ サーバーの全般設定エキスパンダー</span><span class="sxs-lookup"><span data-stu-id="d9e83-103">Archiving Server General Settings Expander</span></span>
 
<span data-ttu-id="d9e83-104">トポロジ ビルダーでは、アーカイブを実行している個々のサーバーのプロパティを編集できます。そのためには、アーカイブを実行しているサーバーをコンソール ツリーで右クリックし、ツール バーの [**アクション**] をクリックするか、[アクション] ウィンドウでタスクをクリックしたうえで、[**プロパティの編集**] をクリックして以下のオプションのいずれかを変更します。</span><span class="sxs-lookup"><span data-stu-id="d9e83-104">In Topology Builder, you can edit the properties for an individual server running Archiving either by right-clicking the server running Archiving in the console tree and clicking **Action** in the toolbar, or by clicking a task in the Actions pane, and then clicking **Edit Properties** and changing any of the following options:</span></span>
  
- <span data-ttu-id="d9e83-105">**FQDN**。アーカイブを実行しているサーバーとして展開するサーバーの完全修飾ドメイン名 (FQDN) を変更する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="d9e83-105">**FQDN**, to change the fully qualified domain name (FQDN) of the server that you want to deploy as an Server running Archiving.</span></span>
    
- <span data-ttu-id="d9e83-p101">**SQL ストア**。アーカイブ用の SQL Server データベースで使用する SQL Server インスタンスを変更する場合に使用します。アーカイブを実行しているサーバーの SQL Server データベースを変更した場合は、変更を有効にするために、アーカイブを実行しているサーバーを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9e83-p101">**SQL store**, to change the instance of SQL Server to be used for the archiving SQL Server database. If you change the SQL Server database of a server running Archiving, you must restart the server running Archiving to make sure that the change takes effect.</span></span>
    
- <span data-ttu-id="d9e83-p102">**ファイル共有**。アーカイブ用のファイル ストアに使用するフォルダーを変更する場合に使用します。アーカイブを実行しているサーバーのファイル共有を変更する場合は、変更を有効にするために、アーカイブを実行しているサーバーを再起動する必要があります。また、アーカイブされた会議ファイルの損失を防ぐために、以前の会議ファイルを新しいファイル ストアのフォルダーに移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9e83-p102">**File share**, to change the folder to be used for the archiving file store. If you change the file share of a Server running Archiving, you must restart the Server running Archiving to make sure that the change takes effect. Additionally, you must move previous conference files to the new file store folder to avoid loss of archived conference files.</span></span>
    
> [!NOTE]
> <span data-ttu-id="d9e83-111">アーカイブを実行しているサーバーに関連付けられているプールを変更するには、アーカイブを実行しているサーバーに現在関連付けられている個々のフロントエンド プール ノードまたは存続可能ブランチ アプライアンス ノードの [**プロパティの編集**] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="d9e83-111">To change the pools associated with a server running Archiving, select the **Edit Properties** option for the individual Front End pool node or Survivable Branch Appliance node that is currently associated with the server running Archiving.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d9e83-p103">アーカイブを実行しているサーバーを以前にトポロジ ビルダー内のトポロジに追加した場合、アーカイブ ノードにはアーカイブを実行しているサーバーが含まれています。一覧にある、アーカイブを実行している任意のサーバーのプロパティを編集できます。ただし、アーカイブを実行しているサーバーのサービスのセットアップも行わない限り、インスタント メッセージングまたは Web 会議 (メッセージング) をアーカイブできません。</span><span class="sxs-lookup"><span data-stu-id="d9e83-p103">The Archiving node contains a server running Archiving if you have previously added a server running Archiving to the topology in Topology Builder. You can edit properties for any server running Archiving in the list. However, instant messaging or web conferencing (messaging) cannot be archived until you also set up the service for the server running Archiving.</span></span> 
  

