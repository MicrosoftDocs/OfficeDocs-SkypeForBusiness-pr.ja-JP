---
title: デバイスログ構成の編集
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.ClientDeviceUpdateEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e534e6a5-fb3e-40b1-a189-fce64c42f512
ROBOTS: NOINDEX, NOFOLLOW
description: ログの最大サイズ、最大ログファイルサイズ、ログファイルが削除されるまでの保存時間の長さを決定する [ログ設定の編集] ページに、デバイスログの構成を追加できます。 組織の要件に応じて、これらの設定を変更することができます。
ms.openlocfilehash: 6c448b886b14397f65d7ebeb5a52b90a38c7b320
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41691542"
---
# <a name="device-log-configuration-edit"></a><span data-ttu-id="e129c-104">デバイス ログの構成: 編集</span><span class="sxs-lookup"><span data-stu-id="e129c-104">Device Log Configuration: Edit</span></span>
 
<span data-ttu-id="e129c-105">ログの最大サイズ、最大ログファイルサイズ、ログファイルが削除されるまでの保存時間の長さを決定する [**ログ設定の編集**] ページに、デバイスログの構成を追加できます。</span><span class="sxs-lookup"><span data-stu-id="e129c-105">You can add a device log configuration to the **Edit Log Setting** page that determines the maximum log cache size, maximum log file size, or length of time a log file is kept before it is purged.</span></span> <span data-ttu-id="e129c-106">組織の要件に応じて、これらの設定を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="e129c-106">You can change these settings according to your organization's requirements.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="e129c-p103">ファイルを削除すると、ファイル システムから完全に削除されます。ファイルを削除した後に復旧することはできません。</span><span class="sxs-lookup"><span data-stu-id="e129c-p103">Purging files permanently removes them from the file system. After you purge a file, it cannot be recovered.</span></span> 
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="e129c-109">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="e129c-109">Tasks you can perform</span></span>

<span data-ttu-id="e129c-110">[**ログ設定の編集**] ページでは、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="e129c-110">You can perform the following tasks on the **Edit Log Setting** page:</span></span>
  
- <span data-ttu-id="e129c-111">デバイスログ構成をグローバルに、または特定のサイトに追加します。</span><span class="sxs-lookup"><span data-stu-id="e129c-111">Add a device log configuration globally or for a particular site.</span></span>
    
- <span data-ttu-id="e129c-112">既存のデバイス ログ構成のオプションを変更します。</span><span class="sxs-lookup"><span data-stu-id="e129c-112">Modify the options for an existing device log configuration.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="e129c-113">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="e129c-113">UI Reference</span></span>

<span data-ttu-id="e129c-114">次の一覧に、このページのメニュー、コマンド、フィールド、およびプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="e129c-114">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="e129c-115">**スコープ**デバイスログ構成のスコープ (グローバルまたはサイト) を識別します。</span><span class="sxs-lookup"><span data-stu-id="e129c-115">**Scope** Identifies the scope (Global or Site) of the device log configuration.</span></span>
    
- <span data-ttu-id="e129c-116">**名前**デバイスログ構成の名前を追加または変更できます。</span><span class="sxs-lookup"><span data-stu-id="e129c-116">**Name** You can add or modify the name of the device log configuration.</span></span>
    
- <span data-ttu-id="e129c-117">**最大ファイルサイズ (バイト)** ログファイルが削除されるまでの最大サイズを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="e129c-117">**Maximum file size (bytes)** You can specify the maximum size a log file can become before it is purged.</span></span> <span data-ttu-id="e129c-118">既定値は1024000バイト (1 MB) です。</span><span class="sxs-lookup"><span data-stu-id="e129c-118">The default is 1,024,000 bytes (1 MB).</span></span>
    
- <span data-ttu-id="e129c-119">**最大キャッシュサイズ (バイト)** ログファイルキャッシュ内に保持できる情報の最大量 (バイト単位) を指定して、キャッシュを消去する必要があります。データはログファイルに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="e129c-119">**Maximum cache size (bytes)** You can specify the maximum amount of information (in bytes) that can be held in the log file cache before that cache must be cleared and the data is written to a log file.</span></span> <span data-ttu-id="e129c-120">既定値は512000バイト (0.5 MB) です。</span><span class="sxs-lookup"><span data-stu-id="e129c-120">The default is 512,000 bytes (0.5 MB).</span></span>
    
- <span data-ttu-id="e129c-121">**キャッシュをフラッシュする分 (1-60)** ログファイルキャッシュに保存されている情報が実際のログファイルに書き込まれる頻度を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="e129c-121">**Minutes to flush cache (1-60)** You can specify how often information stored in the log file cache is written to the actual log file.</span></span> <span data-ttu-id="e129c-122">データをログに記録すると、キャッシュが消去されます。</span><span class="sxs-lookup"><span data-stu-id="e129c-122">After the data is logged, the cache is cleared.</span></span> <span data-ttu-id="e129c-123">既定値は5分です。</span><span class="sxs-lookup"><span data-stu-id="e129c-123">The default is five minutes.</span></span>
    
- <span data-ttu-id="e129c-124">**ログファイルを保持する日数 (1-365)** ログファイルが削除されるまでの保存日数を指定できます。</span><span class="sxs-lookup"><span data-stu-id="e129c-124">**Days to keep log files (1-365)** You can specify the number of days the log files are kept before they are purged.</span></span> <span data-ttu-id="e129c-125">既定値は10日です。</span><span class="sxs-lookup"><span data-stu-id="e129c-125">The default is 10 days.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e129c-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="e129c-126">See also</span></span>

[<span data-ttu-id="e129c-127">デバイス ログの構成</span><span class="sxs-lookup"><span data-stu-id="e129c-127">Device Log Configuration</span></span>](ms.lync.lscp.ClientDeviceCfgMain.md)
