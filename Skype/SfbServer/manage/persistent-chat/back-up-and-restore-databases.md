---
title: Skype for Business Server 2015 での常設チャット データベースのバックアップと復元
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4f2b689b-7f15-48dc-a069-da7bc8527def
description: '概要: Skype for Business Server 2015 で常設チャット サーバー データベースをバックアップおよび復元する方法について学習します。'
ms.openlocfilehash: 2c99f5e955756020f68b51ea214858c23fee0a48
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826377"
---
# <a name="back-up-and-restore-persistent-chat-databases-in-skype-for-business-server-2015"></a><span data-ttu-id="1b22b-103">Skype for Business Server 2015 での常設チャット データベースのバックアップと復元</span><span class="sxs-lookup"><span data-stu-id="1b22b-103">Back up and restore Persistent Chat databases in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="1b22b-104">**概要:** Skype for Business Server 2015 で常設チャット サーバー データベースをバックアップおよび復元する方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="1b22b-104">**Summary:** Learn how to back up and restore Persistent Chat Server databases in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="1b22b-105">常設チャット サーバーでは、SQL Serverコンテンツ、構成、ユーザー プロビジョニング、その他の関連するメタデータなどのチャット ルーム データを格納するために、データベース ソフトウェアを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b22b-105">Persistent Chat Server requires SQL Server database software to store chat room data, such as history and content, configuration, user provisioning, and other relevant metadata.</span></span> <span data-ttu-id="1b22b-106">また、組織に常設チャットアクティビティのアーカイブを要求する規制がある場合、オプションのコンプライアンス サービスが有効になっている場合、チャット コンテンツやイベント (ルームへの参加や退出など) を含むコンプライアンス データを格納するために SQL Server データベース ソフトウェアが使用されます。</span><span class="sxs-lookup"><span data-stu-id="1b22b-106">In addition, if your organization has regulations that require Persistent Chat activity to be archived, and the optional Compliance service is enabled, SQL Server database software is used to store compliance data, including chat content and events, such as joining and leaving rooms.</span></span> <span data-ttu-id="1b22b-107">チャット ルームのコンテンツは、常設チャット データベース (mgc) に格納されます。</span><span class="sxs-lookup"><span data-stu-id="1b22b-107">Chat room content is stored in the Persistent Chat database (mgc).</span></span> <span data-ttu-id="1b22b-108">コンプライアンス データは、コンプライアンス データベース (mgccomp) に格納されます。</span><span class="sxs-lookup"><span data-stu-id="1b22b-108">Compliance data is stored in the Compliance database (mgccomp).</span></span> <span data-ttu-id="1b22b-109">これはビジネスに不可欠なデータで、定期的にバックアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b22b-109">This is business-critical data that should be backed up regularly.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="1b22b-110">常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="1b22b-110">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="1b22b-111">Teams でも同じ機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="1b22b-111">The same functionality is available in Teams.</span></span> <span data-ttu-id="1b22b-112">詳細については、「Microsoft Teams のアップグレード [の開始」を参照してください](/microsoftteams/upgrade-start-here)。</span><span class="sxs-lookup"><span data-stu-id="1b22b-112">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="1b22b-113">常設チャットを使用する必要がある場合は、この機能を必要とするユーザーを Teams に移行するか、Skype for Business Server 2015 を引き続き使用するかのどちらかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="1b22b-113">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="back-up-the-databases"></a><span data-ttu-id="1b22b-114">データベースをバックアップする</span><span class="sxs-lookup"><span data-stu-id="1b22b-114">Back up the databases</span></span>

<span data-ttu-id="1b22b-115">常設チャット データをバックアップするには、2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="1b22b-115">There are two ways of backing up Persistent Chat data.</span></span> 
  
- <span data-ttu-id="1b22b-116">SQL Server バックアップ</span><span class="sxs-lookup"><span data-stu-id="1b22b-116">SQL Server Backup</span></span>
    
- <span data-ttu-id="1b22b-117">**Export-CsPersistentChatData** コマンドレット。常設チャットのデータをファイルとしてエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="1b22b-117">The **Export-CsPersistentChatData** cmdlet, which exports Persistent Chat data as a file</span></span>
    
<span data-ttu-id="1b22b-118">SQL Server バックアップを使用して作成されるデータには **、Export-CsPersistentChatData** コマンドレットによって作成されたディスク領域よりも大幅に多くのディスク領域 (場合によっては 20 倍) が必要ですが、SQL Server バックアップは使い慣れた手順である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1b22b-118">Data that is created by using SQL Server backup requires significantly more disk space—possibly 20 times more—than that created by the **Export-CsPersistentChatData** cmdlet, but SQL Server backup is likely to be a procedure with which you are familiar.</span></span>
  
<span data-ttu-id="1b22b-119">バックアップ手順を使用するSQL Server詳細については、SQLドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b22b-119">If you want to use SQL Server backup procedures, see your SQL documentation for more information.</span></span> 
  
<span data-ttu-id="1b22b-120">**Export-CsPersistentChatData** コマンドレットを使用する場合は、次のようにコマンドを指定できます。</span><span class="sxs-lookup"><span data-stu-id="1b22b-120">If you want to use the **Export-CsPersistentChatData** cmdlet, you can specify the command as follows:</span></span>
  
```PowerShell
Export-CsPersistentChatData [-FileName <String>] <COMMON PARAMETERS>
```

<span data-ttu-id="1b22b-121">または</span><span class="sxs-lookup"><span data-stu-id="1b22b-121">or</span></span>
  
```PowerShell
Export-CsPersistentChatData [-AsBytes <SwitchParameter>] <COMMON PARAMETERS>
```

<span data-ttu-id="1b22b-122">たとえば、次のコマンドは、サーバー 上の常設チャット データベースから常設チャット データをエクスポートatl-sql-001.contoso.com。エクスポートされたデータは、エクスポートされたファイルにC:\Logs\PersistentChatData.zip。</span><span class="sxs-lookup"><span data-stu-id="1b22b-122">For example, the following command exports Persistent Chat data from the Persistent Chat database located on the server atl-sql-001.contoso.com; the exported data will be stored in the file C:\Logs\PersistentChatData.zip.</span></span> <span data-ttu-id="1b22b-123">Level パラメーターが指定されていないので、コマンドは常設チャット情報の完全なエクスポートを実行します。</span><span class="sxs-lookup"><span data-stu-id="1b22b-123">Because the Level parameter was not specified, the command will do a full export of the Persistent Chat information:</span></span>
  
```PowerShell
Export-CsPersistentChatData -DBInstance "atl-sql-001.contoso.com\rtc" -FileName "C:\Logs\PersistentChatData.zip"
```

## <a name="restore-the-databases"></a><span data-ttu-id="1b22b-124">データベースを復元する</span><span class="sxs-lookup"><span data-stu-id="1b22b-124">Restore the databases</span></span>

<span data-ttu-id="1b22b-125">常設チャット データの復元方法は、バックアップに使用した方法によって異なります。</span><span class="sxs-lookup"><span data-stu-id="1b22b-125">How you restore your Persistent Chat data depends on the method that you used to back it up.</span></span> <span data-ttu-id="1b22b-126">バックアップ手順をSQL Server場合は、復元手順SQL Server使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b22b-126">If you used SQL Server backup procedures, you must use SQL Server restore procedures.</span></span> <span data-ttu-id="1b22b-127">**Export-CsPersistentChatData** コマンドレットを使用して常設チャット データをバックアップした場合は **、Import-CsPersistentChatData** コマンドレットを使用してデータを復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b22b-127">If you used the **Export-CsPersistentChatData** cmdlet to back up Persistent Chat data, then you must use the **Import-CsPersistentChatData** cmdlet to restore the data:</span></span>
  
```PowerShell
Import-CsPersistentChatData -FileName <String> <COMMON PARAMETERS>
```

<span data-ttu-id="1b22b-128">または</span><span class="sxs-lookup"><span data-stu-id="1b22b-128">or</span></span>
  
```PowerShell
Import-CsPersistentChatData -ByteInput <Byte > <COMMON PARAMETERS>
```
