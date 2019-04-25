---
title: Skype for Business Server 2015 での常設チャット データベースのバックアップと復元
ms.reviewer: ''
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
ms.openlocfilehash: a07321c7e9167e830a7af472e9022b669a45c3e7
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32222088"
---
# <a name="back-up-and-restore-persistent-chat-databases-in-skype-for-business-server-2015"></a><span data-ttu-id="12d0b-103">Skype for Business Server 2015 での常設チャット データベースのバックアップと復元</span><span class="sxs-lookup"><span data-stu-id="12d0b-103">Back up and restore Persistent Chat databases in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="12d0b-104">**の概要:** バックアップおよびビジネス サーバー 2015 の Skype での永続的なチャット サーバーのデータベースを復元する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="12d0b-104">**Summary:** Learn how to back up and restore Persistent Chat Server databases in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="12d0b-105">永続的なチャット サーバーには、履歴とコンテンツ、構成、ユーザー プロビジョニング、およびその他の関連するメタデータなど、チャット ルームのデータを格納する SQL Server データベースのソフトウェアが必要です。</span><span class="sxs-lookup"><span data-stu-id="12d0b-105">Persistent Chat Server requires SQL Server database software to store chat room data, such as history and content, configuration, user provisioning, and other relevant metadata.</span></span> <span data-ttu-id="12d0b-106">さらに、組織にアーカイブするには、永続的なチャットの活動を必要とする規制があり、オプションのコンプライアンス サービスが有効になっている場合は、SQL Server データベース ソフトウェアを使用して内容を含めチャット イベントでは、次のように、コンプライアンス データを格納参加と、部屋のままです。</span><span class="sxs-lookup"><span data-stu-id="12d0b-106">In addition, if your organization has regulations that require Persistent Chat activity to be archived, and the optional Compliance service is enabled, SQL Server database software is used to store compliance data, including chat content and events, such as joining and leaving rooms.</span></span> <span data-ttu-id="12d0b-107">チャット ルームの内容は、永続的なチャット (mgc) データベースに格納されます。</span><span class="sxs-lookup"><span data-stu-id="12d0b-107">Chat room content is stored in the Persistent Chat database (mgc).</span></span> <span data-ttu-id="12d0b-108">コンプライアンス データはコンプライアンス データベース (mgccomp) に保管されます。</span><span class="sxs-lookup"><span data-stu-id="12d0b-108">Compliance data is stored in the Compliance database (mgccomp).</span></span> <span data-ttu-id="12d0b-109">コンプライアンス データは非常に重要なビジネス データであり、定期的なバックアップが必要です。</span><span class="sxs-lookup"><span data-stu-id="12d0b-109">This is business-critical data that should be backed up regularly.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="12d0b-110">永続的なチャットですがビジネス サーバー 2015 の Skype で利用可能なビジネス サーバー 2019 の Skype でサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="12d0b-110">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="12d0b-111">同じ機能は、チームで使用できます。</span><span class="sxs-lookup"><span data-stu-id="12d0b-111">The same functionality is available in Teams.</span></span> <span data-ttu-id="12d0b-112">詳細については、[マイクロソフトのチームにビジネス用の Skype からの旅](/microsoftteams/journey-skypeforbusiness-teams)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12d0b-112">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="12d0b-113">永続的なチャットを使用する場合は、選択肢は、いずれかをチームでは、この機能を必要とするユーザーを移行するまたはビジネス サーバー 2015 の Skype を使用し続ける。</span><span class="sxs-lookup"><span data-stu-id="12d0b-113">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="back-up-the-databases"></a><span data-ttu-id="12d0b-114">データベースをバックアップする</span><span class="sxs-lookup"><span data-stu-id="12d0b-114">Back up the databases</span></span>

<span data-ttu-id="12d0b-115">永続的なチャットのデータのバックアップの 2 つの方法もあります。</span><span class="sxs-lookup"><span data-stu-id="12d0b-115">There are two ways of backing up Persistent Chat data.</span></span> 
  
- <span data-ttu-id="12d0b-116">SQL Server バックアップ</span><span class="sxs-lookup"><span data-stu-id="12d0b-116">SQL Server Backup</span></span>
    
- <span data-ttu-id="12d0b-117">永続的なチャットのデータをファイルとしてエクスポートする**エクスポート CsPersistentChatData**コマンドレットは、</span><span class="sxs-lookup"><span data-stu-id="12d0b-117">The **Export-CsPersistentChatData** cmdlet, which exports Persistent Chat data as a file</span></span>
    
<span data-ttu-id="12d0b-118">SQL Server バックアップを使用して作成されるデータには、**Export-CsPersistentChatData** で作成する場合に比べて、非常に多くのディスク容量 (場合によっては 20 倍) が必要ですが、SQL Server バックアップは管理者がよく利用する方法です。</span><span class="sxs-lookup"><span data-stu-id="12d0b-118">Data that is created by using SQL Server backup requires significantly more disk space—possibly 20 times more—than that created by the **Export-CsPersistentChatData** cmdlet, but SQL Server backup is likely to be a procedure with which you are familiar.</span></span>
  
<span data-ttu-id="12d0b-119">SQL Server バックアップ手順を使用する場合は、詳細について SQL のマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="12d0b-119">If you want to use SQL Server backup procedures, see your SQL documentation for more information.</span></span> 
  
<span data-ttu-id="12d0b-120">**Export-CsPersistentChatData** コマンドレットを使用する場合は、コマンドを次のように指定します。</span><span class="sxs-lookup"><span data-stu-id="12d0b-120">If you want to use the **Export-CsPersistentChatData** cmdlet, you can specify the command as follows:</span></span>
  
```
Export-CsPersistentChatData [-FileName <String>] <COMMON PARAMETERS>
```

<span data-ttu-id="12d0b-121">または</span><span class="sxs-lookup"><span data-stu-id="12d0b-121">or</span></span>
  
```
Export-CsPersistentChatData [-AsBytes <SwitchParameter>] <COMMON PARAMETERS>
```

<span data-ttu-id="12d0b-p103">たとえば、次に示すコマンドは、常設チャット データをサーバー atl-sql-001.contoso.com 上の常設チャット データベースからエクスポートします。エクスポートされたデータは、ファイル C:\Logs\PersistentChatData.zip に格納されます。Level パラメーターが指定されていないので、このコマンドは常設チャットの情報をすべてエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="12d0b-p103">For example, the following command exports Persistent Chat data from the Persistent Chat database located on the server atl-sql-001.contoso.com; the exported data will be stored in the file C:\Logs\PersistentChatData.zip. Because the Level parameter was not specified, the command will do a full export of the Persistent Chat information:</span></span>
  
```
Export-CsPersistentChatData -DBInstance "atl-sql-001.contoso.com\rtc" -FileName "C:\Logs\PersistentChatData.zip"
```

## <a name="restore-the-databases"></a><span data-ttu-id="12d0b-124">データベースを復元する</span><span class="sxs-lookup"><span data-stu-id="12d0b-124">Restore the databases</span></span>

<span data-ttu-id="12d0b-125">永続的なチャット データを復元する方法は、バックアップを作成するために使用する方法によって異なります。</span><span class="sxs-lookup"><span data-stu-id="12d0b-125">How you restore your Persistent Chat data depends on the method that you used to back it up.</span></span> <span data-ttu-id="12d0b-126">SQL Server バックアップ手順を使用した場合は、SQL Server 復元手順を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="12d0b-126">If you used SQL Server backup procedures, you must use SQL Server restore procedures.</span></span> <span data-ttu-id="12d0b-127">永続的なチャットのデータをバックアップするには、**エクスポート CsPersistentChatData**コマンドレットを使用する場合は、データを復元するのには**インポート CsPersistentChatData**コマンドレットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="12d0b-127">If you used the **Export-CsPersistentChatData** cmdlet to back up Persistent Chat data, then you must use the **Import-CsPersistentChatData** cmdlet to restore the data:</span></span>
  
```
Import-CsPersistentChatData -FileName <String> <COMMON PARAMETERS>
```

<span data-ttu-id="12d0b-128">または</span><span class="sxs-lookup"><span data-stu-id="12d0b-128">or</span></span>
  
```
Import-CsPersistentChatData -ByteInput <Byte > <COMMON PARAMETERS>
```
