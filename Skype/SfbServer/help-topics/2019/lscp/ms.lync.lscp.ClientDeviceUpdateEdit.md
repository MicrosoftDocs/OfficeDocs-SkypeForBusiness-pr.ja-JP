---
title: デバイス ログ構成の編集
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientDeviceUpdateEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: e534e6a5-fb3e-40b1-a189-fce64c42f512
ROBOTS: NOINDEX, NOFOLLOW
description: '[編集 ログ設定] ページでは、最大ログ キャッシュ サイズ、最大ログ ファイル サイズ、またはログ ファイルを削除するまでに保持する期間を指定するデバイス ログ構成を追加できます。 これらの設定は、組織の要件に従って変更できます。'
ms.openlocfilehash: ac6c341460d0e196548a86620d89f67bc51d7b4d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830297"
---
# <a name="device-log-configuration-edit"></a><span data-ttu-id="76c44-104">デバイス ログの構成: 編集</span><span class="sxs-lookup"><span data-stu-id="76c44-104">Device Log Configuration: Edit</span></span>
 
<span data-ttu-id="76c44-105">[**編集 ログ設定**] ページでは、最大ログ キャッシュ サイズ、最大ログ ファイル サイズ、またはログ ファイルを削除するまでに保持する期間を指定するデバイス ログ構成を追加できます。</span><span class="sxs-lookup"><span data-stu-id="76c44-105">You can add a device log configuration to the **Edit Log Setting** page that determines the maximum log cache size, maximum log file size, or length of time a log file is kept before it is purged.</span></span> <span data-ttu-id="76c44-106">これらの設定は、組織の要件に従って変更できます。</span><span class="sxs-lookup"><span data-stu-id="76c44-106">You can change these settings according to your organization's requirements.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="76c44-p103">ファイルを削除すると、それらはファイル システムから完全に削除されます。 ファイルを削除した後、ファイルを復旧することはできません。</span><span class="sxs-lookup"><span data-stu-id="76c44-p103">Purging files permanently removes them from the file system. After you purge a file, it cannot be recovered.</span></span> 
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="76c44-109">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="76c44-109">Tasks you can perform</span></span>

<span data-ttu-id="76c44-110">[**編集 ログ設定**] ページでは、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="76c44-110">You can perform the following tasks on the **Edit Log Setting** page:</span></span>
  
- <span data-ttu-id="76c44-111">デバイス ログ構成をグローバルに、または特定のサイトに追加します。</span><span class="sxs-lookup"><span data-stu-id="76c44-111">Add a device log configuration globally or for a particular site.</span></span>
    
- <span data-ttu-id="76c44-112">既存のデバイス ログ構成のオプションを変更します。</span><span class="sxs-lookup"><span data-stu-id="76c44-112">Modify the options for an existing device log configuration.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="76c44-113">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="76c44-113">UI Reference</span></span>

<span data-ttu-id="76c44-114">次の一覧に、このページのメニュー、コマンド、フィールド、およびプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="76c44-114">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="76c44-115">**スコープ** デバイス ログ構成のスコープ (グローバルまたはサイト) を識別します。</span><span class="sxs-lookup"><span data-stu-id="76c44-115">**Scope** Identifies the scope (Global or Site) of the device log configuration.</span></span>
    
- <span data-ttu-id="76c44-116">**名前** デバイス ログ構成の名前を追加または変更できます。</span><span class="sxs-lookup"><span data-stu-id="76c44-116">**Name** You can add or modify the name of the device log configuration.</span></span>
    
- <span data-ttu-id="76c44-117">**最大ファイル サイズ (バイト)** ログ ファイルを削除する前の最大サイズを指定できます。</span><span class="sxs-lookup"><span data-stu-id="76c44-117">**Maximum file size (bytes)** You can specify the maximum size a log file can become before it is purged.</span></span> <span data-ttu-id="76c44-118">既定値は 1,024,000 バイト (1 MB) です。</span><span class="sxs-lookup"><span data-stu-id="76c44-118">The default is 1,024,000 bytes (1 MB).</span></span>
    
- <span data-ttu-id="76c44-119">**最大キャッシュ サイズ (バイト)** キャッシュをクリアしてデータをログ ファイルに書き込む前にログ ファイル キャッシュに保持できる情報の最大量 (バイト単位) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="76c44-119">**Maximum cache size (bytes)** You can specify the maximum amount of information (in bytes) that can be held in the log file cache before that cache must be cleared and the data is written to a log file.</span></span> <span data-ttu-id="76c44-120">既定値は 512,000 バイト (0.5 MB) です。</span><span class="sxs-lookup"><span data-stu-id="76c44-120">The default is 512,000 bytes (0.5 MB).</span></span>
    
- <span data-ttu-id="76c44-121">**キャッシュをフラッシュする分数 (1 ~ 60)** ログ ファイル キャッシュに格納されている情報が実際のログ ファイルに書き込まれる頻度を指定できます。</span><span class="sxs-lookup"><span data-stu-id="76c44-121">**Minutes to flush cache (1-60)** You can specify how often information stored in the log file cache is written to the actual log file.</span></span> <span data-ttu-id="76c44-122">データがログに記録された後、キャッシュはクリアされます。</span><span class="sxs-lookup"><span data-stu-id="76c44-122">After the data is logged, the cache is cleared.</span></span> <span data-ttu-id="76c44-123">既定値は 5 分です。</span><span class="sxs-lookup"><span data-stu-id="76c44-123">The default is five minutes.</span></span>
    
- <span data-ttu-id="76c44-124">**ログ ファイルを保持する日数 (1 ~ 365)** ログ ファイルが削除される前にログ ファイルを保持する日数を指定できます。</span><span class="sxs-lookup"><span data-stu-id="76c44-124">**Days to keep log files (1-365)** You can specify the number of days the log files are kept before they are purged.</span></span> <span data-ttu-id="76c44-125">既定値は 10 日です。</span><span class="sxs-lookup"><span data-stu-id="76c44-125">The default is 10 days.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="76c44-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="76c44-126">See also</span></span>

[<span data-ttu-id="76c44-127">デバイス ログの構成</span><span class="sxs-lookup"><span data-stu-id="76c44-127">Device Log Configuration</span></span>](ms.lync.lscp.ClientDeviceCfgMain.md)
