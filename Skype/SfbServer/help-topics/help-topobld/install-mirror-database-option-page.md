---
title: ミラー データベースのインストール オプション ページ
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.InstallMirrorDatabaseOptionPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7500896a-14ea-4b11-aaee-be3d81314536
description: ミラーデータベースの設定を構成するには、次のように定義します。
ms.openlocfilehash: dde906a5b4d9544cb357e2eed20cb7769f232be8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819799"
---
# <a name="install-mirror-database-option-page"></a><span data-ttu-id="95abc-103">ミラー データベースのインストール オプション ページ</span><span class="sxs-lookup"><span data-stu-id="95abc-103">Install Mirror Database Option Page</span></span>
 
<span data-ttu-id="95abc-104">**ミラーデータベースの設定**を構成するには、次のように定義します。</span><span class="sxs-lookup"><span data-stu-id="95abc-104">You configure **Mirror Database Settings** by defining the following:</span></span>
  
- <span data-ttu-id="95abc-105">**ファイル共有へのパス**を入力して、ミラーリングされるデータベースのバックアップ SQL Server ファイルの場所を定義します。</span><span class="sxs-lookup"><span data-stu-id="95abc-105">Type the **Path to file share** to define the location for the backup SQL Server files for the database being mirrored.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="95abc-106">プライマリ SQL Server インスタンス (名前付きインスタンスまたは既定のインスタンスのいずれか) には、ここで定義したファイル共有への書き込みアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="95abc-106">The primary SQL Server instance (either named instance or default instance) must have write permissions to the file share you define here.</span></span> <span data-ttu-id="95abc-107">ミラー SQL Server インスタンス (名前付きインスタンスまたは既定のインスタンス) には、同じファイル共有に対する読み取りアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="95abc-107">The mirror SQL Server instance (either named instance or default instance) must have read permissions to the same file share.</span></span> 
  
  <span data-ttu-id="95abc-108">[**OK**]: ダイアログでの変更を受け入れて確定します。</span><span class="sxs-lookup"><span data-stu-id="95abc-108">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="95abc-109">[**キャンセル**]: 変更を破棄してダイアログを閉じます。</span><span class="sxs-lookup"><span data-stu-id="95abc-109">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="95abc-110">[**ヘルプ**]: このヘルプ画面を表示します。</span><span class="sxs-lookup"><span data-stu-id="95abc-110">**Help** Displays this help screen.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="95abc-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="95abc-111">See also</span></span>

[<span data-ttu-id="95abc-112">Skype for Business Server 2015 でバックエンド サーバーの高可用性を実現するための SQL ミラーリングの展開</span><span class="sxs-lookup"><span data-stu-id="95abc-112">Deploy SQL mirroring for Back End Server high availability in Skype for Business Server 2015</span></span>](../../deploy/deploy-high-availability-and-disaster-recovery/sql-mirroring-for-high-availability.md)
