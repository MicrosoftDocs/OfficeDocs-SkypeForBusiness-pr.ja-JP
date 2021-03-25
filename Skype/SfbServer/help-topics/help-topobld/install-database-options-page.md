---
title: データベースのインストール オプション ページ
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.InstallDatabaseOptionPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 926c47a0-3957-4892-b61a-7a4b569552c3
description: データベース ファイルとログ ファイルをサーバーに配置するための高度なオプションを構成SQL Server。 使用できるオプションは次のとおりです。
ms.openlocfilehash: 392db6eb9b882ff66a9f15e1f5c4f0918cb140a5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116075"
---
# <a name="install-database-options-page"></a><span data-ttu-id="30f55-104">データベースのインストール オプション ページ</span><span class="sxs-lookup"><span data-stu-id="30f55-104">Install Database Options Page</span></span>

<span data-ttu-id="30f55-105">データベース ファイルとログ ファイルをサーバーに配置するための高度なオプションを構成SQL Server。</span><span class="sxs-lookup"><span data-stu-id="30f55-105">You configure advanced options for the placement of database and log files on your SQL Server.</span></span> <span data-ttu-id="30f55-106">使用できるオプションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="30f55-106">The options available are:</span></span>

> [!IMPORTANT]
> <span data-ttu-id="30f55-107">コンピューター上のデータとログ ファイルの配置に関連する要件とポリシーに最も適したオプションSQL Serverします。</span><span class="sxs-lookup"><span data-stu-id="30f55-107">Select the option that best fits your requirements and policies pertaining to data and log file placement on your SQL Server computers.</span></span>

 <span data-ttu-id="30f55-108">**データベース ファイルの場所を** 自動的に決定する: 既定のオプションは、SQL Server で使用可能な領域を決定し、最適なパフォーマンスを得るデータベース ファイルとログ ファイルを配布するアルゴリズムを使用します。</span><span class="sxs-lookup"><span data-stu-id="30f55-108">**Automatically determine database file location**: The default option uses an algorithm that determines the available space on the SQL Server and distributes the database and log files for optimal performance.</span></span>

 <span data-ttu-id="30f55-109">**インスタンスSQL Server既定値を使用** する: データベース ファイルとログ ファイルをインスタンス設定に基づいて配置するには、このオプションをSQL Server。</span><span class="sxs-lookup"><span data-stu-id="30f55-109">**Use SQL Server instance defaults**: Select this option to place database file and log files based on the instance settings at SQL Server.</span></span> <span data-ttu-id="30f55-110">通常、これらのオプションの管理と構成はデータベース管理者が行います。</span><span class="sxs-lookup"><span data-stu-id="30f55-110">The options are typically managed and configured by your Database Administrator.</span></span>

 <span data-ttu-id="30f55-111">**ターゲット** SQL Server 上のこれらのパス: このオプションを選択して、SQL Server データベースとログ ファイルの独自のパスを定義するには、データベースとログ ファイルが配置されるドライブとフォルダーへの完全なパスを入力します。</span><span class="sxs-lookup"><span data-stu-id="30f55-111">**Us these path on target SQL Server**: Select this option to define your own paths for SQL Server database and log files by typing the full path to the drive and folder where the database and log files will be placed.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="30f55-112">入力したパスは、パフォーマンス最適化アルゴリズムに基づいて変更されることがあります。</span><span class="sxs-lookup"><span data-stu-id="30f55-112">The paths that you enter may be modified based on performance optimization algorithms in the installation.</span></span> <span data-ttu-id="30f55-113">詳細については、「[Database Installation Using Lync Server Management Shell](/previous-versions/office/lync-server-2013/lync-server-2013-database-installation-using-lync-server-management-shell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30f55-113">For details, see [Database Installation Using Lync Server Management Shell](/previous-versions/office/lync-server-2013/lync-server-2013-database-installation-using-lync-server-management-shell).</span></span>

 <span data-ttu-id="30f55-114">[**OK**]: 変更を確定するには、[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="30f55-114">**OK**: Click the OK button to commit your changes.</span></span>

 <span data-ttu-id="30f55-115">[**キャンセル**]: 変更を破棄して [データベースのインストール] 画面に戻るには、[キャンセル] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="30f55-115">**Cancel**: Click Cancel to discard any changes and return to the Install Database screen.</span></span>

 <span data-ttu-id="30f55-116">[**ヘルプ**]: このヘルプ ページにアクセスするには、[ヘルプ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="30f55-116">**Help**: Click the Help button to access this Help page.</span></span>

## <a name="see-also"></a><span data-ttu-id="30f55-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="30f55-117">See also</span></span>

[<span data-ttu-id="30f55-118">SQL Server データとログ ファイルの配置</span><span class="sxs-lookup"><span data-stu-id="30f55-118">SQL Server Data and Log File Placement</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement)