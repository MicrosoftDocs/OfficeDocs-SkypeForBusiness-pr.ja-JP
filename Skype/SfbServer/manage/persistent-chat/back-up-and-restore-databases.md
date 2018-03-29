---
title: Skype for Business Server 2015 での常設チャット データベースのバックアップと復元
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4f2b689b-7f15-48dc-a069-da7bc8527def
description: '概要: は、バックアップおよびビジネス サーバー 2015 の Skype での永続的なチャット サーバーのデータベースを復元する方法を説明します。'
ms.openlocfilehash: 419085219ea995c680fe31fcca3597a884ceba5d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="back-up-and-restore-persistent-chat-databases-in-skype-for-business-server-2015"></a><span data-ttu-id="6012e-103">Skype for Business Server 2015 での常設チャット データベースのバックアップと復元</span><span class="sxs-lookup"><span data-stu-id="6012e-103">Back up and restore Persistent Chat databases in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="6012e-104">**の概要:**バックアップおよびビジネス サーバー 2015 の Skype での永続的なチャット サーバーのデータベースを復元する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6012e-104">**Summary:** Learn how to back up and restore Persistent Chat Server databases in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="6012e-105">永続的なチャット サーバーには、履歴とコンテンツ、構成、ユーザー プロビジョニング、およびその他の関連するメタデータなど、チャット ルームのデータを格納する SQL Server データベースのソフトウェアが必要です。</span><span class="sxs-lookup"><span data-stu-id="6012e-105">Persistent Chat Server requires SQL Server database software to store chat room data, such as history and content, configuration, user provisioning, and other relevant metadata.</span></span> <span data-ttu-id="6012e-106">さらに、組織にアーカイブするには、永続的なチャットの活動を必要とする規制があり、オプションのコンプライアンス サービスが有効になっている場合は、SQL Server データベース ソフトウェアを使用して内容を含めチャット イベントでは、次のように、コンプライアンス データを格納参加と、部屋のままです。</span><span class="sxs-lookup"><span data-stu-id="6012e-106">In addition, if your organization has regulations that require Persistent Chat activity to be archived, and the optional Compliance service is enabled, SQL Server database software is used to store compliance data, including chat content and events, such as joining and leaving rooms.</span></span> <span data-ttu-id="6012e-107">チャット ルームの内容は、永続的なチャット (mgc) データベースに格納されます。</span><span class="sxs-lookup"><span data-stu-id="6012e-107">Chat room content is stored in the Persistent Chat database (mgc).</span></span> <span data-ttu-id="6012e-108">コンプライアンス データはコンプライアンス データベース (mgccomp) に保管されます。</span><span class="sxs-lookup"><span data-stu-id="6012e-108">Compliance data is stored in the Compliance database (mgccomp).</span></span> <span data-ttu-id="6012e-109">コンプライアンス データは非常に重要なビジネス データであり、定期的なバックアップが必要です。</span><span class="sxs-lookup"><span data-stu-id="6012e-109">This is business-critical data that should be backed up regularly.</span></span> 
  
## <a name="back-up-the-databases"></a><span data-ttu-id="6012e-110">データベースをバックアップする</span><span class="sxs-lookup"><span data-stu-id="6012e-110">Back up the databases</span></span>

<span data-ttu-id="6012e-111">永続的なチャットのデータのバックアップの 2 つの方法もあります。</span><span class="sxs-lookup"><span data-stu-id="6012e-111">There are two ways of backing up Persistent Chat data.</span></span> 
  
- <span data-ttu-id="6012e-112">SQL Server バックアップ</span><span class="sxs-lookup"><span data-stu-id="6012e-112">SQL Server Backup</span></span>
    
- <span data-ttu-id="6012e-113">永続的なチャットのデータをファイルとしてエクスポートする**エクスポート CsPersistentChatData**コマンドレットは、</span><span class="sxs-lookup"><span data-stu-id="6012e-113">The **Export-CsPersistentChatData** cmdlet, which exports Persistent Chat data as a file</span></span>
    
<span data-ttu-id="6012e-114">SQL Server バックアップを使用して作成されるデータには、**Export-CsPersistentChatData** で作成する場合に比べて、非常に多くのディスク容量 (場合によっては 20 倍) が必要ですが、SQL Server バックアップは管理者がよく利用する方法です。</span><span class="sxs-lookup"><span data-stu-id="6012e-114">Data that is created by using SQL Server backup requires significantly more disk space—possibly 20 times more—than that created by the **Export-CsPersistentChatData** cmdlet, but SQL Server backup is likely to be a procedure with which you are familiar.</span></span>
  
<span data-ttu-id="6012e-115">SQL Server バックアップ手順を使用する場合は、詳細について SQL のマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6012e-115">If you want to use SQL Server backup procedures, see your SQL documentation for more information.</span></span> 
  
<span data-ttu-id="6012e-116">**Export-CsPersistentChatData** コマンドレットを使用する場合は、コマンドを次のように指定します。</span><span class="sxs-lookup"><span data-stu-id="6012e-116">If you want to use the **Export-CsPersistentChatData** cmdlet, you can specify the command as follows:</span></span>
  
```
Export-CsPersistentChatData [-FileName <String>] <COMMON PARAMETERS>
```

<span data-ttu-id="6012e-117">または</span><span class="sxs-lookup"><span data-stu-id="6012e-117">or</span></span>
  
```
Export-CsPersistentChatData [-AsBytes <SwitchParameter>] <COMMON PARAMETERS>
```

<span data-ttu-id="6012e-p102">たとえば、次に示すコマンドは、常設チャット データをサーバー atl-sql-001.contoso.com 上の常設チャット データベースからエクスポートします。エクスポートされたデータは、ファイル C:\Logs\PersistentChatData.zip に格納されます。Level パラメーターが指定されていないので、このコマンドは常設チャットの情報をすべてエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="6012e-p102">For example, the following command exports Persistent Chat data from the Persistent Chat database located on the server atl-sql-001.contoso.com; the exported data will be stored in the file C:\Logs\PersistentChatData.zip. Because the Level parameter was not specified, the command will do a full export of the Persistent Chat information:</span></span>
  
```
Export-CsPersistentChatData -DBInstance "atl-sql-001.contoso.com\rtc" -FileName "C:\Logs\PersistentChatData.zip"
```

## <a name="restore-the-databases"></a><span data-ttu-id="6012e-120">データベースを復元する</span><span class="sxs-lookup"><span data-stu-id="6012e-120">Restore the databases</span></span>

<span data-ttu-id="6012e-121">永続的なチャット データを復元する方法は、バックアップを作成するために使用する方法によって異なります。</span><span class="sxs-lookup"><span data-stu-id="6012e-121">How you restore your Persistent Chat data depends on the method that you used to back it up.</span></span> <span data-ttu-id="6012e-122">SQL Server バックアップ手順を使用した場合は、SQL Server 復元手順を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6012e-122">If you used SQL Server backup procedures, you must use SQL Server restore procedures.</span></span> <span data-ttu-id="6012e-123">永続的なチャットのデータをバックアップするには、**エクスポート CsPersistentChatData**コマンドレットを使用する場合は、データを復元するのには**インポート CsPersistentChatData**コマンドレットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6012e-123">If you used the **Export-CsPersistentChatData** cmdlet to back up Persistent Chat data, then you must use the **Import-CsPersistentChatData** cmdlet to restore the data:</span></span>
  
```
Import-CsPersistentChatData -FileName <String> <COMMON PARAMETERS>
```

<span data-ttu-id="6012e-124">または</span><span class="sxs-lookup"><span data-stu-id="6012e-124">or</span></span>
  
```
Import-CsPersistentChatData -ByteInput <Byte > <COMMON PARAMETERS>
```


