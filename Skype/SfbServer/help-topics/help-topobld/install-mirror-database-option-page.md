---
title: ミラー データベースのインストール オプション ページ
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
- ms.lync.tb.InstallMirrorDatabaseOptionPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7500896a-14ea-4b11-aaee-be3d81314536
description: 以下のものを定義することにより、[ミラー データベースの設定] を構成します。
ms.openlocfilehash: 63e3795cc52b9b8e3601b2260df253fdcd2d9c59
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806897"
---
# <a name="install-mirror-database-option-page"></a><span data-ttu-id="919e5-103">ミラー データベースのインストール オプション ページ</span><span class="sxs-lookup"><span data-stu-id="919e5-103">Install Mirror Database Option Page</span></span>
 
<span data-ttu-id="919e5-104">以下のものを定義することにより、[**ミラー データベースの設定**] を構成します。</span><span class="sxs-lookup"><span data-stu-id="919e5-104">You configure **Mirror Database Settings** by defining the following:</span></span>
  
- <span data-ttu-id="919e5-105">[ファイル **共有のパス] を** 入力して、ミラーリングするデータベースのSQL Serverファイルの場所を定義します。</span><span class="sxs-lookup"><span data-stu-id="919e5-105">Type the **Path to file share** to define the location for the backup SQL Server files for the database being mirrored.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="919e5-106">プライマリ SQL Server (名前付きインスタンスまたは既定のインスタンス) には、ここで定義するファイル共有に対する書き込みアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="919e5-106">The primary SQL Server instance (either named instance or default instance) must have write permissions to the file share you define here.</span></span> <span data-ttu-id="919e5-107">ミラー インスタンスSQL Serverインスタンス (名前付きインスタンスまたは既定のインスタンス) は、同じファイル共有に対する読み取りアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="919e5-107">The mirror SQL Server instance (either named instance or default instance) must have read permissions to the same file share.</span></span> 
  
  <span data-ttu-id="919e5-108">[**OK**]: ダイアログでの変更を受け入れて確定します。</span><span class="sxs-lookup"><span data-stu-id="919e5-108">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="919e5-109">[**キャンセル**]: 変更を破棄してダイアログを閉じます。</span><span class="sxs-lookup"><span data-stu-id="919e5-109">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="919e5-110">[**ヘルプ**]: このヘルプ画面を表示します。</span><span class="sxs-lookup"><span data-stu-id="919e5-110">**Help** Displays this help screen.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="919e5-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="919e5-111">See also</span></span>

[<span data-ttu-id="919e5-112">Deploy SQL mirroring for Back End Server high availability in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="919e5-112">Deploy SQL mirroring for Back End Server high availability in Skype for Business Server 2015</span></span>](../../deploy/deploy-high-availability-and-disaster-recovery/sql-mirroring-for-high-availability.md)
