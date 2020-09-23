---
title: データベースのインストール オプション ページ
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: SQL Server でデータベースとログファイルを配置するための詳細オプションを構成します。 使用できるオプションは次のとおりです。
ms.openlocfilehash: 4c8c456aa1fd0e9eee150e184b4d1f7934c26b65
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215308"
---
# <a name="install-database-options-page"></a><span data-ttu-id="6267e-104">データベースのインストール オプション ページ</span><span class="sxs-lookup"><span data-stu-id="6267e-104">Install Database Options Page</span></span>

<span data-ttu-id="6267e-105">SQL Server でデータベースとログファイルを配置するための詳細オプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="6267e-105">You configure advanced options for the placement of database and log files on your SQL Server.</span></span> <span data-ttu-id="6267e-106">使用できるオプションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6267e-106">The options available are:</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6267e-107">SQL Server コンピューターでのデータおよびログファイルの配置に関する要件とポリシーに最適なオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="6267e-107">Select the option that best fits your requirements and policies pertaining to data and log file placement on your SQL Server computers.</span></span>

 <span data-ttu-id="6267e-108">[**データベースファイルの場所を自動的に決定**する]: 既定のオプションでは、SQL Server で使用可能な領域を決定するアルゴリズムを使用し、データベースおよびログファイルを配布して最適なパフォーマンスを実現します。</span><span class="sxs-lookup"><span data-stu-id="6267e-108">**Automatically determine database file location**: The default option uses an algorithm that determines the available space on the SQL Server and distributes the database and log files for optimal performance.</span></span>

 <span data-ttu-id="6267e-109">[ **Sql server インスタンスの既定値を使用**する]: このオプションを選択すると、sql server のインスタンス設定に基づいてデータベースファイルとログファイルが配置されます。</span><span class="sxs-lookup"><span data-stu-id="6267e-109">**Use SQL Server instance defaults**: Select this option to place database file and log files based on the instance settings at SQL Server.</span></span> <span data-ttu-id="6267e-110">通常、これらのオプションの管理と構成はデータベース管理者が行います。</span><span class="sxs-lookup"><span data-stu-id="6267e-110">The options are typically managed and configured by your Database Administrator.</span></span>

 <span data-ttu-id="6267e-111">**[ターゲット SQL server のパス**]: このオプションを選択すると、データベースとログファイルを配置するドライブとフォルダーへの完全なパスを入力することによって、sql server データベースとログファイルのパスを定義することができます。</span><span class="sxs-lookup"><span data-stu-id="6267e-111">**Us these path on target SQL Server**: Select this option to define your own paths for SQL Server database and log files by typing the full path to the drive and folder where the database and log files will be placed.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6267e-112">入力したパスは、パフォーマンス最適化アルゴリズムに基づいて変更されることがあります。</span><span class="sxs-lookup"><span data-stu-id="6267e-112">The paths that you enter may be modified based on performance optimization algorithms in the installation.</span></span> <span data-ttu-id="6267e-113">詳細については、「[Database Installation Using Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6267e-113">For details, see [Database Installation Using Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx).</span></span>

 <span data-ttu-id="6267e-114">[**OK**]: 変更を確定するには、[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6267e-114">**OK**: Click the OK button to commit your changes.</span></span>

 <span data-ttu-id="6267e-115">[**キャンセル**]: 変更を破棄して [データベースのインストール] 画面に戻るには、[キャンセル] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6267e-115">**Cancel**: Click Cancel to discard any changes and return to the Install Database screen.</span></span>

 <span data-ttu-id="6267e-116">[**ヘルプ**]: このヘルプ ページにアクセスするには、[ヘルプ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6267e-116">**Help**: Click the Help button to access this Help page.</span></span>

## <a name="see-also"></a><span data-ttu-id="6267e-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="6267e-117">See also</span></span>

[<span data-ttu-id="6267e-118">SQL Server データとログ ファイルの配置</span><span class="sxs-lookup"><span data-stu-id="6267e-118">SQL Server Data and Log File Placement</span></span>](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)
