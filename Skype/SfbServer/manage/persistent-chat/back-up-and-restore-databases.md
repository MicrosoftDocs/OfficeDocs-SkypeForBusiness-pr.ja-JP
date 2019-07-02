---
title: Skype for Business Server 2015 での常設チャット データベースのバックアップと復元
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4f2b689b-7f15-48dc-a069-da7bc8527def
description: '概要: Skype for Business Server 2015 で永続的なチャットサーバーデータベースのバックアップと復元を行う方法について説明します。'
ms.openlocfilehash: 0bb4895ef85ac9f38f2f9ef414769efcac6894b4
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2019
ms.locfileid: "35417961"
---
# <a name="back-up-and-restore-persistent-chat-databases-in-skype-for-business-server-2015"></a><span data-ttu-id="39030-103">Skype for Business Server 2015 での常設チャット データベースのバックアップと復元</span><span class="sxs-lookup"><span data-stu-id="39030-103">Back up and restore Persistent Chat databases in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="39030-104">**概要:** Skype for Business Server 2015 で永続的なチャットサーバーデータベースのバックアップと復元を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="39030-104">**Summary:** Learn how to back up and restore Persistent Chat Server databases in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="39030-105">常設チャットサーバーには、履歴とコンテンツ、構成、ユーザーのプロビジョニングなど、関連するメタデータを保存するための SQL Server データベースソフトウェアが必要です。</span><span class="sxs-lookup"><span data-stu-id="39030-105">Persistent Chat Server requires SQL Server database software to store chat room data, such as history and content, configuration, user provisioning, and other relevant metadata.</span></span> <span data-ttu-id="39030-106">また、アーカイブするための常設チャット活動を必要とする規制が組織にあり、オプションのコンプライアンスサービスが有効になっている場合、SQL Server データベースソフトウェアを使用して、チャットのコンテンツやイベントなどのコンプライアンスデータを保存することができます。会議室からの参加と退室。</span><span class="sxs-lookup"><span data-stu-id="39030-106">In addition, if your organization has regulations that require Persistent Chat activity to be archived, and the optional Compliance service is enabled, SQL Server database software is used to store compliance data, including chat content and events, such as joining and leaving rooms.</span></span> <span data-ttu-id="39030-107">チャットルームのコンテンツは、常設チャットデータベース (行う) に保存されます。</span><span class="sxs-lookup"><span data-stu-id="39030-107">Chat room content is stored in the Persistent Chat database (mgc).</span></span> <span data-ttu-id="39030-108">コンプライアンス データはコンプライアンス データベース (mgccomp) に保管されます。</span><span class="sxs-lookup"><span data-stu-id="39030-108">Compliance data is stored in the Compliance database (mgccomp).</span></span> <span data-ttu-id="39030-109">コンプライアンス データは非常に重要なビジネス データであり、定期的なバックアップが必要です。</span><span class="sxs-lookup"><span data-stu-id="39030-109">This is business-critical data that should be backed up regularly.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="39030-110">常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="39030-110">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="39030-111">Teams でも同じ機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="39030-111">The same functionality is available in Teams.</span></span> <span data-ttu-id="39030-112">詳細については、「 [Microsoft Teams のアップグレードの](/microsoftteams/upgrade-start-here)概要」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39030-112">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="39030-113">常設チャットを使用する必要がある場合は、この機能が必要なユーザーをチームに移行するか、Skype for Business Server 2015 を使い続けるかのいずれかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="39030-113">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="back-up-the-databases"></a><span data-ttu-id="39030-114">データベースをバックアップする</span><span class="sxs-lookup"><span data-stu-id="39030-114">Back up the databases</span></span>

<span data-ttu-id="39030-115">常設チャットデータをバックアップするには、2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="39030-115">There are two ways of backing up Persistent Chat data.</span></span> 
  
- <span data-ttu-id="39030-116">SQL Server バックアップ</span><span class="sxs-lookup"><span data-stu-id="39030-116">SQL Server Backup</span></span>
    
- <span data-ttu-id="39030-117">**CsPersistentChatData**コマンドレット。常設のチャットデータをファイルとしてエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="39030-117">The **Export-CsPersistentChatData** cmdlet, which exports Persistent Chat data as a file</span></span>
    
<span data-ttu-id="39030-118">SQL Server バックアップを使用して作成されるデータには、**Export-CsPersistentChatData** で作成する場合に比べて、非常に多くのディスク容量 (場合によっては 20 倍) が必要ですが、SQL Server バックアップは管理者がよく利用する方法です。</span><span class="sxs-lookup"><span data-stu-id="39030-118">Data that is created by using SQL Server backup requires significantly more disk space—possibly 20 times more—than that created by the **Export-CsPersistentChatData** cmdlet, but SQL Server backup is likely to be a procedure with which you are familiar.</span></span>
  
<span data-ttu-id="39030-119">SQL Server バックアップ手順を使用する場合は、詳細について SQL のマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="39030-119">If you want to use SQL Server backup procedures, see your SQL documentation for more information.</span></span> 
  
<span data-ttu-id="39030-120">**Export-CsPersistentChatData** コマンドレットを使用する場合は、コマンドを次のように指定します。</span><span class="sxs-lookup"><span data-stu-id="39030-120">If you want to use the **Export-CsPersistentChatData** cmdlet, you can specify the command as follows:</span></span>
  
```
Export-CsPersistentChatData [-FileName <String>] <COMMON PARAMETERS>
```

<span data-ttu-id="39030-121">または</span><span class="sxs-lookup"><span data-stu-id="39030-121">or</span></span>
  
```
Export-CsPersistentChatData [-AsBytes <SwitchParameter>] <COMMON PARAMETERS>
```

<span data-ttu-id="39030-p103">たとえば、次に示すコマンドは、常設チャット データをサーバー atl-sql-001.contoso.com 上の常設チャット データベースからエクスポートします。エクスポートされたデータは、ファイル C:\Logs\PersistentChatData.zip に格納されます。Level パラメーターが指定されていないので、このコマンドは常設チャットの情報をすべてエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="39030-p103">For example, the following command exports Persistent Chat data from the Persistent Chat database located on the server atl-sql-001.contoso.com; the exported data will be stored in the file C:\Logs\PersistentChatData.zip. Because the Level parameter was not specified, the command will do a full export of the Persistent Chat information:</span></span>
  
```
Export-CsPersistentChatData -DBInstance "atl-sql-001.contoso.com\rtc" -FileName "C:\Logs\PersistentChatData.zip"
```

## <a name="restore-the-databases"></a><span data-ttu-id="39030-124">データベースを復元する</span><span class="sxs-lookup"><span data-stu-id="39030-124">Restore the databases</span></span>

<span data-ttu-id="39030-125">常設チャットのデータを復元する方法は、バックアップに使用した方法によって異なります。</span><span class="sxs-lookup"><span data-stu-id="39030-125">How you restore your Persistent Chat data depends on the method that you used to back it up.</span></span> <span data-ttu-id="39030-126">SQL Server バックアップ手順を使用した場合は、SQL Server 復元手順を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="39030-126">If you used SQL Server backup procedures, you must use SQL Server restore procedures.</span></span> <span data-ttu-id="39030-127">**CsPersistentChatData**コマンドレットを使用して常設チャットデータをバックアップする場合は、 **CsPersistentChatData**コマンドレットを使用してデータを復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="39030-127">If you used the **Export-CsPersistentChatData** cmdlet to back up Persistent Chat data, then you must use the **Import-CsPersistentChatData** cmdlet to restore the data:</span></span>
  
```
Import-CsPersistentChatData -FileName <String> <COMMON PARAMETERS>
```

<span data-ttu-id="39030-128">または</span><span class="sxs-lookup"><span data-stu-id="39030-128">or</span></span>
  
```
Import-CsPersistentChatData -ByteInput <Byte > <COMMON PARAMETERS>
```
