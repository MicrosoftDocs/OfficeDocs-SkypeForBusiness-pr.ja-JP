---
title: ミラー データベースのインストール オプション ページ
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.InstallMirrorDatabaseOptionPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7500896a-14ea-4b11-aaee-be3d81314536
description: ミラーデータベースの設定を構成するには、次のように定義します。
ms.openlocfilehash: 5b1cf1160fc28efc8a7787693cc5dd439ea53a17
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34284257"
---
# <a name="install-mirror-database-option-page"></a><span data-ttu-id="00bd2-103">ミラー データベースのインストール オプション ページ</span><span class="sxs-lookup"><span data-stu-id="00bd2-103">Install Mirror Database Option Page</span></span>
 
<span data-ttu-id="00bd2-104">**ミラーデータベースの設定**を構成するには、次のように定義します。</span><span class="sxs-lookup"><span data-stu-id="00bd2-104">You configure **Mirror Database Settings** by defining the following:</span></span>
  
- <span data-ttu-id="00bd2-105">**ファイル共有へのパス**を入力して、ミラーリングされるデータベースのバックアップ SQL Server ファイルの場所を定義します。</span><span class="sxs-lookup"><span data-stu-id="00bd2-105">Type the **Path to file share** to define the location for the backup SQL Server files for the database being mirrored.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="00bd2-106">プライマリ SQL Server インスタンス (名前付きインスタンスまたは既定のインスタンスのいずれか) には、ここで定義したファイル共有への書き込みアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="00bd2-106">The primary SQL Server instance (either named instance or default instance) must have write permissions to the file share you define here.</span></span> <span data-ttu-id="00bd2-107">ミラー SQL Server インスタンス (名前付きインスタンスまたは既定のインスタンス) には、同じファイル共有に対する読み取りアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="00bd2-107">The mirror SQL Server instance (either named instance or default instance) must have read permissions to the same file share.</span></span> 
  
  <span data-ttu-id="00bd2-108">[**OK**]: ダイアログでの変更を受け入れて確定します。</span><span class="sxs-lookup"><span data-stu-id="00bd2-108">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="00bd2-109">[**キャンセル**]: 変更を破棄してダイアログを閉じます。</span><span class="sxs-lookup"><span data-stu-id="00bd2-109">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="00bd2-110">[**ヘルプ**]: このヘルプ画面を表示します。</span><span class="sxs-lookup"><span data-stu-id="00bd2-110">**Help** Displays this help screen.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="00bd2-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="00bd2-111">See also</span></span>

[<span data-ttu-id="00bd2-112">Skype for Business Server 2015 でバックエンド サーバーの高可用性を実現するための SQL ミラーリングの展開</span><span class="sxs-lookup"><span data-stu-id="00bd2-112">Deploy SQL mirroring for Back End Server high availability in Skype for Business Server 2015</span></span>](../../deploy/deploy-high-availability-and-disaster-recovery/sql-mirroring-for-high-availability.md)
