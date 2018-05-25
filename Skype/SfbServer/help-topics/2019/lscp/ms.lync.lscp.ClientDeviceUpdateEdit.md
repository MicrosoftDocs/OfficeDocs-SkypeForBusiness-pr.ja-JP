---
title: デバイス ログ構成の編集
ms.author: laurawi
author: LauraWi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceUpdateEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e534e6a5-fb3e-40b1-a189-fce64c42f512
description: ログの最大キャッシュ ・ サイズ、最大ログ ファイル サイズ、またはログ ファイルがパージされる前に保持される期間の長さを決定するログ設定の編集] ページには、デバイスのログの構成を追加できます。 組織の要件に従って、これらの設定を変更することができます。
ms.openlocfilehash: 8003014f7b94824d0ef36a8d1328c6430e98d894
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2018
---
# <a name="device-log-configuration-edit"></a><span data-ttu-id="54148-104">デバイスのログの構成: 編集</span><span class="sxs-lookup"><span data-stu-id="54148-104">Device Log Configuration: Edit</span></span>
 
<span data-ttu-id="54148-105">ログの最大キャッシュ ・ サイズ、最大ログ ファイル サイズ、またはログ ファイルがパージされる前に保持される期間の長さを決定する**ログ設定の編集**] ページには、デバイスのログの構成を追加できます。</span><span class="sxs-lookup"><span data-stu-id="54148-105">You can add a device log configuration to the **Edit Log Setting** page that determines the maximum log cache size, maximum log file size, or length of time a log file is kept before it is purged.</span></span> <span data-ttu-id="54148-106">組織の要件に従って、これらの設定を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="54148-106">You can change these settings according to your organization's requirements.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="54148-p103">ファイルを削除すると、ファイル システムから完全に削除されます。ファイルを削除した後に復旧することはできません。</span><span class="sxs-lookup"><span data-stu-id="54148-p103">Purging files permanently removes them from the file system. After you purge a file, it cannot be recovered.</span></span> 
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="54148-109">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="54148-109">Tasks you can perform</span></span>

<span data-ttu-id="54148-110">[**ログ設定の編集**] ページで、次の作業を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="54148-110">You can perform the following tasks on the **Edit Log Setting** page:</span></span>
  
- <span data-ttu-id="54148-111">全体または特定のサイトは、デバイスのログの構成を追加します。</span><span class="sxs-lookup"><span data-stu-id="54148-111">Add a device log configuration globally or for a particular site.</span></span>
    
- <span data-ttu-id="54148-112">既存のデバイス ログ構成のオプションを変更します。</span><span class="sxs-lookup"><span data-stu-id="54148-112">Modify the options for an existing device log configuration.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="54148-113">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="54148-113">UI Reference</span></span>

<span data-ttu-id="54148-114">次の一覧に、このページのメニュー、コマンド、フィールド、およびプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="54148-114">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="54148-115">**スコープ**デバイスのログの構成のスコープ (グローバルまたはサイト) を識別します。</span><span class="sxs-lookup"><span data-stu-id="54148-115">**Scope** Identifies the scope (Global or Site) of the device log configuration.</span></span>
    
- <span data-ttu-id="54148-116">**名**追加したり、デバイスのログの構成の名前を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="54148-116">**Name** You can add or modify the name of the device log configuration.</span></span>
    
- <span data-ttu-id="54148-117">**ファイルの最大サイズ (バイト単位)** ログ ファイルがパージされる前になることができます最大サイズを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="54148-117">**Maximum file size (bytes)** You can specify the maximum size a log file can become before it is purged.</span></span> <span data-ttu-id="54148-118">デフォルトは、1,024,000 バイト (1 MB) です。</span><span class="sxs-lookup"><span data-stu-id="54148-118">The default is 1,024,000 bytes (1 MB).</span></span>
    
- <span data-ttu-id="54148-119">**最大キャッシュ サイズ (バイト単位)** バイト単位でキャッシュをクリアする必要があり、データがログ ファイルに書き込まれることにする前にログ ファイルのキャッシュに保持できる情報の最大量を指定できます。</span><span class="sxs-lookup"><span data-stu-id="54148-119">**Maximum cache size (bytes)** You can specify the maximum amount of information (in bytes) that can be held in the log file cache before that cache must be cleared and the data is written to a log file.</span></span> <span data-ttu-id="54148-120">既定では 512,000 バイト (0.5 MB) です。</span><span class="sxs-lookup"><span data-stu-id="54148-120">The default is 512,000 bytes (0.5 MB).</span></span>
    
- <span data-ttu-id="54148-121">**分 (1-60) のキャッシュをフラッシュするには**どのくらいの頻度を指定することがログ ファイルのキャッシュに格納された情報は、実際のログ ファイルに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="54148-121">**Minutes to flush cache (1-60)** You can specify how often information stored in the log file cache is written to the actual log file.</span></span> <span data-ttu-id="54148-122">データがログに記録した後、キャッシュがクリアされます。</span><span class="sxs-lookup"><span data-stu-id="54148-122">After the data is logged, the cache is cleared.</span></span> <span data-ttu-id="54148-123">既定では 5 分です。</span><span class="sxs-lookup"><span data-stu-id="54148-123">The default is five minutes.</span></span>
    
- <span data-ttu-id="54148-124">**(1-365) のログ ファイルを保存する日数**ログ ファイルは、パージする前に保持日数を指定できます。</span><span class="sxs-lookup"><span data-stu-id="54148-124">**Days to keep log files (1-365)** You can specify the number of days the log files are kept before they are purged.</span></span> <span data-ttu-id="54148-125">既定では 10 日です。</span><span class="sxs-lookup"><span data-stu-id="54148-125">The default is 10 days.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="54148-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="54148-126">See also</span></span>

#### 

[<span data-ttu-id="54148-127">デバイスのログの構成</span><span class="sxs-lookup"><span data-stu-id="54148-127">Device Log Configuration</span></span>](device-log-configuration.md)

